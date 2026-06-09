# _ReadDirectDownloadEnablementLiveCheckThreshold(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *)

- ea: `0x180029920`
- end: `0x180029a5e`
- name: `?_ReadDirectDownloadEnablementLiveCheckThreshold@@YAJPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@@Z`
- size: `318`
- prototype: `__int64 __fastcall(struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b21c`
- `0x18002e654`

## callees

- `0x180003450`
- `0x18000912c`
- `0x18000b48c`
- `0x180012f10`
- `0x180029920`
- `0x180046010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800299d1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800299d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029951`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800299ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029a2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029951`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800299ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029a2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800299c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800299c2`

## string_xrefs

- `0x180029997`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180029a18`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x1800299f7`: `DirectDownloadEnablementLiveCheckThreshold in milliseconds fetched from cache: %d`
- `0x180029a0b`: `_ReadDirectDownloadEnablementLiveCheckThreshold`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall _ReadDirectDownloadEnablementLiveCheckThreshold(
        struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *a1)
{
  __int64 (__fastcall *v2)(struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *, PVOID, HSTRING *); // rbx
  char v3; // r8
  HSTRING_HEADER *v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  const wchar_t *StringRawBuffer; // rax
  unsigned int v9; // eax
  int v10; // [rsp+20h] [rbp-68h]
  unsigned int v11; // [rsp+40h] [rbp-48h]
  HSTRING string; // [rsp+50h] [rbp-38h] BYREF
  HSTRING_HEADER v13; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  string = 0;
  v2 = *(__int64 (__fastcall **)(struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *, PVOID, HSTRING *))(*(_QWORD *)a1 + 72LL);
  WindowsDeleteString(0);
  string = 0;
  v4 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v13, (const WCHAR **)off_1800485A8, v3);
  v5 = v2(a1, v4[1].Reserved.Reserved1, &string);
  v6 = v5;
  if ( v5 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v9 = wcstoul(StringRawBuffer, 0, 10);
    if ( v9 )
    {
      dword_180069C08 = v9;
      v11 = v9;
      LogMessage(
        4u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        0xFCAu,
        "_ReadDirectDownloadEnablementLiveCheckThreshold",
        -1,
        L"DirectDownloadEnablementLiveCheckThreshold in milliseconds fetched from cache: %d",
        0,
        0,
        v11);
    }
    WindowsDeleteString(string);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFC4,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      (const char *)(unsigned int)v5,
      v10);
    WindowsDeleteString(string);
    return v6;
  }
}

```

## disassembly

```asm
0x180029920  mov     [rsp+arg_8], rbx
0x180029925  push    rdi
0x180029926  sub     rsp, 80h
0x18002992d  mov     rax, cs:__security_cookie
0x180029934  xor     rax, rsp
0x180029937  mov     [rsp+88h+var_10], rax
0x18002993c  mov     rdi, rcx
0x18002993f  mov     [rsp+88h+string], 0
0x180029948  mov     rax, [rcx]
0x18002994b  mov     rbx, [rax+48h]
0x18002994f  xor     ecx, ecx; string
0x180029951  call    cs:__imp_WindowsDeleteString
0x180029957  mov     [rsp+88h+string], 0
0x180029960  lea     rdx, off_1800485A8; "DIRECTDOWNLOADENABLEMENTLIVECHECKTHRESH"...
0x180029967  lea     rcx, [rsp+88h+var_30]
0x18002996c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180029971  nop
0x180029972  lea     r8, [rsp+88h+string]
0x180029977  mov     rdx, [rax+18h]
0x18002997b  mov     rcx, rdi
0x18002997e  mov     rax, rbx
0x180029981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029986  mov     ebx, eax
0x180029988  test    eax, eax
0x18002998a  jns     short loc_1800299BB
0x18002998c  mov     rcx, [rsp+88h]; this
0x180029994  mov     r9d, eax; char *
0x180029997  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x18002999e  mov     edx, 0FC4h; void *
0x1800299a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800299a8  nop
0x1800299a9  mov     rcx, [rsp+88h+string]; string
0x1800299ae  call    cs:__imp_WindowsDeleteString
0x1800299b4  mov     eax, ebx
0x1800299b6  jmp     loc_180029A3F
0x1800299bb  xor     edx, edx; length
0x1800299bd  mov     rcx, [rsp+88h+string]; string
0x1800299c2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800299c8  xor     edx, edx; EndPtr
0x1800299ca  lea     r8d, [rdx+0Ah]; Radix
0x1800299ce  mov     rcx, rax; String
0x1800299d1  call    cs:__imp_wcstoul
0x1800299d7  test    eax, eax
0x1800299d9  jz      short loc_180029A2A
0x1800299db  mov     cs:dword_180069C08, eax
0x1800299e1  mov     [rsp+88h+var_48], eax
0x1800299e5  mov     [rsp+88h+var_50], 0; unsigned __int16 *
0x1800299ee  mov     [rsp+88h+var_58], 0; char *
0x1800299f7  lea     rax, aDirectdownload_2; "DirectDownloadEnablementLiveCheckThresh"...
0x1800299fe  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x180029a03  mov     [rsp+88h+var_68], 0FFFFFFFFh; int
0x180029a0b  lea     r9, aReaddirectdown; "_ReadDirectDownloadEnablementLiveCheckT"...
0x180029a12  mov     r8d, 0FCAh; unsigned int
0x180029a18  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x180029a1f  mov     ecx, 4; unsigned int
0x180029a24  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180029a29  nop
0x180029a2a  mov     rcx, [rsp+88h+string]; string
0x180029a2f  call    cs:__imp_WindowsDeleteString
0x180029a35  nop
0x180029a36  xor     eax, eax
0x180029a38  jmp     short loc_180029A3F
0x180029a3a  mov     eax, 80004005h
0x180029a3f  mov     rcx, [rsp+88h+var_10]
0x180029a44  xor     rcx, rsp; StackCookie
0x180029a47  call    __security_check_cookie
0x180029a4c  mov     rbx, [rsp+88h+arg_8]
0x180029a54  add     rsp, 80h
0x180029a5b  pop     rdi
0x180029a5c  retn
```
