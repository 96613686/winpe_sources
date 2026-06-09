# Microsoft::CoreUI::Dispatch::UserAdapter::DoWork(HWND__ *,Microsoft::CoreUI::Dispatch::UserAdapter$UserPriority,bool)

- ea: `0x18000870c`
- end: `0x1800089b3`
- name: `?DoWork@UserAdapter@Dispatch@CoreUI@Microsoft@@CAXPEAUHWND__@@W4UserAdapter$UserPriority@234@_N@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007550`

## callees

- `0x180007d80`
- `0x18000870c`
- `0x1800089c0`
- `0x180008ae8`
- `0x18000a3d4`
- `0x18000ec10`
- `0x18001ffcc`
- `0x180020df8`
- `0x180024980`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008765`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008765`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008972`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008972`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008961`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008961`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008788`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008957`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008788`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008957`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800087d3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800087d3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000877e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800087aa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800087bf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800087f5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008809`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800088c6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000877e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800087aa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800087bf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800087f5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008809`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800088c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::CoreUI::Dispatch::UserAdapter::DoWork(const char16_t *a1, unsigned int a2, char a3)
{
  struct Cn::Context *Value; // rbx
  char v6; // si
  __int64 v7; // rdi
  int v8; // ecx
  int v9; // eax
  int v10; // eax
  void *v11; // rsi
  __int64 v12; // rdx
  System::Object *v13; // rbx
  System::Object *v14; // rdi
  __int64 v15; // rax
  int v16; // edi
  HANDLE CurrentThread; // rax
  System::Object *v18; // [rsp+20h] [rbp-48h] BYREF
  void *v19; // [rsp+28h] [rbp-40h]
  struct System::Exception **v20; // [rsp+30h] [rbp-38h] BYREF
  void *retaddr; // [rsp+68h] [rbp+0h]
  const char16_t *v22; // [rsp+70h] [rbp+8h] BYREF
  __int64 v23; // [rsp+88h] [rbp+20h] BYREF

  v22 = a1;
  v23 = 0;
  if ( !Cn::Context::s_fTypeIsInitialized )
    CFlat::Abandonment::Fail(a1, retaddr);
  Value = 0;
  v6 = 0;
  while ( !Value )
  {
LABEL_26:
    Value = (struct Cn::Context *)TlsGetValue(Cn::Context::s_tlsStorage);
    if ( !Value )
    {
      Value = Cn::Context::NoContext_GetThreadContextOrNullAndLock();
      if ( !Value )
      {
        v10 = -2018443007;
        LODWORD(v22) = -2018443007;
        if ( !Cn::Process::Host )
          goto LABEL_15;
        (*(void (__fastcall **)(struct Cn::ICnHost *, const char16_t **, void *))(*(_QWORD *)Cn::Process::Host + 48LL))(
          Cn::Process::Host,
          &v22,
          retaddr);
        v10 = (int)v22;
        if ( (int)v22 < 0 )
          goto LABEL_15;
      }
    }
  }
  v7 = *((_QWORD *)Value + 11);
  if ( v7 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
    v8 = *(_DWORD *)(v7 + 60);
    *(_DWORD *)(v7 + 60) = v8 + 1;
    if ( !v8 )
    {
      *(_QWORD *)(v7 + 64) = TlsGetValue(Cn::Context::s_tlsStorage);
      *(_DWORD *)(v7 + 72) = GetCurrentThreadId();
    }
    v6 = 1;
  }
  v9 = *((_DWORD *)Value + 18);
  if ( !v9 )
  {
    if ( v7 )
    {
      if ( TlsGetValue(Cn::Context::s_tlsStorage)
        || TlsGetValue(Cn::Context::s_tlsStorage) != Value && !TlsSetValue(Cn::Context::s_tlsStorage, Value) )
      {
        CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode();
      }
      _InterlockedIncrement((volatile signed __int32 *)Value + 2);
    }
    v10 = 0;
    goto LABEL_15;
  }
  if ( v9 != 2 )
  {
    if ( v6 )
    {
      Cn::Engine::Lock::Leave((Cn::Engine::Lock *)v7);
      v6 = 0;
    }
    goto LABEL_26;
  }
  v15 = *((_QWORD *)Value + 12);
  if ( v15 )
    v16 = *(_DWORD *)(v15 + 152);
  else
    v16 = 0;
  if ( v16 != GetCurrentThreadId() )
  {
    CurrentThread = GetCurrentThread();
    WaitForSingleObjectEx(CurrentThread, 0x7530u, 0);
  }
  if ( Cn::Process::Host )
    (*(void (__fastcall **)(struct Cn::ICnHost *, void *))(*(_QWORD *)Cn::Process::Host + 56LL))(
      Cn::Process::Host,
      retaddr);
  CFlat::EntryExit::OnEndCallToCFlat(Value);
  v10 = -2018443005;
LABEL_15:
  if ( v10 >= 0 )
  {
    v11 = TlsGetValue(Cn::Context::s_tlsStorage);
    v19 = v11;
    v22 = *(const char16_t **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)TlsGetValue(Cn::Context::s_tlsStorage) + 6) + 56LL)
                                         + 40LL)
                             + 168LL);
    CFlat::Cast::Checked<CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::Win32EventLoopBridge>,Microsoft::CoreUI::Dispatch::EventLoopBridge *>(
      &v18,
      &v22);
    v13 = v18;
    v14 = (System::Object *)*((_QWORD *)v18 + 7);
    v22 = (const char16_t *)v14;
    if ( v14 )
      ++*((_DWORD *)v14 + 4);
    try
    {
      LOBYTE(v12) = a3;
      Microsoft::CoreUI::Dispatch::UserAdapter::OnUserDispatch(v14, v12, a2, &v23);
      if ( v14 )
        System::Object::ReleaseNotFrozen$(v14);
      System::Object::ReleaseNotFrozen$(v13);
    }
    catch ( System::Exception::Holder$ *v20 )
    {
      Microsoft::CoreUI::Runtime::Utils::UnhandledExceptionWorker(*v20);
      v11 = v19;
    }
    CFlat::EntryExit::OnEndCallToCFlat(v11);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
}

```

## disassembly

```asm
0x18000870c  mov     rax, rsp
0x18000870f  mov     [rax+10h], rbx
0x180008713  mov     [rax+8], rcx
0x180008717  push    rsi
0x180008718  push    rdi
0x180008719  push    r12
0x18000871b  push    r14
0x18000871d  push    r15
0x18000871f  sub     rsp, 40h
0x180008723  mov     r15b, r8b
0x180008726  mov     r12d, edx
0x180008729  mov     qword ptr [rax+20h], 0
0x180008731  mov     r14, [rsp+68h]
0x180008736  cmp     cs:?s_fTypeIsInitialized@Context@Cn@@0_NA, 0; bool Cn::Context::s_fTypeIsInitialized
0x18000873d  jz      loc_180008927
0x180008743  xor     ebx, ebx
0x180008745  xor     edi, edi
0x180008747  xor     sil, sil
0x18000874a  test    rbx, rbx
0x18000874d  jz      loc_1800088C0
0x180008753  test    sil, sil
0x180008756  jnz     short loc_180008794
0x180008758  mov     rdi, [rbx+58h]
0x18000875c  test    rdi, rdi
0x18000875f  jz      short loc_180008794
0x180008761  lea     rcx, [rdi+10h]; lpCriticalSection
0x180008765  call    cs:__imp_EnterCriticalSection
0x18000876b  mov     ecx, [rdi+3Ch]
0x18000876e  lea     eax, [rcx+1]
0x180008771  mov     [rdi+3Ch], eax
0x180008774  test    ecx, ecx
0x180008776  jnz     short loc_180008791
0x180008778  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18000877e  call    cs:__imp_TlsGetValue
0x180008784  mov     [rdi+40h], rax
0x180008788  call    cs:__imp_GetCurrentThreadId
0x18000878e  mov     [rdi+48h], eax
0x180008791  mov     sil, 1
0x180008794  mov     eax, [rbx+48h]
0x180008797  test    eax, eax
0x180008799  jnz     loc_180008936
0x18000879f  test    rdi, rdi
0x1800087a2  jz      short loc_1800087E5
0x1800087a4  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800087aa  call    cs:__imp_TlsGetValue
0x1800087b0  test    rax, rax
0x1800087b3  jnz     loc_180008930
0x1800087b9  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800087bf  call    cs:__imp_TlsGetValue
0x1800087c5  cmp     rax, rbx
0x1800087c8  jz      short loc_1800087E1
0x1800087ca  mov     rdx, rbx; lpTlsValue
0x1800087cd  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800087d3  call    cs:__imp_TlsSetValue
0x1800087d9  test    eax, eax
0x1800087db  jz      loc_180008930
0x1800087e1  lock inc dword ptr [rbx+8]
0x1800087e5  xor     eax, eax
0x1800087e7  test    eax, eax
0x1800087e9  js      loc_18000889C
0x1800087ef  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800087f5  call    cs:__imp_TlsGetValue
0x1800087fb  mov     rsi, rax
0x1800087fe  mov     [rsp+68h+var_40], rax
0x180008803  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180008809  call    cs:__imp_TlsGetValue
0x18000880f  mov     rcx, [rax+30h]
0x180008813  mov     rdx, [rcx+38h]
0x180008817  mov     rcx, [rdx+28h]
0x18000881b  mov     rdx, [rcx+0A8h]
0x180008822  mov     [rsp+68h+arg_0], rdx
0x180008827  lea     rdx, [rsp+68h+arg_0]
0x18000882c  lea     rcx, [rsp+68h+var_48]
0x180008831  call    ??$Checked@V?$SmartPtr@VWin32EventLoopBridge@Dispatch@CoreUI@Microsoft@@@CFlat@@PEAVEventLoopBridge@Dispatch@CoreUI@Microsoft@@@Cast@CFlat@@SA?A_P$$QEAPEAVEventLoopBridge@Dispatch@CoreUI@Microsoft@@@Z
0x180008836  nop
0x180008837  mov     rbx, [rsp+68h+var_48]
0x18000883c  mov     rdi, [rbx+38h]
0x180008840  mov     [rsp+68h+arg_0], rdi
0x180008845  test    rdi, rdi
0x180008848  jz      short loc_18000884D
0x18000884a  inc     dword ptr [rdi+10h]
0x18000884d  lea     r9, [rsp+68h+arg_18]
0x180008855  mov     r8d, r12d
0x180008858  mov     dl, r15b
0x18000885b  mov     rcx, rdi
0x18000885e  call    ?OnUserDispatch@UserAdapter@Dispatch@CoreUI@Microsoft@@AEAAX_NW4UserAdapter$UserPriority@234@PEAPEAX@Z; Microsoft::CoreUI::Dispatch::UserAdapter::OnUserDispatch(bool,Microsoft::CoreUI::Dispatch::UserAdapter$UserPriority,void * *)
0x180008863  nop
0x180008864  test    rdi, rdi
0x180008867  jz      short loc_180008872
0x180008869  mov     rcx, rdi; this
0x18000886c  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180008871  nop
0x180008872  mov     rcx, rbx; this
0x180008875  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000887a  nop
0x18000887b  mov     rcx, rsi; void *
0x18000887e  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x180008883  mov     rcx, [rsp+68h+arg_18]
0x18000888b  test    rcx, rcx
0x18000888e  jz      short loc_18000889C
0x180008890  mov     rax, [rcx]
0x180008893  mov     rax, [rax+10h]
0x180008897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000889c  mov     rbx, [rsp+68h+arg_8]
0x1800088a1  add     rsp, 40h
0x1800088a5  pop     r15
0x1800088a7  pop     r14
0x1800088a9  pop     r12
0x1800088ab  pop     rdi
0x1800088ac  pop     rsi
0x1800088ad  retn
0x1800088ae  test    sil, sil
0x1800088b1  jz      short loc_1800088C0
0x1800088b3  mov     rcx, rdi; this
0x1800088b6  call    ?Leave@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Leave(void)
0x1800088bb  xor     edi, edi
0x1800088bd  xor     sil, sil
0x1800088c0  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800088c6  call    cs:__imp_TlsGetValue
0x1800088cc  mov     rbx, rax
0x1800088cf  test    rax, rax
0x1800088d2  jnz     loc_18000874A
0x1800088d8  call    ?NoContext_GetThreadContextOrNullAndLock@Context@Cn@@SAPEAV12@XZ; Cn::Context::NoContext_GetThreadContextOrNullAndLock(void)
0x1800088dd  mov     rbx, rax
0x1800088e0  test    rax, rax
0x1800088e3  jnz     loc_18000874A
0x1800088e9  mov     eax, 87B10101h
0x1800088ee  mov     dword ptr [rsp+68h+arg_0], eax
0x1800088f2  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x1800088f9  test    rcx, rcx
0x1800088fc  jz      loc_1800087E7
0x180008902  mov     rax, [rcx]
0x180008905  mov     r8, r14
0x180008908  lea     rdx, [rsp+68h+arg_0]
0x18000890d  mov     rax, [rax+30h]
0x180008911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008916  mov     eax, dword ptr [rsp+68h+arg_0]
0x18000891a  test    eax, eax
0x18000891c  js      loc_1800087E7
0x180008922  jmp     loc_18000874A
0x180008927  mov     rdx, r14; void *
0x18000892a  call    ?Fail@Abandonment@CFlat@@SAXPEB_SPEAX@Z; CFlat::Abandonment::Fail(char16_t const *,void *)
0x180008930  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x180008936  sub     eax, 1
0x180008939  jz      loc_1800088AE
0x18000893f  cmp     eax, 1
0x180008942  jnz     loc_1800088AE
0x180008948  mov     rax, [rbx+60h]
0x18000894c  test    rax, rax
0x18000894f  jz      short loc_1800089A5
0x180008951  mov     edi, [rax+98h]
0x180008957  call    cs:__imp_GetCurrentThreadId
0x18000895d  cmp     edi, eax
0x18000895f  jz      short loc_180008978
0x180008961  call    cs:__imp_GetCurrentThread
0x180008967  mov     rcx, rax; hHandle
0x18000896a  xor     r8d, r8d; bAlertable
0x18000896d  mov     edx, 7530h; dwMilliseconds
0x180008972  call    cs:__imp_WaitForSingleObjectEx
0x180008978  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x18000897f  test    rcx, rcx
0x180008982  jz      short loc_180008993
0x180008984  mov     rax, [rcx]
0x180008987  mov     rdx, r14
0x18000898a  mov     rax, [rax+38h]
0x18000898e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008993  mov     rcx, rbx; void *
0x180008996  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x18000899b  mov     eax, 87B10103h
0x1800089a0  jmp     loc_1800087E7
0x1800089a5  xor     edi, edi
0x1800089a7  jmp     short loc_180008957
0x1800089a9  mov     rsi, [rsp+68h+var_40]
0x1800089ae  jmp     loc_18000887B
```
