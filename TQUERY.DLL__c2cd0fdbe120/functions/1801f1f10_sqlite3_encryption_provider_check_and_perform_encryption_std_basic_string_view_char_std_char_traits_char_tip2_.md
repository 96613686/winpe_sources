# sqlite3_encryption_provider::check_and_perform_encryption(std::basic_string_view<char,std::char_traits<char>>,tip2::tip_test<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>> &)

- ea: `0x1801f1f10`
- end: `0x1801f22ba`
- name: `?check_and_perform_encryption@sqlite3_encryption_provider@@SA?AW4EncryptionPhase@FirstUpgradeEncryptionUtil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@AEAV?$tip_test@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@tip2@@@Z`
- size: `938`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801f1640`

## callees

- `0x18008b084`
- `0x180098390`
- `0x1800983c0`
- `0x180099540`
- `0x18009bcac`
- `0x18009e1dc`
- `0x180147154`
- `0x180188d90`
- `0x1801a6e2c`
- `0x1801f01ec`
- `0x1801f09d8`
- `0x1801f0a74`
- `0x1801f0b3c`
- `0x1801f0b84`
- `0x1801f0be0`
- `0x1801f1100`
- `0x1801f1460`
- `0x1801f152c`
- `0x1801f1c30`
- `0x1801f1f10`
- `0x1801f25f4`

## import_xrefs

- `msvcp_win!_Thrd_detach` at `0x1801f2128`
- `msvcp_win!_Thrd_detach` at `0x1801f2128`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1801f2112`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1801f2137`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1801f2112`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1801f2137`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801f2017`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801f2017`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801f2044`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801f204d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801f2044`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801f204d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1801f2079`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1801f2079`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801f1f93`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801f1f93`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall sqlite3_encryption_provider::check_and_perform_encryption(_Thrd_t *a1, __int64 a2)
{
  char EncryptionPhaseToPerformForDB; // al
  char v5; // si
  const char *v6; // r9
  __int64 v7; // rax
  HANDLE v8; // rbx
  const char *v9; // r9
  HANDLE CurrentProcess; // rdi
  HANDLE v11; // rax
  BOOL v12; // eax
  const char *v13; // r9
  __int64 v14; // rax
  const char *v15; // r9
  char DBType; // al
  __int64 v17; // rdx
  char GenericDBType; // bl
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // rax
  char v23; // [rsp+40h] [rbp-E8h]
  HANDLE v24; // [rsp+48h] [rbp-E0h] BYREF
  _Thrd_t v25; // [rsp+50h] [rbp-D8h] BYREF
  _Thrd_t v26; // [rsp+60h] [rbp-C8h] BYREF
  HANDLE TargetHandle; // [rsp+70h] [rbp-B8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp-B0h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+80h] [rbp-A8h] BYREF
  _OWORD v30[2]; // [rsp+98h] [rbp-90h] BYREF
  HANDLE v31; // [rsp+B8h] [rbp-70h]
  _BYTE v32[32]; // [rsp+C0h] [rbp-68h] BYREF
  _BYTE v33[32]; // [rsp+E0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v25 = *a1;
  EncryptionPhaseToPerformForDB = FirstUpgradeEncryptionUtil::GetEncryptionPhaseToPerformForDB(&v25);
  v5 = EncryptionPhaseToPerformForDB;
  v23 = EncryptionPhaseToPerformForDB;
  if ( EncryptionPhaseToPerformForDB == 1 )
  {
    v25 = *a1;
    FirstUpgradeEncryptionUtil::GetBlockingEventName(v33, &v25);
    SecurityDescriptor = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;SY)", 1u, &SecurityDescriptor, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\sqlite\\include\\sqlite3_encryption_provider.h",
        v6);
    *(_QWORD *)&EventAttributes.nLength = 24;
    *(_QWORD *)&EventAttributes.bInheritHandle = 0;
    EventAttributes.lpSecurityDescriptor = SecurityDescriptor;
    v25 = *(_Thrd_t *)std::string::operator std::string_view(v33, &v26);
    v7 = from_utf8(v32, &v25);
    if ( *(_QWORD *)(v7 + 24) > 7u )
      v7 = *(_QWORD *)v7;
    v8 = CreateEventW(&EventAttributes, 1, 0, (LPCWSTR)v7);
    v24 = v8;
    std::wstring::_Tidy_deallocate(v32);
    if ( !v8 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\sqlite\\include\\sqlite3_encryption_provider.h",
        v9);
    TargetHandle = 0;
    CurrentProcess = GetCurrentProcess();
    v11 = GetCurrentProcess();
    v12 = DuplicateHandle(v11, v8, CurrentProcess, &TargetHandle, 0, 0, 2u);
    try
    {
      if ( !v12 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x63,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\sqlite\\include\\sqlite3_encryption_provider.h",
          v13);
      v14 = std::string::string(v32, a1);
      v30[0] = *(_OWORD *)v14;
      v30[1] = *(_OWORD *)(v14 + 16);
      *(_QWORD *)(v14 + 16) = 0;
      *(_QWORD *)(v14 + 24) = 15;
      *(_BYTE *)v14 = 0;
      v31 = TargetHandle;
      TargetHandle = 0;
      std::thread::_Start<_lambda_eb34120dbdb1d46a3c04bc19619e7615_,>(&v25, v30);
      _lambda_eb34120dbdb1d46a3c04bc19619e7615_::~_lambda_eb34120dbdb1d46a3c04bc19619e7615_((_lambda_eb34120dbdb1d46a3c04bc19619e7615_ *)v30);
      std::string::_Tidy_deallocate(v32);
      if ( !v25._Id )
        std::_Throw_Cpp_error(1);
      v26 = v25;
      if ( _Thrd_detach(&v26) )
        std::_Throw_Cpp_error(1);
      v25 = 0;
      std::thread::~thread((std::thread *)&v25);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TargetHandle);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\sqlite\\include\\sqlite3_encryption_provider.h",
        v15);
      SetEvent(v24);
      v5 = v23;
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v24);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&SecurityDescriptor);
    std::string::_Tidy_deallocate(v33);
  }
  else if ( EncryptionPhaseToPerformForDB == 2 )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::operator->(
                            a2,
                            &v24)
             + 281LL) = 2;
    tip2::test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::~test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>(&v24);
    v26 = *a1;
    DBType = FirstUpgradeEncryptionUtil::GetDBType(&v26);
    v26 = *a1;
    LOBYTE(v17) = DBType;
    GenericDBType = FirstUpgradeEncryptionUtil::GetGenericDBType(&v26, v17);
    v19 = tip2::tip_test<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::operator->(
            a2,
            &v24);
    *(_BYTE *)(*(_QWORD *)v19 + 282LL) |= GenericDBType;
    tip2::test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::~test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>(&v24);
    v26 = *a1;
    sqlite3_encryption_provider::first_upgrade_encrypt(&v26);
    v26 = *a1;
    LOBYTE(v20) = 3;
    FirstUpgradeEncryptionUtil::SetEncryptionPhaseCompletedForDB(
      `FirstUpgradeEncryptionUtil::Instance'::`2'::instance,
      &v26,
      v20);
    v21 = tip2::tip_test<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::operator->(
            a2,
            &v24);
    *(_BYTE *)(*(_QWORD *)v21 + 283LL) |= GenericDBType;
    tip2::test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::~test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>(&v24);
  }
  return v5;
}

```

## disassembly

```asm
0x1801f1f10  mov     [rsp+arg_10], rbx
0x1801f1f15  push    rsi
0x1801f1f16  push    rdi
0x1801f1f17  push    r14
0x1801f1f19  sub     rsp, 110h
0x1801f1f20  mov     rax, cs:__security_cookie
0x1801f1f27  xor     rax, rsp
0x1801f1f2a  mov     [rsp+128h+var_28], rax
0x1801f1f32  mov     rdi, rdx
0x1801f1f35  mov     r14, rcx
0x1801f1f38  movaps  xmm0, xmmword ptr [rcx]
0x1801f1f3b  movdqa  [rsp+128h+var_D8], xmm0
0x1801f1f41  lea     rcx, [rsp+128h+var_D8]
0x1801f1f46  call    ?GetEncryptionPhaseToPerformForDB@FirstUpgradeEncryptionUtil@@SA?AW4EncryptionPhase@1@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; FirstUpgradeEncryptionUtil::GetEncryptionPhaseToPerformForDB(std::string_view)
0x1801f1f4b  mov     sil, al
0x1801f1f4e  mov     [rsp+128h+var_E8], al
0x1801f1f52  cmp     al, 1
0x1801f1f54  jnz     loc_1801F218B
0x1801f1f5a  movaps  xmm0, xmmword ptr [r14]
0x1801f1f5e  movdqa  [rsp+128h+var_D8], xmm0
0x1801f1f64  lea     rdx, [rsp+128h+var_D8]
0x1801f1f69  lea     rcx, [rsp+128h+var_48]
0x1801f1f71  call    ?GetBlockingEventName@FirstUpgradeEncryptionUtil@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@3@@Z; FirstUpgradeEncryptionUtil::GetBlockingEventName(std::string_view)
0x1801f1f76  nop
0x1801f1f77  mov     [rsp+128h+SecurityDescriptor], 0
0x1801f1f80  xor     r9d, r9d; SecurityDescriptorSize
0x1801f1f83  lea     r8, [rsp+128h+SecurityDescriptor]; SecurityDescriptor
0x1801f1f88  lea     edx, [r9+1]; StringSDRevision
0x1801f1f8c  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)"
0x1801f1f93  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1801f1f99  mov     rcx, [rsp+128h]; this
0x1801f1fa1  test    eax, eax
0x1801f1fa3  jz      loc_1801F2279
0x1801f1fa9  mov     qword ptr [rsp+128h+EventAttributes.nLength], 18h
0x1801f1fb5  mov     qword ptr [rsp+128h+EventAttributes.bInheritHandle], 0
0x1801f1fc1  mov     rax, [rsp+128h+SecurityDescriptor]
0x1801f1fc6  mov     [rsp+128h+EventAttributes.lpSecurityDescriptor], rax
0x1801f1fce  lea     rdx, [rsp+128h+var_C8]
0x1801f1fd3  lea     rcx, [rsp+128h+var_48]
0x1801f1fdb  call    ??B?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string_view@DU?$char_traits@D@std@@@1@XZ; std::string::operator std::string_view(void)
0x1801f1fe0  movups  xmm0, xmmword ptr [rax]
0x1801f1fe3  movdqu  [rsp+128h+var_D8], xmm0
0x1801f1fe9  lea     rdx, [rsp+128h+var_D8]
0x1801f1fee  lea     rcx, [rsp+128h+var_68]
0x1801f1ff6  call    ?from_utf8@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@2@@Z; from_utf8(std::string_view)
0x1801f1ffb  cmp     qword ptr [rax+18h], 7
0x1801f2000  jbe     short loc_1801F2005
0x1801f2002  mov     rax, [rax]
0x1801f2005  mov     r9, rax; lpName
0x1801f2008  xor     r8d, r8d; bInitialState
0x1801f200b  lea     edx, [r8+1]; bManualReset
0x1801f200f  lea     rcx, [rsp+128h+EventAttributes]; lpEventAttributes
0x1801f2017  call    cs:__imp_CreateEventW
0x1801f201d  mov     rbx, rax
0x1801f2020  mov     [rsp+128h+var_E0], rax
0x1801f2025  lea     rcx, [rsp+128h+var_68]
0x1801f202d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801f2032  test    rbx, rbx
0x1801f2035  jz      loc_1801F2289
0x1801f203b  mov     [rsp+128h+TargetHandle], 0
0x1801f2044  call    cs:__imp_GetCurrentProcess
0x1801f204a  mov     rdi, rax
0x1801f204d  call    cs:__imp_GetCurrentProcess
0x1801f2053  mov     [rsp+128h+dwOptions], 2; dwOptions
0x1801f205b  mov     [rsp+128h+bInheritHandle], 0; bInheritHandle
0x1801f2063  mov     [rsp+128h+dwDesiredAccess], 0; dwDesiredAccess
0x1801f206b  lea     r9, [rsp+128h+TargetHandle]; lpTargetHandle
0x1801f2070  mov     r8, rdi; hTargetProcessHandle
0x1801f2073  mov     rdx, rbx; hSourceHandle
0x1801f2076  mov     rcx, rax; hSourceProcessHandle
0x1801f2079  call    cs:__imp_DuplicateHandle
0x1801f207f  test    eax, eax
0x1801f2081  jz      loc_1801F22A1
0x1801f2087  mov     rdx, r14
0x1801f208a  lea     rcx, [rsp+128h+var_68]
0x1801f2092  call    ??$?0V?$basic_string_view@DU?$char_traits@D@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV?$basic_string_view@DU?$char_traits@D@std@@@1@AEBV?$allocator@D@1@@Z; std::string::string(std::string_view const &,std::allocator<char> const &)
0x1801f2097  nop
0x1801f2098  movups  xmm1, xmmword ptr [rax]
0x1801f209b  movups  [rsp+128h+var_90], xmm1
0x1801f20a3  movups  xmm0, xmmword ptr [rax+10h]
0x1801f20a7  movups  [rsp+128h+var_80], xmm0
0x1801f20af  mov     qword ptr [rax+10h], 0
0x1801f20b7  mov     qword ptr [rax+18h], 0Fh
0x1801f20bf  mov     byte ptr [rax], 0
0x1801f20c2  mov     rax, [rsp+128h+TargetHandle]
0x1801f20c7  mov     [rsp+128h+var_70], rax
0x1801f20cf  mov     [rsp+128h+TargetHandle], 0
0x1801f20d8  lea     rdx, [rsp+128h+var_90]
0x1801f20e0  lea     rcx, [rsp+128h+var_D8]
0x1801f20e5  call    ??$_Start@V_lambda_eb34120dbdb1d46a3c04bc19619e7615_@@$$V@thread@std@@AEAAX$$QEAV_lambda_eb34120dbdb1d46a3c04bc19619e7615_@@@Z; std::thread::_Start<_lambda_eb34120dbdb1d46a3c04bc19619e7615_,>(_lambda_eb34120dbdb1d46a3c04bc19619e7615_ &&)
0x1801f20ea  nop
0x1801f20eb  lea     rcx, [rsp+128h+var_90]; this
0x1801f20f3  call    ??1_lambda_eb34120dbdb1d46a3c04bc19619e7615_@@QEAA@XZ; _lambda_eb34120dbdb1d46a3c04bc19619e7615_::~_lambda_eb34120dbdb1d46a3c04bc19619e7615_(void)
0x1801f20f8  nop
0x1801f20f9  lea     rcx, [rsp+128h+var_68]
0x1801f2101  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801f2106  cmp     dword ptr [rsp+128h+var_D8+8], 0
0x1801f210b  jnz     short loc_1801F2118
0x1801f210d  mov     ecx, 1
0x1801f2112  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1801f2118  movaps  xmm0, [rsp+128h+var_D8]
0x1801f211d  movdqa  xmmword ptr [rsp+128h+var_C8._Hnd], xmm0
0x1801f2123  lea     rcx, [rsp+128h+var_C8]; _Thrd_t
0x1801f2128  call    cs:__imp__Thrd_detach
0x1801f212e  test    eax, eax
0x1801f2130  jz      short loc_1801F213D
0x1801f2132  mov     ecx, 1
0x1801f2137  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1801f213d  xorps   xmm0, xmm0
0x1801f2140  movdqa  [rsp+128h+var_D8], xmm0
0x1801f2146  lea     rcx, [rsp+128h+var_D8]; this
0x1801f214b  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x1801f2150  nop
0x1801f2151  lea     rcx, [rsp+128h+TargetHandle]
0x1801f2156  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801f215b  nop
0x1801f215c  jmp     short loc_1801F2163
0x1801f215e  mov     sil, [rsp+128h+var_E8]
0x1801f2163  lea     rcx, [rsp+128h+var_E0]
0x1801f2168  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801f216d  nop
0x1801f216e  lea     rcx, [rsp+128h+SecurityDescriptor]
0x1801f2173  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1801f2178  nop
0x1801f2179  lea     rcx, [rsp+128h+var_48]
0x1801f2181  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801f2186  jmp     loc_1801F2252
0x1801f218b  cmp     al, 2
0x1801f218d  jnz     loc_1801F2252
0x1801f2193  lea     rdx, [rsp+128h+var_E0]
0x1801f2198  mov     rcx, rdi
0x1801f219b  call    ??C?$tip_test@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::operator->(void)
0x1801f21a0  mov     rcx, [rax]
0x1801f21a3  mov     byte ptr [rcx+119h], 2
0x1801f21aa  lea     rcx, [rsp+128h+var_E0]
0x1801f21af  call    ??1?$test_data_control@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::~test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>(void)
0x1801f21b4  movaps  xmm0, xmmword ptr [r14]
0x1801f21b8  movdqa  xmmword ptr [rsp+128h+var_C8._Hnd], xmm0
0x1801f21be  lea     rcx, [rsp+128h+var_C8]
0x1801f21c3  call    ?GetDBType@FirstUpgradeEncryptionUtil@@SA?AW4DBTypes@1@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; FirstUpgradeEncryptionUtil::GetDBType(std::string_view)
0x1801f21c8  movaps  xmm0, xmmword ptr [r14]
0x1801f21cc  movdqa  xmmword ptr [rsp+128h+var_C8._Hnd], xmm0
0x1801f21d2  mov     dl, al
0x1801f21d4  lea     rcx, [rsp+128h+var_C8]
0x1801f21d9  call    ?GetGenericDBType@FirstUpgradeEncryptionUtil@@SA?AW4FirstUpgradeEncryptionDBs@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@W4DBTypes@1@@Z; FirstUpgradeEncryptionUtil::GetGenericDBType(std::string_view,FirstUpgradeEncryptionUtil::DBTypes)
0x1801f21de  mov     bl, al
0x1801f21e0  lea     rdx, [rsp+128h+var_E0]
0x1801f21e5  mov     rcx, rdi
0x1801f21e8  call    ??C?$tip_test@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::operator->(void)
0x1801f21ed  mov     rdx, [rax]
0x1801f21f0  or      [rdx+11Ah], bl
0x1801f21f6  lea     rcx, [rsp+128h+var_E0]
0x1801f21fb  call    ??1?$test_data_control@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::~test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>(void)
0x1801f2200  movaps  xmm0, xmmword ptr [r14]
0x1801f2204  movdqa  xmmword ptr [rsp+128h+var_C8._Hnd], xmm0
0x1801f220a  lea     rcx, [rsp+128h+var_C8]
0x1801f220f  call    ?first_upgrade_encrypt@sqlite3_encryption_provider@@SAXV?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; sqlite3_encryption_provider::first_upgrade_encrypt(std::string_view)
0x1801f2214  movaps  xmm0, xmmword ptr [r14]
0x1801f2218  movdqa  xmmword ptr [rsp+128h+var_C8._Hnd], xmm0
0x1801f221e  mov     r8b, 3
0x1801f2221  lea     rdx, [rsp+128h+var_C8]
0x1801f2226  lea     rcx, ?instance@?1??Instance@FirstUpgradeEncryptionUtil@@SAAEAU2@XZ@4U2@A; FirstUpgradeEncryptionUtil `FirstUpgradeEncryptionUtil::Instance(void)'::`2'::instance
0x1801f222d  call    ?SetEncryptionPhaseCompletedForDB@FirstUpgradeEncryptionUtil@@QEAAXV?$basic_string_view@DU?$char_traits@D@std@@@std@@W4EncryptionPhase@1@@Z; FirstUpgradeEncryptionUtil::SetEncryptionPhaseCompletedForDB(std::string_view,FirstUpgradeEncryptionUtil::EncryptionPhase)
0x1801f2232  lea     rdx, [rsp+128h+var_E0]
0x1801f2237  mov     rcx, rdi
0x1801f223a  call    ??C?$tip_test@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::operator->(void)
0x1801f223f  mov     rcx, [rax]
0x1801f2242  or      [rcx+11Bh], bl
0x1801f2248  lea     rcx, [rsp+128h+var_E0]
0x1801f224d  call    ??1?$test_data_control@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::~test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>(void)
0x1801f2252  mov     al, sil
0x1801f2255  mov     rcx, [rsp+128h+var_28]
0x1801f225d  xor     rcx, rsp; StackCookie
0x1801f2260  call    __security_check_cookie
0x1801f2265  mov     rbx, [rsp+128h+arg_10]
0x1801f226d  add     rsp, 110h
0x1801f2274  pop     r14
0x1801f2276  pop     rdi
0x1801f2277  pop     rsi
0x1801f2278  retn
0x1801f2279  lea     r8, aOnecoreuapBase_48; "onecoreuap\\base\\appmodel\\Search\\sql"...
0x1801f2280  lea     edx, [rax+54h]; void *
0x1801f2283  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801f2289  mov     rcx, [rsp+128h]; this
0x1801f2291  lea     r8, aOnecoreuapBase_48; "onecoreuap\\base\\appmodel\\Search\\sql"...
0x1801f2298  lea     edx, [rbx+5Ch]; void *
0x1801f229b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801f22a1  mov     rcx, [rsp+128h]; this
0x1801f22a9  lea     r8, aOnecoreuapBase_48; "onecoreuap\\base\\appmodel\\Search\\sql"...
0x1801f22b0  lea     edx, [rax+63h]; void *
0x1801f22b3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
