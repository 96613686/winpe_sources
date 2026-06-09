# CDriveConfiguration::Initialized(void)

- ea: `0x180002020`
- end: `0x180002023`
- name: `?Initialized@CDriveConfiguration@@QEAA_NXZ`
- size: `3`
- prototype: `bool __fastcall(CDriveConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
bool __fastcall CDriveConfiguration::Initialized(CDriveConfiguration *this)
{
  return *(_BYTE *)this;
}

```

## disassembly

```asm
0x180002020  mov     al, [rcx]
0x180002022  retn
```
