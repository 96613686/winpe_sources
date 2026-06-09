# _anonymous_namespace_::SetRegistryBoolValue

- ea: `0x18002db04`
- end: `0x18002dbd2`
- name: `_anonymous_namespace_::SetRegistryBoolValue`
- size: `206`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800210c4`
- `0x1800211c4`

## callees

- `0x180028fc0`
- `0x18002a130`
- `0x18002c4f4`
- `0x18002db04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002db4f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002db4f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002db96`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002db96`

## string_xrefs

- `0x18002db61`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\util.cpp`
- `0x18002dba8`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\util.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::SetRegistryBoolValue(__int64 a1, const WCHAR *a2, unsigned __int8 a3)
{
  int v3; // ebx
  unsigned int v5; // eax
  unsigned int v6; // eax
  __int64 result; // rax
  const char *v8; // r9
  unsigned int phkResult; // [rsp+20h] [rbp-18h]
  unsigned int phkResulta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  Data = a1;
  v3 = a3;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v5 = RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
         0,
         2u,
         &hKey);
  try
  {
    if ( v5 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\util.cpp",
        (const char *)v5,
        phkResult);
    LODWORD(Data) = v3;
    v6 = RegSetValueExW(hKey, a2, 0, 4u, (const BYTE *)&Data, 4u);
    if ( v6 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xA8,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\util.cpp",
        (const char *)v6,
        phkResulta);
    result = wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0xAA,
             (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\util.cpp",
             v8);
  }
  return result;
}

```

## disassembly

```asm
0x18002db04  mov     rax, rsp
0x18002db07  mov     [rax+10h], rbx
0x18002db0b  mov     [rax+8], rcx
0x18002db0f  push    rdi
0x18002db10  sub     rsp, 30h
0x18002db14  movzx   ebx, r8b
0x18002db18  mov     rdi, rdx
0x18002db1b  mov     qword ptr [rax+20h], 0
0x18002db23  xor     edx, edx
0x18002db25  lea     rcx, [rax+20h]
0x18002db29  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002db2e  lea     rax, [rsp+38h+hKey]
0x18002db33  mov     [rsp+38h+phkResult], rax; unsigned int
0x18002db38  mov     r9d, 2; samDesired
0x18002db3e  xor     r8d, r8d; ulOptions
0x18002db41  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002db48  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002db4f  call    cs:__imp_RegOpenKeyExW
0x18002db55  mov     rcx, [rsp+38h]; this
0x18002db5a  test    eax, eax
0x18002db5c  jz      short loc_18002DB72
0x18002db5e  mov     r9d, eax; char *
0x18002db61  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002db68  mov     edx, 0A0h; void *
0x18002db6d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002db72  mov     dword ptr [rsp+38h+Data], ebx
0x18002db76  mov     r9d, 4; dwType
0x18002db7c  mov     [rsp+38h+cbData], r9d; cbData
0x18002db81  lea     rax, [rsp+38h+Data]
0x18002db86  mov     [rsp+38h+phkResult], rax; unsigned int
0x18002db8b  xor     r8d, r8d; Reserved
0x18002db8e  mov     rdx, rdi; lpValueName
0x18002db91  mov     rcx, [rsp+38h+hKey]; hKey
0x18002db96  call    cs:__imp_RegSetValueExW
0x18002db9c  mov     rcx, [rsp+38h]; this
0x18002dba1  test    eax, eax
0x18002dba3  jz      short loc_18002DBBA
0x18002dba5  mov     r9d, eax; char *
0x18002dba8  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002dbaf  mov     edx, 0A8h; void *
0x18002dbb4  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002dbba  lea     rcx, [rsp+38h+hKey]
0x18002dbbf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002dbc4  nop
0x18002dbc5  jmp     short $+2
0x18002dbc7  mov     rbx, [rsp+38h+arg_8]
0x18002dbcc  add     rsp, 30h
0x18002dbd0  pop     rdi
0x18002dbd1  retn
```
