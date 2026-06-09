# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::Initialize(HSTRING__ *)

- ea: `0x180033c20`
- end: `0x180033d02`
- name: `?Initialize@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHSTRING__@@@Z`
- size: `226`
- prototype: `int(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180032050`

## callees

- `0x180007c78`
- `0x18001053c`
- `0x180027150`
- `0x180033c20`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033cc8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033cc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033c4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033c4a`

## string_xrefs

- `0x180033c7d`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::Initialize(
        Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *this,
        HSTRING a2)
{
  PCWSTR StringRawBuffer; // rax
  int v4; // eax
  unsigned int v5; // ebx
  int phkResult; // [rsp+20h] [rbp-148h]
  char *v8; // [rsp+30h] [rbp-138h] BYREF
  HKEY v9; // [rsp+38h] [rbp-130h] BYREF
  char v10; // [rsp+40h] [rbp-128h]
  WCHAR SubKey[128]; // [rsp+50h] [rbp-118h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v4 = StringCchPrintfW(SubKey, 0x80u, L"SOFTWARE\\Classes\\OneCoreContracts\\%s", StringRawBuffer);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v9 = 0;
    v8 = (char *)this + 8;
    v10 = 1;
    RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &v9);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v8);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x129,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
      (const char *)(unsigned int)v4,
      phkResult);
    return v5;
  }
}

```

## disassembly

```asm
0x180033c20  mov     [rsp+arg_0], rbx
0x180033c25  push    rdi
0x180033c26  sub     rsp, 160h
0x180033c2d  mov     rax, cs:__security_cookie
0x180033c34  xor     rax, rsp
0x180033c37  mov     [rsp+168h+var_18], rax
0x180033c3f  mov     rax, rdx
0x180033c42  mov     rdi, rcx
0x180033c45  mov     rcx, rax; string
0x180033c48  xor     edx, edx; length
0x180033c4a  call    cs:__imp_WindowsGetStringRawBuffer
0x180033c51  nop     dword ptr [rax+rax+00h]
0x180033c56  lea     r8, aSoftwareClasse; "SOFTWARE\\Classes\\OneCoreContracts\\%s"
0x180033c5d  mov     edx, 80h; unsigned __int64
0x180033c62  mov     r9, rax
0x180033c65  lea     rcx, [rsp+168h+SubKey]; unsigned __int16 *
0x180033c6a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033c6f  mov     ebx, eax
0x180033c71  test    eax, eax
0x180033c73  jns     short loc_180033C95
0x180033c75  mov     rcx, [rsp+168h]; this
0x180033c7d  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180033c84  mov     r9d, eax; char *
0x180033c87  mov     edx, 129h; void *
0x180033c8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033c91  mov     eax, ebx
0x180033c93  jmp     short loc_180033CE0
0x180033c95  and     [rsp+168h+var_130], 0
0x180033c9b  lea     rax, [rdi+8]
0x180033c9f  mov     [rsp+168h+var_138], rax
0x180033ca4  lea     rdx, [rsp+168h+SubKey]; lpSubKey
0x180033ca9  lea     rax, [rsp+168h+var_130]
0x180033cae  mov     [rsp+168h+var_128], 1
0x180033cb3  mov     r9d, 20019h; samDesired
0x180033cb9  mov     qword ptr [rsp+168h+phkResult], rax; phkResult
0x180033cbe  xor     r8d, r8d; ulOptions
0x180033cc1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033cc8  call    cs:__imp_RegOpenKeyExW
0x180033ccf  nop     dword ptr [rax+rax+00h]
0x180033cd4  lea     rcx, [rsp+168h+var_138]
0x180033cd9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180033cde  xor     eax, eax
0x180033ce0  mov     rcx, [rsp+168h+var_18]
0x180033ce8  xor     rcx, rsp; StackCookie
0x180033ceb  call    __security_check_cookie
0x180033cf0  mov     rbx, [rsp+168h+arg_0]
0x180033cf8  add     rsp, 160h
0x180033cff  pop     rdi
0x180033d00  retn
```
