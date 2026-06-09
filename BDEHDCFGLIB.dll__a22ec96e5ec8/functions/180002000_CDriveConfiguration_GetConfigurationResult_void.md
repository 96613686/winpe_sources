# CDriveConfiguration::GetConfigurationResult(void)

- ea: `0x180002000`
- end: `0x180002004`
- name: `?GetConfigurationResult@CDriveConfiguration@@QEAAJXZ`
- size: `4`
- prototype: `__int64 __fastcall(CDriveConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::GetConfigurationResult(CDriveConfiguration *this)
{
  return *((unsigned int *)this + 2);
}

```

## disassembly

```asm
0x180002000  mov     eax, [rcx+8]
0x180002003  retn
```
