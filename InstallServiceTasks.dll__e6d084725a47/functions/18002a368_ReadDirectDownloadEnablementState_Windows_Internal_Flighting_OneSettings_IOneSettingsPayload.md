# _ReadDirectDownloadEnablementState(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *)

- ea: `0x18002a368`
- end: `0x18002a498`
- name: `?_ReadDirectDownloadEnablementState@@YAJPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@@Z`
- size: `304`
- prototype: `__int64 __fastcall(struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b21c`
- `0x18002e654`

## callees

- `0x180003450`
- `0x18000912c`
- `0x18000b48c`
- `0x180012f10`
- `0x180029208`
- `0x18002a368`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a399`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a3f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a469`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a399`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a3f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a469`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a407`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a407`

## string_xrefs

- `0x18002a3df`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18002a452`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18002a445`: `_ReadDirectDownloadEnablementState`
- `0x18002a431`: `DirectDownloadEnablementState fetched from cache: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _ReadDirectDownloadEnablementState(
        struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *a1)
{
  __int64 (__fastcall *v2)(struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *, PVOID, HSTRING *); // rbx
  char v3; // r8
  HSTRING_HEADER *v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 result; // rax
  PCWSTR StringRawBuffer; // rcx
  int v9; // [rsp+20h] [rbp-68h]
  int v10; // [rsp+40h] [rbp-48h]
  HSTRING string; // [rsp+50h] [rbp-38h] BYREF
  HSTRING_HEADER v12; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  string = 0;
  v2 = *(__int64 (__fastcall **)(struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *, PVOID, HSTRING *))(*(_QWORD *)a1 + 72LL);
  WindowsDeleteString(0);
  string = 0;
  v4 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v12, (const WCHAR **)off_1800485B8, v3);
  try
  {
    v5 = v2(a1, v4[1].Reserved.Reserved1, &string);
    v6 = v5;
    if ( v5 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      dword_180083C44 = _ParseDirectDownloadEnablementStateString(StringRawBuffer);
      v10 = dword_180083C44;
      LogMessage(
        4u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        0xF7Du,
        "_ReadDirectDownloadEnablementState",
        -1,
        L"DirectDownloadEnablementState fetched from cache: %d",
        0,
        0,
        v10);
      WindowsDeleteString(string);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF7B,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        (const char *)(unsigned int)v5,
        v9);
      WindowsDeleteString(string);
      result = v6;
    }
  }
  catch ( ... )
  {
    LogSimpleMessage(
      2u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      0xF81u,
      "_ReadDirectDownloadEnablementState",
      -1,
      L"Exception while reading DirectDownloadEnablementState from OneSettings",
      0,
      0);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002a368  mov     [rsp+arg_8], rbx
0x18002a36d  push    rdi
0x18002a36e  sub     rsp, 80h
0x18002a375  mov     rax, cs:__security_cookie
0x18002a37c  xor     rax, rsp
0x18002a37f  mov     [rsp+88h+var_10], rax
0x18002a384  mov     rdi, rcx
0x18002a387  mov     [rsp+88h+string], 0
0x18002a390  mov     rax, [rcx]
0x18002a393  mov     rbx, [rax+48h]
0x18002a397  xor     ecx, ecx; string
0x18002a399  call    cs:__imp_WindowsDeleteString
0x18002a39f  mov     [rsp+88h+string], 0
0x18002a3a8  lea     rdx, off_1800485B8; "DIRECTDOWNLOADENABLEMENTSTATE"
0x18002a3af  lea     rcx, [rsp+88h+var_30]
0x18002a3b4  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002a3b9  nop
0x18002a3ba  lea     r8, [rsp+88h+string]
0x18002a3bf  mov     rdx, [rax+18h]
0x18002a3c3  mov     rcx, rdi
0x18002a3c6  mov     rax, rbx
0x18002a3c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3ce  mov     ebx, eax
0x18002a3d0  test    eax, eax
0x18002a3d2  jns     short loc_18002A400
0x18002a3d4  mov     rcx, [rsp+88h]; this
0x18002a3dc  mov     r9d, eax; char *
0x18002a3df  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x18002a3e6  mov     edx, 0F7Bh; void *
0x18002a3eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a3f0  nop
0x18002a3f1  mov     rcx, [rsp+88h+string]; string
0x18002a3f6  call    cs:__imp_WindowsDeleteString
0x18002a3fc  mov     eax, ebx
0x18002a3fe  jmp     short loc_18002A479
0x18002a400  xor     edx, edx; length
0x18002a402  mov     rcx, [rsp+88h+string]; string
0x18002a407  call    cs:__imp_WindowsGetStringRawBuffer
0x18002a40d  mov     rcx, rax
0x18002a410  call    ?_ParseDirectDownloadEnablementStateString@@YA?AW4DirectDownloadEnablementState@@PEBG@Z; _ParseDirectDownloadEnablementStateString(ushort const *)
0x18002a415  mov     cs:dword_180083C44, eax
0x18002a41b  mov     [rsp+88h+var_48], eax
0x18002a41f  mov     [rsp+88h+var_50], 0; unsigned __int16 *
0x18002a428  mov     [rsp+88h+var_58], 0; char *
0x18002a431  lea     rax, aDirectdownload_0; "DirectDownloadEnablementState fetched f"...
0x18002a438  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x18002a43d  mov     [rsp+88h+var_68], 0FFFFFFFFh; int
0x18002a445  lea     r9, aReaddirectdown_0; "_ReadDirectDownloadEnablementState"
0x18002a44c  mov     r8d, 0F7Dh; unsigned int
0x18002a452  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x18002a459  mov     ecx, 4; unsigned int
0x18002a45e  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18002a463  nop
0x18002a464  mov     rcx, [rsp+88h+string]; string
0x18002a469  call    cs:__imp_WindowsDeleteString
0x18002a46f  nop
0x18002a470  xor     eax, eax
0x18002a472  jmp     short loc_18002A479
0x18002a474  mov     eax, 80004005h
0x18002a479  mov     rcx, [rsp+88h+var_10]
0x18002a47e  xor     rcx, rsp; StackCookie
0x18002a481  call    __security_check_cookie
0x18002a486  mov     rbx, [rsp+88h+arg_8]
0x18002a48e  add     rsp, 80h
0x18002a495  pop     rdi
0x18002a496  retn
```
