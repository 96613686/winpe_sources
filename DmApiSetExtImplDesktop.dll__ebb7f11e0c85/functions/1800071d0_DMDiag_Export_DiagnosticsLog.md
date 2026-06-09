# DMDiag_Export_DiagnosticsLog

- ea: `0x1800071d0`
- end: `0x18000725e`
- name: `DMDiag_Export_DiagnosticsLog`
- size: `142`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800035b4`
- `0x1800071d0`

## import_xrefs

- `wevtapi!EvtOpenSession` at `0x1800071fb`
- `wevtapi!EvtOpenSession` at `0x1800071fb`

## pseudocode

```c
__int64 __fastcall DMDiag_Export_DiagnosticsLog(unsigned __int16 *a1)
{
  _OWORD Login[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v4; // [rsp+40h] [rbp-18h]

  v4 = 0;
  memset(Login, 0, sizeof(Login));
  if ( !EvtOpenSession(EvtRpcLogin, Login, 0, 0) )
    return 2147942406LL;
  ExportEventLogs(
    L"%s\\DeviceManagement-Enterprise-Diagnostics-Provider.evtx",
    L"Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider/Admin",
    a1);
  ExportEventLogs(L"%s\\Microsoft-Windows-AAD.evtx", L"Microsoft-Windows-AAD/Operational", a1);
  ExportEventLogs(L"%s\\Microsoft-Windows-Shell-Core.evtx", L"Microsoft-Windows-Shell-Core/Operational", a1);
  return 0;
}

```

## disassembly

```asm
0x1800071d0  push    rbx
0x1800071d2  sub     rsp, 50h
0x1800071d6  xor     eax, eax
0x1800071d8  lea     rdx, [rsp+58h+Login]; Login
0x1800071dd  xorps   xmm0, xmm0
0x1800071e0  mov     [rsp+58h+var_18], rax
0x1800071e5  mov     rbx, rcx
0x1800071e8  xor     r9d, r9d; Flags
0x1800071eb  xor     r8d, r8d; Timeout
0x1800071ee  lea     ecx, [rax+1]; LoginClass
0x1800071f1  movups  [rsp+58h+Login], xmm0
0x1800071f6  movups  [rsp+58h+var_28], xmm0
0x1800071fb  call    cs:__imp_EvtOpenSession
0x180007202  nop     dword ptr [rax+rax+00h]
0x180007207  test    rax, rax
0x18000720a  jnz     short loc_180007213
0x18000720c  mov     eax, 80070006h
0x180007211  jmp     short loc_180007257
0x180007213  mov     r8, rbx; unsigned __int16 *
0x180007216  lea     rdx, Path; "Microsoft-Windows-DeviceManagement-Ente"...
0x18000721d  lea     rcx, aSDevicemanagem; "%s\\DeviceManagement-Enterprise-Diagnos"...
0x180007224  call    ?ExportEventLogs@@YAJPEBG00@Z; ExportEventLogs(ushort const *,ushort const *,ushort const *)
0x180007229  mov     r8, rbx; unsigned __int16 *
0x18000722c  lea     rdx, aMicrosoftWindo; "Microsoft-Windows-AAD/Operational"
0x180007233  lea     rcx, aSMicrosoftWind; "%s\\Microsoft-Windows-AAD.evtx"
0x18000723a  call    ?ExportEventLogs@@YAJPEBG00@Z; ExportEventLogs(ushort const *,ushort const *,ushort const *)
0x18000723f  mov     r8, rbx; unsigned __int16 *
0x180007242  lea     rdx, aMicrosoftWindo_0; "Microsoft-Windows-Shell-Core/Operationa"...
0x180007249  lea     rcx, aSMicrosoftWind_0; "%s\\Microsoft-Windows-Shell-Core.evtx"
0x180007250  call    ?ExportEventLogs@@YAJPEBG00@Z; ExportEventLogs(ushort const *,ushort const *,ushort const *)
0x180007255  xor     eax, eax
0x180007257  add     rsp, 50h
0x18000725b  pop     rbx
0x18000725c  retn
```
