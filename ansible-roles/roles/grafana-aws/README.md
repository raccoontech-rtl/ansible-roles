# Grafana AWS 배포 Ansible Role

이 Ansible Role은 AWS 환경에서 Grafana를 자동으로 배포하고 구성하는 데 사용됩니다.

## 개요

이 Role은 다음을 수행합니다:
- AWS EC2 인스턴스 생성 및 구성
- Grafana 설치 및 설정
- 보안 그룹 및 IAM 역할 구성
- 모니터링 및 로깅 설정

## 요구사항

- Ansible 2.9+
- boto3 Python 라이브러리
- AWS 자격 증명 (Access Key, Secret Key)
- 대상 서버: Ubuntu 20.04 LTS

## 변수

### 필수 변수

```yaml
aws_region: "ap-northeast-2"
instance_type: "t3.medium"
vpc_id: "vpc-xxxxxxxxx"
subnet_id: "subnet-xxxxxxxxx"
key_name: "your-key-pair"
```

### 선택적 변수

```yaml
grafana_version: "9.5.0"
grafana_port: 3000
admin_user: "admin"
```

## 사용법

```bash
# Playbook 실행
ansible-playbook -i inventory playbook.yml

# 특정 태그로 실행
ansible-playbook -i inventory playbook.yml --tags "deploy"
```

## 보안 고려사항

- 프로덕션 환경에서는 반드시 Vault를 사용하여 민감한 정보를 암호화하세요
- 보안 그룹을 최소 권한 원칙에 따라 구성하세요
- 정기적인 보안 업데이트를 수행하세요

## 라이센스

MIT License

## 지원

기술 지원이 필요한 경우 DevOps팀에 문의하세요.
