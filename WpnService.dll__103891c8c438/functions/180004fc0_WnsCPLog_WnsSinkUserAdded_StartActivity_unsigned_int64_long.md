# WnsCPLog::WnsSinkUserAdded::StartActivity(unsigned __int64,long)

- ea: `0x180004fc0`
- end: `0x1800052ec`
- name: `?StartActivity@WnsSinkUserAdded@WnsCPLog@@QEAAX_KJ@Z`
- size: `812`
- prototype: `void __fastcall(WnsCPLog::WnsSinkUserAdded *__hidden this, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180005300`

## callees

- `0x180004fc0`
- `0x18000d830`
- `0x18000d8f0`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005011`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005011`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005027`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000503f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005081`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005027`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000503f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005081`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051cb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800052ba`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800052ba`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180005064`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180005064`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000516b`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000516b`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180005150`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180005150`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800050a0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800050a0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000519a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000519a`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkUserAdded::StartActivity(WnsCPLog::WnsSinkUserAdded *this, __int64 a2, WINBOOL a3)
{
  RTL_SRWLOCK *v3; // rbx
  RTL_SRWLOCK *v7; // rbx
  __int64 v8; // rsi
  _QWORD *v9; // rbx
  ULONGLONG *v10; // r9
  _QWORD *Ptr; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  const GUID *v14; // r9
  WINBOOL fPending; // [rsp+30h] [rbp-79h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-71h] BYREF
  PSRWLOCK v17; // [rsp+40h] [rbp-69h] BYREF
  __int64 v18; // [rsp+48h] [rbp-61h] BYREF
  __int64 v19; // [rsp+50h] [rbp-59h] BYREF
  GUID ProviderId; // [rsp+58h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-39h] BYREF
  char *v22; // [rsp+80h] [rbp-29h]
  int v23; // [rsp+88h] [rbp-21h]
  int v24; // [rsp+8Ch] [rbp-1Dh]
  __int64 *v25; // [rsp+90h] [rbp-19h]
  __int64 v26; // [rsp+98h] [rbp-11h]
  PSRWLOCK *v27; // [rsp+A0h] [rbp-9h]
  __int64 v28; // [rsp+A8h] [rbp-1h]
  __int64 *v29; // [rsp+B0h] [rbp+7h]
  __int64 v30; // [rsp+B8h] [rbp+Fh]
  WINBOOL *p_fPending; // [rsp+C0h] [rbp+17h]
  __int64 v32; // [rsp+C8h] [rbp+1Fh]

  v3 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  if ( v3 )
  {
    v7 = v3 + 33;
    AcquireSRWLockExclusive(v7);
    SRWLock = 0;
  }
  else
  {
    v17 = 0;
    v7 = 0;
  }
  v8 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)WnsCPTracelogger::Provider() <= 5u )
    *(_OWORD *)(v8 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v8 + 8));
  *(_DWORD *)v8 = 1;
  if ( v7 )
    ReleaseSRWLockExclusive(v7);
  SRWLock = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock)
    && fPending )
  {
    qword_18004A768 = 0;
    SRWLock = (PSRWLOCK)&qword_18004A760;
    byte_18004A770 = 0;
    dword_18004A774 = 0;
    qword_18004A760 = (__int64)&wil::details::FeatureLogging::`vftable';
    CallbackContext = &`WnsCPTracelogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_633a74d489e420a2ff0e92495a1626f6_::_lambda_invoker_cdecl_);
    v9 = CallbackContext;
    qword_18004A768 = (__int64)CallbackContext;
    byte_18004A770 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    v10 = (ULONGLONG *)((char *)CallbackContext + 32);
    *((_QWORD *)CallbackContext + 5) = 0;
    v9[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v9, v10) )
      EventSetInformation(v9[4], 2, v9[1], *(unsigned __int16 *)v9[1]);
    dword_18004A774 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18004A760 + 8))(&qword_18004A760);
    InitOnceComplete(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &qword_18004A760);
  }
  Ptr = SRWLock[1].Ptr;
  if ( *(_DWORD *)Ptr > 5u )
  {
    fPending = a3;
    v18 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v13 = *((_QWORD *)this + 34);
    LODWORD(v17) = CurrentThreadId;
    v19 = 0;
    if ( !*(_BYTE *)(v13 + 4)
      || (v14 = (const GUID *)(v13 + 24), !*(_DWORD *)(v13 + 24))
      && !*(_DWORD *)(v13 + 28)
      && !*(_DWORD *)(v13 + 32)
      && !*(_DWORD *)(v13 + 36) )
    {
      v14 = 0;
    }
    v32 = 4;
    p_fPending = &fPending;
    v30 = 8;
    v29 = &v18;
    v28 = 4;
    v27 = &v17;
    v26 = 8;
    v25 = &v19;
    *(_DWORD *)&ProviderId.Data2 = 261;
    UserData.Ptr = Ptr[1];
    ProviderId.Data1 = 184549376;
    *(_QWORD *)ProviderId.Data4 = 0;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v22 = &byte_180041A77;
    UserData.Reserved = 2;
    v23 = 72;
    v24 = 1;
    LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(Ptr[4], (PCEVENT_DESCRIPTOR)&ProviderId, (LPCGUID)(v13 + 8), v14, 6u, &UserData);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180004fc0  mov     [rsp-8+arg_18], rbx
0x180004fc5  push    rbp
0x180004fc6  push    rdi
0x180004fc7  push    r12
0x180004fc9  push    r14
0x180004fcb  push    r15
0x180004fcd  lea     rbp, [rsp-37h]
0x180004fd2  sub     rsp, 0E0h
0x180004fd9  mov     rax, cs:__security_cookie
0x180004fe0  xor     rax, rsp
0x180004fe3  mov     [rbp+57h+var_30], rax
0x180004fe7  mov     rbx, [rcx+118h]
0x180004fee  xor     r12d, r12d
0x180004ff1  mov     [rsp+100h+arg_8], rsi
0x180004ff9  mov     r14d, r8d
0x180004ffc  mov     r15, rdx
0x180004fff  mov     rdi, rcx
0x180005002  test    rbx, rbx
0x180005005  jz      short loc_18000502F
0x180005007  add     rbx, 108h
0x18000500e  mov     rcx, rbx; SRWLock
0x180005011  call    cs:__imp_AcquireSRWLockExclusive
0x180005017  lea     rax, [rbp+57h+SRWLock]
0x18000501b  mov     [rax], r12
0x18000501e  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180005022  test    rcx, rcx
0x180005025  jz      short loc_180005048
0x180005027  call    cs:__imp_ReleaseSRWLockExclusive
0x18000502d  jmp     short loc_180005048
0x18000502f  lea     rax, [rbp+57h+var_C0]
0x180005033  mov     [rax], r12
0x180005036  mov     rcx, [rbp+57h+var_C0]; SRWLock
0x18000503a  test    rcx, rcx
0x18000503d  jz      short loc_180005045
0x18000503f  call    cs:__imp_ReleaseSRWLockExclusive
0x180005045  mov     rbx, r12
0x180005048  mov     rsi, [rdi+110h]
0x18000504f  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180005054  mov     ecx, [rax]
0x180005056  cmp     ecx, 5
0x180005059  jbe     short loc_18000506C
0x18000505b  lea     rdx, [rsi+8]; ActivityId
0x18000505f  mov     ecx, 3; ControlCode
0x180005064  call    cs:__imp_EventActivityIdControl
0x18000506a  jmp     short loc_180005073
0x18000506c  xorps   xmm0, xmm0
0x18000506f  movups  xmmword ptr [rsi+8], xmm0
0x180005073  mov     dword ptr [rsi], 1
0x180005079  test    rbx, rbx
0x18000507c  jz      short loc_180005087
0x18000507e  mov     rcx, rbx; SRWLock
0x180005081  call    cs:__imp_ReleaseSRWLockExclusive
0x180005087  lea     r9, [rbp+57h+SRWLock]; lpContext
0x18000508b  mov     [rbp+57h+SRWLock], r12
0x18000508f  lea     r8, [rbp+57h+fPending]; fPending
0x180005093  mov     [rbp+57h+fPending], r12d
0x180005097  xor     edx, edx; dwFlags
0x180005099  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x1800050a0  call    cs:__imp_InitOnceBeginInitialize
0x1800050a6  test    eax, eax
0x1800050a8  jz      loc_1800051A8
0x1800050ae  cmp     [rbp+57h+fPending], r12d
0x1800050b2  jz      loc_1800051A8
0x1800050b8  mov     [rsp+100h+arg_10], r13
0x1800050c0  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x1800050c7  lea     r13, qword_18004A760
0x1800050ce  mov     cs:qword_18004A768, r12
0x1800050d5  mov     [rbp+57h+SRWLock], r13
0x1800050d9  mov     cs:byte_18004A770, r12b
0x1800050e0  mov     cs:dword_18004A774, r12d
0x1800050e7  mov     cs:qword_18004A760, rax
0x1800050ee  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800050f5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x1800050fc  mov     cs:CallbackContext, rax
0x180005103  call    atexit
0x180005108  mov     rbx, cs:CallbackContext
0x18000510f  mov     cs:qword_18004A768, rbx
0x180005116  mov     cs:byte_18004A770, 1
0x18000511d  mov     rax, [rbx+8]
0x180005121  movups  xmm0, xmmword ptr [rax-10h]
0x180005125  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x180005129  cmp     [rbx+20h], r12
0x18000512d  jz      short loc_180005136
0x18000512f  mov     ecx, 5
0x180005134  int     29h; Win8: RtlFailFast(ecx)
0x180005136  lea     r9, [rbx+20h]; RegHandle
0x18000513a  mov     [rbx+28h], r12
0x18000513e  mov     r8, rbx; CallbackContext
0x180005141  mov     [rbx+30h], r12
0x180005145  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000514c  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x180005150  call    cs:__imp_EventRegister
0x180005156  test    eax, eax
0x180005158  jnz     short loc_180005171
0x18000515a  mov     r8, [rbx+8]
0x18000515e  mov     edx, 2
0x180005163  mov     rcx, [rbx+20h]
0x180005167  movzx   r9d, word ptr [r8]
0x18000516b  call    cs:__imp_EventSetInformation
0x180005171  mov     rax, cs:qword_18004A760
0x180005178  mov     rcx, r13
0x18000517b  mov     cs:dword_18004A774, 1
0x180005185  mov     rax, [rax+8]
0x180005189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000518e  mov     r8, r13; lpContext
0x180005191  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x180005198  xor     edx, edx; dwFlags
0x18000519a  call    cs:__imp_InitOnceComplete
0x1800051a0  mov     r13, [rsp+100h+arg_10]
0x1800051a8  mov     rax, [rbp+57h+SRWLock]
0x1800051ac  mov     rsi, [rsp+100h+arg_8]
0x1800051b4  mov     rbx, [rax+8]
0x1800051b8  mov     eax, [rbx]
0x1800051ba  cmp     eax, 5
0x1800051bd  jbe     loc_1800052C0
0x1800051c3  mov     [rbp+57h+fPending], r14d
0x1800051c7  mov     [rbp+57h+var_B8], r15
0x1800051cb  call    cs:__imp_GetCurrentThreadId
0x1800051d1  mov     r8, [rdi+110h]
0x1800051d8  mov     dword ptr [rbp+57h+var_C0], eax
0x1800051db  mov     [rbp+57h+var_B0], r12
0x1800051df  cmp     [r8+4], r12b
0x1800051e3  jz      short loc_180005201
0x1800051e5  cmp     [r8+18h], r12d
0x1800051e9  lea     r9, [r8+18h]
0x1800051ed  jnz     short loc_180005204
0x1800051ef  cmp     [r9+4], r12d
0x1800051f3  jnz     short loc_180005204
0x1800051f5  cmp     [r9+8], r12d
0x1800051f9  jnz     short loc_180005204
0x1800051fb  cmp     [r9+0Ch], r12d
0x1800051ff  jnz     short loc_180005204
0x180005201  mov     r9, r12; RelatedActivityId
0x180005204  mov     [rbp+57h+var_38], 4
0x18000520c  lea     rax, [rbp+57h+fPending]
0x180005210  mov     [rbp+57h+var_40], rax
0x180005214  lea     rcx, _TraceLoggingMetadata
0x18000521b  mov     [rbp+57h+var_48], 8
0x180005223  lea     rax, [rbp+57h+var_B8]
0x180005227  mov     [rbp+57h+var_50], rax
0x18000522b  lea     rdx, [rbp+57h+ProviderId]; EventDescriptor
0x18000522f  mov     [rbp+57h+var_58], 4
0x180005237  lea     rax, [rbp+57h+var_C0]
0x18000523b  mov     [rbp+57h+var_60], rax
0x18000523f  add     r8, 8; ActivityId
0x180005243  lea     rax, [rbp+57h+var_B0]
0x180005247  mov     [rbp+57h+var_68], 8
0x18000524f  mov     [rbp+57h+var_70], rax
0x180005253  movzx   eax, cs:word_180041A6D
0x18000525a  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x18000525d  mov     rax, [rbx+8]
0x180005261  mov     [rbp+57h+var_90.Ptr], rax
0x180005265  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x18000526c  mov     qword ptr [rbp+57h+ProviderId.Data4], r12
0x180005270  movzx   eax, word ptr [rax]
0x180005273  mov     [rbp+57h+var_90.Size], eax
0x180005276  lea     rax, byte_180041A77
0x18000527d  mov     [rbp+57h+var_80], rax
0x180005281  lea     rax, _TraceLoggingMetadataEnd
0x180005288  sub     eax, ecx
0x18000528a  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x180005291  mov     [rbp+57h+var_78], 48h ; 'H'
0x180005298  mov     [rbp+57h+var_74], 1
0x18000529f  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800052a2  mov     eax, dword ptr [rbp+57h+SRWLock]
0x1800052a5  mov     rcx, [rbx+20h]; RegHandle
0x1800052a9  lea     rax, [rbp+57h+var_90]
0x1800052ad  mov     [rsp+100h+UserData], rax; UserData
0x1800052b2  mov     [rsp+100h+UserDataCount], 6; UserDataCount
0x1800052ba  call    cs:__imp_EventWriteTransfer
0x1800052c0  mov     rcx, rdi
0x1800052c3  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800052c8  mov     rcx, [rbp+57h+var_30]
0x1800052cc  xor     rcx, rsp; StackCookie
0x1800052cf  call    __security_check_cookie
0x1800052d4  mov     rbx, [rsp+100h+arg_18]
0x1800052dc  add     rsp, 0E0h
0x1800052e3  pop     r15
0x1800052e5  pop     r14
0x1800052e7  pop     r12
0x1800052e9  pop     rdi
0x1800052ea  pop     rbp
0x1800052eb  retn
```
