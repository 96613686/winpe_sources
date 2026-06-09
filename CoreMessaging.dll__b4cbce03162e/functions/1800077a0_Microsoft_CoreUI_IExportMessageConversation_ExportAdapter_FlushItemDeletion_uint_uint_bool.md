# Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$::FlushItemDeletion(uint,uint,bool)

- ea: `0x1800077a0`
- end: `0x180007b14`
- name: `?FlushItemDeletion@ExportAdapter$@IExportMessageConversation@CoreUI@Microsoft@@UEAAJII_N@Z`
- size: `884`
- prototype: `__int64 __fastcall(Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$ *__hidden this, unsigned int, unsigned int, bool)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180007d80`
- `0x1800089c0`
- `0x180010ed0`
- `0x18001d848`
- `0x18001ffcc`
- `0x180020df8`
- `0x180024980`
- `0x18003950c`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007812`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007812`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007acf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007acf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007abe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007abe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007837`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ab4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007837`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ab4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007891`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180007891`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000782d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007868`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000787d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007988`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800079ec`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007a9b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000782d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007868`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000787d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007988`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800079ec`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007a9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$::FlushItemDeletion(
        Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$ *this,
        unsigned int a2,
        unsigned int a3,
        char a4)
{
  __int64 v5; // rbx
  struct Cn::Context *v6; // rbx
  struct Cn::Context *Value; // rdi
  char v8; // r15
  __int64 v9; // r14
  int v10; // ecx
  int v11; // eax
  int v12; // esi
  __int64 v13; // rdi
  int v14; // eax
  unsigned __int16 *v15; // r8
  int i; // edx
  __int64 v17; // rax
  const void *ComInterface; // rcx
  __int64 v20; // rax
  int v21; // esi
  HANDLE CurrentThread; // rax
  const System::Exception::Holder$ *v23; // [rsp+38h] [rbp-40h] BYREF
  void *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v25; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v26; // [rsp+88h] [rbp+10h]
  unsigned int v27; // [rsp+90h] [rbp+18h]
  char v28; // [rsp+98h] [rbp+20h]

  v28 = a4;
  v27 = a3;
  v26 = a2;
  v5 = *((_QWORD *)this + 2);
  if ( !*(_QWORD *)(v5 + 24) )
    return 2276524545LL;
  if ( !Cn::Context::s_fTypeIsInitialized )
    CFlat::Abandonment::Fail((const char16_t *)this, retaddr);
  v6 = *(struct Cn::Context **)(v5 + 16);
  if ( v6 && *((_BYTE *)v6 + 79) && TlsGetValue(Cn::Context::s_tlsStorage) == v6 )
  {
LABEL_18:
    v12 = 0;
    goto LABEL_19;
  }
  Value = v6;
  v8 = 0;
  while ( !Value )
  {
LABEL_45:
    if ( !v6 )
    {
      Value = (struct Cn::Context *)TlsGetValue(Cn::Context::s_tlsStorage);
      if ( !Value )
      {
        Value = Cn::Context::NoContext_GetThreadContextOrNullAndLock();
        if ( !Value )
        {
          v12 = -2018443007;
          LODWORD(v25) = -2018443007;
          if ( !Cn::Process::Host )
            goto LABEL_19;
          (*(void (__fastcall **)(struct Cn::ICnHost *, __int64 *, void *))(*(_QWORD *)Cn::Process::Host + 48LL))(
            Cn::Process::Host,
            &v25,
            retaddr);
          v12 = v25;
          if ( (int)v25 < 0 )
            goto LABEL_19;
        }
      }
    }
  }
  v9 = *((_QWORD *)Value + 11);
  if ( v9 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
    v10 = *(_DWORD *)(v9 + 60);
    *(_DWORD *)(v9 + 60) = v10 + 1;
    if ( !v10 )
    {
      *(_QWORD *)(v9 + 64) = TlsGetValue(Cn::Context::s_tlsStorage);
      *(_DWORD *)(v9 + 72) = GetCurrentThreadId();
    }
    v8 = 1;
  }
  v11 = *((_DWORD *)Value + 18);
  if ( !v11 )
  {
    if ( v6 && Value != v6 )
      CFlat::Abandonment::FailWithHR(-2018443006, retaddr, -2018443006);
    if ( v9 )
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
  if ( v11 != 2 )
  {
    if ( v8 )
    {
      Cn::Engine::Lock::Leave((Cn::Engine::Lock *)v9);
      v8 = 0;
    }
    goto LABEL_45;
  }
  v20 = *((_QWORD *)Value + 12);
  if ( v20 )
    v21 = *(_DWORD *)(v20 + 152);
  else
    v21 = 0;
  if ( v21 != GetCurrentThreadId() )
  {
    CurrentThread = GetCurrentThread();
    WaitForSingleObjectEx(CurrentThread, 0x7530u, 0);
  }
  if ( Cn::Process::Host )
    (*(void (__fastcall **)(struct Cn::ICnHost *, void *))(*(_QWORD *)Cn::Process::Host + 56LL))(
      Cn::Process::Host,
      retaddr);
  CFlat::EntryExit::OnEndCallToCFlat(Value);
  v12 = -2018443005;
LABEL_19:
  if ( v12 >= 0 )
  {
    if ( !v6 )
      v6 = (struct Cn::Context *)TlsGetValue(Cn::Context::s_tlsStorage);
    v13 = *(_QWORD *)(*((_QWORD *)this + 2) + 24LL);
    v25 = v13;
    if ( v13 )
    {
      v14 = *(_DWORD *)(v13 + 16);
      if ( v14 > 0 )
        *(_DWORD *)(v13 + 16) = v14 + 1;
    }
    v15 = *(unsigned __int16 **)(v13 + 8);
    for ( i = 0; ; ++i )
    {
      if ( i >= *v15 )
      {
        ComInterface = 0;
        goto LABEL_40;
      }
      v17 = *v15;
      if ( &Microsoft::CoreUI::IExportMessageConversation::TypeId$ == *(_UNKNOWN **)&v15[8 * (i - v17)] )
        break;
    }
    ComInterface = *(const void **)&v15[8 * (i - v17) + 4];
    if ( ComInterface )
      goto LABEL_63;
LABEL_40:
    if ( v13 && v15 == (unsigned __int16 *)&CFlat::ComImportAdapter::TypeId$ )
      ComInterface = CFlat::ComImportAdapter::GetComInterfaceDispatcher$(
                       (CFlat::ComImportAdapter *)v13,
                       (const struct CFlat::ComInterfaceTypeId *)&Microsoft::CoreUI::IExportMessageConversation::TypeId$);
LABEL_63:
    try
    {
      (*(void (__fastcall **)(const void *, __int64, _QWORD, _QWORD, char))(*(_QWORD *)ComInterface + 56LL))(
        ComInterface,
        v13,
        v26,
        v27,
        v28);
      if ( v13 )
        System::Object::Release$((System::Object *)v13);
    }
    catch ( const System::Exception::Holder$ *v23 )
    {
      LODWORD(v25) = *(_DWORD *)(*(_QWORD *)v23 + 40LL);
      v12 = v25;
    }
    CFlat::EntryExit::OnEndCallToCFlat(v6);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800077a0  mov     [rsp+arg_18], r9b
0x1800077a5  mov     [rsp+arg_10], r8d
0x1800077aa  mov     [rsp+arg_8], edx
0x1800077ae  push    rbx
0x1800077af  push    rsi
0x1800077b0  push    rdi
0x1800077b1  push    r12
0x1800077b3  push    r13
0x1800077b5  push    r14
0x1800077b7  push    r15
0x1800077b9  sub     rsp, 40h
0x1800077bd  mov     r13, rcx
0x1800077c0  mov     rbx, [rcx+10h]
0x1800077c4  cmp     qword ptr [rbx+18h], 0
0x1800077c9  jz      loc_180007971
0x1800077cf  mov     r12, [rsp+78h]
0x1800077d4  cmp     cs:?s_fTypeIsInitialized@Context@Cn@@0_NA, 0; bool Cn::Context::s_fTypeIsInitialized
0x1800077db  jz      loc_180007A56
0x1800077e1  mov     rbx, [rbx+10h]
0x1800077e5  test    rbx, rbx
0x1800077e8  jnz     loc_180007978
0x1800077ee  mov     rdi, rbx
0x1800077f1  xor     r14d, r14d
0x1800077f4  xor     r15b, r15b
0x1800077f7  test    rdi, rdi
0x1800077fa  jz      loc_1800079DD
0x180007800  test    r15b, r15b
0x180007803  jnz     short loc_180007844
0x180007805  mov     r14, [rdi+58h]
0x180007809  test    r14, r14
0x18000780c  jz      short loc_180007844
0x18000780e  lea     rcx, [r14+10h]; lpCriticalSection
0x180007812  call    cs:__imp_EnterCriticalSection
0x180007818  mov     ecx, [r14+3Ch]
0x18000781c  lea     eax, [rcx+1]
0x18000781f  mov     [r14+3Ch], eax
0x180007823  test    ecx, ecx
0x180007825  jnz     short loc_180007841
0x180007827  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18000782d  call    cs:__imp_TlsGetValue
0x180007833  mov     [r14+40h], rax
0x180007837  call    cs:__imp_GetCurrentThreadId
0x18000783d  mov     [r14+48h], eax
0x180007841  mov     r15b, 1
0x180007844  mov     eax, [rdi+48h]
0x180007847  test    eax, eax
0x180007849  jnz     loc_180007A76
0x18000784f  test    rbx, rbx
0x180007852  jz      short loc_18000785D
0x180007854  cmp     rdi, rbx
0x180007857  jnz     loc_180007A5F
0x18000785d  test    r14, r14
0x180007860  jz      short loc_1800078A3
0x180007862  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180007868  call    cs:__imp_TlsGetValue
0x18000786e  test    rax, rax
0x180007871  jnz     loc_180007A70
0x180007877  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18000787d  call    cs:__imp_TlsGetValue
0x180007883  cmp     rax, rdi
0x180007886  jz      short loc_18000789F
0x180007888  mov     rdx, rdi; lpTlsValue
0x18000788b  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180007891  call    cs:__imp_TlsSetValue
0x180007897  test    eax, eax
0x180007899  jz      loc_180007A70
0x18000789f  lock inc dword ptr [rdi+8]
0x1800078a3  xor     esi, esi
0x1800078a5  test    esi, esi
0x1800078a7  js      loc_180007958
0x1800078ad  test    rbx, rbx
0x1800078b0  jz      loc_180007A95
0x1800078b6  mov     [rsp+78h+var_48], rbx
0x1800078bb  mov     rax, [r13+10h]
0x1800078bf  mov     rdi, [rax+18h]
0x1800078c3  mov     [rsp+78h+arg_0], rdi
0x1800078cb  test    rdi, rdi
0x1800078ce  jz      short loc_1800078DC
0x1800078d0  mov     eax, [rdi+10h]
0x1800078d3  test    eax, eax
0x1800078d5  jle     short loc_1800078DC
0x1800078d7  inc     eax
0x1800078d9  mov     [rdi+10h], eax
0x1800078dc  mov     r8, [rdi+8]
0x1800078e0  xor     edx, edx
0x1800078e2  movzx   r9d, word ptr [r8]
0x1800078e6  lea     r10, ?TypeId$@IExportMessageConversation@CoreUI@Microsoft@@2U?$ComInterfaceTypeIdField@VIExportMessageConversation@CoreUI@Microsoft@@UIMessageConversation@@$0A@@CFlat@@B; CFlat::ComInterfaceTypeIdField<Microsoft::CoreUI::IExportMessageConversation,IMessageConversation,0> const Microsoft::CoreUI::IExportMessageConversation::TypeId$
0x1800078ed  cmp     edx, r9d
0x1800078f0  jge     loc_18000799C
0x1800078f6  movzx   eax, word ptr [r8]
0x1800078fa  movsxd  rcx, edx
0x1800078fd  sub     rcx, rax
0x180007900  add     rcx, rcx
0x180007903  cmp     r10, [r8+rcx*8]
0x180007907  jnz     short loc_18000796A
0x180007909  mov     rcx, [r8+rcx*8+8]
0x18000790e  test    rcx, rcx
0x180007911  jz      loc_18000799E
0x180007917  mov     rax, [rcx]
0x18000791a  mov     dl, [rsp+78h+arg_18]
0x180007921  mov     [rsp+78h+var_58], dl
0x180007925  mov     r9d, [rsp+78h+arg_10]
0x18000792d  mov     r8d, [rsp+78h+arg_8]
0x180007935  mov     rdx, rdi
0x180007938  mov     rax, [rax+38h]
0x18000793c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007941  nop
0x180007942  test    rdi, rdi
0x180007945  jz      short loc_180007950
0x180007947  mov     rcx, rdi; this
0x18000794a  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18000794f  nop
0x180007950  mov     rcx, rbx; void *
0x180007953  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x180007958  mov     eax, esi
0x18000795a  add     rsp, 40h
0x18000795e  pop     r15
0x180007960  pop     r14
0x180007962  pop     r13
0x180007964  pop     r12
0x180007966  pop     rdi
0x180007967  pop     rsi
0x180007968  pop     rbx
0x180007969  retn
0x18000796a  inc     edx
0x18000796c  jmp     loc_1800078ED
0x180007971  mov     eax, 87B10201h
0x180007976  jmp     short loc_18000795A
0x180007978  cmp     byte ptr [rbx+4Fh], 0
0x18000797c  jz      loc_1800077EE
0x180007982  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180007988  call    cs:__imp_TlsGetValue
0x18000798e  cmp     rax, rbx
0x180007991  jnz     loc_1800077EE
0x180007997  jmp     loc_1800078A3
0x18000799c  xor     ecx, ecx
0x18000799e  test    rdi, rdi
0x1800079a1  jz      loc_180007917
0x1800079a7  lea     rax, ?TypeId$@ComImportAdapter@CFlat@@2U?$ObjectTypeIdField@VComImportAdapter@CFlat@@$0A@$0A@@2@B; CFlat::ObjectTypeIdField<CFlat::ComImportAdapter,0,0> const CFlat::ComImportAdapter::TypeId$
0x1800079ae  cmp     r8, rax
0x1800079b1  jnz     loc_180007917
0x1800079b7  mov     rdx, r10; struct CFlat::ComInterfaceTypeId *
0x1800079ba  mov     rcx, rdi; this
0x1800079bd  call    ?GetComInterfaceDispatcher$@ComImportAdapter@CFlat@@QEAAPEBXPEBUComInterfaceTypeId@2@@Z; CFlat::ComImportAdapter::GetComInterfaceDispatcher$(CFlat::ComInterfaceTypeId const *)
0x1800079c2  mov     rcx, rax
0x1800079c5  jmp     loc_180007917
0x1800079ca  test    r15b, r15b
0x1800079cd  jz      short loc_1800079DD
0x1800079cf  mov     rcx, r14; this
0x1800079d2  call    ?Leave@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Leave(void)
0x1800079d7  xor     r14d, r14d
0x1800079da  xor     r15b, r15b
0x1800079dd  test    rbx, rbx
0x1800079e0  jnz     loc_1800077F7
0x1800079e6  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800079ec  call    cs:__imp_TlsGetValue
0x1800079f2  mov     rdi, rax
0x1800079f5  test    rax, rax
0x1800079f8  jnz     loc_1800077F7
0x1800079fe  call    ?NoContext_GetThreadContextOrNullAndLock@Context@Cn@@SAPEAV12@XZ; Cn::Context::NoContext_GetThreadContextOrNullAndLock(void)
0x180007a03  mov     rdi, rax
0x180007a06  test    rax, rax
0x180007a09  jnz     loc_1800077F7
0x180007a0f  mov     esi, 87B10101h
0x180007a14  mov     dword ptr [rsp+78h+arg_0], esi
0x180007a1b  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x180007a22  test    rcx, rcx
0x180007a25  jz      loc_1800078A5
0x180007a2b  mov     rax, [rcx]
0x180007a2e  mov     r8, r12
0x180007a31  lea     rdx, [rsp+78h+arg_0]
0x180007a39  mov     rax, [rax+30h]
0x180007a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a42  mov     esi, dword ptr [rsp+78h+arg_0]
0x180007a49  test    esi, esi
0x180007a4b  js      loc_1800078A5
0x180007a51  jmp     loc_1800077F7
0x180007a56  mov     rdx, r12; void *
0x180007a59  call    ?Fail@Abandonment@CFlat@@SAXPEB_SPEAX@Z; CFlat::Abandonment::Fail(char16_t const *,void *)
0x180007a5f  mov     ecx, 87B10102h; int
0x180007a64  mov     r8d, ecx; int
0x180007a67  mov     rdx, r12; void *
0x180007a6a  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x180007a70  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x180007a76  sub     eax, 1
0x180007a79  jz      loc_1800079CA
0x180007a7f  cmp     eax, 1
0x180007a82  jnz     loc_1800079CA
0x180007a88  mov     rax, [rdi+60h]
0x180007a8c  test    rax, rax
0x180007a8f  jnz     short loc_180007AAE
0x180007a91  xor     esi, esi
0x180007a93  jmp     short loc_180007AB4
0x180007a95  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180007a9b  call    cs:__imp_TlsGetValue
0x180007aa1  mov     rbx, rax
0x180007aa4  mov     [rsp+78h+var_48], rax
0x180007aa9  jmp     loc_1800078BB
0x180007aae  mov     esi, [rax+98h]
0x180007ab4  call    cs:__imp_GetCurrentThreadId
0x180007aba  cmp     esi, eax
0x180007abc  jz      short loc_180007AD5
0x180007abe  call    cs:__imp_GetCurrentThread
0x180007ac4  mov     rcx, rax; hHandle
0x180007ac7  xor     r8d, r8d; bAlertable
0x180007aca  mov     edx, 7530h; dwMilliseconds
0x180007acf  call    cs:__imp_WaitForSingleObjectEx
0x180007ad5  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x180007adc  test    rcx, rcx
0x180007adf  jz      short loc_180007AF0
0x180007ae1  mov     rax, [rcx]
0x180007ae4  mov     rdx, r12
0x180007ae7  mov     rax, [rax+38h]
0x180007aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007af0  mov     rcx, rdi; void *
0x180007af3  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x180007af8  mov     esi, 87B10103h
0x180007afd  jmp     loc_1800078A5
0x180007b02  mov     esi, dword ptr [rsp+78h+arg_0]
0x180007b09  mov     rbx, [rsp+78h+var_48]
0x180007b0e  jmp     loc_180007950
```
