# WnsCPLog::WnsSinkChannelRenewed::StartActivity(long,unsigned __int64,ushort const *,ushort const *,long)

- ea: `0x18001c280`
- end: `0x18001c640`
- name: `?StartActivity@WnsSinkChannelRenewed@WnsCPLog@@QEAAXJ_KPEBG1J@Z`
- size: `960`
- prototype: `void __fastcall(WnsCPLog::WnsSinkChannelRenewed *__hidden this, int, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180032e24`

## callees

- `0x18000d830`
- `0x18000d8f0`
- `0x18001c280`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c2cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c2cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c2e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c2fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c340`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c2e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c2fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c340`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c48f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c48f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001c612`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001c612`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001c323`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001c323`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001c42a`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001c42a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18001c40f`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18001c40f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001c363`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001c363`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001c461`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001c461`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkChannelRenewed::StartActivity(
        WnsCPLog::WnsSinkChannelRenewed *this,
        int a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        WINBOOL a6)
{
  RTL_SRWLOCK *v6; // rbx
  RTL_SRWLOCK *v11; // rbx
  __int64 v12; // rsi
  _QWORD *v13; // rbx
  ULONGLONG *v14; // r9
  _QWORD *Ptr; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  const GUID *v18; // r9
  int *v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rcx
  bool v22; // zf
  int v23; // ecx
  int v24; // eax
  WINBOOL fPending; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  GUID ProviderId; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-90h] BYREF
  char *v33; // [rsp+80h] [rbp-80h]
  int v34; // [rsp+88h] [rbp-78h]
  int v35; // [rsp+8Ch] [rbp-74h]
  __int64 *v36; // [rsp+90h] [rbp-70h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  PSRWLOCK *v38; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  int *v40; // [rsp+B0h] [rbp-50h]
  __int64 v41; // [rsp+B8h] [rbp-48h]
  __int64 *v42; // [rsp+C0h] [rbp-40h]
  __int64 v43; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v44; // [rsp+D0h] [rbp-30h]
  int v45; // [rsp+D8h] [rbp-28h]
  int v46; // [rsp+DCh] [rbp-24h]
  int *v47; // [rsp+E0h] [rbp-20h]
  int v48; // [rsp+E8h] [rbp-18h]
  int v49; // [rsp+ECh] [rbp-14h]
  WINBOOL *p_fPending; // [rsp+F0h] [rbp-10h]
  __int64 v51; // [rsp+F8h] [rbp-8h]

  v6 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  if ( v6 )
  {
    v11 = v6 + 33;
    AcquireSRWLockExclusive(v11);
    SRWLock = 0;
  }
  else
  {
    v28 = 0;
    v11 = 0;
  }
  v12 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)WnsCPTracelogger::Provider() <= 5u )
    *(_OWORD *)(v12 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v12 + 8));
  *(_DWORD *)v12 = 1;
  if ( v11 )
    ReleaseSRWLockExclusive(v11);
  SRWLock = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock)
    && fPending )
  {
    qword_18004A768 = 0;
    SRWLock = (PSRWLOCK)&qword_18004A760;
    qword_18004A760 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_18004A770 = 0;
    dword_18004A774 = 0;
    CallbackContext = &`WnsCPTracelogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_633a74d489e420a2ff0e92495a1626f6_::_lambda_invoker_cdecl_);
    v13 = CallbackContext;
    qword_18004A768 = (__int64)CallbackContext;
    byte_18004A770 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    v14 = (ULONGLONG *)((char *)CallbackContext + 32);
    *((_QWORD *)CallbackContext + 5) = 0;
    v13[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v13, v14) )
      EventSetInformation(v13[4], 2, v13[1], *(unsigned __int16 *)v13[1]);
    dword_18004A774 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18004A760 + 8))(&qword_18004A760);
    InitOnceComplete(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &qword_18004A760);
  }
  Ptr = SRWLock[1].Ptr;
  if ( *(_DWORD *)Ptr > 5u )
  {
    fPending = a6;
    v29 = a3;
    v27 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v17 = *((_QWORD *)this + 34);
    LODWORD(v28) = CurrentThreadId;
    v30 = 0;
    if ( !*(_BYTE *)(v17 + 4)
      || (v18 = (const GUID *)(v17 + 24), !*(_DWORD *)(v17 + 24))
      && !*(_DWORD *)(v17 + 28)
      && !*(_DWORD *)(v17 + 32)
      && !*(_DWORD *)(v17 + 36) )
    {
      v18 = 0;
    }
    v19 = (int *)a5;
    p_fPending = &fPending;
    v20 = -1;
    v51 = 4;
    if ( a5 )
    {
      v21 = -1;
      do
        v22 = a5[++v21] == 0;
      while ( !v22 );
      v23 = 2 * v21 + 2;
    }
    else
    {
      v19 = &dword_18003A074;
      v23 = 2;
    }
    v47 = v19;
    v48 = v23;
    v49 = 0;
    if ( a4 )
    {
      do
        v22 = a4[++v20] == 0;
      while ( !v22 );
      v24 = 2 * v20 + 2;
    }
    else
    {
      a4 = (const unsigned __int16 *)&dword_18003A074;
      v24 = 2;
    }
    v45 = v24;
    v44 = a4;
    v42 = &v29;
    v46 = 0;
    v40 = &v27;
    v43 = 8;
    v38 = &v28;
    v36 = &v30;
    *(_DWORD *)&ProviderId.Data2 = 261;
    UserData.Ptr = Ptr[1];
    v41 = 4;
    v39 = 4;
    v37 = 8;
    ProviderId.Data1 = 184549376;
    *(_QWORD *)ProviderId.Data4 = 0;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v33 = &byte_18004289F;
    UserData.Reserved = 2;
    v34 = 115;
    v35 = 1;
    LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(Ptr[4], (PCEVENT_DESCRIPTOR)&ProviderId, (LPCGUID)(v17 + 8), v18, 9u, &UserData);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001c280  push    rbp
0x18001c282  push    rbx
0x18001c283  push    rsi
0x18001c284  push    rdi
0x18001c285  push    r12
0x18001c287  push    r13
0x18001c289  push    r14
0x18001c28b  push    r15
0x18001c28d  lea     rbp, [rsp-18h]
0x18001c292  sub     rsp, 118h
0x18001c299  mov     rax, cs:__security_cookie
0x18001c2a0  xor     rax, rsp
0x18001c2a3  mov     [rbp+50h+var_50], rax
0x18001c2a7  mov     rbx, [rcx+118h]
0x18001c2ae  xor     r13d, r13d
0x18001c2b1  mov     rdi, r9
0x18001c2b4  mov     r15, r8
0x18001c2b7  mov     r12d, edx
0x18001c2ba  mov     r14, rcx
0x18001c2bd  test    rbx, rbx
0x18001c2c0  jz      short loc_18001C2EC
0x18001c2c2  add     rbx, 108h
0x18001c2c9  mov     rcx, rbx; SRWLock
0x18001c2cc  call    cs:__imp_AcquireSRWLockExclusive
0x18001c2d2  lea     rax, [rsp+150h+SRWLock]
0x18001c2d7  mov     [rax], r13
0x18001c2da  mov     rcx, [rsp+150h+SRWLock]; SRWLock
0x18001c2df  test    rcx, rcx
0x18001c2e2  jz      short loc_18001C307
0x18001c2e4  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c2ea  jmp     short loc_18001C307
0x18001c2ec  lea     rax, [rsp+150h+var_108]
0x18001c2f1  mov     [rax], r13
0x18001c2f4  mov     rcx, [rsp+150h+var_108]; SRWLock
0x18001c2f9  test    rcx, rcx
0x18001c2fc  jz      short loc_18001C304
0x18001c2fe  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c304  mov     rbx, r13
0x18001c307  mov     rsi, [r14+110h]
0x18001c30e  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18001c313  mov     ecx, [rax]
0x18001c315  cmp     ecx, 5
0x18001c318  jbe     short loc_18001C32B
0x18001c31a  lea     rdx, [rsi+8]; ActivityId
0x18001c31e  mov     ecx, 3; ControlCode
0x18001c323  call    cs:__imp_EventActivityIdControl
0x18001c329  jmp     short loc_18001C332
0x18001c32b  xorps   xmm0, xmm0
0x18001c32e  movups  xmmword ptr [rsi+8], xmm0
0x18001c332  mov     dword ptr [rsi], 1
0x18001c338  test    rbx, rbx
0x18001c33b  jz      short loc_18001C346
0x18001c33d  mov     rcx, rbx; SRWLock
0x18001c340  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c346  lea     r9, [rsp+150h+SRWLock]; lpContext
0x18001c34b  mov     [rsp+150h+SRWLock], r13
0x18001c350  lea     r8, [rsp+150h+fPending]; fPending
0x18001c355  mov     [rsp+150h+fPending], r13d
0x18001c35a  xor     edx, edx; dwFlags
0x18001c35c  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18001c363  call    cs:__imp_InitOnceBeginInitialize
0x18001c369  test    eax, eax
0x18001c36b  jz      loc_18001C467
0x18001c371  cmp     [rsp+150h+fPending], r13d
0x18001c376  jz      loc_18001C467
0x18001c37c  lea     rax, qword_18004A760
0x18001c383  mov     cs:qword_18004A768, r13
0x18001c38a  mov     [rsp+150h+SRWLock], rax
0x18001c38f  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18001c396  mov     cs:qword_18004A760, rax
0x18001c39d  mov     cs:byte_18004A770, r13b
0x18001c3a4  mov     cs:dword_18004A774, r13d
0x18001c3ab  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001c3b2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x18001c3b9  mov     cs:CallbackContext, rax
0x18001c3c0  call    atexit
0x18001c3c5  mov     rbx, cs:CallbackContext
0x18001c3cc  mov     cs:qword_18004A768, rbx
0x18001c3d3  mov     cs:byte_18004A770, 1
0x18001c3da  mov     rax, [rbx+8]
0x18001c3de  movups  xmm0, xmmword ptr [rax-10h]
0x18001c3e2  movups  xmmword ptr [rsp+150h+ProviderId.Data1], xmm0
0x18001c3e7  cmp     [rbx+20h], r13
0x18001c3eb  jz      short loc_18001C3F4
0x18001c3ed  mov     ecx, 5
0x18001c3f2  int     29h; Win8: RtlFailFast(ecx)
0x18001c3f4  lea     r9, [rbx+20h]; RegHandle
0x18001c3f8  mov     [rbx+28h], r13
0x18001c3fc  mov     r8, rbx; CallbackContext
0x18001c3ff  mov     [rbx+30h], r13
0x18001c403  lea     rdx, _tlgEnableCallback; EnableCallback
0x18001c40a  lea     rcx, [rsp+150h+ProviderId]; ProviderId
0x18001c40f  call    cs:__imp_EventRegister
0x18001c415  test    eax, eax
0x18001c417  jnz     short loc_18001C430
0x18001c419  mov     r8, [rbx+8]
0x18001c41d  mov     edx, 2
0x18001c422  mov     rcx, [rbx+20h]
0x18001c426  movzx   r9d, word ptr [r8]
0x18001c42a  call    cs:__imp_EventSetInformation
0x18001c430  mov     rax, cs:qword_18004A760
0x18001c437  lea     rcx, qword_18004A760
0x18001c43e  mov     cs:dword_18004A774, 1
0x18001c448  mov     rax, [rax+8]
0x18001c44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c451  lea     r8, qword_18004A760; lpContext
0x18001c458  xor     edx, edx; dwFlags
0x18001c45a  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18001c461  call    cs:__imp_InitOnceComplete
0x18001c467  mov     rax, [rsp+150h+SRWLock]
0x18001c46c  mov     rbx, [rax+8]
0x18001c470  mov     eax, [rbx]
0x18001c472  cmp     eax, 5
0x18001c475  jbe     loc_18001C618
0x18001c47b  mov     eax, [rbp+50h+arg_28]
0x18001c481  mov     [rsp+150h+fPending], eax
0x18001c485  mov     [rsp+150h+var_100], r15
0x18001c48a  mov     [rsp+150h+var_110], r12d
0x18001c48f  call    cs:__imp_GetCurrentThreadId
0x18001c495  mov     r8, [r14+110h]
0x18001c49c  mov     dword ptr [rsp+150h+var_108], eax
0x18001c4a0  mov     [rsp+150h+var_F8], r13
0x18001c4a5  cmp     [r8+4], r13b
0x18001c4a9  jz      short loc_18001C4C7
0x18001c4ab  cmp     [r8+18h], r13d
0x18001c4af  lea     r9, [r8+18h]
0x18001c4b3  jnz     short loc_18001C4CA
0x18001c4b5  cmp     [r9+4], r13d
0x18001c4b9  jnz     short loc_18001C4CA
0x18001c4bb  cmp     [r9+8], r13d
0x18001c4bf  jnz     short loc_18001C4CA
0x18001c4c1  cmp     [r9+0Ch], r13d
0x18001c4c5  jnz     short loc_18001C4CA
0x18001c4c7  mov     r9, r13; RelatedActivityId
0x18001c4ca  mov     rdx, [rbp+50h+arg_20]
0x18001c4d1  lea     rax, [rsp+150h+fPending]
0x18001c4d6  mov     [rbp+50h+var_60], rax
0x18001c4da  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001c4e1  mov     [rbp+50h+var_58], 4
0x18001c4e9  test    rdx, rdx
0x18001c4ec  jz      short loc_18001C506
0x18001c4ee  mov     rcx, rax
0x18001c4f1  cmp     [rdx+rcx*2+2], r13w
0x18001c4f7  lea     rcx, [rcx+1]
0x18001c4fb  jnz     short loc_18001C4F1
0x18001c4fd  lea     ecx, ds:2[rcx*2]
0x18001c504  jmp     short loc_18001C512
0x18001c506  lea     rdx, dword_18003A074
0x18001c50d  mov     ecx, 2
0x18001c512  mov     [rbp+50h+var_70], rdx
0x18001c516  mov     [rbp+50h+var_68], ecx
0x18001c519  mov     [rbp+50h+var_64], r13d
0x18001c51d  test    rdi, rdi
0x18001c520  jz      short loc_18001C537
0x18001c522  cmp     [rdi+rax*2+2], r13w
0x18001c528  lea     rax, [rax+1]
0x18001c52c  jnz     short loc_18001C522
0x18001c52e  lea     eax, ds:2[rax*2]
0x18001c535  jmp     short loc_18001C543
0x18001c537  lea     rdi, dword_18003A074
0x18001c53e  mov     eax, 2
0x18001c543  mov     [rbp+50h+var_78], eax
0x18001c546  lea     rcx, _TraceLoggingMetadata
0x18001c54d  mov     [rbp+50h+var_80], rdi
0x18001c551  lea     rax, [rsp+150h+var_100]
0x18001c556  mov     [rbp+50h+var_90], rax
0x18001c55a  lea     rdx, [rsp+150h+ProviderId]; EventDescriptor
0x18001c55f  mov     [rbp+50h+var_74], r13d
0x18001c563  lea     rax, [rsp+150h+var_110]
0x18001c568  mov     [rbp+50h+var_A0], rax
0x18001c56c  add     r8, 8; ActivityId
0x18001c570  mov     [rbp+50h+var_88], 8
0x18001c578  lea     rax, [rsp+150h+var_108]
0x18001c57d  mov     [rbp+50h+var_B0], rax
0x18001c581  lea     rax, [rsp+150h+var_F8]
0x18001c586  mov     [rbp+50h+var_C0], rax
0x18001c58a  movzx   eax, cs:word_180042895
0x18001c591  mov     dword ptr [rsp+150h+ProviderId.Data2], eax
0x18001c595  mov     rax, [rbx+8]
0x18001c599  mov     [rsp+150h+var_E0.Ptr], rax
0x18001c59e  mov     [rbp+50h+var_98], 4
0x18001c5a6  mov     [rbp+50h+var_A8], 4
0x18001c5ae  mov     [rbp+50h+var_B8], 8
0x18001c5b6  mov     [rsp+150h+ProviderId.Data1], 0B000000h
0x18001c5be  mov     qword ptr [rsp+150h+ProviderId.Data4], r13
0x18001c5c3  movzx   eax, word ptr [rax]
0x18001c5c6  mov     [rsp+150h+var_E0.Size], eax
0x18001c5ca  lea     rax, byte_18004289F
0x18001c5d1  mov     [rbp+50h+var_D0], rax
0x18001c5d5  lea     rax, _TraceLoggingMetadataEnd
0x18001c5dc  sub     eax, ecx
0x18001c5de  mov     dword ptr [rsp+150h+var_E0.0Ch], 2
0x18001c5e6  mov     [rbp+50h+var_C8], 73h ; 's'
0x18001c5ed  mov     [rbp+50h+var_C4], 1
0x18001c5f4  mov     dword ptr [rsp+150h+SRWLock], eax
0x18001c5f8  mov     eax, dword ptr [rsp+150h+SRWLock]
0x18001c5fc  mov     rcx, [rbx+20h]; RegHandle
0x18001c600  lea     rax, [rsp+150h+var_E0]
0x18001c605  mov     [rsp+150h+UserData], rax; UserData
0x18001c60a  mov     [rsp+150h+UserDataCount], 9; UserDataCount
0x18001c612  call    cs:__imp_EventWriteTransfer
0x18001c618  mov     rcx, r14
0x18001c61b  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18001c620  mov     rcx, [rbp+50h+var_50]
0x18001c624  xor     rcx, rsp; StackCookie
0x18001c627  call    __security_check_cookie
0x18001c62c  add     rsp, 118h
0x18001c633  pop     r15
0x18001c635  pop     r14
0x18001c637  pop     r13
0x18001c639  pop     r12
0x18001c63b  pop     rdi
0x18001c63c  pop     rsi
0x18001c63d  pop     rbx
0x18001c63e  pop     rbp
0x18001c63f  retn
```
