# RdpIdEvtMonitorCleanup(void *)

- ea: `0x180026ee0`
- end: `0x180027142`
- name: `?RdpIdEvtMonitorCleanup@@YAXPEAX@Z`
- size: `610`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180001bc4`
- `0x180006f60`
- `0x18000d614`
- `0x18000dbd8`
- `0x18000e978`
- `0x18001072c`
- `0x180010764`
- `0x1800212b4`
- `0x180026ee0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026f65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800270d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026f65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800270d7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180027115`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180027115`

## string_xrefs

- `0x18002701c`: `RDPIDD_MONITOR_CONTEXT context is being removed`

## pseudocode

```c
void __fastcall RdpIdEvtMonitorCleanup(void *a1)
{
  char v2; // bl
  bool v3; // di
  bool v4; // si
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  __int64 v8; // rax
  _QWORD *v9; // rdi
  __int64 v10; // rsi
  _DWORD *v11; // r8
  int v12; // r9d
  std::_Ref_count_base *v13; // rcx
  bool v14; // di
  char v15; // al
  int v16; // r8d
  int v17; // edx
  int v18; // [rsp+20h] [rbp-69h]
  int v19; // [rsp+28h] [rbp-61h]
  int v20; // [rsp+50h] [rbp-39h] BYREF
  int v21; // [rsp+54h] [rbp-35h] BYREF
  int v22; // [rsp+58h] [rbp-31h] BYREF
  const char *v23; // [rsp+60h] [rbp-29h] BYREF
  const char *v24; // [rsp+68h] [rbp-21h] BYREF
  int v25[2]; // [rsp+70h] [rbp-19h] BYREF
  __int64 v26; // [rsp+78h] [rbp-11h] BYREF
  std::_Ref_count_base *v27; // [rsp+80h] [rbp-9h]
  GUID ActivityId; // [rsp+88h] [rbp-1h] BYREF

  CAutoSetThreadActivityId::CAutoSetThreadActivityId(
    &ActivityId,
    &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId);
  v2 = 1;
  v3 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v4 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v6) = v4;
    LOBYTE(v7) = v3;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v18,
      v19,
      24,
      &WPP_21c286969d51392f6eed59d913c079a0_Traceguids,
      CurrentThreadId);
  }
  v8 = (*(__int64 (__fastcall **)(__int64, void *, __int64 *))(WdfFunctions_02025 + 984))(
         WdfDriverGlobals,
         a1,
         off_1800570A8);
  v9 = (_QWORD *)v8;
  if ( v8 )
  {
    std::weak_ptr<CRdpIdAdapter>::lock(v8, &v26);
    v10 = v26;
    if ( v26 )
    {
      v11 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v11 > 4u )
      {
        v20 = *(_DWORD *)(*(_QWORD *)(v10 + 232) + 516LL);
        v21 = *(_DWORD *)(v10 + 280);
        v23 = "RDPIDD_MONITOR_CONTEXT context is being removed";
        v24 = "RdpIdEvtMonitorCleanup";
        *(_QWORD *)v25 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp";
        v22 = 2261;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v11,
          (unsigned int)byte_18004E51D,
          (_DWORD)v11,
          v12,
          (__int64)v25,
          (__int64)&v22,
          (__int64)&v24,
          (__int64)&v23,
          (__int64)&v21,
          (__int64)&v20);
      }
    }
    v13 = (std::_Ref_count_base *)v9[1];
    *v9 = 0;
    v9[1] = 0;
    if ( v13 )
      std::_Ref_count_base::_Decwref(v13);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v2 = 0;
  }
  v14 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v15 = GetCurrentThreadId();
    LOBYTE(v16) = v14;
    LOBYTE(v17) = v2;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      v16,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v18,
      v19,
      25,
      &WPP_21c286969d51392f6eed59d913c079a0_Traceguids,
      v15);
  }
  EventActivityIdControl(2u, &ActivityId);
}

```

## disassembly

```asm
0x180026ee0  push    rbp
0x180026ee2  push    rbx
0x180026ee3  push    rsi
0x180026ee4  push    rdi
0x180026ee5  push    r12
0x180026ee7  push    r13
0x180026ee9  push    r14
0x180026eeb  push    r15
0x180026eed  lea     rbp, [rsp-1Fh]
0x180026ef2  sub     rsp, 0A8h
0x180026ef9  mov     rax, cs:__security_cookie
0x180026f00  xor     rax, rsp
0x180026f03  mov     [rbp+57h+var_48], rax
0x180026f07  mov     r14, rcx
0x180026f0a  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x180026f11  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x180026f15  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x180026f1a  mov     rax, cs:WPP_GLOBAL_Control
0x180026f21  lea     r12, WPP_GLOBAL_Control
0x180026f28  mov     bl, 1
0x180026f2a  cmp     rax, r12
0x180026f2d  jz      short loc_180026F3F
0x180026f2f  test    [rax+1Ch], bl
0x180026f32  jz      short loc_180026F3F
0x180026f34  cmp     byte ptr [rax+19h], 4
0x180026f38  jb      short loc_180026F3F
0x180026f3a  mov     dil, bl
0x180026f3d  jmp     short loc_180026F42
0x180026f3f  xor     dil, dil
0x180026f42  lea     r15, WPP_RECORDER_INITIALIZED
0x180026f49  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180026f50  lea     r13, WPP_21c286969d51392f6eed59d913c079a0_Traceguids
0x180026f57  setnz   sil
0x180026f5b  test    dil, dil
0x180026f5e  jnz     short loc_180026F65
0x180026f60  test    sil, sil
0x180026f63  jz      short loc_180026F9B
0x180026f65  call    cs:__imp_GetCurrentThreadId
0x180026f6c  nop     dword ptr [rax+rax+00h]
0x180026f71  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f78  mov     r8b, sil; int
0x180026f7b  mov     dword ptr [rsp+0E0h+var_A0], eax; char
0x180026f7f  mov     dl, dil; int
0x180026f82  mov     [rsp+0E0h+MessageGuid], r13; MessageGuid
0x180026f87  mov     [rsp+0E0h+var_B0], 18h; __int16
0x180026f8e  mov     r9, [rcx+28h]; int
0x180026f92  mov     rcx, [rcx+10h]; int
0x180026f96  call    WPP_RECORDER_AND_TRACE_SF_D
0x180026f9b  mov     rax, cs:WdfFunctions_02025
0x180026fa2  mov     rdx, r14
0x180026fa5  mov     r8, cs:off_1800570A8
0x180026fac  mov     rcx, cs:WdfDriverGlobals
0x180026fb3  mov     rax, [rax+3D8h]
0x180026fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fbf  mov     rdi, rax
0x180026fc2  test    rax, rax
0x180026fc5  jz      loc_1800270AA
0x180026fcb  lea     rdx, [rbp+57h+var_68]
0x180026fcf  mov     rcx, rax
0x180026fd2  call    ?lock@?$weak_ptr@VCRdpIdAdapter@@@std@@QEBA?AV?$shared_ptr@VCRdpIdAdapter@@@2@XZ; std::weak_ptr<CRdpIdAdapter>::lock(void)
0x180026fd7  mov     rsi, [rbp+57h+var_68]
0x180026fdb  test    rsi, rsi
0x180026fde  jz      loc_18002707F
0x180026fe4  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180026fe9  mov     r8, [rax+8]
0x180026fed  mov     ecx, [r8]
0x180026ff0  cmp     ecx, 4
0x180026ff3  jbe     loc_18002707F
0x180026ff9  mov     rax, [rsi+0E8h]
0x180027000  lea     rdx, byte_18004E51D
0x180027007  mov     ecx, [rax+204h]
0x18002700d  mov     [rbp+57h+var_90], ecx
0x180027010  mov     rcx, r8
0x180027013  mov     eax, [rsi+118h]
0x180027019  mov     [rbp+57h+var_8C], eax
0x18002701c  lea     rax, aRdpiddMonitorC_0; "RDPIDD_MONITOR_CONTEXT context is being"...
0x180027023  mov     [rbp+57h+var_80], rax
0x180027027  lea     rax, aRdpidevtmonito; "RdpIdEvtMonitorCleanup"
0x18002702e  mov     [rbp+57h+var_78], rax
0x180027032  lea     rax, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180027039  mov     qword ptr [rbp+57h+var_70], rax
0x18002703d  lea     rax, [rbp+57h+var_90]
0x180027041  mov     [rsp+0E0h+var_98], rax
0x180027046  lea     rax, [rbp+57h+var_8C]
0x18002704a  mov     qword ptr [rsp+0E0h+var_A0], rax
0x18002704f  lea     rax, [rbp+57h+var_80]
0x180027053  mov     [rsp+0E0h+MessageGuid], rax
0x180027058  lea     rax, [rbp+57h+var_78]
0x18002705c  mov     qword ptr [rsp+0E0h+var_B0], rax
0x180027061  lea     rax, [rbp+57h+var_88]
0x180027065  mov     qword ptr [rsp+0E0h+var_B8], rax; int
0x18002706a  lea     rax, [rbp+57h+var_70]
0x18002706e  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180027073  mov     [rbp+57h+var_88], 8D5h
0x18002707a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002707f  mov     rcx, [rdi+8]; this
0x180027083  mov     qword ptr [rdi], 0
0x18002708a  mov     qword ptr [rdi+8], 0
0x180027092  test    rcx, rcx
0x180027095  jz      short loc_18002709C
0x180027097  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18002709c  mov     rcx, [rbp+57h+var_60]; this
0x1800270a0  test    rcx, rcx
0x1800270a3  jz      short loc_1800270AA
0x1800270a5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800270aa  mov     rax, cs:WPP_GLOBAL_Control
0x1800270b1  cmp     rax, r12
0x1800270b4  jz      short loc_1800270C1
0x1800270b6  test    [rax+1Ch], bl
0x1800270b9  jz      short loc_1800270C1
0x1800270bb  cmp     byte ptr [rax+19h], 4
0x1800270bf  jnb     short loc_1800270C3
0x1800270c1  xor     bl, bl
0x1800270c3  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800270ca  setnz   dil
0x1800270ce  test    bl, bl
0x1800270d0  jnz     short loc_1800270D7
0x1800270d2  test    dil, dil
0x1800270d5  jz      short loc_18002710C
0x1800270d7  call    cs:__imp_GetCurrentThreadId
0x1800270de  nop     dword ptr [rax+rax+00h]
0x1800270e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800270ea  mov     r8b, dil; int
0x1800270ed  mov     dword ptr [rsp+0E0h+var_A0], eax; char
0x1800270f1  mov     dl, bl; int
0x1800270f3  mov     [rsp+0E0h+MessageGuid], r13; MessageGuid
0x1800270f8  mov     [rsp+0E0h+var_B0], 19h; __int16
0x1800270ff  mov     r9, [rcx+28h]; int
0x180027103  mov     rcx, [rcx+10h]; int
0x180027107  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002710c  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180027110  mov     ecx, 2; ControlCode
0x180027115  call    cs:__imp_EventActivityIdControl
0x18002711c  nop     dword ptr [rax+rax+00h]
0x180027121  mov     rcx, [rbp+57h+var_48]
0x180027125  xor     rcx, rsp; StackCookie
0x180027128  call    __security_check_cookie
0x18002712d  add     rsp, 0A8h
0x180027134  pop     r15
0x180027136  pop     r14
0x180027138  pop     r13
0x18002713a  pop     r12
0x18002713c  pop     rdi
0x18002713d  pop     rsi
0x18002713e  pop     rbx
0x18002713f  pop     rbp
0x180027140  retn
```
