# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::ShowMdmSyncStatusPageAsync(int,Windows::Foundation::IAsyncOperation<int> * *)

- ea: `0x1800349a0`
- end: `0x180034b47`
- name: `?ShowMdmSyncStatusPageAsync@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJHPEAPEAU?$IAsyncOperation@H@Foundation@Windows@@@Z`
- size: `423`
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
- `0x18001bdf0`
- `0x18001c920`
- `0x18001d25c`
- `0x180020d50`
- `0x1800349a0`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x1800349d6`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800349d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180034a68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180034a68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034a96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034ab0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034a96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034ab0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::ShowMdmSyncStatusPageAsync(
        __int64 a1,
        int a2,
        __int64 a3)
{
  int v5; // edx
  int ActiveUserSid; // eax
  unsigned int v7; // ebx
  __int64 v8; // rax
  HRESULT v9; // eax
  __int64 v10; // rax
  __int64 v11; // r8
  HLOCAL hMem; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v14[12]; // [rsp+28h] [rbp-48h] BYREF
  HSTRING *newString[2]; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v16[40]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  int v18; // [rsp+98h] [rbp+28h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+38h] BYREF

  v18 = a2;
  wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(newString);
  if ( v5 )
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
        (void *)0x3C4,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)ActiveUserSid,
        (int)hMem);
      goto LABEL_12;
    }
    string = 0;
    Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(&string, &hMem);
    LocalFree(hMem);
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(
      newString,
      0);
    if ( !(unsigned __int8)std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(newString) )
    {
      v8 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(v14);
      std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
        newString,
        v8);
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v14);
    }
    v9 = WindowsDuplicateString(string, newString[0]);
    v7 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C8,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)v9,
        (int)hMem);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_12;
    }
    WindowsDeleteString(string);
  }
  *(_QWORD *)v14 = a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(v14);
  v10 = lambda_33ff395ed5420dd35226ef3bdae57de6_::_lambda_33ff395ed5420dd35226ef3bdae57de6_(v16, v14, newString, &v18);
  *(_DWORD *)v14 = 3;
  *(_QWORD *)&v14[4] = 128;
  v7 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CBasicResult_int_0__int_Windows::Internal::ComTaskPoolHandler__lambda_33ff395ed5420dd35226ef3bdae57de6___(
         v14,
         a3,
         v11,
         v10);
  lambda_b2bb3cc6b7b45741a3011b9c2260506d_::__lambda_b2bb3cc6b7b45741a3011b9c2260506d_(v16);
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
LABEL_12:
  std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(newString);
  return v7;
}

```

## disassembly

```asm
0x1800349a0  mov     [rsp-18h+arg_0], rbx
0x1800349a5  mov     [rsp-18h+arg_8], edx
0x1800349a9  push    rbp
0x1800349aa  push    rsi
0x1800349ab  push    rdi
0x1800349ac  mov     rbp, rsp
0x1800349af  sub     rsp, 70h
0x1800349b3  mov     rsi, r8
0x1800349b6  mov     rdi, rcx
0x1800349b9  lea     rcx, [rbp+newString]
0x1800349bd  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x1800349c2  test    edx, edx
0x1800349c4  jnz     loc_180034ABE
0x1800349ca  mov     [rbp+hMem], 0
0x1800349d2  lea     rcx, [rbp+hMem]
0x1800349d6  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800349dd  nop     dword ptr [rax+rax+00h]
0x1800349e2  mov     ebx, eax
0x1800349e4  test    eax, eax
0x1800349e6  jns     short loc_180034A05
0x1800349e8  mov     rcx, [rbp+18h]; this
0x1800349ec  mov     r9d, eax; char *
0x1800349ef  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800349f6  mov     edx, 3C4h; void *
0x1800349fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034a00  jmp     loc_180034B2B
0x180034a05  mov     [rbp+string], 0
0x180034a0d  lea     rdx, [rbp+hMem]
0x180034a11  lea     rcx, [rbp+string]
0x180034a15  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x180034a1a  mov     rcx, [rbp+hMem]; hMem
0x180034a1e  call    cs:__imp_LocalFree
0x180034a25  nop     dword ptr [rax+rax+00h]
0x180034a2a  xor     edx, edx
0x180034a2c  lea     rcx, [rbp+newString]
0x180034a30  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x180034a35  lea     rcx, [rbp+newString]
0x180034a39  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x180034a3e  test    al, al
0x180034a40  jnz     short loc_180034A60
0x180034a42  lea     rcx, [rbp+var_48]
0x180034a46  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x180034a4b  mov     rdx, rax
0x180034a4e  lea     rcx, [rbp+newString]
0x180034a52  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x180034a57  lea     rcx, [rbp+var_48]
0x180034a5b  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x180034a60  mov     rdx, [rbp+newString]; newString
0x180034a64  mov     rcx, [rbp+string]; string
0x180034a68  call    cs:__imp_WindowsDuplicateString
0x180034a6f  nop     dword ptr [rax+rax+00h]
0x180034a74  mov     ebx, eax
0x180034a76  test    eax, eax
0x180034a78  jns     short loc_180034AAC
0x180034a7a  mov     rcx, [rbp+18h]; this
0x180034a7e  mov     r9d, eax; char *
0x180034a81  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180034a88  mov     edx, 3C8h; void *
0x180034a8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034a92  mov     rcx, [rbp+string]; string
0x180034a96  call    cs:__imp_WindowsDeleteString
0x180034a9d  nop     dword ptr [rax+rax+00h]
0x180034aa2  mov     [rbp+string], 0
0x180034aaa  jmp     short loc_180034B2B
0x180034aac  mov     rcx, [rbp+string]; string
0x180034ab0  call    cs:__imp_WindowsDeleteString
0x180034ab7  nop     dword ptr [rax+rax+00h]
0x180034abc  jmp     short loc_180034ACA
0x180034abe  xor     edx, edx
0x180034ac0  lea     rcx, [rbp+newString]
0x180034ac4  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x180034ac9  nop
0x180034aca  mov     [rbp+var_48], rdi
0x180034ace  lea     rcx, [rbp+var_48]
0x180034ad2  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180034ad7  lea     r9, [rbp+arg_8]
0x180034adb  lea     r8, [rbp+newString]
0x180034adf  lea     rdx, [rbp+var_48]
0x180034ae3  lea     rcx, [rbp+var_28]
0x180034ae7  call    _lambda_33ff395ed5420dd35226ef3bdae57de6____lambda_33ff395ed5420dd35226ef3bdae57de6_
0x180034aec  mov     dword ptr [rbp+var_48], 3
0x180034af3  mov     [rbp+var_48+4], 80h
0x180034afb  mov     r9, rax
0x180034afe  mov     rdx, rsi
0x180034b01  lea     rcx, [rbp+var_48]
0x180034b05  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CBasicResult_int_0__int_Windows__Internal__ComTaskPoolHandler__lambda_33ff395ed5420dd35226ef3bdae57de6___
0x180034b0a  mov     ebx, eax
0x180034b0c  lea     rcx, [rbp+var_28]
0x180034b10  call    _lambda_b2bb3cc6b7b45741a3011b9c2260506d_____lambda_b2bb3cc6b7b45741a3011b9c2260506d_
0x180034b15  nop
0x180034b16  test    rdi, rdi
0x180034b19  jz      short loc_180034B2B
0x180034b1b  mov     rcx, [rdi]
0x180034b1e  mov     rax, [rcx+10h]
0x180034b22  mov     rcx, rdi
0x180034b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b2a  nop
0x180034b2b  lea     rcx, [rbp+newString]
0x180034b2f  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x180034b34  mov     eax, ebx
0x180034b36  mov     rbx, [rsp+70h+arg_0]
0x180034b3e  add     rsp, 70h
0x180034b42  pop     rdi
0x180034b43  pop     rsi
0x180034b44  pop     rbp
0x180034b45  retn
```
