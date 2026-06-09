# HandleServiceAGCapabilitiesIndicationRequest

- ea: `0x1400098ac`
- end: `0x140009ace`
- name: `HandleServiceAGCapabilitiesIndicationRequest`
- size: `546`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140029170`

## callees

- `0x1400041d0`
- `0x140006108`
- `0x1400098ac`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall HandleServiceAGCapabilitiesIndicationRequest(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  unsigned int v4; // ebx
  __int64 v5; // rdi
  int v6; // edx
  __int64 v7; // rdx
  BOOL v8; // eax

  v2 = a2;
  v4 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      1,
      62,
      (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400220B0);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
    WdfDriverGlobals,
    *(_QWORD *)(v5 + 328),
    0);
  if ( *(_DWORD *)(v5 + 344) )
  {
    v7 = *(_QWORD *)(v5 + 320);
    v8 = v7
      && *(_DWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                       WdfDriverGlobals,
                       v7,
                       off_140022100)
                   + 24);
    if ( !*(_DWORD *)(v5 + 360) || !v8 || *(_DWORD *)(v5 + 364) )
      v4 = 0;
    CompleteServiceAGCapabilitiesRequest(v2, v4);
    *(_DWORD *)(v5 + 344) = 0;
  }
  else if ( *(_QWORD *)(v5 + 336) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      LOBYTE(v4) = 0;
    }
    if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = v4;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v6,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        WPP_GLOBAL_Control->DeviceExtension,
        3,
        4,
        63,
        (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
      WdfDriverGlobals,
      v2,
      3221225488LL);
  }
  else
  {
    *(_QWORD *)(v5 + 336) = v2;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, void (__fastcall *)(struct WDFREQUEST__ *)))(WdfFunctions_01015 + 3144))(
      WdfDriverGlobals,
      v2,
      EvtServiceRequestCancel);
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(
           WdfDriverGlobals,
           *(_QWORD *)(v5 + 328));
}

```

## disassembly

```asm
0x1400098ac  push    rbx
0x1400098ae  push    rsi
0x1400098af  push    rdi
0x1400098b0  push    r12
0x1400098b2  push    r14
0x1400098b4  push    r15
0x1400098b6  sub     rsp, 48h
0x1400098ba  mov     rsi, rdx
0x1400098bd  mov     rdi, rcx
0x1400098c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400098c7  lea     r14, WPP_GLOBAL_Control
0x1400098ce  mov     ebx, 1
0x1400098d3  cmp     rcx, r14
0x1400098d6  jz      short loc_1400098E9
0x1400098d8  mov     eax, [rcx+2Ch]
0x1400098db  test    bl, al
0x1400098dd  jz      short loc_1400098E9
0x1400098df  cmp     byte ptr [rcx+29h], 4
0x1400098e3  jb      short loc_1400098E9
0x1400098e5  mov     dl, bl
0x1400098e7  jmp     short loc_1400098EB
0x1400098e9  xor     dl, dl
0x1400098eb  lea     r15, WPP_RECORDER_INITIALIZED
0x1400098f2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400098f9  lea     r12, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x140009900  setnz   r8b
0x140009904  test    dl, dl
0x140009906  jnz     short loc_14000990D
0x140009908  test    r8b, r8b
0x14000990b  jz      short loc_14000992F
0x14000990d  mov     r9, [rcx+40h]
0x140009911  mov     rcx, [rcx+18h]
0x140009915  mov     [rsp+78h+var_40], r12
0x14000991a  mov     [rsp+78h+var_48], 3Eh ; '>'
0x140009921  mov     [rsp+78h+var_50], ebx
0x140009925  mov     [rsp+78h+var_58], 4
0x14000992a  call    WPP_RECORDER_AND_TRACE_SF_
0x14000992f  mov     rax, cs:WdfFunctions_01015
0x140009936  mov     rdx, rdi
0x140009939  mov     r8, cs:off_1400220B0
0x140009940  mov     rcx, cs:WdfDriverGlobals
0x140009947  mov     rax, [rax+650h]
0x14000994e  call    _guard_dispatch_icall
0x140009953  mov     rcx, cs:WdfFunctions_01015
0x14000995a  mov     rdi, rax
0x14000995d  xor     r8d, r8d
0x140009960  mov     rax, [rcx+9C8h]
0x140009967  mov     rcx, cs:WdfDriverGlobals
0x14000996e  mov     rdx, [rdi+148h]
0x140009975  call    _guard_dispatch_icall
0x14000997a  cmp     dword ptr [rdi+158h], 0
0x140009981  jz      short loc_1400099ED
0x140009983  mov     rdx, [rdi+140h]
0x14000998a  test    rdx, rdx
0x14000998d  jz      short loc_1400099BA
0x14000998f  mov     rax, cs:WdfFunctions_01015
0x140009996  mov     r8, cs:off_140022100
0x14000999d  mov     rcx, cs:WdfDriverGlobals
0x1400099a4  mov     rax, [rax+650h]
0x1400099ab  call    _guard_dispatch_icall
0x1400099b0  cmp     dword ptr [rax+18h], 0
0x1400099b4  jz      short loc_1400099BA
0x1400099b6  mov     eax, ebx
0x1400099b8  jmp     short loc_1400099BC
0x1400099ba  xor     eax, eax
0x1400099bc  cmp     dword ptr [rdi+168h], 0
0x1400099c3  jz      short loc_1400099D2
0x1400099c5  test    eax, eax
0x1400099c7  jz      short loc_1400099D2
0x1400099c9  cmp     dword ptr [rdi+16Ch], 0
0x1400099d0  jz      short loc_1400099D4
0x1400099d2  xor     ebx, ebx
0x1400099d4  mov     edx, ebx
0x1400099d6  mov     rcx, rsi
0x1400099d9  call    CompleteServiceAGCapabilitiesRequest
0x1400099de  mov     dword ptr [rdi+158h], 0
0x1400099e8  jmp     loc_140009A9E
0x1400099ed  cmp     qword ptr [rdi+150h], 0
0x1400099f5  jz      short loc_140009A73
0x1400099f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400099fe  cmp     rcx, r14
0x140009a01  jz      short loc_140009A10
0x140009a03  mov     eax, [rcx+2Ch]
0x140009a06  test    al, 8
0x140009a08  jz      short loc_140009A10
0x140009a0a  cmp     byte ptr [rcx+29h], 3
0x140009a0e  jnb     short loc_140009A12
0x140009a10  xor     bl, bl
0x140009a12  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009a19  setnz   r8b
0x140009a1d  test    bl, bl
0x140009a1f  jnz     short loc_140009A26
0x140009a21  test    r8b, r8b
0x140009a24  jz      short loc_140009A4E
0x140009a26  mov     r9, [rcx+40h]
0x140009a2a  mov     dl, bl
0x140009a2c  mov     rcx, [rcx+18h]
0x140009a30  mov     [rsp+78h+var_40], r12
0x140009a35  mov     [rsp+78h+var_48], 3Fh ; '?'
0x140009a3c  mov     [rsp+78h+var_50], 4
0x140009a44  mov     [rsp+78h+var_58], 3
0x140009a49  call    WPP_RECORDER_AND_TRACE_SF_
0x140009a4e  mov     rax, cs:WdfFunctions_01015
0x140009a55  mov     r8d, 0C0000010h
0x140009a5b  mov     rcx, cs:WdfDriverGlobals
0x140009a62  mov     rdx, rsi
0x140009a65  mov     rax, [rax+838h]
0x140009a6c  call    _guard_dispatch_icall
0x140009a71  jmp     short loc_140009A9E
0x140009a73  mov     [rdi+150h], rsi
0x140009a7a  lea     r8, ?EvtServiceRequestCancel@@YAXPEAUWDFREQUEST__@@@Z; EvtServiceRequestCancel(WDFREQUEST__ *)
0x140009a81  mov     rax, cs:WdfFunctions_01015
0x140009a88  mov     rdx, rsi
0x140009a8b  mov     rcx, cs:WdfDriverGlobals
0x140009a92  mov     rax, [rax+0C48h]
0x140009a99  call    _guard_dispatch_icall
0x140009a9e  mov     rax, cs:WdfFunctions_01015
0x140009aa5  mov     rdx, [rdi+148h]
0x140009aac  mov     rcx, cs:WdfDriverGlobals
0x140009ab3  mov     rax, [rax+9D0h]
0x140009aba  call    _guard_dispatch_icall
0x140009abf  add     rsp, 48h
0x140009ac3  pop     r15
0x140009ac5  pop     r14
0x140009ac7  pop     r12
0x140009ac9  pop     rdi
0x140009aca  pop     rsi
0x140009acb  pop     rbx
0x140009acc  retn
```
