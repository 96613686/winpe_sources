# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::ShouldShowCollectLogsAsync(int,Windows::Foundation::IAsyncOperation<int> * *)

- ea: `0x1800347b0`
- end: `0x18003498f`
- name: `?ShouldShowCollectLogsAsync@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJHPEAPEAU?$IAsyncOperation@H@Foundation@Windows@@@Z`
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
- `0x18001beb8`
- `0x18001c920`
- `0x18001d6d0`
- `0x180020d50`
- `0x1800347b0`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x1800347f1`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800347f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800348a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800348a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800348d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034909`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800348d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180034909`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034858`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034858`

## pseudocode

```c
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
0x1800347b0  mov     [rsp-18h+arg_8], rbx
0x1800347b5  push    rbp
0x1800347b6  push    rsi
0x1800347b7  push    rdi
0x1800347b8  mov     rbp, rsp
0x1800347bb  sub     rsp, 60h
0x1800347bf  mov     rsi, r8
0x1800347c2  mov     ebx, edx
0x1800347c4  mov     rdi, rcx
0x1800347c7  mov     qword ptr [rbp+var_40], rcx
0x1800347cb  lea     rcx, [rbp+var_40]
0x1800347cf  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x1800347d4  lea     rcx, [rbp+newString]
0x1800347d8  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x1800347dd  test    ebx, ebx
0x1800347df  jnz     loc_180034917
0x1800347e5  mov     [rbp+hMem], 0
0x1800347ed  lea     rcx, [rbp+hMem]
0x1800347f1  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800347f8  nop     dword ptr [rax+rax+00h]
0x1800347fd  mov     ebx, eax
0x1800347ff  test    eax, eax
0x180034801  jns     short loc_18003483F
0x180034803  mov     rcx, [rbp+18h]; this
0x180034807  mov     r9d, eax; char *
0x18003480a  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180034811  mov     edx, 6A8h; void *
0x180034816  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003481b  lea     rcx, [rbp+newString]
0x18003481f  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x180034824  nop
0x180034825  test    rdi, rdi
0x180034828  jz      short loc_18003483A
0x18003482a  mov     rax, [rdi]
0x18003482d  mov     rcx, rdi
0x180034830  mov     rax, [rax+10h]
0x180034834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034839  nop
0x18003483a  jmp     loc_18003497C
0x18003483f  mov     [rbp+string], 0
0x180034847  lea     rdx, [rbp+hMem]
0x18003484b  lea     rcx, [rbp+string]
0x18003484f  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x180034854  mov     rcx, [rbp+hMem]; hMem
0x180034858  call    cs:__imp_LocalFree
0x18003485f  nop     dword ptr [rax+rax+00h]
0x180034864  xor     edx, edx
0x180034866  lea     rcx, [rbp+newString]
0x18003486a  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18003486f  lea     rcx, [rbp+newString]
0x180034873  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x180034878  test    al, al
0x18003487a  jnz     short loc_18003489A
0x18003487c  lea     rcx, [rbp+var_20]
0x180034880  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x180034885  mov     rdx, rax
0x180034888  lea     rcx, [rbp+newString]
0x18003488c  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x180034891  lea     rcx, [rbp+var_20]
0x180034895  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18003489a  mov     rdx, [rbp+newString]; newString
0x18003489e  mov     rcx, [rbp+string]; string
0x1800348a2  call    cs:__imp_WindowsDuplicateString
0x1800348a9  nop     dword ptr [rax+rax+00h]
0x1800348ae  mov     ebx, eax
0x1800348b0  test    eax, eax
0x1800348b2  jns     short loc_180034905
0x1800348b4  mov     rcx, [rbp+18h]; this
0x1800348b8  mov     r9d, eax; char *
0x1800348bb  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800348c2  mov     edx, 6ACh; void *
0x1800348c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800348cc  mov     rcx, [rbp+string]; string
0x1800348d0  call    cs:__imp_WindowsDeleteString
0x1800348d7  nop     dword ptr [rax+rax+00h]
0x1800348dc  mov     [rbp+string], 0
0x1800348e4  lea     rcx, [rbp+newString]
0x1800348e8  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x1800348ed  nop
0x1800348ee  test    rdi, rdi
0x1800348f1  jz      short loc_180034903
0x1800348f3  mov     rax, [rdi]
0x1800348f6  mov     rcx, rdi
0x1800348f9  mov     rax, [rax+10h]
0x1800348fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034902  nop
0x180034903  jmp     short loc_18003497C
0x180034905  mov     rcx, [rbp+string]; string
0x180034909  call    cs:__imp_WindowsDeleteString
0x180034910  nop     dword ptr [rax+rax+00h]
0x180034915  jmp     short loc_180034923
0x180034917  xor     edx, edx
0x180034919  lea     rcx, [rbp+newString]
0x18003491d  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x180034922  nop
0x180034923  lea     r8, [rbp+newString]
0x180034927  lea     rdx, [rbp+var_40]
0x18003492b  lea     rcx, [rbp+var_20]
0x18003492f  call    _lambda_b2bb3cc6b7b45741a3011b9c2260506d____lambda_b2bb3cc6b7b45741a3011b9c2260506d_
0x180034934  mov     [rbp+var_40], 3
0x18003493b  mov     qword ptr [rbp+var_40+4], 80h
0x180034943  mov     r9, rax
0x180034946  mov     rdx, rsi
0x180034949  lea     rcx, [rbp+var_40]
0x18003494d  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CBasicResult_int_0__int_Windows__Internal__ComTaskPoolHandler__lambda_abfd5f1fa9c0a2da91cfb49309b4ea19___
0x180034952  mov     ebx, eax
0x180034954  lea     rcx, [rbp+var_20]
0x180034958  call    _lambda_b2bb3cc6b7b45741a3011b9c2260506d_____lambda_b2bb3cc6b7b45741a3011b9c2260506d_
0x18003495d  lea     rcx, [rbp+newString]
0x180034961  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x180034966  nop
0x180034967  test    rdi, rdi
0x18003496a  jz      short loc_18003497C
0x18003496c  mov     rcx, [rdi]
0x18003496f  mov     rax, [rcx+10h]
0x180034973  mov     rcx, rdi
0x180034976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003497b  nop
0x18003497c  mov     eax, ebx
0x18003497e  mov     rbx, [rsp+60h+arg_8]
0x180034986  add     rsp, 60h
0x18003498a  pop     rdi
0x18003498b  pop     rsi
0x18003498c  pop     rbp
0x18003498d  retn
```
