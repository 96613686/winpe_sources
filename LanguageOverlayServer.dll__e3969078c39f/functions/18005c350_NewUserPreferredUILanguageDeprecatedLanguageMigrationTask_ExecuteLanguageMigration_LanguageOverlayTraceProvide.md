# NewUserPreferredUILanguageDeprecatedLanguageMigrationTask::_ExecuteLanguageMigration(LanguageOverlayTraceProvider::DeprecatedLanguageMigrationTaskActivity &)

- ea: `0x18005c350`
- end: `0x18005c561`
- name: `?_ExecuteLanguageMigration@NewUserPreferredUILanguageDeprecatedLanguageMigrationTask@@MEAAJAEAVDeprecatedLanguageMigrationTaskActivity@LanguageOverlayTraceProvider@@@Z`
- size: `529`
- prototype: `__int64 __fastcall(NewUserPreferredUILanguageDeprecatedLanguageMigrationTask *__hidden this, struct LanguageOverlayTraceProvider::DeprecatedLanguageMigrationTaskActivity *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180003ea0`
- `0x180009084`
- `0x180011318`
- `0x180014e24`
- `0x180014f3c`
- `0x18005aac4`
- `0x18005ac28`
- `0x18005ae1c`
- `0x18005c350`
- `0x18005dd7c`
- `0x18005e154`
- `0x18005f55c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c4a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c4b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c511`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c520`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c4a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c4b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c511`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c520`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c3a4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c3d6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c4c6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c532`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c3a4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c3d6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c4c6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c532`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18005c367`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18005c367`

## string_xrefs

- `0x18005c550`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\raiiutils.cpp`
- `0x18005c392`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deprecatedlanguagemigrationtask.cpp`
- `0x18005c3c4`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deprecatedlanguagemigrationtask.cpp`
- `0x18005c453`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deprecatedlanguagemigrationtask.cpp`

## pseudocode

```c
__int64 __fastcall NewUserPreferredUILanguageDeprecatedLanguageMigrationTask::_ExecuteLanguageMigration(
        NewUserPreferredUILanguageDeprecatedLanguageMigrationTask *this,
        struct LanguageOverlayTraceProvider::DeprecatedLanguageMigrationTaskActivity *a2)
{
  BOOL v3; // eax
  const char *v4; // r9
  int NewUserRegHive; // eax
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 result; // rax
  int v9; // eax
  unsigned int v10; // ebx
  HKEY v11; // rbx
  struct LanguageOverlayTraceProvider::DeprecatedLanguageMigrationTaskActivity *v12; // rdx
  char *v13; // rdi
  int v14; // eax
  unsigned int v15; // esi
  HKEY hKey; // [rsp+20h] [rbp-28h] BYREF
  HKEY v17; // [rsp+28h] [rbp-20h] BYREF
  void *v18; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char v20; // [rsp+68h] [rbp+20h] BYREF
  char v21; // [rsp+69h] [rbp+21h]

  v3 = ImpersonateSelf(SecurityImpersonation);
  try
  {
    if ( !v3 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\raiiutils.cpp",
        v4);
    NewUserRegHive = AdjustPrivilegesToLoadNewUserRegHive();
    v6 = NewUserRegHive;
    if ( NewUserRegHive >= 0 )
    {
      v9 = LoadNewUserRegHive();
      v10 = v9;
      if ( v9 >= 0 )
      {
        v21 = 1;
        OpenRegKey(&v17, -2147483645, L"NewUserDefaultHive");
        v11 = v17;
        OpenRegKey(&hKey, v17, L"Control Panel\\Desktop");
        CreateDeprecatedLanguageSettingsMigrator(&v18);
        v12 = a2;
        v13 = (char *)v18;
        v14 = DeprecatedLanguageSettingsMigrator::MigrateLanguageSetting(
                v18,
                v12,
                L"NewUserPreferredUILanguages",
                &hKey);
        v15 = v14;
        if ( v14 >= 0 )
        {
          if ( v13 )
          {
            std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(v13 + 88);
            std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(v13 + 72);
            std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(v13 + 24);
            std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(v13 + 8);
            operator delete(v13, 0x80u);
          }
          if ( hKey )
            RegCloseKey(hKey);
          if ( v11 )
            RegCloseKey(v11);
          wil::details::lambda_call<_lambda_e7fb553c0e7dd79386aa60b8449ebe8a_>::~lambda_call<_lambda_e7fb553c0e7dd79386aa60b8449ebe8a_>(&v20);
          RevertToSelf();
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x141,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deprecatedlanguagemigrationtask.cpp",
            (const char *)(unsigned int)v14,
            (int)hKey);
          if ( v13 )
          {
            std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(v13 + 88);
            std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(v13 + 72);
            std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(v13 + 24);
            std::list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>::~list<std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>>(v13 + 8);
            operator delete(v13, 0x80u);
          }
          if ( hKey )
            RegCloseKey(hKey);
          if ( v11 )
            RegCloseKey(v11);
          wil::details::lambda_call<_lambda_e7fb553c0e7dd79386aa60b8449ebe8a_>::~lambda_call<_lambda_e7fb553c0e7dd79386aa60b8449ebe8a_>(&v20);
          RevertToSelf();
          result = v15;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deprecatedlanguagemigrationtask.cpp",
          (const char *)(unsigned int)v9,
          (int)hKey);
        RevertToSelf();
        result = v10;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x135,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deprecatedlanguagemigrationtask.cpp",
        (const char *)(unsigned int)NewUserRegHive,
        (int)hKey);
      RevertToSelf();
      result = v6;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x144,
                           (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deprecat"
                                         "edlanguagemigrationtask.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18005c350  mov     [rsp+arg_0], rbx
0x18005c355  mov     [rsp+arg_8], rsi
0x18005c35a  push    rdi
0x18005c35b  sub     rsp, 40h
0x18005c35f  mov     rdi, rdx
0x18005c362  mov     ecx, 2; ImpersonationLevel
0x18005c367  call    cs:__imp_ImpersonateSelf
0x18005c36d  mov     rcx, [rsp+48h]; this
0x18005c372  test    eax, eax
0x18005c374  jz      loc_18005C550
0x18005c37a  mov     byte ptr [rsp+48h+arg_10], 1
0x18005c37f  call    ?AdjustPrivilegesToLoadNewUserRegHive@@YAJXZ; AdjustPrivilegesToLoadNewUserRegHive(void)
0x18005c384  mov     ebx, eax
0x18005c386  test    eax, eax
0x18005c388  jns     short loc_18005C3B1
0x18005c38a  mov     rcx, [rsp+48h]; this
0x18005c38f  mov     r9d, eax; char *
0x18005c392  lea     r8, aOnecoreBaseLan_30; "onecore\\base\\languageoverlay\\service"...
0x18005c399  mov     edx, 135h; void *
0x18005c39e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c3a3  nop
0x18005c3a4  call    cs:__imp_RevertToSelf
0x18005c3aa  mov     eax, ebx
0x18005c3ac  jmp     loc_18005C540
0x18005c3b1  call    ?LoadNewUserRegHive@@YAJXZ; LoadNewUserRegHive(void)
0x18005c3b6  mov     ebx, eax
0x18005c3b8  test    eax, eax
0x18005c3ba  jns     short loc_18005C3E3
0x18005c3bc  mov     rcx, [rsp+48h]; this
0x18005c3c1  mov     r9d, eax; char *
0x18005c3c4  lea     r8, aOnecoreBaseLan_30; "onecore\\base\\languageoverlay\\service"...
0x18005c3cb  mov     edx, 137h; void *
0x18005c3d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c3d5  nop
0x18005c3d6  call    cs:__imp_RevertToSelf
0x18005c3dc  mov     eax, ebx
0x18005c3de  jmp     loc_18005C540
0x18005c3e3  mov     [rsp+48h+arg_19], 1
0x18005c3e8  lea     r8, SubKey; "NewUserDefaultHive"
0x18005c3ef  mov     rdx, 0FFFFFFFF80000003h
0x18005c3f6  lea     rcx, [rsp+48h+var_20]
0x18005c3fb  call    ?OpenRegKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBGK@Z; OpenRegKey(HKEY__ *,ushort const *,ulong)
0x18005c400  nop
0x18005c401  lea     r8, aControlPanelDe; "Control Panel\\Desktop"
0x18005c408  mov     rbx, [rsp+48h+var_20]
0x18005c40d  mov     rdx, rbx
0x18005c410  lea     rcx, [rsp+48h+hKey]
0x18005c415  call    ?OpenRegKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBGK@Z; OpenRegKey(HKEY__ *,ushort const *,ulong)
0x18005c41a  nop
0x18005c41b  lea     rcx, [rsp+48h+var_18]
0x18005c420  call    ?CreateDeprecatedLanguageSettingsMigrator@@YA?AV?$unique_ptr@VDeprecatedLanguageSettingsMigrator@@U?$default_delete@VDeprecatedLanguageSettingsMigrator@@@std@@@std@@XZ; CreateDeprecatedLanguageSettingsMigrator(void)
0x18005c425  lea     r9, [rsp+48h+hKey]
0x18005c42a  lea     r8, aNewuserpreferr; "NewUserPreferredUILanguages"
0x18005c431  mov     rdx, rdi
0x18005c434  mov     rdi, [rsp+48h+var_18]
0x18005c439  mov     rcx, rdi
0x18005c43c  call    ?MigrateLanguageSetting@DeprecatedLanguageSettingsMigrator@@QEAAJAEAVDeprecatedLanguageMigrationTaskActivity@LanguageOverlayTraceProvider@@PEBGAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; DeprecatedLanguageSettingsMigrator::MigrateLanguageSetting(LanguageOverlayTraceProvider::DeprecatedLanguageMigrationTaskActivity &,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &)
0x18005c441  mov     esi, eax
0x18005c443  test    eax, eax
0x18005c445  jns     loc_18005C4D0
0x18005c44b  mov     rcx, [rsp+48h]; this
0x18005c450  mov     r9d, eax; char *
0x18005c453  lea     r8, aOnecoreBaseLan_30; "onecore\\base\\languageoverlay\\service"...
0x18005c45a  mov     edx, 141h; void *
0x18005c45f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c464  test    rdi, rdi
0x18005c467  jz      short loc_18005C49B
0x18005c469  lea     rcx, [rdi+58h]
0x18005c46d  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x18005c472  lea     rcx, [rdi+48h]
0x18005c476  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x18005c47b  lea     rcx, [rdi+18h]
0x18005c47f  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x18005c484  lea     rcx, [rdi+8]
0x18005c488  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x18005c48d  mov     edx, 80h; unsigned __int64
0x18005c492  mov     rcx, rdi; void *
0x18005c495  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005c49a  nop
0x18005c49b  mov     rcx, [rsp+48h+hKey]; hKey
0x18005c4a0  test    rcx, rcx
0x18005c4a3  jz      short loc_18005C4AC
0x18005c4a5  call    cs:__imp_RegCloseKey
0x18005c4ab  nop
0x18005c4ac  test    rbx, rbx
0x18005c4af  jz      short loc_18005C4BB
0x18005c4b1  mov     rcx, rbx; hKey
0x18005c4b4  call    cs:__imp_RegCloseKey
0x18005c4ba  nop
0x18005c4bb  lea     rcx, [rsp+48h+arg_18]
0x18005c4c0  call    ??1?$lambda_call@V_lambda_e7fb553c0e7dd79386aa60b8449ebe8a_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_e7fb553c0e7dd79386aa60b8449ebe8a_>::~lambda_call<_lambda_e7fb553c0e7dd79386aa60b8449ebe8a_>(void)
0x18005c4c5  nop
0x18005c4c6  call    cs:__imp_RevertToSelf
0x18005c4cc  mov     eax, esi
0x18005c4ce  jmp     short loc_18005C540
0x18005c4d0  test    rdi, rdi
0x18005c4d3  jz      short loc_18005C507
0x18005c4d5  lea     rcx, [rdi+58h]
0x18005c4d9  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x18005c4de  lea     rcx, [rdi+48h]
0x18005c4e2  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x18005c4e7  lea     rcx, [rdi+18h]
0x18005c4eb  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$shared_ptr@VExecutionGate@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::shared_ptr<ExecutionGate>>>,std::_Iterator_base0>>>(void)
0x18005c4f0  lea     rcx, [rdi+8]
0x18005c4f4  call    ??1?$list@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>::~list<std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>>(void)
0x18005c4f9  mov     edx, 80h; unsigned __int64
0x18005c4fe  mov     rcx, rdi; void *
0x18005c501  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005c506  nop
0x18005c507  mov     rcx, [rsp+48h+hKey]; hKey
0x18005c50c  test    rcx, rcx
0x18005c50f  jz      short loc_18005C518
0x18005c511  call    cs:__imp_RegCloseKey
0x18005c517  nop
0x18005c518  test    rbx, rbx
0x18005c51b  jz      short loc_18005C527
0x18005c51d  mov     rcx, rbx; hKey
0x18005c520  call    cs:__imp_RegCloseKey
0x18005c526  nop
0x18005c527  lea     rcx, [rsp+48h+arg_18]
0x18005c52c  call    ??1?$lambda_call@V_lambda_e7fb553c0e7dd79386aa60b8449ebe8a_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_e7fb553c0e7dd79386aa60b8449ebe8a_>::~lambda_call<_lambda_e7fb553c0e7dd79386aa60b8449ebe8a_>(void)
0x18005c531  nop
0x18005c532  call    cs:__imp_RevertToSelf
0x18005c538  xor     eax, eax
0x18005c53a  jmp     short loc_18005C540
0x18005c53c  mov     eax, [rsp+48h+arg_10]
0x18005c540  mov     rbx, [rsp+48h+arg_0]
0x18005c545  mov     rsi, [rsp+48h+arg_8]
0x18005c54a  add     rsp, 40h
0x18005c54e  pop     rdi
0x18005c54f  retn
0x18005c550  lea     r8, aOnecoreBaseLan_1; "onecore\\base\\languageoverlay\\service"...
0x18005c557  lea     edx, [rax+43h]; void *
0x18005c55a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
