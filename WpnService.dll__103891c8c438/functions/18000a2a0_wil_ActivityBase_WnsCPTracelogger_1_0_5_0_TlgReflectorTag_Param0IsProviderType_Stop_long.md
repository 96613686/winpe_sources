# wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000a2a0`
- end: `0x18000a5ef`
- name: `?Stop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `847`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `40`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003e60`
- `0x180004d50`
- `0x180005300`
- `0x1800054a0`
- `0x1800058d4`
- `0x180006770`
- `0x180006eb0`
- `0x1800074f0`
- `0x180008780`
- `0x180008cc0`
- `0x180009250`
- `0x1800099f0`
- `0x18000e010`
- `0x18000f690`
- `0x180013394`
- `0x180014710`
- `0x1800157bc`
- `0x180016990`
- `0x180016c40`
- `0x1800179c0`
- `0x180020ee4`
- `0x1800217f4`
- `0x180021e50`
- `0x180023b20`
- `0x180024cd0`
- `0x180024ec0`
- `0x180025530`
- `0x180025730`
- `0x18002d59c`
- `0x18002e2c8`
- `0x18002e4b0`
- `0x18002e580`
- `0x1800300a8`
- `0x180032fe0`
- `0x180033100`
- `0x180033200`
- `0x1800332f0`
- `0x1800333e0`
- `0x180033470`
- `0x180033f38`

## callees

- `0x18000a2a0`
- `0x18000f270`
- `0x1800118ec`
- `0x1800187a0`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a2eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a2eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a303`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a31d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a35e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a303`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a31d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a35e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a4a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a4a6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a57e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a57e`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000a45d`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000a45d`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a442`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a442`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a395`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a395`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a48c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a48c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        const struct wil::FailureInfo *a2)
{
  int v2; // r15d
  RTL_SRWLOCK *v4; // rbx
  RTL_SRWLOCK *v5; // rbx
  __int64 v6; // rax
  int v7; // r14d
  int v8; // esi
  int v9; // r14d
  ULONGLONG *v10; // rbx
  _QWORD *Ptr; // rbx
  const GUID *v12; // r8
  WINBOOL fPending; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  PSRWLOCK v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  GUID ProviderId; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v20; // [rsp+70h] [rbp-90h]
  __int128 v21; // [rsp+80h] [rbp-80h]
  __int128 v22; // [rsp+90h] [rbp-70h]
  __int128 v23; // [rsp+A0h] [rbp-60h]
  __int128 v24; // [rsp+B0h] [rbp-50h]
  __int128 v25; // [rsp+C0h] [rbp-40h]
  __int128 v26; // [rsp+D0h] [rbp-30h]
  __int128 v27; // [rsp+E0h] [rbp-20h]
  __int64 v28; // [rsp+F0h] [rbp-10h]

  v2 = (int)a2;
  v4 = (RTL_SRWLOCK *)a1[35];
  if ( v4 )
  {
    v5 = v4 + 33;
    AcquireSRWLockExclusive(v5);
    SRWLock = 0;
  }
  else
  {
    v16 = 0;
    v5 = 0;
  }
  v6 = a1[34];
  v7 = *(_DWORD *)(v6 + 248);
  if ( v7 < 1 )
  {
    UserData = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    wil::details::WilFailFast((wil::details *)&UserData, a2);
  }
  v8 = *(_DWORD *)(v6 + 72);
  if ( v8 >= 0 )
  {
    *(_DWORD *)(v6 + 72) = v2;
    v8 = v2;
  }
  v9 = v7 - 1;
  *(_DWORD *)(v6 + 248) = v9;
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
  if ( v9 )
  {
    SRWLock = 0;
    fPending = 0;
    if ( InitOnceBeginInitialize(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock)
      && fPending )
    {
      SRWLock = (PSRWLOCK)&qword_18004A760;
      qword_18004A768 = 0;
      byte_18004A770 = 0;
      dword_18004A774 = 0;
      qword_18004A760 = (__int64)&wil::details::FeatureLogging::`vftable';
      CallbackContext = &`WnsCPTracelogger::StaticHandle::StaticHandle'::`2'::__hInner;
      atexit(_lambda_633a74d489e420a2ff0e92495a1626f6_::_lambda_invoker_cdecl_);
      v10 = (ULONGLONG *)CallbackContext;
      qword_18004A768 = (__int64)CallbackContext;
      byte_18004A770 = 1;
      ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
      if ( *((_QWORD *)CallbackContext + 4) )
        __fastfail(5u);
      *((_QWORD *)CallbackContext + 5) = 0;
      v10[6] = 0;
      if ( !EventRegister(&ProviderId, tlgEnableCallback, v10, v10 + 4) )
        EventSetInformation(v10[4], 2, v10[1], *(unsigned __int16 *)v10[1]);
      dword_18004A774 = 1;
      (*(void (__fastcall **)(__int64 *))(qword_18004A760 + 8))(&qword_18004A760);
      InitOnceComplete(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &qword_18004A760);
    }
    Ptr = SRWLock[1].Ptr;
    if ( *(_DWORD *)Ptr > 5u )
    {
      fPending = GetCurrentThreadId();
      LODWORD(v16) = v2;
      v17 = 0x1000000;
      v12 = (const GUID *)(a1[34] + 8LL);
      *(_QWORD *)&v23 = &fPending;
      *((_QWORD *)&v23 + 1) = 4;
      *(_QWORD *)&v22 = &v16;
      *((_QWORD *)&v22 + 1) = 4;
      *(_QWORD *)&v21 = &v17;
      *((_QWORD *)&v21 + 1) = 8;
      ProviderId.Data1 = 184549376;
      *(_DWORD *)&ProviderId.Data2 = 5;
      *(_QWORD *)ProviderId.Data4 = 0;
      UserData.Ptr = Ptr[1];
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      *(_QWORD *)&v20 = word_18003D9A2;
      *((_QWORD *)&v20 + 1) = 0x10000004DLL;
      LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(Ptr[4], (PCEVENT_DESCRIPTOR)&ProviderId, v12, 0, 5u, &UserData);
    }
  }
  else
  {
    wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1, v8);
  }
  return wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x18000a2a0  mov     [rsp-8+arg_8], rbx
0x18000a2a5  mov     [rsp-8+arg_10], rsi
0x18000a2aa  push    rbp
0x18000a2ab  push    rdi
0x18000a2ac  push    r12
0x18000a2ae  push    r14
0x18000a2b0  push    r15
0x18000a2b2  lea     rbp, [rsp-10h]
0x18000a2b7  sub     rsp, 110h
0x18000a2be  mov     rax, cs:__security_cookie
0x18000a2c5  xor     rax, rsp
0x18000a2c8  mov     [rbp+30h+var_30], rax
0x18000a2cc  mov     r15d, edx
0x18000a2cf  mov     rdi, rcx
0x18000a2d2  xor     r12d, r12d
0x18000a2d5  mov     rbx, [rcx+118h]
0x18000a2dc  test    rbx, rbx
0x18000a2df  jz      short loc_18000A30B
0x18000a2e1  add     rbx, 108h
0x18000a2e8  mov     rcx, rbx; SRWLock
0x18000a2eb  call    cs:__imp_AcquireSRWLockExclusive
0x18000a2f1  lea     rax, [rsp+130h+SRWLock]
0x18000a2f6  mov     [rax], r12
0x18000a2f9  mov     rcx, [rsp+130h+SRWLock]; SRWLock
0x18000a2fe  test    rcx, rcx
0x18000a301  jz      short loc_18000A326
0x18000a303  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a309  jmp     short loc_18000A326
0x18000a30b  lea     rax, [rsp+130h+var_F0]
0x18000a310  mov     [rax], r12
0x18000a313  mov     rcx, [rsp+130h+var_F0]; SRWLock
0x18000a318  test    rcx, rcx
0x18000a31b  jz      short loc_18000A323
0x18000a31d  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a323  mov     rbx, r12
0x18000a326  mov     rax, [rdi+110h]
0x18000a32d  mov     r14d, [rax+0F8h]
0x18000a334  cmp     r14d, 1
0x18000a338  jl      loc_18000A5B5
0x18000a33e  mov     esi, [rax+48h]
0x18000a341  test    esi, esi
0x18000a343  js      short loc_18000A34C
0x18000a345  mov     [rax+48h], r15d
0x18000a349  mov     esi, r15d
0x18000a34c  dec     r14d
0x18000a34f  mov     [rax+0F8h], r14d
0x18000a356  test    rbx, rbx
0x18000a359  jz      short loc_18000A364
0x18000a35b  mov     rcx, rbx; SRWLock
0x18000a35e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a364  test    r14d, r14d
0x18000a367  jnz     short loc_18000A378
0x18000a369  mov     edx, esi
0x18000a36b  mov     rcx, rdi
0x18000a36e  call    ?ReportStopActivity@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18000a373  jmp     loc_18000A584
0x18000a378  mov     [rsp+130h+SRWLock], r12
0x18000a37d  mov     [rsp+130h+fPending], r12d
0x18000a382  lea     r9, [rsp+130h+SRWLock]; lpContext
0x18000a387  lea     r8, [rsp+130h+fPending]; fPending
0x18000a38c  xor     edx, edx; dwFlags
0x18000a38e  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18000a395  call    cs:__imp_InitOnceBeginInitialize
0x18000a39b  test    eax, eax
0x18000a39d  jz      loc_18000A492
0x18000a3a3  cmp     [rsp+130h+fPending], 0
0x18000a3a8  jz      loc_18000A492
0x18000a3ae  lea     r14, qword_18004A760
0x18000a3b5  mov     [rsp+130h+SRWLock], r14
0x18000a3ba  mov     cs:qword_18004A768, r12
0x18000a3c1  mov     cs:byte_18004A770, 0
0x18000a3c8  mov     cs:dword_18004A774, r12d
0x18000a3cf  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18000a3d6  mov     cs:qword_18004A760, rax
0x18000a3dd  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000a3e4  mov     cs:CallbackContext, rax
0x18000a3eb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x18000a3f2  call    atexit
0x18000a3f7  mov     rbx, cs:CallbackContext
0x18000a3fe  mov     cs:qword_18004A768, rbx
0x18000a405  mov     cs:byte_18004A770, 1
0x18000a40c  mov     rax, [rbx+8]
0x18000a410  movups  xmm0, xmmword ptr [rax-10h]
0x18000a414  movups  xmmword ptr [rsp+130h+ProviderId.Data1], xmm0
0x18000a419  cmp     qword ptr [rbx+20h], 0
0x18000a41e  jz      short loc_18000A427
0x18000a420  mov     ecx, 5
0x18000a425  int     29h; Win8: RtlFailFast(ecx)
0x18000a427  mov     [rbx+28h], r12
0x18000a42b  mov     [rbx+30h], r12
0x18000a42f  lea     r9, [rbx+20h]; RegHandle
0x18000a433  mov     r8, rbx; CallbackContext
0x18000a436  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000a43d  lea     rcx, [rsp+130h+ProviderId]; ProviderId
0x18000a442  call    cs:__imp_EventRegister
0x18000a448  test    eax, eax
0x18000a44a  jnz     short loc_18000A463
0x18000a44c  mov     r8, [rbx+8]
0x18000a450  movzx   r9d, word ptr [r8]
0x18000a454  mov     edx, 2
0x18000a459  mov     rcx, [rbx+20h]
0x18000a45d  call    cs:__imp_EventSetInformation
0x18000a463  mov     cs:dword_18004A774, 1
0x18000a46d  mov     rax, cs:qword_18004A760
0x18000a474  mov     rcx, r14
0x18000a477  mov     rax, [rax+8]
0x18000a47b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a480  mov     r8, r14; lpContext
0x18000a483  xor     edx, edx; dwFlags
0x18000a485  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18000a48c  call    cs:__imp_InitOnceComplete
0x18000a492  mov     rax, [rsp+130h+SRWLock]
0x18000a497  mov     rbx, [rax+8]
0x18000a49b  mov     eax, [rbx]
0x18000a49d  cmp     eax, 5
0x18000a4a0  jbe     loc_18000A584
0x18000a4a6  call    cs:__imp_GetCurrentThreadId
0x18000a4ac  mov     [rsp+130h+fPending], eax
0x18000a4b0  mov     dword ptr [rsp+130h+var_F0], r15d
0x18000a4b5  mov     [rsp+130h+var_E8], 1000000h
0x18000a4be  mov     r8, [rdi+110h]
0x18000a4c5  add     r8, 8; ActivityId
0x18000a4c9  lea     rax, [rsp+130h+fPending]
0x18000a4ce  mov     qword ptr [rbp+30h+var_90], rax
0x18000a4d2  mov     qword ptr [rbp+30h+var_90+8], 4
0x18000a4da  lea     rax, [rsp+130h+var_F0]
0x18000a4df  mov     qword ptr [rbp+30h+var_A0], rax
0x18000a4e3  mov     qword ptr [rbp+30h+var_A0+8], 4
0x18000a4eb  lea     rax, [rsp+130h+var_E8]
0x18000a4f0  mov     qword ptr [rbp+30h+var_B0], rax
0x18000a4f4  mov     qword ptr [rbp+30h+var_B0+8], 8
0x18000a4fc  mov     [rsp+130h+ProviderId.Data1], 0B000000h
0x18000a504  movzx   eax, cs:word_18003D998
0x18000a50b  mov     dword ptr [rsp+130h+ProviderId.Data2], eax
0x18000a50f  mov     qword ptr [rsp+130h+ProviderId.Data4], r12
0x18000a514  mov     rax, [rbx+8]
0x18000a518  mov     [rsp+130h+var_D0.Ptr], rax
0x18000a51d  movzx   eax, word ptr [rax]
0x18000a520  mov     [rsp+130h+var_D0.Size], eax
0x18000a524  mov     dword ptr [rsp+130h+var_D0.0Ch], 2
0x18000a52c  lea     rax, word_18003D9A2
0x18000a533  mov     qword ptr [rsp+130h+var_C0], rax
0x18000a538  mov     dword ptr [rsp+130h+var_C0+8], 4Dh ; 'M'
0x18000a540  mov     dword ptr [rsp+130h+var_C0+0Ch], 1
0x18000a548  lea     rax, _TraceLoggingMetadataEnd
0x18000a54f  lea     rcx, _TraceLoggingMetadata
0x18000a556  sub     eax, ecx
0x18000a558  mov     dword ptr [rsp+130h+SRWLock], eax
0x18000a55c  mov     eax, dword ptr [rsp+130h+SRWLock]
0x18000a560  lea     rax, [rsp+130h+var_D0]
0x18000a565  mov     [rsp+130h+UserData], rax; UserData
0x18000a56a  mov     [rsp+130h+UserDataCount], 5; UserDataCount
0x18000a572  xor     r9d, r9d; RelatedActivityId
0x18000a575  lea     rdx, [rsp+130h+ProviderId]; EventDescriptor
0x18000a57a  mov     rcx, [rbx+20h]; RegHandle
0x18000a57e  call    cs:__imp_EventWriteTransfer
0x18000a584  mov     rcx, rdi
0x18000a587  call    ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000a58c  nop
0x18000a58d  mov     rcx, [rbp+30h+var_30]
0x18000a591  xor     rcx, rsp; StackCookie
0x18000a594  call    __security_check_cookie
0x18000a599  lea     r11, [rsp+130h+var_20]
0x18000a5a1  mov     rbx, [r11+38h]
0x18000a5a5  mov     rsi, [r11+40h]
0x18000a5a9  mov     rsp, r11
0x18000a5ac  pop     r15
0x18000a5ae  pop     r14
0x18000a5b0  pop     r12
0x18000a5b2  pop     rdi
0x18000a5b3  pop     rbp
0x18000a5b4  retn
0x18000a5b5  xorps   xmm0, xmm0
0x18000a5b8  xor     eax, eax
0x18000a5ba  movups  xmmword ptr [rsp+130h+var_D0.Ptr], xmm0
0x18000a5bf  movups  [rsp+130h+var_C0], xmm0
0x18000a5c4  movups  [rbp+30h+var_B0], xmm0
0x18000a5c8  movups  [rbp+30h+var_A0], xmm0
0x18000a5cc  movups  [rbp+30h+var_90], xmm0
0x18000a5d0  movups  [rbp+30h+var_80], xmm0
0x18000a5d4  movups  [rbp+30h+var_70], xmm0
0x18000a5d8  movups  [rbp+30h+var_60], xmm0
0x18000a5dc  movups  [rbp+30h+var_50], xmm0
0x18000a5e0  mov     [rbp+30h+var_40], rax
0x18000a5e4  lea     rcx, [rsp+130h+var_D0]; this
0x18000a5e9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
