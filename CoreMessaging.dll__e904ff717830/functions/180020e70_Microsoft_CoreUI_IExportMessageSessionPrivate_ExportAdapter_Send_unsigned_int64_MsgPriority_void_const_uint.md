# Microsoft::CoreUI::IExportMessageSessionPrivate::ExportAdapter$::Send(unsigned __int64,MsgPriority,void const *,uint)

- ea: `0x180020e70`
- end: `0x1800211f5`
- name: `?Send@ExportAdapter$@IExportMessageSessionPrivate@CoreUI@Microsoft@@UEAAJ_KW4MsgPriority@@PEBXI@Z`
- size: `901`
- prototype: ``
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
- `0x180020e70`
- `0x180024980`
- `0x18003950c`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020ee6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020ee6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800211b0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800211b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002119f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002119f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020f0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021195`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020f0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021195`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180020f65`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180020f65`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020f01`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020f3c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020f51`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021069`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800210cd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002117c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020f01`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020f3c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020f51`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021069`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800210cd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002117c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::CoreUI::IExportMessageSessionPrivate::ExportAdapter$::Send(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5)
{
  __int64 v6; // rbx
  struct Cn::Context *v7; // rbx
  struct Cn::Context *Value; // rdi
  char v9; // r15
  __int64 v10; // r14
  int v11; // ecx
  int v12; // eax
  int v13; // esi
  __int64 v14; // rdi
  int v15; // eax
  __int64 *v16; // r8
  int i; // edx
  __int64 v18; // rax
  const void *ComInterface; // rcx
  __int64 v21; // rax
  int v22; // esi
  HANDLE CurrentThread; // rax
  const System::Exception::Holder$ *v24; // [rsp+48h] [rbp-40h] BYREF
  void *retaddr; // [rsp+88h] [rbp+0h]
  __int64 v26; // [rsp+90h] [rbp+8h] BYREF
  __int64 v27; // [rsp+98h] [rbp+10h]
  unsigned int v28; // [rsp+A0h] [rbp+18h]
  __int64 v29; // [rsp+A8h] [rbp+20h]

  v29 = a4;
  v28 = a3;
  v27 = a2;
  v6 = *(_QWORD *)(a1 + 16);
  if ( !*(_QWORD *)(v6 + 24) )
    return 2276524545LL;
  if ( !Cn::Context::s_fTypeIsInitialized )
    CFlat::Abandonment::Fail((const char16_t *)a1, retaddr);
  v7 = *(struct Cn::Context **)(v6 + 16);
  if ( v7 && *((_BYTE *)v7 + 79) && TlsGetValue(Cn::Context::s_tlsStorage) == v7 )
  {
LABEL_18:
    v13 = 0;
    goto LABEL_19;
  }
  Value = v7;
  v9 = 0;
  while ( !Value )
  {
LABEL_45:
    if ( !v7 )
    {
      Value = (struct Cn::Context *)TlsGetValue(Cn::Context::s_tlsStorage);
      if ( !Value )
      {
        Value = Cn::Context::NoContext_GetThreadContextOrNullAndLock();
        if ( !Value )
        {
          v13 = -2018443007;
          LODWORD(v26) = -2018443007;
          if ( !Cn::Process::Host )
            goto LABEL_19;
          (*(void (__fastcall **)(struct Cn::ICnHost *, __int64 *, void *))(*(_QWORD *)Cn::Process::Host + 48LL))(
            Cn::Process::Host,
            &v26,
            retaddr);
          v13 = v26;
          if ( (int)v26 < 0 )
            goto LABEL_19;
        }
      }
    }
  }
  v10 = *((_QWORD *)Value + 11);
  if ( v10 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 16));
    v11 = *(_DWORD *)(v10 + 60);
    *(_DWORD *)(v10 + 60) = v11 + 1;
    if ( !v11 )
    {
      *(_QWORD *)(v10 + 64) = TlsGetValue(Cn::Context::s_tlsStorage);
      *(_DWORD *)(v10 + 72) = GetCurrentThreadId();
    }
    v9 = 1;
  }
  v12 = *((_DWORD *)Value + 18);
  if ( !v12 )
  {
    if ( v7 && Value != v7 )
      CFlat::Abandonment::FailWithHR(-2018443006, retaddr, -2018443006);
    if ( v10 )
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
  if ( v12 != 2 )
  {
    if ( v9 )
    {
      Cn::Engine::Lock::Leave((Cn::Engine::Lock *)v10);
      v9 = 0;
    }
    goto LABEL_45;
  }
  v21 = *((_QWORD *)Value + 12);
  if ( v21 )
    v22 = *(_DWORD *)(v21 + 152);
  else
    v22 = 0;
  if ( v22 != GetCurrentThreadId() )
  {
    CurrentThread = GetCurrentThread();
    WaitForSingleObjectEx(CurrentThread, 0x7530u, 0);
  }
  if ( Cn::Process::Host )
    (*(void (__fastcall **)(struct Cn::ICnHost *, void *))(*(_QWORD *)Cn::Process::Host + 56LL))(
      Cn::Process::Host,
      retaddr);
  CFlat::EntryExit::OnEndCallToCFlat(Value);
  v13 = -2018443005;
LABEL_19:
  if ( v13 >= 0 )
  {
    if ( !v7 )
      v7 = (struct Cn::Context *)TlsGetValue(Cn::Context::s_tlsStorage);
    v14 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
    v26 = v14;
    if ( v14 )
    {
      v15 = *(_DWORD *)(v14 + 16);
      if ( v15 > 0 )
        *(_DWORD *)(v14 + 16) = v15 + 1;
    }
    v16 = *(__int64 **)(v14 + 8);
    for ( i = 0; ; ++i )
    {
      if ( i >= *(unsigned __int16 *)v16 )
      {
        ComInterface = 0;
        goto LABEL_40;
      }
      v18 = *(unsigned __int16 *)v16;
      if ( &Microsoft::CoreUI::IExportMessageSessionPrivate::TypeId$ == (__int64 *)v16[2 * (i - v18)] )
        break;
    }
    ComInterface = (const void *)v16[2 * (i - v18) + 1];
    if ( ComInterface )
      goto LABEL_63;
LABEL_40:
    if ( v14 && v16 == &CFlat::ComImportAdapter::TypeId$ )
      ComInterface = CFlat::ComImportAdapter::GetComInterfaceDispatcher$(
                       (CFlat::ComImportAdapter *)v14,
                       (const struct CFlat::ComInterfaceTypeId *)&Microsoft::CoreUI::IExportMessageSessionPrivate::TypeId$);
LABEL_63:
    try
    {
      (*(void (__fastcall **)(const void *, __int64, __int64, _QWORD, __int64, int))(*(_QWORD *)ComInterface + 48LL))(
        ComInterface,
        v14,
        v27,
        v28,
        v29,
        a5);
      if ( v14 )
        System::Object::Release$((System::Object *)v14);
    }
    catch ( const System::Exception::Holder$ *v24 )
    {
      LODWORD(v26) = *(_DWORD *)(*(_QWORD *)v24 + 40LL);
      v13 = v26;
    }
    CFlat::EntryExit::OnEndCallToCFlat(v7);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180020e70  mov     [rsp+arg_18], r9
0x180020e75  mov     [rsp+arg_10], r8d
0x180020e7a  mov     [rsp+arg_8], rdx
0x180020e7f  push    rbx
0x180020e80  push    rsi
0x180020e81  push    rdi
0x180020e82  push    r12
0x180020e84  push    r13
0x180020e86  push    r14
0x180020e88  push    r15
0x180020e8a  sub     rsp, 50h
0x180020e8e  mov     r13, rcx
0x180020e91  mov     rbx, [rcx+10h]
0x180020e95  cmp     qword ptr [rbx+18h], 0
0x180020e9a  jz      loc_180021052
0x180020ea0  mov     r12, [rsp+88h]
0x180020ea8  cmp     cs:?s_fTypeIsInitialized@Context@Cn@@0_NA, 0; bool Cn::Context::s_fTypeIsInitialized
0x180020eaf  jz      loc_180021137
0x180020eb5  mov     rbx, [rbx+10h]
0x180020eb9  test    rbx, rbx
0x180020ebc  jnz     loc_180021059
0x180020ec2  mov     rdi, rbx
0x180020ec5  xor     r14d, r14d
0x180020ec8  xor     r15b, r15b
0x180020ecb  test    rdi, rdi
0x180020ece  jz      loc_1800210BE
0x180020ed4  test    r15b, r15b
0x180020ed7  jnz     short loc_180020F18
0x180020ed9  mov     r14, [rdi+58h]
0x180020edd  test    r14, r14
0x180020ee0  jz      short loc_180020F18
0x180020ee2  lea     rcx, [r14+10h]; lpCriticalSection
0x180020ee6  call    cs:__imp_EnterCriticalSection
0x180020eec  mov     ecx, [r14+3Ch]
0x180020ef0  lea     eax, [rcx+1]
0x180020ef3  mov     [r14+3Ch], eax
0x180020ef7  test    ecx, ecx
0x180020ef9  jnz     short loc_180020F15
0x180020efb  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180020f01  call    cs:__imp_TlsGetValue
0x180020f07  mov     [r14+40h], rax
0x180020f0b  call    cs:__imp_GetCurrentThreadId
0x180020f11  mov     [r14+48h], eax
0x180020f15  mov     r15b, 1
0x180020f18  mov     eax, [rdi+48h]
0x180020f1b  test    eax, eax
0x180020f1d  jnz     loc_180021157
0x180020f23  test    rbx, rbx
0x180020f26  jz      short loc_180020F31
0x180020f28  cmp     rdi, rbx
0x180020f2b  jnz     loc_180021140
0x180020f31  test    r14, r14
0x180020f34  jz      short loc_180020F77
0x180020f36  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180020f3c  call    cs:__imp_TlsGetValue
0x180020f42  test    rax, rax
0x180020f45  jnz     loc_180021151
0x180020f4b  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180020f51  call    cs:__imp_TlsGetValue
0x180020f57  cmp     rax, rdi
0x180020f5a  jz      short loc_180020F73
0x180020f5c  mov     rdx, rdi; lpTlsValue
0x180020f5f  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180020f65  call    cs:__imp_TlsSetValue
0x180020f6b  test    eax, eax
0x180020f6d  jz      loc_180021151
0x180020f73  lock inc dword ptr [rdi+8]
0x180020f77  xor     esi, esi
0x180020f79  test    esi, esi
0x180020f7b  js      loc_180021039
0x180020f81  test    rbx, rbx
0x180020f84  jz      loc_180021176
0x180020f8a  mov     [rsp+88h+var_48], rbx
0x180020f8f  mov     rax, [r13+10h]
0x180020f93  mov     rdi, [rax+18h]
0x180020f97  mov     [rsp+88h+arg_0], rdi
0x180020f9f  test    rdi, rdi
0x180020fa2  jz      short loc_180020FB0
0x180020fa4  mov     eax, [rdi+10h]
0x180020fa7  test    eax, eax
0x180020fa9  jle     short loc_180020FB0
0x180020fab  inc     eax
0x180020fad  mov     [rdi+10h], eax
0x180020fb0  mov     r8, [rdi+8]
0x180020fb4  xor     edx, edx
0x180020fb6  movzx   r9d, word ptr [r8]
0x180020fba  lea     r10, ?TypeId$@IExportMessageSessionPrivate@CoreUI@Microsoft@@2U?$ComInterfaceTypeIdField@VIExportMessageSessionPrivate@CoreUI@Microsoft@@UIMessageSessionPrivate@@$0A@@CFlat@@B; CFlat::ComInterfaceTypeIdField<Microsoft::CoreUI::IExportMessageSessionPrivate,IMessageSessionPrivate,0> const Microsoft::CoreUI::IExportMessageSessionPrivate::TypeId$
0x180020fc1  cmp     edx, r9d
0x180020fc4  jge     loc_18002107D
0x180020fca  movzx   eax, word ptr [r8]
0x180020fce  movsxd  rcx, edx
0x180020fd1  sub     rcx, rax
0x180020fd4  add     rcx, rcx
0x180020fd7  cmp     r10, [r8+rcx*8]
0x180020fdb  jnz     short loc_18002104B
0x180020fdd  mov     rcx, [r8+rcx*8+8]
0x180020fe2  test    rcx, rcx
0x180020fe5  jz      loc_18002107F
0x180020feb  mov     rax, [rcx]
0x180020fee  mov     edx, [rsp+88h+arg_20]
0x180020ff5  mov     [rsp+88h+var_60], edx
0x180020ff9  mov     rdx, [rsp+88h+arg_18]
0x180021001  mov     [rsp+88h+var_68], rdx
0x180021006  mov     r9d, [rsp+88h+arg_10]
0x18002100e  mov     r8, [rsp+88h+arg_8]
0x180021016  mov     rdx, rdi
0x180021019  mov     rax, [rax+30h]
0x18002101d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021022  nop
0x180021023  test    rdi, rdi
0x180021026  jz      short loc_180021031
0x180021028  mov     rcx, rdi; this
0x18002102b  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180021030  nop
0x180021031  mov     rcx, rbx; void *
0x180021034  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x180021039  mov     eax, esi
0x18002103b  add     rsp, 50h
0x18002103f  pop     r15
0x180021041  pop     r14
0x180021043  pop     r13
0x180021045  pop     r12
0x180021047  pop     rdi
0x180021048  pop     rsi
0x180021049  pop     rbx
0x18002104a  retn
0x18002104b  inc     edx
0x18002104d  jmp     loc_180020FC1
0x180021052  mov     eax, 87B10201h
0x180021057  jmp     short loc_18002103B
0x180021059  cmp     byte ptr [rbx+4Fh], 0
0x18002105d  jz      loc_180020EC2
0x180021063  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180021069  call    cs:__imp_TlsGetValue
0x18002106f  cmp     rax, rbx
0x180021072  jnz     loc_180020EC2
0x180021078  jmp     loc_180020F77
0x18002107d  xor     ecx, ecx
0x18002107f  test    rdi, rdi
0x180021082  jz      loc_180020FEB
0x180021088  lea     rax, ?TypeId$@ComImportAdapter@CFlat@@2U?$ObjectTypeIdField@VComImportAdapter@CFlat@@$0A@$0A@@2@B; CFlat::ObjectTypeIdField<CFlat::ComImportAdapter,0,0> const CFlat::ComImportAdapter::TypeId$
0x18002108f  cmp     r8, rax
0x180021092  jnz     loc_180020FEB
0x180021098  mov     rdx, r10; struct CFlat::ComInterfaceTypeId *
0x18002109b  mov     rcx, rdi; this
0x18002109e  call    ?GetComInterfaceDispatcher$@ComImportAdapter@CFlat@@QEAAPEBXPEBUComInterfaceTypeId@2@@Z; CFlat::ComImportAdapter::GetComInterfaceDispatcher$(CFlat::ComInterfaceTypeId const *)
0x1800210a3  mov     rcx, rax
0x1800210a6  jmp     loc_180020FEB
0x1800210ab  test    r15b, r15b
0x1800210ae  jz      short loc_1800210BE
0x1800210b0  mov     rcx, r14; this
0x1800210b3  call    ?Leave@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Leave(void)
0x1800210b8  xor     r14d, r14d
0x1800210bb  xor     r15b, r15b
0x1800210be  test    rbx, rbx
0x1800210c1  jnz     loc_180020ECB
0x1800210c7  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800210cd  call    cs:__imp_TlsGetValue
0x1800210d3  mov     rdi, rax
0x1800210d6  test    rax, rax
0x1800210d9  jnz     loc_180020ECB
0x1800210df  call    ?NoContext_GetThreadContextOrNullAndLock@Context@Cn@@SAPEAV12@XZ; Cn::Context::NoContext_GetThreadContextOrNullAndLock(void)
0x1800210e4  mov     rdi, rax
0x1800210e7  test    rax, rax
0x1800210ea  jnz     loc_180020ECB
0x1800210f0  mov     esi, 87B10101h
0x1800210f5  mov     dword ptr [rsp+88h+arg_0], esi
0x1800210fc  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x180021103  test    rcx, rcx
0x180021106  jz      loc_180020F79
0x18002110c  mov     rax, [rcx]
0x18002110f  mov     r8, r12
0x180021112  lea     rdx, [rsp+88h+arg_0]
0x18002111a  mov     rax, [rax+30h]
0x18002111e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021123  mov     esi, dword ptr [rsp+88h+arg_0]
0x18002112a  test    esi, esi
0x18002112c  js      loc_180020F79
0x180021132  jmp     loc_180020ECB
0x180021137  mov     rdx, r12; void *
0x18002113a  call    ?Fail@Abandonment@CFlat@@SAXPEB_SPEAX@Z; CFlat::Abandonment::Fail(char16_t const *,void *)
0x180021140  mov     ecx, 87B10102h; int
0x180021145  mov     r8d, ecx; int
0x180021148  mov     rdx, r12; void *
0x18002114b  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x180021151  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x180021157  sub     eax, 1
0x18002115a  jz      loc_1800210AB
0x180021160  cmp     eax, 1
0x180021163  jnz     loc_1800210AB
0x180021169  mov     rax, [rdi+60h]
0x18002116d  test    rax, rax
0x180021170  jnz     short loc_18002118F
0x180021172  xor     esi, esi
0x180021174  jmp     short loc_180021195
0x180021176  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18002117c  call    cs:__imp_TlsGetValue
0x180021182  mov     rbx, rax
0x180021185  mov     [rsp+88h+var_48], rax
0x18002118a  jmp     loc_180020F8F
0x18002118f  mov     esi, [rax+98h]
0x180021195  call    cs:__imp_GetCurrentThreadId
0x18002119b  cmp     esi, eax
0x18002119d  jz      short loc_1800211B6
0x18002119f  call    cs:__imp_GetCurrentThread
0x1800211a5  mov     rcx, rax; hHandle
0x1800211a8  xor     r8d, r8d; bAlertable
0x1800211ab  mov     edx, 7530h; dwMilliseconds
0x1800211b0  call    cs:__imp_WaitForSingleObjectEx
0x1800211b6  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x1800211bd  test    rcx, rcx
0x1800211c0  jz      short loc_1800211D1
0x1800211c2  mov     rax, [rcx]
0x1800211c5  mov     rdx, r12
0x1800211c8  mov     rax, [rax+38h]
0x1800211cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211d1  mov     rcx, rdi; void *
0x1800211d4  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x1800211d9  mov     esi, 87B10103h
0x1800211de  jmp     loc_180020F79
0x1800211e3  mov     esi, dword ptr [rsp+88h+arg_0]
0x1800211ea  mov     rbx, [rsp+88h+var_48]
0x1800211ef  jmp     loc_180021031
```
