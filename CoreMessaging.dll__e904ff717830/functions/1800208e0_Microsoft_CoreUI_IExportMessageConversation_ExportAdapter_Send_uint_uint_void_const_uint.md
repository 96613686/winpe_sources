# Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$::Send(uint,uint,void const *,uint)

- ea: `0x1800208e0`
- end: `0x180020d9f`
- name: `?Send@ExportAdapter$@IExportMessageConversation@CoreUI@Microsoft@@UEAAJIIPEBXI@Z`
- size: `1215`
- prototype: `__int64 __fastcall(Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$ *__hidden this, unsigned int, unsigned int, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007d80`
- `0x1800089c0`
- `0x180010ed0`
- `0x18001d848`
- `0x18001ffcc`
- `0x1800208e0`
- `0x180020df8`
- `0x180024980`
- `0x18003950c`
- `0x1800c7f4c`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020b5a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020b5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020955`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020955`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180020d31`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180020d31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020b13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020b13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020d93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020d93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020d20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020d20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002097a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020d15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002097a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020d15`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800209d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180020adc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800209d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180020adc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020970`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800209ab`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800209c0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020ac9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020baf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020c13`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020cfb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020970`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800209ab`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800209c0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020ac9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020baf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020c13`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020cfb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$::Send(
        Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$ *this,
        unsigned int a2,
        unsigned int a3,
        const void *a4,
        unsigned int a5)
{
  __int64 v5; // rbx
  LPVOID v6; // rbx
  struct Cn::Context *Value; // rsi
  char v8; // r12
  __int64 v9; // r14
  int v10; // ecx
  int v11; // eax
  int v12; // r15d
  __int64 v13; // rsi
  int v14; // eax
  __int64 *v15; // r8
  int i; // edx
  __int64 v17; // rax
  const void *ComInterface; // rcx
  int v19; // r14d
  _QWORD *v20; // rsi
  __int64 v21; // rcx
  _QWORD *v23; // rbx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v27; // rcx
  void (__fastcall *v28)(__int64, __int64, __int64); // rax
  __int64 v29; // rax
  int v30; // r14d
  HANDLE CurrentThread; // rax
  DWORD v32; // eax
  LPVOID v33[9]; // [rsp+40h] [rbp-48h] BYREF
  void *retaddr; // [rsp+88h] [rbp+0h]

  v5 = *((_QWORD *)this + 2);
  if ( !*(_QWORD *)(v5 + 24) )
    return 2276524545LL;
  if ( !Cn::Context::s_fTypeIsInitialized )
    CFlat::Abandonment::Fail((const char16_t *)this, retaddr);
  v6 = *(LPVOID *)(v5 + 16);
  if ( !v6 || !*((_BYTE *)v6 + 79) || TlsGetValue(Cn::Context::s_tlsStorage) != v6 )
  {
    Value = (struct Cn::Context *)v6;
    v8 = 0;
    while ( 1 )
    {
      if ( Value )
      {
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
          break;
        }
        if ( v11 == 2 )
        {
          v29 = *((_QWORD *)Value + 12);
          if ( v29 )
            v30 = *(_DWORD *)(v29 + 152);
          else
            v30 = 0;
          if ( v30 != GetCurrentThreadId() )
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
          goto LABEL_19;
        }
        if ( v8 )
        {
          Cn::Engine::Lock::Leave((Cn::Engine::Lock *)v9);
          v8 = 0;
        }
      }
      if ( !v6 )
      {
        Value = (struct Cn::Context *)TlsGetValue(Cn::Context::s_tlsStorage);
        if ( !Value )
        {
          Value = Cn::Context::NoContext_GetThreadContextOrNullAndLock();
          if ( !Value )
          {
            v12 = -2018443007;
            LODWORD(v33[0]) = -2018443007;
            if ( !Cn::Process::Host )
              goto LABEL_19;
            (*(void (__fastcall **)(struct Cn::ICnHost *, LPVOID *, void *))(*(_QWORD *)Cn::Process::Host + 48LL))(
              Cn::Process::Host,
              v33,
              retaddr);
            v12 = (int)v33[0];
            if ( SLODWORD(v33[0]) < 0 )
              goto LABEL_19;
          }
        }
      }
    }
  }
  v12 = 0;
LABEL_19:
  if ( v12 >= 0 )
  {
    if ( !v6 )
      v6 = TlsGetValue(Cn::Context::s_tlsStorage);
    v33[0] = v6;
    v13 = *(_QWORD *)(*((_QWORD *)this + 2) + 24LL);
    if ( v13 )
    {
      v14 = *(_DWORD *)(v13 + 16);
      if ( v14 > 0 )
        *(_DWORD *)(v13 + 16) = v14 + 1;
    }
    v15 = *(__int64 **)(v13 + 8);
    for ( i = 0; ; ++i )
    {
      if ( i >= *(unsigned __int16 *)v15 )
      {
        ComInterface = 0;
        goto LABEL_54;
      }
      v17 = *(unsigned __int16 *)v15;
      if ( &Microsoft::CoreUI::IExportMessageConversation::TypeId$ == (__int64 *)v15[2 * (i - v17)] )
        break;
    }
    ComInterface = (const void *)v15[2 * (i - v17) + 1];
    if ( ComInterface )
      goto LABEL_29;
LABEL_54:
    if ( v13 && v15 == &CFlat::ComImportAdapter::TypeId$ )
      ComInterface = CFlat::ComImportAdapter::GetComInterfaceDispatcher$(
                       (CFlat::ComImportAdapter *)v13,
                       (const struct CFlat::ComInterfaceTypeId *)&Microsoft::CoreUI::IExportMessageConversation::TypeId$);
LABEL_29:
    (*(void (__fastcall **)(const void *, __int64, _QWORD, _QWORD, const void *, unsigned int))(*(_QWORD *)ComInterface
                                                                                              + 40LL))(
      ComInterface,
      v13,
      a2,
      a3,
      a4,
      a5);
    if ( v13 )
      System::Object::Release$((System::Object *)v13);
    v19 = *((_DWORD *)v6 + 28);
    *((_DWORD *)v6 + 28) = 0;
    if ( !*((_BYTE *)v6 + 79) )
    {
      if ( TlsGetValue(Cn::Context::s_tlsStorage) && !TlsSetValue(Cn::Context::s_tlsStorage, 0) )
        CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode();
      v20 = (_QWORD *)*((_QWORD *)v6 + 10);
      *((_QWORD *)v6 + 10) = 0;
      v21 = *((_QWORD *)v6 + 11);
      if ( (*(_DWORD *)(v21 + 60))-- == 1 )
      {
        *(_QWORD *)(v21 + 64) = 0;
        *(_DWORD *)(v21 + 72) = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v21 + 16));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 2, 0xFFFFFFFF) == 1 )
      {
        *((_DWORD *)v6 + 2) = 1;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 8LL))(v6);
        (**(void (__fastcall ***)(LPVOID, __int64))v6)(v6, 1);
      }
      if ( v20 )
      {
        while ( 1 )
        {
          v23 = (_QWORD *)*v20;
          *v20 = 0;
          v24 = v20[3];
          v25 = *((unsigned __int8 *)v20 + 8);
          if ( !*((_BYTE *)v20 + 8) )
            break;
          v25 = (unsigned int)(v25 - 1);
          if ( !(_DWORD)v25 )
          {
            v28 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v24 + 16LL);
LABEL_66:
            v27 = v20[3];
            goto LABEL_47;
          }
          if ( (_DWORD)v25 == 1 )
          {
            v27 = v20[2];
            v28 = (void (__fastcall *)(__int64, __int64, __int64))v20[3];
LABEL_47:
            v28(v27, v25, v24);
          }
          free(v20);
          v20 = v23;
          if ( !v23 )
            goto LABEL_43;
        }
        v28 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v24 + 8LL);
        goto LABEL_66;
      }
LABEL_43:
      if ( v19 )
      {
        v32 = CFlat::Win32ErrorHandling::ConvertHRToWin32Error(v19);
        SetLastError(v32);
      }
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800208e0  mov     rax, rsp
0x1800208e3  mov     [rax+20h], r9
0x1800208e7  mov     [rax+18h], r8d
0x1800208eb  mov     [rax+10h], edx
0x1800208ee  mov     [rax+8], rcx
0x1800208f2  push    rbx
0x1800208f3  push    rsi
0x1800208f4  push    r12
0x1800208f6  push    r13
0x1800208f8  push    r14
0x1800208fa  push    r15
0x1800208fc  sub     rsp, 58h
0x180020900  mov     rbx, [rcx+10h]
0x180020904  cmp     qword ptr [rbx+18h], 0
0x180020909  jz      loc_180020B98
0x18002090f  mov     r13, [rsp+88h]
0x180020917  cmp     cs:?s_fTypeIsInitialized@Context@Cn@@0_NA, 0; bool Cn::Context::s_fTypeIsInitialized
0x18002091e  jz      loc_180020C87
0x180020924  mov     rbx, [rbx+10h]
0x180020928  test    rbx, rbx
0x18002092b  jnz     loc_180020B9F
0x180020931  mov     rsi, rbx
0x180020934  xor     r14d, r14d
0x180020937  xor     r12b, r12b
0x18002093a  test    rsi, rsi
0x18002093d  jz      loc_180020C04
0x180020943  test    r12b, r12b
0x180020946  jnz     short loc_180020987
0x180020948  mov     r14, [rsi+58h]
0x18002094c  test    r14, r14
0x18002094f  jz      short loc_180020987
0x180020951  lea     rcx, [r14+10h]; lpCriticalSection
0x180020955  call    cs:__imp_EnterCriticalSection
0x18002095b  mov     ecx, [r14+3Ch]
0x18002095f  lea     eax, [rcx+1]
0x180020962  mov     [r14+3Ch], eax
0x180020966  test    ecx, ecx
0x180020968  jnz     short loc_180020984
0x18002096a  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180020970  call    cs:__imp_TlsGetValue
0x180020976  mov     [r14+40h], rax
0x18002097a  call    cs:__imp_GetCurrentThreadId
0x180020980  mov     [r14+48h], eax
0x180020984  mov     r12b, 1
0x180020987  mov     eax, [rsi+48h]
0x18002098a  test    eax, eax
0x18002098c  jnz     loc_180020CD5
0x180020992  test    rbx, rbx
0x180020995  jz      short loc_1800209A0
0x180020997  cmp     rsi, rbx
0x18002099a  jnz     loc_180020CBE
0x1800209a0  test    r14, r14
0x1800209a3  jz      short loc_1800209E6
0x1800209a5  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800209ab  call    cs:__imp_TlsGetValue
0x1800209b1  test    rax, rax
0x1800209b4  jnz     loc_180020CCF
0x1800209ba  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800209c0  call    cs:__imp_TlsGetValue
0x1800209c6  cmp     rax, rsi
0x1800209c9  jz      short loc_1800209E2
0x1800209cb  mov     rdx, rsi; lpTlsValue
0x1800209ce  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800209d4  call    cs:__imp_TlsSetValue
0x1800209da  test    eax, eax
0x1800209dc  jz      loc_180020CCF
0x1800209e2  lock inc dword ptr [rsi+8]
0x1800209e6  xor     r15d, r15d
0x1800209e9  test    r15d, r15d
0x1800209ec  js      loc_180020B71
0x1800209f2  test    rbx, rbx
0x1800209f5  jz      loc_180020CF5
0x1800209fb  mov     [rsp+88h+var_48], rbx
0x180020a00  mov     rax, [rsp+88h+arg_0]
0x180020a08  mov     rax, [rax+10h]
0x180020a0c  mov     rsi, [rax+18h]
0x180020a10  mov     [rsp+88h+arg_0], rsi
0x180020a18  test    rsi, rsi
0x180020a1b  jz      short loc_180020A29
0x180020a1d  mov     eax, [rsi+10h]
0x180020a20  test    eax, eax
0x180020a22  jle     short loc_180020A29
0x180020a24  inc     eax
0x180020a26  mov     [rsi+10h], eax
0x180020a29  mov     r8, [rsi+8]
0x180020a2d  xor     edx, edx
0x180020a2f  movzx   r9d, word ptr [r8]
0x180020a33  lea     r10, ?TypeId$@IExportMessageConversation@CoreUI@Microsoft@@2U?$ComInterfaceTypeIdField@VIExportMessageConversation@CoreUI@Microsoft@@UIMessageConversation@@$0A@@CFlat@@B; CFlat::ComInterfaceTypeIdField<Microsoft::CoreUI::IExportMessageConversation,IMessageConversation,0> const Microsoft::CoreUI::IExportMessageConversation::TypeId$
0x180020a3a  cmp     edx, r9d
0x180020a3d  jge     loc_180020BC3
0x180020a43  movzx   eax, word ptr [r8]
0x180020a47  movsxd  rcx, edx
0x180020a4a  sub     rcx, rax
0x180020a4d  add     rcx, rcx
0x180020a50  cmp     r10, [r8+rcx*8]
0x180020a54  jnz     loc_180020B91
0x180020a5a  mov     rcx, [r8+rcx*8+8]
0x180020a5f  test    rcx, rcx
0x180020a62  jz      loc_180020BC5
0x180020a68  mov     rax, [rcx]
0x180020a6b  mov     edx, [rsp+88h+arg_20]
0x180020a72  mov     [rsp+88h+var_60], edx
0x180020a76  mov     rdx, [rsp+88h+arg_18]
0x180020a7e  mov     [rsp+88h+var_68], rdx
0x180020a83  mov     r9d, [rsp+88h+arg_10]
0x180020a8b  mov     r8d, [rsp+88h+arg_8]
0x180020a93  mov     rdx, rsi
0x180020a96  mov     rax, [rax+28h]
0x180020a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a9f  nop
0x180020aa0  test    rsi, rsi
0x180020aa3  jz      short loc_180020AAE
0x180020aa5  mov     rcx, rsi; this
0x180020aa8  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180020aad  nop
0x180020aae  mov     r14d, [rbx+70h]
0x180020ab2  mov     dword ptr [rbx+70h], 0
0x180020ab9  cmp     byte ptr [rbx+4Fh], 0
0x180020abd  jnz     loc_180020B71
0x180020ac3  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180020ac9  call    cs:__imp_TlsGetValue
0x180020acf  test    rax, rax
0x180020ad2  jz      short loc_180020AEA
0x180020ad4  xor     edx, edx; lpTlsValue
0x180020ad6  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180020adc  call    cs:__imp_TlsSetValue
0x180020ae2  test    eax, eax
0x180020ae4  jz      loc_180020D77
0x180020aea  mov     rsi, [rbx+50h]
0x180020aee  mov     qword ptr [rbx+50h], 0
0x180020af6  mov     rcx, [rbx+58h]
0x180020afa  add     dword ptr [rcx+3Ch], 0FFFFFFFFh
0x180020afe  jnz     short loc_180020B0F
0x180020b00  mov     qword ptr [rcx+40h], 0
0x180020b08  mov     dword ptr [rcx+48h], 0
0x180020b0f  add     rcx, 10h; lpCriticalSection
0x180020b13  call    cs:__imp_LeaveCriticalSection
0x180020b19  or      eax, 0FFFFFFFFh
0x180020b1c  lock xadd [rbx+8], eax
0x180020b21  cmp     eax, 1
0x180020b24  jz      loc_180020C90
0x180020b2a  test    rsi, rsi
0x180020b2d  jz      short loc_180020B68
0x180020b2f  mov     rbx, [rsi]
0x180020b32  mov     qword ptr [rsi], 0
0x180020b39  mov     r8, [rsi+18h]
0x180020b3d  movzx   edx, byte ptr [rsi+8]
0x180020b41  test    edx, edx
0x180020b43  jz      loc_180020D7D
0x180020b49  sub     edx, 1
0x180020b4c  jz      loc_180020C78
0x180020b52  cmp     edx, 1
0x180020b55  jz      short loc_180020B83
0x180020b57  mov     rcx, rsi; Block
0x180020b5a  call    cs:__imp_free
0x180020b60  mov     rsi, rbx
0x180020b63  test    rbx, rbx
0x180020b66  jnz     short loc_180020B2F
0x180020b68  test    r14d, r14d
0x180020b6b  jnz     loc_180020D89
0x180020b71  mov     eax, r15d
0x180020b74  add     rsp, 58h
0x180020b78  pop     r15
0x180020b7a  pop     r14
0x180020b7c  pop     r13
0x180020b7e  pop     r12
0x180020b80  pop     rsi
0x180020b81  pop     rbx
0x180020b82  retn
0x180020b83  mov     rcx, [rsi+10h]
0x180020b87  mov     rax, r8
0x180020b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b8f  jmp     short loc_180020B57
0x180020b91  inc     edx
0x180020b93  jmp     loc_180020A3A
0x180020b98  mov     eax, 87B10201h
0x180020b9d  jmp     short loc_180020B74
0x180020b9f  cmp     byte ptr [rbx+4Fh], 0
0x180020ba3  jz      loc_180020931
0x180020ba9  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180020baf  call    cs:__imp_TlsGetValue
0x180020bb5  cmp     rax, rbx
0x180020bb8  jnz     loc_180020931
0x180020bbe  jmp     loc_1800209E6
0x180020bc3  xor     ecx, ecx
0x180020bc5  test    rsi, rsi
0x180020bc8  jz      loc_180020A68
0x180020bce  lea     rax, ?TypeId$@ComImportAdapter@CFlat@@2U?$ObjectTypeIdField@VComImportAdapter@CFlat@@$0A@$0A@@2@B; CFlat::ObjectTypeIdField<CFlat::ComImportAdapter,0,0> const CFlat::ComImportAdapter::TypeId$
0x180020bd5  cmp     r8, rax
0x180020bd8  jnz     loc_180020A68
0x180020bde  mov     rdx, r10; struct CFlat::ComInterfaceTypeId *
0x180020be1  mov     rcx, rsi; this
0x180020be4  call    ?GetComInterfaceDispatcher$@ComImportAdapter@CFlat@@QEAAPEBXPEBUComInterfaceTypeId@2@@Z; CFlat::ComImportAdapter::GetComInterfaceDispatcher$(CFlat::ComInterfaceTypeId const *)
0x180020be9  mov     rcx, rax
0x180020bec  jmp     loc_180020A68
0x180020bf1  test    r12b, r12b
0x180020bf4  jz      short loc_180020C04
0x180020bf6  mov     rcx, r14; this
0x180020bf9  call    ?Leave@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Leave(void)
0x180020bfe  xor     r14d, r14d
0x180020c01  xor     r12b, r12b
0x180020c04  test    rbx, rbx
0x180020c07  jnz     loc_18002093A
0x180020c0d  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180020c13  call    cs:__imp_TlsGetValue
0x180020c19  mov     rsi, rax
0x180020c1c  test    rax, rax
0x180020c1f  jnz     loc_18002093A
0x180020c25  call    ?NoContext_GetThreadContextOrNullAndLock@Context@Cn@@SAPEAV12@XZ; Cn::Context::NoContext_GetThreadContextOrNullAndLock(void)
0x180020c2a  mov     rsi, rax
0x180020c2d  test    rax, rax
0x180020c30  jnz     loc_18002093A
0x180020c36  mov     r15d, 87B10101h
0x180020c3c  mov     dword ptr [rsp+88h+var_48], r15d
0x180020c41  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x180020c48  test    rcx, rcx
0x180020c4b  jz      loc_1800209E9
0x180020c51  mov     rax, [rcx]
0x180020c54  mov     r8, r13
0x180020c57  lea     rdx, [rsp+88h+var_48]
0x180020c5c  mov     rax, [rax+30h]
0x180020c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c65  mov     r15d, dword ptr [rsp+88h+var_48]
0x180020c6a  test    r15d, r15d
0x180020c6d  js      loc_1800209E9
0x180020c73  jmp     loc_18002093A
0x180020c78  mov     rax, [r8]
0x180020c7b  mov     rax, [rax+10h]
0x180020c7f  mov     rcx, r8; char16_t *
0x180020c82  jmp     loc_180020B8A
0x180020c87  mov     rdx, r13; void *
0x180020c8a  call    ?Fail@Abandonment@CFlat@@SAXPEB_SPEAX@Z; CFlat::Abandonment::Fail(char16_t const *,void *)
0x180020c90  mov     dword ptr [rbx+8], 1
0x180020c97  mov     rax, [rbx]
0x180020c9a  mov     rcx, rbx
0x180020c9d  mov     rax, [rax+8]
0x180020ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ca6  mov     rax, [rbx]
0x180020ca9  mov     edx, 1
0x180020cae  mov     rcx, rbx
0x180020cb1  mov     rax, [rax]
0x180020cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cb9  jmp     loc_180020B2A
0x180020cbe  mov     ecx, 87B10102h; int
0x180020cc3  mov     r8d, ecx; int
0x180020cc6  mov     rdx, r13; void *
0x180020cc9  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x180020ccf  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x180020cd5  sub     eax, 1
0x180020cd8  jz      loc_180020BF1
0x180020cde  cmp     eax, 1
0x180020ce1  jnz     loc_180020BF1
0x180020ce7  mov     rax, [rsi+60h]
0x180020ceb  test    rax, rax
0x180020cee  jnz     short loc_180020D0E
0x180020cf0  xor     r14d, r14d
0x180020cf3  jmp     short loc_180020D15
0x180020cf5  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180020cfb  call    cs:__imp_TlsGetValue
0x180020d01  mov     rbx, rax
0x180020d04  mov     [rsp+88h+var_48], rax
0x180020d09  jmp     loc_180020A00
0x180020d0e  mov     r14d, [rax+98h]
0x180020d15  call    cs:__imp_GetCurrentThreadId
0x180020d1b  cmp     r14d, eax
0x180020d1e  jz      short loc_180020D37
0x180020d20  call    cs:__imp_GetCurrentThread
0x180020d26  mov     rcx, rax; hHandle
0x180020d29  xor     r8d, r8d; bAlertable
0x180020d2c  mov     edx, 7530h; dwMilliseconds
0x180020d31  call    cs:__imp_WaitForSingleObjectEx
0x180020d37  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x180020d3e  test    rcx, rcx
0x180020d41  jz      short loc_180020D52
0x180020d43  mov     rax, [rcx]
0x180020d46  mov     rdx, r13
0x180020d49  mov     rax, [rax+38h]
0x180020d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d52  mov     rcx, rsi; void *
0x180020d55  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x180020d5a  mov     r15d, 87B10103h
0x180020d60  jmp     loc_1800209E9
0x180020d65  mov     r15d, dword ptr [rsp+88h+arg_0]
0x180020d6d  mov     rbx, [rsp+88h+var_48]
0x180020d72  jmp     loc_180020AAE
0x180020d77  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x180020d7d  mov     rax, [r8]
0x180020d80  mov     rax, [rax+8]
0x180020d84  jmp     loc_180020C7F
0x180020d89  mov     ecx, r14d; int
0x180020d8c  call    ?ConvertHRToWin32Error@Win32ErrorHandling@CFlat@@SAIH@Z; CFlat::Win32ErrorHandling::ConvertHRToWin32Error(int)
0x180020d91  mov     ecx, eax; dwErrCode
0x180020d93  call    cs:__imp_SetLastError
0x180020d99  jmp     loc_180020B71
```
