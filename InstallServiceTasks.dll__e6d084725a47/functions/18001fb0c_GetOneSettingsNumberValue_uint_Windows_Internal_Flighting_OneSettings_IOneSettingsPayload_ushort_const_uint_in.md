# _GetOneSettingsNumberValue<uint>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,uint &,__int64,uint)

- ea: `0x18001fb0c`
- end: `0x18001fbfe`
- name: `??$_GetOneSettingsNumberValue@I@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAI_JI@Z`
- size: `242`
- prototype: `void __fastcall(__int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002e654`

## callees

- `0x180003450`
- `0x18000b48c`
- `0x18001fb0c`
- `0x1800291d8`
- `0x180046010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001fb9a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001fb9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fb46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fbdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fb46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fbdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fb8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fb8b`

## string_xrefs

- `0x18001fbc5`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`

## pseudocode

```c
void __fastcall _GetOneSettingsNumberValue<unsigned int>(__int64 a1, const WCHAR *a2)
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
0x18001fb0c  push    rbx
0x18001fb0e  push    rsi
0x18001fb0f  push    rdi
0x18001fb10  sub     rsp, 90h
0x18001fb17  mov     rax, cs:__security_cookie
0x18001fb1e  xor     rax, rsp
0x18001fb21  mov     [rsp+0A8h+var_28], rax
0x18001fb29  mov     rdi, r8
0x18001fb2c  mov     rsi, rcx
0x18001fb2f  mov     [rsp+0A8h+var_50], rdx
0x18001fb34  mov     [rsp+0A8h+string], 0
0x18001fb3d  mov     rax, [rcx]
0x18001fb40  mov     rbx, [rax+48h]
0x18001fb44  xor     ecx, ecx; string
0x18001fb46  call    cs:__imp_WindowsDeleteString
0x18001fb4c  mov     [rsp+0A8h+string], 0
0x18001fb55  lea     rdx, [rsp+0A8h+var_50]
0x18001fb5a  lea     rcx, [rsp+0A8h+var_48]
0x18001fb5f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001fb64  nop
0x18001fb65  lea     r8, [rsp+0A8h+string]
0x18001fb6a  mov     rdx, [rax+18h]
0x18001fb6e  mov     rcx, rsi
0x18001fb71  mov     rax, rbx
0x18001fb74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb79  mov     ebx, eax
0x18001fb7b  test    eax, eax
0x18001fb7d  js      short loc_18001FBB6
0x18001fb7f  mov     rcx, [rsp+0A8h+string]; string
0x18001fb84  test    rcx, rcx
0x18001fb87  jz      short loc_18001FBB6
0x18001fb89  xor     edx, edx; length
0x18001fb8b  call    cs:__imp_WindowsGetStringRawBuffer
0x18001fb91  xor     edx, edx; EndPtr
0x18001fb93  lea     r8d, [rdx+0Ah]; Radix
0x18001fb97  mov     rcx, rax; String
0x18001fb9a  call    cs:__imp_wcstoul
0x18001fba0  test    eax, eax
0x18001fba2  jz      short loc_18001FBB6
0x18001fba4  mov     ecx, [rsp+0A8h+arg_20]
0x18001fbab  test    ecx, ecx
0x18001fbad  jz      short loc_18001FBB4
0x18001fbaf  cmp     ecx, eax
0x18001fbb1  cmovb   eax, ecx
0x18001fbb4  mov     [rdi], eax
0x18001fbb6  mov     rcx, [rsp+0A8h]; this
0x18001fbbe  test    ebx, ebx
0x18001fbc0  jns     short loc_18001FBD7
0x18001fbc2  mov     r9d, ebx; char *
0x18001fbc5  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x18001fbcc  mov     edx, 1DBh; void *
0x18001fbd1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001fbd6  nop
0x18001fbd7  mov     rcx, [rsp+0A8h+string]; string
0x18001fbdc  call    cs:__imp_WindowsDeleteString
0x18001fbe2  nop
0x18001fbe3  mov     rcx, [rsp+0A8h+var_28]
0x18001fbeb  xor     rcx, rsp; StackCookie
0x18001fbee  call    __security_check_cookie
0x18001fbf3  add     rsp, 90h
0x18001fbfa  pop     rdi
0x18001fbfb  pop     rsi
0x18001fbfc  pop     rbx
0x18001fbfd  retn
```
