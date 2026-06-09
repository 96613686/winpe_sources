# WnsCPLog::WnsCMRequestChannel::StartActivity(unsigned __int64,ushort const *,ulong,ulong,long)

- ea: `0x180006b00`
- end: `0x180006ea0`
- name: `?StartActivity@WnsCMRequestChannel@WnsCPLog@@QEAAX_KPEBGKKJ@Z`
- size: `928`
- prototype: `void __fastcall(WnsCPLog::WnsCMRequestChannel *__hidden this, unsigned __int64, const unsigned __int16 *, unsigned int, unsigned int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800054a0`
- `0x180006eb0`

## callees

- `0x180006b00`
- `0x18000d830`
- `0x18000d8f0`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006b4c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006b4c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b64`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006bc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b64`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006bc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d19`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006e72`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006e72`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180006ba3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180006ba3`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180006caa`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180006caa`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180006c8f`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180006c8f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006be3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006be3`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006ce1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006ce1`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMRequestChannel::StartActivity(
        WnsCPLog::WnsCMRequestChannel *this,
        __int64 a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int a5,
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
  __int64 v19; // rax
  int v21; // eax
  WINBOOL fPending; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+44h] [rbp-BCh] BYREF
  PSRWLOCK v26; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  GUID ProviderId; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-90h] BYREF
  char *v31; // [rsp+80h] [rbp-80h]
  int v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+8Ch] [rbp-74h]
  __int64 *v34; // [rsp+90h] [rbp-70h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  PSRWLOCK *v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 *v38; // [rsp+B0h] [rbp-50h]
  __int64 v39; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v40; // [rsp+C0h] [rbp-40h]
  int v41; // [rsp+C8h] [rbp-38h]
  int v42; // [rsp+CCh] [rbp-34h]
  int *v43; // [rsp+D0h] [rbp-30h]
  __int64 v44; // [rsp+D8h] [rbp-28h]
  unsigned int *v45; // [rsp+E0h] [rbp-20h]
  __int64 v46; // [rsp+E8h] [rbp-18h]
  WINBOOL *p_fPending; // [rsp+F0h] [rbp-10h]
  __int64 v48; // [rsp+F8h] [rbp-8h]

  v6 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  if ( v6 )
  {
    v11 = v6 + 33;
    AcquireSRWLockExclusive(v11);
    SRWLock = 0;
  }
  else
  {
    v26 = 0;
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
    v24 = a5;
    v25 = a4;
    v27 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v17 = *((_QWORD *)this + 34);
    LODWORD(v26) = CurrentThreadId;
    v28 = 0;
    if ( !*(_BYTE *)(v17 + 4)
      || (v18 = (const GUID *)(v17 + 24), !*(_DWORD *)(v17 + 24))
      && !*(_DWORD *)(v17 + 28)
      && !*(_DWORD *)(v17 + 32)
      && !*(_DWORD *)(v17 + 36) )
    {
      v18 = 0;
    }
    v48 = 4;
    p_fPending = &fPending;
    v45 = &v24;
    v43 = &v25;
    v46 = 4;
    v44 = 4;
    if ( a3 )
    {
      v19 = -1;
      while ( a3[++v19] != 0 )
        ;
      v21 = 2 * v19 + 2;
    }
    else
    {
      a3 = (const unsigned __int16 *)&dword_18003A074;
      v21 = 2;
    }
    v41 = v21;
    v40 = a3;
    v38 = &v27;
    v42 = 0;
    v36 = &v26;
    v39 = 8;
    v34 = &v28;
    *(_DWORD *)&ProviderId.Data2 = 261;
    UserData.Ptr = Ptr[1];
    v37 = 4;
    v35 = 8;
    ProviderId.Data1 = 184549376;
    *(_QWORD *)ProviderId.Data4 = 0;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v31 = byte_18003F045;
    UserData.Reserved = 2;
    v32 = 109;
    v33 = 1;
    LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(Ptr[4], (PCEVENT_DESCRIPTOR)&ProviderId, (LPCGUID)(v17 + 8), v18, 9u, &UserData);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180006b00  push    rbp
0x180006b02  push    rbx
0x180006b03  push    rsi
0x180006b04  push    rdi
0x180006b05  push    r12
0x180006b07  push    r13
0x180006b09  push    r14
0x180006b0b  push    r15
0x180006b0d  lea     rbp, [rsp-18h]
0x180006b12  sub     rsp, 118h
0x180006b19  mov     rax, cs:__security_cookie
0x180006b20  xor     rax, rsp
0x180006b23  mov     [rbp+50h+var_50], rax
0x180006b27  mov     rbx, [rcx+118h]
0x180006b2e  xor     r13d, r13d
0x180006b31  mov     r15d, r9d
0x180006b34  mov     rdi, r8
0x180006b37  mov     r12, rdx
0x180006b3a  mov     r14, rcx
0x180006b3d  test    rbx, rbx
0x180006b40  jz      short loc_180006B6C
0x180006b42  add     rbx, 108h
0x180006b49  mov     rcx, rbx; SRWLock
0x180006b4c  call    cs:__imp_AcquireSRWLockExclusive
0x180006b52  lea     rax, [rsp+150h+SRWLock]
0x180006b57  mov     [rax], r13
0x180006b5a  mov     rcx, [rsp+150h+SRWLock]; SRWLock
0x180006b5f  test    rcx, rcx
0x180006b62  jz      short loc_180006B87
0x180006b64  call    cs:__imp_ReleaseSRWLockExclusive
0x180006b6a  jmp     short loc_180006B87
0x180006b6c  lea     rax, [rsp+150h+var_108]
0x180006b71  mov     [rax], r13
0x180006b74  mov     rcx, [rsp+150h+var_108]; SRWLock
0x180006b79  test    rcx, rcx
0x180006b7c  jz      short loc_180006B84
0x180006b7e  call    cs:__imp_ReleaseSRWLockExclusive
0x180006b84  mov     rbx, r13
0x180006b87  mov     rsi, [r14+110h]
0x180006b8e  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180006b93  mov     ecx, [rax]
0x180006b95  cmp     ecx, 5
0x180006b98  jbe     short loc_180006BAB
0x180006b9a  lea     rdx, [rsi+8]; ActivityId
0x180006b9e  mov     ecx, 3; ControlCode
0x180006ba3  call    cs:__imp_EventActivityIdControl
0x180006ba9  jmp     short loc_180006BB2
0x180006bab  xorps   xmm0, xmm0
0x180006bae  movups  xmmword ptr [rsi+8], xmm0
0x180006bb2  mov     dword ptr [rsi], 1
0x180006bb8  test    rbx, rbx
0x180006bbb  jz      short loc_180006BC6
0x180006bbd  mov     rcx, rbx; SRWLock
0x180006bc0  call    cs:__imp_ReleaseSRWLockExclusive
0x180006bc6  lea     r9, [rsp+150h+SRWLock]; lpContext
0x180006bcb  mov     [rsp+150h+SRWLock], r13
0x180006bd0  lea     r8, [rsp+150h+fPending]; fPending
0x180006bd5  mov     [rsp+150h+fPending], r13d
0x180006bda  xor     edx, edx; dwFlags
0x180006bdc  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x180006be3  call    cs:__imp_InitOnceBeginInitialize
0x180006be9  test    eax, eax
0x180006beb  jz      loc_180006CE7
0x180006bf1  cmp     [rsp+150h+fPending], r13d
0x180006bf6  jz      loc_180006CE7
0x180006bfc  lea     rax, qword_18004A760
0x180006c03  mov     cs:qword_18004A768, r13
0x180006c0a  mov     [rsp+150h+SRWLock], rax
0x180006c0f  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180006c16  mov     cs:qword_18004A760, rax
0x180006c1d  mov     cs:byte_18004A770, r13b
0x180006c24  mov     cs:dword_18004A774, r13d
0x180006c2b  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WnsCPTracelogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180006c32  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x180006c39  mov     cs:CallbackContext, rax
0x180006c40  call    atexit
0x180006c45  mov     rbx, cs:CallbackContext
0x180006c4c  mov     cs:qword_18004A768, rbx
0x180006c53  mov     cs:byte_18004A770, 1
0x180006c5a  mov     rax, [rbx+8]
0x180006c5e  movups  xmm0, xmmword ptr [rax-10h]
0x180006c62  movups  xmmword ptr [rsp+150h+ProviderId.Data1], xmm0
0x180006c67  cmp     [rbx+20h], r13
0x180006c6b  jz      short loc_180006C74
0x180006c6d  mov     ecx, 5
0x180006c72  int     29h; Win8: RtlFailFast(ecx)
0x180006c74  lea     r9, [rbx+20h]; RegHandle
0x180006c78  mov     [rbx+28h], r13
0x180006c7c  mov     r8, rbx; CallbackContext
0x180006c7f  mov     [rbx+30h], r13
0x180006c83  lea     rdx, _tlgEnableCallback; EnableCallback
0x180006c8a  lea     rcx, [rsp+150h+ProviderId]; ProviderId
0x180006c8f  call    cs:__imp_EventRegister
0x180006c95  test    eax, eax
0x180006c97  jnz     short loc_180006CB0
0x180006c99  mov     r8, [rbx+8]
0x180006c9d  mov     edx, 2
0x180006ca2  mov     rcx, [rbx+20h]
0x180006ca6  movzx   r9d, word ptr [r8]
0x180006caa  call    cs:__imp_EventSetInformation
0x180006cb0  mov     rax, cs:qword_18004A760
0x180006cb7  lea     rcx, qword_18004A760
0x180006cbe  mov     cs:dword_18004A774, 1
0x180006cc8  mov     rax, [rax+8]
0x180006ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cd1  lea     r8, qword_18004A760; lpContext
0x180006cd8  xor     edx, edx; dwFlags
0x180006cda  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x180006ce1  call    cs:__imp_InitOnceComplete
0x180006ce7  mov     rax, [rsp+150h+SRWLock]
0x180006cec  mov     rbx, [rax+8]
0x180006cf0  mov     eax, [rbx]
0x180006cf2  cmp     eax, 5
0x180006cf5  jbe     loc_180006E78
0x180006cfb  mov     eax, [rbp+50h+arg_28]
0x180006d01  mov     [rsp+150h+fPending], eax
0x180006d05  mov     eax, [rbp+50h+arg_20]
0x180006d0b  mov     [rsp+150h+var_110], eax
0x180006d0f  mov     [rsp+150h+var_10C], r15d
0x180006d14  mov     [rsp+150h+var_100], r12
0x180006d19  call    cs:__imp_GetCurrentThreadId
0x180006d1f  mov     r8, [r14+110h]
0x180006d26  mov     dword ptr [rsp+150h+var_108], eax
0x180006d2a  mov     [rsp+150h+var_F8], r13
0x180006d2f  cmp     [r8+4], r13b
0x180006d33  jz      short loc_180006D51
0x180006d35  cmp     [r8+18h], r13d
0x180006d39  lea     r9, [r8+18h]
0x180006d3d  jnz     short loc_180006D54
0x180006d3f  cmp     [r9+4], r13d
0x180006d43  jnz     short loc_180006D54
0x180006d45  cmp     [r9+8], r13d
0x180006d49  jnz     short loc_180006D54
0x180006d4b  cmp     [r9+0Ch], r13d
0x180006d4f  jnz     short loc_180006D54
0x180006d51  mov     r9, r13; RelatedActivityId
0x180006d54  mov     [rbp+50h+var_58], 4
0x180006d5c  lea     rax, [rsp+150h+fPending]
0x180006d61  mov     [rbp+50h+var_60], rax
0x180006d65  lea     rax, [rsp+150h+var_110]
0x180006d6a  mov     [rbp+50h+var_70], rax
0x180006d6e  lea     rax, [rsp+150h+var_10C]
0x180006d73  mov     [rbp+50h+var_80], rax
0x180006d77  mov     [rbp+50h+var_68], 4
0x180006d7f  mov     [rbp+50h+var_78], 4
0x180006d87  test    rdi, rdi
0x180006d8a  jz      short loc_180006DA8
0x180006d8c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006d93  cmp     [rdi+rax*2+2], r13w
0x180006d99  lea     rax, [rax+1]
0x180006d9d  jnz     short loc_180006D93
0x180006d9f  lea     eax, ds:2[rax*2]
0x180006da6  jmp     short loc_180006DB4
0x180006da8  lea     rdi, dword_18003A074
0x180006daf  mov     eax, 2
0x180006db4  mov     [rbp+50h+var_88], eax
0x180006db7  lea     rcx, _TraceLoggingMetadata
0x180006dbe  mov     [rbp+50h+var_90], rdi
0x180006dc2  lea     rax, [rsp+150h+var_100]
0x180006dc7  mov     [rbp+50h+var_A0], rax
0x180006dcb  lea     rdx, [rsp+150h+ProviderId]; EventDescriptor
0x180006dd0  mov     [rbp+50h+var_84], r13d
0x180006dd4  lea     rax, [rsp+150h+var_108]
0x180006dd9  mov     [rbp+50h+var_B0], rax
0x180006ddd  add     r8, 8; ActivityId
0x180006de1  lea     rax, [rsp+150h+var_F8]
0x180006de6  mov     [rbp+50h+var_98], 8
0x180006dee  mov     [rbp+50h+var_C0], rax
0x180006df2  movzx   eax, cs:word_18003F03B
0x180006df9  mov     dword ptr [rsp+150h+ProviderId.Data2], eax
0x180006dfd  mov     rax, [rbx+8]
0x180006e01  mov     [rsp+150h+var_E0.Ptr], rax
0x180006e06  mov     [rbp+50h+var_A8], 4
0x180006e0e  mov     [rbp+50h+var_B8], 8
0x180006e16  mov     [rsp+150h+ProviderId.Data1], 0B000000h
0x180006e1e  mov     qword ptr [rsp+150h+ProviderId.Data4], r13
0x180006e23  movzx   eax, word ptr [rax]
0x180006e26  mov     [rsp+150h+var_E0.Size], eax
0x180006e2a  lea     rax, byte_18003F045
0x180006e31  mov     [rbp+50h+var_D0], rax
0x180006e35  lea     rax, _TraceLoggingMetadataEnd
0x180006e3c  sub     eax, ecx
0x180006e3e  mov     dword ptr [rsp+150h+var_E0.0Ch], 2
0x180006e46  mov     [rbp+50h+var_C8], 6Dh ; 'm'
0x180006e4d  mov     [rbp+50h+var_C4], 1
0x180006e54  mov     dword ptr [rsp+150h+SRWLock], eax
0x180006e58  mov     eax, dword ptr [rsp+150h+SRWLock]
0x180006e5c  mov     rcx, [rbx+20h]; RegHandle
0x180006e60  lea     rax, [rsp+150h+var_E0]
0x180006e65  mov     [rsp+150h+UserData], rax; UserData
0x180006e6a  mov     [rsp+150h+UserDataCount], 9; UserDataCount
0x180006e72  call    cs:__imp_EventWriteTransfer
0x180006e78  mov     rcx, r14
0x180006e7b  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180006e80  mov     rcx, [rbp+50h+var_50]
0x180006e84  xor     rcx, rsp; StackCookie
0x180006e87  call    __security_check_cookie
0x180006e8c  add     rsp, 118h
0x180006e93  pop     r15
0x180006e95  pop     r14
0x180006e97  pop     r13
0x180006e99  pop     r12
0x180006e9b  pop     rdi
0x180006e9c  pop     rsi
0x180006e9d  pop     rbx
0x180006e9e  pop     rbp
0x180006e9f  retn
```
