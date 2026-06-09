# CrossMachineCommunicationServices::AddNamedPipe(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x180080db0`
- end: `0x180080f21`
- name: `?AddNamedPipe@CrossMachineCommunicationServices@@UEAA?AW4AddNamedPipeResult@ICrossMachineCommunicationServices@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0K@Z`
- size: `369`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800067f8`
- `0x1800109bc`
- `0x180012484`
- `0x180031540`
- `0x180080db0`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180080dea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180080dea`

## string_xrefs

- `0x180080dfb`: `onecore\windows\accessibletech\common\crossmachinecommunicationservices.cpp`
- `0x180080e49`: `onecore\windows\accessibletech\common\crossmachinecommunicationservices.cpp`
- `0x180080e71`: `onecore\windows\accessibletech\common\crossmachinecommunicationservices.cpp`
- `0x180080ee7`: `onecore\windows\accessibletech\common\crossmachinecommunicationservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CrossMachineCommunicationServices::AddNamedPipe(__int64 a1, __int64 a2, _QWORD *a3, unsigned int a4)
{
  HRESULT v7; // eax
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  int ppv; // [rsp+20h] [rbp-48h]
  __int64 v13; // [rsp+30h] [rbp-38h] BYREF
  LPVOID v14; // [rsp+38h] [rbp-30h] BYREF
  _QWORD v15[2]; // [rsp+40h] [rbp-28h] BYREF
  __int128 v16; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  v14 = 0;
  v7 = CoCreateInstance(&CLSID_UiaManager, 0, 4u, &GUID_c0bc943b_c585_40b4_9764_105af9dc62fc, &v14);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\crossmachinecommunicationservices.cpp",
      (const char *)(unsigned int)v7,
      ppv);
  v13 = 0;
  v8 = *(_QWORD *)v14;
  v13 = 0;
  v16 = *(_OWORD *)(a1 + 8);
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int64 *))(v8 + 24))(v14, &v16, &v13);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\crossmachinecommunicationservices.cpp",
      (const char *)(unsigned int)v9,
      ppv);
  if ( !v13 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\crossmachinecommunicationservices.cpp",
      (const char *)0x80004005LL,
      ppv);
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  wil::make_bstr(v15, a3);
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v13 + 24LL))(v13, v15[0], a4);
  if ( v10 == -2147024713 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v15);
    wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v13);
    wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v14);
    return 1;
  }
  else
  {
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\crossmachinecommunicationservices.cpp",
        (const char *)(unsigned int)v10,
        ppv);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v15);
    wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v13);
    wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v14);
    return 0;
  }
}

```

## disassembly

```asm
0x180080db0  push    rbp
0x180080db2  push    rbx
0x180080db3  push    rsi
0x180080db4  push    rdi
0x180080db5  mov     rbp, rsp
0x180080db8  sub     rsp, 68h
0x180080dbc  mov     esi, r9d
0x180080dbf  mov     rbx, r8
0x180080dc2  mov     rdi, rcx
0x180080dc5  mov     [rbp+var_30], 0
0x180080dcd  lea     rax, [rbp+var_30]
0x180080dd1  mov     qword ptr [rsp+68h+ppv], rax; int
0x180080dd6  lea     r9, _GUID_c0bc943b_c585_40b4_9764_105af9dc62fc; riid
0x180080ddd  xor     edx, edx; pUnkOuter
0x180080ddf  lea     r8d, [rdx+4]; dwClsContext
0x180080de3  lea     rcx, CLSID_UiaManager; rclsid
0x180080dea  call    cs:__imp_CoCreateInstance
0x180080df0  mov     rcx, [rbp+20h]; this
0x180080df4  test    eax, eax
0x180080df6  jns     short loc_180080E0D
0x180080df8  mov     r9d, eax; char *
0x180080dfb  lea     r8, aOnecoreWindows_28; "onecore\\windows\\accessibletech\\commo"...
0x180080e02  mov     edx, 1Ah; void *
0x180080e07  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080e0d  mov     [rbp+var_38], 0
0x180080e15  mov     rcx, [rbp+var_30]
0x180080e19  mov     rax, [rcx]
0x180080e1c  mov     [rbp+var_38], 0
0x180080e24  movups  xmm0, xmmword ptr [rdi+8]
0x180080e28  movdqu  [rbp+var_18], xmm0
0x180080e2d  lea     r8, [rbp+var_38]
0x180080e31  lea     rdx, [rbp+var_18]
0x180080e35  mov     rax, [rax+18h]
0x180080e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080e3e  mov     rcx, [rbp+20h]; this
0x180080e42  test    eax, eax
0x180080e44  jns     short loc_180080E5B
0x180080e46  mov     r9d, eax; char *
0x180080e49  lea     r8, aOnecoreWindows_28; "onecore\\windows\\accessibletech\\commo"...
0x180080e50  mov     edx, 1Dh; void *
0x180080e55  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080e5b  cmp     [rbp+var_38], 0
0x180080e60  setz    al
0x180080e63  mov     rcx, [rbp+20h]; this
0x180080e67  test    al, al
0x180080e69  jz      short loc_180080E83
0x180080e6b  mov     r9d, 80004005h; char *
0x180080e71  lea     r8, aOnecoreWindows_28; "onecore\\windows\\accessibletech\\commo"...
0x180080e78  mov     edx, 1Fh; void *
0x180080e7d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080e83  cmp     qword ptr [rbx+18h], 7
0x180080e88  jbe     short loc_180080E8D
0x180080e8a  mov     rbx, [rbx]
0x180080e8d  mov     rdx, rbx
0x180080e90  lea     rcx, [rbp+var_28]
0x180080e94  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180080e99  nop
0x180080e9a  mov     rcx, [rbp+var_38]
0x180080e9e  mov     rax, [rcx]
0x180080ea1  mov     r8d, esi
0x180080ea4  mov     rdx, [rbp+var_28]
0x180080ea8  mov     rax, [rax+18h]
0x180080eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080eb1  cmp     eax, 800700B7h
0x180080eb6  jnz     short loc_180080EDC
0x180080eb8  lea     rcx, [rbp+var_28]
0x180080ebc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180080ec1  nop
0x180080ec2  lea     rcx, [rbp+var_38]
0x180080ec6  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x180080ecb  nop
0x180080ecc  lea     rcx, [rbp+var_30]
0x180080ed0  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x180080ed5  mov     eax, 1
0x180080eda  jmp     short loc_180080F18
0x180080edc  mov     rcx, [rbp+20h]; this
0x180080ee0  test    eax, eax
0x180080ee2  jns     short loc_180080EF9
0x180080ee4  mov     r9d, eax; char *
0x180080ee7  lea     r8, aOnecoreWindows_28; "onecore\\windows\\accessibletech\\commo"...
0x180080eee  mov     edx, 2Ah ; '*'; void *
0x180080ef3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080ef9  lea     rcx, [rbp+var_28]
0x180080efd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180080f02  nop
0x180080f03  lea     rcx, [rbp+var_38]
0x180080f07  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x180080f0c  nop
0x180080f0d  lea     rcx, [rbp+var_30]
0x180080f11  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x180080f16  xor     eax, eax
0x180080f18  add     rsp, 68h
0x180080f1c  pop     rdi
0x180080f1d  pop     rsi
0x180080f1e  pop     rbx
0x180080f1f  pop     rbp
0x180080f20  retn
```
