# CWwanDeviceEnumerator::getDeviceInfo(void *,_GUID const &,_DO_DEVINFO_DATA &,bool *)

- ea: `0x18001aa1c`
- end: `0x18001ac15`
- name: `?getDeviceInfo@CWwanDeviceEnumerator@@CAKPEAXAEBU_GUID@@AEAU_DO_DEVINFO_DATA@@PEA_N@Z`
- size: `505`
- prototype: `unsigned int __fastcall(void *, const struct _GUID *, struct _DO_DEVINFO_DATA *, bool *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001ac1c`
- `0x180095630`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x180011698`
- `0x180011a58`
- `0x180012300`
- `0x180014f1c`
- `0x180015d6c`
- `0x18001aa1c`
- `0x1800c5d28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aac4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001ab4d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001ab4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aab8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aab8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ab29`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ab29`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18001aa6b`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18001aa6b`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18001aaa3`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18001aaa3`

## string_xrefs

- `0x18001aacc`: `DevObjOpenDevRegKey Failure %u`
- `0x18001ab6b`: `CLSIDFromString Failure %x`

## pseudocode

```c
__int64 __fastcall CWwanDeviceEnumerator::getDeviceInfo(
        void *a1,
        const struct _GUID *a2,
        struct _DO_DEVINFO_DATA *a3,
        bool *a4)
{
  unsigned int v8; // ebx
  unsigned int i; // r14d
  HKEY v10; // rdi
  HKEY v11; // rbx
  DWORD LastError; // eax
  const unsigned __int16 *v13; // r8
  HRESULT v14; // eax
  __int64 v15; // rax
  LPBYTE lpData; // [rsp+20h] [rbp-69h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-61h]
  HKEY hKey; // [rsp+30h] [rbp-59h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-51h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-4Dh] BYREF
  GUID pclsid; // [rsp+40h] [rbp-49h] BYREF
  OLECHAR Data[40]; // [rsp+50h] [rbp-39h] BYREF

  if ( a1 == (void *)-1LL )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v8 = 0;
  for ( i = 0; (unsigned int)DevObjEnumDeviceInfo(a1, i, a3); ++i )
  {
    tlx::unique_any<tlx::file_handle_traits>::unique_any<tlx::file_handle_traits>(&hKey);
    v10 = hKey;
    LODWORD(lpcbData) = 131097;
    LODWORD(lpData) = 2;
    hKey = (HKEY)DevObjOpenDevRegKey(a1, a3, 1);
    v11 = hKey;
    if ( v10 )
      RegCloseKey(v10);
    if ( v11 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      LastError = GetLastError();
      v8 = LastError;
      v13 = L"DevObjOpenDevRegKey Failure %u";
LABEL_9:
      WwanLog::Warning("CWwanDeviceEnumerator::getDeviceInfo", 0, v13, LastError, lpData, lpcbData);
      goto LABEL_21;
    }
    memset_0(Data, 0, sizeof(Data));
    cbData = 80;
    Type = 0;
    LastError = RegQueryValueExW(v11, L"NetCfgInstanceId", 0, &Type, (LPBYTE)Data, &cbData);
    v8 = LastError;
    if ( LastError )
    {
      v13 = L"RegQueryValueEx NetCfgInstanceId Failure %u";
      goto LABEL_9;
    }
    pclsid = 0;
    v14 = CLSIDFromString(Data, &pclsid);
    v8 = v14;
    if ( v14 >= 0 )
    {
      v15 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&pclsid.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&pclsid.Data1 )
        v15 = *(_QWORD *)a2->Data4 - *(_QWORD *)pclsid.Data4;
      if ( !v15 )
      {
        WwanLog::Info("CWwanDeviceEnumerator::getDeviceInfo", 0, L"Matching device found!");
        v8 = 0;
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
        goto LABEL_23;
      }
      v8 = 1168;
    }
    else
    {
      if ( (v14 & 0x1FFF0000) == 0x70000 )
        v8 = (unsigned __int16)v14;
      WwanLog::Warning("CWwanDeviceEnumerator::getDeviceInfo", 0, L"CLSIDFromString Failure %x", v8, lpData, lpcbData);
    }
LABEL_21:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
  }
  if ( v8 == 1168 )
  {
    WwanLog::Error("CWwanDeviceEnumerator::getDeviceInfo", 0, L"No matching device found!");
    return v8;
  }
LABEL_23:
  if ( a4 )
    *a4 = 0;
  return v8;
}

```

## disassembly

```asm
0x18001aa1c  mov     [rsp-8+arg_8], rbx
0x18001aa21  push    rbp
0x18001aa22  push    rsi
0x18001aa23  push    rdi
0x18001aa24  push    r12
0x18001aa26  push    r13
0x18001aa28  push    r14
0x18001aa2a  push    r15
0x18001aa2c  lea     rbp, [rsp-27h]
0x18001aa31  sub     rsp, 0B0h
0x18001aa38  mov     rax, cs:__security_cookie
0x18001aa3f  xor     rax, rsp
0x18001aa42  mov     [rbp+57h+var_40], rax
0x18001aa46  mov     rsi, r9
0x18001aa49  mov     r13, r8
0x18001aa4c  mov     r12, rdx
0x18001aa4f  mov     r15, rcx
0x18001aa52  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001aa56  jnz     short loc_18001AA5D
0x18001aa58  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001aa5d  xor     ebx, ebx
0x18001aa5f  xor     r14d, r14d
0x18001aa62  mov     r8, r13
0x18001aa65  mov     edx, r14d
0x18001aa68  mov     rcx, r15
0x18001aa6b  call    cs:__imp_DevObjEnumDeviceInfo
0x18001aa71  test    eax, eax
0x18001aa73  jz      loc_18001ABF6
0x18001aa79  lea     rcx, [rbp+57h+hKey]
0x18001aa7d  call    ??0?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::unique_any<tlx::file_handle_traits>(void)
0x18001aa82  mov     rdi, [rbp+57h+hKey]
0x18001aa86  xor     r9d, r9d
0x18001aa89  mov     dword ptr [rsp+0E0h+lpcbData], 20019h
0x18001aa91  mov     rdx, r13
0x18001aa94  mov     rcx, r15
0x18001aa97  mov     dword ptr [rsp+0E0h+lpData], 2
0x18001aa9f  lea     r8d, [r9+1]
0x18001aaa3  call    cs:__imp_DevObjOpenDevRegKey
0x18001aaa9  mov     [rbp+57h+hKey], rax
0x18001aaad  mov     rbx, rax
0x18001aab0  test    rdi, rdi
0x18001aab3  jz      short loc_18001AABE
0x18001aab5  mov     rcx, rdi; hKey
0x18001aab8  call    cs:__imp_RegCloseKey
0x18001aabe  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001aac2  jnz     short loc_18001AAE9
0x18001aac4  call    cs:__imp_GetLastError
0x18001aaca  mov     ebx, eax
0x18001aacc  lea     r8, aDevobjopendevr_1; "DevObjOpenDevRegKey Failure %u"
0x18001aad3  mov     r9d, eax
0x18001aad6  xor     edx, edx; struct _GUID *
0x18001aad8  lea     rcx, aCwwandeviceenu_6; "CWwanDeviceEnumerator::getDeviceInfo"
0x18001aadf  call    ?Warning@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Warning(char const *,_GUID const *,ushort const *,...)
0x18001aae4  jmp     loc_18001AB94
0x18001aae9  mov     edi, 50h ; 'P'
0x18001aaee  lea     rcx, [rbp+57h+Data]; void *
0x18001aaf2  mov     r8d, edi; Size
0x18001aaf5  xor     edx, edx; Val
0x18001aaf7  call    memset_0
0x18001aafc  lea     rax, [rbp+57h+cbData]
0x18001ab00  mov     [rbp+57h+cbData], edi
0x18001ab03  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x18001ab08  lea     r9, [rbp+57h+Type]; lpType
0x18001ab0c  lea     rax, [rbp+57h+Data]
0x18001ab10  mov     [rbp+57h+Type], 0
0x18001ab17  xor     r8d, r8d; lpReserved
0x18001ab1a  mov     [rsp+0E0h+lpData], rax; lpData
0x18001ab1f  lea     rdx, ValueName; "NetCfgInstanceId"
0x18001ab26  mov     rcx, rbx; hKey
0x18001ab29  call    cs:__imp_RegQueryValueExW
0x18001ab2f  mov     ebx, eax
0x18001ab31  test    eax, eax
0x18001ab33  jz      short loc_18001AB3E
0x18001ab35  lea     r8, aRegqueryvaluee_0; "RegQueryValueEx NetCfgInstanceId Failur"...
0x18001ab3c  jmp     short loc_18001AAD3
0x18001ab3e  xorps   xmm0, xmm0
0x18001ab41  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18001ab45  lea     rcx, [rbp+57h+Data]; lpsz
0x18001ab49  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18001ab4d  call    cs:__imp_CLSIDFromString
0x18001ab53  mov     ebx, eax
0x18001ab55  test    eax, eax
0x18001ab57  jns     short loc_18001AB77
0x18001ab59  and     eax, 1FFF0000h
0x18001ab5e  cmp     eax, 70000h
0x18001ab63  jnz     short loc_18001AB68
0x18001ab65  movzx   ebx, bx
0x18001ab68  mov     r9d, ebx
0x18001ab6b  lea     r8, aClsidfromstrin; "CLSIDFromString Failure %x"
0x18001ab72  jmp     loc_18001AAD6
0x18001ab77  mov     rax, [r12]
0x18001ab7b  sub     rax, qword ptr [rbp+57h+pclsid.Data1]
0x18001ab7f  jnz     short loc_18001AB8A
0x18001ab81  mov     rax, [r12+8]
0x18001ab86  sub     rax, qword ptr [rbp+57h+pclsid.Data4]
0x18001ab8a  test    rax, rax
0x18001ab8d  jz      short loc_18001ABA5
0x18001ab8f  mov     ebx, 490h
0x18001ab94  lea     rcx, [rbp+57h+hKey]
0x18001ab98  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001ab9d  inc     r14d
0x18001aba0  jmp     loc_18001AA62
0x18001aba5  lea     r8, aMatchingDevice; "Matching device found!"
0x18001abac  xor     edx, edx; struct _GUID *
0x18001abae  lea     rcx, aCwwandeviceenu_6; "CWwanDeviceEnumerator::getDeviceInfo"
0x18001abb5  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18001abba  lea     rcx, [rbp+57h+hKey]
0x18001abbe  xor     ebx, ebx
0x18001abc0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001abc5  test    rsi, rsi
0x18001abc8  jz      short loc_18001ABCD
0x18001abca  mov     byte ptr [rsi], 0
0x18001abcd  mov     eax, ebx
0x18001abcf  mov     rcx, [rbp+57h+var_40]
0x18001abd3  xor     rcx, rsp; StackCookie
0x18001abd6  call    __security_check_cookie
0x18001abdb  mov     rbx, [rsp+0E0h+arg_8]
0x18001abe3  add     rsp, 0B0h
0x18001abea  pop     r15
0x18001abec  pop     r14
0x18001abee  pop     r13
0x18001abf0  pop     r12
0x18001abf2  pop     rdi
0x18001abf3  pop     rsi
0x18001abf4  pop     rbp
0x18001abf5  retn
0x18001abf6  cmp     ebx, 490h
0x18001abfc  jnz     short loc_18001ABC5
0x18001abfe  lea     r8, aNoMatchingDevi; "No matching device found!"
0x18001ac05  xor     edx, edx; struct _GUID *
0x18001ac07  lea     rcx, aCwwandeviceenu_6; "CWwanDeviceEnumerator::getDeviceInfo"
0x18001ac0e  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001ac13  jmp     short loc_18001ABCD
```
