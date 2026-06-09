# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::RetrieveCustomErrorText(int,Windows::Foundation::IAsyncOperation<HSTRING__ *> * *)

- ea: `0x1800332f0`
- end: `0x1800334cf`
- name: `?RetrieveCustomErrorText@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJHPEAPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@Z`
- size: `479`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a5c4`
- `0x180017298`
- `0x180017860`
- `0x180017b70`
- `0x180017bf0`
- `0x18001823c`
- `0x1800184e8`
- `0x180018738`
- `0x18001c1a4`
- `0x18001c920`
- `0x18001d6d0`
- `0x180020d50`
- `0x1800332f0`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x180033331`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180033331`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800333e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800333e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033410`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033449`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033410`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033449`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033398`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033398`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::RetrieveCustomErrorText(
        __int64 a1,
        int a2,
        __int64 a3)
{
  int ActiveUserSid; // eax
  unsigned int v7; // ebx
  __int64 v8; // rax
  HRESULT v9; // eax
  __int64 v10; // rax
  __int64 v11; // r8
  int v13[4]; // [rsp+20h] [rbp-40h] BYREF
  HSTRING *newString[2]; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HSTRING string; // [rsp+80h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp+38h] BYREF

  *(_QWORD *)v13 = a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(v13);
  wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(newString);
  if ( a2 )
  {
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(
      newString,
      0);
  }
  else
  {
    hMem = 0;
    ActiveUserSid = DmGetActiveUserSid((unsigned __int16 **)&hMem);
    v7 = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x706,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)ActiveUserSid,
        v13[0]);
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(newString);
      if ( a1 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
      return v7;
    }
    string = 0;
    Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(&string, &hMem);
    LocalFree(hMem);
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(
      newString,
      0);
    if ( !(unsigned __int8)std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(newString) )
    {
      v8 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(v15);
      std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
        newString,
        v8);
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v15);
    }
    v9 = WindowsDuplicateString(string, newString[0]);
    v7 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x70A,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)v9,
        v13[0]);
      WindowsDeleteString(string);
      string = 0;
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(newString);
      if ( a1 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
      return v7;
    }
    WindowsDeleteString(string);
  }
  v10 = lambda_b2bb3cc6b7b45741a3011b9c2260506d_::_lambda_b2bb3cc6b7b45741a3011b9c2260506d_(v15, v13, newString);
  v13[0] = 3;
  *(_QWORD *)&v13[1] = 128;
  v7 = ((__int64 (__fastcall *)(int *, __int64, __int64, __int64))Windows::Internal::MakeAsyncOperation_Windows::Internal::CHSTRINGResult_HSTRING_____Windows::Internal::ComTaskPoolHandler__lambda_b2bb3cc6b7b45741a3011b9c2260506d___)(
         v13,
         a3,
         v11,
         v10);
  lambda_b2bb3cc6b7b45741a3011b9c2260506d_::__lambda_b2bb3cc6b7b45741a3011b9c2260506d_(v15);
  std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(newString);
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return v7;
}

```

## disassembly

```asm
0x1800332f0  mov     [rsp-18h+arg_8], rbx
0x1800332f5  push    rbp
0x1800332f6  push    rsi
0x1800332f7  push    rdi
0x1800332f8  mov     rbp, rsp
0x1800332fb  sub     rsp, 60h
0x1800332ff  mov     rsi, r8
0x180033302  mov     ebx, edx
0x180033304  mov     rdi, rcx
0x180033307  mov     qword ptr [rbp+var_40], rcx
0x18003330b  lea     rcx, [rbp+var_40]
0x18003330f  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180033314  lea     rcx, [rbp+newString]
0x180033318  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18003331d  test    ebx, ebx
0x18003331f  jnz     loc_180033457
0x180033325  mov     [rbp+hMem], 0
0x18003332d  lea     rcx, [rbp+hMem]
0x180033331  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180033338  nop     dword ptr [rax+rax+00h]
0x18003333d  mov     ebx, eax
0x18003333f  test    eax, eax
0x180033341  jns     short loc_18003337F
0x180033343  mov     rcx, [rbp+18h]; this
0x180033347  mov     r9d, eax; char *
0x18003334a  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180033351  mov     edx, 706h; void *
0x180033356  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003335b  lea     rcx, [rbp+newString]
0x18003335f  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x180033364  nop
0x180033365  test    rdi, rdi
0x180033368  jz      short loc_18003337A
0x18003336a  mov     rax, [rdi]
0x18003336d  mov     rcx, rdi
0x180033370  mov     rax, [rax+10h]
0x180033374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033379  nop
0x18003337a  jmp     loc_1800334BC
0x18003337f  mov     [rbp+string], 0
0x180033387  lea     rdx, [rbp+hMem]
0x18003338b  lea     rcx, [rbp+string]
0x18003338f  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x180033394  mov     rcx, [rbp+hMem]; hMem
0x180033398  call    cs:__imp_LocalFree
0x18003339f  nop     dword ptr [rax+rax+00h]
0x1800333a4  xor     edx, edx
0x1800333a6  lea     rcx, [rbp+newString]
0x1800333aa  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x1800333af  lea     rcx, [rbp+newString]
0x1800333b3  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x1800333b8  test    al, al
0x1800333ba  jnz     short loc_1800333DA
0x1800333bc  lea     rcx, [rbp+var_20]
0x1800333c0  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x1800333c5  mov     rdx, rax
0x1800333c8  lea     rcx, [rbp+newString]
0x1800333cc  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x1800333d1  lea     rcx, [rbp+var_20]
0x1800333d5  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x1800333da  mov     rdx, [rbp+newString]; newString
0x1800333de  mov     rcx, [rbp+string]; string
0x1800333e2  call    cs:__imp_WindowsDuplicateString
0x1800333e9  nop     dword ptr [rax+rax+00h]
0x1800333ee  mov     ebx, eax
0x1800333f0  test    eax, eax
0x1800333f2  jns     short loc_180033445
0x1800333f4  mov     rcx, [rbp+18h]; this
0x1800333f8  mov     r9d, eax; char *
0x1800333fb  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180033402  mov     edx, 70Ah; void *
0x180033407  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003340c  mov     rcx, [rbp+string]; string
0x180033410  call    cs:__imp_WindowsDeleteString
0x180033417  nop     dword ptr [rax+rax+00h]
0x18003341c  mov     [rbp+string], 0
0x180033424  lea     rcx, [rbp+newString]
0x180033428  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18003342d  nop
0x18003342e  test    rdi, rdi
0x180033431  jz      short loc_180033443
0x180033433  mov     rax, [rdi]
0x180033436  mov     rcx, rdi
0x180033439  mov     rax, [rax+10h]
0x18003343d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033442  nop
0x180033443  jmp     short loc_1800334BC
0x180033445  mov     rcx, [rbp+string]; string
0x180033449  call    cs:__imp_WindowsDeleteString
0x180033450  nop     dword ptr [rax+rax+00h]
0x180033455  jmp     short loc_180033463
0x180033457  xor     edx, edx
0x180033459  lea     rcx, [rbp+newString]
0x18003345d  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x180033462  nop
0x180033463  lea     r8, [rbp+newString]
0x180033467  lea     rdx, [rbp+var_40]
0x18003346b  lea     rcx, [rbp+var_20]
0x18003346f  call    _lambda_b2bb3cc6b7b45741a3011b9c2260506d____lambda_b2bb3cc6b7b45741a3011b9c2260506d_
0x180033474  mov     [rbp+var_40], 3
0x18003347b  mov     qword ptr [rbp+var_40+4], 80h
0x180033483  mov     r9, rax
0x180033486  mov     rdx, rsi
0x180033489  lea     rcx, [rbp+var_40]
0x18003348d  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CHSTRINGResult_HSTRING_____Windows__Internal__ComTaskPoolHandler__lambda_b2bb3cc6b7b45741a3011b9c2260506d___
0x180033492  mov     ebx, eax
0x180033494  lea     rcx, [rbp+var_20]
0x180033498  call    _lambda_b2bb3cc6b7b45741a3011b9c2260506d_____lambda_b2bb3cc6b7b45741a3011b9c2260506d_
0x18003349d  lea     rcx, [rbp+newString]
0x1800334a1  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x1800334a6  nop
0x1800334a7  test    rdi, rdi
0x1800334aa  jz      short loc_1800334BC
0x1800334ac  mov     rcx, [rdi]
0x1800334af  mov     rax, [rcx+10h]
0x1800334b3  mov     rcx, rdi
0x1800334b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334bb  nop
0x1800334bc  mov     eax, ebx
0x1800334be  mov     rbx, [rsp+60h+arg_8]
0x1800334c6  add     rsp, 60h
0x1800334ca  pop     rdi
0x1800334cb  pop     rsi
0x1800334cc  pop     rbp
0x1800334cd  retn
```
