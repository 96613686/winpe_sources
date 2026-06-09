# Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$::GetItem(uint,uint,void * *)

- ea: `0x180021200`
- end: `0x180021538`
- name: `?GetItem@ExportAdapter$@IExportMessageConversation@CoreUI@Microsoft@@UEAAJIIPEAPEAX@Z`
- size: `824`
- prototype: `__int64 __fastcall(Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$ *__hidden this, unsigned int, unsigned int, void **)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007d80`
- `0x1800089c0`
- `0x180010ed0`
- `0x18001d848`
- `0x18001ffcc`
- `0x180020df8`
- `0x180021200`
- `0x180024980`
- `0x18003950c`
- `0x18008ae1c`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021272`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021272`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180021504`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180021504`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800214f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800214f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021295`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800214e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021295`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800214e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800212ee`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800212ee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002128b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800212c5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800212da`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800213cc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002142f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800214d5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002128b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800212c5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800212da`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800213cc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002142f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800214d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$::GetItem(
        Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$ *this,
        unsigned int a2,
        unsigned int a3,
        void **a4)
{
  __int64 v7; // rbx
  struct Cn::Context *v8; // rbx
  struct Cn::Context *Value; // rdi
  char v10; // bp
  __int64 v11; // rsi
  int v12; // ecx
  int v13; // eax
  int v14; // eax
  unsigned int v15; // esi
  __int64 v16; // rdi
  int v17; // eax
  __int64 *v18; // r8
  int i; // edx
  __int64 v20; // rax
  const void *ComInterface; // rcx
  __int64 v23; // rax
  int v24; // esi
  HANDLE CurrentThread; // rax
  void *retaddr; // [rsp+68h] [rbp+0h]
  int v27; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v28; // [rsp+78h] [rbp+10h]

  v28 = a2;
  v7 = *((_QWORD *)this + 2);
  if ( !*(_QWORD *)(v7 + 24) )
    CFlat::Abandonment::Fail((const char16_t *)this);
  if ( !Cn::Context::s_fTypeIsInitialized )
    CFlat::Abandonment::Fail((const char16_t *)this, retaddr);
  v8 = *(struct Cn::Context **)(v7 + 16);
  if ( v8 && *((_BYTE *)v8 + 79) && TlsGetValue(Cn::Context::s_tlsStorage) == v8 )
  {
LABEL_18:
    v14 = 0;
    goto LABEL_19;
  }
  Value = v8;
  v10 = 0;
  while ( !Value )
  {
LABEL_44:
    if ( !v8 )
    {
      Value = (struct Cn::Context *)TlsGetValue(Cn::Context::s_tlsStorage);
      if ( !Value )
      {
        Value = Cn::Context::NoContext_GetThreadContextOrNullAndLock();
        if ( !Value )
        {
          v14 = -2018443007;
          v27 = -2018443007;
          if ( !Cn::Process::Host )
            goto LABEL_19;
          (*(void (__fastcall **)(struct Cn::ICnHost *, int *, void *))(*(_QWORD *)Cn::Process::Host + 48LL))(
            Cn::Process::Host,
            &v27,
            retaddr);
          v14 = v27;
          if ( v27 < 0 )
            goto LABEL_19;
        }
      }
    }
  }
  v11 = *((_QWORD *)Value + 11);
  if ( v11 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 16));
    v12 = *(_DWORD *)(v11 + 60);
    *(_DWORD *)(v11 + 60) = v12 + 1;
    if ( !v12 )
    {
      *(_QWORD *)(v11 + 64) = TlsGetValue(Cn::Context::s_tlsStorage);
      *(_DWORD *)(v11 + 72) = GetCurrentThreadId();
    }
    v10 = 1;
  }
  v13 = *((_DWORD *)Value + 18);
  if ( !v13 )
  {
    if ( v8 && Value != v8 )
      CFlat::Abandonment::FailWithHR(-2018443006, retaddr, -2018443006);
    if ( v11 )
    {
      if ( TlsGetValue(Cn::Context::s_tlsStorage)
        || TlsGetValue(Cn::Context::s_tlsStorage) != Value && !TlsSetValue(Cn::Context::s_tlsStorage, Value) )
      {
        CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode();
      }
      _InterlockedIncrement((volatile signed __int32 *)Value + 2);
    }
    goto LABEL_18;
  }
  if ( v13 != 2 )
  {
    if ( v10 )
    {
      Cn::Engine::Lock::Leave((Cn::Engine::Lock *)v11);
      v10 = 0;
    }
    goto LABEL_44;
  }
  v23 = *((_QWORD *)Value + 12);
  if ( v23 )
    v24 = *(_DWORD *)(v23 + 152);
  else
    v24 = 0;
  if ( v24 != GetCurrentThreadId() )
  {
    CurrentThread = GetCurrentThread();
    WaitForSingleObjectEx(CurrentThread, 0x7530u, 0);
  }
  if ( Cn::Process::Host )
    (*(void (__fastcall **)(struct Cn::ICnHost *, void *))(*(_QWORD *)Cn::Process::Host + 56LL))(
      Cn::Process::Host,
      retaddr);
  CFlat::EntryExit::OnEndCallToCFlat(Value);
  v14 = -2018443005;
LABEL_19:
  v15 = 0;
  if ( v14 >= 0 )
  {
    if ( !v8 )
      v8 = (struct Cn::Context *)TlsGetValue(Cn::Context::s_tlsStorage);
    v16 = *(_QWORD *)(*((_QWORD *)this + 2) + 24LL);
    if ( v16 )
    {
      v17 = *(_DWORD *)(v16 + 16);
      if ( v17 > 0 )
        *(_DWORD *)(v16 + 16) = v17 + 1;
    }
    v18 = *(__int64 **)(v16 + 8);
    for ( i = 0; ; ++i )
    {
      if ( i >= *(unsigned __int16 *)v18 )
      {
        ComInterface = 0;
        goto LABEL_39;
      }
      v20 = *(unsigned __int16 *)v18;
      if ( &Microsoft::CoreUI::IExportMessageConversation::TypeId$ == (__int64 *)v18[2 * (i - v20)] )
        break;
    }
    ComInterface = (const void *)v18[2 * (i - v20) + 1];
    if ( ComInterface )
      goto LABEL_29;
LABEL_39:
    if ( v16 && v18 == &CFlat::ComImportAdapter::TypeId$ )
      ComInterface = CFlat::ComImportAdapter::GetComInterfaceDispatcher$(
                       (CFlat::ComImportAdapter *)v16,
                       (const struct CFlat::ComInterfaceTypeId *)&Microsoft::CoreUI::IExportMessageConversation::TypeId$);
LABEL_29:
    v15 = (*(__int64 (__fastcall **)(const void *, __int64, _QWORD, _QWORD, void **))(*(_QWORD *)ComInterface + 32LL))(
            ComInterface,
            v16,
            v28,
            a3,
            a4);
    if ( v16 )
      System::Object::Release$((System::Object *)v16);
    CFlat::EntryExit::OnEndCallToCFlat(v8);
  }
  return v15;
}

```

## disassembly

```asm
0x180021200  mov     [rsp+arg_10], rbx
0x180021205  mov     [rsp+arg_8], edx
0x180021209  push    rbp
0x18002120a  push    rsi
0x18002120b  push    rdi
0x18002120c  push    r12
0x18002120e  push    r13
0x180021210  push    r14
0x180021212  push    r15
0x180021214  sub     rsp, 30h
0x180021218  mov     r12, r9
0x18002121b  mov     r13d, r8d
0x18002121e  mov     r15, rcx
0x180021221  mov     rbx, [rcx+10h]
0x180021225  cmp     qword ptr [rbx+18h], 0
0x18002122a  jz      loc_1800213B6
0x180021230  mov     r14, [rsp+68h]
0x180021235  cmp     cs:?s_fTypeIsInitialized@Context@Cn@@0_NA, 0; bool Cn::Context::s_fTypeIsInitialized
0x18002123c  jz      loc_180021490
0x180021242  mov     rbx, [rbx+10h]
0x180021246  test    rbx, rbx
0x180021249  jnz     loc_1800213BC
0x18002124f  mov     rdi, rbx
0x180021252  xor     esi, esi
0x180021254  xor     bpl, bpl
0x180021257  test    rdi, rdi
0x18002125a  jz      loc_180021420
0x180021260  test    bpl, bpl
0x180021263  jnz     short loc_1800212A1
0x180021265  mov     rsi, [rdi+58h]
0x180021269  test    rsi, rsi
0x18002126c  jz      short loc_1800212A1
0x18002126e  lea     rcx, [rsi+10h]; lpCriticalSection
0x180021272  call    cs:__imp_EnterCriticalSection
0x180021278  mov     ecx, [rsi+3Ch]
0x18002127b  lea     eax, [rcx+1]
0x18002127e  mov     [rsi+3Ch], eax
0x180021281  test    ecx, ecx
0x180021283  jnz     short loc_18002129E
0x180021285  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18002128b  call    cs:__imp_TlsGetValue
0x180021291  mov     [rsi+40h], rax
0x180021295  call    cs:__imp_GetCurrentThreadId
0x18002129b  mov     [rsi+48h], eax
0x18002129e  mov     bpl, 1
0x1800212a1  mov     eax, [rdi+48h]
0x1800212a4  test    eax, eax
0x1800212a6  jnz     loc_1800214B0
0x1800212ac  test    rbx, rbx
0x1800212af  jz      short loc_1800212BA
0x1800212b1  cmp     rdi, rbx
0x1800212b4  jnz     loc_180021499
0x1800212ba  test    rsi, rsi
0x1800212bd  jz      short loc_180021300
0x1800212bf  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800212c5  call    cs:__imp_TlsGetValue
0x1800212cb  test    rax, rax
0x1800212ce  jnz     loc_1800214AA
0x1800212d4  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800212da  call    cs:__imp_TlsGetValue
0x1800212e0  cmp     rax, rdi
0x1800212e3  jz      short loc_1800212FC
0x1800212e5  mov     rdx, rdi; lpTlsValue
0x1800212e8  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800212ee  call    cs:__imp_TlsSetValue
0x1800212f4  test    eax, eax
0x1800212f6  jz      loc_1800214AA
0x1800212fc  lock inc dword ptr [rdi+8]
0x180021300  xor     eax, eax
0x180021302  xor     esi, esi
0x180021304  test    eax, eax
0x180021306  js      loc_180021398
0x18002130c  test    rbx, rbx
0x18002130f  jz      loc_1800214CF
0x180021315  mov     rax, [r15+10h]
0x180021319  mov     rdi, [rax+18h]
0x18002131d  test    rdi, rdi
0x180021320  jz      short loc_18002132E
0x180021322  mov     eax, [rdi+10h]
0x180021325  test    eax, eax
0x180021327  jle     short loc_18002132E
0x180021329  inc     eax
0x18002132b  mov     [rdi+10h], eax
0x18002132e  mov     r8, [rdi+8]
0x180021332  xor     edx, edx
0x180021334  movzx   r9d, word ptr [r8]
0x180021338  lea     r10, ?TypeId$@IExportMessageConversation@CoreUI@Microsoft@@2U?$ComInterfaceTypeIdField@VIExportMessageConversation@CoreUI@Microsoft@@UIMessageConversation@@$0A@@CFlat@@B; CFlat::ComInterfaceTypeIdField<Microsoft::CoreUI::IExportMessageConversation,IMessageConversation,0> const Microsoft::CoreUI::IExportMessageConversation::TypeId$
0x18002133f  cmp     edx, r9d
0x180021342  jge     loc_1800213E0
0x180021348  movzx   eax, word ptr [r8]
0x18002134c  movsxd  rcx, edx
0x18002134f  sub     rcx, rax
0x180021352  add     rcx, rcx
0x180021355  cmp     r10, [r8+rcx*8]
0x180021359  jnz     short loc_1800213B2
0x18002135b  mov     rcx, [r8+rcx*8+8]
0x180021360  test    rcx, rcx
0x180021363  jz      short loc_1800213E2
0x180021365  mov     rdx, [rcx]
0x180021368  mov     rax, [rdx+20h]
0x18002136c  mov     [rsp+68h+var_48], r12
0x180021371  mov     r9d, r13d
0x180021374  mov     r8d, [rsp+68h+arg_8]
0x180021379  mov     rdx, rdi
0x18002137c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021381  mov     esi, eax
0x180021383  test    rdi, rdi
0x180021386  jz      short loc_180021390
0x180021388  mov     rcx, rdi; this
0x18002138b  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180021390  mov     rcx, rbx; void *
0x180021393  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x180021398  mov     eax, esi
0x18002139a  mov     rbx, [rsp+68h+arg_10]
0x1800213a2  add     rsp, 30h
0x1800213a6  pop     r15
0x1800213a8  pop     r14
0x1800213aa  pop     r13
0x1800213ac  pop     r12
0x1800213ae  pop     rdi
0x1800213af  pop     rsi
0x1800213b0  pop     rbp
0x1800213b1  retn
0x1800213b2  inc     edx
0x1800213b4  jmp     short loc_18002133F
0x1800213b6  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x1800213bc  cmp     byte ptr [rbx+4Fh], 0
0x1800213c0  jz      loc_18002124F
0x1800213c6  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800213cc  call    cs:__imp_TlsGetValue
0x1800213d2  cmp     rax, rbx
0x1800213d5  jnz     loc_18002124F
0x1800213db  jmp     loc_180021300
0x1800213e0  xor     ecx, ecx
0x1800213e2  test    rdi, rdi
0x1800213e5  jz      loc_180021365
0x1800213eb  lea     rax, ?TypeId$@ComImportAdapter@CFlat@@2U?$ObjectTypeIdField@VComImportAdapter@CFlat@@$0A@$0A@@2@B; CFlat::ObjectTypeIdField<CFlat::ComImportAdapter,0,0> const CFlat::ComImportAdapter::TypeId$
0x1800213f2  cmp     r8, rax
0x1800213f5  jnz     loc_180021365
0x1800213fb  mov     rdx, r10; struct CFlat::ComInterfaceTypeId *
0x1800213fe  mov     rcx, rdi; this
0x180021401  call    ?GetComInterfaceDispatcher$@ComImportAdapter@CFlat@@QEAAPEBXPEBUComInterfaceTypeId@2@@Z; CFlat::ComImportAdapter::GetComInterfaceDispatcher$(CFlat::ComInterfaceTypeId const *)
0x180021406  mov     rcx, rax
0x180021409  jmp     loc_180021365
0x18002140e  test    bpl, bpl
0x180021411  jz      short loc_180021420
0x180021413  mov     rcx, rsi; this
0x180021416  call    ?Leave@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Leave(void)
0x18002141b  xor     esi, esi
0x18002141d  xor     bpl, bpl
0x180021420  test    rbx, rbx
0x180021423  jnz     loc_180021257
0x180021429  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18002142f  call    cs:__imp_TlsGetValue
0x180021435  mov     rdi, rax
0x180021438  test    rax, rax
0x18002143b  jnz     loc_180021257
0x180021441  call    ?NoContext_GetThreadContextOrNullAndLock@Context@Cn@@SAPEAV12@XZ; Cn::Context::NoContext_GetThreadContextOrNullAndLock(void)
0x180021446  mov     rdi, rax
0x180021449  test    rax, rax
0x18002144c  jnz     loc_180021257
0x180021452  mov     eax, 87B10101h
0x180021457  mov     [rsp+68h+arg_0], eax
0x18002145b  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x180021462  test    rcx, rcx
0x180021465  jz      loc_180021302
0x18002146b  mov     rax, [rcx]
0x18002146e  mov     r8, r14
0x180021471  lea     rdx, [rsp+68h+arg_0]
0x180021476  mov     rax, [rax+30h]
0x18002147a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002147f  mov     eax, [rsp+68h+arg_0]
0x180021483  test    eax, eax
0x180021485  js      loc_180021302
0x18002148b  jmp     loc_180021257
0x180021490  mov     rdx, r14; void *
0x180021493  call    ?Fail@Abandonment@CFlat@@SAXPEB_SPEAX@Z; CFlat::Abandonment::Fail(char16_t const *,void *)
0x180021499  mov     ecx, 87B10102h; int
0x18002149e  mov     r8d, ecx; int
0x1800214a1  mov     rdx, r14; void *
0x1800214a4  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x1800214aa  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x1800214b0  sub     eax, 1
0x1800214b3  jz      loc_18002140E
0x1800214b9  cmp     eax, 1
0x1800214bc  jnz     loc_18002140E
0x1800214c2  mov     rax, [rdi+60h]
0x1800214c6  test    rax, rax
0x1800214c9  jnz     short loc_1800214E3
0x1800214cb  xor     esi, esi
0x1800214cd  jmp     short loc_1800214E9
0x1800214cf  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800214d5  call    cs:__imp_TlsGetValue
0x1800214db  mov     rbx, rax
0x1800214de  jmp     loc_180021315
0x1800214e3  mov     esi, [rax+98h]
0x1800214e9  call    cs:__imp_GetCurrentThreadId
0x1800214ef  cmp     esi, eax
0x1800214f1  jz      short loc_18002150A
0x1800214f3  call    cs:__imp_GetCurrentThread
0x1800214f9  mov     rcx, rax; hHandle
0x1800214fc  xor     r8d, r8d; bAlertable
0x1800214ff  mov     edx, 7530h; dwMilliseconds
0x180021504  call    cs:__imp_WaitForSingleObjectEx
0x18002150a  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x180021511  test    rcx, rcx
0x180021514  jz      short loc_180021525
0x180021516  mov     rax, [rcx]
0x180021519  mov     rdx, r14
0x18002151c  mov     rax, [rax+38h]
0x180021520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021525  mov     rcx, rdi; void *
0x180021528  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x18002152d  mov     eax, 87B10103h
0x180021532  jmp     loc_180021302
```
