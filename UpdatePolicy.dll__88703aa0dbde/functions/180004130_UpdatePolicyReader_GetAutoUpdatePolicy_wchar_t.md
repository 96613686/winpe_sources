# UpdatePolicyReader::GetAutoUpdatePolicy(wchar_t * *)

- ea: `0x180004130`
- end: `0x18000413f`
- name: `?GetAutoUpdatePolicy@UpdatePolicyReader@@SAJPEAPEA_W@Z`
- size: `15`
- prototype: `__int64 __fastcall(wchar_t **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x18000448c`

## string_xrefs

- `0x180004133`: `GetAutoUpdatePolicy`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::GetAutoUpdatePolicy(wchar_t **a1)
{
  return UndockedModuleForwarder::InvokeExportMethod<long,wchar_t * *>(a1, "GetAutoUpdatePolicy", a1);
}

```

## disassembly

```asm
0x180004130  mov     r8, rcx
0x180004133  lea     rdx, aGetautoupdatep_0; "GetAutoUpdatePolicy"
0x18000413a  jmp     ??$InvokeExportMethod@JPEAPEA_W@UndockedModuleForwarder@@QEAAJPEBDPEAPEA_W@Z; UndockedModuleForwarder::InvokeExportMethod<long,wchar_t * *>(char const *,wchar_t * *)
```
