# CrossMachineCommunicationServices::RemoveNamedPipe(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180080f30`
- end: `0x18008101e`
- name: `?RemoveNamedPipe@CrossMachineCommunicationServices@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800067f8`
- `0x180031540`
- `0x180080f30`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180080f60`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180080f60`

## string_xrefs

- `0x180080f72`: `onecore\windows\accessibletech\common\crossmachinecommunicationservices.cpp`
- `0x180080fc7`: `onecore\windows\accessibletech\common\crossmachinecommunicationservices.cpp`
- `0x180080ff1`: `onecore\windows\accessibletech\common\crossmachinecommunicationservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CrossMachineCommunicationServices::RemoveNamedPipe(__int64 a1)
{
  HRESULT Instance; // eax
  __int64 v3; // rax
  int v4; // eax
  int ppv; // [rsp+20h] [rbp-38h]
  LPVOID v7[2]; // [rsp+30h] [rbp-28h] BYREF
  __int128 v8; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v10; // [rsp+78h] [rbp+20h] BYREF

  v7[0] = 0;
  Instance = CoCreateInstance(&CLSID_UiaManager, 0, 4u, &GUID_c0bc943b_c585_40b4_9764_105af9dc62fc, v7);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\crossmachinecommunicationservices.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  v10 = 0;
  v3 = *(_QWORD *)v7[0];
  v10 = 0;
  v8 = *(_OWORD *)(a1 + 8);
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int64 *))(v3 + 24))(v7[0], &v8, &v10);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\crossmachinecommunicationservices.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  if ( !v10 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\crossmachinecommunicationservices.cpp",
      (const char *)0x80004005LL,
      ppv);
  wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v10);
  return wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(v7);
}

```

## disassembly

```asm
0x180080f30  push    rbx
0x180080f32  sub     rsp, 50h
0x180080f36  mov     rbx, rcx
0x180080f39  mov     [rsp+58h+var_28], 0
0x180080f42  lea     rax, [rsp+58h+var_28]
0x180080f47  mov     qword ptr [rsp+58h+ppv], rax; int
0x180080f4c  lea     r9, _GUID_c0bc943b_c585_40b4_9764_105af9dc62fc; riid
0x180080f53  xor     edx, edx; pUnkOuter
0x180080f55  lea     r8d, [rdx+4]; dwClsContext
0x180080f59  lea     rcx, CLSID_UiaManager; rclsid
0x180080f60  call    cs:__imp_CoCreateInstance
0x180080f66  mov     rcx, [rsp+58h]; this
0x180080f6b  test    eax, eax
0x180080f6d  jns     short loc_180080F84
0x180080f6f  mov     r9d, eax; char *
0x180080f72  lea     r8, aOnecoreWindows_28; "onecore\\windows\\accessibletech\\commo"...
0x180080f79  mov     edx, 3Ch ; '<'; void *
0x180080f7e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080f84  mov     [rsp+58h+arg_18], 0
0x180080f8d  mov     rcx, [rsp+58h+var_28]
0x180080f92  mov     rax, [rcx]
0x180080f95  mov     [rsp+58h+arg_18], 0
0x180080f9e  movups  xmm0, xmmword ptr [rbx+8]
0x180080fa2  movdqu  [rsp+58h+var_18], xmm0
0x180080fa8  lea     r8, [rsp+58h+arg_18]
0x180080fad  lea     rdx, [rsp+58h+var_18]
0x180080fb2  mov     rax, [rax+18h]
0x180080fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080fbb  mov     rcx, [rsp+58h]; this
0x180080fc0  test    eax, eax
0x180080fc2  jns     short loc_180080FD9
0x180080fc4  mov     r9d, eax; char *
0x180080fc7  lea     r8, aOnecoreWindows_28; "onecore\\windows\\accessibletech\\commo"...
0x180080fce  mov     edx, 3Fh ; '?'; void *
0x180080fd3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080fd9  cmp     [rsp+58h+arg_18], 0
0x180080fdf  setz    al
0x180080fe2  mov     rcx, [rsp+58h]; this
0x180080fe7  test    al, al
0x180080fe9  jz      short loc_180081003
0x180080feb  mov     r9d, 80004005h; char *
0x180080ff1  lea     r8, aOnecoreWindows_28; "onecore\\windows\\accessibletech\\commo"...
0x180080ff8  mov     edx, 41h ; 'A'; void *
0x180080ffd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180081003  lea     rcx, [rsp+58h+arg_18]
0x180081008  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x18008100d  nop
0x18008100e  lea     rcx, [rsp+58h+var_28]
0x180081013  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x180081018  add     rsp, 50h
0x18008101c  pop     rbx
0x18008101d  retn
```
