# UserRequestPolicyEngine::RunPolicyEvaluation(EvaluationTrigger,std::vector<Microsoft::WRL::ComPtr<IUserAccount>,std::allocator<Microsoft::WRL::ComPtr<IUserAccount>>> &,_GUID const &)

- ea: `0x18001d480`
- end: `0x18001d8f7`
- name: `?RunPolicyEvaluation@UserRequestPolicyEngine@@UEAAJW4EvaluationTrigger@@AEAV?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@AEBU_GUID@@@Z`
- size: `1143`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180003530`
- `0x18000a104`
- `0x18000a1bc`
- `0x18000a584`
- `0x18000ccd4`
- `0x18000cd50`
- `0x180012294`
- `0x18001238c`
- `0x180013dcc`
- `0x1800151cc`
- `0x180015490`
- `0x1800154cc`
- `0x180019b18`
- `0x18001bbe4`
- `0x18001bcfc`
- `0x18001cc7c`
- `0x18001cfb4`
- `0x18001d01c`
- `0x18001d2c0`
- `0x18001d318`
- `0x18001d480`
- `0x18001d900`
- `0x18001d948`
- `0x18001d9f4`
- `0x18001deac`
- `0x18001e0cc`
- `0x180022560`
- `0x1800227e4`
- `0x180026010`

## string_xrefs

- `0x18001d4fb`: `RequestedDeletes\User`
- `0x18001d8a4`: `Loaded user requested delete from the registry: User SID: %ws`
- `0x18001d6ad`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\userrequestpolicyengine.cpp`
- `0x18001d862`: `Loaded device owner requested delete from the registry: User SID: %ws`
- `0x18001d590`: `RequestedDeletes\DeviceOwner`

## pseudocode

```c
// Hidden C++ exception states: #wind=14 #try_helpers=1
__int64 __fastcall UserRequestPolicyEngine::RunPolicyEvaluation(_QWORD **a1, int a2, __int64 a3, __int64 a4)
{
  HKEY SharedPCRegistryKeyIfExists; // rsi
  __int64 KeySubkeyNames; // rax
  _QWORD *v7; // rdi
  _QWORD *i; // rbx
  HKEY v9; // rdi
  __int64 v10; // rax
  _QWORD *v11; // r14
  _QWORD *j; // rbx
  unsigned int v13; // r12d
  unsigned int v14; // r13d
  _QWORD *v15; // rcx
  __int64 *v16; // r15
  __int64 v17; // rdx
  __int64 *v18; // rax
  __int64 v19; // r14
  __int64 (__fastcall *v20)(__int64, __int64 *); // rbx
  int v21; // eax
  __int64 *v22; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  _QWORD *v26; // [rsp+20h] [rbp-2B8h]
  HKEY v28; // [rsp+38h] [rbp-2A0h] BYREF
  __int64 v29; // [rsp+40h] [rbp-298h] BYREF
  HKEY v30; // [rsp+48h] [rbp-290h] BYREF
  __int64 v31; // [rsp+50h] [rbp-288h] BYREF
  _QWORD **v32; // [rsp+58h] [rbp-280h]
  _QWORD *v33; // [rsp+60h] [rbp-278h] BYREF
  __int64 v34; // [rsp+68h] [rbp-270h]
  __int64 v35; // [rsp+70h] [rbp-268h]
  __int64 *k; // [rsp+78h] [rbp-260h]
  HKEY v37; // [rsp+80h] [rbp-258h] BYREF
  HKEY v38; // [rsp+88h] [rbp-250h] BYREF
  __int64 v39; // [rsp+90h] [rbp-248h] BYREF
  _QWORD *v40; // [rsp+98h] [rbp-240h]
  __int64 v41; // [rsp+A0h] [rbp-238h]
  __int64 v42; // [rsp+D0h] [rbp-208h] BYREF
  _QWORD *v43; // [rsp+D8h] [rbp-200h]
  __int64 v44; // [rsp+E0h] [rbp-1F8h]
  _QWORD v45[8]; // [rsp+110h] [rbp-1C8h] BYREF
  _QWORD v46[42]; // [rsp+150h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v32 = a1;
  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v46,
    (__int64)"UserRequestPolicyEvaluation");
  v46[0] = &PolicyTelemetry::UserRequestPolicyEvaluation::`vftable';
  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
    v46,
    a4);
  PolicyTelemetry::UserRequestPolicyEvaluation::StartActivity((PolicyTelemetry::UserRequestPolicyEvaluation *)v46);
  std::wstring::wstring((__int64)v45, (__int64)L"RequestedDeletes\\User");
  SharedPCRegistryKeyIfExists = GetSharedPCRegistryKeyIfExists();
  v38 = SharedPCRegistryKeyIfExists;
  std::wstring::_Tidy_deallocate((__int64)v45);
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(&v42);
  if ( SharedPCRegistryKeyIfExists )
  {
    v28 = SharedPCRegistryKeyIfExists;
    KeySubkeyNames = GetKeySubkeyNames(v45, &v28);
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::operator=(
      (__int64)&v42,
      KeySubkeyNames);
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v45);
    v7 = v43;
    for ( i = (_QWORD *)*v43; i != v7; i = (_QWORD *)*i )
    {
      std::wstring::wstring(v45, i + 2);
      v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      PolicyTelemetry::TraceLoggingInfo("Loaded user requested delete from the registry: User SID: %ws", v25);
      std::wstring::_Tidy_deallocate((__int64)v45);
    }
  }
  std::wstring::wstring((__int64)v45, (__int64)L"RequestedDeletes\\DeviceOwner");
  v9 = GetSharedPCRegistryKeyIfExists();
  v37 = v9;
  std::wstring::_Tidy_deallocate((__int64)v45);
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(&v39);
  if ( v9 )
  {
    v28 = v9;
    v10 = GetKeySubkeyNames(v45, &v28);
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::operator=(
      (__int64)&v39,
      v10);
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v45);
    v11 = v40;
    for ( j = (_QWORD *)*v40; j != v11; j = (_QWORD *)*j )
    {
      std::wstring::wstring(v45, j + 2);
      v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      PolicyTelemetry::TraceLoggingInfo("Loaded device owner requested delete from the registry: User SID: %ws", v24);
      std::wstring::_Tidy_deallocate((__int64)v45);
    }
  }
  v13 = 0;
  v14 = 0;
  if ( v44 || v41 )
  {
    GetDeletionCandidates((__int64)&v33);
    v15 = v33;
    v16 = v33;
    v17 = v34;
    v18 = (__int64 *)v34;
    for ( k = (__int64 *)v34; ; v18 = k )
    {
      if ( v16 == v18 )
      {
        if ( v15 )
        {
          std::_Destroy_range<std::allocator<wil::com_ptr_t<IUserAccount,wil::err_exception_policy>>>((__int64)v15, v17);
          std::_Deallocate<16>(v33, (v35 - (_QWORD)v33) & 0xFFFFFFFFFFFFFFF8uLL);
        }
        break;
      }
      v29 = 0;
      v19 = *v16;
      v20 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v16 + 24LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v29,
        0);
      v21 = v20(v19, &v29);
      if ( v21 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x51,
          (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\userrequestpolicyengine.cpp",
          (const char *)(unsigned int)v21,
          (int)v26);
      std::wstring::wstring((__int64)v45, v29);
      if ( std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::count() )
      {
        ++v13;
        v30 = SharedPCRegistryKeyIfExists;
        wil::com_ptr_t<Windows::System::Internal::IUserProfile,wil::err_exception_policy>::com_ptr_t<Windows::System::Internal::IUserProfile,wil::err_exception_policy>(
          &v31,
          *v16);
        v26 = v45;
        UserRequestPolicyEngine::DeleteUserAndCleanUp(v32, &v31, a2, &v30);
        v22 = &v31;
      }
      else
      {
        if ( !std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::count() )
          goto LABEL_18;
        ++v14;
        v30 = v9;
        wil::com_ptr_t<Windows::System::Internal::IUserProfile,wil::err_exception_policy>::com_ptr_t<Windows::System::Internal::IUserProfile,wil::err_exception_policy>(
          &v28,
          *v16);
        v26 = v45;
        UserRequestPolicyEngine::DeleteUserAndCleanUp(v32, (__int64 *)&v28, a2, &v30);
        v22 = (__int64 *)&v28;
      }
      wil::com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>(v22);
LABEL_18:
      std::wstring::_Tidy_deallocate((__int64)v45);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v29);
      ++v16;
      v17 = v34;
      v15 = v33;
    }
  }
  PolicyTelemetry::UserRequestPolicyEvaluation::Stop((PolicyTelemetry::UserRequestPolicyEvaluation *)v46, v13, v14);
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v39);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v37);
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v42);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v38);
  PolicyTelemetry::UserRequestPolicyEvaluation::~UserRequestPolicyEvaluation((PolicyTelemetry::UserRequestPolicyEvaluation *)v46);
  return 0;
}

```

## disassembly

```asm
0x18001d480  mov     [rsp+arg_8], rbx
0x18001d485  mov     [rsp+arg_18], rsi
0x18001d48a  push    rdi
0x18001d48b  push    r12
0x18001d48d  push    r13
0x18001d48f  push    r14
0x18001d491  push    r15
0x18001d493  sub     rsp, 2B0h
0x18001d49a  mov     rax, cs:__security_cookie
0x18001d4a1  xor     rax, rsp
0x18001d4a4  mov     [rsp+2D8h+var_38], rax
0x18001d4ac  mov     rbx, r9
0x18001d4af  mov     r15, r8
0x18001d4b2  mov     [rsp+2D8h+var_2A8], edx
0x18001d4b6  mov     [rsp+2D8h+var_280], rcx
0x18001d4bb  lea     rdx, aUserrequestpol; "UserRequestPolicyEvaluation"
0x18001d4c2  lea     rcx, [rsp+2D8h+var_188]
0x18001d4ca  call    ??0?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001d4cf  lea     rax, ??_7UserRequestPolicyEvaluation@PolicyTelemetry@@6B@; const PolicyTelemetry::UserRequestPolicyEvaluation::`vftable'
0x18001d4d6  mov     [rsp+2D8h+var_188], rax
0x18001d4de  mov     rdx, rbx
0x18001d4e1  lea     rcx, [rsp+2D8h+var_188]
0x18001d4e9  call    ?SetRelatedActivityId@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x18001d4ee  lea     rcx, [rsp+2D8h+var_188]; this
0x18001d4f6  call    ?StartActivity@UserRequestPolicyEvaluation@PolicyTelemetry@@QEAAXXZ; PolicyTelemetry::UserRequestPolicyEvaluation::StartActivity(void)
0x18001d4fb  lea     rdx, aRequesteddelet; "RequestedDeletes\\User"
0x18001d502  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d50a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d50f  nop
0x18001d510  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d518  call    ?GetSharedPCRegistryKeyIfExists@@YAPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; GetSharedPCRegistryKeyIfExists(std::wstring const &,ulong)
0x18001d51d  mov     rsi, rax
0x18001d520  mov     [rsp+2D8h+var_250], rax
0x18001d528  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d530  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d535  lea     rcx, [rsp+2D8h+var_208]
0x18001d53d  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x18001d542  nop
0x18001d543  test    rsi, rsi
0x18001d546  jz      short loc_18001D590
0x18001d548  mov     [rsp+2D8h+var_2A0], rsi
0x18001d54d  lea     rdx, [rsp+2D8h+var_2A0]
0x18001d552  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d55a  call    ?GetKeySubkeyNames@@YA?AV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBQEAUHKEY__@@@Z; GetKeySubkeyNames(HKEY__ * const &)
0x18001d55f  mov     rdx, rax
0x18001d562  lea     rcx, [rsp+2D8h+var_208]
0x18001d56a  call    ??4?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::operator=(std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>> &&)
0x18001d56f  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d577  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x18001d57c  mov     rdi, [rsp+2D8h+var_200]
0x18001d584  mov     rbx, [rdi]
0x18001d587  cmp     rbx, rdi
0x18001d58a  jnz     loc_18001D883
0x18001d590  lea     rdx, aRequesteddelet_0; "RequestedDeletes\\DeviceOwner"
0x18001d597  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d59f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d5a4  nop
0x18001d5a5  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d5ad  call    ?GetSharedPCRegistryKeyIfExists@@YAPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; GetSharedPCRegistryKeyIfExists(std::wstring const &,ulong)
0x18001d5b2  mov     rdi, rax
0x18001d5b5  mov     [rsp+2D8h+var_258], rax
0x18001d5bd  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d5c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d5ca  lea     rcx, [rsp+2D8h+var_248]
0x18001d5d2  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x18001d5d7  nop
0x18001d5d8  test    rdi, rdi
0x18001d5db  jz      short loc_18001D625
0x18001d5dd  mov     [rsp+2D8h+var_2A0], rdi
0x18001d5e2  lea     rdx, [rsp+2D8h+var_2A0]
0x18001d5e7  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d5ef  call    ?GetKeySubkeyNames@@YA?AV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBQEAUHKEY__@@@Z; GetKeySubkeyNames(HKEY__ * const &)
0x18001d5f4  mov     rdx, rax
0x18001d5f7  lea     rcx, [rsp+2D8h+var_248]
0x18001d5ff  call    ??4?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::operator=(std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>> &&)
0x18001d604  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d60c  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x18001d611  mov     r14, [rsp+2D8h+var_240]
0x18001d619  mov     rbx, [r14]
0x18001d61c  cmp     rbx, r14
0x18001d61f  jnz     loc_18001D841
0x18001d625  xor     r12d, r12d
0x18001d628  xor     r13d, r13d
0x18001d62b  cmp     [rsp+2D8h+var_1F8], r12
0x18001d633  jnz     short loc_18001D643
0x18001d635  cmp     [rsp+2D8h+var_238], r12
0x18001d63d  jz      loc_18001D7E1
0x18001d643  mov     rdx, r15
0x18001d646  lea     rcx, [rsp+2D8h+var_278]
0x18001d64b  call    ?GetDeletionCandidates@@YA?AV?$vector@V?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEBV?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@2@@Z; GetDeletionCandidates(std::vector<Microsoft::WRL::ComPtr<IUserAccount>> const &)
0x18001d650  nop
0x18001d651  mov     rcx, [rsp+2D8h+var_278]
0x18001d656  mov     r15, rcx
0x18001d659  mov     rdx, [rsp+2D8h+var_270]
0x18001d65e  mov     rax, rdx
0x18001d661  mov     [rsp+2D8h+var_260], rdx
0x18001d666  cmp     r15, rax
0x18001d669  jz      loc_18001D7C1
0x18001d66f  mov     [rsp+2D8h+var_298], 0
0x18001d678  mov     r14, [r15]
0x18001d67b  mov     rax, [r14]
0x18001d67e  mov     rbx, [rax+18h]
0x18001d682  xor     edx, edx
0x18001d684  lea     rcx, [rsp+2D8h+var_298]
0x18001d689  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001d68e  lea     rdx, [rsp+2D8h+var_298]
0x18001d693  mov     rcx, r14
0x18001d696  mov     rax, rbx
0x18001d699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d69e  mov     rcx, [rsp+2D8h]; this
0x18001d6a6  test    eax, eax
0x18001d6a8  jns     short loc_18001D6BE
0x18001d6aa  mov     r9d, eax; char *
0x18001d6ad  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001d6b4  mov     edx, 51h ; 'Q'; void *
0x18001d6b9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001d6be  mov     rdx, [rsp+2D8h+var_298]
0x18001d6c3  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d6cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d6d0  nop
0x18001d6d1  lea     rdx, [rsp+2D8h+var_1C8]
0x18001d6d9  lea     rcx, [rsp+2D8h+var_208]
0x18001d6e1  call    ?count@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::count(std::wstring const &)
0x18001d6e6  test    rax, rax
0x18001d6e9  jz      short loc_18001D72F
0x18001d6eb  inc     r12
0x18001d6ee  mov     [rsp+2D8h+var_290], rsi
0x18001d6f3  mov     rdx, [r15]
0x18001d6f6  lea     rcx, [rsp+2D8h+var_288]
0x18001d6fb  call    ??0?$com_ptr_t@UIUserProfile@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIUserProfile@Internal@System@Windows@@@Z; wil::com_ptr_t<Windows::System::Internal::IUserProfile,wil::err_exception_policy>::com_ptr_t<Windows::System::Internal::IUserProfile,wil::err_exception_policy>(Windows::System::Internal::IUserProfile *)
0x18001d700  nop
0x18001d701  lea     rax, [rsp+2D8h+var_1C8]
0x18001d709  mov     [rsp+2D8h+var_2B8], rax
0x18001d70e  lea     r9, [rsp+2D8h+var_290]
0x18001d713  mov     r8d, [rsp+2D8h+var_2A8]
0x18001d718  lea     rdx, [rsp+2D8h+var_288]
0x18001d71d  mov     rcx, [rsp+2D8h+var_280]
0x18001d722  call    ?DeleteUserAndCleanUp@UserRequestPolicyEngine@@AEAAXAEBV?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@W4EvaluationTrigger@@AEBQEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; UserRequestPolicyEngine::DeleteUserAndCleanUp(wil::com_ptr_t<IUserAccount,wil::err_exception_policy> const &,EvaluationTrigger,HKEY__ * const &,std::wstring const &)
0x18001d727  nop
0x18001d728  lea     rcx, [rsp+2D8h+var_288]
0x18001d72d  jmp     short loc_18001D78B
0x18001d72f  lea     rdx, [rsp+2D8h+var_1C8]
0x18001d737  lea     rcx, [rsp+2D8h+var_248]
0x18001d73f  call    ?count@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::count(std::wstring const &)
0x18001d744  test    rax, rax
0x18001d747  jz      short loc_18001D791
0x18001d749  inc     r13
0x18001d74c  mov     [rsp+2D8h+var_290], rdi
0x18001d751  mov     rdx, [r15]
0x18001d754  lea     rcx, [rsp+2D8h+var_2A0]
0x18001d759  call    ??0?$com_ptr_t@UIUserProfile@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIUserProfile@Internal@System@Windows@@@Z; wil::com_ptr_t<Windows::System::Internal::IUserProfile,wil::err_exception_policy>::com_ptr_t<Windows::System::Internal::IUserProfile,wil::err_exception_policy>(Windows::System::Internal::IUserProfile *)
0x18001d75e  nop
0x18001d75f  lea     rax, [rsp+2D8h+var_1C8]
0x18001d767  mov     [rsp+2D8h+var_2B8], rax
0x18001d76c  lea     r9, [rsp+2D8h+var_290]
0x18001d771  mov     r8d, [rsp+2D8h+var_2A8]
0x18001d776  lea     rdx, [rsp+2D8h+var_2A0]
0x18001d77b  mov     rcx, [rsp+2D8h+var_280]
0x18001d780  call    ?DeleteUserAndCleanUp@UserRequestPolicyEngine@@AEAAXAEBV?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@W4EvaluationTrigger@@AEBQEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; UserRequestPolicyEngine::DeleteUserAndCleanUp(wil::com_ptr_t<IUserAccount,wil::err_exception_policy> const &,EvaluationTrigger,HKEY__ * const &,std::wstring const &)
0x18001d785  nop
0x18001d786  lea     rcx, [rsp+2D8h+var_2A0]
0x18001d78b  call    ??1?$com_ptr_t@UIUserProfile2@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>(void)
0x18001d790  nop
0x18001d791  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d799  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d79e  nop
0x18001d79f  lea     rcx, [rsp+2D8h+var_298]
0x18001d7a4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d7a9  add     r15, 8
0x18001d7ad  mov     rdx, [rsp+2D8h+var_270]
0x18001d7b2  mov     rcx, [rsp+2D8h+var_278]
0x18001d7b7  mov     rax, [rsp+2D8h+var_260]
0x18001d7bc  jmp     loc_18001D666
0x18001d7c1  test    rcx, rcx
0x18001d7c4  jz      short loc_18001D7E1
0x18001d7c6  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<IUserAccount,wil::err_exception_policy>>>(wil::com_ptr_t<IUserAccount,wil::err_exception_policy> *,wil::com_ptr_t<IUserAccount,wil::err_exception_policy> * const,std::allocator<wil::com_ptr_t<IUserAccount,wil::err_exception_policy>> &)
0x18001d7cb  mov     rcx, [rsp+2D8h+var_278]
0x18001d7d0  mov     rdx, [rsp+2D8h+var_268]
0x18001d7d5  sub     rdx, rcx
0x18001d7d8  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001d7dc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001d7e1  mov     r8d, r13d; unsigned int
0x18001d7e4  mov     edx, r12d; unsigned int
0x18001d7e7  lea     rcx, [rsp+2D8h+var_188]; this
0x18001d7ef  call    ?Stop@UserRequestPolicyEvaluation@PolicyTelemetry@@QEAAXII@Z; PolicyTelemetry::UserRequestPolicyEvaluation::Stop(uint,uint)
0x18001d7f4  nop
0x18001d7f5  lea     rcx, [rsp+2D8h+var_248]
0x18001d7fd  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x18001d802  nop
0x18001d803  lea     rcx, [rsp+2D8h+var_258]
0x18001d80b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001d810  nop
0x18001d811  lea     rcx, [rsp+2D8h+var_208]
0x18001d819  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x18001d81e  nop
0x18001d81f  lea     rcx, [rsp+2D8h+var_250]
0x18001d827  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001d82c  nop
0x18001d82d  lea     rcx, [rsp+2D8h+var_188]; this
0x18001d835  call    ??1UserRequestPolicyEvaluation@PolicyTelemetry@@QEAA@XZ; PolicyTelemetry::UserRequestPolicyEvaluation::~UserRequestPolicyEvaluation(void)
0x18001d83a  xor     eax, eax
0x18001d83c  jmp     loc_18001D8C9
0x18001d841  lea     rdx, [rbx+10h]
0x18001d845  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d84d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d852  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d85a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001d85f  mov     rdx, rax
0x18001d862  lea     rcx, aLoadedDeviceOw; "Loaded device owner requested delete fr"...
0x18001d869  call    ?TraceLoggingInfo@PolicyTelemetry@@SAXPEBDZZ; PolicyTelemetry::TraceLoggingInfo(char const *,...)
0x18001d86e  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d876  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d87b  mov     rbx, [rbx]
0x18001d87e  jmp     loc_18001D61C
0x18001d883  lea     rdx, [rbx+10h]
0x18001d887  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d88f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d894  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d89c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001d8a1  mov     rdx, rax
0x18001d8a4  lea     rcx, aLoadedUserRequ; "Loaded user requested delete from the r"...
0x18001d8ab  call    ?TraceLoggingInfo@PolicyTelemetry@@SAXPEBDZZ; PolicyTelemetry::TraceLoggingInfo(char const *,...)
0x18001d8b0  lea     rcx, [rsp+2D8h+var_1C8]
0x18001d8b8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d8bd  mov     rbx, [rbx]
0x18001d8c0  jmp     loc_18001D587
0x18001d8c5  mov     eax, [rsp+2D8h+var_2A8]
0x18001d8c9  mov     rcx, [rsp+2D8h+var_38]
0x18001d8d1  xor     rcx, rsp; StackCookie
0x18001d8d4  call    __security_check_cookie
0x18001d8d9  lea     r11, [rsp+2D8h+var_28]
0x18001d8e1  mov     rbx, [r11+38h]
0x18001d8e5  mov     rsi, [r11+48h]
0x18001d8e9  mov     rsp, r11
0x18001d8ec  pop     r15
0x18001d8ee  pop     r14
0x18001d8f0  pop     r13
0x18001d8f2  pop     r12
0x18001d8f4  pop     rdi
0x18001d8f5  retn
```
