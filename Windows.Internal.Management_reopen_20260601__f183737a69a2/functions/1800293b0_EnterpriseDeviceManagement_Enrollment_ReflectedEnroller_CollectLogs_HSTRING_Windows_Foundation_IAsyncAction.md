# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::CollectLogs(HSTRING__ *,Windows::Foundation::IAsyncAction * *)

- ea: `0x1800293b0`
- end: `0x1800295bd`
- name: `?CollectLogs@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJPEAUHSTRING__@@PEAPEAUIAsyncAction@Foundation@Windows@@@Z`
- size: `525`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *this, HSTRING, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a5c4`
- `0x180017298`
- `0x180017860`
- `0x180017a88`
- `0x180017b70`
- `0x180017bf0`
- `0x1800181cc`
- `0x18001823c`
- `0x1800183bc`
- `0x1800184e8`
- `0x180018738`
- `0x18001af34`
- `0x18001d00c`
- `0x18001d3c0`
- `0x180020e30`
- `0x1800293b0`
- `0x18003a488`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!DmGetCurrentUserToken` at `0x1800294e2`
- `DMCmnUtils!DmGetCurrentUserToken` at `0x1800294e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180029410`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180029410`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::CollectLogs(
        EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *this,
        HSTRING a2,
        struct Windows::Foundation::IAsyncAction **a3)
{
  __int64 v6; // rax
  HRESULT v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  __int64 v10; // rax
  int CurrentUserToken; // eax
  __int64 v12; // rax
  __int64 v13; // r8
  int v15; // [rsp+20h] [rbp-39h] BYREF
  __int64 v16; // [rsp+24h] [rbp-35h]
  void **v17[2]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v18[16]; // [rsp+40h] [rbp-19h] BYREF
  HSTRING *newString[2]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v20[80]; // [rsp+60h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *v22; // [rsp+D8h] [rbp+7Fh] BYREF

  wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(newString);
  wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(
    newString,
    0);
  if ( !(unsigned __int8)std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(newString) )
  {
    v6 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(v18);
    std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
      newString,
      v6);
    std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v18);
  }
  v7 = WindowsDuplicateString(a2, newString[0]);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v22 = this;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v22);
    v18[0] = 0;
    v18[2] = 0;
    v9 = AutoImpersonate::ImpersonateClient((AutoImpersonate *)v18);
    v8 = v9;
    if ( v9 >= 0 )
    {
      wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(v17);
      wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::reset(
        v17,
        0);
      if ( !(unsigned __int8)std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(v17) )
      {
        v10 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,>(&v15);
        std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
          v17,
          v10);
        std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(&v15);
      }
      CurrentUserToken = DmGetCurrentUserToken(v17[0]);
      v8 = CurrentUserToken;
      if ( CurrentUserToken >= 0 )
      {
        AutoImpersonate::RevertToSelf((AutoImpersonate *)v18);
        v12 = lambda_983e7096dbc2b690dc04e89e03f79965_::_lambda_983e7096dbc2b690dc04e89e03f79965_(
                v20,
                newString,
                &v22,
                v17);
        v15 = 3;
        v16 = 128;
        v8 = ((__int64 (__fastcall *)(int *, struct Windows::Foundation::IAsyncAction **, __int64, __int64))Windows::Internal::MakeAsyncAction_Microsoft::WRL::AsyncCausalityOptions__SetEnrollmentAsDormantName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows::Internal::ComTaskPoolHandler__lambda_62c2241fa5d119ab705689d3d9afbb97___)(
               &v15,
               a3,
               v13,
               v12);
        lambda_983e7096dbc2b690dc04e89e03f79965_::__lambda_983e7096dbc2b690dc04e89e03f79965_(v20);
        std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v17);
        AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v18);
        if ( this )
          (*(void (__fastcall **)(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *))(*(_QWORD *)this + 16LL))(this);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6E2,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
          (const char *)(unsigned int)CurrentUserToken,
          v15);
        std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v17);
        AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v18);
        if ( this )
          (*(void (__fastcall **)(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *))(*(_QWORD *)this + 16LL))(this);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6DF,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)v9,
        v15);
      AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v18);
      if ( this )
        (*(void (__fastcall **)(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *))(*(_QWORD *)this + 16LL))(this);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6DA,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
      (const char *)(unsigned int)v7,
      v15);
  }
  std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(newString);
  return v8;
}

```

## disassembly

```asm
0x1800293b0  push    rbp
0x1800293b2  push    rbx
0x1800293b3  push    rsi
0x1800293b4  push    rdi
0x1800293b5  lea     rbp, [rsp-3Fh]
0x1800293ba  sub     rsp, 98h
0x1800293c1  mov     rsi, r8
0x1800293c4  mov     rdi, rdx
0x1800293c7  mov     rbx, rcx
0x1800293ca  lea     rcx, [rbp+57h+newString]
0x1800293ce  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x1800293d3  xor     edx, edx
0x1800293d5  lea     rcx, [rbp+57h+newString]
0x1800293d9  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x1800293de  lea     rcx, [rbp+57h+newString]
0x1800293e2  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x1800293e7  test    al, al
0x1800293e9  jnz     short loc_180029409
0x1800293eb  lea     rcx, [rbp+57h+var_70]
0x1800293ef  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x1800293f4  mov     rdx, rax
0x1800293f7  lea     rcx, [rbp+57h+newString]
0x1800293fb  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x180029400  lea     rcx, [rbp+57h+var_70]
0x180029404  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x180029409  mov     rdx, [rbp+57h+newString]; newString
0x18002940d  mov     rcx, rdi; string
0x180029410  call    cs:__imp_WindowsDuplicateString
0x180029417  nop     dword ptr [rax+rax+00h]
0x18002941c  mov     edi, eax
0x18002941e  test    eax, eax
0x180029420  jns     short loc_18002943F
0x180029422  mov     rcx, [rbp+5Fh]; this
0x180029426  mov     r9d, eax; char *
0x180029429  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180029430  mov     edx, 6DAh; void *
0x180029435  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002943a  jmp     loc_1800295A5
0x18002943f  mov     [rbp+57h+arg_18], rbx
0x180029443  lea     rcx, [rbp+57h+arg_18]
0x180029447  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18002944c  mov     [rbp+57h+var_70], 0
0x180029450  mov     [rbp+57h+var_6E], 0
0x180029454  lea     rcx, [rbp+57h+var_70]; this
0x180029458  call    ?ImpersonateClient@AutoImpersonate@@QEAAJXZ; AutoImpersonate::ImpersonateClient(void)
0x18002945d  mov     edi, eax
0x18002945f  test    eax, eax
0x180029461  jns     short loc_18002949F
0x180029463  mov     rcx, [rbp+5Fh]; this
0x180029467  mov     r9d, eax; char *
0x18002946a  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180029471  mov     edx, 6DFh; void *
0x180029476  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002947b  lea     rcx, [rbp+57h+var_70]; this
0x18002947f  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x180029484  nop
0x180029485  test    rbx, rbx
0x180029488  jz      short loc_18002949A
0x18002948a  mov     rax, [rbx]
0x18002948d  mov     rcx, rbx
0x180029490  mov     rax, [rax+10h]
0x180029494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029499  nop
0x18002949a  jmp     loc_1800295A5
0x18002949f  lea     rcx, [rbp+57h+var_80]
0x1800294a3  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x1800294a8  xor     edx, edx
0x1800294aa  lea     rcx, [rbp+57h+var_80]
0x1800294ae  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x1800294b3  lea     rcx, [rbp+57h+var_80]
0x1800294b7  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x1800294bc  test    al, al
0x1800294be  jnz     short loc_1800294DE
0x1800294c0  lea     rcx, [rbp+57h+var_90]
0x1800294c4  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,>(void)
0x1800294c9  mov     rdx, rax
0x1800294cc  lea     rcx, [rbp+57h+var_80]
0x1800294d0  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x1800294d5  lea     rcx, [rbp+57h+var_90]
0x1800294d9  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x1800294de  mov     rcx, [rbp+57h+var_80]
0x1800294e2  call    cs:__imp_?DmGetCurrentUserToken@@YAJPEAPEAX@Z; DmGetCurrentUserToken(void * *)
0x1800294e9  nop     dword ptr [rax+rax+00h]
0x1800294ee  mov     edi, eax
0x1800294f0  test    eax, eax
0x1800294f2  jns     short loc_180029536
0x1800294f4  mov     rcx, [rbp+5Fh]; this
0x1800294f8  mov     r9d, eax; char *
0x1800294fb  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180029502  mov     edx, 6E2h; void *
0x180029507  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002950c  lea     rcx, [rbp+57h+var_80]
0x180029510  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x180029515  lea     rcx, [rbp+57h+var_70]; this
0x180029519  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18002951e  nop
0x18002951f  test    rbx, rbx
0x180029522  jz      short loc_180029534
0x180029524  mov     rax, [rbx]
0x180029527  mov     rcx, rbx
0x18002952a  mov     rax, [rax+10h]
0x18002952e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029533  nop
0x180029534  jmp     short loc_1800295A5
0x180029536  lea     rcx, [rbp+57h+var_70]; this
0x18002953a  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x18002953f  lea     r9, [rbp+57h+var_80]
0x180029543  lea     r8, [rbp+57h+arg_18]
0x180029547  lea     rdx, [rbp+57h+newString]
0x18002954b  lea     rcx, [rbp+57h+var_50]
0x18002954f  call    _lambda_983e7096dbc2b690dc04e89e03f79965____lambda_983e7096dbc2b690dc04e89e03f79965_
0x180029554  mov     [rbp+57h+var_90], 3
0x18002955b  mov     [rbp+57h+var_8C], 80h
0x180029563  mov     r9, rax
0x180029566  mov     rdx, rsi
0x180029569  lea     rcx, [rbp+57h+var_90]
0x18002956d  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__SetEnrollmentAsDormantName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_62c2241fa5d119ab705689d3d9afbb97___
0x180029572  mov     edi, eax
0x180029574  lea     rcx, [rbp+57h+var_50]
0x180029578  call    _lambda_983e7096dbc2b690dc04e89e03f79965_____lambda_983e7096dbc2b690dc04e89e03f79965_
0x18002957d  lea     rcx, [rbp+57h+var_80]
0x180029581  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x180029586  lea     rcx, [rbp+57h+var_70]; this
0x18002958a  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18002958f  nop
0x180029590  test    rbx, rbx
0x180029593  jz      short loc_1800295A5
0x180029595  mov     rcx, [rbx]
0x180029598  mov     rax, [rcx+10h]
0x18002959c  mov     rcx, rbx
0x18002959f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295a4  nop
0x1800295a5  lea     rcx, [rbp+57h+newString]
0x1800295a9  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x1800295ae  mov     eax, edi
0x1800295b0  add     rsp, 98h
0x1800295b7  pop     rdi
0x1800295b8  pop     rsi
0x1800295b9  pop     rbx
0x1800295ba  pop     rbp
0x1800295bb  retn
```
