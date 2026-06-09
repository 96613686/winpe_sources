# CDriveConfiguration::GetActionType(void)

- ea: `0x18000f8d0`
- end: `0x18000f8d4`
- name: `?GetActionType@CDriveConfiguration@@QEAA?AW4BDECFG_ACTION_TYPE@@XZ`
- size: `4`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::GetActionType(__int64 a1)
{
  return *(unsigned int *)(a1 + 64);
}

```

## disassembly

```asm
0x18000f8d0  mov     eax, [rcx+40h]
0x18000f8d3  retn
```
