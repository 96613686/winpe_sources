# CSetLockScreenImageTask::s_SendChangeNotification(void)

- ea: `0x180036a6c`
- end: `0x180036c08`
- name: `?s_SendChangeNotification@CSetLockScreenImageTask@@SAXXZ`
- size: `412`
- prototype: `void(void)`
- caller_count: `6`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180036680`
- `0x1800368d0`
- `0x180036c10`
- `0x1800adeb0`
- `0x1800b472c`
- `0x1800b5460`

## callees

- `0x180009eec`
- `0x18000a910`
- `0x18000d2b8`
- `0x18001a3d0`
- `0x180036a6c`
- `0x180039e34`
- `0x18003aa84`
- `0x180050ba0`
- `0x1800b9bd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036ab9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036b29`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036ab9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036b29`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180036ba2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180036ba2`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180036b94`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180036b94`
- `ntdll!RtlPublishWnfStateData` at `0x180036bbd`
- `ntdll!RtlPublishWnfStateData` at `0x180036bbd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180036b7d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180036b7d`

## string_xrefs

- `0x180036b4f`: `LoggedOnUserSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void CSetLockScreenImageTask::s_SendChangeNotification(void)
{
  LSTATUS v0; // eax
  bool v1; // sf
  LSTATUS v2; // eax
  bool v3; // sf
  DWORD LengthSid; // eax
  PSID Sid; // [rsp+30h] [rbp-50h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR StringSid[3]; // [rsp+48h] [rbp-38h] BYREF
  WCHAR SubKey[8]; // [rsp+60h] [rbp-20h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\SessionData",
         0,
         8u,
         &hKey);
  v1 = v0 < 0;
  if ( v0 > 0 )
    v1 = 1;
  if ( !v1 && (int)StringCchPrintfW(SubKey, 8u, L"%d", NtCurrentPeb()->SessionId) >= 0 )
  {
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v2 = RegOpenKeyExW(hKey, SubKey, 0, 1u, &phkResult);
    v3 = v2 < 0;
    if ( v2 > 0 )
      v3 = 1;
    if ( !v3 )
    {
      memset(StringSid, 0, sizeof(StringSid));
      if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
                  StringSid,
                  phkResult,
                  L"LoggedOnUserSID") >= 0
        && StringSid[0]
        && *StringSid[0] )
      {
        Sid = 0;
        if ( ConvertStringSidToSidW(StringSid[0], &Sid) || (int)ResultFromKnownLastError() >= 0 )
        {
          if ( IsValidSid(Sid) )
          {
            LengthSid = GetLengthSid(Sid);
            RtlPublishWnfStateData(WNF_SHEL_LOCKSCREEN_IMAGE_CHANGED, 0, Sid, LengthSid, 0);
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(StringSid);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x180036a6c  mov     [rsp-8+arg_0], rbx
0x180036a71  push    rbp
0x180036a72  mov     rbp, rsp
0x180036a75  sub     rsp, 80h
0x180036a7c  mov     rax, cs:__security_cookie
0x180036a83  xor     rax, rsp
0x180036a86  mov     [rbp+var_10], rax
0x180036a8a  xor     ebx, ebx
0x180036a8c  mov     [rbp+hKey], rbx
0x180036a90  xor     edx, edx
0x180036a92  lea     rcx, [rbp+hKey]
0x180036a96  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180036a9b  lea     rax, [rbp+hKey]
0x180036a9f  mov     [rsp+80h+phkResult], rax; phkResult
0x180036aa4  lea     r9d, [rbx+8]; samDesired
0x180036aa8  xor     r8d, r8d; ulOptions
0x180036aab  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180036ab2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180036ab9  call    cs:__imp_RegOpenKeyExW
0x180036abf  test    eax, eax
0x180036ac1  jle     short loc_180036ACD
0x180036ac3  movzx   eax, ax
0x180036ac6  or      eax, 80070000h
0x180036acb  test    eax, eax
0x180036acd  js      loc_180036BE2
0x180036ad3  mov     r9, gs:60h
0x180036adc  mov     r9d, [r9+2C0h]
0x180036ae3  lea     r8, aD; "%d"
0x180036aea  mov     edx, 8; unsigned __int64
0x180036aef  lea     rcx, [rbp+SubKey]; unsigned __int16 *
0x180036af3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036af8  test    eax, eax
0x180036afa  js      loc_180036BE2
0x180036b00  mov     [rbp+var_48], rbx
0x180036b04  xor     edx, edx
0x180036b06  lea     rcx, [rbp+var_48]
0x180036b0a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180036b0f  lea     rax, [rbp+var_48]
0x180036b13  mov     [rsp+80h+phkResult], rax; phkResult
0x180036b18  mov     r9d, 1; samDesired
0x180036b1e  xor     r8d, r8d; ulOptions
0x180036b21  lea     rdx, [rbp+SubKey]; lpSubKey
0x180036b25  mov     rcx, [rbp+hKey]; hKey
0x180036b29  call    cs:__imp_RegOpenKeyExW
0x180036b2f  test    eax, eax
0x180036b31  jle     short loc_180036B3D
0x180036b33  movzx   eax, ax
0x180036b36  or      eax, 80070000h
0x180036b3b  test    eax, eax
0x180036b3d  js      loc_180036BD8
0x180036b43  mov     [rbp+StringSid], rbx
0x180036b47  mov     [rbp+var_30], rbx
0x180036b4b  mov     [rbp+var_28], rbx
0x180036b4f  lea     r8, aLoggedonusersi; "LoggedOnUserSID"
0x180036b56  mov     rdx, [rbp+var_48]
0x180036b5a  lea     rcx, [rbp+StringSid]
0x180036b5e  call    ?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x180036b63  test    eax, eax
0x180036b65  js      short loc_180036BCE
0x180036b67  mov     rcx, [rbp+StringSid]; StringSid
0x180036b6b  test    rcx, rcx
0x180036b6e  jz      short loc_180036BCE
0x180036b70  cmp     [rcx], bx
0x180036b73  jz      short loc_180036BCE
0x180036b75  mov     [rbp+Sid], rbx
0x180036b79  lea     rdx, [rbp+Sid]; Sid
0x180036b7d  call    cs:__imp_ConvertStringSidToSidW
0x180036b83  test    eax, eax
0x180036b85  jnz     short loc_180036B90
0x180036b87  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180036b8c  test    eax, eax
0x180036b8e  js      short loc_180036BC4
0x180036b90  mov     rcx, [rbp+Sid]; pSid
0x180036b94  call    cs:__imp_IsValidSid
0x180036b9a  test    eax, eax
0x180036b9c  jz      short loc_180036BC4
0x180036b9e  mov     rcx, [rbp+Sid]; pSid
0x180036ba2  call    cs:__imp_GetLengthSid
0x180036ba8  mov     [rsp+80h+phkResult], rbx
0x180036bad  mov     r9d, eax
0x180036bb0  mov     r8, [rbp+Sid]
0x180036bb4  xor     edx, edx
0x180036bb6  mov     rcx, cs:WNF_SHEL_LOCKSCREEN_IMAGE_CHANGED
0x180036bbd  call    cs:__imp_RtlPublishWnfStateData
0x180036bc3  nop
0x180036bc4  lea     rcx, [rbp+Sid]
0x180036bc8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180036bcd  nop
0x180036bce  lea     rcx, [rbp+StringSid]
0x180036bd2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180036bd7  nop
0x180036bd8  lea     rcx, [rbp+var_48]
0x180036bdc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180036be1  nop
0x180036be2  lea     rcx, [rbp+hKey]
0x180036be6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180036beb  mov     rcx, [rbp+var_10]
0x180036bef  xor     rcx, rsp; StackCookie
0x180036bf2  call    __security_check_cookie
0x180036bf7  mov     rbx, [rsp+80h+arg_0]
0x180036bff  add     rsp, 80h
0x180036c06  pop     rbp
0x180036c07  retn
```
