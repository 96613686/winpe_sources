# LanguageManager::_RegisterProgressEventHandler(ILanguagePackProgressEventHandler *,ILanguageFeatureProgressEventHandler *)

- ea: `0x180033418`
- end: `0x1800338df`
- name: `?_RegisterProgressEventHandler@LanguageManager@@CAIPEAUILanguagePackProgressEventHandler@@PEAUILanguageFeatureProgressEventHandler@@@Z`
- size: `1223`
- prototype: `__int64 __fastcall(IUnknown *pProxy, IUnknown *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f990`
- `0x18002f9e0`

## callees

- `0x180003a00`
- `0x180005db4`
- `0x180012a98`
- `0x1800137bc`
- `0x180014ed0`
- `0x18002c4d8`
- `0x18002d4c0`
- `0x180031a2c`
- `0x180033374`
- `0x180033418`
- `0x1800362a0`
- `0x180060070`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800337ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800337ef`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800334e8`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180033519`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800335b4`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800335e5`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800334e8`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180033519`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800335b4`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800335e5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003352b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800335f7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003352b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800335f7`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800334b2`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003357e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800334b2`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003357e`
- `msvcp_win!_Mtx_unlock` at `0x180033799`
- `msvcp_win!_Mtx_unlock` at `0x180033799`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180033731`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180033752`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180033731`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180033752`
- `msvcp_win!_Mtx_lock` at `0x180033724`
- `msvcp_win!_Mtx_lock` at `0x180033724`

## string_xrefs

- `0x180033822`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagemanager.cpp`
- `0x18003383a`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagemanager.cpp`
- `0x18003384f`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagemanager.cpp`
- `0x180033864`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagemanager.cpp`
- `0x180033879`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagemanager.cpp`
- `0x18003388e`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagemanager.cpp`
- `0x1800338a3`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagemanager.cpp`
- `0x1800338b8`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagemanager.cpp`
- `0x1800338cd`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LanguageManager::_RegisterProgressEventHandler(IUnknown *pProxy, IUnknown *a2)
{
  char v4; // al
  int v5; // eax
  HRESULT v6; // eax
  HRESULT v7; // eax
  HRESULT v8; // eax
  IUnknown *v9; // rcx
  int v10; // eax
  HRESULT v11; // eax
  HRESULT v12; // eax
  HRESULT v13; // eax
  IUnknown *v14; // rcx
  unsigned __int32 v15; // r14d
  IUnknown *v16; // rdi
  char *v17; // r15
  _QWORD *UserSidString; // rax
  __int64 v19; // r8
  void *v20; // rbx
  __int64 v21; // rcx
  IUnknown **v22; // rdx
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-49h]
  DWORD dwAuthnLevela; // [rsp+20h] [rbp-49h]
  DWORD dwAuthnLevelb; // [rsp+20h] [rbp-49h]
  DWORD dwAuthnLevelc; // [rsp+20h] [rbp-49h]
  IUnknown *v28; // [rsp+48h] [rbp-21h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v30[32]; // [rsp+58h] [rbp-11h] BYREF
  IUnknown *pProxya; // [rsp+78h] [rbp+Fh] BYREF
  void *v32; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  LODWORD(pProxya) = 0;
  if ( pProxy || (v4 = 0, a2) )
    v4 = 1;
  if ( !v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
      (const char *)0x80004003LL,
      dwAuthnLevel);
  LanguageManager::_EnsureTrustedCaller();
  if ( pProxy )
  {
    pProxya = 0;
    v5 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))pProxy->lpVtbl->QueryInterface)(
           pProxy,
           &GUID_00000000_0000_0000_c000_000000000046,
           &pProxya);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C7,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
        (const char *)(unsigned int)v5,
        dwAuthnLevel);
    v6 = CoImpersonateClient();
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C9,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
        (const char *)(unsigned int)v6,
        dwAuthnLevel);
    v7 = CoSetProxyBlanket(pProxya, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 2u, 0, 0x20u);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D4,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
        (const char *)(unsigned int)v7,
        dwAuthnLevela);
    v8 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 2u, 0, 0x20u);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1DE,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
        (const char *)(unsigned int)v8,
        dwAuthnLevel);
    CoRevertToSelf();
    v9 = pProxya;
    if ( pProxya )
    {
      pProxya = 0;
      ((void (__fastcall *)(IUnknown *))v9->lpVtbl->Release)(v9);
    }
  }
  if ( a2 )
  {
    pProxya = 0;
    v10 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_00000000_0000_0000_c000_000000000046,
            &pProxya);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C7,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
        (const char *)(unsigned int)v10,
        dwAuthnLevel);
    v11 = CoImpersonateClient();
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C9,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
        (const char *)(unsigned int)v11,
        dwAuthnLevel);
    v12 = CoSetProxyBlanket(pProxya, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 2u, 0, 0x20u);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D4,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
        (const char *)(unsigned int)v12,
        dwAuthnLevelb);
    v13 = CoSetProxyBlanket(a2, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 2u, 0, 0x20u);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1DE,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
        (const char *)(unsigned int)v13,
        dwAuthnLevelc);
    CoRevertToSelf();
    v14 = pProxya;
    if ( pProxya )
    {
      pProxya = 0;
      ((void (__fastcall *)(IUnknown *))v14->lpVtbl->Release)(v14);
    }
  }
  GetCallerTokenHandleForIdentification((__int64)&hObject);
  v15 = _InterlockedIncrement((volatile signed __int32 *)&LanguageManager::s_nextEventRegistrationCookie);
  v16 = (IUnknown *)operator new(0x38u);
  v28 = v16;
  v17 = (char *)hObject;
  UserSidString = (_QWORD *)GetUserSidString(v30, hObject);
  LODWORD(pProxya) = 1;
  if ( UserSidString[3] > 7u )
    UserSidString = (_QWORD *)*UserSidString;
  *(_OWORD *)&v16->lpVtbl = 0;
  v16[2].lpVtbl = 0;
  v16[3].lpVtbl = 0;
  v19 = -1;
  do
    ++v19;
  while ( *((_WORD *)UserSidString + v19) );
  std::wstring::_Construct<1,unsigned short const *>(v16, UserSidString, v19);
  v16[4].lpVtbl = (struct IUnknownVtbl *)pProxy;
  if ( pProxy )
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->AddRef)(pProxy);
  v16[5].lpVtbl = (struct IUnknownVtbl *)a2;
  if ( a2 )
    ((void (__fastcall *)(IUnknown *))a2->lpVtbl->AddRef)(a2);
  LODWORD(v16[6].lpVtbl) = v15;
  v20 = operator new(0x18u);
  *(_OWORD *)v20 = 0;
  *((_DWORD *)v20 + 2) = 1;
  *((_DWORD *)v20 + 3) = 1;
  *(_QWORD *)v20 = &std::_Ref_count<ProgressEventRegistration>::`vftable';
  *((_QWORD *)v20 + 2) = v16;
  pProxya = v16;
  v32 = v20;
  v28 = 0;
  std::_Temporary_owner<ProgressEventRegistration>::~_Temporary_owner<ProgressEventRegistration>(&v28);
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v30);
  v28 = (IUnknown *)&LanguageManager::s_eventRegistrationLock;
  if ( _Mtx_lock((_Mtx_t)&LanguageManager::s_eventRegistrationLock) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( dword_180089ECC == 0x7FFFFFFF )
  {
    dword_180089ECC = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v22 = (IUnknown **)qword_18008A3C0;
  if ( qword_18008A3C0 == qword_18008A3C8 )
  {
    std::vector<std::shared_ptr<ProgressEventRegistration>>::_Emplace_reallocate<std::shared_ptr<ProgressEventRegistration> const &>(
      v21,
      qword_18008A3C0,
      &pProxya);
    v20 = v32;
  }
  else
  {
    *(_QWORD *)qword_18008A3C0 = 0;
    v22[1] = 0;
    _InterlockedAdd((volatile signed __int32 *)v20 + 2, 1u);
    *v22 = v16;
    v22[1] = (IUnknown *)v20;
    qword_18008A3C0 += 16;
  }
  _Mtx_unlock((_Mtx_t)&LanguageManager::s_eventRegistrationLock);
  LanguageManager::_RaiseProgressEvent();
  if ( v20 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v20)(v20);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v17);
  return v15;
}

```

## disassembly

```asm
0x180033418  mov     [rsp-8+arg_10], rbx
0x18003341d  push    rbp
0x18003341e  push    rsi
0x18003341f  push    rdi
0x180033420  push    r12
0x180033422  push    r13
0x180033424  push    r14
0x180033426  push    r15
0x180033428  lea     rbp, [rsp-27h]
0x18003342d  sub     rsp, 90h
0x180033434  mov     rax, cs:__security_cookie
0x18003343b  xor     rax, rsp
0x18003343e  mov     [rbp+57h+var_38], rax
0x180033442  mov     rbx, rdx
0x180033445  mov     rsi, rcx
0x180033448  xor     r12d, r12d
0x18003344b  mov     dword ptr [rbp+57h+pProxy], r12d
0x18003344f  test    rcx, rcx
0x180033452  jnz     short loc_18003345C
0x180033454  test    rdx, rdx
0x180033457  mov     al, r12b
0x18003345a  jz      short loc_18003345E
0x18003345c  mov     al, 1
0x18003345e  mov     rcx, [rbp+5Fh]; this
0x180033462  test    al, al
0x180033464  jz      loc_180033834
0x18003346a  call    ?_EnsureTrustedCaller@LanguageManager@@CAXXZ; LanguageManager::_EnsureTrustedCaller(void)
0x18003346f  mov     edi, 20h ; ' '
0x180033474  lea     r14d, [rdi-1Eh]
0x180033478  or      r13, 0FFFFFFFFFFFFFFFFh
0x18003347c  or      r15d, 0FFFFFFFFh
0x180033480  test    rsi, rsi
0x180033483  jz      loc_18003354C
0x180033489  mov     [rbp+57h+pProxy], r12
0x18003348d  mov     rax, [rsi]
0x180033490  lea     r8, [rbp+57h+pProxy]
0x180033494  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18003349b  mov     rcx, rsi
0x18003349e  mov     rax, [rax]
0x1800334a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334a6  mov     rcx, [rbp+5Fh]; this
0x1800334aa  test    eax, eax
0x1800334ac  js      loc_18003384C
0x1800334b2  call    cs:__imp_CoImpersonateClient
0x1800334b8  mov     rcx, [rbp+5Fh]; this
0x1800334bc  test    eax, eax
0x1800334be  js      loc_180033861
0x1800334c4  mov     [rbp+57h+var_80], 1
0x1800334c8  mov     [rsp+0C0h+dwCapabilities], edi; dwCapabilities
0x1800334cc  mov     [rsp+0C0h+pAuthInfo], r12; pAuthInfo
0x1800334d1  mov     [rsp+0C0h+dwImpLevel], r14d; dwImpLevel
0x1800334d6  mov     [rsp+0C0h+dwAuthnLevel], r12d; int
0x1800334db  mov     r9, r13; pServerPrincName
0x1800334de  xor     r8d, r8d; dwAuthzSvc
0x1800334e1  mov     edx, r15d; dwAuthnSvc
0x1800334e4  mov     rcx, [rbp+57h+pProxy]; pProxy
0x1800334e8  call    cs:__imp_CoSetProxyBlanket
0x1800334ee  mov     rcx, [rbp+5Fh]; this
0x1800334f2  test    eax, eax
0x1800334f4  js      loc_180033876
0x1800334fa  mov     [rsp+0C0h+dwCapabilities], edi; dwCapabilities
0x1800334fe  mov     [rsp+0C0h+pAuthInfo], r12; pAuthInfo
0x180033503  mov     [rsp+0C0h+dwImpLevel], r14d; dwImpLevel
0x180033508  mov     [rsp+0C0h+dwAuthnLevel], r12d; int
0x18003350d  mov     r9, r13; pServerPrincName
0x180033510  xor     r8d, r8d; dwAuthzSvc
0x180033513  mov     edx, r15d; dwAuthnSvc
0x180033516  mov     rcx, rsi; pProxy
0x180033519  call    cs:__imp_CoSetProxyBlanket
0x18003351f  mov     rcx, [rbp+5Fh]; this
0x180033523  test    eax, eax
0x180033525  js      loc_18003388B
0x18003352b  call    cs:__imp_CoRevertToSelf
0x180033531  nop
0x180033532  mov     rcx, [rbp+57h+pProxy]
0x180033536  test    rcx, rcx
0x180033539  jz      short loc_18003354C
0x18003353b  mov     [rbp+57h+pProxy], r12
0x18003353f  mov     rax, [rcx]
0x180033542  mov     rax, [rax+10h]
0x180033546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003354b  nop
0x18003354c  test    rbx, rbx
0x18003354f  jz      loc_180033618
0x180033555  mov     [rbp+57h+pProxy], r12
0x180033559  mov     rax, [rbx]
0x18003355c  lea     r8, [rbp+57h+pProxy]
0x180033560  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180033567  mov     rcx, rbx
0x18003356a  mov     rax, [rax]
0x18003356d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033572  mov     rcx, [rbp+5Fh]; this
0x180033576  test    eax, eax
0x180033578  js      loc_1800338A0
0x18003357e  call    cs:__imp_CoImpersonateClient
0x180033584  mov     rcx, [rbp+5Fh]; this
0x180033588  test    eax, eax
0x18003358a  js      loc_1800338B5
0x180033590  mov     [rbp+57h+var_80], 1
0x180033594  mov     [rsp+0C0h+dwCapabilities], edi; dwCapabilities
0x180033598  mov     [rsp+0C0h+pAuthInfo], r12; pAuthInfo
0x18003359d  mov     [rsp+0C0h+dwImpLevel], r14d; dwImpLevel
0x1800335a2  mov     [rsp+0C0h+dwAuthnLevel], r12d; int
0x1800335a7  mov     r9, r13; pServerPrincName
0x1800335aa  xor     r8d, r8d; dwAuthzSvc
0x1800335ad  mov     edx, r15d; dwAuthnSvc
0x1800335b0  mov     rcx, [rbp+57h+pProxy]; pProxy
0x1800335b4  call    cs:__imp_CoSetProxyBlanket
0x1800335ba  mov     rcx, [rbp+5Fh]; this
0x1800335be  test    eax, eax
0x1800335c0  js      loc_1800338CA
0x1800335c6  mov     [rsp+0C0h+dwCapabilities], edi; dwCapabilities
0x1800335ca  mov     [rsp+0C0h+pAuthInfo], r12; pAuthInfo
0x1800335cf  mov     [rsp+0C0h+dwImpLevel], r14d; dwImpLevel
0x1800335d4  mov     [rsp+0C0h+dwAuthnLevel], r12d; int
0x1800335d9  mov     r9, r13; pServerPrincName
0x1800335dc  xor     r8d, r8d; dwAuthzSvc
0x1800335df  mov     edx, r15d; dwAuthnSvc
0x1800335e2  mov     rcx, rbx; pProxy
0x1800335e5  call    cs:__imp_CoSetProxyBlanket
0x1800335eb  mov     rcx, [rbp+5Fh]; this
0x1800335ef  test    eax, eax
0x1800335f1  js      loc_18003381F
0x1800335f7  call    cs:__imp_CoRevertToSelf
0x1800335fd  nop
0x1800335fe  mov     rcx, [rbp+57h+pProxy]
0x180033602  test    rcx, rcx
0x180033605  jz      short loc_180033618
0x180033607  mov     [rbp+57h+pProxy], r12
0x18003360b  mov     rax, [rcx]
0x18003360e  mov     rax, [rax+10h]
0x180033612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033617  nop
0x180033618  lea     rcx, [rbp+57h+hObject]
0x18003361c  call    ?GetCallerTokenHandleForIdentification@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; GetCallerTokenHandleForIdentification(void)
0x180033621  nop
0x180033622  mov     r14d, 1
0x180033628  lock xadd cs:?s_nextEventRegistrationCookie@LanguageManager@@0IA, r14d; uint LanguageManager::s_nextEventRegistrationCookie
0x180033631  inc     r14d
0x180033634  mov     ecx, 38h ; '8'; Size
0x180033639  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003363e  mov     rdi, rax
0x180033641  mov     [rbp+57h+var_78], rax
0x180033645  mov     r15, [rbp+57h+hObject]
0x180033649  mov     rdx, r15
0x18003364c  lea     rcx, [rbp+57h+var_68]
0x180033650  call    ?GetUserSidString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetUserSidString(void *)
0x180033655  nop
0x180033656  mov     dword ptr [rbp+57h+pProxy], 1
0x18003365d  cmp     qword ptr [rax+18h], 7
0x180033662  jbe     short loc_180033667
0x180033664  mov     rax, [rax]
0x180033667  xorps   xmm0, xmm0
0x18003366a  movups  xmmword ptr [rdi], xmm0
0x18003366d  mov     [rdi+10h], r12
0x180033671  mov     [rdi+18h], r12
0x180033675  mov     r8, r13
0x180033678  inc     r8
0x18003367b  cmp     [rax+r8*2], r12w
0x180033680  jnz     short loc_180033678
0x180033682  mov     rdx, rax
0x180033685  mov     rcx, rdi
0x180033688  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003368d  mov     [rdi+20h], rsi
0x180033691  test    rsi, rsi
0x180033694  jz      short loc_1800336A6
0x180033696  mov     rax, [rsi]
0x180033699  mov     rcx, rsi
0x18003369c  mov     rax, [rax+8]
0x1800336a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336a5  nop
0x1800336a6  mov     [rdi+28h], rbx
0x1800336aa  test    rbx, rbx
0x1800336ad  jz      short loc_1800336BF
0x1800336af  mov     rax, [rbx]
0x1800336b2  mov     rcx, rbx
0x1800336b5  mov     rax, [rax+8]
0x1800336b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336be  nop
0x1800336bf  mov     [rdi+30h], r14d
0x1800336c3  mov     [rbp+57h+var_78], rdi
0x1800336c7  mov     ecx, 18h; Size
0x1800336cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800336d1  mov     rbx, rax
0x1800336d4  mov     [rbp+57h+var_78], rax
0x1800336d8  xorps   xmm0, xmm0
0x1800336db  movups  xmmword ptr [rax], xmm0
0x1800336de  mov     esi, 1
0x1800336e3  mov     [rax+8], esi
0x1800336e6  mov     [rax+0Ch], esi
0x1800336e9  lea     rax, ??_7?$_Ref_count@VProgressEventRegistration@@@std@@6B@; const std::_Ref_count<ProgressEventRegistration>::`vftable'
0x1800336f0  mov     [rbx], rax
0x1800336f3  mov     [rbx+10h], rdi
0x1800336f7  mov     [rbp+57h+pProxy], rdi
0x1800336fb  mov     [rbp+57h+var_40], rbx
0x1800336ff  mov     [rbp+57h+var_78], r12
0x180033703  lea     rcx, [rbp+57h+var_78]
0x180033707  call    ??1?$_Temporary_owner@VProgressEventRegistration@@@std@@QEAA@XZ; std::_Temporary_owner<ProgressEventRegistration>::~_Temporary_owner<ProgressEventRegistration>(void)
0x18003370c  nop
0x18003370d  lea     rcx, [rbp+57h+var_68]; void *
0x180033711  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180033716  lea     rax, ?s_eventRegistrationLock@LanguageManager@@0Vrecursive_mutex@std@@A; std::recursive_mutex LanguageManager::s_eventRegistrationLock
0x18003371d  mov     [rbp+57h+var_78], rax
0x180033721  mov     rcx, rax; _Mtx_t
0x180033724  call    cs:__imp__Mtx_lock
0x18003372a  test    eax, eax
0x18003372c  jz      short loc_180033738
0x18003372e  lea     ecx, [rsi+4]
0x180033731  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180033737  int     3; Trap to Debugger
0x180033738  mov     eax, cs:dword_180089ECC
0x18003373e  cmp     eax, 7FFFFFFFh
0x180033743  jnz     short loc_180033759
0x180033745  dec     eax
0x180033747  mov     cs:dword_180089ECC, eax
0x18003374d  mov     ecx, 6
0x180033752  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180033758  nop
0x180033759  mov     rdx, cs:qword_18008A3C0
0x180033760  cmp     rdx, cs:qword_18008A3C8
0x180033767  jz      short loc_180033785
0x180033769  mov     [rdx], r12
0x18003376c  mov     [rdx+8], r12
0x180033770  lock add [rbx+8], esi
0x180033774  mov     [rdx], rdi
0x180033777  mov     [rdx+8], rbx
0x18003377b  add     cs:qword_18008A3C0, 10h
0x180033783  jmp     short loc_180033792
0x180033785  lea     r8, [rbp+57h+pProxy]
0x180033789  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VProgressEventRegistration@@@std@@@?$vector@V?$shared_ptr@VProgressEventRegistration@@@std@@V?$allocator@V?$shared_ptr@VProgressEventRegistration@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VProgressEventRegistration@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<ProgressEventRegistration>>::_Emplace_reallocate<std::shared_ptr<ProgressEventRegistration> const &>(std::shared_ptr<ProgressEventRegistration> * const,std::shared_ptr<ProgressEventRegistration> const &)
0x18003378e  mov     rbx, [rbp+57h+var_40]
0x180033792  lea     rcx, ?s_eventRegistrationLock@LanguageManager@@0Vrecursive_mutex@std@@A; _Mtx_t
0x180033799  call    cs:__imp__Mtx_unlock
0x18003379f  call    ?_RaiseProgressEvent@LanguageManager@@CAXXZ; LanguageManager::_RaiseProgressEvent(void)
0x1800337a4  nop
0x1800337a5  test    rbx, rbx
0x1800337a8  jz      short loc_1800337E2
0x1800337aa  mov     eax, r13d
0x1800337ad  lock xadd [rbx+8], eax
0x1800337b2  add     eax, r13d
0x1800337b5  jnz     short loc_1800337E2
0x1800337b7  mov     rax, [rbx]
0x1800337ba  mov     rcx, rbx
0x1800337bd  mov     rax, [rax]
0x1800337c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337c5  mov     eax, r13d
0x1800337c8  lock xadd [rbx+0Ch], eax
0x1800337cd  add     eax, r13d
0x1800337d0  jnz     short loc_1800337E2
0x1800337d2  mov     rax, [rbx]
0x1800337d5  mov     rcx, rbx
0x1800337d8  mov     rax, [rax+8]
0x1800337dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337e1  nop
0x1800337e2  lea     rdx, [r15-1]
0x1800337e6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800337ea  ja      short loc_1800337F5
0x1800337ec  mov     rcx, r15; hObject
0x1800337ef  call    cs:__imp_CloseHandle
0x1800337f5  mov     eax, r14d
0x1800337f8  mov     rcx, [rbp+57h+var_38]
0x1800337fc  xor     rcx, rsp; StackCookie
0x1800337ff  call    __security_check_cookie
0x180033804  mov     rbx, [rsp+0C0h+arg_10]
0x18003380c  add     rsp, 90h
0x180033813  pop     r15
0x180033815  pop     r14
0x180033817  pop     r13
0x180033819  pop     r12
0x18003381b  pop     rdi
0x18003381c  pop     rsi
0x18003381d  pop     rbp
0x18003381e  retn
0x18003381f  mov     r9d, eax; char *
0x180033822  lea     r8, aOnecoreBaseLan_4; "onecore\\base\\languageoverlay\\service"...
0x180033829  mov     edx, 1DEh; void *
0x18003382e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033834  mov     r9d, 80004003h; char *
0x18003383a  lea     r8, aOnecoreBaseLan_4; "onecore\\base\\languageoverlay\\service"...
0x180033841  mov     edx, 1E6h; void *
0x180033846  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003384c  mov     r9d, eax; char *
0x18003384f  lea     r8, aOnecoreBaseLan_4; "onecore\\base\\languageoverlay\\service"...
0x180033856  mov     edx, 1C7h; void *
0x18003385b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033861  mov     r9d, eax; char *
0x180033864  lea     r8, aOnecoreBaseLan_4; "onecore\\base\\languageoverlay\\service"...
0x18003386b  mov     edx, 1C9h; void *
0x180033870  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033876  mov     r9d, eax; char *
0x180033879  lea     r8, aOnecoreBaseLan_4; "onecore\\base\\languageoverlay\\service"...
0x180033880  mov     edx, 1D4h; void *
0x180033885  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003388b  mov     r9d, eax; char *
0x18003388e  lea     r8, aOnecoreBaseLan_4; "onecore\\base\\languageoverlay\\service"...
0x180033895  mov     edx, 1DEh; void *
0x18003389a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800338a0  mov     r9d, eax; char *
0x1800338a3  lea     r8, aOnecoreBaseLan_4; "onecore\\base\\languageoverlay\\service"...
0x1800338aa  mov     edx, 1C7h; void *
  ... truncated ...
```
