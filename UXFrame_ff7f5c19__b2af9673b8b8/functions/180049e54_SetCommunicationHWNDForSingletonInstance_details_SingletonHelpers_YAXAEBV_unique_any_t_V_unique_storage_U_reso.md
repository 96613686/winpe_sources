# ?SetCommunicationHWNDForSingletonInstance@details@SingletonHelpers@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@_W@4@1PEAUHWND__@@@Z

- ea: `0x180049e54`
- end: `0x180049f09`
- name: `?SetCommunicationHWNDForSingletonInstance@details@SingletonHelpers@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@_W@4@1PEAUHWND__@@@Z`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180048f24`

## callees

- `0x180002b20`
- `0x18000e224`
- `0x18001049c`
- `0x180013174`
- `0x180049e54`
- `0x18004e680`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180049ecf`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180049ecf`

## string_xrefs

- `0x180049e7c`: `ShellCommon\Internal\Shell\Inc\SingletonHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SingletonHelpers::details::SetCommunicationHWNDForSingletonInstance(
        _QWORD *a1,
        __int64 *a2,
        HKEY *a3,
        const char *a4)
{
  int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // r8d
  unsigned int lpData; // [rsp+20h] [rbp-38h]
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  int Data; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = (int)a4;
  if ( !*a1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xE6,
      (unsigned int)"ShellCommon\\Internal\\Shell\\Inc\\SingletonHelpers.h",
      a4);
  hKey = 0;
  SingletonHelpers::details::GetSingletonSessionSubKey(&hKey, a2, a3, 0x20006u);
  Data = v4;
  v5 = RegSetKeyValueW(hKey, 0, L"CommunicationHWND", 4u, &Data, 4u);
  if ( v5 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0xEC, v6, (const char *)v5, lpData);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x180049e54  push    rbx
0x180049e56  sub     rsp, 50h
0x180049e5a  mov     rax, cs:__security_cookie
0x180049e61  xor     rax, rsp
0x180049e64  mov     [rsp+58h+var_18], rax
0x180049e69  mov     rbx, r9
0x180049e6c  cmp     qword ptr [rcx], 0
0x180049e70  setz    al
0x180049e73  mov     rcx, [rsp+58h]; this
0x180049e78  test    al, al
0x180049e7a  jz      short loc_180049E8E
0x180049e7c  lea     r8, aShellcommonInt; "ShellCommon\\Internal\\Shell\\Inc\\Sing"...
0x180049e83  mov     edx, 0E6h; void *
0x180049e88  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180049e8e  mov     [rsp+58h+hKey], 0
0x180049e97  mov     r9d, 20006h
0x180049e9d  lea     rcx, [rsp+58h+hKey]
0x180049ea2  call    ?GetSingletonSessionSubKey@details@SingletonHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@_W@4@0K@Z; SingletonHelpers::details::GetSingletonSessionSubKey(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,ulong)
0x180049ea7  nop
0x180049ea8  mov     [rsp+58h+Data], ebx
0x180049eac  mov     r9d, 4; dwType
0x180049eb2  mov     [rsp+58h+cbData], r9d; cbData
0x180049eb7  lea     rax, [rsp+58h+Data]
0x180049ebc  mov     [rsp+58h+lpData], rax; unsigned int
0x180049ec1  mov     r8, cs:off_1800633F0; lpValueName
0x180049ec8  xor     edx, edx; lpSubKey
0x180049eca  mov     rcx, [rsp+58h+hKey]; hKey
0x180049ecf  call    cs:__imp_RegSetKeyValueW
0x180049ed5  mov     rcx, [rsp+58h]; this
0x180049eda  test    eax, eax
0x180049edc  jz      short loc_180049EEC
0x180049ede  mov     r9d, eax; char *
0x180049ee1  mov     edx, 0ECh; void *
0x180049ee6  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180049eec  lea     rcx, [rsp+58h+hKey]
0x180049ef1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180049ef6  mov     rcx, [rsp+58h+var_18]
0x180049efb  xor     rcx, rsp; StackCookie
0x180049efe  call    __security_check_cookie
0x180049f03  add     rsp, 50h
0x180049f07  pop     rbx
0x180049f08  retn
```
