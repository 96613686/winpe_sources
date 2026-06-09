# RdpIdEvtIddCxMonitorSetDefaultHdrMetaData(IDDCX_MONITOR__ *,IDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA const *)

- ea: `0x1800265f0`
- end: `0x180026739`
- name: `?RdpIdEvtIddCxMonitorSetDefaultHdrMetaData@@YAJPEAUIDDCX_MONITOR__@@PEBUIDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA@@@Z`
- size: `329`
- prototype: `__int64 __fastcall(struct IDDCX_MONITOR__ *, const struct IDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180006f60`
- `0x18000dbd8`
- `0x18000e978`
- `0x1800265f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002666b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800266d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002666b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800266d1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026710`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026710`

## pseudocode

```c
__int64 __fastcall RdpIdEvtIddCxMonitorSetDefaultHdrMetaData(
        struct IDDCX_MONITOR__ *a1,
        const struct IDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA *a2)
{
  PVOID *v2; // rax
  char v3; // bl
  bool v4; // di
  _UNKNOWN **v5; // rcx
  bool v6; // si
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  bool v10; // di
  char v11; // al
  int v12; // r8d
  int v13; // edx
  int v15; // [rsp+20h] [rbp-88h]
  int v16; // [rsp+28h] [rbp-80h]
  GUID ActivityId; // [rsp+50h] [rbp-58h] BYREF

  CAutoSetThreadActivityId::CAutoSetThreadActivityId(
    &ActivityId,
    &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId);
  v2 = (PVOID *)WPP_GLOBAL_Control;
  v3 = 1;
  v4 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v8) = v6;
    LOBYTE(v9) = v4;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v15,
      v16,
      22,
      &WPP_21c286969d51392f6eed59d913c079a0_Traceguids,
      CurrentThreadId);
    v2 = (PVOID *)WPP_GLOBAL_Control;
    v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  if ( v2 == &WPP_GLOBAL_Control || (*((_BYTE *)v2 + 28) & 1) == 0 || *((_BYTE *)v2 + 25) < 4u )
    v3 = 0;
  v10 = v5 != &WPP_RECORDER_INITIALIZED;
  if ( v3 || v5 != &WPP_RECORDER_INITIALIZED )
  {
    v11 = GetCurrentThreadId();
    LOBYTE(v12) = v10;
    LOBYTE(v13) = v3;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      v12,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v15,
      v16,
      23,
      &WPP_21c286969d51392f6eed59d913c079a0_Traceguids,
      v11);
  }
  EventActivityIdControl(2u, &ActivityId);
  return 0;
}

```

## disassembly

```asm
0x1800265f0  push    rbx
0x1800265f2  push    rbp
0x1800265f3  push    rsi
0x1800265f4  push    rdi
0x1800265f5  push    r14
0x1800265f7  push    r15
0x1800265f9  sub     rsp, 78h
0x1800265fd  mov     rax, cs:__security_cookie
0x180026604  xor     rax, rsp
0x180026607  mov     [rsp+0A8h+var_48], rax
0x18002660c  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x180026613  lea     rcx, [rsp+0A8h+ActivityId]; ActivityId
0x180026618  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18002661d  mov     rax, cs:WPP_GLOBAL_Control
0x180026624  lea     rbp, WPP_GLOBAL_Control
0x18002662b  mov     bl, 1
0x18002662d  cmp     rax, rbp
0x180026630  jz      short loc_180026642
0x180026632  test    [rax+1Ch], bl
0x180026635  jz      short loc_180026642
0x180026637  cmp     byte ptr [rax+19h], 4
0x18002663b  jb      short loc_180026642
0x18002663d  mov     dil, bl
0x180026640  jmp     short loc_180026645
0x180026642  xor     dil, dil
0x180026645  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x18002664c  lea     r14, WPP_RECORDER_INITIALIZED
0x180026653  cmp     rcx, r14
0x180026656  lea     r15, WPP_21c286969d51392f6eed59d913c079a0_Traceguids
0x18002665d  setnz   sil
0x180026661  test    dil, dil
0x180026664  jnz     short loc_18002666B
0x180026666  test    sil, sil
0x180026669  jz      short loc_1800266AF
0x18002666b  call    cs:__imp_GetCurrentThreadId
0x180026672  nop     dword ptr [rax+rax+00h]
0x180026677  mov     rcx, cs:WPP_GLOBAL_Control
0x18002667e  mov     r8b, sil; int
0x180026681  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x180026685  mov     dl, dil; int
0x180026688  mov     [rsp+0A8h+MessageGuid], r15; MessageGuid
0x18002668d  mov     [rsp+0A8h+var_78], 16h; __int16
0x180026694  mov     r9, [rcx+28h]; int
0x180026698  mov     rcx, [rcx+10h]; int
0x18002669c  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800266a1  mov     rax, cs:WPP_GLOBAL_Control
0x1800266a8  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x1800266af  cmp     rax, rbp
0x1800266b2  jz      short loc_1800266BF
0x1800266b4  test    [rax+1Ch], bl
0x1800266b7  jz      short loc_1800266BF
0x1800266b9  cmp     byte ptr [rax+19h], 4
0x1800266bd  jnb     short loc_1800266C1
0x1800266bf  xor     bl, bl
0x1800266c1  cmp     rcx, r14
0x1800266c4  setnz   dil
0x1800266c8  test    bl, bl
0x1800266ca  jnz     short loc_1800266D1
0x1800266cc  test    dil, dil
0x1800266cf  jz      short loc_180026706
0x1800266d1  call    cs:__imp_GetCurrentThreadId
0x1800266d8  nop     dword ptr [rax+rax+00h]
0x1800266dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800266e4  mov     r8b, dil; int
0x1800266e7  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x1800266eb  mov     dl, bl; int
0x1800266ed  mov     [rsp+0A8h+MessageGuid], r15; MessageGuid
0x1800266f2  mov     [rsp+0A8h+var_78], 17h; __int16
0x1800266f9  mov     r9, [rcx+28h]; int
0x1800266fd  mov     rcx, [rcx+10h]; int
0x180026701  call    WPP_RECORDER_AND_TRACE_SF_D
0x180026706  lea     rdx, [rsp+0A8h+ActivityId]; ActivityId
0x18002670b  mov     ecx, 2; ControlCode
0x180026710  call    cs:__imp_EventActivityIdControl
0x180026717  nop     dword ptr [rax+rax+00h]
0x18002671c  xor     eax, eax
0x18002671e  mov     rcx, [rsp+0A8h+var_48]
0x180026723  xor     rcx, rsp; StackCookie
0x180026726  call    __security_check_cookie
0x18002672b  add     rsp, 78h
0x18002672f  pop     r15
0x180026731  pop     r14
0x180026733  pop     rdi
0x180026734  pop     rsi
0x180026735  pop     rbp
0x180026736  pop     rbx
0x180026737  retn
```
