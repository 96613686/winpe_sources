# ?SetPIDAndClearCommunicationHWNDForSingletonInstance@details@SingletonHelpers@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@_W@4@1@Z

- ea: `0x180049f10`
- end: `0x180049fda`
- name: `?SetPIDAndClearCommunicationHWNDForSingletonInstance@details@SingletonHelpers@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@_W@4@1@Z`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004b86c`

## callees

- `0x180002b20`
- `0x18000e224`
- `0x18001049c`
- `0x180013174`
- `0x180049f10`
- `0x18004e680`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180049f5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180049f5f`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180049fb7`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180049fb7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180049f8c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180049f8c`

## string_xrefs

- `0x180049f33`: `ShellCommon\Internal\Shell\Inc\SingletonHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SingletonHelpers::details::SetPIDAndClearCommunicationHWNDForSingletonInstance(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  unsigned int v4; // eax
  unsigned int v5; // r8d
  unsigned int lpData; // [rsp+20h] [rbp-38h]
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  DWORD Data; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !*a1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC1,
      (unsigned int)"ShellCommon\\Internal\\Shell\\Inc\\SingletonHelpers.h",
      a4);
  hKey = 0;
  SingletonHelpers::details::GetSingletonSessionSubKey(&hKey, a2, a3, 131078);
  Data = GetCurrentProcessId();
  v4 = RegSetKeyValueW(hKey, 0, L"ProcessId", 4u, &Data, 4u);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0xC7, v5, (const char *)v4, lpData);
  RegDeleteKeyValueW(hKey, 0, L"CommunicationHWND");
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x180049f10  sub     rsp, 58h
0x180049f14  mov     rax, cs:__security_cookie
0x180049f1b  xor     rax, rsp
0x180049f1e  mov     [rsp+58h+var_18], rax
0x180049f23  cmp     qword ptr [rcx], 0
0x180049f27  setz    al
0x180049f2a  mov     rcx, [rsp+58h]; this
0x180049f2f  test    al, al
0x180049f31  jz      short loc_180049F45
0x180049f33  lea     r8, aShellcommonInt; "ShellCommon\\Internal\\Shell\\Inc\\Sing"...
0x180049f3a  mov     edx, 0C1h; void *
0x180049f3f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180049f45  mov     [rsp+58h+hKey], 0
0x180049f4e  mov     r9d, 20006h
0x180049f54  lea     rcx, [rsp+58h+hKey]
0x180049f59  call    ?GetSingletonSessionSubKey@details@SingletonHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@_W@4@0K@Z; SingletonHelpers::details::GetSingletonSessionSubKey(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,ulong)
0x180049f5e  nop
0x180049f5f  call    cs:__imp_GetCurrentProcessId
0x180049f65  mov     [rsp+58h+Data], eax
0x180049f69  mov     r9d, 4; dwType
0x180049f6f  mov     [rsp+58h+cbData], r9d; cbData
0x180049f74  lea     rax, [rsp+58h+Data]
0x180049f79  mov     [rsp+58h+lpData], rax; unsigned int
0x180049f7e  mov     r8, cs:off_180063400; lpValueName
0x180049f85  xor     edx, edx; lpSubKey
0x180049f87  mov     rcx, [rsp+58h+hKey]; hKey
0x180049f8c  call    cs:__imp_RegSetKeyValueW
0x180049f92  mov     rcx, [rsp+58h]; this
0x180049f97  test    eax, eax
0x180049f99  jz      short loc_180049FA9
0x180049f9b  mov     r9d, eax; char *
0x180049f9e  mov     edx, 0C7h; void *
0x180049fa3  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180049fa9  mov     r8, cs:off_1800633F0; lpValueName
0x180049fb0  xor     edx, edx; lpSubKey
0x180049fb2  mov     rcx, [rsp+58h+hKey]; hKey
0x180049fb7  call    cs:__imp_RegDeleteKeyValueW
0x180049fbd  nop
0x180049fbe  lea     rcx, [rsp+58h+hKey]
0x180049fc3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180049fc8  mov     rcx, [rsp+58h+var_18]
0x180049fcd  xor     rcx, rsp; StackCookie
0x180049fd0  call    __security_check_cookie
0x180049fd5  add     rsp, 58h
0x180049fd9  retn
```
