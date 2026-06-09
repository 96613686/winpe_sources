# CDriveConfiguration::ActionRequiresCreate(void)

- ea: `0x18000f1d0`
- end: `0x18000f1de`
- name: `?ActionRequiresCreate@CDriveConfiguration@@QEAA_NXZ`
- size: `14`
- prototype: `bool __fastcall(CDriveConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
bool __fastcall CDriveConfiguration::ActionRequiresCreate(CDriveConfiguration *this)
{
  return ((*((_DWORD *)this + 16) - 1) & 0xFFFFFFFD) == 0;
}

```

## disassembly

```asm
0x18000f1d0  mov     eax, [rcx+40h]
0x18000f1d3  dec     eax
0x18000f1d5  test    eax, 0FFFFFFFDh
0x18000f1da  setz    al
0x18000f1dd  retn
```
