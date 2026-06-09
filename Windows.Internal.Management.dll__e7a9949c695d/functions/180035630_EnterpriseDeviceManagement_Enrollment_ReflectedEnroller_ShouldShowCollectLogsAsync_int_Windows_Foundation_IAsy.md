# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::ShouldShowCollectLogsAsync(int,Windows::Foundation::IAsyncOperation<int> * *)

- ea: `0x180035630`
- end: `0x1800357f0`
- name: `?ShouldShowCollectLogsAsync@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJHPEAPEAU?$IAsyncOperation@H@Foundation@Windows@@@Z`
- size: `448`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
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
- `0x18001d9cc`
- `0x18001e414`
- `0x18001f194`
- `0x180022700`
- `0x180035630`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x180035671`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180035671`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180035716`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180035716`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003573e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035771`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003573e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035771`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800356d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800356d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::ShouldShowCollectLogsAsync(
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
        (void *)0x6A8,
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
        (void *)0x6AC,
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
  v7 = ((__int64 (__fastcall *)(int *, __int64, __int64, __int64))Windows::Internal::MakeAsyncOperation_Windows::Internal::CBasicResult_int_0__int_Windows::Internal::ComTaskPoolHandler__lambda_abfd5f1fa9c0a2da91cfb49309b4ea19___)(
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
0x180035630  mov     [rsp-18h+arg_8], rbx
0x180035635  push    rbp
0x180035636  push    rsi
0x180035637  push    rdi
0x180035638  mov     rbp, rsp
0x18003563b  sub     rsp, 60h
0x18003563f  mov     rsi, r8
0x180035642  mov     ebx, edx
0x180035644  mov     rdi, rcx
0x180035647  mov     qword ptr [rbp+var_40], rcx
0x18003564b  lea     rcx, [rbp+var_40]
0x18003564f  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180035654  lea     rcx, [rbp+newString]
0x180035658  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18003565d  test    ebx, ebx
0x18003565f  jnz     loc_180035779
0x180035665  mov     [rbp+hMem], 0
0x18003566d  lea     rcx, [rbp+hMem]
0x180035671  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180035677  mov     ebx, eax
0x180035679  test    eax, eax
0x18003567b  jns     short loc_1800356B9
0x18003567d  mov     rcx, [rbp+18h]; this
0x180035681  mov     r9d, eax; char *
0x180035684  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003568b  mov     edx, 6A8h; void *
0x180035690  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035695  lea     rcx, [rbp+newString]
0x180035699  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18003569e  nop
0x18003569f  test    rdi, rdi
0x1800356a2  jz      short loc_1800356B4
0x1800356a4  mov     rax, [rdi]
0x1800356a7  mov     rcx, rdi
0x1800356aa  mov     rax, [rax+10h]
0x1800356ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800356b3  nop
0x1800356b4  jmp     loc_1800357DE
0x1800356b9  mov     [rbp+string], 0
0x1800356c1  lea     rdx, [rbp+hMem]
0x1800356c5  lea     rcx, [rbp+string]
0x1800356c9  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x1800356ce  mov     rcx, [rbp+hMem]; hMem
0x1800356d2  call    cs:__imp_LocalFree
0x1800356d8  xor     edx, edx
0x1800356da  lea     rcx, [rbp+newString]
0x1800356de  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x1800356e3  lea     rcx, [rbp+newString]
0x1800356e7  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x1800356ec  test    al, al
0x1800356ee  jnz     short loc_18003570E
0x1800356f0  lea     rcx, [rbp+var_20]
0x1800356f4  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x1800356f9  mov     rdx, rax
0x1800356fc  lea     rcx, [rbp+newString]
0x180035700  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x180035705  lea     rcx, [rbp+var_20]
0x180035709  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18003570e  mov     rdx, [rbp+newString]; newString
0x180035712  mov     rcx, [rbp+string]; string
0x180035716  call    cs:__imp_WindowsDuplicateString
0x18003571c  mov     ebx, eax
0x18003571e  test    eax, eax
0x180035720  jns     short loc_18003576D
0x180035722  mov     rcx, [rbp+18h]; this
0x180035726  mov     r9d, eax; char *
0x180035729  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180035730  mov     edx, 6ACh; void *
0x180035735  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003573a  mov     rcx, [rbp+string]; string
0x18003573e  call    cs:__imp_WindowsDeleteString
0x180035744  mov     [rbp+string], 0
0x18003574c  lea     rcx, [rbp+newString]
0x180035750  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x180035755  nop
0x180035756  test    rdi, rdi
0x180035759  jz      short loc_18003576B
0x18003575b  mov     rax, [rdi]
0x18003575e  mov     rcx, rdi
0x180035761  mov     rax, [rax+10h]
0x180035765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003576a  nop
0x18003576b  jmp     short loc_1800357DE
0x18003576d  mov     rcx, [rbp+string]; string
0x180035771  call    cs:__imp_WindowsDeleteString
0x180035777  jmp     short loc_180035785
0x180035779  xor     edx, edx
0x18003577b  lea     rcx, [rbp+newString]
0x18003577f  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x180035784  nop
0x180035785  lea     r8, [rbp+newString]
0x180035789  lea     rdx, [rbp+var_40]
0x18003578d  lea     rcx, [rbp+var_20]
0x180035791  call    _lambda_b2bb3cc6b7b45741a3011b9c2260506d____lambda_b2bb3cc6b7b45741a3011b9c2260506d_
0x180035796  mov     [rbp+var_40], 3
0x18003579d  mov     qword ptr [rbp+var_40+4], 80h
0x1800357a5  mov     r9, rax
0x1800357a8  mov     rdx, rsi
0x1800357ab  lea     rcx, [rbp+var_40]
0x1800357af  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CBasicResult_int_0__int_Windows__Internal__ComTaskPoolHandler__lambda_abfd5f1fa9c0a2da91cfb49309b4ea19___
0x1800357b4  mov     ebx, eax
0x1800357b6  lea     rcx, [rbp+var_20]
0x1800357ba  call    _lambda_b2bb3cc6b7b45741a3011b9c2260506d_____lambda_b2bb3cc6b7b45741a3011b9c2260506d_
0x1800357bf  lea     rcx, [rbp+newString]
0x1800357c3  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x1800357c8  nop
0x1800357c9  test    rdi, rdi
0x1800357cc  jz      short loc_1800357DE
0x1800357ce  mov     rcx, [rdi]
0x1800357d1  mov     rax, [rcx+10h]
0x1800357d5  mov     rcx, rdi
0x1800357d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357dd  nop
0x1800357de  mov     eax, ebx
0x1800357e0  mov     rbx, [rsp+60h+arg_8]
0x1800357e8  add     rsp, 60h
0x1800357ec  pop     rdi
0x1800357ed  pop     rsi
0x1800357ee  pop     rbp
0x1800357ef  retn
```
