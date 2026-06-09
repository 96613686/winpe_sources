# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::CollectLogs(HSTRING__ *,Windows::Foundation::IAsyncAction * *)

- ea: `0x18002aa40`
- end: `0x18002ac40`
- name: `?CollectLogs@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJPEAUHSTRING__@@PEAPEAUIAsyncAction@Foundation@Windows@@@Z`
- size: `512`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *this, HSTRING, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a2a4`
- `0x180016b54`
- `0x180017074`
- `0x180017284`
- `0x18001736c`
- `0x1800173ec`
- `0x180018f88`
- `0x180018ff0`
- `0x1800199f8`
- `0x180019b2c`
- `0x180019f1c`
- `0x18001ca6c`
- `0x18001eae4`
- `0x18001ee88`
- `0x1800227dc`
- `0x18002aa40`
- `0x18003b0f8`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!DmGetCurrentUserToken` at `0x18002ab6c`
- `DMCmnUtils!DmGetCurrentUserToken` at `0x18002ab6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002aaa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002aaa0`

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
0x18002aa40  push    rbp
0x18002aa42  push    rbx
0x18002aa43  push    rsi
0x18002aa44  push    rdi
0x18002aa45  lea     rbp, [rsp-3Fh]
0x18002aa4a  sub     rsp, 98h
0x18002aa51  mov     rsi, r8
0x18002aa54  mov     rdi, rdx
0x18002aa57  mov     rbx, rcx
0x18002aa5a  lea     rcx, [rbp+57h+newString]
0x18002aa5e  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18002aa63  xor     edx, edx
0x18002aa65  lea     rcx, [rbp+57h+newString]
0x18002aa69  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18002aa6e  lea     rcx, [rbp+57h+newString]
0x18002aa72  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18002aa77  test    al, al
0x18002aa79  jnz     short loc_18002AA99
0x18002aa7b  lea     rcx, [rbp+57h+var_70]
0x18002aa7f  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x18002aa84  mov     rdx, rax
0x18002aa87  lea     rcx, [rbp+57h+newString]
0x18002aa8b  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18002aa90  lea     rcx, [rbp+57h+var_70]
0x18002aa94  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18002aa99  mov     rdx, [rbp+57h+newString]; newString
0x18002aa9d  mov     rcx, rdi; string
0x18002aaa0  call    cs:__imp_WindowsDuplicateString
0x18002aaa6  mov     edi, eax
0x18002aaa8  test    eax, eax
0x18002aaaa  jns     short loc_18002AAC9
0x18002aaac  mov     rcx, [rbp+5Fh]; this
0x18002aab0  mov     r9d, eax; char *
0x18002aab3  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002aaba  mov     edx, 6DAh; void *
0x18002aabf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002aac4  jmp     loc_18002AC29
0x18002aac9  mov     [rbp+57h+arg_18], rbx
0x18002aacd  lea     rcx, [rbp+57h+arg_18]
0x18002aad1  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18002aad6  mov     [rbp+57h+var_70], 0
0x18002aada  mov     [rbp+57h+var_6E], 0
0x18002aade  lea     rcx, [rbp+57h+var_70]; this
0x18002aae2  call    ?ImpersonateClient@AutoImpersonate@@QEAAJXZ; AutoImpersonate::ImpersonateClient(void)
0x18002aae7  mov     edi, eax
0x18002aae9  test    eax, eax
0x18002aaeb  jns     short loc_18002AB29
0x18002aaed  mov     rcx, [rbp+5Fh]; this
0x18002aaf1  mov     r9d, eax; char *
0x18002aaf4  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002aafb  mov     edx, 6DFh; void *
0x18002ab00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ab05  lea     rcx, [rbp+57h+var_70]; this
0x18002ab09  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18002ab0e  nop
0x18002ab0f  test    rbx, rbx
0x18002ab12  jz      short loc_18002AB24
0x18002ab14  mov     rax, [rbx]
0x18002ab17  mov     rcx, rbx
0x18002ab1a  mov     rax, [rax+10h]
0x18002ab1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab23  nop
0x18002ab24  jmp     loc_18002AC29
0x18002ab29  lea     rcx, [rbp+57h+var_80]
0x18002ab2d  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18002ab32  xor     edx, edx
0x18002ab34  lea     rcx, [rbp+57h+var_80]
0x18002ab38  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x18002ab3d  lea     rcx, [rbp+57h+var_80]
0x18002ab41  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18002ab46  test    al, al
0x18002ab48  jnz     short loc_18002AB68
0x18002ab4a  lea     rcx, [rbp+57h+var_90]
0x18002ab4e  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,>(void)
0x18002ab53  mov     rdx, rax
0x18002ab56  lea     rcx, [rbp+57h+var_80]
0x18002ab5a  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18002ab5f  lea     rcx, [rbp+57h+var_90]
0x18002ab63  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18002ab68  mov     rcx, [rbp+57h+var_80]
0x18002ab6c  call    cs:__imp_?DmGetCurrentUserToken@@YAJPEAPEAX@Z; DmGetCurrentUserToken(void * *)
0x18002ab72  mov     edi, eax
0x18002ab74  test    eax, eax
0x18002ab76  jns     short loc_18002ABBA
0x18002ab78  mov     rcx, [rbp+5Fh]; this
0x18002ab7c  mov     r9d, eax; char *
0x18002ab7f  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002ab86  mov     edx, 6E2h; void *
0x18002ab8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ab90  lea     rcx, [rbp+57h+var_80]
0x18002ab94  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18002ab99  lea     rcx, [rbp+57h+var_70]; this
0x18002ab9d  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18002aba2  nop
0x18002aba3  test    rbx, rbx
0x18002aba6  jz      short loc_18002ABB8
0x18002aba8  mov     rax, [rbx]
0x18002abab  mov     rcx, rbx
0x18002abae  mov     rax, [rax+10h]
0x18002abb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abb7  nop
0x18002abb8  jmp     short loc_18002AC29
0x18002abba  lea     rcx, [rbp+57h+var_70]; this
0x18002abbe  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x18002abc3  lea     r9, [rbp+57h+var_80]
0x18002abc7  lea     r8, [rbp+57h+arg_18]
0x18002abcb  lea     rdx, [rbp+57h+newString]
0x18002abcf  lea     rcx, [rbp+57h+var_50]
0x18002abd3  call    _lambda_983e7096dbc2b690dc04e89e03f79965____lambda_983e7096dbc2b690dc04e89e03f79965_
0x18002abd8  mov     [rbp+57h+var_90], 3
0x18002abdf  mov     [rbp+57h+var_8C], 80h
0x18002abe7  mov     r9, rax
0x18002abea  mov     rdx, rsi
0x18002abed  lea     rcx, [rbp+57h+var_90]
0x18002abf1  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__SetEnrollmentAsDormantName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_62c2241fa5d119ab705689d3d9afbb97___
0x18002abf6  mov     edi, eax
0x18002abf8  lea     rcx, [rbp+57h+var_50]
0x18002abfc  call    _lambda_983e7096dbc2b690dc04e89e03f79965_____lambda_983e7096dbc2b690dc04e89e03f79965_
0x18002ac01  lea     rcx, [rbp+57h+var_80]
0x18002ac05  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18002ac0a  lea     rcx, [rbp+57h+var_70]; this
0x18002ac0e  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18002ac13  nop
0x18002ac14  test    rbx, rbx
0x18002ac17  jz      short loc_18002AC29
0x18002ac19  mov     rcx, [rbx]
0x18002ac1c  mov     rax, [rcx+10h]
0x18002ac20  mov     rcx, rbx
0x18002ac23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac28  nop
0x18002ac29  lea     rcx, [rbp+57h+newString]
0x18002ac2d  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18002ac32  mov     eax, edi
0x18002ac34  add     rsp, 98h
0x18002ac3b  pop     rdi
0x18002ac3c  pop     rsi
0x18002ac3d  pop     rbx
0x18002ac3e  pop     rbp
0x18002ac3f  retn
```
