# [thunk]:PolicyModel::CFilePathRule::`vector deleting destructor'`adjustor{8}' (uint)

- ea: `0x14000ed30`
- end: `0x14000ed39`
- name: `??_ECFilePathRule@PolicyModel@@W7EAAPEAXI@Z`
- size: `9`
- prototype: `void *__fastcall(__int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ed40`

## pseudocode

```c
void *__fastcall PolicyModel::CFilePathRule::`vector deleting destructor'(__int64 a1, unsigned int a2)
{
  return PolicyModel::CFilePathRule::`scalar deleting destructor'((PolicyModel::CFilePathRule *)(a1 - 8), a2);
}

```

## disassembly

```asm
0x14000ed30  sub     rcx, 8; this
0x14000ed34  jmp     ??_GCFilePathRule@PolicyModel@@UEAAPEAXI@Z; PolicyModel::CFilePathRule::`scalar deleting destructor'(uint)
```
