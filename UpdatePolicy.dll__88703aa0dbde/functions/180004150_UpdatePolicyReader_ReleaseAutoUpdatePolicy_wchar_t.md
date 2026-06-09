# UpdatePolicyReader::ReleaseAutoUpdatePolicy(wchar_t * *)

- ea: `0x180004150`
- end: `0x18000415f`
- name: `?ReleaseAutoUpdatePolicy@UpdatePolicyReader@@SAJPEAPEA_W@Z`
- size: `15`
- prototype: `__int64 __fastcall(wchar_t **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x18000448c`

## string_xrefs

- `0x180004153`: `ReleaseAutoUpdatePolicy`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReleaseAutoUpdatePolicy(wchar_t **a1)
{
  return UndockedModuleForwarder::InvokeExportMethod<long,wchar_t * *>(a1, "ReleaseAutoUpdatePolicy", a1);
}

```

## disassembly

```asm
0x180004150  mov     r8, rcx
0x180004153  lea     rdx, aReleaseautoupd_0; "ReleaseAutoUpdatePolicy"
0x18000415a  jmp     ??$InvokeExportMethod@JPEAPEA_W@UndockedModuleForwarder@@QEAAJPEBDPEAPEA_W@Z; UndockedModuleForwarder::InvokeExportMethod<long,wchar_t * *>(char const *,wchar_t * *)
```
