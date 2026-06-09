# Windows::Internal::AssignedAccess::AssignedAccessConfiguration::GetUserInfoForGroup(ushort const *,Windows::Internal::AssignedAccess::IAssignedAccessUserInfo * *)

- ea: `0x180080320`
- end: `0x18008081d`
- name: `?GetUserInfoForGroup@AssignedAccessConfiguration@AssignedAccess@Internal@Windows@@AEAAJPEBGPEAPEAUIAssignedAccessUserInfo@234@@Z`
- size: `1277`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfiguration *__hidden this, const unsigned __int16 *, struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo **)`
- caller_count: `0`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x18000e760`
- `0x1800109e0`
- `0x180010c98`
- `0x180013fac`
- `0x180014a5c`
- `0x18001f2b0`
- `0x18002249c`
- `0x180022930`
- `0x1800271e4`
- `0x18002901c`
- `0x180050440`
- `0x180050980`
- `0x18007cba0`
- `0x18007dbb0`
- `0x18007dc70`
- `0x18007dd00`
- `0x18007df50`
- `0x18007e0c4`
- `0x18007e518`
- `0x18007e9f8`
- `0x18007ed48`
- `0x18007ee44`
- `0x18007ee98`
- `0x18007f1a4`
- `0x180080320`
- `0x180080a30`
- `0x180082528`
- `0x180083a24`
- `0x180083bd0`
- `0x180084b7c`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180080590`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180080590`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800804bc`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800804bc`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180080688`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180080688`

## string_xrefs

- `0x1800803c9`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfiguration.cpp`
- `0x180080463`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfiguration.cpp`
- `0x1800806b3`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfiguration.cpp`
- `0x18008075f`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfiguration.cpp`
- `0x180080798`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfiguration.cpp`
- `0x180080357`: `AssignedAccessConfiguration_GetUserInfoForGroup`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfiguration::GetUserInfoForGroup(
        Windows::Internal::AssignedAccess::AssignedAccessConfiguration *this,
        unsigned __int16 *a2,
        struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo **a3)
{
  int GroupTypeFromUserSid; // eax
  int Instance; // ebx
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  int v8; // eax
  bool v9; // r14
  const wchar_t *v10; // rcx
  __int64 *v11; // rsi
  __int64 *v12; // r15
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  unsigned __int16 *v16; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  const wchar_t *v18; // rcx
  HSTRING v19; // rax
  __int64 *v20; // rax
  __int64 v21; // rbx
  int v22; // edi
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rdx
  int v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+20h] [rbp-E0h]
  bool v29; // [rsp+40h] [rbp-C0h] BYREF
  bool v30; // [rsp+41h] [rbp-BFh] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  int v32; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v33; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v35; // [rsp+68h] [rbp-98h] BYREF
  int v36; // [rsp+70h] [rbp-90h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h] BYREF
  struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo **v38; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v39[56]; // [rsp+88h] [rbp-78h] BYREF
  HSTRING v40; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v41; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v42; // [rsp+D0h] [rbp-30h]
  char v43[32]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v44[42]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v33 = a2;
  v38 = a3;
  wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v44,
    "AssignedAccessConfiguration_GetUserInfoForGroup");
  v44[0] = &AssignedAccessTelemetry::AssignedAccessConfiguration_GetUserInfoForGroup::`vftable';
  AssignedAccessTelemetry::AssignedAccessConfiguration_GetUserInfoForGroup::StartActivity((AssignedAccessTelemetry::AssignedAccessConfiguration_GetUserInfoForGroup *)v44);
  *v38 = 0;
  if ( !*((_QWORD *)this + 11) || Windows::Internal::AssignedAccess::UserInfoHelper::IsUserAdmin(v33) )
  {
    v29 = 0;
    AssignedAccessTelemetry::AssignedAccessConfiguration_GetUserInfoForGroup::IsGroupFoundForUser<unsigned short const * &,bool>(
      v44,
      &v33,
      &v29);
    wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v44);
  }
  else
  {
    v32 = -1;
    GroupTypeFromUserSid = Windows::Internal::AssignedAccess::UserInfoHelper::GetGroupTypeFromUserSid(
                             v33,
                             (enum Windows::Internal::AssignedAccess::AccountType *)&v32);
    Instance = GroupTypeFromUserSid;
    if ( GroupTypeFromUserSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x144,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfiguration.cpp",
        (const char *)(unsigned int)GroupTypeFromUserSid,
        v27);
LABEL_40:
      AssignedAccessTelemetry::AssignedAccessConfiguration_GetUserInfoForGroup::~AssignedAccessConfiguration_GetUserInfoForGroup((AssignedAccessTelemetry::AssignedAccessConfiguration_GetUserInfoForGroup *)v44);
      return (unsigned int)Instance;
    }
    std::_Hash<std::_Umap_traits<enum Windows::Internal::AssignedAccess::AccountType,std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>>,std::_Uhash_compare<enum Windows::Internal::AssignedAccess::AccountType,std::hash<enum Windows::Internal::AssignedAccess::AccountType>,std::equal_to<enum Windows::Internal::AssignedAccess::AccountType>>,std::allocator<std::pair<enum Windows::Internal::AssignedAccess::AccountType const,std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>>>>,0>>::find(
      (char *)this + 72,
      &v37,
      &v32);
    if ( v37 == *((_QWORD *)this + 10) )
    {
      v29 = 0;
      AssignedAccessTelemetry::AssignedAccessConfiguration_GetUserInfoForGroup::IsGroupFoundForUser<unsigned short const * &,bool>(
        v44,
        &v33,
        &v29);
      wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v44);
      Instance = 0;
      goto LABEL_40;
    }
    v34 = 0;
    std::wstring::wstring(v39, v33);
    Instance = Windows::Internal::AssignedAccess::AssignedAccessAccount_CreateInstance(v32);
    std::wstring::_Tidy_deallocate(v39);
    if ( Instance < 0 )
    {
      v6 = (unsigned int)Instance;
      v7 = 335;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfiguration.cpp",
        (const char *)v6,
        v27);
LABEL_39:
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v34);
      goto LABEL_40;
    }
    string = 0;
    v8 = Windows::Internal::AssignedAccess::CreateGroupCheckStateMachineInstance(v34, (unsigned int)v32, &string);
    Instance = v8;
    if ( v8 < 0 )
    {
      v6 = (unsigned int)v8;
      v7 = 337;
      goto LABEL_9;
    }
    v35 = string;
    v36 = 0;
    RtlGetDeviceFamilyInfoEnum(0, &v36, 0);
    v30 = v36 == 10;
    lambda_e42e5ec538a610012981636a1bc3c7cc_::_lambda_e42e5ec538a610012981636a1bc3c7cc_(
      (unsigned int)v39,
      (unsigned int)&v37,
      (unsigned int)&v35,
      (unsigned int)&v30,
      (__int64)&v33,
      (__int64)this,
      (__int64)&v38);
    if ( v30 )
    {
      v9 = 0;
      string = 0;
      if ( Windows::Internal::AssignedAccess::AssignedAccessConfiguration::get_GlobalProfile(
             (Windows::Internal::AssignedAccess::AssignedAccessConfiguration *)((char *)this + 48),
             (struct Windows::Internal::AssignedAccess::IAssignedAccessProfile **)&string) >= 0 )
        v9 = string != 0;
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&string);
      v11 = *(__int64 **)(v37 + 24);
      v12 = *(__int64 **)(v37 + 32);
      while ( 1 )
      {
        if ( v11 == v12 )
          goto LABEL_22;
        v29 = 0;
        string = 0;
        v13 = *v11;
        v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*v11 + 48LL);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
          &string,
          0);
        v15 = v14(v13, &string);
        Instance = v15;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x18E,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfiguration.cpp",
            (const char *)(unsigned int)v15,
            v28);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
          goto LABEL_38;
        }
        v16 = v33;
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        if ( (int)Windows::Internal::AssignedAccess::AssignedAccessConfiguration::HandleMembershipCheckResult(
                    -2147483638,
                    StringRawBuffer,
                    v16,
                    v9,
                    &v29) < 0 )
          break;
        if ( v29 )
        {
          wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperation,wil::err_exception_policy>::copy_to<Windows::Internal::AssignedAccess::IProfileOperation>(
            v11,
            v38);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
LABEL_22:
          AssignedAccessTelemetry::AssignedAccessConfiguration_Message<unsigned short const (&)[43]>(v10);
          std::wstring::wstring(v39, v33);
          v19 = v35;
          v35 = 0;
          v40 = v19;
          v41 = 0;
          v42 = 0;
          std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>>::_Construct_n<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy> * const &,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy> * const &>(
            &v41,
            (__int64)(*(_QWORD *)(v37 + 32) - *(_QWORD *)(v37 + 24)) >> 3,
            (__int64 *)(v37 + 24),
            (__int64 *)(v37 + 32));
          std::wstring::wstring(v43, v39);
          v20 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_cb90e41610cc836ffe699673a8903d80_____lambda_cb90e41610cc836ffe699673a8903d80___(
                             &string,
                             &v40);
          v21 = *v20;
          *v20 = 0;
          if ( string )
          {
            string = 0;
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::AssignedAccess::IProfileOperationBuilder>::Release();
          }
          v22 = SHTaskPoolQueueTask(0, 514, 0);
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          if ( v22 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1E7,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfiguration.cpp",
              (const char *)(unsigned int)v22,
              v21);
          lambda_cb90e41610cc836ffe699673a8903d80_::__lambda_cb90e41610cc836ffe699673a8903d80_(&v40);
          std::wstring::_Tidy_deallocate(v39);
          goto LABEL_29;
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
        ++v11;
      }
      AssignedAccessTelemetry::AssignedAccessConfiguration_Message<unsigned short const (&)[41]>(v18);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
      v23 = lambda_e42e5ec538a610012981636a1bc3c7cc_::operator()(v39);
      Instance = v23;
      v32 = v23;
      if ( v23 >= 0 )
        goto LABEL_29;
      if ( !v9 )
      {
        v25 = 439;
        goto LABEL_37;
      }
      AssignedAccessTelemetry::AssignedAccessConfiguration_MembershipCheck_IgnoreFailure<unsigned short const (&)[35],long const &>(
        v24,
        &v32);
    }
    else
    {
      v23 = lambda_e42e5ec538a610012981636a1bc3c7cc_::operator()(v39);
      Instance = v23;
      if ( v23 < 0 )
      {
        v25 = 492;
LABEL_37:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfiguration.cpp",
          (const char *)(unsigned int)v23,
          v28);
LABEL_38:
        std::unique_ptr<Windows::Internal::AssignedAccess::GroupCheckStateMachine>::~unique_ptr<Windows::Internal::AssignedAccess::GroupCheckStateMachine>(&v35);
        goto LABEL_39;
      }
    }
LABEL_29:
    v29 = *v38 != 0;
    AssignedAccessTelemetry::AssignedAccessConfiguration_GetUserInfoForGroup::IsGroupFoundForUser<unsigned short const * &,bool>(
      v44,
      &v33,
      &v29);
    wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v44);
    std::unique_ptr<Windows::Internal::AssignedAccess::GroupCheckStateMachine>::~unique_ptr<Windows::Internal::AssignedAccess::GroupCheckStateMachine>(&v35);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v34);
  }
  AssignedAccessTelemetry::AssignedAccessConfiguration_GetUserInfoForGroup::~AssignedAccessConfiguration_GetUserInfoForGroup((AssignedAccessTelemetry::AssignedAccessConfiguration_GetUserInfoForGroup *)v44);
  return 0;
}

```

## disassembly

```asm
0x180080320  push    rbp
0x180080322  push    rbx
0x180080323  push    rsi
0x180080324  push    rdi
0x180080325  push    r12
0x180080327  push    r14
0x180080329  push    r15
0x18008032b  lea     rbp, [rsp-160h]
0x180080333  sub     rsp, 260h
0x18008033a  mov     rax, cs:__security_cookie
0x180080341  xor     rax, rsp
0x180080344  mov     [rbp+190h+var_40], rax
0x18008034b  mov     rdi, rcx
0x18008034e  mov     [rsp+290h+var_238], rdx
0x180080353  mov     [rbp+190h+var_210], r8
0x180080357  lea     rdx, aAssignedaccess_12; "AssignedAccessConfiguration_GetUserInfo"...
0x18008035e  lea     rcx, [rbp+190h+var_190]
0x180080362  call    ??0?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180080367  lea     rax, ??_7AssignedAccessConfiguration_GetUserInfoForGroup@AssignedAccessTelemetry@@6B@; const AssignedAccessTelemetry::AssignedAccessConfiguration_GetUserInfoForGroup::`vftable'
0x18008036e  mov     [rbp+190h+var_190], rax
0x180080372  lea     rcx, [rbp+190h+var_190]; this
0x180080376  call    ?StartActivity@AssignedAccessConfiguration_GetUserInfoForGroup@AssignedAccessTelemetry@@QEAAXXZ; AssignedAccessTelemetry::AssignedAccessConfiguration_GetUserInfoForGroup::StartActivity(void)
0x18008037b  nop
0x18008037c  xor     r12d, r12d
0x18008037f  mov     rax, [rbp+190h+var_210]
0x180080383  mov     [rax], r12
0x180080386  cmp     [rdi+58h], r12
0x18008038a  jz      loc_1800807CF
0x180080390  mov     rcx, [rsp+290h+var_238]; unsigned __int16 *
0x180080395  call    ?IsUserAdmin@UserInfoHelper@AssignedAccess@Internal@Windows@@SA_NPEBG@Z; Windows::Internal::AssignedAccess::UserInfoHelper::IsUserAdmin(ushort const *)
0x18008039a  test    al, al
0x18008039c  jnz     loc_1800807CF
0x1800803a2  mov     [rsp+290h+var_240], 0FFFFFFFFh
0x1800803aa  lea     rdx, [rsp+290h+var_240]; enum Windows::Internal::AssignedAccess::AccountType *
0x1800803af  mov     rcx, [rsp+290h+var_238]; unsigned __int16 *
0x1800803b4  call    ?GetGroupTypeFromUserSid@UserInfoHelper@AssignedAccess@Internal@Windows@@SAJPEBGAEAW4AccountType@234@@Z; Windows::Internal::AssignedAccess::UserInfoHelper::GetGroupTypeFromUserSid(ushort const *,Windows::Internal::AssignedAccess::AccountType &)
0x1800803b9  mov     ebx, eax
0x1800803bb  test    eax, eax
0x1800803bd  jns     short loc_1800803DF
0x1800803bf  mov     rcx, [rbp+198h]; this
0x1800803c6  mov     r9d, eax; char *
0x1800803c9  lea     r8, aOnecoreuapBase_44; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800803d0  mov     edx, 144h; void *
0x1800803d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800803da  jmp     loc_1800807C2
0x1800803df  lea     r8, [rsp+290h+var_240]
0x1800803e4  lea     rdx, [rsp+290h+var_218]
0x1800803e9  lea     rcx, [rdi+48h]
0x1800803ed  call    ?find@?$_Hash@V?$_Umap_traits@W4AccountType@AssignedAccess@Internal@Windows@@V?$vector@V?$com_ptr_t@UIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@V?$_Uhash_compare@W4AccountType@AssignedAccess@Internal@Windows@@U?$hash@W4AccountType@AssignedAccess@Internal@Windows@@@std@@U?$equal_to@W4AccountType@AssignedAccess@Internal@Windows@@@6@@6@V?$allocator@U?$pair@$$CBW4AccountType@AssignedAccess@Internal@Windows@@V?$vector@V?$com_ptr_t@UIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4AccountType@AssignedAccess@Internal@Windows@@V?$vector@V?$com_ptr_t@UIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@std@@@std@@@2@AEBW4AccountType@AssignedAccess@Internal@Windows@@@Z; std::_Hash<std::_Umap_traits<Windows::Internal::AssignedAccess::AccountType,std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>>,std::_Uhash_compare<Windows::Internal::AssignedAccess::AccountType,std::hash<Windows::Internal::AssignedAccess::AccountType>,std::equal_to<Windows::Internal::AssignedAccess::AccountType>>,std::allocator<std::pair<Windows::Internal::AssignedAccess::AccountType const,std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>>>>,0>>::find(Windows::Internal::AssignedAccess::AccountType const &)
0x1800803f2  mov     rax, [rdi+50h]
0x1800803f6  cmp     [rsp+290h+var_218], rax
0x1800803fb  jnz     short loc_180080426
0x1800803fd  mov     [rsp+290h+var_250], r12b
0x180080402  lea     r8, [rsp+290h+var_250]
0x180080407  lea     rdx, [rsp+290h+var_238]
0x18008040c  lea     rcx, [rbp+190h+var_190]
0x180080410  call    ??$IsGroupFoundForUser@AEAPEBG_N@AssignedAccessConfiguration_GetUserInfoForGroup@AssignedAccessTelemetry@@QEAAXAEAPEBG$$QEA_N@Z; AssignedAccessTelemetry::AssignedAccessConfiguration_GetUserInfoForGroup::IsGroupFoundForUser<ushort const * &,bool>(ushort const * &,bool &&)
0x180080415  lea     rcx, [rbp+190h+var_190]
0x180080419  call    ?Stop@?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18008041e  mov     ebx, r12d
0x180080421  jmp     loc_1800807C2
0x180080426  mov     [rsp+290h+var_230], r12
0x18008042b  mov     rdx, [rsp+290h+var_238]
0x180080430  lea     rcx, [rbp+190h+var_208]
0x180080434  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180080439  nop
0x18008043a  lea     r8, [rsp+290h+var_230]
0x18008043f  lea     rdx, [rbp+190h+var_208]
0x180080443  mov     ecx, [rsp+290h+var_240]; int
0x180080447  call    ?AssignedAccessAccount_CreateInstance@AssignedAccess@Internal@Windows@@YAJW4AccountType@123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIAssignedAccessAccount@123@@Z; Windows::Internal::AssignedAccess::AssignedAccessAccount_CreateInstance(Windows::Internal::AssignedAccess::AccountType,std::wstring const &,Windows::Internal::AssignedAccess::IAssignedAccessAccount * *)
0x18008044c  mov     ebx, eax
0x18008044e  lea     rcx, [rbp+190h+var_208]
0x180080452  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180080457  test    ebx, ebx
0x180080459  jns     short loc_18008047B
0x18008045b  mov     r9d, ebx; char *
0x18008045e  mov     edx, 14Fh; void *
0x180080463  lea     r8, aOnecoreuapBase_44; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18008046a  mov     rcx, [rbp+198h]; this
0x180080471  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080476  jmp     loc_1800807B7
0x18008047b  mov     [rsp+290h+string], r12
0x180080480  lea     r8, [rsp+290h+string]
0x180080485  mov     edx, [rsp+290h+var_240]
0x180080489  mov     rcx, [rsp+290h+var_230]
0x18008048e  call    ?CreateGroupCheckStateMachineInstance@AssignedAccess@Internal@Windows@@YAJPEAUIAssignedAccessAccount@123@W4AccountType@123@PEAPEAVGroupCheckStateMachine@123@@Z; Windows::Internal::AssignedAccess::CreateGroupCheckStateMachineInstance(Windows::Internal::AssignedAccess::IAssignedAccessAccount *,Windows::Internal::AssignedAccess::AccountType,Windows::Internal::AssignedAccess::GroupCheckStateMachine * *)
0x180080493  mov     ebx, eax
0x180080495  test    eax, eax
0x180080497  jns     short loc_1800804A3
0x180080499  mov     r9d, eax
0x18008049c  mov     edx, 151h
0x1800804a1  jmp     short loc_180080463
0x1800804a3  mov     rax, [rsp+290h+string]
0x1800804a8  mov     [rsp+290h+var_228], rax
0x1800804ad  mov     [rsp+290h+var_220], r12d
0x1800804b2  xor     r8d, r8d
0x1800804b5  lea     rdx, [rsp+290h+var_220]
0x1800804ba  xor     ecx, ecx
0x1800804bc  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800804c2  cmp     [rsp+290h+var_220], 0Ah
0x1800804c7  setz    [rsp+290h+var_24F]
0x1800804cc  lea     rax, [rbp+190h+var_210]
0x1800804d0  mov     [rsp+290h+var_260], rax
0x1800804d5  mov     [rsp+290h+var_268], rdi
0x1800804da  lea     rax, [rsp+290h+var_238]
0x1800804df  mov     [rsp+290h+var_270], rax; int
0x1800804e4  lea     r9, [rsp+290h+var_24F]
0x1800804e9  lea     r8, [rsp+290h+var_228]
0x1800804ee  lea     rdx, [rsp+290h+var_218]
0x1800804f3  lea     rcx, [rbp+190h+var_208]
0x1800804f7  call    _lambda_e42e5ec538a610012981636a1bc3c7cc____lambda_e42e5ec538a610012981636a1bc3c7cc_
0x1800804fc  cmp     [rsp+290h+var_24F], r12b
0x180080501  jz      loc_18008077D
0x180080507  mov     r14b, r12b
0x18008050a  mov     [rsp+290h+string], r12
0x18008050f  lea     rcx, [rdi+30h]; this
0x180080513  lea     rdx, [rsp+290h+string]; struct Windows::Internal::AssignedAccess::IAssignedAccessProfile **
0x180080518  call    ?get_GlobalProfile@AssignedAccessConfiguration@AssignedAccess@Internal@Windows@@UEAAJPEAPEAUIAssignedAccessProfile@234@@Z; Windows::Internal::AssignedAccess::AssignedAccessConfiguration::get_GlobalProfile(Windows::Internal::AssignedAccess::IAssignedAccessProfile * *)
0x18008051d  test    eax, eax
0x18008051f  js      short loc_18008052A
0x180080521  cmp     [rsp+290h+string], r12
0x180080526  setnz   r14b
0x18008052a  lea     rcx, [rsp+290h+string]
0x18008052f  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180080534  mov     rax, [rsp+290h+var_218]
0x180080539  mov     rsi, [rax+18h]
0x18008053d  mov     r15, [rax+20h]
0x180080541  cmp     rsi, r15
0x180080544  jz      loc_1800805EC
0x18008054a  mov     [rsp+290h+var_250], r12b
0x18008054f  mov     [rsp+290h+string], r12
0x180080554  mov     rdi, [rsi]
0x180080557  mov     rax, [rdi]
0x18008055a  mov     rbx, [rax+30h]
0x18008055e  xor     edx, edx
0x180080560  lea     rcx, [rsp+290h+string]
0x180080565  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18008056a  lea     rdx, [rsp+290h+string]
0x18008056f  mov     rcx, rdi
0x180080572  mov     rax, rbx
0x180080575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008057a  mov     ebx, eax
0x18008057c  test    eax, eax
0x18008057e  js      loc_180080755
0x180080584  mov     rbx, [rsp+290h+var_238]
0x180080589  xor     edx, edx; length
0x18008058b  mov     rcx, [rsp+290h+string]; string
0x180080590  call    cs:__imp_WindowsGetStringRawBuffer
0x180080596  lea     rcx, [rsp+290h+var_250]
0x18008059b  mov     [rsp+290h+var_270], rcx; bool *
0x1800805a0  mov     r9b, r14b; bool
0x1800805a3  mov     r8, rbx; unsigned __int16 *
0x1800805a6  mov     rdx, rax; unsigned __int16 *
0x1800805a9  mov     ecx, 8000000Ah; int
0x1800805ae  call    ?HandleMembershipCheckResult@AssignedAccessConfiguration@AssignedAccess@Internal@Windows@@SAJJPEBG0_NAEA_N@Z; Windows::Internal::AssignedAccess::AssignedAccessConfiguration::HandleMembershipCheckResult(long,ushort const *,ushort const *,bool,bool &)
0x1800805b3  test    eax, eax
0x1800805b5  js      loc_18008071A
0x1800805bb  cmp     [rsp+290h+var_250], r12b
0x1800805c0  jnz     short loc_1800805D5
0x1800805c2  lea     rcx, [rsp+290h+string]
0x1800805c7  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800805cc  add     rsi, 8
0x1800805d0  jmp     loc_180080541
0x1800805d5  mov     rdx, [rbp+190h+var_210]
0x1800805d9  mov     rcx, rsi
0x1800805dc  call    ??$copy_to@UIProfileOperation@AssignedAccess@Internal@Windows@@@?$com_ptr_t@UIProfileOperation@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUIProfileOperation@AssignedAccess@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperation,wil::err_exception_policy>::copy_to<Windows::Internal::AssignedAccess::IProfileOperation>(Windows::Internal::AssignedAccess::IProfileOperation * *)
0x1800805e1  nop
0x1800805e2  lea     rcx, [rsp+290h+string]
0x1800805e7  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800805ec  call    ??$AssignedAccessConfiguration_Message@AEAY0CL@$$CBG@AssignedAccessTelemetry@@SAXAEAY0CL@$$CBG@Z; AssignedAccessTelemetry::AssignedAccessConfiguration_Message<ushort const (&)[43]>(ushort const (&)[43])
0x1800805f1  mov     rdx, [rsp+290h+var_238]
0x1800805f6  lea     rcx, [rbp+190h+var_208]
0x1800805fa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800805ff  nop
0x180080600  mov     r8, [rsp+290h+var_218]
0x180080605  add     r8, 18h
0x180080609  mov     rax, [rsp+290h+var_228]
0x18008060e  mov     [rsp+290h+var_228], r12
0x180080613  mov     [rbp+190h+var_1D0], rax
0x180080617  mov     [rbp+190h+var_1C8], r12
0x18008061b  xorps   xmm0, xmm0
0x18008061e  movdqa  [rbp+190h+var_1C0], xmm0
0x180080623  lea     r9, [r8+8]
0x180080627  mov     rdx, [r9]
0x18008062a  sub     rdx, [r8]
0x18008062d  sar     rdx, 3
0x180080631  lea     rcx, [rbp+190h+var_1C8]
0x180080635  call    ??$_Construct_n@AEBQEAV?$com_ptr_t@UIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@AEBQEAV12@@?$vector@V?$com_ptr_t@UIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAX_KAEBQEAV?$com_ptr_t@UIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@1@Z; std::vector<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>>::_Construct_n<wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy> * const &,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy> * const &>(unsigned __int64,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy> * const &,wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy> * const &)
0x18008063a  nop
0x18008063b  lea     rdx, [rbp+190h+var_208]
0x18008063f  lea     rcx, [rbp+190h+var_1B0]
0x180080643  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180080648  nop
0x180080649  lea     rdx, [rbp+190h+var_1D0]
0x18008064d  lea     rcx, [rsp+290h+string]
0x180080652  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_cb90e41610cc836ffe699673a8903d80_____lambda_cb90e41610cc836ffe699673a8903d80___
0x180080657  mov     rbx, [rax]
0x18008065a  mov     [rax], r12
0x18008065d  mov     rcx, [rsp+290h+string]
0x180080662  test    rcx, rcx
0x180080665  jz      short loc_180080671
0x180080667  mov     [rsp+290h+string], r12
0x18008066c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIProfileOperationBuilder@AssignedAccess@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::AssignedAccess::IProfileOperationBuilder>::Release(void)
0x180080671  mov     [rsp+290h+var_268], r12
0x180080676  mov     [rsp+290h+var_270], rbx; int
0x18008067b  xor     r9d, r9d
0x18008067e  xor     r8d, r8d
0x180080681  mov     edx, 202h
0x180080686  xor     ecx, ecx
0x180080688  call    cs:__imp_SHTaskPoolQueueTask
0x18008068e  mov     edi, eax
0x180080690  test    rbx, rbx
0x180080693  jz      short loc_1800806A5
0x180080695  mov     rdx, [rbx]
0x180080698  mov     rcx, rbx
0x18008069b  mov     rax, [rdx+10h]
0x18008069f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800806a4  nop
0x1800806a5  mov     rcx, [rbp+198h]; this
0x1800806ac  test    edi, edi
0x1800806ae  jns     short loc_1800806C4
0x1800806b0  mov     r9d, edi; char *
0x1800806b3  lea     r8, aOnecoreuapBase_44; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800806ba  mov     edx, 1E7h; void *
0x1800806bf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800806c4  lea     rcx, [rbp+190h+var_1D0]
0x1800806c8  call    _lambda_cb90e41610cc836ffe699673a8903d80_____lambda_cb90e41610cc836ffe699673a8903d80_
0x1800806cd  nop
0x1800806ce  lea     rcx, [rbp+190h+var_208]
0x1800806d2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800806d7  mov     rax, [rbp+190h+var_210]
0x1800806db  cmp     [rax], r12
0x1800806de  setnz   [rsp+290h+var_250]
0x1800806e3  lea     r8, [rsp+290h+var_250]
0x1800806e8  lea     rdx, [rsp+290h+var_238]
0x1800806ed  lea     rcx, [rbp+190h+var_190]
0x1800806f1  call    ??$IsGroupFoundForUser@AEAPEBG_N@AssignedAccessConfiguration_GetUserInfoForGroup@AssignedAccessTelemetry@@QEAAXAEAPEBG$$QEA_N@Z; AssignedAccessTelemetry::AssignedAccessConfiguration_GetUserInfoForGroup::IsGroupFoundForUser<ushort const * &,bool>(ushort const * &,bool &&)
0x1800806f6  lea     rcx, [rbp+190h+var_190]
0x1800806fa  call    ?Stop@?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800806ff  nop
0x180080700  lea     rcx, [rsp+290h+var_228]
0x180080705  call    ??1?$unique_ptr@VGroupCheckStateMachine@AssignedAccess@Internal@Windows@@U?$default_delete@VGroupCheckStateMachine@AssignedAccess@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::AssignedAccess::GroupCheckStateMachine>::~unique_ptr<Windows::Internal::AssignedAccess::GroupCheckStateMachine>(void)
0x18008070a  nop
0x18008070b  lea     rcx, [rsp+290h+var_230]
0x180080710  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180080715  jmp     loc_1800807F1
0x18008071a  call    ??$AssignedAccessConfiguration_Message@AEAY0CJ@$$CBG@AssignedAccessTelemetry@@SAXAEAY0CJ@$$CBG@Z; AssignedAccessTelemetry::AssignedAccessConfiguration_Message<ushort const (&)[41]>(ushort const (&)[41])
0x18008071f  nop
0x180080720  lea     rcx, [rsp+290h+string]
0x180080725  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18008072a  lea     rcx, [rbp+190h+var_208]
0x18008072e  call    _lambda_e42e5ec538a610012981636a1bc3c7cc___operator__
0x180080733  mov     ebx, eax
0x180080735  mov     [rsp+290h+var_240], eax
0x180080739  test    eax, eax
0x18008073b  jns     short loc_1800806D7
0x18008073d  test    r14b, r14b
0x180080740  jnz     short loc_180080749
0x180080742  mov     edx, 1B7h
0x180080747  jmp     short loc_180080795
0x180080749  lea     rdx, [rsp+290h+var_240]
0x18008074e  call    ??$AssignedAccessConfiguration_MembershipCheck_IgnoreFailure@AEAY0CD@$$CBGAEBJ@AssignedAccessTelemetry@@SAXAEAY0CD@$$CBGAEBJ@Z; AssignedAccessTelemetry::AssignedAccessConfiguration_MembershipCheck_IgnoreFailure<ushort const (&)[35],long const &>(ushort const (&)[35],long const &)
0x180080753  jmp     short loc_1800806D7
0x180080755  mov     rcx, [rbp+198h]; this
0x18008075c  mov     r9d, eax; char *
0x18008075f  lea     r8, aOnecoreuapBase_44; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180080766  mov     edx, 18Eh; void *
0x18008076b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080770  nop
0x180080771  lea     rcx, [rsp+290h+string]
0x180080776  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18008077b  jmp     short loc_1800807AC
0x18008077d  lea     rcx, [rbp+190h+var_208]
0x180080781  call    _lambda_e42e5ec538a610012981636a1bc3c7cc___operator__
0x180080786  mov     ebx, eax
0x180080788  test    eax, eax
0x18008078a  jns     loc_1800806D7
0x180080790  mov     edx, 1ECh; void *
0x180080795  mov     r9d, eax; char *
0x180080798  lea     r8, aOnecoreuapBase_44; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18008079f  mov     rcx, [rbp+198h]; this
0x1800807a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800807ab  nop
0x1800807ac  lea     rcx, [rsp+290h+var_228]
0x1800807b1  call    ??1?$unique_ptr@VGroupCheckStateMachine@AssignedAccess@Internal@Windows@@U?$default_delete@VGroupCheckStateMachine@AssignedAccess@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::AssignedAccess::GroupCheckStateMachine>::~unique_ptr<Windows::Internal::AssignedAccess::GroupCheckStateMachine>(void)
0x1800807b6  nop
0x1800807b7  lea     rcx, [rsp+290h+var_230]
0x1800807bc  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800807c1  nop
0x1800807c2  lea     rcx, [rbp+190h+var_190]; this
0x1800807c6  call    ??1AssignedAccessConfiguration_GetUserInfoForGroup@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::AssignedAccessConfiguration_GetUserInfoForGroup::~AssignedAccessConfiguration_GetUserInfoForGroup(void)
0x1800807cb  mov     eax, ebx
0x1800807cd  jmp     short loc_1800807FC
0x1800807cf  mov     [rsp+290h+var_250], r12b
0x1800807d4  lea     r8, [rsp+290h+var_250]
0x1800807d9  lea     rdx, [rsp+290h+var_238]
0x1800807de  lea     rcx, [rbp+190h+var_190]
0x1800807e2  call    ??$IsGroupFoundForUser@AEAPEBG_N@AssignedAccessConfiguration_GetUserInfoForGroup@AssignedAccessTelemetry@@QEAAXAEAPEBG$$QEA_N@Z; AssignedAccessTelemetry::AssignedAccessConfiguration_GetUserInfoForGroup::IsGroupFoundForUser<ushort const * &,bool>(ushort const * &,bool &&)
0x1800807e7  lea     rcx, [rbp+190h+var_190]
0x1800807eb  call    ?Stop@?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
  ... truncated ...
```
