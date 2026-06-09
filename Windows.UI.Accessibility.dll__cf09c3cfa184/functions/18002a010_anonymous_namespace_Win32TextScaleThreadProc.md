# _anonymous_namespace_::Win32TextScaleThreadProc

- ea: `0x18002a010`
- end: `0x18002a0ec`
- name: `_anonymous_namespace_::Win32TextScaleThreadProc`
- size: `220`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180008ebc`
- `0x18000cf94`
- `0x18000e2ec`
- `0x180028f9c`
- `0x18002a010`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002a0a3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002a0a3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a052`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a052`

## string_xrefs

- `0x18002a0c5`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`
- `0x18002a0d9`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall anonymous_namespace_::Win32TextScaleThreadProc(PVOID Parameter)
{
  HRESULT v1; // eax
  int v2; // eax
  const char *v3; // r9
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v7; // [rsp+40h] [rbp+8h]
  LPVOID v8; // [rsp+48h] [rbp+10h] BYREF
  PVOID v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = Parameter;
  try
  {
    wil::CoInitializeEx();
    v8 = 0;
    v1 = CoCreateInstance(&rclsid, 0, 3u, &GUID_2b28b8ef_ef92_4587_adf0_b8c9f8b7a27e, &v8);
    if ( v1 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.viewmanagement.core.u"
                      "isettingscontroller.cpp",
        (const char *)(unsigned int)v1,
        ppv);
    v2 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 24LL))(v8);
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.viewmanagement.core.u"
                      "isettingscontroller.cpp",
        (const char *)(unsigned int)v2,
        ppv);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v8);
    if ( v7 )
      CoUninitialize();
    std::unique_ptr<int>::~unique_ptr<int>(&v9);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x78,
                           (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.vi"
                                         "ewmanagement.core.uisettingscontroller.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x18002a010  push    rbx
0x18002a012  sub     rsp, 30h
0x18002a016  mov     rbx, rcx
0x18002a019  mov     [rsp+38h+arg_10], rcx
0x18002a01e  lea     rcx, [rsp+38h+arg_0]
0x18002a023  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x18002a028  nop
0x18002a029  mov     ebx, [rbx]
0x18002a02b  mov     [rsp+38h+arg_8], 0
0x18002a034  lea     rax, [rsp+38h+arg_8]
0x18002a039  mov     qword ptr [rsp+38h+ppv], rax; int
0x18002a03e  lea     r9, _GUID_2b28b8ef_ef92_4587_adf0_b8c9f8b7a27e; riid
0x18002a045  xor     edx, edx; pUnkOuter
0x18002a047  lea     r8d, [rdx+3]; dwClsContext
0x18002a04b  lea     rcx, rclsid; rclsid
0x18002a052  call    cs:__imp_CoCreateInstance
0x18002a058  mov     rcx, [rsp+38h]; this
0x18002a05d  test    eax, eax
0x18002a05f  js      short loc_18002A0C2
0x18002a061  mov     rcx, [rsp+38h+arg_8]
0x18002a066  mov     rax, [rcx]
0x18002a069  movd    xmm1, ebx
0x18002a06d  cvtdq2pd xmm1, xmm1
0x18002a071  divsd   xmm1, cs:__real@4059000000000000
0x18002a079  mov     rax, [rax+18h]
0x18002a07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a082  mov     rcx, [rsp+38h]; this
0x18002a087  test    eax, eax
0x18002a089  js      short loc_18002A0D6
0x18002a08b  lea     rcx, [rsp+38h+arg_8]
0x18002a090  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18002a095  nop
0x18002a096  mov     al, byte ptr [rsp+38h+arg_0]
0x18002a09a  mov     byte ptr [rsp+38h+arg_0], 0
0x18002a09f  test    al, al
0x18002a0a1  jz      short loc_18002A0AA
0x18002a0a3  call    cs:__imp_CoUninitialize
0x18002a0a9  nop
0x18002a0aa  lea     rcx, [rsp+38h+arg_10]
0x18002a0af  call    ??1?$unique_ptr@HU?$default_delete@H@std@@@std@@QEAA@XZ; std::unique_ptr<int>::~unique_ptr<int>(void)
0x18002a0b4  xor     eax, eax
0x18002a0b6  jmp     short loc_18002A0BC
0x18002a0b8  mov     eax, [rsp+38h+arg_0]
0x18002a0bc  add     rsp, 30h
0x18002a0c0  pop     rbx
0x18002a0c1  retn
0x18002a0c2  mov     r9d, eax; char *
0x18002a0c5  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002a0cc  mov     edx, 73h ; 's'; void *
0x18002a0d1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002a0d6  mov     r9d, eax; char *
0x18002a0d9  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002a0e0  mov     edx, 74h ; 't'; void *
0x18002a0e5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
