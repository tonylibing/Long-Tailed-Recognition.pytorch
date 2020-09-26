# Long-Tailed image Classification

This project is built on top of [Decoupling Representation and Classifier for Long-Tailed Recognition (ICLR 2020)](https://github.com/facebookresearch/classifier-balancing). The main body of the proposed Causal-TDE is under [./models/CausalNormClassifier.py](models/CausalNormClassifier.py) and [run_networks.py](run_networks.py) 


### Training
For ImageNet_LT: 
```bash
python main.py --cfg ./config/ImageNet_LT/causal_norm.yaml
```

For Long-Tailed CIFAR-10 using ResNet32:
```bash
python main.py --cfg ./config/CIFAR10_LT/causal_norm_32.yaml
```

For Long-Tailed CIFAR-10 using ResNext50:
```bash
python main.py --cfg ./config/CIFAR10_LT/causal_norm.yaml
```

For Long-Tailed CIFAR-100 using ResNet32:
```bash
python main.py --cfg ./config/CIFAR100_LT/causal_norm_32.yaml
```

For Long-Tailed CIFAR-100 using ResNext50:
```bash
python main.py --cfg ./config/CIFAR100_LT/causal_norm.yaml
```

If you want to change any hyper-parameter, you can find them in the corresponding yaml config file. **IMPORTANT: if you just want to change the TDE trade-off parameter alpha, you don't need to re-train the model, you can directly use different alphas during testing, because it's not involved in training**.

### Testing
For ImageNet_LT: 
```bash
python main.py --cfg ./config/ImageNet_LT/causal_norm.yaml --test --model_dir ./logs/ImageNet_LT/models/your_model
```

For Long-Tailed CIFAR-10 using ResNet32:
```bash
python main.py --cfg ./config/CIFAR10_LT/causal_norm_32.yaml --test --model_dir ./logs/ImageNet_LT/models/your_model
```

For Long-Tailed CIFAR-10 using ResNext50:
```bash
python main.py --cfg ./config/CIFAR10_LT/causal_norm.yaml --test --model_dir ./logs/ImageNet_LT/models/your_model
```

For Long-Tailed CIFAR-100 using ResNet32:
```bash
python main.py --cfg ./config/CIFAR100_LT/causal_norm_32.yaml --test --model_dir ./logs/ImageNet_LT/models/your_model
```

For Long-Tailed CIFAR-100 using ResNext50:
```bash
python main.py --cfg ./config/CIFAR100_LT/causal_norm.yaml --test --model_dir ./logs/ImageNet_LT/models/your_model
```

### Results

![alt text](imagenet-lt.png "from 'Long-Tailed Classification by Keeping the Good and Removing the Bad Momentum Causal Effect'")

![alt text](long-tailed-cifar.png "from 'Long-Tailed Classification by Keeping the Good and Removing the Bad Momentum Causal Effect'")