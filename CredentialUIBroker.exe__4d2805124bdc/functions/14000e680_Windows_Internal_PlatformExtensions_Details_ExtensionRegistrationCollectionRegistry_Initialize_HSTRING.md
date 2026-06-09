# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::Initialize(HSTRING__ *)

- ea: `0x14000e680`
- end: `0x14000e758`
- name: `?Initialize@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHSTRING__@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *this, HSTRING)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x14000d40c`

## callees

- `0x140003620`
- `0x140008f70`
- `0x14000e680`
- `0x1400136fc`
- `0x1400163c8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000e725`
- `ADVAPI32!RegOpenKeyExW` at `0x14000e725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000e6aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000e6aa`

## string_xrefs

- `0x14000e6d7`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

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
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v4,
      phkResult);
    return v5;
  }
}

```

## disassembly

```asm
0x14000e680  mov     [rsp+arg_0], rbx
0x14000e685  push    rdi
0x14000e686  sub     rsp, 160h
0x14000e68d  mov     rax, cs:__security_cookie
0x14000e694  xor     rax, rsp
0x14000e697  mov     [rsp+168h+var_18], rax
0x14000e69f  mov     rax, rdx
0x14000e6a2  mov     rdi, rcx
0x14000e6a5  mov     rcx, rax; string
0x14000e6a8  xor     edx, edx; length
0x14000e6aa  call    cs:__imp_WindowsGetStringRawBuffer
0x14000e6b0  lea     r8, aSoftwareClasse; "SOFTWARE\\Classes\\OneCoreContracts\\%s"
0x14000e6b7  mov     edx, 80h; unsigned __int64
0x14000e6bc  mov     r9, rax
0x14000e6bf  lea     rcx, [rsp+168h+SubKey]; unsigned __int16 *
0x14000e6c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000e6c9  mov     ebx, eax
0x14000e6cb  test    eax, eax
0x14000e6cd  jns     short loc_14000E6EF
0x14000e6cf  mov     rcx, [rsp+168h]; this
0x14000e6d7  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x14000e6de  mov     r9d, eax; char *
0x14000e6e1  mov     edx, 129h; void *
0x14000e6e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e6eb  mov     eax, ebx
0x14000e6ed  jmp     short loc_14000E737
0x14000e6ef  lea     rax, [rdi+8]
0x14000e6f3  mov     [rsp+168h+var_130], 0
0x14000e6fc  mov     [rsp+168h+var_138], rax
0x14000e701  lea     rdx, [rsp+168h+SubKey]; lpSubKey
0x14000e706  lea     rax, [rsp+168h+var_130]
0x14000e70b  mov     [rsp+168h+var_128], 1
0x14000e710  mov     r9d, 20019h; samDesired
0x14000e716  mov     qword ptr [rsp+168h+phkResult], rax; phkResult
0x14000e71b  xor     r8d, r8d; ulOptions
0x14000e71e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000e725  call    cs:__imp_RegOpenKeyExW
0x14000e72b  lea     rcx, [rsp+168h+var_138]
0x14000e730  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x14000e735  xor     eax, eax
0x14000e737  mov     rcx, [rsp+168h+var_18]
0x14000e73f  xor     rcx, rsp; StackCookie
0x14000e742  call    __security_check_cookie
0x14000e747  mov     rbx, [rsp+168h+arg_0]
0x14000e74f  add     rsp, 160h
0x14000e756  pop     rdi
0x14000e757  retn
```
