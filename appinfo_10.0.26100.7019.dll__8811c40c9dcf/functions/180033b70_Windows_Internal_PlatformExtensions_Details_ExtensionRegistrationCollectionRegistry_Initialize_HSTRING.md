# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::Initialize(HSTRING__ *)

- ea: `0x180033b70`
- end: `0x180033c52`
- name: `?Initialize@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHSTRING__@@@Z`
- size: `226`
- prototype: `int(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180031fe0`

## callees

- `0x180007c78`
- `0x180010400`
- `0x180028790`
- `0x180033b70`
- `0x180042950`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033c18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033c18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033b9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033b9a`

## string_xrefs

- `0x180033bcd`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`

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
0x180033b70  mov     [rsp+arg_0], rbx
0x180033b75  push    rdi
0x180033b76  sub     rsp, 160h
0x180033b7d  mov     rax, cs:__security_cookie
0x180033b84  xor     rax, rsp
0x180033b87  mov     [rsp+168h+var_18], rax
0x180033b8f  mov     rax, rdx
0x180033b92  mov     rdi, rcx
0x180033b95  mov     rcx, rax; string
0x180033b98  xor     edx, edx; length
0x180033b9a  call    cs:__imp_WindowsGetStringRawBuffer
0x180033ba1  nop     dword ptr [rax+rax+00h]
0x180033ba6  lea     r8, aSoftwareClasse; "SOFTWARE\\Classes\\OneCoreContracts\\%s"
0x180033bad  mov     edx, 80h; unsigned __int64
0x180033bb2  mov     r9, rax
0x180033bb5  lea     rcx, [rsp+168h+SubKey]; unsigned __int16 *
0x180033bba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033bbf  mov     ebx, eax
0x180033bc1  test    eax, eax
0x180033bc3  jns     short loc_180033BE5
0x180033bc5  mov     rcx, [rsp+168h]; this
0x180033bcd  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180033bd4  mov     r9d, eax; char *
0x180033bd7  mov     edx, 129h; void *
0x180033bdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033be1  mov     eax, ebx
0x180033be3  jmp     short loc_180033C30
0x180033be5  and     [rsp+168h+var_130], 0
0x180033beb  lea     rax, [rdi+8]
0x180033bef  mov     [rsp+168h+var_138], rax
0x180033bf4  lea     rdx, [rsp+168h+SubKey]; lpSubKey
0x180033bf9  lea     rax, [rsp+168h+var_130]
0x180033bfe  mov     [rsp+168h+var_128], 1
0x180033c03  mov     r9d, 20019h; samDesired
0x180033c09  mov     qword ptr [rsp+168h+phkResult], rax; phkResult
0x180033c0e  xor     r8d, r8d; ulOptions
0x180033c11  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033c18  call    cs:__imp_RegOpenKeyExW
0x180033c1f  nop     dword ptr [rax+rax+00h]
0x180033c24  lea     rcx, [rsp+168h+var_138]
0x180033c29  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180033c2e  xor     eax, eax
0x180033c30  mov     rcx, [rsp+168h+var_18]
0x180033c38  xor     rcx, rsp; StackCookie
0x180033c3b  call    __security_check_cookie
0x180033c40  mov     rbx, [rsp+168h+arg_0]
0x180033c48  add     rsp, 160h
0x180033c4f  pop     rdi
0x180033c50  retn
```
