# Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$::RemoveItem(uint,uint,bool,void * *)

- ea: `0x18001f9b0`
- end: `0x18001ffc5`
- name: `?RemoveItem@ExportAdapter$@IExportMessageConversation@CoreUI@Microsoft@@UEAAJII_NPEAPEAX@Z`
- size: `1557`
- prototype: `__int64 __fastcall(Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$ *__hidden this, unsigned int, unsigned int, bool, void **)`
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x1800080a8`
- `0x1800082d0`
- `0x1800089c0`
- `0x180009750`
- `0x180010ed0`
- `0x18001f9b0`
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

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fc47`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fc47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fa2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fa2a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001ff24`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001ff24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fbf7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fbf7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ffb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ffb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ff13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ff13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fa4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ff08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fa4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ff08`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001faa9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001fbcc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001faa9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001fbcc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fa45`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fa80`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fa95`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fbb9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fca0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fd3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fdc5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001feee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fa45`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fa80`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fa95`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fbb9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fca0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fd3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fdc5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001feee`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$::RemoveItem(
        Microsoft::CoreUI::IExportMessageConversation::ExportAdapter$ *this,
        unsigned int a2,
        int a3,
        char a4,
        void **a5)
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
  __int64 *v18; // r10
  int v19; // edx
  __int64 v20; // r9
  __int64 *v21; // rax
  void ***v22; // rcx
  int v23; // r14d
  const char16_t *v24; // rcx
  _QWORD *v25; // rdi
  __int64 v26; // rcx
  _QWORD *v28; // rbx
  __int64 v29; // r8
  __int64 v31; // rcx
  void (__fastcall *v32)(__int64); // rax
  __int64 v33; // rax
  void *v34; // r12
  void *v35; // r13
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // r15
  __int64 v40; // rax
  int v41; // r14d
  HANDLE CurrentThread; // rax
  DWORD v43; // eax
  int v44; // [rsp+40h] [rbp-98h] BYREF
  __int64 *v45; // [rsp+48h] [rbp-90h] BYREF
  void *v46; // [rsp+50h] [rbp-88h] BYREF
  _QWORD v47[2]; // [rsp+58h] [rbp-80h] BYREF
  _QWORD v48[14]; // [rsp+68h] [rbp-70h] BYREF
  void *retaddr; // [rsp+D8h] [rbp+0h]
  int v50; // [rsp+E0h] [rbp+8h]

  v6 = *((_QWORD *)this + 2);
  if ( !*(_QWORD *)(v6 + 24) )
    return 2276524545LL;
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
            CFlat::Abandonment::FailWithHR(-2018443006, retaddr, -2018443006);
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
          v40 = *((_QWORD *)Value + 12);
          if ( v40 )
            v41 = *(_DWORD *)(v40 + 152);
          else
            v41 = 0;
          if ( v41 != GetCurrentThreadId() )
          {
            CurrentThread = GetCurrentThread();
            WaitForSingleObjectEx(CurrentThread, 0x7530u, 0);
          }
          if ( Cn::Process::Host )
            (*(void (__fastcall **)(struct Cn::ICnHost *, void *))(*(_QWORD *)Cn::Process::Host + 56LL))(
              Cn::Process::Host,
              retaddr);
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
            v44 = -2018443007;
            if ( !Cn::Process::Host
              || ((*(void (__fastcall **)(struct Cn::ICnHost *, int *, void *))(*(_QWORD *)Cn::Process::Host + 48LL))(
                    Cn::Process::Host,
                    &v44,
                    retaddr),
                  v50 = v44,
                  v44 < 0) )
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
    if ( a5 )
      *a5 = 0;
    v16 = *(_QWORD *)(*((_QWORD *)this + 2) + 24LL);
    v48[4] = v16;
    if ( v16 )
    {
      v17 = *(_DWORD *)(v16 + 16);
      if ( v17 > 0 )
        *(_DWORD *)(v16 + 16) = v17 + 1;
    }
    v18 = *(__int64 **)(v16 + 8);
    v19 = 0;
    v20 = *(unsigned __int16 *)v18;
    while ( 1 )
    {
      if ( v19 >= (int)v20 )
      {
        v22 = 0;
        goto LABEL_59;
      }
      v21 = &v18[2 * (v19 - v20)];
      if ( &Microsoft::CoreUI::IExportMessageConversation::TypeId$ == (__int64 *)*v21 )
        break;
      ++v19;
    }
    v22 = (void ***)v21[1];
    if ( v22 )
      goto LABEL_31;
LABEL_59:
    if ( v16 && v18 == &CFlat::ComImportAdapter::TypeId$ )
    {
      v45 = &Microsoft::CoreUI::IExportMessageConversation::TypeId$;
      std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::find(
        v16 + 32,
        v48,
        &v45);
      if ( v48[0] == *(_QWORD *)(v16 + 40) )
      {
        v34 = TlsGetValue(Cn::Context::s_tlsStorage);
        v35 = CFlat::EntryExit::ValidateCall(v34, *(void **)(v16 + 24), 0);
        CFlat::EntryExit::OnBeginCallToNative(v34);
        v46 = 0;
        v44 = 0;
        v36 = lambda_9f26dbb50c5457f1a45ef1436d9c8d4d_::_lambda_9f26dbb50c5457f1a45ef1436d9c8d4d_(
                (unsigned int)v48,
                (unsigned int)&v44,
                v16,
                (unsigned int)&v45,
                (__int64)&v46);
        CFlat::SehSafe::Execute__lambda_9f26dbb50c5457f1a45ef1436d9c8d4d___(v34, v36);
        Cn::Context::NoContext_NotifyReturn((Cn::Context *)v34, v35);
        v37 = v16 + 32;
        if ( v44 == -2147467262 )
        {
          *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::_Try_emplace<CFlat::ComInterfaceTypeId const * const &,>(
                                   v37,
                                   v48,
                                   &v45)
                    + 24LL) = 0;
          v33 = 0;
        }
        else
        {
          v38 = std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::_Try_emplace<CFlat::ComInterfaceTypeId const * const &,>(
                  v37,
                  v48,
                  &v45);
          v39 = *(_QWORD *)v38;
          if ( *(_QWORD *)(*(_QWORD *)v38 + 24LL) )
          {
            CFlat::EntryExit::ReleaseComInterfaceFromCFlatCode(v34, v46);
          }
          else
          {
            *(_QWORD *)(v39 + 24) = v46;
            CFlat::EntryExit::AddCachedComImportAdapter(v34, v46, (struct CFlat::ComImportAdapter *)v16);
          }
          v33 = *(_QWORD *)(v39 + 24);
        }
      }
      else
      {
        v33 = *(_QWORD *)(v48[0] + 24LL);
      }
      v22 = 0;
      if ( v33 )
        v22 = &off_1800D0720;
      v15 = v50;
    }
LABEL_31:
    ((void (__fastcall *)(void ***, _QWORD *, __int64, _QWORD, int, char))(*v22)[3])(v22, v47, v16, a2, a3, a4);
    if ( v16 )
      System::Object::Release$((System::Object *)v16);
    if ( a5 && v47 != a5 )
      *a5 = (void *)v47[0];
    v23 = *((_DWORD *)v7 + 28);
    *((_DWORD *)v7 + 28) = 0;
    if ( !*((_BYTE *)v7 + 79) )
    {
      if ( TlsGetValue(Cn::Context::s_tlsStorage) && !TlsSetValue(Cn::Context::s_tlsStorage, 0) )
        CFlat::Abandonment::Fail(v24);
      v25 = (_QWORD *)*((_QWORD *)v7 + 10);
      *((_QWORD *)v7 + 10) = 0;
      v26 = *((_QWORD *)v7 + 11);
      if ( (*(_DWORD *)(v26 + 60))-- == 1 )
      {
        *(_QWORD *)(v26 + 64) = 0;
        *(_DWORD *)(v26 + 72) = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v26 + 16));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) == 1 )
      {
        *((_DWORD *)v7 + 2) = 1;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 8LL))(v7);
        (**(void (__fastcall ***)(LPVOID, __int64))v7)(v7, 1);
      }
      if ( v25 )
      {
        while ( 1 )
        {
          v28 = (_QWORD *)*v25;
          *v25 = 0;
          v29 = v25[3];
          if ( !*((_BYTE *)v25 + 8) )
            break;
          if ( *((_BYTE *)v25 + 8) == 1 )
          {
            v32 = *(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL);
LABEL_75:
            v31 = v25[3];
            goto LABEL_52;
          }
          if ( *((_BYTE *)v25 + 8) == 2 )
          {
            v31 = v25[2];
            v32 = (void (__fastcall *)(__int64))v25[3];
LABEL_52:
            v32(v31);
          }
          free(v25);
          v25 = v28;
          if ( !v28 )
            goto LABEL_48;
        }
        v32 = *(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL);
        goto LABEL_75;
      }
LABEL_48:
      if ( v23 )
      {
        v43 = CFlat::Win32ErrorHandling::ConvertHRToWin32Error(v23);
        SetLastError(v43);
      }
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001f9b0  mov     [rsp+arg_18], r9b
0x18001f9b5  mov     [rsp+arg_10], r8d
0x18001f9ba  mov     [rsp+arg_8], edx
0x18001f9be  push    rbx
0x18001f9bf  push    rsi
0x18001f9c0  push    rdi
0x18001f9c1  push    r12
0x18001f9c3  push    r13
0x18001f9c5  push    r14
0x18001f9c7  push    r15
0x18001f9c9  sub     rsp, 0A0h
0x18001f9d0  mov     r13, rcx
0x18001f9d3  mov     rbx, [rcx+10h]
0x18001f9d7  cmp     qword ptr [rbx+18h], 0
0x18001f9dc  jz      loc_18001FC89
0x18001f9e2  mov     r12, [rsp+0D8h]
0x18001f9ea  cmp     cs:?s_fTypeIsInitialized@Context@Cn@@0_NA, 0; bool Cn::Context::s_fTypeIsInitialized
0x18001f9f1  jz      loc_18001FE79
0x18001f9f7  mov     rbx, [rbx+10h]
0x18001f9fb  test    rbx, rbx
0x18001f9fe  jnz     loc_18001FC90
0x18001fa04  mov     rdi, rbx
0x18001fa07  xor     esi, esi
0x18001fa09  mov     r14d, esi
0x18001fa0c  xor     r15b, r15b
0x18001fa0f  test    rdi, rdi
0x18001fa12  jz      loc_18001FD2E
0x18001fa18  test    r15b, r15b
0x18001fa1b  jnz     short loc_18001FA5C
0x18001fa1d  mov     r14, [rdi+58h]
0x18001fa21  test    r14, r14
0x18001fa24  jz      short loc_18001FA5C
0x18001fa26  lea     rcx, [r14+10h]; lpCriticalSection
0x18001fa2a  call    cs:__imp_EnterCriticalSection
0x18001fa30  mov     ecx, [r14+3Ch]
0x18001fa34  lea     eax, [rcx+1]
0x18001fa37  mov     [r14+3Ch], eax
0x18001fa3b  test    ecx, ecx
0x18001fa3d  jnz     short loc_18001FA59
0x18001fa3f  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001fa45  call    cs:__imp_TlsGetValue
0x18001fa4b  mov     [r14+40h], rax
0x18001fa4f  call    cs:__imp_GetCurrentThreadId
0x18001fa55  mov     [r14+48h], eax
0x18001fa59  mov     r15b, 1
0x18001fa5c  mov     eax, [rdi+48h]
0x18001fa5f  test    eax, eax
0x18001fa61  jnz     loc_18001FEC8
0x18001fa67  test    rbx, rbx
0x18001fa6a  jz      short loc_18001FA75
0x18001fa6c  cmp     rdi, rbx
0x18001fa6f  jnz     loc_18001FEB0
0x18001fa75  test    r14, r14
0x18001fa78  jz      short loc_18001FABB
0x18001fa7a  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001fa80  call    cs:__imp_TlsGetValue
0x18001fa86  test    rax, rax
0x18001fa89  jnz     loc_18001FEC2
0x18001fa8f  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001fa95  call    cs:__imp_TlsGetValue
0x18001fa9b  cmp     rax, rdi
0x18001fa9e  jz      short loc_18001FAB7
0x18001faa0  mov     rdx, rdi; lpTlsValue
0x18001faa3  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001faa9  call    cs:__imp_TlsSetValue
0x18001faaf  test    eax, eax
0x18001fab1  jz      loc_18001FF83
0x18001fab7  lock inc dword ptr [rdi+8]
0x18001fabb  mov     r15d, esi
0x18001fabe  mov     [rsp+0D8h+arg_0], esi
0x18001fac5  test    r15d, r15d
0x18001fac8  js      loc_18001FC5E
0x18001face  test    rbx, rbx
0x18001fad1  jz      loc_18001FEE8
0x18001fad7  mov     [rsp+0D8h+var_78], rbx
0x18001fadc  mov     r14, [rsp+0D8h+arg_20]
0x18001fae4  test    r14, r14
0x18001fae7  jz      short loc_18001FAEC
0x18001fae9  mov     [r14], rsi
0x18001faec  mov     rax, [r13+10h]
0x18001faf0  mov     rdi, [rax+18h]
0x18001faf4  mov     [rsp+0D8h+var_50], rdi
0x18001fafc  test    rdi, rdi
0x18001faff  jz      short loc_18001FB0D
0x18001fb01  mov     eax, [rdi+10h]
0x18001fb04  test    eax, eax
0x18001fb06  jle     short loc_18001FB0D
0x18001fb08  inc     eax
0x18001fb0a  mov     [rdi+10h], eax
0x18001fb0d  mov     r10, [rdi+8]
0x18001fb11  mov     edx, esi
0x18001fb13  movzx   r9d, word ptr [r10]
0x18001fb17  lea     r11, ?TypeId$@IExportMessageConversation@CoreUI@Microsoft@@2U?$ComInterfaceTypeIdField@VIExportMessageConversation@CoreUI@Microsoft@@UIMessageConversation@@$0A@@CFlat@@B; CFlat::ComInterfaceTypeIdField<Microsoft::CoreUI::IExportMessageConversation,IMessageConversation,0> const Microsoft::CoreUI::IExportMessageConversation::TypeId$
0x18001fb1e  cmp     edx, r9d
0x18001fb21  jge     loc_18001FCB6
0x18001fb27  movsxd  rcx, edx
0x18001fb2a  sub     rcx, r9
0x18001fb2d  add     rcx, rcx
0x18001fb30  lea     rax, [r10+rcx*8]
0x18001fb34  cmp     r11, [rax]
0x18001fb37  jnz     loc_18001FC82
0x18001fb3d  mov     rcx, [rax+8]
0x18001fb41  test    rcx, rcx
0x18001fb44  jz      loc_18001FCB9
0x18001fb4a  mov     rax, [rcx]
0x18001fb4d  movzx   edx, [rsp+0D8h+arg_18]
0x18001fb55  mov     [rsp+0D8h+var_B0], dl
0x18001fb59  mov     edx, [rsp+0D8h+arg_10]
0x18001fb60  mov     dword ptr [rsp+0D8h+var_B8], edx
0x18001fb64  mov     r9d, [rsp+0D8h+arg_8]
0x18001fb6c  mov     r8, rdi
0x18001fb6f  lea     rdx, [rsp+0D8h+var_80]
0x18001fb74  mov     rax, [rax+18h]
0x18001fb78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb7d  nop
0x18001fb7e  test    rdi, rdi
0x18001fb81  jz      short loc_18001FB8B
0x18001fb83  mov     rcx, rdi; this
0x18001fb86  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18001fb8b  test    r14, r14
0x18001fb8e  jz      short loc_18001FBA2
0x18001fb90  lea     rax, [rsp+0D8h+var_80]
0x18001fb95  cmp     rax, r14
0x18001fb98  jz      short loc_18001FBA2
0x18001fb9a  mov     rax, [rsp+0D8h+var_80]
0x18001fb9f  mov     [r14], rax
0x18001fba2  mov     r14d, [rbx+70h]
0x18001fba6  mov     [rbx+70h], esi
0x18001fba9  cmp     byte ptr [rbx+4Fh], 0
0x18001fbad  jnz     loc_18001FC5E
0x18001fbb3  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001fbb9  call    cs:__imp_TlsGetValue
0x18001fbbf  test    rax, rax
0x18001fbc2  jz      short loc_18001FBDA
0x18001fbc4  xor     edx, edx; lpTlsValue
0x18001fbc6  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001fbcc  call    cs:__imp_TlsSetValue
0x18001fbd2  test    eax, eax
0x18001fbd4  jz      loc_18001FF9D
0x18001fbda  mov     rdi, [rbx+50h]
0x18001fbde  mov     [rbx+50h], rsi
0x18001fbe2  mov     rcx, [rbx+58h]
0x18001fbe6  add     dword ptr [rcx+3Ch], 0FFFFFFFFh
0x18001fbea  jnz     short loc_18001FBF3
0x18001fbec  mov     [rcx+40h], rsi
0x18001fbf0  mov     [rcx+48h], esi
0x18001fbf3  add     rcx, 10h; lpCriticalSection
0x18001fbf7  call    cs:__imp_LeaveCriticalSection
0x18001fbfd  mov     eax, 0FFFFFFFFh
0x18001fc02  lock xadd [rbx+8], eax
0x18001fc07  cmp     eax, 1
0x18001fc0a  jz      loc_18001FE82
0x18001fc10  test    rdi, rdi
0x18001fc13  jz      short loc_18001FC55
0x18001fc15  nop     word ptr [rax+rax+00000000h]
0x18001fc20  mov     rbx, [rdi]
0x18001fc23  mov     [rdi], rsi
0x18001fc26  mov     r8, [rdi+18h]
0x18001fc2a  movzx   ecx, byte ptr [rdi+8]
0x18001fc2e  test    ecx, ecx
0x18001fc30  jz      loc_18001FFA3
0x18001fc36  sub     ecx, 1
0x18001fc39  jz      loc_18001FDB0
0x18001fc3f  cmp     ecx, 1
0x18001fc42  jz      short loc_18001FC74
0x18001fc44  mov     rcx, rdi; Block
0x18001fc47  call    cs:__imp_free
0x18001fc4d  mov     rdi, rbx
0x18001fc50  test    rbx, rbx
0x18001fc53  jnz     short loc_18001FC20
0x18001fc55  test    r14d, r14d
0x18001fc58  jnz     loc_18001FFAF
0x18001fc5e  mov     eax, r15d
0x18001fc61  add     rsp, 0A0h
0x18001fc68  pop     r15
0x18001fc6a  pop     r14
0x18001fc6c  pop     r13
0x18001fc6e  pop     r12
0x18001fc70  pop     rdi
0x18001fc71  pop     rsi
0x18001fc72  pop     rbx
0x18001fc73  retn
0x18001fc74  mov     rcx, [rdi+10h]
0x18001fc78  mov     rax, r8
0x18001fc7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc80  jmp     short loc_18001FC44
0x18001fc82  inc     edx
0x18001fc84  jmp     loc_18001FB1E
0x18001fc89  mov     eax, 87B10201h
0x18001fc8e  jmp     short loc_18001FC61
0x18001fc90  cmp     byte ptr [rbx+4Fh], 0
0x18001fc94  jz      loc_18001FA04
0x18001fc9a  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001fca0  call    cs:__imp_TlsGetValue
0x18001fca6  cmp     rax, rbx
0x18001fca9  jnz     loc_18001FA04
0x18001fcaf  xor     esi, esi
0x18001fcb1  jmp     loc_18001FABB
0x18001fcb6  mov     rcx, rsi
0x18001fcb9  test    rdi, rdi
0x18001fcbc  jz      loc_18001FB4A
0x18001fcc2  lea     rax, ?TypeId$@ComImportAdapter@CFlat@@2U?$ObjectTypeIdField@VComImportAdapter@CFlat@@$0A@$0A@@2@B; CFlat::ObjectTypeIdField<CFlat::ComImportAdapter,0,0> const CFlat::ComImportAdapter::TypeId$
0x18001fcc9  cmp     r10, rax
0x18001fccc  jnz     loc_18001FB4A
0x18001fcd2  mov     [rsp+0D8h+var_90], r11
0x18001fcd7  lea     r8, [rsp+0D8h+var_90]
0x18001fcdc  lea     rdx, [rsp+0D8h+var_70]
0x18001fce1  lea     rcx, [rdi+20h]
0x18001fce5  call    ?find@?$_Hash@V?$_Umap_traits@PEBUComInterfaceTypeId@CFlat@@PEAXV?$_Uhash_compare@PEBUComInterfaceTypeId@CFlat@@U?$hash@PEBUComInterfaceTypeId@CFlat@@@std@@U?$equal_to@PEBUComInterfaceTypeId@CFlat@@@4@@std@@V?$Allocator@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@@std@@@std@@@2@AEBQEBUComInterfaceTypeId@CFlat@@@Z; std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::find(CFlat::ComInterfaceTypeId const * const &)
0x18001fcea  mov     rax, [rsp+0D8h+var_70]
0x18001fcef  cmp     rax, [rdi+28h]
0x18001fcf3  jz      loc_18001FDBF
0x18001fcf9  mov     rax, [rax+18h]
0x18001fcfd  lea     rdx, off_1800D0720
0x18001fd04  mov     rcx, rsi
0x18001fd07  test    rax, rax
0x18001fd0a  cmovnz  rcx, rdx
0x18001fd0e  mov     r15d, [rsp+0D8h+arg_0]
0x18001fd16  jmp     loc_18001FB4A
0x18001fd1b  test    r15b, r15b
0x18001fd1e  jz      short loc_18001FD2E
0x18001fd20  mov     rcx, r14; this
0x18001fd23  call    ?Leave@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Leave(void)
0x18001fd28  mov     r14, rsi
0x18001fd2b  xor     r15b, r15b
0x18001fd2e  test    rbx, rbx
0x18001fd31  jnz     loc_18001FA0F
0x18001fd37  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001fd3d  call    cs:__imp_TlsGetValue
0x18001fd43  mov     rdi, rax
0x18001fd46  test    rax, rax
0x18001fd49  jnz     loc_18001FA0F
0x18001fd4f  call    ?NoContext_GetThreadContextOrNullAndLock@Context@Cn@@SAPEAV12@XZ; Cn::Context::NoContext_GetThreadContextOrNullAndLock(void)
0x18001fd54  mov     rdi, rax
0x18001fd57  test    rax, rax
0x18001fd5a  jnz     loc_18001FA0F
0x18001fd60  mov     eax, 87B10101h
0x18001fd65  mov     [rsp+0D8h+arg_0], eax
0x18001fd6c  mov     [rsp+0D8h+var_98], eax
0x18001fd70  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x18001fd77  test    rcx, rcx
0x18001fd7a  jz      short loc_18001FDA3
0x18001fd7c  mov     rax, [rcx]
0x18001fd7f  mov     r8, r12
0x18001fd82  lea     rdx, [rsp+0D8h+var_98]
0x18001fd87  mov     rax, [rax+30h]
0x18001fd8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd90  mov     eax, [rsp+0D8h+var_98]
0x18001fd94  mov     [rsp+0D8h+arg_0], eax
0x18001fd9b  test    eax, eax
0x18001fd9d  jns     loc_18001FA0F
0x18001fda3  mov     r15d, [rsp+0D8h+arg_0]
0x18001fdab  jmp     loc_18001FAC5
0x18001fdb0  mov     rax, [r8]
0x18001fdb3  mov     rax, [rax+10h]
0x18001fdb7  mov     rcx, r8
0x18001fdba  jmp     loc_18001FC7B
0x18001fdbf  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001fdc5  call    cs:__imp_TlsGetValue
0x18001fdcb  mov     r12, rax
0x18001fdce  xor     r8d, r8d; int
0x18001fdd1  mov     rdx, [rdi+18h]; void *
0x18001fdd5  mov     rcx, rax; void *
0x18001fdd8  call    ?ValidateCall@EntryExit@CFlat@@SAPEAXPEAX0H@Z; CFlat::EntryExit::ValidateCall(void *,void *,int)
0x18001fddd  mov     r13, rax
0x18001fde0  mov     rcx, r12; void *
0x18001fde3  call    ?OnBeginCallToNative@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnBeginCallToNative(void *)
0x18001fde8  mov     [rsp+0D8h+var_88], rsi
0x18001fded  mov     [rsp+0D8h+var_98], esi
0x18001fdf1  lea     rax, [rsp+0D8h+var_88]
0x18001fdf6  mov     [rsp+0D8h+var_B8], rax
0x18001fdfb  lea     r9, [rsp+0D8h+var_90]
0x18001fe00  mov     r8, rdi
0x18001fe03  lea     rdx, [rsp+0D8h+var_98]
0x18001fe08  lea     rcx, [rsp+0D8h+var_70]
0x18001fe0d  call    _lambda_9f26dbb50c5457f1a45ef1436d9c8d4d____lambda_9f26dbb50c5457f1a45ef1436d9c8d4d_
0x18001fe12  mov     rdx, rax
0x18001fe15  mov     rcx, r12
0x18001fe18  call    CFlat__SehSafe__Execute__lambda_9f26dbb50c5457f1a45ef1436d9c8d4d___
0x18001fe1d  mov     rdx, r13; void *
0x18001fe20  mov     rcx, r12; this
0x18001fe23  call    ?NoContext_NotifyReturn@Context@Cn@@QEAAXPEAX@Z; Cn::Context::NoContext_NotifyReturn(void *)
0x18001fe28  lea     r8, [rsp+0D8h+var_90]
0x18001fe2d  lea     rdx, [rsp+0D8h+var_70]
0x18001fe32  lea     rcx, [rdi+20h]
0x18001fe36  cmp     [rsp+0D8h+var_98], 80004002h
0x18001fe3e  jz      loc_18001FF60
0x18001fe44  call    ??$_Try_emplace@AEBQEBUComInterfaceTypeId@CFlat@@$$V@?$_Hash@V?$_Umap_traits@PEBUComInterfaceTypeId@CFlat@@PEAXV?$_Uhash_compare@PEBUComInterfaceTypeId@CFlat@@U?$hash@PEBUComInterfaceTypeId@CFlat@@@std@@U?$equal_to@PEBUComInterfaceTypeId@CFlat@@@4@@std@@V?$Allocator@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@PEAX@std@@_N@1@AEBQEBUComInterfaceTypeId@CFlat@@@Z; std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::_Try_emplace<CFlat::ComInterfaceTypeId const * const &,>(CFlat::ComInterfaceTypeId const * const &)
0x18001fe49  mov     r15, [rax]
0x18001fe4c  mov     rcx, r12; void *
0x18001fe4f  cmp     qword ptr [r15+18h], 0
0x18001fe54  jnz     loc_18001FF74
0x18001fe5a  mov     rax, [rsp+0D8h+var_88]
0x18001fe5f  mov     [r15+18h], rax
0x18001fe63  mov     r8, rdi; struct CFlat::ComImportAdapter *
0x18001fe66  mov     rdx, [rsp+0D8h+var_88]; void *
0x18001fe6b  call    ?AddCachedComImportAdapter@EntryExit@CFlat@@SAXPEAX0PEAVComImportAdapter@2@@Z; CFlat::EntryExit::AddCachedComImportAdapter(void *,void *,CFlat::ComImportAdapter *)
0x18001fe70  mov     rax, [r15+18h]
0x18001fe74  jmp     loc_18001FCFD
0x18001fe79  mov     rdx, r12; void *
  ... truncated ...
```
