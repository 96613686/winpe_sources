# NetSetupTraceLogging::EvaluatePluginFilter::StartActivity(_GUID const &,wchar_t const *,ulong)

- ea: `0x18000dd40`
- end: `0x18000e084`
- name: `?StartActivity@EvaluatePluginFilter@NetSetupTraceLogging@@QEAAXAEBU_GUID@@PEB_WK@Z`
- size: `836`
- prototype: `void __fastcall(NetSetupTraceLogging::EvaluatePluginFilter *__hidden this, const struct _GUID *, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d860`

## callees

- `0x180001008`
- `0x18000dd40`
- `0x180033720`
- `0x18003513c`
- `0x180064e14`
- `0x1800810d0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dda4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ddbe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000de17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dda4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ddbe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000de17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dd8c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dd8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000df1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000df1d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000dedf`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000dedf`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000de3a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000de3a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ddfa`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ddfa`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e056`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e056`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::EvaluatePluginFilter::StartActivity(
        NetSetupTraceLogging::EvaluatePluginFilter *this,
        const struct _GUID *a2,
        const wchar_t *a3,
        WINBOOL a4)
{
  RTL_SRWLOCK *v4; // rbx
  RTL_SRWLOCK *v9; // rbx
  __int64 v10; // rsi
  const struct _tlgProvider_t *v11; // rax
  _QWORD *Ptr; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  const GUID *v15; // r9
  __int64 v16; // rax
  int v18; // eax
  PSRWLOCK v19; // [rsp+30h] [rbp-99h] BYREF
  __int64 v20; // [rsp+38h] [rbp-91h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-89h] BYREF
  WINBOOL fPending; // [rsp+48h] [rbp-81h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-79h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-69h] BYREF
  char *v25; // [rsp+70h] [rbp-59h]
  int v26; // [rsp+78h] [rbp-51h]
  int v27; // [rsp+7Ch] [rbp-4Dh]
  __int64 *v28; // [rsp+80h] [rbp-49h]
  __int64 v29; // [rsp+88h] [rbp-41h]
  PSRWLOCK *v30; // [rsp+90h] [rbp-39h]
  __int64 v31; // [rsp+98h] [rbp-31h]
  const struct _GUID *v32; // [rsp+A0h] [rbp-29h]
  __int64 v33; // [rsp+A8h] [rbp-21h]
  const wchar_t *v34; // [rsp+B0h] [rbp-19h]
  int v35; // [rsp+B8h] [rbp-11h]
  int v36; // [rsp+BCh] [rbp-Dh]
  WINBOOL *p_fPending; // [rsp+C0h] [rbp-9h]
  __int64 v38; // [rsp+C8h] [rbp-1h]

  v4 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  if ( v4 )
  {
    v9 = v4 + 33;
    AcquireSRWLockExclusive(v9);
    SRWLock = 0;
  }
  else
  {
    v19 = 0;
    v9 = 0;
  }
  v10 = *((_QWORD *)this + 34);
  v11 = NetSetupTraceLogging::Provider();
  if ( *(_DWORD *)v11 > 5u && (*((_QWORD *)v11 + 2) & 2) != 0 && (*((_QWORD *)v11 + 3) & 2LL) == *((_QWORD *)v11 + 3) )
    EventActivityIdControl(3u, (LPGUID)(v10 + 8));
  else
    *(_OWORD *)(v10 + 8) = 0;
  *(_DWORD *)v10 = 1;
  if ( v9 )
    ReleaseSRWLockExclusive(v9);
  SRWLock = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`NetSetupTraceLogging::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock)
    && fPending )
  {
    qword_1800D4E80 = 0;
    SRWLock = (PSRWLOCK)&qword_1800D4E78;
    qword_1800D4E78 = (__int64)&NetSetupTraceLogging::`vftable';
    byte_1800D4E88 = 0;
    dword_1800D4E8C = 0;
    CallbackContext = &`NetSetupTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_17d5a69de876e4b99dd4545a5408007a_::_lambda_invoker_cdecl_);
    qword_1800D4E80 = (__int64)CallbackContext;
    byte_1800D4E88 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_1800D4E8C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800D4E78 + 8))(&qword_1800D4E78);
    InitOnceComplete(&`NetSetupTraceLogging::Instance'::`2'::wrapper, 0, &qword_1800D4E78);
  }
  Ptr = SRWLock[1].Ptr;
  if ( *(_DWORD *)Ptr > 5u && (Ptr[2] & 2) != 0 && (Ptr[3] & 2LL) == Ptr[3] )
  {
    fPending = a4;
    CurrentThreadId = GetCurrentThreadId();
    v14 = *((_QWORD *)this + 34);
    LODWORD(v19) = CurrentThreadId;
    v20 = 0;
    if ( !*(_BYTE *)(v14 + 4)
      || (v15 = (const GUID *)(v14 + 24), !*(_DWORD *)(v14 + 24))
      && !*(_DWORD *)(v14 + 28)
      && !*(_DWORD *)(v14 + 32)
      && !*(_DWORD *)(v14 + 36) )
    {
      v15 = 0;
    }
    v38 = 4;
    p_fPending = &fPending;
    if ( a3 )
    {
      v16 = -1;
      while ( a3[++v16] != 0 )
        ;
      v18 = 2 * v16 + 2;
    }
    else
    {
      a3 = &Data;
      v18 = 2;
    }
    v35 = v18;
    v34 = a3;
    v30 = &v19;
    v36 = 0;
    v28 = &v20;
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = Ptr[1];
    v32 = a2;
    v33 = 16;
    v31 = 4;
    v29 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 2;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v25 = byte_1800B3F6B;
    UserData.Reserved = 2;
    v26 = 106;
    v27 = 1;
    LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(Ptr[4], &EventDescriptor, (LPCGUID)(v14 + 8), v15, 7u, &UserData);
  }
  wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x18000dd40  push    rbp
0x18000dd42  push    rbx
0x18000dd43  push    rsi
0x18000dd44  push    rdi
0x18000dd45  push    r12
0x18000dd47  push    r13
0x18000dd49  push    r14
0x18000dd4b  push    r15
0x18000dd4d  lea     rbp, [rsp-1Fh]
0x18000dd52  sub     rsp, 0E8h
0x18000dd59  mov     rax, cs:__security_cookie
0x18000dd60  xor     rax, rsp
0x18000dd63  mov     [rbp+57h+var_50], rax
0x18000dd67  mov     rbx, [rcx+118h]
0x18000dd6e  xor     r13d, r13d
0x18000dd71  mov     r15d, r9d
0x18000dd74  mov     rdi, r8
0x18000dd77  mov     r12, rdx
0x18000dd7a  mov     r14, rcx
0x18000dd7d  test    rbx, rbx
0x18000dd80  jz      short loc_18000DDAC
0x18000dd82  add     rbx, 108h
0x18000dd89  mov     rcx, rbx; SRWLock
0x18000dd8c  call    cs:__imp_AcquireSRWLockExclusive
0x18000dd92  lea     rax, [rsp+120h+SRWLock]
0x18000dd97  mov     [rax], r13
0x18000dd9a  mov     rcx, [rsp+120h+SRWLock]; SRWLock
0x18000dd9f  test    rcx, rcx
0x18000dda2  jz      short loc_18000DDC7
0x18000dda4  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ddaa  jmp     short loc_18000DDC7
0x18000ddac  lea     rax, [rsp+120h+var_F0]
0x18000ddb1  mov     [rax], r13
0x18000ddb4  mov     rcx, [rsp+120h+var_F0]; SRWLock
0x18000ddb9  test    rcx, rcx
0x18000ddbc  jz      short loc_18000DDC4
0x18000ddbe  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ddc4  mov     rbx, r13
0x18000ddc7  mov     rsi, [r14+110h]
0x18000ddce  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x18000ddd3  mov     ecx, [rax]
0x18000ddd5  cmp     ecx, 5
0x18000ddd8  jbe     short loc_18000DE02
0x18000ddda  mov     rcx, [rax+18h]
0x18000ddde  mov     rax, [rax+10h]
0x18000dde2  test    al, 2
0x18000dde4  jz      short loc_18000DE02
0x18000dde6  mov     rax, rcx
0x18000dde9  and     eax, 2
0x18000ddec  cmp     rax, rcx
0x18000ddef  jnz     short loc_18000DE02
0x18000ddf1  lea     rdx, [rsi+8]; ActivityId
0x18000ddf5  mov     ecx, 3; ControlCode
0x18000ddfa  call    cs:__imp_EventActivityIdControl
0x18000de00  jmp     short loc_18000DE09
0x18000de02  xorps   xmm0, xmm0
0x18000de05  movups  xmmword ptr [rsi+8], xmm0
0x18000de09  mov     dword ptr [rsi], 1
0x18000de0f  test    rbx, rbx
0x18000de12  jz      short loc_18000DE1D
0x18000de14  mov     rcx, rbx; SRWLock
0x18000de17  call    cs:__imp_ReleaseSRWLockExclusive
0x18000de1d  lea     r9, [rsp+120h+SRWLock]; lpContext
0x18000de22  mov     [rsp+120h+SRWLock], r13
0x18000de27  lea     r8, [rsp+120h+fPending]; fPending
0x18000de2c  mov     [rsp+120h+fPending], r13d
0x18000de31  xor     edx, edx; dwFlags
0x18000de33  lea     rcx, ?wrapper@?1??Instance@NetSetupTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VNetSetupTraceLogging@@@details@wil@@A; lpInitOnce
0x18000de3a  call    cs:__imp_InitOnceBeginInitialize
0x18000de40  test    eax, eax
0x18000de42  jz      loc_18000DEE5
0x18000de48  cmp     [rsp+120h+fPending], r13d
0x18000de4d  jz      loc_18000DEE5
0x18000de53  lea     rbx, qword_1800D4E78
0x18000de5a  mov     cs:qword_1800D4E80, r13
0x18000de61  lea     rax, ??_7NetSetupTraceLogging@@6B@; const NetSetupTraceLogging::`vftable'
0x18000de68  mov     [rsp+120h+SRWLock], rbx
0x18000de6d  mov     cs:qword_1800D4E78, rax
0x18000de74  mov     cs:byte_1800D4E88, r13b
0x18000de7b  mov     cs:dword_1800D4E8C, r13d
0x18000de82  lea     rax, ?__hInner@?1???0StaticHandle@NetSetupTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `NetSetupTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000de89  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_17d5a69de876e4b99dd4545a5408007a_@@CA@XZ; void (__cdecl *)()
0x18000de90  mov     cs:CallbackContext, rax
0x18000de97  call    atexit
0x18000de9c  mov     rcx, cs:CallbackContext; CallbackContext
0x18000dea3  mov     cs:qword_1800D4E80, rcx
0x18000deaa  mov     cs:byte_1800D4E88, 1
0x18000deb1  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000deb6  mov     rax, cs:qword_1800D4E78
0x18000debd  mov     rcx, rbx
0x18000dec0  mov     cs:dword_1800D4E8C, 1
0x18000deca  mov     rax, [rax+8]
0x18000dece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ded3  mov     r8, rbx; lpContext
0x18000ded6  lea     rcx, ?wrapper@?1??Instance@NetSetupTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VNetSetupTraceLogging@@@details@wil@@A; lpInitOnce
0x18000dedd  xor     edx, edx; dwFlags
0x18000dedf  call    cs:__imp_InitOnceComplete
0x18000dee5  mov     rax, [rsp+120h+SRWLock]
0x18000deea  mov     rbx, [rax+8]
0x18000deee  mov     eax, [rbx]
0x18000def0  cmp     eax, 5
0x18000def3  jbe     loc_18000E05C
0x18000def9  mov     rcx, [rbx+18h]
0x18000defd  mov     rax, [rbx+10h]
0x18000df01  test    al, 2
0x18000df03  jz      loc_18000E05C
0x18000df09  mov     rax, rcx
0x18000df0c  and     eax, 2
0x18000df0f  cmp     rax, rcx
0x18000df12  jnz     loc_18000E05C
0x18000df18  mov     [rsp+120h+fPending], r15d
0x18000df1d  call    cs:__imp_GetCurrentThreadId
0x18000df23  mov     r8, [r14+110h]
0x18000df2a  mov     dword ptr [rsp+120h+var_F0], eax
0x18000df2e  mov     [rsp+120h+var_E8], r13
0x18000df33  cmp     [r8+4], r13b
0x18000df37  jz      short loc_18000DF55
0x18000df39  cmp     [r8+18h], r13d
0x18000df3d  lea     r9, [r8+18h]
0x18000df41  jnz     short loc_18000DF58
0x18000df43  cmp     [r9+4], r13d
0x18000df47  jnz     short loc_18000DF58
0x18000df49  cmp     [r9+8], r13d
0x18000df4d  jnz     short loc_18000DF58
0x18000df4f  cmp     [r9+0Ch], r13d
0x18000df53  jnz     short loc_18000DF58
0x18000df55  mov     r9, r13; RelatedActivityId
0x18000df58  mov     [rbp+57h+var_58], 4
0x18000df60  lea     rax, [rsp+120h+fPending]
0x18000df65  mov     [rbp+57h+var_60], rax
0x18000df69  test    rdi, rdi
0x18000df6c  jz      short loc_18000DF95
0x18000df6e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000df75  nop     word ptr [rax+rax+00000000h]
0x18000df80  cmp     [rdi+rax*2+2], r13w
0x18000df86  lea     rax, [rax+1]
0x18000df8a  jnz     short loc_18000DF80
0x18000df8c  lea     eax, ds:2[rax*2]
0x18000df93  jmp     short loc_18000DFA1
0x18000df95  lea     rdi, Data
0x18000df9c  mov     eax, 2
0x18000dfa1  mov     [rbp+57h+var_68], eax
0x18000dfa4  lea     rcx, _TraceLoggingMetadata
0x18000dfab  mov     [rbp+57h+var_70], rdi
0x18000dfaf  lea     rax, [rsp+120h+var_F0]
0x18000dfb4  mov     [rbp+57h+var_90], rax
0x18000dfb8  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000dfbc  lea     rax, [rsp+120h+var_E8]
0x18000dfc1  mov     [rbp+57h+var_64], r13d
0x18000dfc5  mov     [rbp+57h+var_A0], rax
0x18000dfc9  add     r8, 8; ActivityId
0x18000dfcd  movzx   eax, cs:word_1800B3F61
0x18000dfd4  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000dfd7  mov     rax, [rbx+8]
0x18000dfdb  mov     [rbp+57h+var_C0.Ptr], rax
0x18000dfdf  mov     [rbp+57h+var_80], r12
0x18000dfe3  mov     [rbp+57h+var_78], 10h
0x18000dfeb  mov     [rbp+57h+var_88], 4
0x18000dff3  mov     [rbp+57h+var_98], 8
0x18000dffb  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000e002  mov     [rbp+57h+EventDescriptor.Keyword], 2
0x18000e00a  movzx   eax, word ptr [rax]
0x18000e00d  mov     [rbp+57h+var_C0.Size], eax
0x18000e010  lea     rax, byte_1800B3F6B
0x18000e017  mov     [rbp+57h+var_B0], rax
0x18000e01b  lea     rax, _TraceLoggingMetadataEnd
0x18000e022  sub     eax, ecx
0x18000e024  mov     dword ptr [rbp+57h+var_C0.0Ch], 2
0x18000e02b  mov     [rbp+57h+var_A8], 6Ah ; 'j'
0x18000e032  mov     [rbp+57h+var_A4], 1
0x18000e039  mov     dword ptr [rsp+120h+SRWLock], eax
0x18000e03d  mov     eax, dword ptr [rsp+120h+SRWLock]
0x18000e041  mov     rcx, [rbx+20h]; RegHandle
0x18000e045  lea     rax, [rbp+57h+var_C0]
0x18000e049  mov     [rsp+120h+UserData], rax; UserData
0x18000e04e  mov     [rsp+120h+UserDataCount], 7; UserDataCount
0x18000e056  call    cs:__imp_EventWriteTransfer
0x18000e05c  mov     rcx, r14
0x18000e05f  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18000e064  mov     rcx, [rbp+57h+var_50]
0x18000e068  xor     rcx, rsp; StackCookie
0x18000e06b  call    __security_check_cookie
0x18000e070  add     rsp, 0E8h
0x18000e077  pop     r15
0x18000e079  pop     r14
0x18000e07b  pop     r13
0x18000e07d  pop     r12
0x18000e07f  pop     rdi
0x18000e080  pop     rsi
0x18000e081  pop     rbx
0x18000e082  pop     rbp
0x18000e083  retn
```
