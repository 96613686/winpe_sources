# wil::details::RaiseRoOriginateOnWilExceptions(wil::FailureInfo const &)

- ea: `0x18002c5c0`
- end: `0x18002c6d8`
- name: `?RaiseRoOriginateOnWilExceptions@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `280`
- prototype: `void __fastcall(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800169bc`
- `0x180029058`
- `0x180029638`
- `0x18002bcd8`
- `0x18002c5c0`
- `0x18002ca28`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002c697`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002c697`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18002c66f`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18002c66f`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18002c5e7`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18002c5e7`

## string_xrefs

- `0x18002c68e`: `api-ms-win-core-winrt-error-l1-1-1.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::RaiseRoOriginateOnWilExceptions(wil::details *this, const struct wil::FailureInfo *a2)
{
  bool v3; // di
  void (__fastcall *Proc)(_QWORD, _QWORD, _QWORD); // rax
  _QWORD v5[2]; // [rsp+30h] [rbp-10h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp+20h] BYREF
  __int64 v7; // [rsp+68h] [rbp+28h] BYREF
  __int64 v8; // [rsp+70h] [rbp+30h] BYREF
  __int64 v9; // [rsp+78h] [rbp+38h] BYREF

  v3 = 1;
  if ( *(_DWORD *)this <= 1u )
  {
    v7 = 0;
    if ( (unsigned int)GetRestrictedErrorInfo(&v7, a2) )
      goto LABEL_8;
    v5[0] = 0;
    LODWORD(phModule) = *((_DWORD *)this + 2);
    v9 = 0;
    v8 = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD *, HMODULE *, __int64 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
           v7,
           v5,
           &phModule,
           &v9,
           &v8) >= 0 )
      v3 = *((_DWORD *)this + 2) != (_DWORD)phModule;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v8);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v9);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v5);
    if ( v3 )
    {
LABEL_8:
      phModule = 0;
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
        &phModule,
        0);
      if ( GetModuleHandleExW(0, L"api-ms-win-core-winrt-error-l1-1-1.dll", &phModule) )
      {
        Proc = (void (__fastcall *)(_QWORD, _QWORD, _QWORD))wil::details::GetProcAddress<int (*)(long,unsigned int,unsigned short const *)>(phModule);
        if ( Proc )
          Proc(*((unsigned int *)this + 2), 0, *((_QWORD *)this + 3));
      }
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&phModule);
    }
    else if ( v7 )
    {
      SetRestrictedErrorInfo();
    }
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v7);
  }
}

```

## disassembly

```asm
0x18002c5c0  push    rbp
0x18002c5c2  push    rbx
0x18002c5c3  push    rdi
0x18002c5c4  mov     rbp, rsp
0x18002c5c7  sub     rsp, 40h
0x18002c5cb  mov     rbx, rcx
0x18002c5ce  mov     edi, 1
0x18002c5d3  cmp     [rcx], edi
0x18002c5d5  ja      loc_18002C6D0
0x18002c5db  mov     [rbp+arg_8], 0
0x18002c5e3  lea     rcx, [rbp+arg_8]
0x18002c5e7  call    cs:__imp_GetRestrictedErrorInfo
0x18002c5ed  test    eax, eax
0x18002c5ef  jnz     loc_18002C677
0x18002c5f5  mov     [rbp+var_10], 0
0x18002c5fd  mov     eax, [rbx+8]
0x18002c600  mov     dword ptr [rbp+phModule], eax
0x18002c603  mov     [rbp+arg_18], 0
0x18002c60b  mov     [rbp+arg_10], 0
0x18002c613  mov     rcx, [rbp+arg_8]
0x18002c617  mov     rax, [rcx]
0x18002c61a  lea     rdx, [rbp+arg_10]
0x18002c61e  mov     [rsp+40h+var_20], rdx
0x18002c623  lea     r9, [rbp+arg_18]
0x18002c627  lea     r8, [rbp+phModule]
0x18002c62b  lea     rdx, [rbp+var_10]
0x18002c62f  mov     rax, [rax+18h]
0x18002c633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c638  test    eax, eax
0x18002c63a  js      short loc_18002C646
0x18002c63c  mov     eax, dword ptr [rbp+phModule]
0x18002c63f  cmp     [rbx+8], eax
0x18002c642  setnz   dil
0x18002c646  lea     rcx, [rbp+arg_10]
0x18002c64a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c64f  lea     rcx, [rbp+arg_18]
0x18002c653  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c658  lea     rcx, [rbp+var_10]
0x18002c65c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c661  test    dil, dil
0x18002c664  jnz     short loc_18002C677
0x18002c666  mov     rcx, [rbp+arg_8]
0x18002c66a  test    rcx, rcx
0x18002c66d  jz      short loc_18002C6C6
0x18002c66f  call    cs:__imp_SetRestrictedErrorInfo
0x18002c675  jmp     short loc_18002C6C6
0x18002c677  mov     [rbp+phModule], 0
0x18002c67f  xor     edx, edx
0x18002c681  lea     rcx, [rbp+phModule]
0x18002c685  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18002c68a  lea     r8, [rbp+phModule]; phModule
0x18002c68e  lea     rdx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-error-l1-1-1.dll"
0x18002c695  xor     ecx, ecx; dwFlags
0x18002c697  call    cs:__imp_GetModuleHandleExW
0x18002c69d  test    eax, eax
0x18002c69f  jz      short loc_18002C6BD
0x18002c6a1  mov     rcx, [rbp+phModule]
0x18002c6a5  call    ??$GetProcAddress@P6AHJIPEBG@Z@details@wil@@YAP6AHJIPEBG@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<int (*)(long,uint,ushort const *)>(HINSTANCE__ *,char const *)
0x18002c6aa  test    rax, rax
0x18002c6ad  jz      short loc_18002C6BD
0x18002c6af  mov     r8, [rbx+18h]
0x18002c6b3  xor     edx, edx
0x18002c6b5  mov     ecx, [rbx+8]
0x18002c6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6bd  lea     rcx, [rbp+phModule]
0x18002c6c1  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002c6c6  lea     rcx, [rbp+arg_8]
0x18002c6ca  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18002c6cf  nop
0x18002c6d0  add     rsp, 40h
0x18002c6d4  pop     rdi
0x18002c6d5  pop     rbx
0x18002c6d6  pop     rbp
0x18002c6d7  retn
```
