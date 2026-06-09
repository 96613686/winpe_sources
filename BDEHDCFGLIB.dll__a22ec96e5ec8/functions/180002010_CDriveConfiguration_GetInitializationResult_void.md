# CDriveConfiguration::GetInitializationResult(void)

- ea: `0x180002010`
- end: `0x180002014`
- name: `?GetInitializationResult@CDriveConfiguration@@QEAAJXZ`
- size: `4`
- prototype: `__int64 __fastcall(CDriveConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::GetInitializationResult(CDriveConfiguration *this)
{
  return *((unsigned int *)this + 1);
}

```

## disassembly

```asm
0x180002010  mov     eax, [rcx+4]
0x180002013  retn
```
