# CDriveConfiguration::ActionRequiresShrink(void)

- ea: `0x18000f200`
- end: `0x18000f208`
- name: `?ActionRequiresShrink@CDriveConfiguration@@QEAA_NXZ`
- size: `8`
- prototype: `bool __fastcall(CDriveConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
bool __fastcall CDriveConfiguration::ActionRequiresShrink(CDriveConfiguration *this)
{
  return *((_DWORD *)this + 16) == 1;
}

```

## disassembly

```asm
0x18000f200  cmp     dword ptr [rcx+40h], 1
0x18000f204  setz    al
0x18000f207  retn
```
