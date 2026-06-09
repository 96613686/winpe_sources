# RdpIdEvtIddCxMonitorQueryTargetModes2(IDDCX_MONITOR__ *,IDARG_IN_QUERYTARGETMODES2 const *,IDARG_OUT_QUERYTARGETMODES *)

- ea: `0x1800263c0`
- end: `0x1800265dc`
- name: `?RdpIdEvtIddCxMonitorQueryTargetModes2@@YAJPEAUIDDCX_MONITOR__@@PEBUIDARG_IN_QUERYTARGETMODES2@@PEAUIDARG_OUT_QUERYTARGETMODES@@@Z`
- size: `540`
- prototype: `__int64 __fastcall(struct IDDCX_MONITOR__ *, const struct IDARG_IN_QUERYTARGETMODES2 *, struct IDARG_OUT_QUERYTARGETMODES *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180006f60`
- `0x18000dbd8`
- `0x18000e978`
- `0x18001072c`
- `0x1800212b4`
- `0x18002511c`
- `0x1800263c0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026453`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026549`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026453`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026549`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002659a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002659a`

## pseudocode

```c
__int64 __fastcall RdpIdEvtIddCxMonitorQueryTargetModes2(
        struct IDDCX_MONITOR__ *a1,
        const struct IDARG_IN_QUERYTARGETMODES2 *a2,
        struct IDARG_OUT_QUERYTARGETMODES *a3)
{
  char v6; // bl
  bool v7; // di
  bool v8; // si
  char CurrentThreadId; // al
  int v10; // r8d
  int v11; // edx
  __int64 v12; // rax
  int TargetModes; // eax
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
      12,
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
      if ( *((_DWORD *)a2 + 6) )
      {
        v22[0] = *((_QWORD *)a2 + 4);
        v22[1] = *((unsigned int *)a2 + 6);
        TargetModes = CRdpIdMonitor::GetTargetModes(v23, v22);
      }
      else
      {
        TargetModes = -858993459 * ((__int64)(*(_QWORD *)(v23 + 120) - *(_QWORD *)(v23 + 112)) >> 4);
      }
      *(_DWORD *)a3 = TargetModes;
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
        13,
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
                           (void *)0x754,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
                           v18);
  }
  return result;
}

```

## disassembly

```asm
0x1800263c0  mov     r11, rsp
0x1800263c3  mov     [r11+10h], rbx
0x1800263c7  mov     [r11+20h], rsi
0x1800263cb  push    rdi
0x1800263cc  push    r12
0x1800263ce  push    r13
0x1800263d0  push    r14
0x1800263d2  push    r15
0x1800263d4  sub     rsp, 0A0h
0x1800263db  mov     rax, cs:__security_cookie
0x1800263e2  xor     rax, rsp
0x1800263e5  mov     [rsp+0C8h+var_38], rax
0x1800263ed  mov     r12, r8
0x1800263f0  mov     r15, rdx
0x1800263f3  mov     r13, rcx
0x1800263f6  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x1800263fd  lea     rcx, [r11-48h]; ActivityId
0x180026401  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x180026406  lea     rcx, WPP_GLOBAL_Control
0x18002640d  mov     rax, cs:WPP_GLOBAL_Control
0x180026414  mov     bl, 1
0x180026416  cmp     rax, rcx
0x180026419  jz      short loc_18002642B
0x18002641b  test    [rax+1Ch], bl
0x18002641e  jz      short loc_18002642B
0x180026420  cmp     byte ptr [rax+19h], 4
0x180026424  jb      short loc_18002642B
0x180026426  mov     dil, bl
0x180026429  jmp     short loc_18002642E
0x18002642b  xor     dil, dil
0x18002642e  lea     rax, WPP_RECORDER_INITIALIZED
0x180026435  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002643c  setnz   sil
0x180026440  test    dil, dil
0x180026443  jnz     short loc_180026453
0x180026445  test    sil, sil
0x180026448  jnz     short loc_180026453
0x18002644a  lea     r14, WPP_21c286969d51392f6eed59d913c079a0_Traceguids
0x180026451  jmp     short loc_180026490
0x180026453  call    cs:__imp_GetCurrentThreadId
0x18002645a  nop     dword ptr [rax+rax+00h]
0x18002645f  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x180026463  lea     r14, WPP_21c286969d51392f6eed59d913c079a0_Traceguids
0x18002646a  mov     [rsp+0C8h+MessageGuid], r14; MessageGuid
0x18002646f  mov     [rsp+0C8h+var_98], 0Ch; __int16
0x180026476  mov     rcx, cs:WPP_GLOBAL_Control
0x18002647d  mov     r9, [rcx+28h]; int
0x180026481  mov     r8b, sil; int
0x180026484  mov     dl, dil; int
0x180026487  mov     rcx, [rcx+10h]; int
0x18002648b  call    WPP_RECORDER_AND_TRACE_SF_D
0x180026490  mov     rax, cs:WdfFunctions_02025
0x180026497  mov     r8, cs:off_1800570A8
0x18002649e  mov     rdx, r13
0x1800264a1  mov     rcx, cs:WdfDriverGlobals
0x1800264a8  mov     rax, [rax+3D8h]
0x1800264af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264b4  lea     rdx, [rsp+0C8h+var_58]
0x1800264b9  mov     rcx, rax
0x1800264bc  call    ?lock@?$weak_ptr@VCRdpIdAdapter@@@std@@QEBA?AV?$shared_ptr@VCRdpIdAdapter@@@2@XZ; std::weak_ptr<CRdpIdAdapter>::lock(void)
0x1800264c1  mov     rcx, [rsp+0C8h+var_58]
0x1800264c6  test    rcx, rcx
0x1800264c9  jz      short loc_18002650E
0x1800264cb  cmp     dword ptr [r15+18h], 0
0x1800264d0  jnz     short loc_1800264EE
0x1800264d2  mov     rax, [rcx+78h]
0x1800264d6  sub     rax, [rcx+70h]
0x1800264da  sar     rax, 4
0x1800264de  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x1800264e8  imul    rax, rcx
0x1800264ec  jmp     short loc_18002650A
0x1800264ee  mov     rax, [r15+20h]
0x1800264f2  mov     [rsp+0C8h+var_68], rax
0x1800264f7  mov     eax, [r15+18h]
0x1800264fb  mov     [rsp+0C8h+var_60], rax
0x180026500  lea     rdx, [rsp+0C8h+var_68]
0x180026505  call    ?GetTargetModes@CRdpIdMonitor@@QEAA_KV?$span@UIDDCX_TARGET_MODE2@@$0?0@std@@@Z; CRdpIdMonitor::GetTargetModes(std::span<IDDCX_TARGET_MODE2,-1>)
0x18002650a  mov     [r12], eax
0x18002650e  mov     rax, cs:WPP_GLOBAL_Control
0x180026515  lea     rcx, WPP_GLOBAL_Control
0x18002651c  cmp     rax, rcx
0x18002651f  jz      short loc_18002652C
0x180026521  test    [rax+1Ch], bl
0x180026524  jz      short loc_18002652C
0x180026526  cmp     byte ptr [rax+19h], 4
0x18002652a  jnb     short loc_18002652E
0x18002652c  xor     bl, bl
0x18002652e  lea     rax, WPP_RECORDER_INITIALIZED
0x180026535  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002653c  setnz   dil
0x180026540  test    bl, bl
0x180026542  jnz     short loc_180026549
0x180026544  test    dil, dil
0x180026547  jz      short loc_18002657E
0x180026549  call    cs:__imp_GetCurrentThreadId
0x180026550  nop     dword ptr [rax+rax+00h]
0x180026555  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x180026559  mov     [rsp+0C8h+MessageGuid], r14; MessageGuid
0x18002655e  mov     [rsp+0C8h+var_98], 0Dh; __int16
0x180026565  mov     rcx, cs:WPP_GLOBAL_Control
0x18002656c  mov     r9, [rcx+28h]; int
0x180026570  mov     r8b, dil; int
0x180026573  mov     dl, bl; int
0x180026575  mov     rcx, [rcx+10h]; int
0x180026579  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002657e  mov     rcx, [rsp+0C8h+var_50]; this
0x180026583  test    rcx, rcx
0x180026586  jz      short loc_18002658D
0x180026588  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002658d  lea     rdx, [rsp+0C8h+ActivityId]; ActivityId
0x180026595  mov     ecx, 2; ControlCode
0x18002659a  call    cs:__imp_EventActivityIdControl
0x1800265a1  nop     dword ptr [rax+rax+00h]
0x1800265a6  xor     eax, eax
0x1800265a8  jmp     short loc_1800265AE
0x1800265aa  mov     eax, [rsp+0C8h+var_78]
0x1800265ae  mov     rcx, [rsp+0C8h+var_38]
0x1800265b6  xor     rcx, rsp; StackCookie
0x1800265b9  call    __security_check_cookie
0x1800265be  lea     r11, [rsp+0C8h+var_28]
0x1800265c6  mov     rbx, [r11+38h]
0x1800265ca  mov     rsi, [r11+48h]
0x1800265ce  mov     rsp, r11
0x1800265d1  pop     r15
0x1800265d3  pop     r14
0x1800265d5  pop     r13
0x1800265d7  pop     r12
0x1800265d9  pop     rdi
0x1800265da  retn
```
