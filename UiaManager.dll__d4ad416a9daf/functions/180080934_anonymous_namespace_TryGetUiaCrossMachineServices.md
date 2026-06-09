# _anonymous_namespace_::TryGetUiaCrossMachineServices

- ea: `0x180080934`
- end: `0x180080a20`
- name: `_anonymous_namespace_::TryGetUiaCrossMachineServices`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003a54c`

## callees

- `0x1800067f8`
- `0x180031540`
- `0x180080934`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008096e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008096e`

## string_xrefs

- `0x180080980`: `onecore\windows\accessibletech\common\basicutils.cpp`
- `0x1800809d3`: `onecore\windows\accessibletech\common\basicutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall anonymous_namespace_::TryGetUiaCrossMachineServices(_QWORD *a1, __int128 *a2)
{
  HRESULT Instance; // eax
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rax
  const char *v8; // r9
  _QWORD *result; // rax
  int v10; // [rsp+20h] [rbp-38h]
  __int128 v11; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v15; // [rsp+70h] [rbp+18h] BYREF
  __int64 *v16; // [rsp+78h] [rbp+20h] BYREF

  v16 = 0;
  Instance = CoCreateInstance(&CLSID_UiaManager, 0, 4u, &GUID_c0bc943b_c585_40b4_9764_105af9dc62fc, (LPVOID *)&v16);
  try
  {
    if ( Instance < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\basicutils.cpp",
        (const char *)(unsigned int)Instance,
        v10);
    v15 = 0;
    v5 = *v16;
    v15 = 0;
    v11 = *a2;
    v6 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64 *))(v5 + 24))(v16, &v11, &v15);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\basicutils.cpp",
        (const char *)(unsigned int)v6,
        v10);
    v7 = v15;
    v15 = 0;
    *a1 = v7;
    wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v15);
    wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v16);
    result = a1;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basicutils.cpp",
      v8);
    *a1 = 0;
    return a1;
  }
  return result;
}

```

## disassembly

```asm
0x180080934  mov     r11, rsp
0x180080937  mov     [r11+10h], rbx
0x18008093b  mov     [r11+8], rcx
0x18008093f  push    rdi
0x180080940  sub     rsp, 50h
0x180080944  mov     rdi, rdx
0x180080947  mov     rbx, rcx
0x18008094a  mov     qword ptr [r11+20h], 0
0x180080952  lea     rax, [r11+20h]
0x180080956  mov     [r11-38h], rax
0x18008095a  lea     r9, _GUID_c0bc943b_c585_40b4_9764_105af9dc62fc; riid
0x180080961  xor     edx, edx; pUnkOuter
0x180080963  lea     r8d, [rdx+4]; dwClsContext
0x180080967  lea     rcx, CLSID_UiaManager; rclsid
0x18008096e  call    cs:__imp_CoCreateInstance
0x180080974  mov     rcx, [rsp+58h]; this
0x180080979  test    eax, eax
0x18008097b  jns     short loc_180080991
0x18008097d  mov     r9d, eax; char *
0x180080980  lea     r8, aOnecoreWindows_3; "onecore\\windows\\accessibletech\\commo"...
0x180080987  mov     edx, 61h ; 'a'; void *
0x18008098c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080991  mov     [rsp+58h+arg_10], 0
0x18008099a  mov     rcx, [rsp+58h+arg_18]
0x18008099f  mov     rax, [rcx]
0x1800809a2  mov     [rsp+58h+arg_10], 0
0x1800809ab  movups  xmm0, xmmword ptr [rdi]
0x1800809ae  movdqu  [rsp+58h+var_18], xmm0
0x1800809b4  lea     r8, [rsp+58h+arg_10]
0x1800809b9  lea     rdx, [rsp+58h+var_18]
0x1800809be  mov     rax, [rax+18h]
0x1800809c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800809c7  mov     rcx, [rsp+58h]; this
0x1800809cc  test    eax, eax
0x1800809ce  jns     short loc_1800809E4
0x1800809d0  mov     r9d, eax; char *
0x1800809d3  lea     r8, aOnecoreWindows_3; "onecore\\windows\\accessibletech\\commo"...
0x1800809da  mov     edx, 64h ; 'd'; void *
0x1800809df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800809e4  mov     rax, [rsp+58h+arg_10]
0x1800809e9  mov     [rsp+58h+arg_10], 0
0x1800809f2  mov     [rbx], rax
0x1800809f5  lea     rcx, [rsp+58h+arg_10]
0x1800809fa  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x1800809ff  nop
0x180080a00  lea     rcx, [rsp+58h+arg_18]
0x180080a05  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x180080a0a  mov     rax, rbx
0x180080a0d  jmp     short loc_180080A14
0x180080a0f  mov     rax, [rsp+58h+arg_0]
0x180080a14  mov     rbx, [rsp+58h+arg_8]
0x180080a19  add     rsp, 50h
0x180080a1d  pop     rdi
0x180080a1e  retn
```
