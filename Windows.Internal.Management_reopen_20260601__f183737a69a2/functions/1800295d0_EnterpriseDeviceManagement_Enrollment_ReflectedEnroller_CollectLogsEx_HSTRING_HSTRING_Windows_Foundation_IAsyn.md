# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::CollectLogsEx(HSTRING__ *,HSTRING__ *,Windows::Foundation::IAsyncAction * *)

- ea: `0x1800295d0`
- end: `0x18002986b`
- name: `?CollectLogsEx@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJPEAUHSTRING__@@0PEAPEAUIAsyncAction@Foundation@Windows@@@Z`
- size: `667`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *this, HSTRING, HSTRING, struct Windows::Foundation::IAsyncAction **)`
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
- `0x18001acc4`
- `0x18001d00c`
- `0x18001d620`
- `0x180020f78`
- `0x1800295d0`
- `0x18003a488`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!DmGetCurrentUserToken` at `0x18002977c`
- `DMCmnUtils!DmGetCurrentUserToken` at `0x18002977c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180029635`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800296aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180029635`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800296aa`

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
0x1800295d0  push    rbp
0x1800295d2  push    rbx
0x1800295d3  push    rsi
0x1800295d4  push    rdi
0x1800295d5  push    r14
0x1800295d7  lea     rbp, [rsp-37h]
0x1800295dc  sub     rsp, 0D0h
0x1800295e3  mov     r14, r9
0x1800295e6  mov     rdi, r8
0x1800295e9  mov     rsi, rdx
0x1800295ec  mov     rbx, rcx
0x1800295ef  lea     rcx, [rbp+57h+newString]
0x1800295f3  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x1800295f8  xor     edx, edx
0x1800295fa  lea     rcx, [rbp+57h+newString]
0x1800295fe  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x180029603  lea     rcx, [rbp+57h+newString]
0x180029607  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18002960c  test    al, al
0x18002960e  jnz     short loc_18002962E
0x180029610  lea     rcx, [rbp+57h+var_C0]
0x180029614  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x180029619  mov     rdx, rax
0x18002961c  lea     rcx, [rbp+57h+newString]
0x180029620  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x180029625  lea     rcx, [rbp+57h+var_C0]
0x180029629  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18002962e  mov     rdx, [rbp+57h+newString]; newString
0x180029632  mov     rcx, rdi; string
0x180029635  call    cs:__imp_WindowsDuplicateString
0x18002963c  nop     dword ptr [rax+rax+00h]
0x180029641  mov     edi, eax
0x180029643  test    eax, eax
0x180029645  jns     short loc_180029664
0x180029647  mov     rcx, [rbp+5Fh]; this
0x18002964b  mov     r9d, eax; char *
0x18002964e  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180029655  mov     edx, 75Fh; void *
0x18002965a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002965f  jmp     loc_180029851
0x180029664  lea     rcx, [rbp+57h+var_B0]
0x180029668  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18002966d  xor     edx, edx
0x18002966f  lea     rcx, [rbp+57h+var_B0]
0x180029673  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x180029678  lea     rcx, [rbp+57h+var_B0]
0x18002967c  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x180029681  test    al, al
0x180029683  jnz     short loc_1800296A3
0x180029685  lea     rcx, [rbp+57h+var_C0]
0x180029689  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x18002968e  mov     rdx, rax
0x180029691  lea     rcx, [rbp+57h+var_B0]
0x180029695  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18002969a  lea     rcx, [rbp+57h+var_C0]
0x18002969e  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x1800296a3  mov     rdx, [rbp+57h+var_B0]; newString
0x1800296a7  mov     rcx, rsi; string
0x1800296aa  call    cs:__imp_WindowsDuplicateString
0x1800296b1  nop     dword ptr [rax+rax+00h]
0x1800296b6  mov     edi, eax
0x1800296b8  test    eax, eax
0x1800296ba  jns     short loc_1800296D9
0x1800296bc  mov     rcx, [rbp+5Fh]; this
0x1800296c0  mov     r9d, eax; char *
0x1800296c3  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800296ca  mov     edx, 761h; void *
0x1800296cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800296d4  jmp     loc_180029848
0x1800296d9  mov     [rbp+57h+var_A0], rbx
0x1800296dd  lea     rcx, [rbp+57h+var_A0]
0x1800296e1  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x1800296e6  mov     [rbp+57h+var_C0], 0
0x1800296ea  mov     [rbp+57h+var_BE], 0
0x1800296ee  lea     rcx, [rbp+57h+var_C0]; this
0x1800296f2  call    ?ImpersonateClient@AutoImpersonate@@QEAAJXZ; AutoImpersonate::ImpersonateClient(void)
0x1800296f7  mov     edi, eax
0x1800296f9  test    eax, eax
0x1800296fb  jns     short loc_180029739
0x1800296fd  mov     rcx, [rbp+5Fh]; this
0x180029701  mov     r9d, eax; char *
0x180029704  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002970b  mov     edx, 766h; void *
0x180029710  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029715  lea     rcx, [rbp+57h+var_C0]; this
0x180029719  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18002971e  nop
0x18002971f  test    rbx, rbx
0x180029722  jz      short loc_180029734
0x180029724  mov     rax, [rbx]
0x180029727  mov     rcx, rbx
0x18002972a  mov     rax, [rax+10h]
0x18002972e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029733  nop
0x180029734  jmp     loc_180029848
0x180029739  lea     rcx, [rbp+57h+var_90]
0x18002973d  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x180029742  xor     edx, edx
0x180029744  lea     rcx, [rbp+57h+var_90]
0x180029748  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x18002974d  lea     rcx, [rbp+57h+var_90]
0x180029751  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x180029756  test    al, al
0x180029758  jnz     short loc_180029778
0x18002975a  lea     rcx, [rbp+57h+var_70]
0x18002975e  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,>(void)
0x180029763  mov     rdx, rax
0x180029766  lea     rcx, [rbp+57h+var_90]
0x18002976a  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18002976f  lea     rcx, [rbp+57h+var_70]
0x180029773  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x180029778  mov     rcx, [rbp+57h+var_90]
0x18002977c  call    cs:__imp_?DmGetCurrentUserToken@@YAJPEAPEAX@Z; DmGetCurrentUserToken(void * *)
0x180029783  nop     dword ptr [rax+rax+00h]
0x180029788  mov     edi, eax
0x18002978a  test    eax, eax
0x18002978c  jns     short loc_1800297D0
0x18002978e  mov     rcx, [rbp+5Fh]; this
0x180029792  mov     r9d, eax; char *
0x180029795  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002979c  mov     edx, 769h; void *
0x1800297a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800297a6  lea     rcx, [rbp+57h+var_90]
0x1800297aa  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x1800297af  lea     rcx, [rbp+57h+var_C0]; this
0x1800297b3  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x1800297b8  nop
0x1800297b9  test    rbx, rbx
0x1800297bc  jz      short loc_1800297CE
0x1800297be  mov     rax, [rbx]
0x1800297c1  mov     rcx, rbx
0x1800297c4  mov     rax, [rax+10h]
0x1800297c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297cd  nop
0x1800297ce  jmp     short loc_180029848
0x1800297d0  lea     rcx, [rbp+57h+var_C0]; this
0x1800297d4  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x1800297d9  lea     rax, [rbp+57h+var_90]
0x1800297dd  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1800297e2  lea     r9, [rbp+57h+var_A0]
0x1800297e6  lea     r8, [rbp+57h+newString]
0x1800297ea  lea     rdx, [rbp+57h+var_B0]
0x1800297ee  lea     rcx, [rbp+57h+var_60]
0x1800297f2  call    _lambda_9b3f0fd6c649547fba8ab002190a251b____lambda_9b3f0fd6c649547fba8ab002190a251b_
0x1800297f7  mov     dword ptr [rbp+57h+var_A0], 3
0x1800297fe  mov     [rbp+57h+var_A0+4], 80h
0x180029806  mov     r9, rax
0x180029809  mov     rdx, r14
0x18002980c  lea     rcx, [rbp+57h+var_A0]
0x180029810  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__CollectLogsExAsyncActionName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_9b3f0fd6c649547fba8ab002190a251b___
0x180029815  mov     edi, eax
0x180029817  lea     rcx, [rbp+57h+var_60]
0x18002981b  call    _lambda_9b3f0fd6c649547fba8ab002190a251b_____lambda_9b3f0fd6c649547fba8ab002190a251b_
0x180029820  lea     rcx, [rbp+57h+var_90]
0x180029824  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x180029829  lea     rcx, [rbp+57h+var_C0]; this
0x18002982d  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x180029832  nop
0x180029833  test    rbx, rbx
0x180029836  jz      short loc_180029848
0x180029838  mov     rcx, [rbx]
0x18002983b  mov     rax, [rcx+10h]
0x18002983f  mov     rcx, rbx
0x180029842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029847  nop
0x180029848  lea     rcx, [rbp+57h+var_B0]
0x18002984c  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x180029851  lea     rcx, [rbp+57h+newString]
0x180029855  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18002985a  mov     eax, edi
0x18002985c  add     rsp, 0D0h
0x180029863  pop     r14
0x180029865  pop     rdi
0x180029866  pop     rsi
0x180029867  pop     rbx
0x180029868  pop     rbp
0x180029869  retn
```
