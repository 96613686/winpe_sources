# [thunk]:PolicyModel::CFilePath::`vector deleting destructor'`adjustor{8}' (uint)

- ea: `0x14000d820`
- end: `0x14000d829`
- name: `??_ECFilePath@PolicyModel@@W7EAAPEAXI@Z`
- size: `9`
- prototype: `void *__fastcall(__int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000d840`

## pseudocode

```c
void *__fastcall PolicyModel::CFilePath::`vector deleting destructor'(__int64 a1, unsigned int a2)
{
  return PolicyModel::CFilePath::`scalar deleting destructor'((PolicyModel::CFilePath *)(a1 - 8), a2);
}

```

## disassembly

```asm
0x14000d820  sub     rcx, 8; this
0x14000d824  jmp     ??_GCFilePath@PolicyModel@@UEAAPEAXI@Z; PolicyModel::CFilePath::`scalar deleting destructor'(uint)
```
