# ?ClearDataForSingletonInstance@details@SingletonHelpers@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@_W@4@1@Z

- ea: `0x18000f838`
- end: `0x18000f8a9`
- name: `?ClearDataForSingletonInstance@details@SingletonHelpers@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@_W@4@1@Z`
- size: `113`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000e63c`
- `0x18004d4d0`

## callees

- `0x18000e224`
- `0x18000f838`
- `0x18001049c`
- `0x180013174`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18000f880`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18000f894`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18000f880`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18000f894`

## string_xrefs

- `0x18000f847`: `ShellCommon\Internal\Shell\Inc\SingletonHelpers.h`
- `0x18000f88b`: `CommunicationHWND`

## pseudocode

```c
__int64 __fastcall SingletonHelpers::details::ClearDataForSingletonInstance(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  HKEY hKey[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !*a1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xD1,
      (unsigned int)"ShellCommon\\Internal\\Shell\\Inc\\SingletonHelpers.h",
      a4);
  hKey[0] = 0;
  SingletonHelpers::details::GetSingletonSessionSubKey(hKey, a2, a3, 131078);
  RegDeleteKeyValueW(hKey[0], 0, L"ProcessId");
  RegDeleteKeyValueW(hKey[0], 0, L"CommunicationHWND");
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
}

```

## disassembly

```asm
0x18000f838  sub     rsp, 38h
0x18000f83c  cmp     qword ptr [rcx], 0
0x18000f840  jnz     short loc_18000F859
0x18000f842  mov     rcx, [rsp+38h]; this
0x18000f847  lea     r8, aShellcommonInt; "ShellCommon\\Internal\\Shell\\Inc\\Sing"...
0x18000f84e  mov     edx, 0D1h; void *
0x18000f853  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000f859  mov     r9d, 20006h
0x18000f85f  mov     [rsp+38h+hKey], 0
0x18000f868  lea     rcx, [rsp+38h+hKey]
0x18000f86d  call    ?GetSingletonSessionSubKey@details@SingletonHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@_W@4@0K@Z; SingletonHelpers::details::GetSingletonSessionSubKey(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,ulong)
0x18000f872  mov     r8, cs:lpValueName; lpValueName
0x18000f879  xor     edx, edx; lpSubKey
0x18000f87b  mov     rcx, [rsp+38h+hKey]; hKey
0x18000f880  call    cs:__imp_RegDeleteKeyValueW
0x18000f886  mov     rcx, [rsp+38h+hKey]; hKey
0x18000f88b  lea     r8, aCommunicationh; "CommunicationHWND"
0x18000f892  xor     edx, edx; lpSubKey
0x18000f894  call    cs:__imp_RegDeleteKeyValueW
0x18000f89a  lea     rcx, [rsp+38h+hKey]
0x18000f89f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000f8a4  add     rsp, 38h
0x18000f8a8  retn
```
