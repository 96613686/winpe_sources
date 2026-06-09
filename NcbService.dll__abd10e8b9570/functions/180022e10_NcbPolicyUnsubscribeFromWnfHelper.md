# NcbPolicyUnsubscribeFromWnfHelper

- ea: `0x180022e10`
- end: `0x180022e5e`
- name: `NcbPolicyUnsubscribeFromWnfHelper`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017d00`
- `0x180022ddc`

## callees

- `0x18000a0a0`
- `0x180022e10`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180022e20`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180022e20`

## string_xrefs

- `0x180022e38`: `NcbPolicy: RtlUnsubscribeWnfNotificationWaitForCompletion failed with status - `

## pseudocode

```c
__int64 __fastcall NcbPolicyUnsubscribeFromWnfHelper(_QWORD *a1)
{
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  int v5; // ebx

  v2 = RtlUnsubscribeWnfNotificationWaitForCompletion(*a1);
  v5 = v2;
  if ( v2 < 0 && (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(
      v4,
      v3,
      L"NcbPolicy: RtlUnsubscribeWnfNotificationWaitForCompletion failed with status - ",
      (unsigned int)v2);
  *a1 = 0;
  return (v5 >> 31) & 0x1F;
}

```

## disassembly

```asm
0x180022e10  mov     [rsp+arg_0], rbx
0x180022e15  push    rdi
0x180022e16  sub     rsp, 20h
0x180022e1a  mov     rdi, rcx
0x180022e1d  mov     rcx, [rcx]
0x180022e20  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180022e26  mov     ebx, eax
0x180022e28  test    eax, eax
0x180022e2a  jns     short loc_180022E44
0x180022e2c  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180022e33  jz      short loc_180022E44
0x180022e35  mov     r9d, eax
0x180022e38  lea     r8, aNcbpolicyRtlun; "NcbPolicy: RtlUnsubscribeWnfNotificatio"...
0x180022e3f  call    McTemplateU0zq_EventWriteTransfer
0x180022e44  sar     ebx, 1Fh
0x180022e47  and     ebx, 1Fh
0x180022e4a  mov     qword ptr [rdi], 0
0x180022e51  mov     eax, ebx
0x180022e53  mov     rbx, [rsp+28h+arg_0]
0x180022e58  add     rsp, 20h
0x180022e5c  pop     rdi
0x180022e5d  retn
```
