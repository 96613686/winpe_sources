# RdpIdEvtIddCxMonitorGetDefaultModes(IDDCX_MONITOR__ *,IDARG_IN_GETDEFAULTDESCRIPTIONMODES const *,IDARG_OUT_GETDEFAULTDESCRIPTIONMODES *)

- ea: `0x180026190`
- end: `0x1800263b3`
- name: `?RdpIdEvtIddCxMonitorGetDefaultModes@@YAJPEAUIDDCX_MONITOR__@@PEBUIDARG_IN_GETDEFAULTDESCRIPTIONMODES@@PEAUIDARG_OUT_GETDEFAULTDESCRIPTIONMODES@@@Z`
- size: `547`
- prototype: `__int64 __fastcall(struct IDDCX_MONITOR__ *, const struct IDARG_IN_GETDEFAULTDESCRIPTIONMODES *, struct IDARG_OUT_GETDEFAULTDESCRIPTIONMODES *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180006f60`
- `0x18000dbd8`
- `0x18000e978`
- `0x18001072c`
- `0x1800212b4`
- `0x180025010`
- `0x180026190`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026223`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026320`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026223`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026320`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026371`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026371`

## pseudocode

```c
__int64 __fastcall RdpIdEvtIddCxMonitorGetDefaultModes(
        struct IDDCX_MONITOR__ *a1,
        const struct IDARG_IN_GETDEFAULTDESCRIPTIONMODES *a2,
        struct IDARG_OUT_GETDEFAULTDESCRIPTIONMODES *a3)
{
  char v6; // bl
  bool v7; // di
  bool v8; // si
  char CurrentThreadId; // al
  int v10; // r8d
  int v11; // edx
  __int64 v12; // rax
  int DefaultModes; // eax
  bool v14; // di
  char v15; // al
  int v16; // r8d
  int v17; // edx
  const char *v18; // r9
  __int64 result; // rax
  int v20; // [rsp+20h] [rbp-A8h]
  int v21; // [rsp+28h] [rbp-A0h]
  _QWORD v22[2]; // [rsp+60h] [rbp-68h] BYREF
  __int64 v23; // [rsp+70h] [rbp-58h] BYREF
  std::_Ref_count_base *v24; // [rsp+78h] [rbp-50h]
  GUID ActivityId; // [rsp+80h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  CAutoSetThreadActivityId::CAutoSetThreadActivityId(
    &ActivityId,
    &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId);
  v6 = 1;
  v7 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v8 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v10) = v8;
    LOBYTE(v11) = v7;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      v10,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v20,
      v21,
      10,
      &WPP_21c286969d51392f6eed59d913c079a0_Traceguids,
      CurrentThreadId);
  }
  try
  {
    v12 = (*(__int64 (__fastcall **)(__int64, struct IDDCX_MONITOR__ *, __int64 *))(WdfFunctions_02025 + 984))(
            WdfDriverGlobals,
            a1,
            off_1800570A8);
    std::weak_ptr<CRdpIdAdapter>::lock(v12, &v23);
    if ( v23 )
    {
      if ( *(_DWORD *)a2 )
      {
        v22[0] = *((_QWORD *)a2 + 1);
        v22[1] = *(unsigned int *)a2;
        DefaultModes = CRdpIdMonitor::GetDefaultModes(v23, v22);
        *((_DWORD *)a3 + 1) = 0;
      }
      else
      {
        DefaultModes = -858993459 * ((__int64)(*(_QWORD *)(v23 + 120) - *(_QWORD *)(v23 + 112)) >> 4);
      }
      *(_DWORD *)a3 = DefaultModes;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v6 = 0;
    }
    v14 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = GetCurrentThreadId();
      LOBYTE(v16) = v14;
      LOBYTE(v17) = v6;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        v16,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v20,
        v21,
        11,
        &WPP_21c286969d51392f6eed59d913c079a0_Traceguids,
        v15);
    }
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
    EventActivityIdControl(2u, &ActivityId);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Nt_Return_CaughtException(
                           retaddr,
                           (void *)0x712,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
                           v18);
  }
  return result;
}

```

## disassembly

```asm
0x180026190  mov     r11, rsp
0x180026193  mov     [r11+10h], rbx
0x180026197  mov     [r11+20h], rsi
0x18002619b  push    rdi
0x18002619c  push    r12
0x18002619e  push    r13
0x1800261a0  push    r14
0x1800261a2  push    r15
0x1800261a4  sub     rsp, 0A0h
0x1800261ab  mov     rax, cs:__security_cookie
0x1800261b2  xor     rax, rsp
0x1800261b5  mov     [rsp+0C8h+var_38], rax
0x1800261bd  mov     r14, r8
0x1800261c0  mov     r13, rdx
0x1800261c3  mov     r12, rcx
0x1800261c6  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x1800261cd  lea     rcx, [r11-48h]; ActivityId
0x1800261d1  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x1800261d6  lea     rcx, WPP_GLOBAL_Control
0x1800261dd  mov     rax, cs:WPP_GLOBAL_Control
0x1800261e4  mov     bl, 1
0x1800261e6  cmp     rax, rcx
0x1800261e9  jz      short loc_1800261FB
0x1800261eb  test    [rax+1Ch], bl
0x1800261ee  jz      short loc_1800261FB
0x1800261f0  cmp     byte ptr [rax+19h], 4
0x1800261f4  jb      short loc_1800261FB
0x1800261f6  mov     dil, bl
0x1800261f9  jmp     short loc_1800261FE
0x1800261fb  xor     dil, dil
0x1800261fe  lea     rax, WPP_RECORDER_INITIALIZED
0x180026205  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002620c  setnz   sil
0x180026210  test    dil, dil
0x180026213  jnz     short loc_180026223
0x180026215  test    sil, sil
0x180026218  jnz     short loc_180026223
0x18002621a  lea     r15, WPP_21c286969d51392f6eed59d913c079a0_Traceguids
0x180026221  jmp     short loc_180026260
0x180026223  call    cs:__imp_GetCurrentThreadId
0x18002622a  nop     dword ptr [rax+rax+00h]
0x18002622f  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x180026233  lea     r15, WPP_21c286969d51392f6eed59d913c079a0_Traceguids
0x18002623a  mov     [rsp+0C8h+MessageGuid], r15; MessageGuid
0x18002623f  mov     [rsp+0C8h+var_98], 0Ah; __int16
0x180026246  mov     rcx, cs:WPP_GLOBAL_Control
0x18002624d  mov     r9, [rcx+28h]; int
0x180026251  mov     r8b, sil; int
0x180026254  mov     dl, dil; int
0x180026257  mov     rcx, [rcx+10h]; int
0x18002625b  call    WPP_RECORDER_AND_TRACE_SF_D
0x180026260  mov     rax, cs:WdfFunctions_02025
0x180026267  mov     r8, cs:off_1800570A8
0x18002626e  mov     rdx, r12
0x180026271  mov     rcx, cs:WdfDriverGlobals
0x180026278  mov     rax, [rax+3D8h]
0x18002627f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026284  lea     rdx, [rsp+0C8h+var_58]
0x180026289  mov     rcx, rax
0x18002628c  call    ?lock@?$weak_ptr@VCRdpIdAdapter@@@std@@QEBA?AV?$shared_ptr@VCRdpIdAdapter@@@2@XZ; std::weak_ptr<CRdpIdAdapter>::lock(void)
0x180026291  mov     rcx, [rsp+0C8h+var_58]
0x180026296  test    rcx, rcx
0x180026299  jz      short loc_1800262E5
0x18002629b  cmp     dword ptr [r13+0], 0
0x1800262a0  jnz     short loc_1800262BE
0x1800262a2  mov     rax, [rcx+78h]
0x1800262a6  sub     rax, [rcx+70h]
0x1800262aa  sar     rax, 4
0x1800262ae  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x1800262b8  imul    rax, rcx
0x1800262bc  jmp     short loc_1800262E2
0x1800262be  mov     rax, [r13+8]
0x1800262c2  mov     [rsp+0C8h+var_68], rax
0x1800262c7  mov     eax, [r13+0]
0x1800262cb  mov     [rsp+0C8h+var_60], rax
0x1800262d0  lea     rdx, [rsp+0C8h+var_68]
0x1800262d5  call    ?GetDefaultModes@CRdpIdMonitor@@QEAA_KV?$span@UIDDCX_MONITOR_MODE@@$0?0@std@@@Z; CRdpIdMonitor::GetDefaultModes(std::span<IDDCX_MONITOR_MODE,-1>)
0x1800262da  mov     dword ptr [r14+4], 0
0x1800262e2  mov     [r14], eax
0x1800262e5  mov     rax, cs:WPP_GLOBAL_Control
0x1800262ec  lea     rcx, WPP_GLOBAL_Control
0x1800262f3  cmp     rax, rcx
0x1800262f6  jz      short loc_180026303
0x1800262f8  test    [rax+1Ch], bl
0x1800262fb  jz      short loc_180026303
0x1800262fd  cmp     byte ptr [rax+19h], 4
0x180026301  jnb     short loc_180026305
0x180026303  xor     bl, bl
0x180026305  lea     rax, WPP_RECORDER_INITIALIZED
0x18002630c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180026313  setnz   dil
0x180026317  test    bl, bl
0x180026319  jnz     short loc_180026320
0x18002631b  test    dil, dil
0x18002631e  jz      short loc_180026355
0x180026320  call    cs:__imp_GetCurrentThreadId
0x180026327  nop     dword ptr [rax+rax+00h]
0x18002632c  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x180026330  mov     [rsp+0C8h+MessageGuid], r15; MessageGuid
0x180026335  mov     [rsp+0C8h+var_98], 0Bh; __int16
0x18002633c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026343  mov     r9, [rcx+28h]; int
0x180026347  mov     r8b, dil; int
0x18002634a  mov     dl, bl; int
0x18002634c  mov     rcx, [rcx+10h]; int
0x180026350  call    WPP_RECORDER_AND_TRACE_SF_D
0x180026355  mov     rcx, [rsp+0C8h+var_50]; this
0x18002635a  test    rcx, rcx
0x18002635d  jz      short loc_180026364
0x18002635f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180026364  lea     rdx, [rsp+0C8h+ActivityId]; ActivityId
0x18002636c  mov     ecx, 2; ControlCode
0x180026371  call    cs:__imp_EventActivityIdControl
0x180026378  nop     dword ptr [rax+rax+00h]
0x18002637d  xor     eax, eax
0x18002637f  jmp     short loc_180026385
0x180026381  mov     eax, [rsp+0C8h+var_78]
0x180026385  mov     rcx, [rsp+0C8h+var_38]
0x18002638d  xor     rcx, rsp; StackCookie
0x180026390  call    __security_check_cookie
0x180026395  lea     r11, [rsp+0C8h+var_28]
0x18002639d  mov     rbx, [r11+38h]
0x1800263a1  mov     rsi, [r11+48h]
0x1800263a5  mov     rsp, r11
0x1800263a8  pop     r15
0x1800263aa  pop     r14
0x1800263ac  pop     r13
0x1800263ae  pop     r12
0x1800263b0  pop     rdi
0x1800263b1  retn
```
