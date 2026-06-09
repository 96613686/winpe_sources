# _GetOneSettingsNumberValue<__int64>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,__int64 &,__int64,__int64)

- ea: `0x18001fc04`
- end: `0x18001fcff`
- name: `??$_GetOneSettingsNumberValue@_J@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEA_J_J3@Z`
- size: `251`
- prototype: `void __fastcall(__int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002e654`

## callees

- `0x180003450`
- `0x18000b48c`
- `0x18001fc04`
- `0x1800291d8`
- `0x180046010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001fc9a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001fc9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fcd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fcd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fc8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fc8b`

## string_xrefs

- `0x18001fcbd`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`

## pseudocode

```c
void __fastcall _GetOneSettingsNumberValue<__int64>(__int64 a1, const WCHAR *a2)
{
  __int64 (*v2)(void); // rbx
  char v3; // r8
  int v4; // ebx
  int v5; // [rsp+20h] [rbp-88h]
  const WCHAR *v6; // [rsp+58h] [rbp-50h] BYREF
  HSTRING_HEADER v7; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v6 = a2;
  v2 = *(__int64 (**)(void))(*(_QWORD *)a1 + 72LL);
  WindowsDeleteString(0);
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v7, &v6, v3);
  try
  {
    v4 = v2();
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1DB,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        (const char *)(unsigned int)v4,
        v5);
    WindowsDeleteString(0);
  }
  catch ( ... )
  {
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      0x1DFu,
      "_GetOneSettingsNumberValue",
      -1,
      L"Exception while reading OneSettings value for %s, using default value",
      0,
      0,
      v6);
  }
}

```

## disassembly

```asm
0x18001fc04  mov     [rsp+arg_18], rbx
0x18001fc09  push    rsi
0x18001fc0a  push    rdi
0x18001fc0b  push    r14
0x18001fc0d  sub     rsp, 90h
0x18001fc14  mov     rax, cs:__security_cookie
0x18001fc1b  xor     rax, rsp
0x18001fc1e  mov     [rsp+0A8h+var_28], rax
0x18001fc26  mov     r14, r9
0x18001fc29  mov     rdi, r8
0x18001fc2c  mov     rsi, rcx
0x18001fc2f  mov     [rsp+0A8h+var_50], rdx
0x18001fc34  mov     [rsp+0A8h+string], 0
0x18001fc3d  mov     rax, [rcx]
0x18001fc40  mov     rbx, [rax+48h]
0x18001fc44  xor     ecx, ecx; string
0x18001fc46  call    cs:__imp_WindowsDeleteString
0x18001fc4c  mov     [rsp+0A8h+string], 0
0x18001fc55  lea     rdx, [rsp+0A8h+var_50]
0x18001fc5a  lea     rcx, [rsp+0A8h+var_48]
0x18001fc5f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001fc64  nop
0x18001fc65  lea     r8, [rsp+0A8h+string]
0x18001fc6a  mov     rdx, [rax+18h]
0x18001fc6e  mov     rcx, rsi
0x18001fc71  mov     rax, rbx
0x18001fc74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc79  mov     ebx, eax
0x18001fc7b  test    eax, eax
0x18001fc7d  js      short loc_18001FCAE
0x18001fc7f  mov     rcx, [rsp+0A8h+string]; string
0x18001fc84  test    rcx, rcx
0x18001fc87  jz      short loc_18001FCAE
0x18001fc89  xor     edx, edx; length
0x18001fc8b  call    cs:__imp_WindowsGetStringRawBuffer
0x18001fc91  xor     edx, edx; EndPtr
0x18001fc93  lea     r8d, [rdx+0Ah]; Radix
0x18001fc97  mov     rcx, rax; String
0x18001fc9a  call    cs:__imp_wcstoul
0x18001fca0  mov     eax, eax
0x18001fca2  imul    rax, r14
0x18001fca6  test    rax, rax
0x18001fca9  jz      short loc_18001FCAE
0x18001fcab  mov     [rdi], rax
0x18001fcae  mov     rcx, [rsp+0A8h]; this
0x18001fcb6  test    ebx, ebx
0x18001fcb8  jns     short loc_18001FCCF
0x18001fcba  mov     r9d, ebx; char *
0x18001fcbd  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x18001fcc4  mov     edx, 1DBh; void *
0x18001fcc9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001fcce  nop
0x18001fccf  mov     rcx, [rsp+0A8h+string]; string
0x18001fcd4  call    cs:__imp_WindowsDeleteString
0x18001fcda  nop
0x18001fcdb  mov     rcx, [rsp+0A8h+var_28]
0x18001fce3  xor     rcx, rsp; StackCookie
0x18001fce6  call    __security_check_cookie
0x18001fceb  mov     rbx, [rsp+0A8h+arg_18]
0x18001fcf3  add     rsp, 90h
0x18001fcfa  pop     r14
0x18001fcfc  pop     rdi
0x18001fcfd  pop     rsi
0x18001fcfe  retn
```
