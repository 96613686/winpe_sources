# _IsScanForUpdatesEnabled_::_1_::catch$16

- ea: `0x18004cfd5`
- end: `0x18004d013`
- name: `_IsScanForUpdatesEnabled_::_1_::catch$16`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180022724`

## string_xrefs

- `0x18004cfe9`: `Error getting ScanForUpdates scheduled task info`
- `0x18004cff0`: `onecoreuap\enduser\winstore\servicescommon\lib\commonsettings.cpp`

## pseudocode

```c
__int64 __fastcall IsScanForUpdatesEnabled_::_1_::catch_16(__int64 a1, __int64 a2)
{
  const char *v3; // [rsp+20h] [rbp-38h]

  wil::details::in1diag3::Log_CaughtExceptionMsg(
    *(wil::details::in1diag3 **)(a2 + 504),
    (void *)0x24,
    (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\commonsettings.cpp",
    "Error getting ScanForUpdates scheduled task info",
    v3);
  return 0;
}

```

## disassembly

```asm
0x18004cfd5  mov     [rsp+arg_8], rdx
0x18004cfda  push    rbp
0x18004cfdb  sub     rsp, 50h
0x18004cfdf  mov     rbp, rdx
0x18004cfe2  mov     rcx, [rbp+1F8h]; this
0x18004cfe9  lea     r9, aErrorGettingSc; "Error getting ScanForUpdates scheduled "...
0x18004cff0  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\services"...
0x18004cff7  mov     edx, 24h ; '$'; void *
0x18004cffc  call    ?Log_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Log_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x18004d001  nop
0x18004d002  mov     rax, 0
0x18004d00c  add     rsp, 50h
0x18004d010  pop     rbp
0x18004d011  retn
```
