# _anonymous_namespace_::CreateRegistryKeyWithAcl

- ea: `0x18002d2b0`
- end: `0x18002d44e`
- name: `_anonymous_namespace_::CreateRegistryKeyWithAcl`
- size: `414`
- prototype: `__int64 __fastcall(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002d628`
- `0x18002d6d8`

## callees

- `0x180003980`
- `0x180004344`
- `0x180006c10`
- `0x18000cf94`
- `0x18000ea34`
- `0x18002a130`
- `0x18002c4f4`
- `0x18002cef0`
- `0x18002cf50`
- `0x18002d2b0`
- `0x18002d454`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d3f8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d3f8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002d365`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002d365`

## string_xrefs

- `0x18002d32f`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\util.cpp`
- `0x18002d376`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\util.cpp`
- `0x18002d40c`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\util.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PHKEY __fastcall anonymous_namespace_::CreateRegistryKeyWithAcl(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey)
{
  _QWORD *CurrentUserSid; // rax
  int v7; // eax
  const char *v8; // r9
  unsigned int v9; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-E0h]
  DWORD dwDisposition; // [rsp+54h] [rbp-ACh] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-98h] BYREF
  PHKEY v17; // [rsp+80h] [rbp-80h]
  WCHAR StringSecurityDescriptor[512]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  v17 = phkResult;
  memset_0(StringSecurityDescriptor, 0, sizeof(StringSecurityDescriptor));
  CurrentUserSid = (_QWORD *)anonymous_namespace_::GetCurrentUserSid(&StringSid);
  v7 = StringCchPrintfW(
         StringSecurityDescriptor,
         0x200u,
         L"D:(A;OICI;KA;;;SY)(A;OICI;KA;;;BA)(A;OICI;KR;;;RC)(A;OICI;KR;;;AC)(A;OICI;KR;;;WD)(A;OICI;KR;;;S-1-15-3-1024-10"
          "65365936-1281604716-3511738428-1654721687-432734479-3232135806-4053264122-3456934681)(A;OICI;KA;;;%ws)",
         *CurrentUserSid);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\util.cpp",
      (const char *)(unsigned int)v7,
      dwOptions);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\util.cpp",
      v8);
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
  dwDisposition = 0;
  *phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  v9 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x20006u, &SecurityAttributes, phkResult, &dwDisposition);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\util.cpp",
      (const char *)v9,
      dwOptionsa);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
  return phkResult;
}

```

## disassembly

```asm
0x18002d2b0  mov     [rsp-8+arg_18], rbx
0x18002d2b5  push    rbp
0x18002d2b6  push    rsi
0x18002d2b7  push    rdi
0x18002d2b8  lea     rbp, [rsp-3A0h]
0x18002d2c0  sub     rsp, 4A0h
0x18002d2c7  mov     rax, cs:__security_cookie
0x18002d2ce  xor     rax, rsp
0x18002d2d1  mov     [rbp+3B0h+var_20], rax
0x18002d2d8  mov     rsi, r8
0x18002d2db  mov     rdi, rdx
0x18002d2de  mov     rbx, rcx
0x18002d2e1  mov     [rbp+3B0h+var_430], rcx
0x18002d2e5  mov     [rsp+4B0h+var_460], 0
0x18002d2ed  xor     edx, edx; Val
0x18002d2ef  mov     r8d, 400h; Size
0x18002d2f5  lea     rcx, [rbp+3B0h+StringSecurityDescriptor]; void *
0x18002d2f9  call    memset_0
0x18002d2fe  lea     rcx, [rsp+4B0h+StringSid]; StringSid
0x18002d303  call    _anonymous_namespace___GetCurrentUserSid
0x18002d308  nop
0x18002d309  mov     r9, [rax]
0x18002d30c  lea     r8, aDAOiciKaSyAOic; "D:(A;OICI;KA;;;SY)(A;OICI;KA;;;BA)(A;OI"...
0x18002d313  mov     edx, 200h; unsigned __int64
0x18002d318  lea     rcx, [rbp+3B0h+StringSecurityDescriptor]; unsigned __int16 *
0x18002d31c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002d321  test    eax, eax
0x18002d323  jns     short loc_18002D341
0x18002d325  mov     rcx, [rbp+3B8h]; this
0x18002d32c  mov     r9d, eax; char *
0x18002d32f  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002d336  mov     edx, 6Dh ; 'm'; void *
0x18002d33b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002d341  lea     rcx, [rsp+4B0h+StringSid]
0x18002d346  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d34b  nop
0x18002d34c  mov     [rsp+4B0h+SecurityDescriptor], 0
0x18002d355  xor     r9d, r9d; SecurityDescriptorSize
0x18002d358  lea     r8, [rsp+4B0h+SecurityDescriptor]; SecurityDescriptor
0x18002d35d  lea     edx, [r9+1]; StringSDRevision
0x18002d361  lea     rcx, [rbp+3B0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18002d365  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002d36b  mov     rcx, [rbp+3B8h]; this
0x18002d372  test    eax, eax
0x18002d374  jnz     short loc_18002D386
0x18002d376  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002d37d  lea     edx, [rax+74h]; void *
0x18002d380  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002d386  mov     qword ptr [rsp+4B0h+SecurityAttributes.nLength], 18h
0x18002d38f  mov     qword ptr [rsp+4B0h+SecurityAttributes.bInheritHandle], 0
0x18002d398  mov     rax, [rsp+4B0h+SecurityDescriptor]
0x18002d39d  mov     [rsp+4B0h+SecurityAttributes.lpSecurityDescriptor], rax
0x18002d3a2  mov     [rsp+4B0h+dwDisposition], 0
0x18002d3aa  mov     qword ptr [rbx], 0
0x18002d3b1  mov     [rsp+4B0h+var_460], 1
0x18002d3b9  xor     edx, edx
0x18002d3bb  mov     rcx, rbx
0x18002d3be  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002d3c3  lea     rax, [rsp+4B0h+dwDisposition]
0x18002d3c8  mov     [rsp+4B0h+lpdwDisposition], rax; lpdwDisposition
0x18002d3cd  mov     [rsp+4B0h+phkResult], rbx; phkResult
0x18002d3d2  lea     rax, [rsp+4B0h+SecurityAttributes]
0x18002d3d7  mov     [rsp+4B0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18002d3dc  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x18002d3e4  mov     [rsp+4B0h+dwOptions], 0; unsigned int
0x18002d3ec  xor     r9d, r9d; lpClass
0x18002d3ef  xor     r8d, r8d; Reserved
0x18002d3f2  mov     rdx, rsi; lpSubKey
0x18002d3f5  mov     rcx, rdi; hKey
0x18002d3f8  call    cs:__imp_RegCreateKeyExW
0x18002d3fe  mov     rcx, [rbp+3B8h]; this
0x18002d405  test    eax, eax
0x18002d407  jz      short loc_18002D41E
0x18002d409  mov     r9d, eax; char *
0x18002d40c  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002d413  mov     edx, 7Dh ; '}'; void *
0x18002d418  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002d41e  lea     rcx, [rsp+4B0h+SecurityDescriptor]
0x18002d423  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002d428  mov     rax, rbx
0x18002d42b  mov     rcx, [rbp+3B0h+var_20]
0x18002d432  xor     rcx, rsp; StackCookie
0x18002d435  call    __security_check_cookie
0x18002d43a  mov     rbx, [rsp+4B0h+arg_18]
0x18002d442  add     rsp, 4A0h
0x18002d449  pop     rdi
0x18002d44a  pop     rsi
0x18002d44b  pop     rbp
0x18002d44c  retn
```
