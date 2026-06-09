# CDriveConfiguration::GetShrinkSize(void)

- ea: `0x18000f940`
- end: `0x18000f948`
- name: `?GetShrinkSize@CDriveConfiguration@@QEAA_KXZ`
- size: `8`
- prototype: `unsigned __int64 __fastcall(CDriveConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
unsigned __int64 __fastcall CDriveConfiguration::GetShrinkSize(CDriveConfiguration *this)
{
  return *((_QWORD *)this + 145);
}

```

## disassembly

```asm
0x18000f940  mov     rax, [rcx+488h]
0x18000f947  retn
```
