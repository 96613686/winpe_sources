# UserInsights::SetRegistryValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar *,ulong)

- ea: `0x180278588`
- end: `0x1802786e5`
- name: `?SetRegistryValue@UserInsights@@AEAA_NPEAUHKEY__@@PEBG1KPEAEK@Z`
- size: `349`
- prototype: `bool __fastcall(UserInsights *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, BYTE *lpData, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180278274`

## callees

- `0x1800775e8`
- `0x1800ce2c4`
- `0x1800ce404`
- `0x18013bad0`
- `0x180277b84`
- `0x180277f5c`
- `0x180278588`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18027869b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18027869b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802786aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802786aa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180278672`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180278672`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180278615`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180278615`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall UserInsights::SetRegistryValue(
        UserInsights *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        BYTE *lpData)
{
  bool v6; // bl
  __int64 v7; // r8
  const WCHAR *v8; // rax
  HKEY phkResult; // [rsp+50h] [rbp-21h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-11h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-9h] BYREF
  _BYTE v14[32]; // [rsp+80h] [rbp+Fh] BYREF

  v6 = 0;
  phkResult = 0;
  hKey = 0;
  std::wstring::wstring(v14, a2, this, a4);
  InsightsRegistryPath(
    -2147483647,
    (unsigned int)L"Software\\Microsoft\\Input\\TypingInsights",
    *(_QWORD *)(v7 + 48),
    (unsigned int)&hKey,
    (__int64)v14);
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  SecurityDescriptor = 0;
  ConvertStringSecurityDescriptorToSecurityDescriptorW(
    L"D:(A;CIOI;KRKW;;;SY)(A;CIOI;KRKW;;;BU)(A;CIOI;KRKW;;;AU)(A;CIOI;KRKW;;;AC)",
    1u,
    &SecurityDescriptor,
    0);
  SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
  SecurityAttributes.bInheritHandle = 0;
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
  if ( !RegCreateKeyExW(hKey, v8, 0, 0, 0, 0x20006u, &SecurityAttributes, &phkResult, 0) )
  {
    v6 = RegSetValueExW(phkResult, L"Insights", 0, 3u, lpData, 0x1Cu) == 0;
    RegCloseKey(phkResult);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SecurityDescriptor);
  std::wstring::_Tidy_deallocate(v14);
  return v6;
}

```

## disassembly

```asm
0x180278588  mov     [rsp-8+arg_8], rbx
0x18027858d  mov     [rsp-8+arg_10], rdi
0x180278592  push    rbp
0x180278593  lea     rbp, [rsp-3Fh]
0x180278598  sub     rsp, 0B0h
0x18027859f  mov     rax, cs:__security_cookie
0x1802785a6  xor     rax, rsp
0x1802785a9  mov     [rbp+3Fh+var_10], rax
0x1802785ad  mov     r8, rcx
0x1802785b0  mov     rdi, [rbp+3Fh+lpData]
0x1802785b4  xor     bl, bl
0x1802785b6  mov     [rbp+3Fh+var_60], 0
0x1802785be  mov     [rbp+3Fh+hKey], 0
0x1802785c6  lea     rcx, [rbp+3Fh+var_30]
0x1802785ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1802785cf  lea     rcx, [rbp+3Fh+var_30]
0x1802785d3  mov     qword ptr [rsp+0B0h+dwOptions], rcx
0x1802785d8  lea     r9, [rbp+3Fh+hKey]
0x1802785dc  mov     r8, [r8+30h]
0x1802785e0  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Input\\TypingInsig"...
0x1802785e7  mov     rcx, 0FFFFFFFF80000001h
0x1802785ee  call    InsightsRegistryPath
0x1802785f3  xorps   xmm0, xmm0
0x1802785f6  xor     eax, eax
0x1802785f8  movups  xmmword ptr [rbp+3Fh+SecurityAttributes.nLength], xmm0
0x1802785fc  mov     qword ptr [rbp+3Fh+SecurityAttributes.bInheritHandle], rax
0x180278600  mov     [rbp+3Fh+SecurityDescriptor], rax
0x180278604  xor     r9d, r9d; SecurityDescriptorSize
0x180278607  lea     r8, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x18027860b  lea     edx, [rax+1]; StringSDRevision
0x18027860e  lea     rcx, StringSecurityDescriptor; "D:(A;CIOI;KRKW;;;SY)(A;CIOI;KRKW;;;BU)("...
0x180278615  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18027861b  mov     [rbp+3Fh+SecurityAttributes.nLength], 18h
0x180278622  mov     rax, [rbp+3Fh+SecurityDescriptor]
0x180278626  mov     [rbp+3Fh+SecurityAttributes.lpSecurityDescriptor], rax
0x18027862a  mov     [rbp+3Fh+SecurityAttributes.bInheritHandle], 0
0x180278631  lea     rcx, [rbp+3Fh+var_30]
0x180278635  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18027863a  mov     rdx, rax; lpSubKey
0x18027863d  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x180278646  lea     rax, [rbp+3Fh+var_60]
0x18027864a  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18027864f  lea     rax, [rbp+3Fh+SecurityAttributes]
0x180278653  mov     [rsp+0B0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180278658  mov     [rsp+0B0h+samDesired], 20006h; samDesired
0x180278660  mov     [rsp+0B0h+dwOptions], 0; dwOptions
0x180278668  xor     r9d, r9d; lpClass
0x18027866b  xor     r8d, r8d; Reserved
0x18027866e  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180278672  call    cs:__imp_RegCreateKeyExW
0x180278678  test    eax, eax
0x18027867a  jnz     short loc_1802786B0
0x18027867c  mov     [rsp+0B0h+samDesired], 1Ch; cbData
0x180278684  mov     qword ptr [rsp+0B0h+dwOptions], rdi; lpData
0x180278689  lea     r9d, [rax+3]; dwType
0x18027868d  xor     r8d, r8d; Reserved
0x180278690  lea     rdx, aInsights; "Insights"
0x180278697  mov     rcx, [rbp+3Fh+var_60]; hKey
0x18027869b  call    cs:__imp_RegSetValueExW
0x1802786a1  test    eax, eax
0x1802786a3  setz    bl
0x1802786a6  mov     rcx, [rbp+3Fh+var_60]; hKey
0x1802786aa  call    cs:__imp_RegCloseKey
0x1802786b0  lea     rcx, [rbp+3Fh+SecurityDescriptor]
0x1802786b4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1802786b9  lea     rcx, [rbp+3Fh+var_30]
0x1802786bd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802786c2  mov     al, bl
0x1802786c4  mov     rcx, [rbp+3Fh+var_10]
0x1802786c8  xor     rcx, rsp; StackCookie
0x1802786cb  call    __security_check_cookie
0x1802786d0  lea     r11, [rsp+0B0h+var_s0]
0x1802786d8  mov     rbx, [r11+18h]
0x1802786dc  mov     rdi, [r11+20h]
0x1802786e0  mov     rsp, r11
0x1802786e3  pop     rbp
0x1802786e4  retn
```
