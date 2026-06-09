# LogStateForAllLanguages(LanguageOverlayTraceProvider::EvaluatePendingUpdatesForUserActivity const &,void *)

- ea: `0x1800412a8`
- end: `0x180041a71`
- name: `?LogStateForAllLanguages@@YAXAEBVEvaluatePendingUpdatesForUserActivity@LanguageOverlayTraceProvider@@PEAX@Z`
- size: `1993`
- prototype: `void __fastcall(const struct LanguageOverlayTraceProvider::EvaluatePendingUpdatesForUserActivity *, void *)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180019390`

## callees

- `0x180003a00`
- `0x180005db4`
- `0x180011318`
- `0x180014e24`
- `0x180014ed0`
- `0x180014f3c`
- `0x1800178ac`
- `0x180027818`
- `0x18003566c`
- `0x180035810`
- `0x1800367f4`
- `0x18003fdfc`
- `0x180041038`
- `0x1800412a8`
- `0x180041e8c`
- `0x180042144`
- `0x1800421cc`
- `0x1800452d8`
- `0x18004c324`
- `0x180059ce8`
- `0x180059d7c`
- `0x18005f094`
- `0x18005f678`
- `0x180061b94`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041641`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041641`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004158d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004158d`
- `api-ms-win-core-localization-obsolete-l1-2-0!EnumUILanguagesW` at `0x1800413fd`
- `api-ms-win-core-localization-obsolete-l1-2-0!EnumUILanguagesW` at `0x1800413fd`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180041563`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180041563`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x1800416b6`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x1800416b6`

## string_xrefs

- `0x18004159a`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`
- `0x180041a5e`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall LogStateForAllLanguages(
        const struct LanguageOverlayTraceProvider::EvaluatePendingUpdatesForUserActivity *a1,
        void *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rax
  __int64 v6; // rax
  const char *v7; // r9
  _QWORD *v8; // rax
  __int64 v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // rax
  __int64 UserDefaultUILanguage; // rdx
  char v13; // al
  HKEY v14; // rcx
  _QWORD *v15; // rdx
  __int64 SystemPreferredLanguages; // rax
  __int64 SystemDefaultUILanguage; // rdx
  __int64 *v18; // rdi
  __int64 *i; // rbx
  const char *v20; // r9
  _QWORD *v21; // r15
  char **v22; // rax
  char **v23; // rax
  _BYTE v24[8]; // [rsp+30h] [rbp-208h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-200h] BYREF
  int v26; // [rsp+40h] [rbp-1F8h]
  _DWORD v27[3]; // [rsp+48h] [rbp-1F0h] BYREF
  __int64 v28; // [rsp+54h] [rbp-1E4h]
  __int64 v29; // [rsp+5Ch] [rbp-1DCh]
  __int64 v30; // [rsp+64h] [rbp-1D4h]
  int v31; // [rsp+6Ch] [rbp-1CCh]
  char **v32; // [rsp+70h] [rbp-1C8h]
  _DWORD v33[3]; // [rsp+78h] [rbp-1C0h] BYREF
  __int64 v34; // [rsp+84h] [rbp-1B4h]
  __int64 v35; // [rsp+8Ch] [rbp-1ACh]
  __int64 v36; // [rsp+94h] [rbp-1A4h]
  int v37; // [rsp+9Ch] [rbp-19Ch]
  char **v38; // [rsp+A0h] [rbp-198h]
  _QWORD v39[7]; // [rsp+B0h] [rbp-188h] BYREF
  _QWORD *v40; // [rsp+E8h] [rbp-150h]
  void (__fastcall ***v41)(_QWORD, __int64); // [rsp+F0h] [rbp-148h] BYREF
  void (__fastcall ***v42)(_QWORD, __int64); // [rsp+F8h] [rbp-140h] BYREF
  int v43; // [rsp+100h] [rbp-138h] BYREF
  _QWORD v44[2]; // [rsp+108h] [rbp-130h] BYREF
  char *v45; // [rsp+118h] [rbp-120h] BYREF
  __int128 v46; // [rsp+120h] [rbp-118h]
  __int64 v47; // [rsp+130h] [rbp-108h]
  __int64 v48; // [rsp+138h] [rbp-100h]
  LONG_PTR lParam; // [rsp+140h] [rbp-F8h] BYREF
  void *v50; // [rsp+148h] [rbp-F0h] BYREF
  int v51; // [rsp+150h] [rbp-E8h]
  char *v52[4]; // [rsp+158h] [rbp-E0h] BYREF
  int v53; // [rsp+178h] [rbp-C0h]
  int v54; // [rsp+17Ch] [rbp-BCh]
  _BYTE v55[8]; // [rsp+180h] [rbp-B8h] BYREF
  void *v56; // [rsp+188h] [rbp-B0h] BYREF
  char *v57; // [rsp+198h] [rbp-A0h] BYREF
  int v58; // [rsp+1C0h] [rbp-78h] BYREF
  void *v59; // [rsp+1C8h] [rbp-70h] BYREF
  int v60; // [rsp+1D0h] [rbp-68h]
  char *v61[4]; // [rsp+1D8h] [rbp-60h] BYREF
  int v62; // [rsp+1F8h] [rbp-40h]
  int v63; // [rsp+1FCh] [rbp-3Ch]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  try
  {
    v26 = 0;
    v44[1] = 0;
    v4 = operator new(0x38u);
    *v4 = v4;
    v4[1] = v4;
    v44[0] = v4;
    v45 = 0;
    v46 = 0;
    v47 = 7;
    v48 = 8;
    v43 = 1065353216;
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::weak_ptr<ExecutionGate>>>>>>>::_Assign_grow(
      &v45,
      16,
      v4);
    v5 = (_QWORD *)CreateSystemLanguageResourcesProvider(&hKey);
    v6 = (*(__int64 (__fastcall **)(_QWORD, LONG_PTR *))(*(_QWORD *)*v5 + 8LL))(*v5, &lParam);
    SetStateFlagForLanguages(&v43, v6, 32);
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(v52);
    std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(&v50);
    if ( hKey )
      (**(void (__fastcall ***)(HKEY, __int64))hKey)(hKey, 1);
    std::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(&lParam);
    if ( !EnumUILanguagesW(lambda_693fcef0bf018ca94be9a2f9071acd03_::_lambda_invoker_cdecl_, 0x98u, (LONG_PTR)&lParam) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x114,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
        v7);
    std::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(
      &v58,
      &lParam);
    v26 = 1;
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(v52);
    std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(&v50);
    SetStateFlagForLanguages(&v43, &v58, 256);
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(v61);
    std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(&v59);
    v8 = (_QWORD *)CreateOverlayLanguageResourcesProvider(&hKey);
    v9 = (*(__int64 (__fastcall **)(_QWORD, LONG_PTR *))(*(_QWORD *)*v8 + 8LL))(*v8, &lParam);
    SetStateFlagForLanguages(&v43, v9, 64);
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(v52);
    std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(&v50);
    if ( hKey )
      (**(void (__fastcall ***)(HKEY, __int64))hKey)(hKey, 1);
    raii::ImpersonateLoggedOnUser(v24, a2);
    v10 = (_QWORD *)CreateOverlayLanguageResourcesProvider(&hKey);
    v11 = (*(__int64 (__fastcall **)(_QWORD, LONG_PTR *))(*(_QWORD *)*v10 + 8LL))(*v10, &lParam);
    SetStateFlagForLanguages(&v43, v11, 192);
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(v52);
    std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(&v50);
    if ( hKey )
      (**(void (__fastcall ***)(HKEY, __int64))hKey)(hKey, 1);
    UserDefaultUILanguage = GetUserDefaultUILanguage();
    SetStateFlagForLanguage_0(&v43, UserDefaultUILanguage, 4);
    v13 = v24[0];
    v24[0] = 0;
    if ( v13 )
      RevertToSelf();
    TryOpenRegKey(
      &hKey,
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
      9u);
    std::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::unordered_set<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(&lParam);
    v26 = 3;
    v14 = hKey;
    if ( hKey )
    {
      v39[0] = off_18006BE68;
      v39[1] = &lParam;
      v40 = v39;
      EnumerateRegKeys(hKey);
      if ( v40 )
      {
        v15 = v39;
        LOBYTE(v15) = v40 != v39;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v40 + 32LL))(v40, v15);
      }
      v14 = hKey;
    }
    if ( v14 )
      RegCloseKey(v14);
    SetStateFlagForLanguages(&v43, &lParam, 1);
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(v52);
    std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(&v50);
    SystemPreferredLanguages = GetSystemPreferredLanguages((__int64)&lParam);
    SetStateFlagForLanguages(&v43, SystemPreferredLanguages, 8);
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(v52);
    std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(&v50);
    SystemDefaultUILanguage = GetSystemDefaultUILanguage();
    SetStateFlagForLanguage_0(&v43, SystemDefaultUILanguage, 16);
    GetPreferredLanguagesForUser((__int64)&lParam, (__int64)a2);
    SetStateFlagForLanguages(&v43, &lParam, 3);
    SetStateFlagForLanguages(&v43, v55, 512);
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(&v57);
    std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(&v56);
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(v52);
    std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(&v50);
    CreateOverlayLanguageResourcesStateManager(&v41, a2);
    CreateSystemLanguageResourcesStateManager(&v42);
    v18 = (__int64 *)v44[0];
    for ( i = *(__int64 **)v44[0]; i != v18; i = (__int64 *)*i )
    {
      v21 = i + 2;
      GetReconciliationInfo(&lParam, i + 2, v41);
      GetReconciliationInfo(&v58, i + 2, v42);
      v33[0] = lParam;
      v33[1] = v51;
      v33[2] = v53;
      v34 = 10000000 * (60 * (int)v50 + 0x2B6109100LL);
      v35 = 10000000 * (60 * HIDWORD(v50) + 0x2B6109100LL);
      v36 = 10000000 * (60 * ((int)v50 + v54) + 0x2B6109100LL);
      v22 = 0;
      v37 = 0;
      if ( v52[2] )
      {
        v22 = v52;
        if ( v52[3] > (char *)7 )
          v22 = (char **)v52[0];
      }
      v38 = v22;
      v27[0] = v58;
      v27[1] = v60;
      v27[2] = v62;
      v28 = 10000000 * (60 * (int)v59 + 0x2B6109100LL);
      v29 = 10000000 * (60 * HIDWORD(v59) + 0x2B6109100LL);
      v30 = 10000000 * (60 * ((int)v59 + v63) + 0x2B6109100LL);
      v23 = 0;
      v31 = 0;
      if ( v61[2] )
      {
        v23 = v61;
        if ( v61[3] > (char *)7 )
          v23 = (char **)v61[0];
      }
      v32 = v23;
      if ( (unsigned __int64)i[5] > 7 )
        v21 = (_QWORD *)*v21;
      LanguageOverlayTraceProvider::EvaluatePendingUpdatesForUserActivity::LogLanguageState(
        a1,
        v21,
        *((unsigned int *)i + 12),
        v33,
        v27);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v61);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v52);
    }
    if ( v42 )
      (**v42)(v42, 1);
    if ( v41 )
      (**v41)(v41, 1);
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(&v45);
    std::list<std::pair<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>> const,enum LanguageStateFlags>>::~list<std::pair<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>> const,enum LanguageStateFlags>>(v44);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x167,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\telemetryutils.cpp",
      v20);
  }
}

```

## disassembly

```asm
0x1800412a8  mov     [rsp+arg_10], rbx
0x1800412ad  push    rsi
0x1800412ae  push    rdi
0x1800412af  push    r12
0x1800412b1  push    r14
0x1800412b3  push    r15
0x1800412b5  sub     rsp, 210h
0x1800412bc  mov     rax, cs:__security_cookie
0x1800412c3  xor     rax, rsp
0x1800412c6  mov     [rsp+238h+var_38], rax
0x1800412ce  mov     rbx, rdx
0x1800412d1  mov     r12, rcx
0x1800412d4  mov     [rsp+238h+var_1F8], 0
0x1800412dc  mov     [rsp+238h+var_138], 0
0x1800412e7  mov     [rsp+238h+var_130], 0
0x1800412f3  mov     [rsp+238h+var_128], 0
0x1800412ff  mov     ecx, 38h ; '8'; Size
0x180041304  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180041309  mov     [rax], rax
0x18004130c  mov     [rax+8], rax
0x180041310  mov     [rsp+238h+var_130], rax
0x180041318  mov     [rsp+238h+var_120], 0
0x180041324  xorps   xmm0, xmm0
0x180041327  movdqa  [rsp+238h+var_118], xmm0
0x180041330  mov     [rsp+238h+var_108], 7
0x18004133c  mov     r14d, 8
0x180041342  mov     [rsp+238h+var_100], r14
0x18004134a  mov     [rsp+238h+var_138], 3F800000h
0x180041355  mov     r8, rax
0x180041358  lea     r15d, [r14+8]
0x18004135c  mov     edx, r15d
0x18004135f  lea     rcx, [rsp+238h+var_120]
0x180041367  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$weak_ptr@VExecutionGate@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$weak_ptr@VExecutionGate@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::weak_ptr<ExecutionGate>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::weak_ptr<ExecutionGate>>>>>)
0x18004136c  nop
0x18004136d  lea     rcx, [rsp+238h+hKey]
0x180041372  call    ?CreateSystemLanguageResourcesProvider@@YA?AV?$unique_ptr@UILanguageResourcesProvider@@U?$default_delete@UILanguageResourcesProvider@@@std@@@std@@XZ; CreateSystemLanguageResourcesProvider(void)
0x180041377  nop
0x180041378  mov     rcx, [rax]
0x18004137b  mov     rax, [rcx]
0x18004137e  lea     rdx, [rsp+238h+lParam]
0x180041386  mov     rax, [rax+8]
0x18004138a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004138f  nop
0x180041390  lea     r8d, [r14+18h]
0x180041394  mov     rdx, rax
0x180041397  lea     rcx, [rsp+238h+var_138]
0x18004139f  call    _SetStateFlagForLanguages
0x1800413a4  nop
0x1800413a5  lea     rcx, [rsp+238h+var_E0]
0x1800413ad  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x1800413b2  lea     rcx, [rsp+238h+var_F0]
0x1800413ba  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x1800413bf  nop
0x1800413c0  mov     rcx, [rsp+238h+hKey]
0x1800413c5  lea     esi, [r14-7]
0x1800413c9  test    rcx, rcx
0x1800413cc  jz      short loc_1800413DB
0x1800413ce  mov     rax, [rcx]
0x1800413d1  mov     edx, esi
0x1800413d3  mov     rax, [rax]
0x1800413d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413db  lea     rcx, [rsp+238h+lParam]
0x1800413e3  call    ??0?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x1800413e8  nop
0x1800413e9  lea     r8, [rsp+238h+lParam]; lParam
0x1800413f1  mov     edx, 98h; dwFlags
0x1800413f6  lea     rcx, _lambda_693fcef0bf018ca94be9a2f9071acd03____lambda_invoker_cdecl_; lpUILanguageEnumProc
0x1800413fd  call    cs:__imp_EnumUILanguagesW
0x180041403  mov     rcx, [rsp+238h]; this
0x18004140b  test    eax, eax
0x18004140d  jz      loc_180041A5E
0x180041413  lea     rdx, [rsp+238h+lParam]
0x18004141b  lea     rcx, [rsp+238h+var_78]
0x180041423  call    ??0?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>> &&)
0x180041428  mov     [rsp+238h+var_1F8], esi
0x18004142c  lea     rcx, [rsp+238h+var_E0]
0x180041434  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x180041439  lea     rcx, [rsp+238h+var_F0]
0x180041441  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x180041446  nop
0x180041447  mov     r8d, 100h
0x18004144d  lea     rdx, [rsp+238h+var_78]
0x180041455  lea     rcx, [rsp+238h+var_138]
0x18004145d  call    _SetStateFlagForLanguages
0x180041462  nop
0x180041463  lea     rcx, [rsp+238h+var_60]
0x18004146b  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x180041470  lea     rcx, [rsp+238h+var_70]
0x180041478  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x18004147d  lea     rcx, [rsp+238h+hKey]
0x180041482  call    ?CreateOverlayLanguageResourcesProvider@@YA?AV?$unique_ptr@UILanguageResourcesProvider@@U?$default_delete@UILanguageResourcesProvider@@@std@@@std@@XZ; CreateOverlayLanguageResourcesProvider(void)
0x180041487  nop
0x180041488  mov     rcx, [rax]
0x18004148b  mov     rax, [rcx]
0x18004148e  lea     rdx, [rsp+238h+lParam]
0x180041496  mov     rax, [rax+8]
0x18004149a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004149f  nop
0x1800414a0  mov     r8d, 40h ; '@'
0x1800414a6  mov     rdx, rax
0x1800414a9  lea     rcx, [rsp+238h+var_138]
0x1800414b1  call    _SetStateFlagForLanguages
0x1800414b6  nop
0x1800414b7  lea     rcx, [rsp+238h+var_E0]
0x1800414bf  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x1800414c4  lea     rcx, [rsp+238h+var_F0]
0x1800414cc  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x1800414d1  nop
0x1800414d2  mov     rcx, [rsp+238h+hKey]
0x1800414d7  test    rcx, rcx
0x1800414da  jz      short loc_1800414E9
0x1800414dc  mov     rax, [rcx]
0x1800414df  mov     edx, esi
0x1800414e1  mov     rax, [rax]
0x1800414e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414e9  mov     rdx, rbx
0x1800414ec  lea     rcx, [rsp+238h+var_208]
0x1800414f1  call    ?ImpersonateLoggedOnUser@raii@@YA?AV?$unique_call@P6AHXZ$1?RevertToSelf@@YAHXZ$00@wil@@PEAX@Z; raii::ImpersonateLoggedOnUser(void *)
0x1800414f6  nop
0x1800414f7  lea     rcx, [rsp+238h+hKey]
0x1800414fc  call    ?CreateOverlayLanguageResourcesProvider@@YA?AV?$unique_ptr@UILanguageResourcesProvider@@U?$default_delete@UILanguageResourcesProvider@@@std@@@std@@XZ; CreateOverlayLanguageResourcesProvider(void)
0x180041501  nop
0x180041502  mov     rcx, [rax]
0x180041505  mov     rax, [rcx]
0x180041508  lea     rdx, [rsp+238h+lParam]
0x180041510  mov     rax, [rax+8]
0x180041514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041519  nop
0x18004151a  mov     r8d, 0C0h
0x180041520  mov     rdx, rax
0x180041523  lea     rcx, [rsp+238h+var_138]
0x18004152b  call    _SetStateFlagForLanguages
0x180041530  nop
0x180041531  lea     rcx, [rsp+238h+var_E0]
0x180041539  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x18004153e  lea     rcx, [rsp+238h+var_F0]
0x180041546  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x18004154b  nop
0x18004154c  mov     rcx, [rsp+238h+hKey]
0x180041551  test    rcx, rcx
0x180041554  jz      short loc_180041563
0x180041556  mov     rax, [rcx]
0x180041559  mov     edx, esi
0x18004155b  mov     rax, [rax]
0x18004155e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041563  call    cs:__imp_GetUserDefaultUILanguage
0x180041569  movzx   edx, ax
0x18004156c  mov     r8d, 4
0x180041572  lea     rcx, [rsp+238h+var_138]
0x18004157a  call    _SetStateFlagForLanguage_0
0x18004157f  nop
0x180041580  mov     al, [rsp+238h+var_208]
0x180041584  mov     [rsp+238h+var_208], 0
0x180041589  test    al, al
0x18004158b  jz      short loc_180041594
0x18004158d  call    cs:__imp_RevertToSelf
0x180041593  nop
0x180041594  mov     r9d, 9
0x18004159a  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800415a1  mov     rdx, 0FFFFFFFF80000002h
0x1800415a8  lea     rcx, [rsp+238h+hKey]
0x1800415ad  call    ?TryOpenRegKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBGK@Z; TryOpenRegKey(HKEY__ *,ushort const *,ulong)
0x1800415b2  nop
0x1800415b3  lea     rcx, [rsp+238h+lParam]
0x1800415bb  call    ??0?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::unordered_set<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x1800415c0  mov     edi, 3
0x1800415c5  mov     [rsp+238h+var_1F8], edi
0x1800415c9  mov     rcx, [rsp+238h+hKey]; hKey
0x1800415ce  test    rcx, rcx
0x1800415d1  jz      short loc_18004163C
0x1800415d3  lea     rax, off_18006BE68
0x1800415da  mov     [rsp+238h+var_188], rax
0x1800415e2  lea     rax, [rsp+238h+lParam]
0x1800415ea  mov     [rsp+238h+var_180], rax
0x1800415f2  lea     rax, [rsp+238h+var_188]
0x1800415fa  mov     [rsp+238h+var_150], rax
0x180041602  lea     rdx, [rsp+238h+var_188]
0x18004160a  call    ?EnumerateRegKeys@@YAXPEAUHKEY__@@AEBV?$function@$$A6AXPEBG0AEBU_FILETIME@@@Z@std@@@Z; EnumerateRegKeys(HKEY__ *,std::function<void (ushort const *,ushort const *,_FILETIME const &)> const &)
0x18004160f  nop
0x180041610  mov     rcx, [rsp+238h+var_150]
0x180041618  test    rcx, rcx
0x18004161b  jz      short loc_180041637
0x18004161d  mov     rax, [rcx]
0x180041620  lea     rdx, [rsp+238h+var_188]
0x180041628  cmp     rcx, rdx
0x18004162b  setnz   dl
0x18004162e  mov     rax, [rax+20h]
0x180041632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041637  mov     rcx, [rsp+238h+hKey]; hKey
0x18004163c  test    rcx, rcx
0x18004163f  jz      short loc_180041647
0x180041641  call    cs:__imp_RegCloseKey
0x180041647  mov     r8d, esi
0x18004164a  lea     rdx, [rsp+238h+lParam]
0x180041652  lea     rcx, [rsp+238h+var_138]
0x18004165a  call    _SetStateFlagForLanguages
0x18004165f  nop
0x180041660  lea     rcx, [rsp+238h+var_E0]
0x180041668  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x18004166d  lea     rcx, [rsp+238h+var_F0]
0x180041675  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x18004167a  lea     rcx, [rsp+238h+lParam]
0x180041682  call    ?GetSystemPreferredLanguages@@YA?AV?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@XZ; GetSystemPreferredLanguages(void)
0x180041687  nop
0x180041688  mov     r8d, r14d
0x18004168b  mov     rdx, rax
0x18004168e  lea     rcx, [rsp+238h+var_138]
0x180041696  call    _SetStateFlagForLanguages
0x18004169b  nop
0x18004169c  lea     rcx, [rsp+238h+var_E0]
0x1800416a4  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x1800416a9  lea     rcx, [rsp+238h+var_F0]
0x1800416b1  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x1800416b6  call    cs:__imp_GetSystemDefaultUILanguage
0x1800416bc  movzx   edx, ax
0x1800416bf  mov     r8d, r15d
0x1800416c2  lea     rcx, [rsp+238h+var_138]
0x1800416ca  call    _SetStateFlagForLanguage_0
0x1800416cf  mov     rdx, rbx
0x1800416d2  lea     rcx, [rsp+238h+lParam]
0x1800416da  call    ?GetPreferredLanguagesForUser@@YA?AU?$pair@V?$unordered_set@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@U?$hash@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@U?$equal_to@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@V12@@std@@PEAX@Z; GetPreferredLanguagesForUser(void *)
0x1800416df  nop
0x1800416e0  mov     r8d, edi
0x1800416e3  lea     rdx, [rsp+238h+lParam]
0x1800416eb  lea     rcx, [rsp+238h+var_138]
0x1800416f3  call    _SetStateFlagForLanguages
0x1800416f8  mov     r8d, 200h
0x1800416fe  lea     rdx, [rsp+238h+var_B8]
0x180041706  lea     rcx, [rsp+238h+var_138]
0x18004170e  call    _SetStateFlagForLanguages
0x180041713  nop
0x180041714  lea     rcx, [rsp+238h+var_A0]
0x18004171c  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x180041721  lea     rcx, [rsp+238h+var_B0]
0x180041729  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x18004172e  lea     rcx, [rsp+238h+var_E0]
0x180041736  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x18004173b  lea     rcx, [rsp+238h+var_F0]
0x180041743  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x180041748  mov     rdx, rbx
0x18004174b  lea     rcx, [rsp+238h+var_148]
0x180041753  call    ?CreateOverlayLanguageResourcesStateManager@@YA?AV?$unique_ptr@UILanguageResourcesStateManager@@U?$default_delete@UILanguageResourcesStateManager@@@std@@@std@@PEAX@Z; CreateOverlayLanguageResourcesStateManager(void *)
0x180041758  nop
0x180041759  lea     rcx, [rsp+238h+var_140]
0x180041761  call    ?CreateSystemLanguageResourcesStateManager@@YA?AV?$unique_ptr@UILanguageResourcesStateManager@@U?$default_delete@UILanguageResourcesStateManager@@@std@@@std@@XZ; CreateSystemLanguageResourcesStateManager(void)
0x180041766  nop
0x180041767  mov     rdi, [rsp+238h+var_130]
0x18004176f  mov     rbx, [rdi]
0x180041772  cmp     rbx, rdi
0x180041775  jnz     short loc_1800417F0
0x180041777  mov     rcx, [rsp+238h+var_140]
0x18004177f  test    rcx, rcx
0x180041782  jz      short loc_180041792
0x180041784  mov     rax, [rcx]
0x180041787  mov     edx, esi
0x180041789  mov     rax, [rax]
0x18004178c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041791  nop
0x180041792  mov     rcx, [rsp+238h+var_148]
0x18004179a  test    rcx, rcx
0x18004179d  jz      short loc_1800417AD
0x18004179f  mov     rax, [rcx]
0x1800417a2  mov     edx, esi
0x1800417a4  mov     rax, [rax]
0x1800417a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417ac  nop
0x1800417ad  lea     rcx, [rsp+238h+var_120]
0x1800417b5  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x1800417ba  lea     rcx, [rsp+238h+var_130]
0x1800417c2  call    ??1?$list@U?$pair@$$CBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@W4LanguageStateFlags@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@W4LanguageStateFlags@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const,LanguageStateFlags>>::~list<std::pair<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const,LanguageStateFlags>>(void)
0x1800417c7  nop
0x1800417c8  mov     rcx, [rsp+238h+var_38]
0x1800417d0  xor     rcx, rsp; StackCookie
0x1800417d3  call    __security_check_cookie
0x1800417d8  mov     rbx, [rsp+238h+arg_10]
0x1800417e0  add     rsp, 210h
0x1800417e7  pop     r15
0x1800417e9  pop     r14
0x1800417eb  pop     r12
0x1800417ed  pop     rdi
0x1800417ee  pop     rsi
0x1800417ef  retn
0x1800417f0  lea     r15, [rbx+10h]
0x1800417f4  mov     ecx, [rbx+30h]
0x1800417f7  test    cl, 2
0x1800417fa  jz      short loc_180041833
0x1800417fc  mov     r9d, 2
0x180041802  mov     r14d, r9d
0x180041805  mov     eax, ecx
0x180041807  and     eax, 0A0h
0x18004180c  sub     eax, 20h ; ' '
0x18004180f  jz      short loc_18004183F
0x180041811  sub     eax, 60h ; '`'
0x180041814  jz      short loc_18004182E
0x180041816  cmp     eax, 20h ; ' '
0x180041819  jz      short loc_180041829
0x18004181b  bt      ecx, 9
0x18004181f  jb      short loc_180041842
0x180041821  xor     r9d, r9d
0x180041824  xor     r14d, r14d
  ... truncated ...
```
