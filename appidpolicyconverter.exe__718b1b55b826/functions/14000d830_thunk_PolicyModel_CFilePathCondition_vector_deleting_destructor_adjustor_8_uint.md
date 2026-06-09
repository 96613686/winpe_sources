# [thunk]:PolicyModel::CFilePathCondition::`vector deleting destructor'`adjustor{8}' (uint)

- ea: `0x14000d830`
- end: `0x14000d839`
- name: `??_ECFilePathCondition@PolicyModel@@W7EAAPEAXI@Z`
- size: `9`
- prototype: `void *__fastcall(__int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000d880`

## pseudocode

```c
void *__fastcall PolicyModel::CFilePathCondition::`vector deleting destructor'(__int64 a1, unsigned int a2)
{
  return PolicyModel::CFilePathCondition::`scalar deleting destructor'((PolicyModel::CFilePathCondition *)(a1 - 8), a2);
}

```

## disassembly

```asm
0x14000d830  sub     rcx, 8; this
0x14000d834  jmp     ??_GCFilePathCondition@PolicyModel@@UEAAPEAXI@Z; PolicyModel::CFilePathCondition::`scalar deleting destructor'(uint)
```
