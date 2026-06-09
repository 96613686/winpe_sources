# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::RetrieveCustomErrorText(int,Windows::Foundation::IAsyncOperation<HSTRING__ *> * *)

- ea: `0x180034280`
- end: `0x180034440`
- name: `?RetrieveCustomErrorText@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJHPEAPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@Z`
- size: `448`
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
- `0x18001dca8`
- `0x18001e414`
- `0x18001f194`
- `0x180022700`
- `0x180034280`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x1800342c1`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800342c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180034366`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180034366`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003438e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800343c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003438e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800343c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034322`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034322`

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
  _QWORD *v8; // rax
  HRESULT v9; // eax
  __int64 v10; // rax
  __int64 v11; // r8
  int v13[4]; // [rsp+20h] [rbp-40h] BYREF
  __int128 newString; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v15[4]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HSTRING string; // [rsp+80h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp+38h] BYREF

  *(_QWORD *)v13 = a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(v13);
  wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(&newString);
  if ( a2 )
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
        (void *)0x706,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)ActiveUserSid,
        v13[0]);
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(&newString);
      if ( a1 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
      return v7;
    }
    string = 0;
    Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(&string, &hMem);
    LocalFree(hMem);
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(
      &newString,
      0);
    if ( !(unsigned __int8)std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(&newString) )
    {
      v8 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(v15);
      std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
        &newString,
        v8);
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v15);
    }
    v9 = WindowsDuplicateString(string, (HSTRING *)newString);
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
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(&newString);
      if ( a1 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
      return v7;
    }
    WindowsDeleteString(string);
  }
  v10 = lambda_b2bb3cc6b7b45741a3011b9c2260506d_::_lambda_b2bb3cc6b7b45741a3011b9c2260506d_(v15, v13, &newString);
  v13[0] = 3;
  *(_QWORD *)&v13[1] = 128;
  v7 = ((__int64 (__fastcall *)(int *, __int64, __int64, __int64))Windows::Internal::MakeAsyncOperation_Windows::Internal::CHSTRINGResult_HSTRING_____Windows::Internal::ComTaskPoolHandler__lambda_b2bb3cc6b7b45741a3011b9c2260506d___)(
         v13,
         a3,
         v11,
         v10);
  lambda_b2bb3cc6b7b45741a3011b9c2260506d_::__lambda_b2bb3cc6b7b45741a3011b9c2260506d_(v15);
  std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(&newString);
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return v7;
}

```

## disassembly

```asm
0x180034280  mov     [rsp-18h+arg_8], rbx
0x180034285  push    rbp
0x180034286  push    rsi
0x180034287  push    rdi
0x180034288  mov     rbp, rsp
0x18003428b  sub     rsp, 60h
0x18003428f  mov     rsi, r8
0x180034292  mov     ebx, edx
0x180034294  mov     rdi, rcx
0x180034297  mov     qword ptr [rbp+var_40], rcx
0x18003429b  lea     rcx, [rbp+var_40]
0x18003429f  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x1800342a4  lea     rcx, [rbp+newString]
0x1800342a8  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x1800342ad  test    ebx, ebx
0x1800342af  jnz     loc_1800343C9
0x1800342b5  mov     [rbp+hMem], 0
0x1800342bd  lea     rcx, [rbp+hMem]
0x1800342c1  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800342c7  mov     ebx, eax
0x1800342c9  test    eax, eax
0x1800342cb  jns     short loc_180034309
0x1800342cd  mov     rcx, [rbp+18h]; this
0x1800342d1  mov     r9d, eax; char *
0x1800342d4  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800342db  mov     edx, 706h; void *
0x1800342e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800342e5  lea     rcx, [rbp+newString]
0x1800342e9  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x1800342ee  nop
0x1800342ef  test    rdi, rdi
0x1800342f2  jz      short loc_180034304
0x1800342f4  mov     rax, [rdi]
0x1800342f7  mov     rcx, rdi
0x1800342fa  mov     rax, [rax+10h]
0x1800342fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034303  nop
0x180034304  jmp     loc_18003442E
0x180034309  mov     [rbp+string], 0
0x180034311  lea     rdx, [rbp+hMem]
0x180034315  lea     rcx, [rbp+string]
0x180034319  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x18003431e  mov     rcx, [rbp+hMem]; hMem
0x180034322  call    cs:__imp_LocalFree
0x180034328  xor     edx, edx
0x18003432a  lea     rcx, [rbp+newString]
0x18003432e  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x180034333  lea     rcx, [rbp+newString]
0x180034337  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18003433c  test    al, al
0x18003433e  jnz     short loc_18003435E
0x180034340  lea     rcx, [rbp+var_20]
0x180034344  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x180034349  mov     rdx, rax
0x18003434c  lea     rcx, [rbp+newString]
0x180034350  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x180034355  lea     rcx, [rbp+var_20]
0x180034359  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18003435e  mov     rdx, qword ptr [rbp+newString]; newString
0x180034362  mov     rcx, [rbp+string]; string
0x180034366  call    cs:__imp_WindowsDuplicateString
0x18003436c  mov     ebx, eax
0x18003436e  test    eax, eax
0x180034370  jns     short loc_1800343BD
0x180034372  mov     rcx, [rbp+18h]; this
0x180034376  mov     r9d, eax; char *
0x180034379  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180034380  mov     edx, 70Ah; void *
0x180034385  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003438a  mov     rcx, [rbp+string]; string
0x18003438e  call    cs:__imp_WindowsDeleteString
0x180034394  mov     [rbp+string], 0
0x18003439c  lea     rcx, [rbp+newString]
0x1800343a0  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x1800343a5  nop
0x1800343a6  test    rdi, rdi
0x1800343a9  jz      short loc_1800343BB
0x1800343ab  mov     rax, [rdi]
0x1800343ae  mov     rcx, rdi
0x1800343b1  mov     rax, [rax+10h]
0x1800343b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343ba  nop
0x1800343bb  jmp     short loc_18003442E
0x1800343bd  mov     rcx, [rbp+string]; string
0x1800343c1  call    cs:__imp_WindowsDeleteString
0x1800343c7  jmp     short loc_1800343D5
0x1800343c9  xor     edx, edx
0x1800343cb  lea     rcx, [rbp+newString]
0x1800343cf  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x1800343d4  nop
0x1800343d5  lea     r8, [rbp+newString]
0x1800343d9  lea     rdx, [rbp+var_40]
0x1800343dd  lea     rcx, [rbp+var_20]
0x1800343e1  call    _lambda_b2bb3cc6b7b45741a3011b9c2260506d____lambda_b2bb3cc6b7b45741a3011b9c2260506d_
0x1800343e6  mov     [rbp+var_40], 3
0x1800343ed  mov     qword ptr [rbp+var_40+4], 80h
0x1800343f5  mov     r9, rax
0x1800343f8  mov     rdx, rsi
0x1800343fb  lea     rcx, [rbp+var_40]
0x1800343ff  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CHSTRINGResult_HSTRING_____Windows__Internal__ComTaskPoolHandler__lambda_b2bb3cc6b7b45741a3011b9c2260506d___
0x180034404  mov     ebx, eax
0x180034406  lea     rcx, [rbp+var_20]
0x18003440a  call    _lambda_b2bb3cc6b7b45741a3011b9c2260506d_____lambda_b2bb3cc6b7b45741a3011b9c2260506d_
0x18003440f  lea     rcx, [rbp+newString]
0x180034413  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x180034418  nop
0x180034419  test    rdi, rdi
0x18003441c  jz      short loc_18003442E
0x18003441e  mov     rcx, [rdi]
0x180034421  mov     rax, [rcx+10h]
0x180034425  mov     rcx, rdi
0x180034428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003442d  nop
0x18003442e  mov     eax, ebx
0x180034430  mov     rbx, [rsp+60h+arg_8]
0x180034438  add     rsp, 60h
0x18003443c  pop     rdi
0x18003443d  pop     rsi
0x18003443e  pop     rbp
0x18003443f  retn
```
