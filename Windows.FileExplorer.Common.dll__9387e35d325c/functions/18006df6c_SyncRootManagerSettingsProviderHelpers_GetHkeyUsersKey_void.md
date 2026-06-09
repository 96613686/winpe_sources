# SyncRootManagerSettingsProviderHelpers::GetHkeyUsersKey(void *)

- ea: `0x18006df6c`
- end: `0x18006e04c`
- name: `?GetHkeyUsersKey@SyncRootManagerSettingsProviderHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAX@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002a4e4`

## callees

- `0x180007900`
- `0x18001d320`
- `0x180020358`
- `0x180059c98`
- `0x18006b7d0`
- `0x18006df6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e005`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e005`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006dfab`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006dfab`

## string_xrefs

- `0x18006dfb5`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SyncRootManagerSettingsProviderHelpers.h`
- `0x18006e016`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SyncRootManagerSettingsProviderHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall SyncRootManagerSettingsProviderHelpers::GetHkeyUsersKey(_QWORD *a1, void *a2)
{
  const char *v4; // r9
  unsigned int v5; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  _QWORD *v8; // [rsp+38h] [rbp-18h] BYREF
  HKEY v9; // [rsp+40h] [rbp-10h] BYREF
  char v10; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  LPWSTR StringSid; // [rsp+80h] [rbp+30h] BYREF

  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( !ConvertSidToStringSidW(a2, &StringSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xC2,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SyncRootManagerSettingsProviderHelpers.h",
      v4);
  *a1 = 0;
  v8 = a1;
  v9 = 0;
  v10 = 1;
  v5 = RegOpenKeyExW(HKEY_USERS, StringSid, 0, 0x10109u, &v9);
  if ( v5 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xC4,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SyncRootManagerSettingsProviderHelpers.h",
      (const char *)v5,
      phkResult);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v8);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&StringSid);
  return a1;
}

```

## disassembly

```asm
0x18006df6c  mov     [rsp-18h+arg_8], rbx
0x18006df71  mov     [rsp-18h+arg_0], rcx
0x18006df76  push    rbp
0x18006df77  push    rsi
0x18006df78  push    rdi
0x18006df79  mov     rbp, rsp
0x18006df7c  sub     rsp, 50h
0x18006df80  mov     rbx, rdx
0x18006df83  mov     rdi, rcx
0x18006df86  mov     [rbp+var_20], 0
0x18006df8d  mov     [rbp+StringSid], 0
0x18006df95  xor     edx, edx
0x18006df97  lea     rcx, [rbp+StringSid]
0x18006df9b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006dfa0  mov     rsi, [rbp+18h]
0x18006dfa4  lea     rdx, [rbp+StringSid]; StringSid
0x18006dfa8  mov     rcx, rbx; Sid
0x18006dfab  call    cs:__imp_ConvertSidToStringSidW
0x18006dfb1  test    eax, eax
0x18006dfb3  jnz     short loc_18006DFCA
0x18006dfb5  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\fileexplorer\\windo"...
0x18006dfbc  mov     edx, 0C2h; void *
0x18006dfc1  mov     rcx, rsi; this
0x18006dfc4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18006dfca  mov     qword ptr [rdi], 0
0x18006dfd1  mov     [rbp+var_20], 1
0x18006dfd8  mov     [rbp+var_18], rdi
0x18006dfdc  mov     [rbp+var_10], 0
0x18006dfe4  mov     [rbp+var_8], 1
0x18006dfe8  lea     rax, [rbp+var_10]
0x18006dfec  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int
0x18006dff1  mov     r9d, 10109h; samDesired
0x18006dff7  xor     r8d, r8d; ulOptions
0x18006dffa  mov     rdx, [rbp+StringSid]; lpSubKey
0x18006dffe  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18006e005  call    cs:__imp_RegOpenKeyExW
0x18006e00b  mov     rcx, [rbp+18h]; this
0x18006e00f  test    eax, eax
0x18006e011  jz      short loc_18006E028
0x18006e013  mov     r9d, eax; char *
0x18006e016  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\fileexplorer\\windo"...
0x18006e01d  mov     edx, 0C4h; void *
0x18006e022  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18006e028  lea     rcx, [rbp+var_18]
0x18006e02c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18006e031  nop
0x18006e032  lea     rcx, [rbp+StringSid]; void *
0x18006e036  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18006e03b  mov     rax, rdi
0x18006e03e  mov     rbx, [rsp+50h+arg_8]
0x18006e043  add     rsp, 50h
0x18006e047  pop     rdi
0x18006e048  pop     rsi
0x18006e049  pop     rbp
0x18006e04a  retn
```
