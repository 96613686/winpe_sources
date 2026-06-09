# CloudStore_CreateInstance(Windows::Internal::Storage::Cloud::CloudStoreOptions,Windows::System::IUser *,Windows::Security::Credentials::IWebAccount *,ushort const *,Windows::Internal::Storage::Cloud::WaitTimes const &,_GUID const &,void * *)

- ea: `0x18002f814`
- end: `0x18002ff93`
- name: `?CloudStore_CreateInstance@@YAJW4CloudStoreOptions@Cloud@Storage@Internal@Windows@@PEAUIUser@System@5@PEAUIWebAccount@Credentials@Security@5@PEBGAEBUWaitTimes@2345@AEBU_GUID@@PEAPEAX@Z`
- size: `1919`
- prototype: `__int64 __fastcall(char, __int64, __int64, _WORD *, struct Windows::Internal::Storage::Cloud::WaitTimes *, __int64, void **)`
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000eb40`
- `0x18000ee20`

## callees

- `0x18001582c`
- `0x180016cf4`
- `0x1800238d0`
- `0x180024fd0`
- `0x1800250e0`
- `0x180025508`
- `0x18002e010`
- `0x18002ec7c`
- `0x18002f814`
- `0x180031134`
- `0x1800311a0`
- `0x18003137c`
- `0x180031798`
- `0x1800322f8`
- `0x180032964`
- `0x180032b48`
- `0x180042e50`
- `0x180062040`
- `0x180063c4c`
- `0x1800d1d50`
- `0x1800d6e40`
- `0x1800e93e0`
- `0x1800f9bbc`
- `0x1801201a0`
- `0x180123882`
- `0x1801afa28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff5c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002ff1b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002ff1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f90e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f91c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002feb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f90e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f91c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002feb2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002ff6e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002ff6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fcaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fcaf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f968`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f968`

## pseudocode

```c
__int64 __fastcall CloudStore_CreateInstance(
        char a1,
        __int64 a2,
        __int64 a3,
        _WORD *a4,
        struct Windows::Internal::Storage::Cloud::WaitTimes *a5,
        __int64 a6,
        void **a7)
{
  bool v10; // di
  int v11; // ebx
  int v12; // r14d
  int v13; // r12d
  CloudStoreUtilities *v14; // rcx
  int v15; // eax
  __int64 v16; // r8
  const char *v17; // r9
  HANDLE v18; // rbx
  const char *v19; // r9
  signed int Error; // ebx
  char *v21; // rcx
  char *v22; // rax
  int v23; // ebx
  __int64 v24; // rcx
  LPVOID *v25; // r14
  __int64 v26; // rdi
  __int64 v27; // rcx
  __int64 v28; // r15
  __int64 v29; // rsi
  const unsigned __int16 *v30; // r12
  __int128 *v31; // rdi
  int v32; // ebx
  __int64 v33; // rax
  __int64 v34; // rax
  _QWORD *v35; // rsi
  unsigned __int64 v36; // r14
  int Instance; // eax
  const char *v38; // r9
  __int64 result; // rax
  __int64 v40; // r15
  HANDLE CurrentProcess; // rax
  unsigned __int16 **v42; // r8
  int PackageFamilyNameFromProcess; // eax
  int v44; // eax
  signed int LastError; // eax
  int ReturnLength; // [rsp+20h] [rbp-1C8h]
  int ReturnLengtha; // [rsp+20h] [rbp-1C8h]
  int TokenInformation; // [rsp+30h] [rbp-1B8h] BYREF
  DWORD v49; // [rsp+34h] [rbp-1B4h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-1B0h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-1A8h] BYREF
  LPVOID *p_pv; // [rsp+48h] [rbp-1A0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-198h] BYREF
  __int64 v54; // [rsp+58h] [rbp-190h]
  __int64 v55; // [rsp+60h] [rbp-188h]
  void **v56; // [rsp+68h] [rbp-180h]
  char v57[32]; // [rsp+70h] [rbp-178h] BYREF
  _BYTE v58[32]; // [rsp+90h] [rbp-158h] BYREF
  _QWORD v59[4]; // [rsp+B0h] [rbp-138h] BYREF
  __int128 v60; // [rsp+D0h] [rbp-118h] BYREF
  __int128 v61; // [rsp+E0h] [rbp-108h]
  __int64 v62; // [rsp+F0h] [rbp-F8h]
  std::_Ref_count_base *v63; // [rsp+F8h] [rbp-F0h]
  __int128 v64; // [rsp+100h] [rbp-E8h] BYREF
  __int128 v65; // [rsp+110h] [rbp-D8h]
  _BYTE v66[32]; // [rsp+120h] [rbp-C8h] BYREF
  __int64 v67; // [rsp+140h] [rbp-A8h] BYREF
  std::_Ref_count_base *v68; // [rsp+148h] [rbp-A0h]
  __int128 v69; // [rsp+150h] [rbp-98h] BYREF
  __int128 v70; // [rsp+160h] [rbp-88h]
  _BYTE v71[32]; // [rsp+170h] [rbp-78h] BYREF
  __int64 v72; // [rsp+190h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  try
  {
    v56 = a7;
    v10 = 0;
    v11 = 0;
    TokenInformation = 0;
    *a7 = 0;
    v12 = a1 & 1;
    if ( v12 != (a2 == 0) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x179C,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)retaddr);
    v13 = a1 & 2;
    if ( (v13 != 0) != (a3 == 0) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x179D,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)retaddr);
    if ( (a1 & 8) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x179E,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)retaddr);
    pv = 0;
    if ( !a4 || !*a4 )
    {
      if ( (a1 & 4) != 0 )
      {
        p_pv = &pv;
        v53 = 0;
        LOBYTE(v54) = 1;
        CurrentProcess = GetCurrentProcess();
        PackageFamilyNameFromProcess = CallerIdentity::GetPackageFamilyNameFromProcess(CurrentProcess, &v53, v42);
        if ( PackageFamilyNameFromProcess < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x17A7,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
            (const char *)(unsigned int)PackageFamilyNameFromProcess,
            ReturnLength);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pv);
      }
      else if ( UseCloudStoreOnActivityFeed::IsEnabled() )
      {
        v15 = CloudStoreUtilities::VerifyStoreAccessPermissions(v14);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x17B0,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
            (const char *)(unsigned int)v15,
            ReturnLength);
      }
      else
      {
        v44 = CloudStoreUtilities::VerifyStoreAccessPermissions(v14);
        if ( v44 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x17B5,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
            (const char *)(unsigned int)v44,
            ReturnLength);
      }
LABEL_24:
      if ( v12 )
      {
        v22 = (char *)EffectiveUserContext::CreateForCurrentUser(v58);
        v23 = v11 | 1;
      }
      else
      {
        v22 = EffectiveUserContext::CreateForUser(v57, a2, v16, v17);
        v23 = v11 | 2;
      }
      TokenInformation = v23;
      v24 = *((_QWORD *)v22 + 1);
      if ( v24 )
        _InterlockedIncrement((volatile signed __int32 *)(v24 + 8));
      v25 = *(LPVOID **)v22;
      p_pv = *(LPVOID **)v22;
      v26 = *((_QWORD *)v22 + 1);
      v53 = v26;
      v27 = *((_QWORD *)v22 + 3);
      if ( v27 )
        _InterlockedIncrement((volatile signed __int32 *)(v27 + 8));
      v28 = *((_QWORD *)v22 + 2);
      v54 = v28;
      v29 = *((_QWORD *)v22 + 3);
      v55 = v29;
      if ( (v23 & 2) != 0 )
      {
        v23 &= ~2u;
        TokenInformation = v23;
        EffectiveUserContext::~EffectiveUserContext((EffectiveUserContext *)v57);
      }
      if ( (v23 & 1) != 0 )
      {
        v23 &= ~1u;
        TokenInformation = v23;
        EffectiveUserContext::~EffectiveUserContext((EffectiveUserContext *)v58);
      }
      if ( v13 )
      {
        v64 = 0;
        if ( v26 )
          _InterlockedIncrement((volatile signed __int32 *)(v26 + 8));
        *(_QWORD *)&v64 = v25;
        *((_QWORD *)&v64 + 1) = v26;
        v65 = 0;
        if ( v29 )
          _InterlockedIncrement((volatile signed __int32 *)(v29 + 8));
        *(_QWORD *)&v65 = v28;
        *((_QWORD *)&v65 + 1) = v29;
        v30 = &LocaleName;
        std::wstring::wstring(v66);
        std::make_shared<EffectiveWebAccountContext::State,>(&v67);
        *(_DWORD *)(v67 + 52) = 1;
        v31 = &v64;
        v32 = v23 | 0x44;
      }
      else
      {
        v69 = 0;
        if ( v26 )
          _InterlockedIncrement((volatile signed __int32 *)(v26 + 8));
        *(_QWORD *)&v69 = v25;
        *((_QWORD *)&v69 + 1) = v26;
        v70 = 0;
        if ( v29 )
          _InterlockedIncrement((volatile signed __int32 *)(v29 + 8));
        *(_QWORD *)&v70 = v28;
        *((_QWORD *)&v70 + 1) = v29;
        v30 = &LocaleName;
        std::wstring::wstring(v71);
        std::make_shared<EffectiveWebAccountContext::State,>(&v72);
        wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::operator=(v72 + 8, a3);
        v31 = &v69;
        v32 = v23 | 0x88;
      }
      TokenInformation = v32;
      v33 = *((_QWORD *)v31 + 1);
      if ( v33 )
        _InterlockedIncrement((volatile signed __int32 *)(v33 + 8));
      v59[0] = *(_QWORD *)v31;
      v59[1] = *((_QWORD *)v31 + 1);
      v34 = *((_QWORD *)v31 + 3);
      if ( v34 )
        _InterlockedIncrement((volatile signed __int32 *)(v34 + 8));
      v59[2] = *((_QWORD *)v31 + 2);
      v59[3] = *((_QWORD *)v31 + 3);
      v35 = v31 + 2;
      v60 = 0;
      v61 = 0;
      v36 = *((_QWORD *)v31 + 6);
      if ( *((_QWORD *)v31 + 7) > 7u )
        v35 = (_QWORD *)*v35;
      if ( v36 > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlength_error("string too long");
      if ( v36 > 7 )
      {
        v40 = std::wstring::_Calculate_growth(*((_QWORD *)v31 + 6));
        if ( (unsigned __int64)(v40 + 1) > 0x7FFFFFFFFFFFFFFFLL )
          std::_Throw_bad_array_new_length();
        *(_QWORD *)&v60 = std::_Allocate<16,std::_Default_allocate_traits>(2 * (v40 + 1));
        *(_QWORD *)&v61 = v36;
        *((_QWORD *)&v61 + 1) = v40;
        memcpy_0((void *)v60, v35, 2 * v36 + 2);
      }
      else
      {
        *(_QWORD *)&v61 = *((_QWORD *)v31 + 6);
        *((_QWORD *)&v61 + 1) = 7;
        v60 = *(_OWORD *)v35;
      }
      v62 = *((_QWORD *)v31 + 8);
      v63 = (std::_Ref_count_base *)*((_QWORD *)v31 + 9);
      *((_QWORD *)v31 + 8) = 0;
      *((_QWORD *)v31 + 9) = 0;
      if ( (v32 & 8) != 0 )
      {
        LOBYTE(v32) = v32 & 0xF7;
        EffectiveWebAccountContext::~EffectiveWebAccountContext((EffectiveWebAccountContext *)&v69);
      }
      if ( (v32 & 4) != 0 )
      {
        if ( v68 )
          std::_Ref_count_base::_Decref(v68);
        std::wstring::~wstring(v66);
        EffectiveUserContext::~EffectiveUserContext((EffectiveUserContext *)&v64);
      }
      if ( pv )
        v30 = (const unsigned __int16 *)pv;
      Instance = CloudStore_CreateInstance(
                   (const struct EffectiveUserContext *)&p_pv,
                   (const struct EffectiveWebAccountContext *)v59,
                   v30,
                   a5,
                   &GUID_880ef12d_8696_41da_b117_28494bad244c,
                   v56);
      if ( Instance < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x17D7,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)(unsigned int)Instance,
          ReturnLengtha);
      if ( v63 )
        std::_Ref_count_base::_Decref(v63);
      std::wstring::~wstring(&v60);
      EffectiveUserContext::~EffectiveUserContext((EffectiveUserContext *)v59);
      EffectiveUserContext::~EffectiveUserContext((EffectiveUserContext *)&p_pv);
      if ( pv )
        CoTaskMemFree(pv);
      return 0;
    }
    if ( (a1 & 4) == 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x17BD,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)retaddr);
    v18 = GetCurrentProcess();
    TokenHandle = 0;
    if ( v18 == GetCurrentProcess() )
    {
      TokenHandle = (HANDLE)-4LL;
    }
    else if ( !OpenProcessToken(v18, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      Error = LastError;
      if ( LastError > 0 )
        Error = (unsigned __int16)LastError | 0x80070000;
LABEL_15:
      if ( Error >= 0 )
      {
        v49 = 0;
        TokenInformation = 0;
        if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &v49) )
        {
          Error = 0;
        }
        else
        {
          Error = ResultFromKnownLastError();
          if ( Error < 0 )
            goto LABEL_19;
        }
        v10 = TokenInformation != 0;
      }
LABEL_19:
      v21 = (char *)TokenHandle;
      TokenHandle = 0;
      if ( (unsigned __int64)(v21 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v21);
      if ( Error < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x17C2,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)(unsigned int)Error,
          ReturnLength);
      if ( v10 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x17C3,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          v19);
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &TokenHandle,
        a4);
      v11 = 16;
      TokenInformation = 16;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pv,
        TokenHandle);
      goto LABEL_24;
    }
    Error = 0;
    goto LABEL_15;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x17DA,
                           (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                           v38);
  }
  return result;
}

```

## disassembly

```asm
0x18002f814  push    rbx
0x18002f816  push    rsi
0x18002f817  push    rdi
0x18002f818  push    r12
0x18002f81a  push    r13
0x18002f81c  push    r14
0x18002f81e  push    r15
0x18002f820  sub     rsp, 1B0h
0x18002f827  mov     rax, cs:__security_cookie
0x18002f82e  xor     rax, rsp
0x18002f831  mov     [rsp+1E8h+var_48], rax
0x18002f839  mov     rsi, r9
0x18002f83c  mov     r13, r8
0x18002f83f  mov     r15, rdx
0x18002f842  mov     rax, [rsp+1E8h+arg_30]
0x18002f84a  mov     [rsp+1E8h+var_180], rax
0x18002f84f  xor     edi, edi
0x18002f851  mov     ebx, edi
0x18002f853  mov     [rsp+1E8h+TokenInformation], ebx
0x18002f857  mov     [rax], rdi
0x18002f85a  mov     r14d, ecx
0x18002f85d  and     r14d, 1
0x18002f861  mov     r9, [rsp+1E8h]; char *
0x18002f869  mov     eax, edi
0x18002f86b  test    rdx, rdx
0x18002f86e  setz    al
0x18002f871  cmp     r14d, eax
0x18002f874  jnz     loc_18002FD9B
0x18002f87a  mov     r12d, ecx
0x18002f87d  mov     r9, [rsp+1E8h]; char *
0x18002f885  mov     edx, edi
0x18002f887  test    r8, r8
0x18002f88a  setz    dl
0x18002f88d  mov     eax, edi
0x18002f88f  and     r12d, 2
0x18002f893  setnz   al
0x18002f896  cmp     eax, edx
0x18002f898  jnz     loc_18002FDB0
0x18002f89e  mov     rax, [rsp+1E8h]
0x18002f8a6  test    cl, 8
0x18002f8a9  jnz     loc_18002FDC5
0x18002f8af  mov     [rsp+1E8h+pv], rdi
0x18002f8b4  test    rsi, rsi
0x18002f8b7  jz      short loc_18002F8BE
0x18002f8b9  cmp     [rsi], di
0x18002f8bc  jnz     short loc_18002F8FD
0x18002f8be  test    cl, 4
0x18002f8c1  jnz     loc_18002FE9E
0x18002f8c7  call    ?IsEnabled@UseCloudStoreOnActivityFeed@@SA_NXZ; UseCloudStoreOnActivityFeed::IsEnabled(void)
0x18002f8cc  test    al, al
0x18002f8ce  jz      loc_18002FEE0
0x18002f8d4  call    ?VerifyStoreAccessPermissions@CloudStoreUtilities@@YAJXZ; CloudStoreUtilities::VerifyStoreAccessPermissions(void)
0x18002f8d9  mov     rcx, [rsp+1E8h]; this
0x18002f8e1  test    eax, eax
0x18002f8e3  jns     loc_18002F9E3
0x18002f8e9  mov     r9d, eax; char *
0x18002f8ec  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18002f8f3  mov     edx, 17B0h; void *
0x18002f8f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002f8fd  and     ecx, 4
0x18002f900  mov     rcx, [rsp+1E8h]; this
0x18002f908  jz      loc_18002FE12
0x18002f90e  call    cs:__imp_GetCurrentProcess
0x18002f914  mov     rbx, rax
0x18002f917  mov     [rsp+1E8h+TokenHandle], rdi
0x18002f91c  call    cs:__imp_GetCurrentProcess
0x18002f922  cmp     rbx, rax
0x18002f925  jnz     loc_18002FF0E
0x18002f92b  mov     [rsp+1E8h+TokenHandle], 0FFFFFFFFFFFFFFFCh
0x18002f934  mov     ebx, edi
0x18002f936  test    ebx, ebx
0x18002f938  js      short loc_18002F981
0x18002f93a  mov     [rsp+1E8h+var_1B4], 0
0x18002f942  mov     [rsp+1E8h+TokenInformation], 0
0x18002f94a  lea     rax, [rsp+1E8h+var_1B4]
0x18002f94f  mov     [rsp+1E8h+ReturnLength], rax; int
0x18002f954  mov     r9d, 4; TokenInformationLength
0x18002f95a  lea     r8, [rsp+1E8h+TokenInformation]; TokenInformation
0x18002f95f  lea     edx, [r9+19h]; TokenInformationClass
0x18002f963  mov     rcx, [rsp+1E8h+TokenHandle]; TokenHandle
0x18002f968  call    cs:__imp_GetTokenInformation
0x18002f96e  test    eax, eax
0x18002f970  jz      loc_18002FE4B
0x18002f976  xor     ebx, ebx
0x18002f978  cmp     [rsp+1E8h+TokenInformation], 0
0x18002f97d  setnz   dil
0x18002f981  mov     rcx, [rsp+1E8h+TokenHandle]; hObject
0x18002f986  mov     [rsp+1E8h+TokenHandle], 0
0x18002f98f  lea     rax, [rcx-1]
0x18002f993  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f997  jbe     loc_18002FF5C
0x18002f99d  mov     rcx, [rsp+1E8h]; this
0x18002f9a5  test    ebx, ebx
0x18002f9a7  js      loc_18002FE8A
0x18002f9ad  mov     rcx, [rsp+1E8h]; this
0x18002f9b5  test    dil, dil
0x18002f9b8  jnz     loc_18002FE24
0x18002f9be  mov     rdx, rsi
0x18002f9c1  lea     rcx, [rsp+1E8h+TokenHandle]
0x18002f9c6  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002f9cb  mov     ebx, 10h
0x18002f9d0  mov     [rsp+1E8h+TokenInformation], ebx
0x18002f9d4  mov     rdx, [rsp+1E8h+TokenHandle]
0x18002f9d9  lea     rcx, [rsp+1E8h+pv]
0x18002f9de  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002f9e3  test    r14d, r14d
0x18002f9e6  jz      loc_18002FE36
0x18002f9ec  lea     rcx, [rsp+1E8h+var_158]
0x18002f9f4  call    ?CreateForCurrentUser@EffectiveUserContext@@SA?AV1@_N@Z; EffectiveUserContext::CreateForCurrentUser(bool)
0x18002f9f9  nop
0x18002f9fa  or      ebx, 1
0x18002f9fd  mov     [rsp+1E8h+TokenInformation], ebx
0x18002fa01  mov     rcx, [rax+8]
0x18002fa05  test    rcx, rcx
0x18002fa08  jz      short loc_18002FA0E
0x18002fa0a  lock inc dword ptr [rcx+8]
0x18002fa0e  mov     r14, [rax]
0x18002fa11  mov     [rsp+1E8h+var_1A0], r14
0x18002fa16  mov     rdi, [rax+8]
0x18002fa1a  mov     [rsp+1E8h+var_198], rdi
0x18002fa1f  mov     rcx, [rax+18h]
0x18002fa23  test    rcx, rcx
0x18002fa26  jz      short loc_18002FA2C
0x18002fa28  lock inc dword ptr [rcx+8]
0x18002fa2c  mov     r15, [rax+10h]
0x18002fa30  mov     [rsp+1E8h+var_190], r15
0x18002fa35  mov     rsi, [rax+18h]
0x18002fa39  mov     [rsp+1E8h+var_188], rsi
0x18002fa3e  test    bl, 2
0x18002fa41  jnz     loc_18002FE74
0x18002fa47  test    bl, 1
0x18002fa4a  jz      short loc_18002FA60
0x18002fa4c  and     ebx, 0FFFFFFFEh
0x18002fa4f  mov     [rsp+1E8h+TokenInformation], ebx
0x18002fa53  lea     rcx, [rsp+1E8h+var_158]; this
0x18002fa5b  call    ??1EffectiveUserContext@@QEAA@XZ; EffectiveUserContext::~EffectiveUserContext(void)
0x18002fa60  mov     rax, [rsp+1E8h+pv]
0x18002fa65  xorps   xmm0, xmm0
0x18002fa68  test    r12d, r12d
0x18002fa6b  jz      loc_18002FD02
0x18002fa71  movdqa  [rsp+1E8h+var_E8], xmm0
0x18002fa7a  test    rdi, rdi
0x18002fa7d  jz      short loc_18002FA83
0x18002fa7f  lock inc dword ptr [rdi+8]
0x18002fa83  mov     qword ptr [rsp+1E8h+var_E8], r14
0x18002fa8b  mov     qword ptr [rsp+1E8h+var_E8+8], rdi
0x18002fa93  movdqa  [rsp+1E8h+var_D8], xmm0
0x18002fa9c  test    rsi, rsi
0x18002fa9f  jz      short loc_18002FAA5
0x18002faa1  lock inc dword ptr [rsi+8]
0x18002faa5  mov     qword ptr [rsp+1E8h+var_D8], r15
0x18002faad  mov     qword ptr [rsp+1E8h+var_D8+8], rsi
0x18002fab5  lea     r12, LocaleName
0x18002fabc  mov     rdx, r12
0x18002fabf  test    rax, rax
0x18002fac2  cmovnz  rdx, rax
0x18002fac6  lea     rcx, [rsp+1E8h+var_C8]
0x18002face  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002fad3  nop
0x18002fad4  lea     rcx, [rsp+1E8h+var_A8]
0x18002fadc  call    ??$make_shared@UState@EffectiveWebAccountContext@@$$V@std@@YA?AV?$shared_ptr@UState@EffectiveWebAccountContext@@@0@XZ; std::make_shared<EffectiveWebAccountContext::State,>(void)
0x18002fae1  nop
0x18002fae2  or      ebx, 40h
0x18002fae5  mov     rax, [rsp+1E8h+var_A8]
0x18002faed  mov     dword ptr [rax+34h], 1
0x18002faf4  lea     rdi, [rsp+1E8h+var_E8]
0x18002fafc  or      ebx, 4
0x18002faff  mov     [rsp+1E8h+TokenInformation], ebx
0x18002fb03  mov     rax, [rdi+8]
0x18002fb07  test    rax, rax
0x18002fb0a  jz      short loc_18002FB10
0x18002fb0c  lock inc dword ptr [rax+8]
0x18002fb10  mov     rax, [rdi]
0x18002fb13  mov     [rsp+1E8h+var_138], rax
0x18002fb1b  mov     rax, [rdi+8]
0x18002fb1f  mov     [rsp+1E8h+var_130], rax
0x18002fb27  mov     rax, [rdi+18h]
0x18002fb2b  test    rax, rax
0x18002fb2e  jz      short loc_18002FB34
0x18002fb30  lock inc dword ptr [rax+8]
0x18002fb34  mov     rax, [rdi+10h]
0x18002fb38  mov     [rsp+1E8h+var_128], rax
0x18002fb40  mov     rax, [rdi+18h]
0x18002fb44  mov     [rsp+1E8h+var_120], rax
0x18002fb4c  lea     rsi, [rdi+20h]
0x18002fb50  xorps   xmm0, xmm0
0x18002fb53  movups  [rsp+1E8h+var_118], xmm0
0x18002fb5b  xorps   xmm1, xmm1
0x18002fb5e  movdqa  [rsp+1E8h+var_108], xmm1
0x18002fb67  mov     r14, [rsi+10h]
0x18002fb6b  mov     edx, 7
0x18002fb70  cmp     [rsi+18h], rdx
0x18002fb74  jbe     short loc_18002FB79
0x18002fb76  mov     rsi, [rsi]
0x18002fb79  mov     r8, 7FFFFFFFFFFFFFFEh
0x18002fb83  cmp     r14, r8
0x18002fb86  ja      loc_18002FF67
0x18002fb8c  cmp     r14, rdx
0x18002fb8f  ja      loc_18002FCDA
0x18002fb95  mov     qword ptr [rsp+1E8h+var_108], r14
0x18002fb9d  mov     qword ptr [rsp+1E8h+var_108+8], rdx
0x18002fba5  mov     rax, [rsi]
0x18002fba8  mov     qword ptr [rsp+1E8h+var_118], rax
0x18002fbb0  mov     rax, [rsi+8]
0x18002fbb4  mov     qword ptr [rsp+1E8h+var_118+8], rax
0x18002fbbc  mov     rax, [rdi+40h]
0x18002fbc0  mov     [rsp+1E8h+var_F8], rax
0x18002fbc8  mov     rax, [rdi+48h]
0x18002fbcc  mov     [rsp+1E8h+var_F0], rax
0x18002fbd4  mov     qword ptr [rdi+40h], 0
0x18002fbdc  mov     qword ptr [rdi+48h], 0
0x18002fbe4  test    bl, 8
0x18002fbe7  jnz     loc_18002FF75
0x18002fbed  test    bl, 4
0x18002fbf0  jz      short loc_18002FC1E
0x18002fbf2  mov     rcx, [rsp+1E8h+var_A0]; this
0x18002fbfa  test    rcx, rcx
0x18002fbfd  jz      short loc_18002FC04
0x18002fbff  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002fc04  lea     rcx, [rsp+1E8h+var_C8]
0x18002fc0c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002fc11  lea     rcx, [rsp+1E8h+var_E8]; this
0x18002fc19  call    ??1EffectiveUserContext@@QEAA@XZ; EffectiveUserContext::~EffectiveUserContext(void)
0x18002fc1e  mov     rax, [rsp+1E8h+pv]
0x18002fc23  test    rax, rax
0x18002fc26  cmovnz  r12, rax
0x18002fc2a  mov     rax, [rsp+1E8h+var_180]
0x18002fc2f  mov     [rsp+1E8h+var_1C0], rax; void **
0x18002fc34  lea     rax, _GUID_880ef12d_8696_41da_b117_28494bad244c
0x18002fc3b  mov     [rsp+1E8h+ReturnLength], rax; int
0x18002fc40  mov     r9, [rsp+1E8h+arg_20]; struct Windows::Internal::Storage::Cloud::WaitTimes *
0x18002fc48  mov     r8, r12; unsigned __int16 *
0x18002fc4b  lea     rdx, [rsp+1E8h+var_138]; struct EffectiveWebAccountContext *
0x18002fc53  lea     rcx, [rsp+1E8h+var_1A0]; struct EffectiveUserContext *
0x18002fc58  call    ?CloudStore_CreateInstance@@YAJAEBVEffectiveUserContext@@AEBVEffectiveWebAccountContext@@PEBGAEBUWaitTimes@Cloud@Storage@Internal@Windows@@AEBU_GUID@@PEAPEAX@Z; CloudStore_CreateInstance(EffectiveUserContext const &,EffectiveWebAccountContext const &,ushort const *,Windows::Internal::Storage::Cloud::WaitTimes const &,_GUID const &,void * *)
0x18002fc5d  mov     rcx, [rsp+1E8h]; this
0x18002fc65  test    eax, eax
0x18002fc67  js      loc_18002FE5F
0x18002fc6d  mov     rcx, [rsp+1E8h+var_F0]; this
0x18002fc75  test    rcx, rcx
0x18002fc78  jz      short loc_18002FC7F
0x18002fc7a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002fc7f  lea     rcx, [rsp+1E8h+var_118]
0x18002fc87  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002fc8c  lea     rcx, [rsp+1E8h+var_138]; this
0x18002fc94  call    ??1EffectiveUserContext@@QEAA@XZ; EffectiveUserContext::~EffectiveUserContext(void)
0x18002fc99  nop
0x18002fc9a  lea     rcx, [rsp+1E8h+var_1A0]; this
0x18002fc9f  call    ??1EffectiveUserContext@@QEAA@XZ; EffectiveUserContext::~EffectiveUserContext(void)
0x18002fca4  nop
0x18002fca5  mov     rcx, [rsp+1E8h+pv]; pv
0x18002fcaa  test    rcx, rcx
0x18002fcad  jz      short loc_18002FCB5
0x18002fcaf  call    cs:__imp_CoTaskMemFree
0x18002fcb5  xor     eax, eax
0x18002fcb7  mov     rcx, [rsp+1E8h+var_48]
0x18002fcbf  xor     rcx, rsp; StackCookie
0x18002fcc2  call    __security_check_cookie
0x18002fcc7  add     rsp, 1B0h
0x18002fcce  pop     r15
0x18002fcd0  pop     r14
0x18002fcd2  pop     r13
0x18002fcd4  pop     r12
0x18002fcd6  pop     rdi
0x18002fcd7  pop     rsi
0x18002fcd8  pop     rbx
0x18002fcd9  retn
0x18002fcda  mov     rcx, r14
0x18002fcdd  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18002fce2  mov     r15, rax
0x18002fce5  lea     rcx, [rax+1]
0x18002fce9  mov     rax, 7FFFFFFFFFFFFFFFh
0x18002fcf3  cmp     rcx, rax
0x18002fcf6  jbe     loc_18002FDDA
0x18002fcfc  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18002fd02  movdqa  [rsp+1E8h+var_98], xmm0
0x18002fd0b  test    rdi, rdi
0x18002fd0e  jz      short loc_18002FD14
0x18002fd10  lock inc dword ptr [rdi+8]
0x18002fd14  mov     qword ptr [rsp+1E8h+var_98], r14
0x18002fd1c  mov     qword ptr [rsp+1E8h+var_98+8], rdi
0x18002fd24  movdqa  [rsp+1E8h+var_88], xmm0
0x18002fd2d  test    rsi, rsi
0x18002fd30  jz      short loc_18002FD36
0x18002fd32  lock inc dword ptr [rsi+8]
0x18002fd36  mov     qword ptr [rsp+1E8h+var_88], r15
0x18002fd3e  mov     qword ptr [rsp+1E8h+var_88+8], rsi
0x18002fd46  lea     r12, LocaleName
0x18002fd4d  mov     rdx, r12
0x18002fd50  test    rax, rax
0x18002fd53  cmovnz  rdx, rax
0x18002fd57  lea     rcx, [rsp+1E8h+var_78]
0x18002fd5f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002fd64  nop
0x18002fd65  lea     rcx, [rsp+1E8h+var_58]
0x18002fd6d  call    ??$make_shared@UState@EffectiveWebAccountContext@@$$V@std@@YA?AV?$shared_ptr@UState@EffectiveWebAccountContext@@@0@XZ; std::make_shared<EffectiveWebAccountContext::State,>(void)
0x18002fd72  nop
0x18002fd73  bts     ebx, 7
0x18002fd77  mov     rcx, [rsp+1E8h+var_58]
0x18002fd7f  add     rcx, 8
  ... truncated ...
```
