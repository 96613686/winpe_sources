# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::ShowMdmSyncStatusPageAsync(int,Windows::Foundation::IAsyncOperation<int> * *)

- ea: `0x180035800`
- end: `0x180035988`
- name: `?ShowMdmSyncStatusPageAsync@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJHPEAPEAU?$IAsyncOperation@H@Foundation@Windows@@@Z`
- size: `392`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a2a4`
- `0x180016b54`
- `0x180017074`
- `0x18001736c`
- `0x1800173ec`
- `0x180018ff0`
- `0x180019b2c`
- `0x180019f1c`
- `0x18001d904`
- `0x18001e414`
- `0x18001ed24`
- `0x180022700`
- `0x180035800`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x180035836`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180035836`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800358bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800358bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800358e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800358f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800358e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800358f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035878`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035878`

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
  _QWORD *v8; // rax
  HRESULT v9; // eax
  __int64 v10; // rax
  __int64 v11; // r8
  HLOCAL hMem; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v14[12]; // [rsp+28h] [rbp-48h] BYREF
  __int128 newString; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v16[40]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  int v18; // [rsp+98h] [rbp+28h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+38h] BYREF

  v18 = a2;
  wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(&newString);
  if ( v5 )
  {
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(
      &newString,
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
      &newString,
      0);
    if ( !(unsigned __int8)std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(&newString) )
    {
      v8 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(v14);
      std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
        &newString,
        v8);
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v14);
    }
    v9 = WindowsDuplicateString(string, (HSTRING *)newString);
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
  v10 = lambda_33ff395ed5420dd35226ef3bdae57de6_::_lambda_33ff395ed5420dd35226ef3bdae57de6_(v16, v14, &newString, &v18);
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
  std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(&newString);
  return v7;
}

```

## disassembly

```asm
0x180035800  mov     [rsp-18h+arg_0], rbx
0x180035805  mov     [rsp-18h+arg_8], edx
0x180035809  push    rbp
0x18003580a  push    rsi
0x18003580b  push    rdi
0x18003580c  mov     rbp, rsp
0x18003580f  sub     rsp, 70h
0x180035813  mov     rsi, r8
0x180035816  mov     rdi, rcx
0x180035819  lea     rcx, [rbp+newString]
0x18003581d  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x180035822  test    edx, edx
0x180035824  jnz     loc_180035900
0x18003582a  mov     [rbp+hMem], 0
0x180035832  lea     rcx, [rbp+hMem]
0x180035836  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18003583c  mov     ebx, eax
0x18003583e  test    eax, eax
0x180035840  jns     short loc_18003585F
0x180035842  mov     rcx, [rbp+18h]; this
0x180035846  mov     r9d, eax; char *
0x180035849  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180035850  mov     edx, 3C4h; void *
0x180035855  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003585a  jmp     loc_18003596D
0x18003585f  mov     [rbp+string], 0
0x180035867  lea     rdx, [rbp+hMem]
0x18003586b  lea     rcx, [rbp+string]
0x18003586f  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x180035874  mov     rcx, [rbp+hMem]; hMem
0x180035878  call    cs:__imp_LocalFree
0x18003587e  xor     edx, edx
0x180035880  lea     rcx, [rbp+newString]
0x180035884  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x180035889  lea     rcx, [rbp+newString]
0x18003588d  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x180035892  test    al, al
0x180035894  jnz     short loc_1800358B4
0x180035896  lea     rcx, [rbp+var_48]
0x18003589a  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x18003589f  mov     rdx, rax
0x1800358a2  lea     rcx, [rbp+newString]
0x1800358a6  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x1800358ab  lea     rcx, [rbp+var_48]
0x1800358af  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x1800358b4  mov     rdx, qword ptr [rbp+newString]; newString
0x1800358b8  mov     rcx, [rbp+string]; string
0x1800358bc  call    cs:__imp_WindowsDuplicateString
0x1800358c2  mov     ebx, eax
0x1800358c4  test    eax, eax
0x1800358c6  jns     short loc_1800358F4
0x1800358c8  mov     rcx, [rbp+18h]; this
0x1800358cc  mov     r9d, eax; char *
0x1800358cf  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800358d6  mov     edx, 3C8h; void *
0x1800358db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800358e0  mov     rcx, [rbp+string]; string
0x1800358e4  call    cs:__imp_WindowsDeleteString
0x1800358ea  mov     [rbp+string], 0
0x1800358f2  jmp     short loc_18003596D
0x1800358f4  mov     rcx, [rbp+string]; string
0x1800358f8  call    cs:__imp_WindowsDeleteString
0x1800358fe  jmp     short loc_18003590C
0x180035900  xor     edx, edx
0x180035902  lea     rcx, [rbp+newString]
0x180035906  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18003590b  nop
0x18003590c  mov     [rbp+var_48], rdi
0x180035910  lea     rcx, [rbp+var_48]
0x180035914  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180035919  lea     r9, [rbp+arg_8]
0x18003591d  lea     r8, [rbp+newString]
0x180035921  lea     rdx, [rbp+var_48]
0x180035925  lea     rcx, [rbp+var_28]
0x180035929  call    _lambda_33ff395ed5420dd35226ef3bdae57de6____lambda_33ff395ed5420dd35226ef3bdae57de6_
0x18003592e  mov     dword ptr [rbp+var_48], 3
0x180035935  mov     [rbp+var_48+4], 80h
0x18003593d  mov     r9, rax
0x180035940  mov     rdx, rsi
0x180035943  lea     rcx, [rbp+var_48]
0x180035947  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CBasicResult_int_0__int_Windows__Internal__ComTaskPoolHandler__lambda_33ff395ed5420dd35226ef3bdae57de6___
0x18003594c  mov     ebx, eax
0x18003594e  lea     rcx, [rbp+var_28]
0x180035952  call    _lambda_b2bb3cc6b7b45741a3011b9c2260506d_____lambda_b2bb3cc6b7b45741a3011b9c2260506d_
0x180035957  nop
0x180035958  test    rdi, rdi
0x18003595b  jz      short loc_18003596D
0x18003595d  mov     rcx, [rdi]
0x180035960  mov     rax, [rcx+10h]
0x180035964  mov     rcx, rdi
0x180035967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003596c  nop
0x18003596d  lea     rcx, [rbp+newString]
0x180035971  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x180035976  mov     eax, ebx
0x180035978  mov     rbx, [rsp+70h+arg_0]
0x180035980  add     rsp, 70h
0x180035984  pop     rdi
0x180035985  pop     rsi
0x180035986  pop     rbp
0x180035987  retn
```
