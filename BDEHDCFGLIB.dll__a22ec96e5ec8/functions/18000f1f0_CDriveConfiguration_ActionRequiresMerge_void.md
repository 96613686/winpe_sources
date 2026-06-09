# CDriveConfiguration::ActionRequiresMerge(void)

- ea: `0x18000f1f0`
- end: `0x18000f1f8`
- name: `?ActionRequiresMerge@CDriveConfiguration@@QEAA_NXZ`
- size: `8`
- prototype: `bool __fastcall(CDriveConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
bool __fastcall CDriveConfiguration::ActionRequiresMerge(CDriveConfiguration *this)
{
  return *((_DWORD *)this + 16) != 0;
}

```

## disassembly

```asm
0x18000f1f0  cmp     dword ptr [rcx+40h], 0
0x18000f1f4  setnz   al
0x18000f1f7  retn
```
