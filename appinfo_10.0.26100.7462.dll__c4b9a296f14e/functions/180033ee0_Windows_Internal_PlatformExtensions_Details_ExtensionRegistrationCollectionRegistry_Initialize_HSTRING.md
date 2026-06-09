# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::Initialize(HSTRING__ *)

- ea: `0x180033ee0`
- end: `0x180033fc2`
- name: `?Initialize@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHSTRING__@@@Z`
- size: `226`
- prototype: `int(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180032310`

## callees

- `0x180007c78`
- `0x18001053c`
- `0x180027220`
- `0x180033ee0`
- `0x180044a20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033f88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033f88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033f0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033f0a`

## string_xrefs

- `0x180033f3d`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`

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
0x180033ee0  mov     [rsp+arg_0], rbx
0x180033ee5  push    rdi
0x180033ee6  sub     rsp, 160h
0x180033eed  mov     rax, cs:__security_cookie
0x180033ef4  xor     rax, rsp
0x180033ef7  mov     [rsp+168h+var_18], rax
0x180033eff  mov     rax, rdx
0x180033f02  mov     rdi, rcx
0x180033f05  mov     rcx, rax; string
0x180033f08  xor     edx, edx; length
0x180033f0a  call    cs:__imp_WindowsGetStringRawBuffer
0x180033f11  nop     dword ptr [rax+rax+00h]
0x180033f16  lea     r8, aSoftwareClasse; "SOFTWARE\\Classes\\OneCoreContracts\\%s"
0x180033f1d  mov     edx, 80h; unsigned __int64
0x180033f22  mov     r9, rax
0x180033f25  lea     rcx, [rsp+168h+SubKey]; unsigned __int16 *
0x180033f2a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033f2f  mov     ebx, eax
0x180033f31  test    eax, eax
0x180033f33  jns     short loc_180033F55
0x180033f35  mov     rcx, [rsp+168h]; this
0x180033f3d  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180033f44  mov     r9d, eax; char *
0x180033f47  mov     edx, 129h; void *
0x180033f4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033f51  mov     eax, ebx
0x180033f53  jmp     short loc_180033FA0
0x180033f55  and     [rsp+168h+var_130], 0
0x180033f5b  lea     rax, [rdi+8]
0x180033f5f  mov     [rsp+168h+var_138], rax
0x180033f64  lea     rdx, [rsp+168h+SubKey]; lpSubKey
0x180033f69  lea     rax, [rsp+168h+var_130]
0x180033f6e  mov     [rsp+168h+var_128], 1
0x180033f73  mov     r9d, 20019h; samDesired
0x180033f79  mov     qword ptr [rsp+168h+phkResult], rax; phkResult
0x180033f7e  xor     r8d, r8d; ulOptions
0x180033f81  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033f88  call    cs:__imp_RegOpenKeyExW
0x180033f8f  nop     dword ptr [rax+rax+00h]
0x180033f94  lea     rcx, [rsp+168h+var_138]
0x180033f99  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180033f9e  xor     eax, eax
0x180033fa0  mov     rcx, [rsp+168h+var_18]
0x180033fa8  xor     rcx, rsp; StackCookie
0x180033fab  call    __security_check_cookie
0x180033fb0  mov     rbx, [rsp+168h+arg_0]
0x180033fb8  add     rsp, 160h
0x180033fbf  pop     rdi
0x180033fc0  retn
```
