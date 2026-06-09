# sqlite3_encryption_provider::check_and_perform_encryption(std::basic_string_view<char,std::char_traits<char>>,tip2::tip_test<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>> &)

- ea: `0x180122de4`
- end: `0x18012316e`
- name: `?check_and_perform_encryption@sqlite3_encryption_provider@@SA?AW4EncryptionPhase@FirstUpgradeEncryptionUtil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@AEAV?$tip_test@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@tip2@@@Z`
- size: `906`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800ccddc`

## callees

- `0x180012120`
- `0x18005e788`
- `0x18006e16c`
- `0x180083e54`
- `0x180085978`
- `0x1800865e8`
- `0x180086654`
- `0x1800cdc48`
- `0x1800cdc80`
- `0x1800e95f0`
- `0x18010822c`
- `0x180122de4`
- `0x180123174`
- `0x1801231c4`
- `0x1801244c0`
- `0x18014694c`
- `0x18016ad90`
- `0x18016bd8c`
- `0x18016c408`
- `0x18016c4b4`
- `0x180170454`
- `0x18017068c`
- `0x180173fb8`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180123007`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18012302c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180123007`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18012302c`
- `msvcp_win!_Thrd_detach` at `0x18012301d`
- `msvcp_win!_Thrd_detach` at `0x18012301d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180122eff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180122eff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180122f40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180122f49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180122f40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180122f49`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180122f75`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180122f75`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180122e6f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180122e6f`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall sqlite3_encryption_provider::check_and_perform_encryption(_Thrd_t *a1, __int64 a2)
{
  char EncryptionPhaseToPerformForDB; // al
  char v5; // si
  PSECURITY_DESCRIPTOR *v6; // rax
  const char *v7; // r9
  __int64 v8; // rax
  HANDLE v9; // rbx
  const char *v10; // r9
  HANDLE CurrentProcess; // rdi
  HANDLE v12; // rax
  const char *v13; // r9
  __int64 v14; // rax
  const char *v15; // r9
  char DBType; // al
  __int64 v17; // rdx
  char GenericDBType; // bl
  __int64 v19; // rax
  __int64 v20; // rax
  char v22; // [rsp+40h] [rbp-E8h]
  HANDLE v23; // [rsp+48h] [rbp-E0h] BYREF
  _Thrd_t v24; // [rsp+50h] [rbp-D8h] BYREF
  _Thrd_t v25; // [rsp+60h] [rbp-C8h] BYREF
  HANDLE TargetHandle; // [rsp+70h] [rbp-B8h] BYREF
  void *v27; // [rsp+78h] [rbp-B0h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+80h] [rbp-A8h] BYREF
  _BYTE v29[32]; // [rsp+98h] [rbp-90h] BYREF
  _BYTE v30[32]; // [rsp+B8h] [rbp-70h] BYREF
  HANDLE v31; // [rsp+D8h] [rbp-50h]
  _BYTE v32[32]; // [rsp+E0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v24 = *a1;
  EncryptionPhaseToPerformForDB = FirstUpgradeEncryptionUtil::GetEncryptionPhaseToPerformForDB(&v24);
  v5 = EncryptionPhaseToPerformForDB;
  v22 = EncryptionPhaseToPerformForDB;
  if ( EncryptionPhaseToPerformForDB == 1 )
  {
    v24 = *a1;
    FirstUpgradeEncryptionUtil::GetBlockingEventName(v32, &v24);
    v27 = 0;
    v6 = (PSECURITY_DESCRIPTOR *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&v27);
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;SY)", 1u, v6, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\sqlite\\include\\sqlite3_encryption_provider.h",
        v7);
    *(_QWORD *)&EventAttributes.nLength = 24;
    *(_QWORD *)&EventAttributes.bInheritHandle = 0;
    EventAttributes.lpSecurityDescriptor = v27;
    v24 = *(_Thrd_t *)std::string::operator std::string_view(v32, &v25);
    v8 = from_utf8(v29, &v24);
    if ( *(_QWORD *)(v8 + 24) > 7u )
      v8 = *(_QWORD *)v8;
    v9 = CreateEventW(&EventAttributes, 1, 0, (LPCWSTR)v8);
    v23 = v9;
    ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v29);
    if ( !v9 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\sqlite\\include\\sqlite3_encryption_provider.h",
        v10);
    try
    {
      TargetHandle = 0;
      CurrentProcess = GetCurrentProcess();
      v12 = GetCurrentProcess();
      if ( !DuplicateHandle(v12, v9, CurrentProcess, &TargetHandle, 0, 0, 2u) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x63,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\sqlite\\include\\sqlite3_encryption_provider.h",
          v13);
      v14 = std::string::string(v29, a1);
      std::string::string(v30, v14);
      v31 = TargetHandle;
      TargetHandle = 0;
      std::thread::_Start<_lambda_eb34120dbdb1d46a3c04bc19619e7615_,>(&v24, v30);
      _lambda_eb34120dbdb1d46a3c04bc19619e7615_::~_lambda_eb34120dbdb1d46a3c04bc19619e7615_((_lambda_eb34120dbdb1d46a3c04bc19619e7615_ *)v30);
      std::string::_Tidy_deallocate(v29);
      if ( !v24._Id )
        std::_Throw_Cpp_error(1);
      v25 = v24;
      if ( _Thrd_detach(&v25) )
        std::_Throw_Cpp_error(1);
      v24 = 0;
      std::thread::~thread((std::thread *)&v24);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TargetHandle);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\sqlite\\include\\sqlite3_encryption_provider.h",
        v15);
      SetEvent(v23);
      v5 = v22;
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v27);
    std::string::_Tidy_deallocate(v32);
  }
  else if ( EncryptionPhaseToPerformForDB == 2 )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::operator->(
                            a2,
                            &v23)
             + 281LL) = 2;
    tip2::test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::~test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>(&v23);
    v25 = *a1;
    DBType = FirstUpgradeEncryptionUtil::GetDBType(&v25);
    v25 = *a1;
    LOBYTE(v17) = DBType;
    GenericDBType = FirstUpgradeEncryptionUtil::GetGenericDBType(&v25, v17);
    v19 = tip2::tip_test<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::operator->(
            a2,
            &v23);
    *(_BYTE *)(*(_QWORD *)v19 + 282LL) |= GenericDBType;
    tip2::test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::~test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>(&v23);
    v25 = *a1;
    sqlite3_encryption_provider::first_upgrade_encrypt(&v25);
    v25 = *a1;
    FirstUpgradeEncryptionUtil::SetEncryptionPhaseCompletedForDB((std::_Mutex_base *)`FirstUpgradeEncryptionUtil::Instance'::`2'::instance);
    v20 = tip2::tip_test<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::operator->(
            a2,
            &v23);
    *(_BYTE *)(*(_QWORD *)v20 + 283LL) |= GenericDBType;
    tip2::test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::~test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>(&v23);
  }
  return v5;
}

```

## disassembly

```asm
0x180122de4  mov     [rsp+arg_10], rbx
0x180122de9  push    rsi
0x180122dea  push    rdi
0x180122deb  push    r14
0x180122ded  sub     rsp, 110h
0x180122df4  mov     rax, cs:__security_cookie
0x180122dfb  xor     rax, rsp
0x180122dfe  mov     [rsp+128h+var_28], rax
0x180122e06  mov     rdi, rdx
0x180122e09  mov     r14, rcx
0x180122e0c  movaps  xmm0, xmmword ptr [rcx]
0x180122e0f  movdqa  [rsp+128h+var_D8], xmm0
0x180122e15  lea     rcx, [rsp+128h+var_D8]
0x180122e1a  call    ?GetEncryptionPhaseToPerformForDB@FirstUpgradeEncryptionUtil@@SA?AW4EncryptionPhase@1@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; FirstUpgradeEncryptionUtil::GetEncryptionPhaseToPerformForDB(std::string_view)
0x180122e1f  mov     sil, al
0x180122e22  mov     [rsp+128h+var_E8], al
0x180122e26  cmp     al, 1
0x180122e28  jnz     loc_180123080
0x180122e2e  movaps  xmm0, xmmword ptr [r14]
0x180122e32  movdqa  [rsp+128h+var_D8], xmm0
0x180122e38  lea     rdx, [rsp+128h+var_D8]
0x180122e3d  lea     rcx, [rsp+128h+var_48]
0x180122e45  call    ?GetBlockingEventName@FirstUpgradeEncryptionUtil@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@3@@Z; FirstUpgradeEncryptionUtil::GetBlockingEventName(std::string_view)
0x180122e4a  nop
0x180122e4b  mov     [rsp+128h+var_B0], 0
0x180122e54  lea     rcx, [rsp+128h+var_B0]
0x180122e59  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x180122e5e  mov     r8, rax; SecurityDescriptor
0x180122e61  xor     r9d, r9d; SecurityDescriptorSize
0x180122e64  lea     edx, [r9+1]; StringSDRevision
0x180122e68  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)"
0x180122e6f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180122e75  mov     rcx, [rsp+128h]; this
0x180122e7d  test    eax, eax
0x180122e7f  jnz     short loc_180122E91
0x180122e81  lea     r8, aOnecoreuapBase_38; "onecoreuap\\base\\appmodel\\Search\\sql"...
0x180122e88  lea     edx, [rax+54h]; void *
0x180122e8b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180122e91  mov     qword ptr [rsp+128h+EventAttributes.nLength], 18h
0x180122e9d  mov     qword ptr [rsp+128h+EventAttributes.bInheritHandle], 0
0x180122ea9  mov     rax, [rsp+128h+var_B0]
0x180122eae  mov     [rsp+128h+EventAttributes.lpSecurityDescriptor], rax
0x180122eb6  lea     rdx, [rsp+128h+var_C8]
0x180122ebb  lea     rcx, [rsp+128h+var_48]
0x180122ec3  call    ??B?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string_view@DU?$char_traits@D@std@@@1@XZ; std::string::operator std::string_view(void)
0x180122ec8  movups  xmm0, xmmword ptr [rax]
0x180122ecb  movdqu  [rsp+128h+var_D8], xmm0
0x180122ed1  lea     rdx, [rsp+128h+var_D8]
0x180122ed6  lea     rcx, [rsp+128h+var_90]
0x180122ede  call    ?from_utf8@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@2@@Z; from_utf8(std::string_view)
0x180122ee3  cmp     qword ptr [rax+18h], 7
0x180122ee8  jbe     short loc_180122EED
0x180122eea  mov     rax, [rax]
0x180122eed  mov     r9, rax; lpName
0x180122ef0  xor     r8d, r8d; bInitialState
0x180122ef3  lea     edx, [r8+1]; bManualReset
0x180122ef7  lea     rcx, [rsp+128h+EventAttributes]; lpEventAttributes
0x180122eff  call    cs:__imp_CreateEventW
0x180122f05  mov     rbx, rax
0x180122f08  mov     [rsp+128h+var_E0], rax
0x180122f0d  lea     rcx, [rsp+128h+var_90]; this
0x180122f15  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x180122f1a  test    rbx, rbx
0x180122f1d  jnz     short loc_180122F37
0x180122f1f  mov     rcx, [rsp+128h]; this
0x180122f27  lea     r8, aOnecoreuapBase_38; "onecoreuap\\base\\appmodel\\Search\\sql"...
0x180122f2e  lea     edx, [rbx+5Ch]; void *
0x180122f31  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180122f37  mov     [rsp+128h+TargetHandle], 0
0x180122f40  call    cs:__imp_GetCurrentProcess
0x180122f46  mov     rdi, rax
0x180122f49  call    cs:__imp_GetCurrentProcess
0x180122f4f  mov     [rsp+128h+dwOptions], 2; dwOptions
0x180122f57  mov     [rsp+128h+bInheritHandle], 0; bInheritHandle
0x180122f5f  mov     [rsp+128h+dwDesiredAccess], 0; dwDesiredAccess
0x180122f67  lea     r9, [rsp+128h+TargetHandle]; lpTargetHandle
0x180122f6c  mov     r8, rdi; hTargetProcessHandle
0x180122f6f  mov     rdx, rbx; hSourceHandle
0x180122f72  mov     rcx, rax; hSourceProcessHandle
0x180122f75  call    cs:__imp_DuplicateHandle
0x180122f7b  test    eax, eax
0x180122f7d  jnz     short loc_180122F96
0x180122f7f  mov     rcx, [rsp+128h]; this
0x180122f87  lea     r8, aOnecoreuapBase_38; "onecoreuap\\base\\appmodel\\Search\\sql"...
0x180122f8e  lea     edx, [rax+63h]; void *
0x180122f91  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180122f96  mov     rdx, r14
0x180122f99  lea     rcx, [rsp+128h+var_90]
0x180122fa1  call    ??$?0V?$basic_string_view@DU?$char_traits@D@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV?$basic_string_view@DU?$char_traits@D@std@@@1@AEBV?$allocator@D@1@@Z; std::string::string(std::string_view const &,std::allocator<char> const &)
0x180122fa6  nop
0x180122fa7  mov     rdx, rax
0x180122faa  lea     rcx, [rsp+128h+var_70]
0x180122fb2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x180122fb7  mov     rcx, [rsp+128h+TargetHandle]
0x180122fbc  mov     [rsp+128h+var_50], rcx
0x180122fc4  mov     [rsp+128h+TargetHandle], 0
0x180122fcd  lea     rdx, [rsp+128h+var_70]
0x180122fd5  lea     rcx, [rsp+128h+var_D8]
0x180122fda  call    ??$_Start@V_lambda_eb34120dbdb1d46a3c04bc19619e7615_@@$$V@thread@std@@AEAAX$$QEAV_lambda_eb34120dbdb1d46a3c04bc19619e7615_@@@Z; std::thread::_Start<_lambda_eb34120dbdb1d46a3c04bc19619e7615_,>(_lambda_eb34120dbdb1d46a3c04bc19619e7615_ &&)
0x180122fdf  nop
0x180122fe0  lea     rcx, [rsp+128h+var_70]; this
0x180122fe8  call    ??1_lambda_eb34120dbdb1d46a3c04bc19619e7615_@@QEAA@XZ; _lambda_eb34120dbdb1d46a3c04bc19619e7615_::~_lambda_eb34120dbdb1d46a3c04bc19619e7615_(void)
0x180122fed  nop
0x180122fee  lea     rcx, [rsp+128h+var_90]
0x180122ff6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180122ffb  cmp     dword ptr [rsp+128h+var_D8+8], 0
0x180123000  jnz     short loc_18012300D
0x180123002  mov     ecx, 1
0x180123007  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18012300d  movaps  xmm0, [rsp+128h+var_D8]
0x180123012  movdqa  xmmword ptr [rsp+128h+var_C8._Hnd], xmm0
0x180123018  lea     rcx, [rsp+128h+var_C8]; _Thrd_t
0x18012301d  call    cs:__imp__Thrd_detach
0x180123023  test    eax, eax
0x180123025  jz      short loc_180123032
0x180123027  mov     ecx, 1
0x18012302c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180123032  xorps   xmm0, xmm0
0x180123035  movdqa  [rsp+128h+var_D8], xmm0
0x18012303b  lea     rcx, [rsp+128h+var_D8]; this
0x180123040  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x180123045  nop
0x180123046  lea     rcx, [rsp+128h+TargetHandle]
0x18012304b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180123050  nop
0x180123051  jmp     short loc_180123058
0x180123053  mov     sil, [rsp+128h+var_E8]
0x180123058  lea     rcx, [rsp+128h+var_E0]
0x18012305d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180123062  nop
0x180123063  lea     rcx, [rsp+128h+var_B0]
0x180123068  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18012306d  nop
0x18012306e  lea     rcx, [rsp+128h+var_48]
0x180123076  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18012307b  jmp     loc_180123147
0x180123080  cmp     al, 2
0x180123082  jnz     loc_180123147
0x180123088  lea     rdx, [rsp+128h+var_E0]
0x18012308d  mov     rcx, rdi
0x180123090  call    ??C?$tip_test@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::operator->(void)
0x180123095  mov     rcx, [rax]
0x180123098  mov     byte ptr [rcx+119h], 2
0x18012309f  lea     rcx, [rsp+128h+var_E0]
0x1801230a4  call    ??1?$test_data_control@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::~test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>(void)
0x1801230a9  movaps  xmm0, xmmword ptr [r14]
0x1801230ad  movdqa  xmmword ptr [rsp+128h+var_C8._Hnd], xmm0
0x1801230b3  lea     rcx, [rsp+128h+var_C8]
0x1801230b8  call    ?GetDBType@FirstUpgradeEncryptionUtil@@SA?AW4DBTypes@1@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; FirstUpgradeEncryptionUtil::GetDBType(std::string_view)
0x1801230bd  movaps  xmm0, xmmword ptr [r14]
0x1801230c1  movdqa  xmmword ptr [rsp+128h+var_C8._Hnd], xmm0
0x1801230c7  mov     dl, al
0x1801230c9  lea     rcx, [rsp+128h+var_C8]
0x1801230ce  call    ?GetGenericDBType@FirstUpgradeEncryptionUtil@@SA?AW4FirstUpgradeEncryptionDBs@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@W4DBTypes@1@@Z; FirstUpgradeEncryptionUtil::GetGenericDBType(std::string_view,FirstUpgradeEncryptionUtil::DBTypes)
0x1801230d3  mov     bl, al
0x1801230d5  lea     rdx, [rsp+128h+var_E0]
0x1801230da  mov     rcx, rdi
0x1801230dd  call    ??C?$tip_test@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::operator->(void)
0x1801230e2  mov     rdx, [rax]
0x1801230e5  or      [rdx+11Ah], bl
0x1801230eb  lea     rcx, [rsp+128h+var_E0]
0x1801230f0  call    ??1?$test_data_control@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::~test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>(void)
0x1801230f5  movaps  xmm0, xmmword ptr [r14]
0x1801230f9  movdqa  xmmword ptr [rsp+128h+var_C8._Hnd], xmm0
0x1801230ff  lea     rcx, [rsp+128h+var_C8]
0x180123104  call    ?first_upgrade_encrypt@sqlite3_encryption_provider@@SAXV?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; sqlite3_encryption_provider::first_upgrade_encrypt(std::string_view)
0x180123109  movaps  xmm0, xmmword ptr [r14]
0x18012310d  movdqa  xmmword ptr [rsp+128h+var_C8._Hnd], xmm0
0x180123113  mov     r8b, 3
0x180123116  lea     rdx, [rsp+128h+var_C8]
0x18012311b  lea     rcx, ?instance@?1??Instance@FirstUpgradeEncryptionUtil@@SAAEAU2@XZ@4U2@A; this
0x180123122  call    ?SetEncryptionPhaseCompletedForDB@FirstUpgradeEncryptionUtil@@QEAAXV?$basic_string_view@DU?$char_traits@D@std@@@std@@W4EncryptionPhase@1@@Z; FirstUpgradeEncryptionUtil::SetEncryptionPhaseCompletedForDB(std::string_view,FirstUpgradeEncryptionUtil::EncryptionPhase)
0x180123127  lea     rdx, [rsp+128h+var_E0]
0x18012312c  mov     rcx, rdi
0x18012312f  call    ??C?$tip_test@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::operator->(void)
0x180123134  mov     rcx, [rax]
0x180123137  or      [rcx+11Bh], bl
0x18012313d  lea     rcx, [rsp+128h+var_E0]
0x180123142  call    ??1?$test_data_control@V?$merged_data@U_tip_FirstUpgradeEncryptionTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>::~test_data_control<tip2::details::merged_data<_tip_FirstUpgradeEncryptionTest,_tip_FirstUpgradeEncryptionTest>>(void)
0x180123147  mov     al, sil
0x18012314a  mov     rcx, [rsp+128h+var_28]
0x180123152  xor     rcx, rsp; StackCookie
0x180123155  call    __security_check_cookie
0x18012315a  mov     rbx, [rsp+128h+arg_10]
0x180123162  add     rsp, 110h
0x180123169  pop     r14
0x18012316b  pop     rdi
0x18012316c  pop     rsi
0x18012316d  retn
```
