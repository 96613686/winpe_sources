# WPP_SF_sid

- ea: `0x180004a04`
- end: `0x180004a62`
- name: `WPP_SF_sid`
- size: `94`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180003c80`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180004a57`
- `ntdll!EtwTraceMessage` at `0x180004a57`

## string_xrefs

- `0x180004a40`: `ServiceMain`

## pseudocode

```c
__int64 __fastcall WPP_SF_sid(__int64 a1)
{
  return EtwTraceMessage(a1, 43, WPP_c500ddf3cb7e33b2855b0d42471a40ca_Traceguids);
}

```

## disassembly

```asm
0x180004a04  mov     r11, rsp
0x180004a07  sub     rsp, 68h
0x180004a0b  mov     qword ptr [r11-18h], 0
0x180004a13  lea     rax, [r11+30h]
0x180004a17  mov     qword ptr [r11-20h], 4
0x180004a1f  lea     r8, WPP_c500ddf3cb7e33b2855b0d42471a40ca_Traceguids
0x180004a26  mov     [r11-28h], rax
0x180004a2a  mov     r9d, 1Fh
0x180004a30  mov     qword ptr [r11-30h], 8
0x180004a38  lea     rax, [r11+28h]
0x180004a3c  mov     [r11-38h], rax
0x180004a40  lea     rax, aServicemain_0; "ServiceMain"
0x180004a47  mov     qword ptr [r11-40h], 0Ch
0x180004a4f  lea     edx, [r9+0Ch]
0x180004a53  mov     [r11-48h], rax
0x180004a57  call    cs:__imp_EtwTraceMessage
0x180004a5d  add     rsp, 68h
0x180004a61  retn
```
