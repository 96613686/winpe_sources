# Microsoft::CoreUI::IExportMessageTimer::ExportAdapter$::SetRelative(__int64,__int64)

- ea: `0x180021540`
- end: `0x1800218a3`
- name: `?SetRelative@ExportAdapter$@IExportMessageTimer@CoreUI@Microsoft@@UEAAJ_J0@Z`
- size: `867`
- prototype: `__int64 __fastcall(Microsoft::CoreUI::IExportMessageTimer::ExportAdapter$ *__hidden this, __int64, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007d80`
- `0x1800089c0`
- `0x180010ed0`
- `0x18001d848`
- `0x18001ffcc`
- `0x180020df8`
- `0x180021540`
- `0x180024980`
- `0x18003950c`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800215ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800215ae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002185b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002185b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002184a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002184a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800215d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021840`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800215d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021840`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002162d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002162d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800215c9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021604`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021619`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021715`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021775`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021824`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800215c9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021604`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021619`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021715`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021775`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021824`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::CoreUI::IExportMessageTimer::ExportAdapter$::SetRelative(
        Microsoft::CoreUI::IExportMessageTimer::ExportAdapter$ *this,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rbx
  struct Cn::Context *v5; // rbx
  struct Cn::Context *Value; // rdi
  char v7; // r15
  __int64 v8; // r14
  int v9; // ecx
  int v10; // eax
  int v11; // esi
  __int64 v12; // rdi
  int v13; // eax
  unsigned __int16 *v14; // r8
  int i; // edx
  __int64 v16; // rax
  const void *ComInterface; // rcx
  __int64 v19; // rax
  int v20; // esi
  HANDLE CurrentThread; // rax
  const System::Exception::Holder$ *v22; // [rsp+30h] [rbp-48h] BYREF
  void *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v24; // [rsp+80h] [rbp+8h] BYREF
  __int64 v25; // [rsp+88h] [rbp+10h]
  __int64 v26; // [rsp+90h] [rbp+18h]
  struct Cn::Context *v27; // [rsp+98h] [rbp+20h]

  v26 = a3;
  v25 = a2;
  v4 = *((_QWORD *)this + 2);
  if ( !*(_QWORD *)(v4 + 24) )
    return 2276524545LL;
  if ( !Cn::Context::s_fTypeIsInitialized )
    CFlat::Abandonment::Fail((const char16_t *)this, retaddr);
  v5 = *(struct Cn::Context **)(v4 + 16);
  if ( v5 && *((_BYTE *)v5 + 79) && TlsGetValue(Cn::Context::s_tlsStorage) == v5 )
  {
LABEL_18:
    v11 = 0;
    goto LABEL_19;
  }
  Value = v5;
  v7 = 0;
  while ( !Value )
  {
LABEL_45:
    if ( !v5 )
    {
      Value = (struct Cn::Context *)TlsGetValue(Cn::Context::s_tlsStorage);
      if ( !Value )
      {
        Value = Cn::Context::NoContext_GetThreadContextOrNullAndLock();
        if ( !Value )
        {
          v11 = -2018443007;
          LODWORD(v24) = -2018443007;
          if ( !Cn::Process::Host )
            goto LABEL_19;
          (*(void (__fastcall **)(struct Cn::ICnHost *, __int64 *, void *))(*(_QWORD *)Cn::Process::Host + 48LL))(
            Cn::Process::Host,
            &v24,
            retaddr);
          v11 = v24;
          if ( (int)v24 < 0 )
            goto LABEL_19;
        }
      }
    }
  }
  v8 = *((_QWORD *)Value + 11);
  if ( v8 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 16));
    v9 = *(_DWORD *)(v8 + 60);
    *(_DWORD *)(v8 + 60) = v9 + 1;
    if ( !v9 )
    {
      *(_QWORD *)(v8 + 64) = TlsGetValue(Cn::Context::s_tlsStorage);
      *(_DWORD *)(v8 + 72) = GetCurrentThreadId();
    }
    v7 = 1;
  }
  v10 = *((_DWORD *)Value + 18);
  if ( !v10 )
  {
    if ( v5 && Value != v5 )
      CFlat::Abandonment::FailWithHR(-2018443006, retaddr, -2018443006);
    if ( v8 )
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
  if ( v10 != 2 )
  {
    if ( v7 )
    {
      Cn::Engine::Lock::Leave((Cn::Engine::Lock *)v8);
      v7 = 0;
    }
    goto LABEL_45;
  }
  v19 = *((_QWORD *)Value + 12);
  if ( v19 )
    v20 = *(_DWORD *)(v19 + 152);
  else
    v20 = 0;
  if ( v20 != GetCurrentThreadId() )
  {
    CurrentThread = GetCurrentThread();
    WaitForSingleObjectEx(CurrentThread, 0x7530u, 0);
  }
  if ( Cn::Process::Host )
    (*(void (__fastcall **)(struct Cn::ICnHost *, void *))(*(_QWORD *)Cn::Process::Host + 56LL))(
      Cn::Process::Host,
      retaddr);
  CFlat::EntryExit::OnEndCallToCFlat(Value);
  v11 = -2018443005;
LABEL_19:
  if ( v11 >= 0 )
  {
    if ( !v5 )
      v5 = (struct Cn::Context *)TlsGetValue(Cn::Context::s_tlsStorage);
    v27 = v5;
    v12 = *(_QWORD *)(*((_QWORD *)this + 2) + 24LL);
    v24 = v12;
    if ( v12 )
    {
      v13 = *(_DWORD *)(v12 + 16);
      if ( v13 > 0 )
        *(_DWORD *)(v12 + 16) = v13 + 1;
    }
    v14 = *(unsigned __int16 **)(v12 + 8);
    for ( i = 0; ; ++i )
    {
      if ( i >= *v14 )
      {
        ComInterface = 0;
        goto LABEL_40;
      }
      v16 = *v14;
      if ( &Microsoft::CoreUI::IExportMessageTimer::TypeId$ == *(_UNKNOWN **)&v14[8 * (i - v16)] )
        break;
    }
    ComInterface = *(const void **)&v14[8 * (i - v16) + 4];
    if ( ComInterface )
      goto LABEL_63;
LABEL_40:
    if ( v12 && v14 == (unsigned __int16 *)&CFlat::ComImportAdapter::TypeId$ )
      ComInterface = CFlat::ComImportAdapter::GetComInterfaceDispatcher$(
                       (CFlat::ComImportAdapter *)v12,
                       (const struct CFlat::ComInterfaceTypeId *)&Microsoft::CoreUI::IExportMessageTimer::TypeId$);
LABEL_63:
    try
    {
      (*(void (__fastcall **)(const void *, __int64, __int64, __int64))(*(_QWORD *)ComInterface + 56LL))(
        ComInterface,
        v12,
        v25,
        v26);
      if ( v12 )
        System::Object::Release$((System::Object *)v12);
    }
    catch ( const System::Exception::Holder$ *v22 )
    {
      LODWORD(v24) = *(_DWORD *)(*(_QWORD *)v22 + 40LL);
      v11 = v24;
      v5 = v27;
    }
    CFlat::EntryExit::OnEndCallToCFlat(v5);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180021540  mov     [rsp+arg_10], r8
0x180021545  mov     [rsp+arg_8], rdx
0x18002154a  push    rbx
0x18002154b  push    rsi
0x18002154c  push    rdi
0x18002154d  push    r12
0x18002154f  push    r13
0x180021551  push    r14
0x180021553  push    r15
0x180021555  sub     rsp, 40h
0x180021559  mov     r13, rcx
0x18002155c  mov     rbx, [rcx+10h]
0x180021560  cmp     qword ptr [rbx+18h], 0
0x180021565  jz      loc_1800216FE
0x18002156b  mov     r12, [rsp+78h]
0x180021570  cmp     cs:?s_fTypeIsInitialized@Context@Cn@@0_NA, 0; bool Cn::Context::s_fTypeIsInitialized
0x180021577  jz      loc_1800217DF
0x18002157d  mov     rbx, [rbx+10h]
0x180021581  test    rbx, rbx
0x180021584  jnz     loc_180021705
0x18002158a  mov     rdi, rbx
0x18002158d  xor     r14d, r14d
0x180021590  xor     r15b, r15b
0x180021593  test    rdi, rdi
0x180021596  jz      loc_180021766
0x18002159c  test    r15b, r15b
0x18002159f  jnz     short loc_1800215E0
0x1800215a1  mov     r14, [rdi+58h]
0x1800215a5  test    r14, r14
0x1800215a8  jz      short loc_1800215E0
0x1800215aa  lea     rcx, [r14+10h]; lpCriticalSection
0x1800215ae  call    cs:__imp_EnterCriticalSection
0x1800215b4  mov     ecx, [r14+3Ch]
0x1800215b8  lea     eax, [rcx+1]
0x1800215bb  mov     [r14+3Ch], eax
0x1800215bf  test    ecx, ecx
0x1800215c1  jnz     short loc_1800215DD
0x1800215c3  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800215c9  call    cs:__imp_TlsGetValue
0x1800215cf  mov     [r14+40h], rax
0x1800215d3  call    cs:__imp_GetCurrentThreadId
0x1800215d9  mov     [r14+48h], eax
0x1800215dd  mov     r15b, 1
0x1800215e0  mov     eax, [rdi+48h]
0x1800215e3  test    eax, eax
0x1800215e5  jnz     loc_1800217FF
0x1800215eb  test    rbx, rbx
0x1800215ee  jz      short loc_1800215F9
0x1800215f0  cmp     rdi, rbx
0x1800215f3  jnz     loc_1800217E8
0x1800215f9  test    r14, r14
0x1800215fc  jz      short loc_18002163F
0x1800215fe  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180021604  call    cs:__imp_TlsGetValue
0x18002160a  test    rax, rax
0x18002160d  jnz     loc_1800217F9
0x180021613  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180021619  call    cs:__imp_TlsGetValue
0x18002161f  cmp     rax, rdi
0x180021622  jz      short loc_18002163B
0x180021624  mov     rdx, rdi; lpTlsValue
0x180021627  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18002162d  call    cs:__imp_TlsSetValue
0x180021633  test    eax, eax
0x180021635  jz      loc_1800217F9
0x18002163b  lock inc dword ptr [rdi+8]
0x18002163f  xor     esi, esi
0x180021641  test    esi, esi
0x180021643  js      loc_1800216E8
0x180021649  test    rbx, rbx
0x18002164c  jz      loc_18002181E
0x180021652  mov     [rsp+78h+arg_18], rbx
0x18002165a  mov     rax, [r13+10h]
0x18002165e  mov     rdi, [rax+18h]
0x180021662  mov     [rsp+78h+arg_0], rdi
0x18002166a  test    rdi, rdi
0x18002166d  jz      short loc_18002167B
0x18002166f  mov     eax, [rdi+10h]
0x180021672  test    eax, eax
0x180021674  jle     short loc_18002167B
0x180021676  inc     eax
0x180021678  mov     [rdi+10h], eax
0x18002167b  mov     r8, [rdi+8]
0x18002167f  xor     edx, edx
0x180021681  movzx   r9d, word ptr [r8]
0x180021685  lea     r10, ?TypeId$@IExportMessageTimer@CoreUI@Microsoft@@2U?$ComInterfaceTypeIdField@VIExportMessageTimer@CoreUI@Microsoft@@UIMessageTimer@@$0A@@CFlat@@B; CFlat::ComInterfaceTypeIdField<Microsoft::CoreUI::IExportMessageTimer,IMessageTimer,0> const Microsoft::CoreUI::IExportMessageTimer::TypeId$
0x18002168c  cmp     edx, r9d
0x18002168f  jge     loc_180021729
0x180021695  movzx   eax, word ptr [r8]
0x180021699  movsxd  rcx, edx
0x18002169c  sub     rcx, rax
0x18002169f  add     rcx, rcx
0x1800216a2  cmp     r10, [r8+rcx*8]
0x1800216a6  jnz     short loc_1800216FA
0x1800216a8  mov     rcx, [r8+rcx*8+8]
0x1800216ad  test    rcx, rcx
0x1800216b0  jz      short loc_18002172B
0x1800216b2  mov     rax, [rcx]
0x1800216b5  mov     r9, [rsp+78h+arg_10]
0x1800216bd  mov     r8, [rsp+78h+arg_8]
0x1800216c5  mov     rdx, rdi
0x1800216c8  mov     rax, [rax+38h]
0x1800216cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216d1  nop
0x1800216d2  test    rdi, rdi
0x1800216d5  jz      short loc_1800216E0
0x1800216d7  mov     rcx, rdi; this
0x1800216da  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x1800216df  nop
0x1800216e0  mov     rcx, rbx; void *
0x1800216e3  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x1800216e8  mov     eax, esi
0x1800216ea  add     rsp, 40h
0x1800216ee  pop     r15
0x1800216f0  pop     r14
0x1800216f2  pop     r13
0x1800216f4  pop     r12
0x1800216f6  pop     rdi
0x1800216f7  pop     rsi
0x1800216f8  pop     rbx
0x1800216f9  retn
0x1800216fa  inc     edx
0x1800216fc  jmp     short loc_18002168C
0x1800216fe  mov     eax, 87B10201h
0x180021703  jmp     short loc_1800216EA
0x180021705  cmp     byte ptr [rbx+4Fh], 0
0x180021709  jz      loc_18002158A
0x18002170f  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180021715  call    cs:__imp_TlsGetValue
0x18002171b  cmp     rax, rbx
0x18002171e  jnz     loc_18002158A
0x180021724  jmp     loc_18002163F
0x180021729  xor     ecx, ecx
0x18002172b  test    rdi, rdi
0x18002172e  jz      short loc_1800216B2
0x180021730  lea     rax, ?TypeId$@ComImportAdapter@CFlat@@2U?$ObjectTypeIdField@VComImportAdapter@CFlat@@$0A@$0A@@2@B; CFlat::ObjectTypeIdField<CFlat::ComImportAdapter,0,0> const CFlat::ComImportAdapter::TypeId$
0x180021737  cmp     r8, rax
0x18002173a  jnz     loc_1800216B2
0x180021740  mov     rdx, r10; struct CFlat::ComInterfaceTypeId *
0x180021743  mov     rcx, rdi; this
0x180021746  call    ?GetComInterfaceDispatcher$@ComImportAdapter@CFlat@@QEAAPEBXPEBUComInterfaceTypeId@2@@Z; CFlat::ComImportAdapter::GetComInterfaceDispatcher$(CFlat::ComInterfaceTypeId const *)
0x18002174b  mov     rcx, rax
0x18002174e  jmp     loc_1800216B2
0x180021753  test    r15b, r15b
0x180021756  jz      short loc_180021766
0x180021758  mov     rcx, r14; this
0x18002175b  call    ?Leave@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Leave(void)
0x180021760  xor     r14d, r14d
0x180021763  xor     r15b, r15b
0x180021766  test    rbx, rbx
0x180021769  jnz     loc_180021593
0x18002176f  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180021775  call    cs:__imp_TlsGetValue
0x18002177b  mov     rdi, rax
0x18002177e  test    rax, rax
0x180021781  jnz     loc_180021593
0x180021787  call    ?NoContext_GetThreadContextOrNullAndLock@Context@Cn@@SAPEAV12@XZ; Cn::Context::NoContext_GetThreadContextOrNullAndLock(void)
0x18002178c  mov     rdi, rax
0x18002178f  test    rax, rax
0x180021792  jnz     loc_180021593
0x180021798  mov     esi, 87B10101h
0x18002179d  mov     dword ptr [rsp+78h+arg_0], esi
0x1800217a4  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x1800217ab  test    rcx, rcx
0x1800217ae  jz      loc_180021641
0x1800217b4  mov     rax, [rcx]
0x1800217b7  mov     r8, r12
0x1800217ba  lea     rdx, [rsp+78h+arg_0]
0x1800217c2  mov     rax, [rax+30h]
0x1800217c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217cb  mov     esi, dword ptr [rsp+78h+arg_0]
0x1800217d2  test    esi, esi
0x1800217d4  js      loc_180021641
0x1800217da  jmp     loc_180021593
0x1800217df  mov     rdx, r12; void *
0x1800217e2  call    ?Fail@Abandonment@CFlat@@SAXPEB_SPEAX@Z; CFlat::Abandonment::Fail(char16_t const *,void *)
0x1800217e8  mov     ecx, 87B10102h; int
0x1800217ed  mov     r8d, ecx; int
0x1800217f0  mov     rdx, r12; void *
0x1800217f3  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x1800217f9  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x1800217ff  sub     eax, 1
0x180021802  jz      loc_180021753
0x180021808  cmp     eax, 1
0x18002180b  jnz     loc_180021753
0x180021811  mov     rax, [rdi+60h]
0x180021815  test    rax, rax
0x180021818  jnz     short loc_18002183A
0x18002181a  xor     esi, esi
0x18002181c  jmp     short loc_180021840
0x18002181e  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180021824  call    cs:__imp_TlsGetValue
0x18002182a  mov     rbx, rax
0x18002182d  mov     [rsp+78h+arg_18], rax
0x180021835  jmp     loc_18002165A
0x18002183a  mov     esi, [rax+98h]
0x180021840  call    cs:__imp_GetCurrentThreadId
0x180021846  cmp     esi, eax
0x180021848  jz      short loc_180021861
0x18002184a  call    cs:__imp_GetCurrentThread
0x180021850  mov     rcx, rax; hHandle
0x180021853  xor     r8d, r8d; bAlertable
0x180021856  mov     edx, 7530h; dwMilliseconds
0x18002185b  call    cs:__imp_WaitForSingleObjectEx
0x180021861  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x180021868  test    rcx, rcx
0x18002186b  jz      short loc_18002187C
0x18002186d  mov     rax, [rcx]
0x180021870  mov     rdx, r12
0x180021873  mov     rax, [rax+38h]
0x180021877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002187c  mov     rcx, rdi; void *
0x18002187f  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x180021884  mov     esi, 87B10103h
0x180021889  jmp     loc_180021641
0x18002188e  mov     esi, dword ptr [rsp+78h+arg_0]
0x180021895  mov     rbx, [rsp+78h+arg_18]
0x18002189d  jmp     loc_1800216E0
```
