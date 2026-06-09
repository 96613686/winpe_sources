# StateRepository::Trace::WinRT::API::Method::StartActivity(char const *,uint)

- ea: `0x18000cc30`
- end: `0x18000d09b`
- name: `?StartActivity@Method@API@WinRT@Trace@StateRepository@@QEAAXPEBDI@Z`
- size: `1131`
- prototype: `void __fastcall(StateRepository::Trace::WinRT::API::Method *this, const char *, WINBOOL)`
- caller_count: `24`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004650`
- `0x180004a70`
- `0x180009ba0`
- `0x18000a230`
- `0x18000a980`
- `0x18000ad70`
- `0x18000b030`
- `0x18000b3c0`
- `0x18000b780`
- `0x18000bb70`
- `0x18000c33c`
- `0x18000ca84`
- `0x18000cb58`
- `0x18000e940`
- `0x18000ec50`
- `0x18000f090`
- `0x18000f7b0`
- `0x18002ea40`
- `0x1800370b0`
- `0x180040e40`
- `0x18006ac90`
- `0x18007df20`
- `0x180080580`
- `0x180082850`

## callees

- `0x18000cc30`
- `0x180051650`
- `0x18018f650`
- `0x18018fadc`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cc91`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cca9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ce14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cc91`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cca9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ce14`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cc79`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cc79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cf4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cf4c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d063`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d063`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000cdf3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000cdf3`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000cd82`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000cedb`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000cd82`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000cedb`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000cd9d`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000cef6`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000cd9d`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000cef6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000cdd3`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000cf2d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000cdd3`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000cf2d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ccd6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ce37`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ccd6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ce37`

## pseudocode

```c
void __fastcall StateRepository::Trace::WinRT::API::Method::StartActivity(
        StateRepository::Trace::WinRT::API::Method *this,
        const char *a2,
        WINBOOL a3)
{
  RTL_SRWLOCK *v3; // rbx
  RTL_SRWLOCK *v7; // rbx
  __int64 v8; // r12
  _QWORD *v9; // rsi
  ULONGLONG *v10; // r9
  PVOID v11; // r8
  _QWORD *v12; // rbx
  bool v13; // zf
  ULONGLONG *v14; // r9
  _QWORD *Ptr; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  const GUID *v18; // r9
  __int64 v19; // rax
  int v20; // eax
  WINBOOL fPending; // [rsp+30h] [rbp-89h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-81h] BYREF
  PSRWLOCK v23; // [rsp+40h] [rbp-79h] BYREF
  __int64 v24; // [rsp+48h] [rbp-71h] BYREF
  GUID ProviderId; // [rsp+50h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-59h] BYREF
  void *v27; // [rsp+70h] [rbp-49h]
  int v28; // [rsp+78h] [rbp-41h]
  int v29; // [rsp+7Ch] [rbp-3Dh]
  __int64 *v30; // [rsp+80h] [rbp-39h]
  __int64 v31; // [rsp+88h] [rbp-31h]
  PSRWLOCK *v32; // [rsp+90h] [rbp-29h]
  __int64 v33; // [rsp+98h] [rbp-21h]
  const char *v34; // [rsp+A0h] [rbp-19h]
  int v35; // [rsp+A8h] [rbp-11h]
  int v36; // [rsp+ACh] [rbp-Dh]
  WINBOOL *p_fPending; // [rsp+B0h] [rbp-9h]
  __int64 v38; // [rsp+B8h] [rbp-1h]

  v3 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  if ( v3 )
  {
    v7 = v3 + 33;
    AcquireSRWLockExclusive(v7);
    SRWLock = 0;
  }
  else
  {
    v23 = 0;
    v7 = 0;
  }
  v8 = *((_QWORD *)this + 34);
  SRWLock = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(
         &`StateRepository::Tracing::Service::Instance'::`2'::wrapper,
         0,
         &fPending,
         (LPVOID *)&SRWLock)
    && fPending )
  {
    SRWLock = (PSRWLOCK)&qword_1804DFA68;
    qword_1804DFA70 = 0;
    byte_1804DFA78 = 0;
    dword_1804DFA7C = 0;
    qword_1804DFA68 = &StateRepository::Tracing::Core::`vftable';
    CallbackContext = &`StateRepository::Tracing::Service::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_1af0911b883bb9c47756bb2ef208bbf6_::_lambda_invoker_cdecl_);
    v9 = CallbackContext;
    qword_1804DFA70 = (__int64)CallbackContext;
    byte_1804DFA78 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    v10 = (ULONGLONG *)((char *)CallbackContext + 32);
    v11 = CallbackContext;
    *((_QWORD *)CallbackContext + 5) = 0;
    v9[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v11, v10) )
      EventSetInformation(v9[4], 2, v9[1], *(unsigned __int16 *)v9[1]);
    dword_1804DFA7C = 1;
    (*(void (__fastcall **)(void *))(qword_1804DFA68 + 8LL))(&qword_1804DFA68);
    InitOnceComplete(&`StateRepository::Tracing::Service::Instance'::`2'::wrapper, 0, &qword_1804DFA68);
  }
  if ( *(_DWORD *)SRWLock[1].Ptr <= 5u )
    *(_OWORD *)(v8 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v8 + 8));
  *(_DWORD *)v8 = 1;
  if ( v7 )
    ReleaseSRWLockExclusive(v7);
  SRWLock = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(
         &`StateRepository::Tracing::Service::Instance'::`2'::wrapper,
         0,
         &fPending,
         (LPVOID *)&SRWLock)
    && fPending )
  {
    SRWLock = (PSRWLOCK)&qword_1804DFA68;
    qword_1804DFA68 = &StateRepository::Tracing::Core::`vftable';
    qword_1804DFA70 = 0;
    byte_1804DFA78 = 0;
    dword_1804DFA7C = 0;
    CallbackContext = &`StateRepository::Tracing::Service::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_1af0911b883bb9c47756bb2ef208bbf6_::_lambda_invoker_cdecl_);
    v12 = CallbackContext;
    qword_1804DFA70 = (__int64)CallbackContext;
    byte_1804DFA78 = 1;
    v13 = *((_QWORD *)CallbackContext + 4) == 0;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( !v13 )
      __fastfail(5u);
    v14 = (ULONGLONG *)((char *)CallbackContext + 32);
    *((_QWORD *)CallbackContext + 5) = 0;
    v12[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v12, v14) )
      EventSetInformation(v12[4], 2, v12[1], *(unsigned __int16 *)v12[1]);
    dword_1804DFA7C = 1;
    (*(void (__fastcall **)(void *))(qword_1804DFA68 + 8LL))(&qword_1804DFA68);
    InitOnceComplete(&`StateRepository::Tracing::Service::Instance'::`2'::wrapper, 0, &qword_1804DFA68);
  }
  Ptr = SRWLock[1].Ptr;
  if ( *(_DWORD *)Ptr > 5u )
  {
    fPending = a3;
    CurrentThreadId = GetCurrentThreadId();
    v17 = *((_QWORD *)this + 34);
    LODWORD(v23) = CurrentThreadId;
    v24 = 0;
    if ( !*(_BYTE *)(v17 + 4)
      || (v18 = (const GUID *)(v17 + 24), !*(_DWORD *)(v17 + 24))
      && !*(_DWORD *)(v17 + 28)
      && !*(_DWORD *)(v17 + 32)
      && !*(_DWORD *)(v17 + 36) )
    {
      v18 = 0;
    }
    v38 = 4;
    p_fPending = &fPending;
    if ( a2 )
    {
      v19 = -1;
      do
        ++v19;
      while ( a2[v19] );
      v20 = v19 + 1;
    }
    else
    {
      a2 = (const char *)&word_1802B5BBC;
      v20 = 1;
    }
    v35 = v20;
    v34 = a2;
    v32 = &v23;
    v36 = 0;
    v30 = &v24;
    *(_DWORD *)&ProviderId.Data2 = 261;
    UserData.Ptr = Ptr[1];
    v33 = 4;
    v31 = 8;
    ProviderId.Data1 = 184549376;
    *(_QWORD *)ProviderId.Data4 = 0;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v27 = &unk_1804C4482;
    UserData.Reserved = 2;
    v28 = 75;
    v29 = 1;
    LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(Ptr[4], (PCEVENT_DESCRIPTOR)&ProviderId, (LPCGUID)(v17 + 8), v18, 6u, &UserData);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((StateRepository::Trace::WinRT::API::Method *)((char *)this + 288));
}

```

## disassembly

```asm
0x18000cc30  push    rbp
0x18000cc32  push    rbx
0x18000cc33  push    rsi
0x18000cc34  push    rdi
0x18000cc35  push    r12
0x18000cc37  push    r13
0x18000cc39  push    r14
0x18000cc3b  push    r15
0x18000cc3d  lea     rbp, [rsp-1Fh]
0x18000cc42  sub     rsp, 0D8h
0x18000cc49  mov     rax, cs:__security_cookie
0x18000cc50  xor     rax, rsp
0x18000cc53  mov     [rbp+57h+var_50], rax
0x18000cc57  mov     rbx, [rcx+118h]
0x18000cc5e  xor     r15d, r15d
0x18000cc61  mov     r13d, r8d
0x18000cc64  mov     rdi, rdx
0x18000cc67  mov     r14, rcx
0x18000cc6a  test    rbx, rbx
0x18000cc6d  jz      short loc_18000CC99
0x18000cc6f  add     rbx, 108h
0x18000cc76  mov     rcx, rbx; SRWLock
0x18000cc79  call    cs:__imp_AcquireSRWLockExclusive
0x18000cc7f  lea     rax, [rsp+110h+SRWLock]
0x18000cc84  mov     [rax], r15
0x18000cc87  mov     rcx, [rsp+110h+SRWLock]; SRWLock
0x18000cc8c  test    rcx, rcx
0x18000cc8f  jz      short loc_18000CCB2
0x18000cc91  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cc97  jmp     short loc_18000CCB2
0x18000cc99  lea     rax, [rbp+57h+var_D0]
0x18000cc9d  mov     [rax], r15
0x18000cca0  mov     rcx, [rbp+57h+var_D0]; SRWLock
0x18000cca4  test    rcx, rcx
0x18000cca7  jz      short loc_18000CCAF
0x18000cca9  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ccaf  mov     rbx, r15
0x18000ccb2  mov     r12, [r14+110h]
0x18000ccb9  lea     r9, [rsp+110h+SRWLock]; lpContext
0x18000ccbe  lea     r8, [rsp+110h+fPending]; fPending
0x18000ccc3  mov     [rsp+110h+SRWLock], r15
0x18000ccc8  xor     edx, edx; dwFlags
0x18000ccca  mov     [rsp+110h+fPending], r15d
0x18000cccf  lea     rcx, ?wrapper@?1??Instance@Service@Tracing@StateRepository@@KAPEAV234@XZ@4V?$static_lazy@VService@Tracing@StateRepository@@@details@wil@@A; lpInitOnce
0x18000ccd6  call    cs:__imp_InitOnceBeginInitialize
0x18000ccdc  lea     rsi, qword_1804DFA68
0x18000cce3  lea     rcx, ??_7Core@Tracing@StateRepository@@6B@; const StateRepository::Tracing::Core::`vftable'
0x18000ccea  lea     rdx, ?__hInner@?1???0StaticHandle@Service@Tracing@StateRepository@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `StateRepository::Tracing::Service::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000ccf1  test    eax, eax
0x18000ccf3  jz      loc_18000CDD9
0x18000ccf9  cmp     [rsp+110h+fPending], r15d
0x18000ccfe  jz      loc_18000CDD9
0x18000cd04  mov     [rsp+110h+SRWLock], rsi
0x18000cd09  mov     cs:qword_1804DFA70, r15
0x18000cd10  mov     cs:byte_1804DFA78, r15b
0x18000cd17  mov     cs:dword_1804DFA7C, r15d
0x18000cd1e  mov     cs:qword_1804DFA68, rcx
0x18000cd25  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1af0911b883bb9c47756bb2ef208bbf6_@@CA@XZ; void (__cdecl *)()
0x18000cd2c  mov     cs:CallbackContext, rdx
0x18000cd33  call    atexit
0x18000cd38  mov     rsi, cs:CallbackContext
0x18000cd3f  mov     cs:qword_1804DFA70, rsi
0x18000cd46  mov     cs:byte_1804DFA78, 1
0x18000cd4d  mov     rax, [rsi+8]
0x18000cd51  movups  xmm0, xmmword ptr [rax-10h]
0x18000cd55  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x18000cd59  cmp     [rsi+20h], r15
0x18000cd5d  jz      short loc_18000CD66
0x18000cd5f  mov     ecx, 5
0x18000cd64  int     29h; Win8: RtlFailFast(ecx)
0x18000cd66  xor     eax, eax
0x18000cd68  lea     r9, [rsi+20h]; RegHandle
0x18000cd6c  mov     r8, rsi; CallbackContext
0x18000cd6f  mov     [rsi+28h], rax
0x18000cd73  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000cd7a  mov     [rsi+30h], rax
0x18000cd7e  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x18000cd82  call    cs:__imp_EventRegister
0x18000cd88  test    eax, eax
0x18000cd8a  jnz     short loc_18000CDA3
0x18000cd8c  mov     r8, [rsi+8]
0x18000cd90  mov     edx, 2
0x18000cd95  mov     rcx, [rsi+20h]
0x18000cd99  movzx   r9d, word ptr [r8]
0x18000cd9d  call    cs:__imp_EventSetInformation
0x18000cda3  mov     rax, cs:qword_1804DFA68
0x18000cdaa  lea     rsi, qword_1804DFA68
0x18000cdb1  mov     rcx, rsi
0x18000cdb4  mov     cs:dword_1804DFA7C, 1
0x18000cdbe  mov     rax, [rax+8]
0x18000cdc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdc7  mov     r8, rsi; lpContext
0x18000cdca  lea     rcx, ?wrapper@?1??Instance@Service@Tracing@StateRepository@@KAPEAV234@XZ@4V?$static_lazy@VService@Tracing@StateRepository@@@details@wil@@A; lpInitOnce
0x18000cdd1  xor     edx, edx; dwFlags
0x18000cdd3  call    cs:__imp_InitOnceComplete
0x18000cdd9  mov     rax, [rsp+110h+SRWLock]
0x18000cdde  mov     rcx, [rax+8]
0x18000cde2  mov     eax, [rcx]
0x18000cde4  cmp     eax, 5
0x18000cde7  jbe     short loc_18000CDFB
0x18000cde9  lea     rdx, [r12+8]; ActivityId
0x18000cdee  mov     ecx, 3; ControlCode
0x18000cdf3  call    cs:__imp_EventActivityIdControl
0x18000cdf9  jmp     short loc_18000CE04
0x18000cdfb  xorps   xmm0, xmm0
0x18000cdfe  movups  xmmword ptr [r12+8], xmm0
0x18000ce04  mov     dword ptr [r12], 1
0x18000ce0c  test    rbx, rbx
0x18000ce0f  jz      short loc_18000CE1A
0x18000ce11  mov     rcx, rbx; SRWLock
0x18000ce14  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ce1a  lea     r9, [rsp+110h+SRWLock]; lpContext
0x18000ce1f  mov     [rsp+110h+SRWLock], r15
0x18000ce24  lea     r8, [rsp+110h+fPending]; fPending
0x18000ce29  mov     [rsp+110h+fPending], r15d
0x18000ce2e  xor     edx, edx; dwFlags
0x18000ce30  lea     rcx, ?wrapper@?1??Instance@Service@Tracing@StateRepository@@KAPEAV234@XZ@4V?$static_lazy@VService@Tracing@StateRepository@@@details@wil@@A; lpInitOnce
0x18000ce37  call    cs:__imp_InitOnceBeginInitialize
0x18000ce3d  test    eax, eax
0x18000ce3f  jz      loc_18000CF33
0x18000ce45  cmp     [rsp+110h+fPending], 0
0x18000ce4a  jz      loc_18000CF33
0x18000ce50  lea     rax, ??_7Core@Tracing@StateRepository@@6B@; const StateRepository::Tracing::Core::`vftable'
0x18000ce57  mov     [rsp+110h+SRWLock], rsi
0x18000ce5c  mov     cs:qword_1804DFA68, rax
0x18000ce63  mov     cs:qword_1804DFA70, r15
0x18000ce6a  mov     cs:byte_1804DFA78, 0
0x18000ce71  mov     cs:dword_1804DFA7C, r15d
0x18000ce78  lea     rax, ?__hInner@?1???0StaticHandle@Service@Tracing@StateRepository@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `StateRepository::Tracing::Service::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000ce7f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1af0911b883bb9c47756bb2ef208bbf6_@@CA@XZ; void (__cdecl *)()
0x18000ce86  mov     cs:CallbackContext, rax
0x18000ce8d  call    atexit
0x18000ce92  mov     rbx, cs:CallbackContext
0x18000ce99  mov     cs:qword_1804DFA70, rbx
0x18000cea0  mov     cs:byte_1804DFA78, 1
0x18000cea7  cmp     qword ptr [rbx+20h], 0
0x18000ceac  mov     rax, [rbx+8]
0x18000ceb0  movups  xmm0, xmmword ptr [rax-10h]
0x18000ceb4  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x18000ceb8  jz      short loc_18000CEC1
0x18000ceba  mov     ecx, 5
0x18000cebf  int     29h; Win8: RtlFailFast(ecx)
0x18000cec1  lea     r9, [rbx+20h]; RegHandle
0x18000cec5  mov     [rbx+28h], r15
0x18000cec9  mov     r8, rbx; CallbackContext
0x18000cecc  mov     [rbx+30h], r15
0x18000ced0  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000ced7  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x18000cedb  call    cs:__imp_EventRegister
0x18000cee1  test    eax, eax
0x18000cee3  jnz     short loc_18000CEFC
0x18000cee5  mov     r8, [rbx+8]
0x18000cee9  mov     edx, 2
0x18000ceee  mov     rcx, [rbx+20h]
0x18000cef2  movzx   r9d, word ptr [r8]
0x18000cef6  call    cs:__imp_EventSetInformation
0x18000cefc  mov     rax, cs:qword_1804DFA68
0x18000cf03  lea     rcx, qword_1804DFA68
0x18000cf0a  mov     cs:dword_1804DFA7C, 1
0x18000cf14  mov     rax, [rax+8]
0x18000cf18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf1d  lea     r8, qword_1804DFA68; lpContext
0x18000cf24  xor     edx, edx; dwFlags
0x18000cf26  lea     rcx, ?wrapper@?1??Instance@Service@Tracing@StateRepository@@KAPEAV234@XZ@4V?$static_lazy@VService@Tracing@StateRepository@@@details@wil@@A; lpInitOnce
0x18000cf2d  call    cs:__imp_InitOnceComplete
0x18000cf33  mov     rax, [rsp+110h+SRWLock]
0x18000cf38  mov     rbx, [rax+8]
0x18000cf3c  mov     eax, [rbx]
0x18000cf3e  cmp     eax, 5
0x18000cf41  jbe     loc_18000D069
0x18000cf47  mov     [rsp+110h+fPending], r13d
0x18000cf4c  call    cs:__imp_GetCurrentThreadId
0x18000cf52  mov     r8, [r14+110h]
0x18000cf59  mov     dword ptr [rbp+57h+var_D0], eax
0x18000cf5c  mov     [rbp+57h+var_C8], r15
0x18000cf60  cmp     byte ptr [r8+4], 0
0x18000cf65  jz      short loc_18000CF87
0x18000cf67  cmp     dword ptr [r8+18h], 0
0x18000cf6c  lea     r9, [r8+18h]
0x18000cf70  jnz     short loc_18000CF8A
0x18000cf72  cmp     dword ptr [r9+4], 0
0x18000cf77  jnz     short loc_18000CF8A
0x18000cf79  cmp     dword ptr [r9+8], 0
0x18000cf7e  jnz     short loc_18000CF8A
0x18000cf80  cmp     dword ptr [r9+0Ch], 0
0x18000cf85  jnz     short loc_18000CF8A
0x18000cf87  mov     r9, r15; RelatedActivityId
0x18000cf8a  mov     [rbp+57h+var_58], 4
0x18000cf92  lea     rax, [rsp+110h+fPending]
0x18000cf97  mov     [rbp+57h+var_60], rax
0x18000cf9b  test    rdi, rdi
0x18000cf9e  jz      short loc_18000CFB4
0x18000cfa0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000cfa7  inc     rax
0x18000cfaa  cmp     byte ptr [rdi+rax], 0
0x18000cfae  jnz     short loc_18000CFA7
0x18000cfb0  inc     eax
0x18000cfb2  jmp     short loc_18000CFC0
0x18000cfb4  lea     rdi, word_1802B5BBC
0x18000cfbb  mov     eax, 1
0x18000cfc0  mov     [rbp+57h+var_68], eax
0x18000cfc3  lea     rcx, _TraceLoggingMetadata
0x18000cfca  mov     [rbp+57h+var_70], rdi
0x18000cfce  lea     rax, [rbp+57h+var_D0]
0x18000cfd2  mov     [rbp+57h+var_80], rax
0x18000cfd6  lea     rdx, [rbp+57h+ProviderId]; EventDescriptor
0x18000cfda  lea     rax, [rbp+57h+var_C8]
0x18000cfde  mov     [rbp+57h+var_64], r15d
0x18000cfe2  mov     [rbp+57h+var_90], rax
0x18000cfe6  add     r8, 8; ActivityId
0x18000cfea  movzx   eax, cs:word_1804C4478
0x18000cff1  mov     dword ptr [rbp+57h+ProviderId.Data2], eax
0x18000cff4  mov     rax, [rbx+8]
0x18000cff8  mov     [rbp+57h+var_B0.Ptr], rax
0x18000cffc  mov     [rbp+57h+var_78], 4
0x18000d004  mov     [rbp+57h+var_88], 8
0x18000d00c  mov     [rbp+57h+ProviderId.Data1], 0B000000h
0x18000d013  mov     qword ptr [rbp+57h+ProviderId.Data4], r15
0x18000d017  movzx   eax, word ptr [rax]
0x18000d01a  mov     [rbp+57h+var_B0.Size], eax
0x18000d01d  lea     rax, unk_1804C4482
0x18000d024  mov     [rbp+57h+var_A0], rax
0x18000d028  lea     rax, _TraceLoggingMetadataEnd
0x18000d02f  sub     eax, ecx
0x18000d031  mov     dword ptr [rbp+57h+var_B0.0Ch], 2
0x18000d038  mov     [rbp+57h+var_98], 4Bh ; 'K'
0x18000d03f  mov     [rbp+57h+var_94], 1
0x18000d046  mov     dword ptr [rsp+110h+SRWLock], eax
0x18000d04a  mov     eax, dword ptr [rsp+110h+SRWLock]
0x18000d04e  mov     rcx, [rbx+20h]; RegHandle
0x18000d052  lea     rax, [rbp+57h+var_B0]
0x18000d056  mov     [rsp+110h+UserData], rax; UserData
0x18000d05b  mov     [rsp+110h+UserDataCount], 6; UserDataCount
0x18000d063  call    cs:__imp_EventWriteTransfer
0x18000d069  lea     rcx, [r14+120h]; this
0x18000d070  cmp     dword ptr [rcx+18h], 0
0x18000d074  jnz     short loc_18000D07B
0x18000d076  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000d07b  mov     rcx, [rbp+57h+var_50]
0x18000d07f  xor     rcx, rsp; StackCookie
0x18000d082  call    __security_check_cookie
0x18000d087  add     rsp, 0D8h
0x18000d08e  pop     r15
0x18000d090  pop     r14
0x18000d092  pop     r13
0x18000d094  pop     r12
0x18000d096  pop     rdi
0x18000d097  pop     rsi
0x18000d098  pop     rbx
0x18000d099  pop     rbp
0x18000d09a  retn
```
