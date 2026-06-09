# CopyAcceleratorFeatures::FeaturesNotificationCallback(void *,tagMP_CONFIG_ORIGIN)

- ea: `0x140020730`
- end: `0x140020745`
- name: `?FeaturesNotificationCallback@CopyAcceleratorFeatures@@CAXPEAXW4tagMP_CONFIG_ORIGIN@@@Z`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x140020800`
- `0x1400208f4`

## pseudocode

```c
void CopyAcceleratorFeatures::FeaturesNotificationCallback()
{
  CopyAcceleratorFeatures *Instance; // rax

  Instance = CopyAcceleratorFeatures::GetInstance();
  CopyAcceleratorFeatures::UpdateCancellableCopySupport(Instance);
}

```

## disassembly

```asm
0x140020730  sub     rsp, 28h
0x140020734  call    ?GetInstance@CopyAcceleratorFeatures@@SAAEAV1@XZ; CopyAcceleratorFeatures::GetInstance(void)
0x140020739  mov     rcx, rax; this
0x14002073c  add     rsp, 28h
0x140020740  jmp     ?UpdateCancellableCopySupport@CopyAcceleratorFeatures@@AEAAXXZ; CopyAcceleratorFeatures::UpdateCancellableCopySupport(void)
```
