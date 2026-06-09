# ContainerManagerApi::DelegatePipeUnmapToUiaManager(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18007ff8c`
- end: `0x18008005f`
- name: `?DelegatePipeUnmapToUiaManager@ContainerManagerApi@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180080300`

## callees

- `0x1800067f8`
- `0x180031540`
- `0x18007ff8c`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007ffc9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007ffc9`

## string_xrefs

- `0x18007ffdb`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`
- `0x180080033`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ContainerManagerApi::DelegatePipeUnmapToUiaManager(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  HRESULT Instance; // eax
  __int64 v7; // rax
  int v8; // eax
  int v10; // [rsp+20h] [rbp-28h]
  __int128 v11; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 *v13; // [rsp+68h] [rbp+20h] BYREF

  v13 = 0;
  Instance = CoCreateInstance(&CLSID_UiaManager, 0, 4u, &GUID_22bcd67a_1154_466f_972a_899e63847049, (LPVOID *)&v13);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp",
      (const char *)(unsigned int)Instance,
      v10);
  v7 = *v13;
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  v11 = *(_OWORD *)(a1 + 8);
  v8 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, _QWORD *, _QWORD *))(v7 + 48))(v13, &v11, a2, a3);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp",
      (const char *)(unsigned int)v8,
      v10);
  return wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v13);
}

```

## disassembly

```asm
0x18007ff8c  mov     r11, rsp
0x18007ff8f  mov     [r11+8], rbx
0x18007ff93  mov     [r11+10h], rsi
0x18007ff97  push    rdi
0x18007ff98  sub     rsp, 40h
0x18007ff9c  mov     rdi, r8
0x18007ff9f  mov     rbx, rdx
0x18007ffa2  mov     rsi, rcx
0x18007ffa5  mov     qword ptr [r11+20h], 0
0x18007ffad  lea     rax, [r11+20h]
0x18007ffb1  mov     [r11-28h], rax
0x18007ffb5  lea     r9, _GUID_22bcd67a_1154_466f_972a_899e63847049; riid
0x18007ffbc  xor     edx, edx; pUnkOuter
0x18007ffbe  lea     r8d, [rdx+4]; dwClsContext
0x18007ffc2  lea     rcx, CLSID_UiaManager; rclsid
0x18007ffc9  call    cs:__imp_CoCreateInstance
0x18007ffcf  mov     rcx, [rsp+48h]; this
0x18007ffd4  test    eax, eax
0x18007ffd6  jns     short loc_18007FFED
0x18007ffd8  mov     r9d, eax; char *
0x18007ffdb  lea     r8, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x18007ffe2  mov     edx, 0BFh; void *
0x18007ffe7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007ffed  mov     rcx, [rsp+48h+arg_18]
0x18007fff2  mov     rax, [rcx]
0x18007fff5  cmp     qword ptr [rdi+18h], 7
0x18007fffa  jbe     short loc_18007FFFF
0x18007fffc  mov     rdi, [rdi]
0x18007ffff  cmp     qword ptr [rbx+18h], 7
0x180080004  jbe     short loc_180080009
0x180080006  mov     rbx, [rbx]
0x180080009  movups  xmm0, xmmword ptr [rsi+8]
0x18008000d  movdqu  [rsp+48h+var_18], xmm0
0x180080013  mov     r9, rdi
0x180080016  mov     r8, rbx
0x180080019  lea     rdx, [rsp+48h+var_18]
0x18008001e  mov     rax, [rax+30h]
0x180080022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080027  mov     rcx, [rsp+48h]; this
0x18008002c  test    eax, eax
0x18008002e  jns     short loc_180080045
0x180080030  mov     r9d, eax; char *
0x180080033  lea     r8, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x18008003a  mov     edx, 0C4h; void *
0x18008003f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080045  lea     rcx, [rsp+48h+arg_18]
0x18008004a  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x18008004f  mov     rbx, [rsp+48h+arg_0]
0x180080054  mov     rsi, [rsp+48h+arg_8]
0x180080059  add     rsp, 40h
0x18008005d  pop     rdi
0x18008005e  retn
```
