# Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$::AllocateItemForPeer(uint,void const *,uint *)

- ea: `0x18001f3b0`
- end: `0x18001f9a3`
- name: `?AllocateItemForPeer@ExportAdapter$@IExportMessageConversation@CoreUI@Microsoft@@UEAAJIPEBXPEAI@Z`
- size: `1523`
- prototype: `__int64 __fastcall(Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$ *__hidden this, unsigned int, const void *, unsigned int *)`
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x1800080a8`
- `0x1800082d0`
- `0x1800089c0`
- `0x180009750`
- `0x180010ed0`
- `0x18001f3b0`
- `0x18001ffcc`
- `0x180020df8`
- `0x180021bfc`
- `0x180024980`
- `0x18003950c`
- `0x18004a348`
- `0x18004aa90`
- `0x18008ae1c`
- `0x1800a6888`
- `0x1800c7e58`
- `0x1800c7eec`
- `0x1800c7f4c`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f617`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f617`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f42d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f42d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001f8f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001f8f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f5c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f5c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f997`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f997`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f8e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f8e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f452`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f8dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f452`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f8dc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001f4ac`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001f59b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001f4ac`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001f59b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f448`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f483`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f498`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f588`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f670`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f705`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f78f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f8c2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f448`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f483`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f498`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f588`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f670`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f705`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f78f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f8c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$::AllocateItemForPeer(
        Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$ *this,
        unsigned int a2,
        const void *a3,
        unsigned int *a4)
{
  __int64 v6; // rbx
  LPVOID v7; // rbx
  struct Cn::Context *Value; // rdi
  char v9; // r15
  __int64 v10; // r14
  int v11; // ecx
  int v12; // eax
  const char16_t *v13; // rcx
  const char16_t *v14; // rcx
  int v15; // r15d
  __int64 v16; // rdi
  int v17; // eax
  unsigned __int16 *v18; // r10
  int v19; // edx
  __int64 v20; // r9
  unsigned __int16 *v21; // rax
  void ***v22; // rcx
  unsigned int v23; // r14d
  int v24; // r14d
  const char16_t *v25; // rcx
  _QWORD *v26; // rdi
  __int64 v27; // rcx
  _QWORD *v29; // rbx
  __int64 v30; // r8
  __int64 v32; // rcx
  void (__fastcall *v33)(__int64); // rax
  __int64 v34; // rax
  void *v35; // r15
  void *v36; // r13
  __int64 v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // r14
  __int64 v41; // rax
  int v42; // r14d
  HANDLE CurrentThread; // rax
  DWORD v44; // eax
  int v45; // [rsp+30h] [rbp-88h] BYREF
  void *v46; // [rsp+38h] [rbp-80h] BYREF
  _QWORD v47[2]; // [rsp+40h] [rbp-78h] BYREF
  _QWORD v48[13]; // [rsp+50h] [rbp-68h] BYREF
  void *retaddr; // [rsp+B8h] [rbp+0h]
  int v50; // [rsp+C0h] [rbp+8h]

  v6 = *((_QWORD *)this + 2);
  if ( !*(_QWORD *)(v6 + 24) )
    return 2276524545LL;
  v46 = retaddr;
  if ( !Cn::Context::s_fTypeIsInitialized )
    CFlat::Abandonment::Fail((const char16_t *)this, retaddr);
  v7 = *(LPVOID *)(v6 + 16);
  if ( !v7 || !*((_BYTE *)v7 + 79) || TlsGetValue(Cn::Context::s_tlsStorage) != v7 )
  {
    Value = (struct Cn::Context *)v7;
    v9 = 0;
    while ( 1 )
    {
      if ( Value )
      {
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
            CFlat::Abandonment::FailWithHR(-2018443006, v46, -2018443006);
          if ( v10 )
          {
            if ( TlsGetValue(Cn::Context::s_tlsStorage) )
              CFlat::Abandonment::Fail(v13);
            if ( TlsGetValue(Cn::Context::s_tlsStorage) != Value && !TlsSetValue(Cn::Context::s_tlsStorage, Value) )
              CFlat::Abandonment::Fail(v14);
            _InterlockedIncrement((volatile signed __int32 *)Value + 2);
          }
          break;
        }
        if ( v12 == 2 )
        {
          v41 = *((_QWORD *)Value + 12);
          if ( v41 )
            v42 = *(_DWORD *)(v41 + 152);
          else
            v42 = 0;
          if ( v42 != GetCurrentThreadId() )
          {
            CurrentThread = GetCurrentThread();
            WaitForSingleObjectEx(CurrentThread, 0x7530u, 0);
          }
          if ( Cn::Process::Host )
            (*(void (__fastcall **)(struct Cn::ICnHost *, void *))(*(_QWORD *)Cn::Process::Host + 56LL))(
              Cn::Process::Host,
              v46);
          v15 = -2018443005;
          v50 = -2018443005;
          CFlat::EntryExit::OnEndCallToCFlat(Value);
          goto LABEL_19;
        }
        if ( v9 )
        {
          Cn::Engine::Lock::Leave((Cn::Engine::Lock *)v10);
          v9 = 0;
        }
      }
      if ( !v7 )
      {
        Value = (struct Cn::Context *)TlsGetValue(Cn::Context::s_tlsStorage);
        if ( !Value )
        {
          Value = Cn::Context::NoContext_GetThreadContextOrNullAndLock();
          if ( !Value )
          {
            v50 = -2018443007;
            v45 = -2018443007;
            if ( !Cn::Process::Host
              || ((*(void (__fastcall **)(struct Cn::ICnHost *, int *, void *))(*(_QWORD *)Cn::Process::Host + 48LL))(
                    Cn::Process::Host,
                    &v45,
                    v46),
                  v50 = v45,
                  v45 < 0) )
            {
              v15 = v50;
              goto LABEL_19;
            }
          }
        }
      }
    }
  }
  v15 = 0;
  v50 = 0;
LABEL_19:
  if ( v15 >= 0 )
  {
    if ( !v7 )
      v7 = TlsGetValue(Cn::Context::s_tlsStorage);
    v47[1] = v7;
    v16 = *(_QWORD *)(*((_QWORD *)this + 2) + 24LL);
    v48[4] = v16;
    if ( v16 )
    {
      v17 = *(_DWORD *)(v16 + 16);
      if ( v17 > 0 )
        *(_DWORD *)(v16 + 16) = v17 + 1;
    }
    v18 = *(unsigned __int16 **)(v16 + 8);
    v19 = 0;
    v20 = *v18;
    while ( 1 )
    {
      if ( v19 >= (int)v20 )
      {
        v22 = 0;
        goto LABEL_56;
      }
      v21 = &v18[8 * (v19 - v20)];
      if ( &Microsoft::CoreUI::IExportMessageConversation::TypeId$ == *(_UNKNOWN **)v21 )
        break;
      ++v19;
    }
    v22 = (void ***)*((_QWORD *)v21 + 1);
    if ( v22 )
      goto LABEL_29;
LABEL_56:
    if ( v16 && v18 == (unsigned __int16 *)&CFlat::ComImportAdapter::TypeId$ )
    {
      v47[0] = &Microsoft::CoreUI::IExportMessageConversation::TypeId$;
      std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::find(
        v16 + 32,
        v48,
        v47);
      if ( v48[0] == *(_QWORD *)(v16 + 40) )
      {
        v35 = TlsGetValue(Cn::Context::s_tlsStorage);
        v36 = CFlat::EntryExit::ValidateCall(v35, *(void **)(v16 + 24), 0);
        CFlat::EntryExit::OnBeginCallToNative(v35);
        v46 = 0;
        v45 = 0;
        v37 = lambda_9f26dbb50c5457f1a45ef1436d9c8d4d_::_lambda_9f26dbb50c5457f1a45ef1436d9c8d4d_(
                (unsigned int)v48,
                (unsigned int)&v45,
                v16,
                (unsigned int)v47,
                (__int64)&v46);
        CFlat::SehSafe::Execute__lambda_9f26dbb50c5457f1a45ef1436d9c8d4d___(v35, v37);
        Cn::Context::NoContext_NotifyReturn((Cn::Context *)v35, v36);
        v38 = v16 + 32;
        if ( v45 == -2147467262 )
        {
          *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::_Try_emplace<CFlat::ComInterfaceTypeId const * const &,>(
                                   v38,
                                   v48,
                                   v47)
                    + 24LL) = 0;
          v34 = 0;
          v15 = v50;
        }
        else
        {
          v39 = std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::_Try_emplace<CFlat::ComInterfaceTypeId const * const &,>(
                  v38,
                  v48,
                  v47);
          v40 = *(_QWORD *)v39;
          if ( *(_QWORD *)(*(_QWORD *)v39 + 24LL) )
          {
            CFlat::EntryExit::ReleaseComInterfaceFromCFlatCode(v35, v46);
          }
          else
          {
            *(_QWORD *)(v40 + 24) = v46;
            CFlat::EntryExit::AddCachedComImportAdapter(v35, v46, (struct CFlat::ComImportAdapter *)v16);
          }
          v34 = *(_QWORD *)(v40 + 24);
          v15 = v50;
        }
      }
      else
      {
        v34 = *(_QWORD *)(v48[0] + 24LL);
      }
      v22 = 0;
      if ( v34 )
        v22 = &off_1800D0720;
    }
LABEL_29:
    v23 = ((__int64 (__fastcall *)(void ***, __int64, _QWORD, const void *))**v22)(v22, v16, a2, a3);
    if ( v16 )
      System::Object::Release$((System::Object *)v16);
    if ( a4 )
      *a4 = v23;
    v24 = *((_DWORD *)v7 + 28);
    *((_DWORD *)v7 + 28) = 0;
    if ( !*((_BYTE *)v7 + 79) )
    {
      if ( TlsGetValue(Cn::Context::s_tlsStorage) && !TlsSetValue(Cn::Context::s_tlsStorage, 0) )
        CFlat::Abandonment::Fail(v25);
      v26 = (_QWORD *)*((_QWORD *)v7 + 10);
      *((_QWORD *)v7 + 10) = 0;
      v27 = *((_QWORD *)v7 + 11);
      if ( (*(_DWORD *)(v27 + 60))-- == 1 )
      {
        *(_QWORD *)(v27 + 64) = 0;
        *(_DWORD *)(v27 + 72) = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v27 + 16));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) == 1 )
      {
        *((_DWORD *)v7 + 2) = 1;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 8LL))(v7);
        (**(void (__fastcall ***)(LPVOID, __int64))v7)(v7, 1);
      }
      if ( v26 )
      {
        while ( 1 )
        {
          v29 = (_QWORD *)*v26;
          *v26 = 0;
          v30 = v26[3];
          if ( !*((_BYTE *)v26 + 8) )
            break;
          if ( *((_BYTE *)v26 + 8) == 1 )
          {
            v33 = *(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL);
LABEL_71:
            v32 = v26[3];
            goto LABEL_49;
          }
          if ( *((_BYTE *)v26 + 8) == 2 )
          {
            v32 = v26[2];
            v33 = (void (__fastcall *)(__int64))v26[3];
LABEL_49:
            v33(v32);
          }
          free(v26);
          v26 = v29;
          if ( !v29 )
            goto LABEL_45;
        }
        v33 = *(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL);
        goto LABEL_71;
      }
LABEL_45:
      if ( v24 )
      {
        v44 = CFlat::Win32ErrorHandling::ConvertHRToWin32Error(v24);
        SetLastError(v44);
      }
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001f3b0  mov     [rsp+arg_10], r8
0x18001f3b5  mov     [rsp+arg_8], edx
0x18001f3b9  push    rbx
0x18001f3ba  push    rsi
0x18001f3bb  push    rdi
0x18001f3bc  push    r12
0x18001f3be  push    r13
0x18001f3c0  push    r14
0x18001f3c2  push    r15
0x18001f3c4  sub     rsp, 80h
0x18001f3cb  mov     r12, r9
0x18001f3ce  mov     r13, rcx
0x18001f3d1  mov     rbx, [rcx+10h]
0x18001f3d5  cmp     qword ptr [rbx+18h], 0
0x18001f3da  jz      loc_18001F659
0x18001f3e0  mov     rax, [rsp+0B8h]
0x18001f3e8  mov     [rsp+0B8h+var_80], rax
0x18001f3ed  cmp     cs:?s_fTypeIsInitialized@Context@Cn@@0_NA, 0; bool Cn::Context::s_fTypeIsInitialized
0x18001f3f4  jz      loc_18001F84B
0x18001f3fa  mov     rbx, [rbx+10h]
0x18001f3fe  test    rbx, rbx
0x18001f401  jnz     loc_18001F660
0x18001f407  mov     rdi, rbx
0x18001f40a  xor     esi, esi
0x18001f40c  mov     r14d, esi
0x18001f40f  xor     r15b, r15b
0x18001f412  test    rdi, rdi
0x18001f415  jz      loc_18001F6F6
0x18001f41b  test    r15b, r15b
0x18001f41e  jnz     short loc_18001F45F
0x18001f420  mov     r14, [rdi+58h]
0x18001f424  test    r14, r14
0x18001f427  jz      short loc_18001F45F
0x18001f429  lea     rcx, [r14+10h]; lpCriticalSection
0x18001f42d  call    cs:__imp_EnterCriticalSection
0x18001f433  mov     ecx, [r14+3Ch]
0x18001f437  lea     eax, [rcx+1]
0x18001f43a  mov     [r14+3Ch], eax
0x18001f43e  test    ecx, ecx
0x18001f440  jnz     short loc_18001F45C
0x18001f442  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001f448  call    cs:__imp_TlsGetValue
0x18001f44e  mov     [r14+40h], rax
0x18001f452  call    cs:__imp_GetCurrentThreadId
0x18001f458  mov     [r14+48h], eax
0x18001f45c  mov     r15b, 1
0x18001f45f  mov     eax, [rdi+48h]
0x18001f462  test    eax, eax
0x18001f464  jnz     loc_18001F89C
0x18001f46a  test    rbx, rbx
0x18001f46d  jz      short loc_18001F478
0x18001f46f  cmp     rdi, rbx
0x18001f472  jnz     loc_18001F882
0x18001f478  test    r14, r14
0x18001f47b  jz      short loc_18001F4BE
0x18001f47d  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001f483  call    cs:__imp_TlsGetValue
0x18001f489  test    rax, rax
0x18001f48c  jnz     loc_18001F896
0x18001f492  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001f498  call    cs:__imp_TlsGetValue
0x18001f49e  cmp     rax, rdi
0x18001f4a1  jz      short loc_18001F4BA
0x18001f4a3  mov     rdx, rdi; lpTlsValue
0x18001f4a6  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001f4ac  call    cs:__imp_TlsSetValue
0x18001f4b2  test    eax, eax
0x18001f4b4  jz      loc_18001F961
0x18001f4ba  lock inc dword ptr [rdi+8]
0x18001f4be  mov     r15d, esi
0x18001f4c1  mov     [rsp+0B8h+arg_0], esi
0x18001f4c8  test    r15d, r15d
0x18001f4cb  js      loc_18001F62E
0x18001f4d1  test    rbx, rbx
0x18001f4d4  jz      loc_18001F8BC
0x18001f4da  mov     [rsp+0B8h+var_70], rbx
0x18001f4df  mov     rax, [r13+10h]
0x18001f4e3  mov     rdi, [rax+18h]
0x18001f4e7  mov     [rsp+0B8h+var_48], rdi
0x18001f4ec  test    rdi, rdi
0x18001f4ef  jz      short loc_18001F4FD
0x18001f4f1  mov     eax, [rdi+10h]
0x18001f4f4  test    eax, eax
0x18001f4f6  jle     short loc_18001F4FD
0x18001f4f8  inc     eax
0x18001f4fa  mov     [rdi+10h], eax
0x18001f4fd  mov     r10, [rdi+8]
0x18001f501  mov     edx, esi
0x18001f503  movzx   r9d, word ptr [r10]
0x18001f507  lea     r11, ?TypeId$@IExportMessageConversation@CoreUI@Microsoft@@2U?$ComInterfaceTypeIdField@VIExportMessageConversation@CoreUI@Microsoft@@UIMessageConversation@@$0A@@CFlat@@B; CFlat::ComInterfaceTypeIdField<Microsoft::CoreUI::IExportMessageConversation,IMessageConversation,0> const Microsoft::CoreUI::IExportMessageConversation::TypeId$
0x18001f50e  cmp     edx, r9d
0x18001f511  jge     loc_18001F686
0x18001f517  movsxd  rcx, edx
0x18001f51a  sub     rcx, r9
0x18001f51d  add     rcx, rcx
0x18001f520  lea     rax, [r10+rcx*8]
0x18001f524  cmp     r11, [rax]
0x18001f527  jnz     loc_18001F652
0x18001f52d  mov     rcx, [rax+8]
0x18001f531  test    rcx, rcx
0x18001f534  jz      loc_18001F689
0x18001f53a  mov     rax, [rcx]
0x18001f53d  mov     r9, [rsp+0B8h+arg_10]
0x18001f545  mov     r8d, [rsp+0B8h+arg_8]
0x18001f54d  mov     rdx, rdi
0x18001f550  mov     rax, [rax]
0x18001f553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f558  mov     r14d, eax
0x18001f55b  test    rdi, rdi
0x18001f55e  jz      short loc_18001F568
0x18001f560  mov     rcx, rdi; this
0x18001f563  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18001f568  test    r12, r12
0x18001f56b  jz      short loc_18001F571
0x18001f56d  mov     [r12], r14d
0x18001f571  mov     r14d, [rbx+70h]
0x18001f575  mov     [rbx+70h], esi
0x18001f578  cmp     byte ptr [rbx+4Fh], 0
0x18001f57c  jnz     loc_18001F62E
0x18001f582  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001f588  call    cs:__imp_TlsGetValue
0x18001f58e  test    rax, rax
0x18001f591  jz      short loc_18001F5A9
0x18001f593  xor     edx, edx; lpTlsValue
0x18001f595  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001f59b  call    cs:__imp_TlsSetValue
0x18001f5a1  test    eax, eax
0x18001f5a3  jz      loc_18001F97B
0x18001f5a9  mov     rdi, [rbx+50h]
0x18001f5ad  mov     [rbx+50h], rsi
0x18001f5b1  mov     rcx, [rbx+58h]
0x18001f5b5  add     dword ptr [rcx+3Ch], 0FFFFFFFFh
0x18001f5b9  jnz     short loc_18001F5C2
0x18001f5bb  mov     [rcx+40h], rsi
0x18001f5bf  mov     [rcx+48h], esi
0x18001f5c2  add     rcx, 10h; lpCriticalSection
0x18001f5c6  call    cs:__imp_LeaveCriticalSection
0x18001f5cc  mov     eax, 0FFFFFFFFh
0x18001f5d1  lock xadd [rbx+8], eax
0x18001f5d6  cmp     eax, 1
0x18001f5d9  jz      loc_18001F854
0x18001f5df  test    rdi, rdi
0x18001f5e2  jz      short loc_18001F625
0x18001f5e4  nop     dword ptr [rax+00h]
0x18001f5e8  nop     dword ptr [rax+rax+00000000h]
0x18001f5f0  mov     rbx, [rdi]
0x18001f5f3  mov     [rdi], rsi
0x18001f5f6  mov     r8, [rdi+18h]
0x18001f5fa  movzx   ecx, byte ptr [rdi+8]
0x18001f5fe  test    ecx, ecx
0x18001f600  jz      loc_18001F981
0x18001f606  sub     ecx, 1
0x18001f609  jz      loc_18001F77A
0x18001f60f  cmp     ecx, 1
0x18001f612  jz      short loc_18001F644
0x18001f614  mov     rcx, rdi; Block
0x18001f617  call    cs:__imp_free
0x18001f61d  mov     rdi, rbx
0x18001f620  test    rbx, rbx
0x18001f623  jnz     short loc_18001F5F0
0x18001f625  test    r14d, r14d
0x18001f628  jnz     loc_18001F98D
0x18001f62e  mov     eax, r15d
0x18001f631  add     rsp, 80h
0x18001f638  pop     r15
0x18001f63a  pop     r14
0x18001f63c  pop     r13
0x18001f63e  pop     r12
0x18001f640  pop     rdi
0x18001f641  pop     rsi
0x18001f642  pop     rbx
0x18001f643  retn
0x18001f644  mov     rcx, [rdi+10h]
0x18001f648  mov     rax, r8
0x18001f64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f650  jmp     short loc_18001F614
0x18001f652  inc     edx
0x18001f654  jmp     loc_18001F50E
0x18001f659  mov     eax, 87B10201h
0x18001f65e  jmp     short loc_18001F631
0x18001f660  cmp     byte ptr [rbx+4Fh], 0
0x18001f664  jz      loc_18001F407
0x18001f66a  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001f670  call    cs:__imp_TlsGetValue
0x18001f676  cmp     rax, rbx
0x18001f679  jnz     loc_18001F407
0x18001f67f  xor     esi, esi
0x18001f681  jmp     loc_18001F4BE
0x18001f686  mov     rcx, rsi
0x18001f689  test    rdi, rdi
0x18001f68c  jz      loc_18001F53A
0x18001f692  lea     rax, ?TypeId$@ComImportAdapter@CFlat@@2U?$ObjectTypeIdField@VComImportAdapter@CFlat@@$0A@$0A@@2@B; CFlat::ObjectTypeIdField<CFlat::ComImportAdapter,0,0> const CFlat::ComImportAdapter::TypeId$
0x18001f699  cmp     r10, rax
0x18001f69c  jnz     loc_18001F53A
0x18001f6a2  mov     [rsp+0B8h+var_78], r11
0x18001f6a7  lea     r8, [rsp+0B8h+var_78]
0x18001f6ac  lea     rdx, [rsp+0B8h+var_68]
0x18001f6b1  lea     rcx, [rdi+20h]
0x18001f6b5  call    ?find@?$_Hash@V?$_Umap_traits@PEBUComInterfaceTypeId@CFlat@@PEAXV?$_Uhash_compare@PEBUComInterfaceTypeId@CFlat@@U?$hash@PEBUComInterfaceTypeId@CFlat@@@std@@U?$equal_to@PEBUComInterfaceTypeId@CFlat@@@4@@std@@V?$Allocator@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@@std@@@std@@@2@AEBQEBUComInterfaceTypeId@CFlat@@@Z; std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::find(CFlat::ComInterfaceTypeId const * const &)
0x18001f6ba  mov     rax, [rsp+0B8h+var_68]
0x18001f6bf  cmp     rax, [rdi+28h]
0x18001f6c3  jz      loc_18001F789
0x18001f6c9  mov     rax, [rax+18h]
0x18001f6cd  lea     rdx, off_1800D0720
0x18001f6d4  mov     rcx, rsi
0x18001f6d7  test    rax, rax
0x18001f6da  cmovnz  rcx, rdx
0x18001f6de  jmp     loc_18001F53A
0x18001f6e3  test    r15b, r15b
0x18001f6e6  jz      short loc_18001F6F6
0x18001f6e8  mov     rcx, r14; this
0x18001f6eb  call    ?Leave@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Leave(void)
0x18001f6f0  mov     r14, rsi
0x18001f6f3  xor     r15b, r15b
0x18001f6f6  test    rbx, rbx
0x18001f6f9  jnz     loc_18001F412
0x18001f6ff  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001f705  call    cs:__imp_TlsGetValue
0x18001f70b  mov     rdi, rax
0x18001f70e  test    rax, rax
0x18001f711  jnz     loc_18001F412
0x18001f717  call    ?NoContext_GetThreadContextOrNullAndLock@Context@Cn@@SAPEAV12@XZ; Cn::Context::NoContext_GetThreadContextOrNullAndLock(void)
0x18001f71c  mov     rdi, rax
0x18001f71f  test    rax, rax
0x18001f722  jnz     loc_18001F412
0x18001f728  mov     eax, 87B10101h
0x18001f72d  mov     [rsp+0B8h+arg_0], eax
0x18001f734  mov     [rsp+0B8h+var_88], eax
0x18001f738  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x18001f73f  test    rcx, rcx
0x18001f742  jz      short loc_18001F76D
0x18001f744  mov     rax, [rcx]
0x18001f747  mov     r8, [rsp+0B8h+var_80]
0x18001f74c  lea     rdx, [rsp+0B8h+var_88]
0x18001f751  mov     rax, [rax+30h]
0x18001f755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f75a  mov     eax, [rsp+0B8h+var_88]
0x18001f75e  mov     [rsp+0B8h+arg_0], eax
0x18001f765  test    eax, eax
0x18001f767  jns     loc_18001F412
0x18001f76d  mov     r15d, [rsp+0B8h+arg_0]
0x18001f775  jmp     loc_18001F4C8
0x18001f77a  mov     rax, [r8]
0x18001f77d  mov     rax, [rax+10h]
0x18001f781  mov     rcx, r8
0x18001f784  jmp     loc_18001F64B
0x18001f789  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001f78f  call    cs:__imp_TlsGetValue
0x18001f795  mov     r15, rax
0x18001f798  xor     r8d, r8d; int
0x18001f79b  mov     rdx, [rdi+18h]; void *
0x18001f79f  mov     rcx, rax; void *
0x18001f7a2  call    ?ValidateCall@EntryExit@CFlat@@SAPEAXPEAX0H@Z; CFlat::EntryExit::ValidateCall(void *,void *,int)
0x18001f7a7  mov     r13, rax
0x18001f7aa  mov     rcx, r15; void *
0x18001f7ad  call    ?OnBeginCallToNative@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnBeginCallToNative(void *)
0x18001f7b2  mov     [rsp+0B8h+var_80], rsi
0x18001f7b7  mov     [rsp+0B8h+var_88], esi
0x18001f7bb  lea     rax, [rsp+0B8h+var_80]
0x18001f7c0  mov     [rsp+0B8h+var_98], rax
0x18001f7c5  lea     r9, [rsp+0B8h+var_78]
0x18001f7ca  mov     r8, rdi
0x18001f7cd  lea     rdx, [rsp+0B8h+var_88]
0x18001f7d2  lea     rcx, [rsp+0B8h+var_68]
0x18001f7d7  call    _lambda_9f26dbb50c5457f1a45ef1436d9c8d4d____lambda_9f26dbb50c5457f1a45ef1436d9c8d4d_
0x18001f7dc  mov     rdx, rax
0x18001f7df  mov     rcx, r15
0x18001f7e2  call    CFlat__SehSafe__Execute__lambda_9f26dbb50c5457f1a45ef1436d9c8d4d___
0x18001f7e7  mov     rdx, r13; void *
0x18001f7ea  mov     rcx, r15; this
0x18001f7ed  call    ?NoContext_NotifyReturn@Context@Cn@@QEAAXPEAX@Z; Cn::Context::NoContext_NotifyReturn(void *)
0x18001f7f2  lea     r8, [rsp+0B8h+var_78]
0x18001f7f7  lea     rdx, [rsp+0B8h+var_68]
0x18001f7fc  lea     rcx, [rdi+20h]
0x18001f800  cmp     [rsp+0B8h+var_88], 80004002h
0x18001f808  jz      loc_18001F936
0x18001f80e  call    ??$_Try_emplace@AEBQEBUComInterfaceTypeId@CFlat@@$$V@?$_Hash@V?$_Umap_traits@PEBUComInterfaceTypeId@CFlat@@PEAXV?$_Uhash_compare@PEBUComInterfaceTypeId@CFlat@@U?$hash@PEBUComInterfaceTypeId@CFlat@@@std@@U?$equal_to@PEBUComInterfaceTypeId@CFlat@@@4@@std@@V?$Allocator@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@PEAX@std@@_N@1@AEBQEBUComInterfaceTypeId@CFlat@@@Z; std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::_Try_emplace<CFlat::ComInterfaceTypeId const * const &,>(CFlat::ComInterfaceTypeId const * const &)
0x18001f813  mov     r14, [rax]
0x18001f816  mov     rcx, r15; void *
0x18001f819  cmp     qword ptr [r14+18h], 0
0x18001f81e  jnz     loc_18001F952
0x18001f824  mov     rax, [rsp+0B8h+var_80]
0x18001f829  mov     [r14+18h], rax
0x18001f82d  mov     r8, rdi; struct CFlat::ComImportAdapter *
0x18001f830  mov     rdx, [rsp+0B8h+var_80]; void *
0x18001f835  call    ?AddCachedComImportAdapter@EntryExit@CFlat@@SAXPEAX0PEAVComImportAdapter@2@@Z; CFlat::EntryExit::AddCachedComImportAdapter(void *,void *,CFlat::ComImportAdapter *)
0x18001f83a  mov     rax, [r14+18h]
0x18001f83e  mov     r15d, [rsp+0B8h+arg_0]
0x18001f846  jmp     loc_18001F6CD
0x18001f84b  mov     rdx, rax; void *
0x18001f84e  call    ?Fail@Abandonment@CFlat@@SAXPEB_SPEAX@Z; CFlat::Abandonment::Fail(char16_t const *,void *)
0x18001f854  mov     dword ptr [rbx+8], 1
0x18001f85b  mov     rax, [rbx]
0x18001f85e  mov     rcx, rbx
0x18001f861  mov     rax, [rax+8]
0x18001f865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f86a  mov     rax, [rbx]
0x18001f86d  mov     edx, 1
0x18001f872  mov     rcx, rbx
0x18001f875  mov     rax, [rax]
  ... truncated ...
```
