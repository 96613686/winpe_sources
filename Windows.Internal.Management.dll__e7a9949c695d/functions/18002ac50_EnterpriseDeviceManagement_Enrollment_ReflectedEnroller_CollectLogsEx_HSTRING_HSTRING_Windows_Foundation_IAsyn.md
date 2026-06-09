# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::CollectLogsEx(HSTRING__ *,HSTRING__ *,Windows::Foundation::IAsyncAction * *)

- ea: `0x18002ac50`
- end: `0x18002aed8`
- name: `?CollectLogsEx@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJPEAUHSTRING__@@0PEAPEAUIAsyncAction@Foundation@Windows@@@Z`
- size: `648`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *this, HSTRING, HSTRING, struct Windows::Foundation::IAsyncAction **)`
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
- `0x18001c7fc`
- `0x18001eae4`
- `0x18001f0e4`
- `0x180022924`
- `0x18002ac50`
- `0x18003b0f8`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!DmGetCurrentUserToken` at `0x18002adf0`
- `DMCmnUtils!DmGetCurrentUserToken` at `0x18002adf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002acb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002ad24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002acb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002ad24`

## pseudocode

```c
__int64 __fastcall EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::CollectLogsEx(
        EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *this,
        HSTRING a2,
        HSTRING a3,
        struct Windows::Foundation::IAsyncAction **a4)
{
  __int64 v8; // rax
  HRESULT v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rax
  HRESULT v12; // eax
  int v13; // eax
  __int64 v14; // rax
  int CurrentUserToken; // eax
  __int64 v16; // rax
  __int64 v17; // r8
  int v19; // [rsp+20h] [rbp-79h]
  _BYTE v20[16]; // [rsp+30h] [rbp-69h] BYREF
  HSTRING *v21[2]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v22[12]; // [rsp+50h] [rbp-49h] BYREF
  void **v23[2]; // [rsp+60h] [rbp-39h] BYREF
  HSTRING *newString[2]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v25[16]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v26[96]; // [rsp+90h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(newString);
  wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(
    newString,
    0);
  if ( !(unsigned __int8)std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(newString) )
  {
    v8 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(v20);
    std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
      newString,
      v8);
    std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v20);
  }
  v9 = WindowsDuplicateString(a3, newString[0]);
  v10 = v9;
  if ( v9 >= 0 )
  {
    wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(v21);
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(
      v21,
      0);
    if ( !(unsigned __int8)std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(v21) )
    {
      v11 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(v20);
      std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
        v21,
        v11);
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v20);
    }
    v12 = WindowsDuplicateString(a2, v21[0]);
    v10 = v12;
    if ( v12 >= 0 )
    {
      *(_QWORD *)v22 = this;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(v22);
      v20[0] = 0;
      v20[2] = 0;
      v13 = AutoImpersonate::ImpersonateClient((AutoImpersonate *)v20);
      v10 = v13;
      if ( v13 >= 0 )
      {
        wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(v23);
        wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::reset(
          v23,
          0);
        if ( !(unsigned __int8)std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(v23) )
        {
          v14 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,>(v25);
          std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
            v23,
            v14);
          std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v25);
        }
        CurrentUserToken = DmGetCurrentUserToken(v23[0]);
        v10 = CurrentUserToken;
        if ( CurrentUserToken >= 0 )
        {
          AutoImpersonate::RevertToSelf((AutoImpersonate *)v20);
          v16 = lambda_9b3f0fd6c649547fba8ab002190a251b_::_lambda_9b3f0fd6c649547fba8ab002190a251b_(
                  (unsigned int)v26,
                  (unsigned int)v21,
                  (unsigned int)newString,
                  (unsigned int)v22,
                  (__int64)v23);
          *(_DWORD *)v22 = 3;
          *(_QWORD *)&v22[4] = 128;
          v10 = Windows::Internal::MakeAsyncAction_Microsoft::WRL::AsyncCausalityOptions__CollectLogsExAsyncActionName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows::Internal::ComTaskPoolHandler__lambda_9b3f0fd6c649547fba8ab002190a251b___(
                  v22,
                  a4,
                  v17,
                  v16);
          lambda_9b3f0fd6c649547fba8ab002190a251b_::__lambda_9b3f0fd6c649547fba8ab002190a251b_(v26);
          std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v23);
          AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v20);
          if ( this )
            (*(void (__fastcall **)(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *))(*(_QWORD *)this + 16LL))(this);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x769,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
            (const char *)(unsigned int)CurrentUserToken,
            v19);
          std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v23);
          AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v20);
          if ( this )
            (*(void (__fastcall **)(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *))(*(_QWORD *)this + 16LL))(this);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x766,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
          (const char *)(unsigned int)v13,
          v19);
        AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v20);
        if ( this )
          (*(void (__fastcall **)(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *))(*(_QWORD *)this + 16LL))(this);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x761,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)v12,
        v19);
    }
    std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v21);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x75F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
      (const char *)(unsigned int)v9,
      v19);
  }
  std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(newString);
  return v10;
}

```

## disassembly

```asm
0x18002ac50  push    rbp
0x18002ac52  push    rbx
0x18002ac53  push    rsi
0x18002ac54  push    rdi
0x18002ac55  push    r14
0x18002ac57  lea     rbp, [rsp-37h]
0x18002ac5c  sub     rsp, 0D0h
0x18002ac63  mov     r14, r9
0x18002ac66  mov     rdi, r8
0x18002ac69  mov     rsi, rdx
0x18002ac6c  mov     rbx, rcx
0x18002ac6f  lea     rcx, [rbp+57h+newString]
0x18002ac73  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18002ac78  xor     edx, edx
0x18002ac7a  lea     rcx, [rbp+57h+newString]
0x18002ac7e  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18002ac83  lea     rcx, [rbp+57h+newString]
0x18002ac87  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18002ac8c  test    al, al
0x18002ac8e  jnz     short loc_18002ACAE
0x18002ac90  lea     rcx, [rbp+57h+var_C0]
0x18002ac94  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x18002ac99  mov     rdx, rax
0x18002ac9c  lea     rcx, [rbp+57h+newString]
0x18002aca0  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18002aca5  lea     rcx, [rbp+57h+var_C0]
0x18002aca9  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18002acae  mov     rdx, [rbp+57h+newString]; newString
0x18002acb2  mov     rcx, rdi; string
0x18002acb5  call    cs:__imp_WindowsDuplicateString
0x18002acbb  mov     edi, eax
0x18002acbd  test    eax, eax
0x18002acbf  jns     short loc_18002ACDE
0x18002acc1  mov     rcx, [rbp+5Fh]; this
0x18002acc5  mov     r9d, eax; char *
0x18002acc8  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002accf  mov     edx, 75Fh; void *
0x18002acd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002acd9  jmp     loc_18002AEBF
0x18002acde  lea     rcx, [rbp+57h+var_B0]
0x18002ace2  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18002ace7  xor     edx, edx
0x18002ace9  lea     rcx, [rbp+57h+var_B0]
0x18002aced  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18002acf2  lea     rcx, [rbp+57h+var_B0]
0x18002acf6  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18002acfb  test    al, al
0x18002acfd  jnz     short loc_18002AD1D
0x18002acff  lea     rcx, [rbp+57h+var_C0]
0x18002ad03  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x18002ad08  mov     rdx, rax
0x18002ad0b  lea     rcx, [rbp+57h+var_B0]
0x18002ad0f  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18002ad14  lea     rcx, [rbp+57h+var_C0]
0x18002ad18  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18002ad1d  mov     rdx, [rbp+57h+var_B0]; newString
0x18002ad21  mov     rcx, rsi; string
0x18002ad24  call    cs:__imp_WindowsDuplicateString
0x18002ad2a  mov     edi, eax
0x18002ad2c  test    eax, eax
0x18002ad2e  jns     short loc_18002AD4D
0x18002ad30  mov     rcx, [rbp+5Fh]; this
0x18002ad34  mov     r9d, eax; char *
0x18002ad37  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002ad3e  mov     edx, 761h; void *
0x18002ad43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ad48  jmp     loc_18002AEB6
0x18002ad4d  mov     [rbp+57h+var_A0], rbx
0x18002ad51  lea     rcx, [rbp+57h+var_A0]
0x18002ad55  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18002ad5a  mov     [rbp+57h+var_C0], 0
0x18002ad5e  mov     [rbp+57h+var_BE], 0
0x18002ad62  lea     rcx, [rbp+57h+var_C0]; this
0x18002ad66  call    ?ImpersonateClient@AutoImpersonate@@QEAAJXZ; AutoImpersonate::ImpersonateClient(void)
0x18002ad6b  mov     edi, eax
0x18002ad6d  test    eax, eax
0x18002ad6f  jns     short loc_18002ADAD
0x18002ad71  mov     rcx, [rbp+5Fh]; this
0x18002ad75  mov     r9d, eax; char *
0x18002ad78  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002ad7f  mov     edx, 766h; void *
0x18002ad84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ad89  lea     rcx, [rbp+57h+var_C0]; this
0x18002ad8d  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18002ad92  nop
0x18002ad93  test    rbx, rbx
0x18002ad96  jz      short loc_18002ADA8
0x18002ad98  mov     rax, [rbx]
0x18002ad9b  mov     rcx, rbx
0x18002ad9e  mov     rax, [rax+10h]
0x18002ada2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ada7  nop
0x18002ada8  jmp     loc_18002AEB6
0x18002adad  lea     rcx, [rbp+57h+var_90]
0x18002adb1  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18002adb6  xor     edx, edx
0x18002adb8  lea     rcx, [rbp+57h+var_90]
0x18002adbc  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x18002adc1  lea     rcx, [rbp+57h+var_90]
0x18002adc5  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18002adca  test    al, al
0x18002adcc  jnz     short loc_18002ADEC
0x18002adce  lea     rcx, [rbp+57h+var_70]
0x18002add2  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,>(void)
0x18002add7  mov     rdx, rax
0x18002adda  lea     rcx, [rbp+57h+var_90]
0x18002adde  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18002ade3  lea     rcx, [rbp+57h+var_70]
0x18002ade7  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18002adec  mov     rcx, [rbp+57h+var_90]
0x18002adf0  call    cs:__imp_?DmGetCurrentUserToken@@YAJPEAPEAX@Z; DmGetCurrentUserToken(void * *)
0x18002adf6  mov     edi, eax
0x18002adf8  test    eax, eax
0x18002adfa  jns     short loc_18002AE3E
0x18002adfc  mov     rcx, [rbp+5Fh]; this
0x18002ae00  mov     r9d, eax; char *
0x18002ae03  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002ae0a  mov     edx, 769h; void *
0x18002ae0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ae14  lea     rcx, [rbp+57h+var_90]
0x18002ae18  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18002ae1d  lea     rcx, [rbp+57h+var_C0]; this
0x18002ae21  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18002ae26  nop
0x18002ae27  test    rbx, rbx
0x18002ae2a  jz      short loc_18002AE3C
0x18002ae2c  mov     rax, [rbx]
0x18002ae2f  mov     rcx, rbx
0x18002ae32  mov     rax, [rax+10h]
0x18002ae36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae3b  nop
0x18002ae3c  jmp     short loc_18002AEB6
0x18002ae3e  lea     rcx, [rbp+57h+var_C0]; this
0x18002ae42  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x18002ae47  lea     rax, [rbp+57h+var_90]
0x18002ae4b  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18002ae50  lea     r9, [rbp+57h+var_A0]
0x18002ae54  lea     r8, [rbp+57h+newString]
0x18002ae58  lea     rdx, [rbp+57h+var_B0]
0x18002ae5c  lea     rcx, [rbp+57h+var_60]
0x18002ae60  call    _lambda_9b3f0fd6c649547fba8ab002190a251b____lambda_9b3f0fd6c649547fba8ab002190a251b_
0x18002ae65  mov     dword ptr [rbp+57h+var_A0], 3
0x18002ae6c  mov     [rbp+57h+var_A0+4], 80h
0x18002ae74  mov     r9, rax
0x18002ae77  mov     rdx, r14
0x18002ae7a  lea     rcx, [rbp+57h+var_A0]
0x18002ae7e  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__CollectLogsExAsyncActionName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_9b3f0fd6c649547fba8ab002190a251b___
0x18002ae83  mov     edi, eax
0x18002ae85  lea     rcx, [rbp+57h+var_60]
0x18002ae89  call    _lambda_9b3f0fd6c649547fba8ab002190a251b_____lambda_9b3f0fd6c649547fba8ab002190a251b_
0x18002ae8e  lea     rcx, [rbp+57h+var_90]
0x18002ae92  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18002ae97  lea     rcx, [rbp+57h+var_C0]; this
0x18002ae9b  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18002aea0  nop
0x18002aea1  test    rbx, rbx
0x18002aea4  jz      short loc_18002AEB6
0x18002aea6  mov     rcx, [rbx]
0x18002aea9  mov     rax, [rcx+10h]
0x18002aead  mov     rcx, rbx
0x18002aeb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aeb5  nop
0x18002aeb6  lea     rcx, [rbp+57h+var_B0]
0x18002aeba  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18002aebf  lea     rcx, [rbp+57h+newString]
0x18002aec3  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18002aec8  mov     eax, edi
0x18002aeca  add     rsp, 0D0h
0x18002aed1  pop     r14
0x18002aed3  pop     rdi
0x18002aed4  pop     rsi
0x18002aed5  pop     rbx
0x18002aed6  pop     rbp
0x18002aed7  retn
```
