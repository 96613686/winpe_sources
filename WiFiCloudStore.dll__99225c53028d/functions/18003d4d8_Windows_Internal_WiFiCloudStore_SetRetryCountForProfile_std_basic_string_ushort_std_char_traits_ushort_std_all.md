# Windows::Internal::WiFiCloudStore::SetRetryCountForProfile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_GUID const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,Windows::Internal::WiFiCloudStore::RetryStatistics const &)

- ea: `0x18003d4d8`
- end: `0x18003d5c4`
- name: `?SetRetryCountForProfile@WiFiCloudStore@Internal@Windows@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@W4ProfileModificationType@123@W4ProfileGeneration@123@AEBURetryStatistics@123@@Z`
- size: `236`
- prototype: `__int64 __fastcall(int, int, int, int, BYTE *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800360bc`
- `0x18003ee84`

## callees

- `0x1800079f0`
- `0x180007f90`
- `0x18000ac14`
- `0x1800111a8`
- `0x18001de24`
- `0x18001e1a0`
- `0x18002a030`
- `0x180031ce4`
- `0x18003d4d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003d565`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003d565`

## string_xrefs

- `0x18003d57a`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::WiFiCloudStore::SetRetryCountForProfile(
        __int64 a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        BYTE *a5)
{
  __int64 v6; // rax
  unsigned int v7; // eax
  unsigned int lpData; // [rsp+20h] [rbp-78h]
  HKEY hKey; // [rsp+30h] [rbp-68h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v12[32]; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken(&StringSid, a2);
  Windows::Internal::WiFiCloudStore::OpenProfileSyncRetryKeyForUser(&hKey);
  v6 = Windows::Internal::WiFiCloudStore::ProfileNameToCDSReferenceId(v12, a1);
  if ( *(_QWORD *)(v6 + 24) > 7u )
    v6 = *(_QWORD *)v6;
  v7 = RegSetValueExW(hKey, (LPCWSTR)v6, 0, 3u, a5, 0xCu);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
      (const char *)v7,
      lpData);
  std::wstring::~wstring((__int64)v12);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
}

```

## disassembly

```asm
0x18003d4d8  push    rbx
0x18003d4da  push    rbp
0x18003d4db  push    rsi
0x18003d4dc  push    rdi
0x18003d4dd  push    r14
0x18003d4df  sub     rsp, 70h
0x18003d4e3  mov     rax, cs:__security_cookie
0x18003d4ea  xor     rax, rsp
0x18003d4ed  mov     [rsp+98h+var_38], rax
0x18003d4f2  mov     esi, r9d
0x18003d4f5  mov     edi, r8d
0x18003d4f8  mov     rbx, rdx
0x18003d4fb  mov     rbp, rcx
0x18003d4fe  mov     r14, [rsp+98h+arg_20]
0x18003d506  lea     rcx, [rsp+98h+StringSid]; StringSid
0x18003d50b  call    ?GetUserSidStringFromToken@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAX@Z; Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken(void * const)
0x18003d510  nop
0x18003d511  mov     rax, [rsp+98h+StringSid]
0x18003d516  mov     [rsp+98h+lpData], rax
0x18003d51b  mov     r9d, esi
0x18003d51e  mov     r8d, edi
0x18003d521  mov     rdx, rbx
0x18003d524  lea     rcx, [rsp+98h+hKey]
0x18003d529  call    ?OpenProfileSyncRetryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@W4ProfileModificationType@123@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::OpenProfileSyncRetryKeyForUser(_GUID const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x18003d52e  nop
0x18003d52f  mov     rdx, rbp
0x18003d532  lea     rcx, [rsp+98h+var_58]
0x18003d537  call    ?ProfileNameToCDSReferenceId@WiFiCloudStore@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z; Windows::Internal::WiFiCloudStore::ProfileNameToCDSReferenceId(std::wstring const &)
0x18003d53c  nop
0x18003d53d  cmp     qword ptr [rax+18h], 7
0x18003d542  jbe     short loc_18003D547
0x18003d544  mov     rax, [rax]
0x18003d547  mov     [rsp+98h+cbData], 0Ch; cbData
0x18003d54f  mov     [rsp+98h+lpData], r14; unsigned int
0x18003d554  mov     r9d, 3; dwType
0x18003d55a  xor     r8d, r8d; Reserved
0x18003d55d  mov     rdx, rax; lpValueName
0x18003d560  mov     rcx, [rsp+98h+hKey]; hKey
0x18003d565  call    cs:__imp_RegSetValueExW
0x18003d56b  mov     rcx, [rsp+98h]; this
0x18003d573  test    eax, eax
0x18003d575  jz      short loc_18003D58C
0x18003d577  mov     r9d, eax; char *
0x18003d57a  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x18003d581  mov     edx, 8Bh; void *
0x18003d586  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003d58c  lea     rcx, [rsp+98h+var_58]
0x18003d591  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d596  nop
0x18003d597  lea     rcx, [rsp+98h+hKey]
0x18003d59c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003d5a1  nop
0x18003d5a2  lea     rcx, [rsp+98h+StringSid]
0x18003d5a7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d5ac  mov     rcx, [rsp+98h+var_38]
0x18003d5b1  xor     rcx, rsp; StackCookie
0x18003d5b4  call    __security_check_cookie
0x18003d5b9  add     rsp, 70h
0x18003d5bd  pop     r14
0x18003d5bf  pop     rdi
0x18003d5c0  pop     rsi
0x18003d5c1  pop     rbp
0x18003d5c2  pop     rbx
0x18003d5c3  retn
```
