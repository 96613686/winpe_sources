# CWwanDeviceEnumerator::getParentFromDeviceInfo(void *,_DO_DEVINFO_DATA &,_GUID &)

- ea: `0x18001b328`
- end: `0x18001b5e8`
- name: `?getParentFromDeviceInfo@CWwanDeviceEnumerator@@AEBAKPEAXAEAU_DO_DEVINFO_DATA@@AEAU_GUID@@@Z`
- size: `704`
- prototype: `unsigned int __fastcall(CWwanDeviceEnumerator *__hidden this, void *, struct _DO_DEVINFO_DATA *, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001ac1c`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x180010e94`
- `0x180011a58`
- `0x180012300`
- `0x180019b1c`
- `0x180019d0c`
- `0x18001b328`
- `0x1800c5d28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b3b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b3b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4ef`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001b584`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001b584`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001b560`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001b560`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18001b3a3`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18001b413`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18001b3a3`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18001b413`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18001b4d4`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18001b4d4`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18001b476`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18001b476`

## string_xrefs

- `0x18001b49c`: `Failed to open parent device info [%u]`
- `0x18001b4f7`: `DevObjOpenDevRegKey for parent device Failure [%u]`
- `0x18001b5a2`: `CLSIDFromString Failure [%u]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWwanDeviceEnumerator::getParentFromDeviceInfo(
        CWwanDeviceEnumerator *this,
        void *a2,
        struct _DO_DEVINFO_DATA *a3,
        struct _GUID *a4)
{
  __int64 v7; // rbx
  DWORD LastError; // ebx
  DWORD v9; // eax
  __int64 v10; // rax
  DWORD v11; // eax
  const unsigned __int16 *v12; // r8
  HRESULT v13; // eax
  unsigned int v15; // [rsp+40h] [rbp-89h] BYREF
  int v16; // [rsp+44h] [rbp-85h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-81h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-79h] BYREF
  DWORD Type; // [rsp+54h] [rbp-75h] BYREF
  __int64 v20; // [rsp+58h] [rbp-71h] BYREF
  GUID pclsid; // [rsp+60h] [rbp-69h] BYREF
  _OWORD v22[3]; // [rsp+70h] [rbp-59h] BYREF
  OLECHAR Data[40]; // [rsp+A0h] [rbp-29h] BYREF

  v16 = 0;
  v15 = 0;
  *a4 = GUID_NULL;
  if ( (unsigned int)DevObjGetDeviceProperty(a2, a3, &DEVPKEY_Device_Parent, &v16, 0, 0, &v15, 0) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( GetLastError() != 122 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  std::make_unique<unsigned char [0],0>(&v20, v15);
  v7 = v20;
  if ( !v20 )
  {
    LastError = 14;
    goto LABEL_26;
  }
  if ( !(unsigned int)DevObjGetDeviceProperty(a2, a3, &DEVPKEY_Device_Parent, &v16, v20, v15, 0, 0) )
  {
    WwanLog::Error("CWwanDeviceEnumerator::getParentFromDeviceInfo", 0, L"Failed to get device property");
    LastError = GetLastError();
    goto LABEL_26;
  }
  if ( v16 != 18 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  memset(v22, 0, sizeof(v22));
  LODWORD(v22[0]) = 48;
  if ( (unsigned int)DevObjOpenDeviceInfo(a2, v7, 0, 0, v22) )
  {
    v10 = DevObjOpenDevRegKey(a2, v22, 1);
    std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(&hKey, v10);
    if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      v11 = GetLastError();
      LastError = v11;
      v12 = L"DevObjOpenDevRegKey for parent device Failure [%u]";
    }
    else
    {
      memset_0(Data, 0, sizeof(Data));
      cbData = 80;
      Type = 0;
      v11 = RegQueryValueExW(hKey, L"NetCfgInstanceId", 0, &Type, (LPBYTE)Data, &cbData);
      LastError = v11;
      if ( !v11 )
      {
        pclsid = 0;
        v13 = CLSIDFromString(Data, &pclsid);
        LastError = v13;
        if ( v13 >= 0 )
        {
          *a4 = pclsid;
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
          LastError = 0;
          goto LABEL_26;
        }
        if ( (v13 & 0x1FFF0000) == 0x70000 )
          LastError = (unsigned __int16)v13;
        WwanLog::Error("CWwanDeviceEnumerator::getParentFromDeviceInfo", 0, L"CLSIDFromString Failure [%u]", LastError);
        goto LABEL_18;
      }
      v12 = L"RegQueryValueEx NetCfgInstanceId Failure [%u]";
    }
    WwanLog::Error("CWwanDeviceEnumerator::getParentFromDeviceInfo", 0, v12, v11);
LABEL_18:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
    goto LABEL_26;
  }
  v9 = GetLastError();
  LastError = v9;
  if ( v9 == -536870399 )
    LastError = 1168;
  else
    WwanLog::Error("CWwanDeviceEnumerator::getParentFromDeviceInfo", 0, L"Failed to open parent device info [%u]", v9);
LABEL_26:
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v20);
  return LastError;
}

```

## disassembly

```asm
0x18001b328  push    rbp
0x18001b32a  push    rbx
0x18001b32b  push    rsi
0x18001b32c  push    rdi
0x18001b32d  push    r14
0x18001b32f  lea     rbp, [rsp-37h]
0x18001b334  sub     rsp, 100h
0x18001b33b  mov     rax, cs:__security_cookie
0x18001b342  xor     rax, rsp
0x18001b345  mov     [rbp+57h+var_30], rax
0x18001b349  mov     r14, r9
0x18001b34c  mov     rsi, r8
0x18001b34f  mov     rdi, rdx
0x18001b352  mov     [rsp+120h+var_DC], 0
0x18001b35a  mov     [rsp+120h+var_E0], 0
0x18001b362  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001b369  movdqu  xmmword ptr [r9], xmm0
0x18001b36e  mov     [rsp+120h+var_E8], 0
0x18001b376  lea     rax, [rsp+120h+var_E0]
0x18001b37b  mov     [rsp+120h+var_F0], rax
0x18001b380  mov     dword ptr [rsp+120h+lpcbData], 0
0x18001b388  mov     [rsp+120h+lpData], 0
0x18001b391  lea     r9, [rsp+120h+var_DC]
0x18001b396  lea     r8, DEVPKEY_Device_Parent
0x18001b39d  mov     rdx, rsi
0x18001b3a0  mov     rcx, rdi
0x18001b3a3  call    cs:__imp_DevObjGetDeviceProperty
0x18001b3a9  test    eax, eax
0x18001b3ab  jz      short loc_18001B3B2
0x18001b3ad  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001b3b2  call    cs:__imp_GetLastError
0x18001b3b8  cmp     eax, 7Ah ; 'z'
0x18001b3bb  jz      short loc_18001B3C2
0x18001b3bd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001b3c2  mov     edx, [rsp+120h+var_E0]
0x18001b3c6  lea     rcx, [rbp+57h+var_C8]
0x18001b3ca  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x18001b3cf  nop
0x18001b3d0  mov     rbx, [rbp+57h+var_C8]
0x18001b3d4  test    rbx, rbx
0x18001b3d7  jnz     short loc_18001B3E3
0x18001b3d9  mov     ebx, 0Eh
0x18001b3de  jmp     loc_18001B5C3
0x18001b3e3  mov     eax, [rsp+120h+var_E0]
0x18001b3e7  mov     [rsp+120h+var_E8], 0
0x18001b3ef  mov     [rsp+120h+var_F0], 0
0x18001b3f8  mov     dword ptr [rsp+120h+lpcbData], eax
0x18001b3fc  mov     [rsp+120h+lpData], rbx
0x18001b401  lea     r9, [rsp+120h+var_DC]
0x18001b406  lea     r8, DEVPKEY_Device_Parent
0x18001b40d  mov     rdx, rsi
0x18001b410  mov     rcx, rdi
0x18001b413  call    cs:__imp_DevObjGetDeviceProperty
0x18001b419  test    eax, eax
0x18001b41b  jnz     short loc_18001B43F
0x18001b41d  lea     r8, aFailedToGetDev; "Failed to get device property"
0x18001b424  xor     edx, edx; struct _GUID *
0x18001b426  lea     rcx, aCwwandeviceenu_7; "CWwanDeviceEnumerator::getParentFromDev"...
0x18001b42d  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001b432  call    cs:__imp_GetLastError
0x18001b438  mov     ebx, eax
0x18001b43a  jmp     loc_18001B5C3
0x18001b43f  cmp     [rsp+120h+var_DC], 12h
0x18001b444  jz      short loc_18001B44B
0x18001b446  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001b44b  xorps   xmm0, xmm0
0x18001b44e  movups  [rbp+57h+var_B0], xmm0
0x18001b452  movups  [rbp+57h+var_A0], xmm0
0x18001b456  movups  [rbp+57h+var_90], xmm0
0x18001b45a  mov     dword ptr [rbp+57h+var_B0], 30h ; '0'
0x18001b461  lea     rax, [rbp+57h+var_B0]
0x18001b465  mov     [rsp+120h+lpData], rax
0x18001b46a  xor     r9d, r9d
0x18001b46d  xor     r8d, r8d
0x18001b470  mov     rdx, rbx
0x18001b473  mov     rcx, rdi
0x18001b476  call    cs:__imp_DevObjOpenDeviceInfo
0x18001b47c  test    eax, eax
0x18001b47e  jnz     short loc_18001B4B6
0x18001b480  call    cs:__imp_GetLastError
0x18001b486  mov     ebx, eax
0x18001b488  cmp     eax, 0E0000201h
0x18001b48d  jnz     short loc_18001B499
0x18001b48f  mov     ebx, 490h
0x18001b494  jmp     loc_18001B5C3
0x18001b499  mov     r9d, eax
0x18001b49c  lea     r8, aFailedToOpenPa; "Failed to open parent device info [%u]"
0x18001b4a3  xor     edx, edx; struct _GUID *
0x18001b4a5  lea     rcx, aCwwandeviceenu_7; "CWwanDeviceEnumerator::getParentFromDev"...
0x18001b4ac  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001b4b1  jmp     loc_18001B5C3
0x18001b4b6  mov     dword ptr [rsp+120h+lpcbData], 20019h
0x18001b4be  mov     dword ptr [rsp+120h+lpData], 2
0x18001b4c6  xor     r9d, r9d
0x18001b4c9  lea     r8d, [r9+1]
0x18001b4cd  lea     rdx, [rbp+57h+var_B0]
0x18001b4d1  mov     rcx, rdi
0x18001b4d4  call    cs:__imp_DevObjOpenDevRegKey
0x18001b4da  mov     rdx, rax
0x18001b4dd  lea     rcx, [rsp+120h+hKey]
0x18001b4e2  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x18001b4e7  cmp     [rsp+120h+hKey], 0FFFFFFFFFFFFFFFFh
0x18001b4ed  jnz     short loc_18001B51E
0x18001b4ef  call    cs:__imp_GetLastError
0x18001b4f5  mov     ebx, eax
0x18001b4f7  lea     r8, aDevobjopendevr_0; "DevObjOpenDevRegKey for parent device F"...
0x18001b4fe  mov     r9d, eax
0x18001b501  xor     edx, edx; struct _GUID *
0x18001b503  lea     rcx, aCwwandeviceenu_7; "CWwanDeviceEnumerator::getParentFromDev"...
0x18001b50a  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18001b50f  lea     rcx, [rsp+120h+hKey]
0x18001b514  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001b519  jmp     loc_18001B5C3
0x18001b51e  mov     ebx, 50h ; 'P'
0x18001b523  mov     r8d, ebx; Size
0x18001b526  xor     edx, edx; Val
0x18001b528  lea     rcx, [rbp+57h+Data]; void *
0x18001b52c  call    memset_0
0x18001b531  mov     [rbp+57h+cbData], ebx
0x18001b534  mov     [rbp+57h+Type], 0
0x18001b53b  lea     rax, [rbp+57h+cbData]
0x18001b53f  mov     [rsp+120h+lpcbData], rax; lpcbData
0x18001b544  lea     rax, [rbp+57h+Data]
0x18001b548  mov     [rsp+120h+lpData], rax; lpData
0x18001b54d  lea     r9, [rbp+57h+Type]; lpType
0x18001b551  xor     r8d, r8d; lpReserved
0x18001b554  lea     rdx, ValueName; "NetCfgInstanceId"
0x18001b55b  mov     rcx, [rsp+120h+hKey]; hKey
0x18001b560  call    cs:__imp_RegQueryValueExW
0x18001b566  mov     ebx, eax
0x18001b568  test    eax, eax
0x18001b56a  jz      short loc_18001B575
0x18001b56c  lea     r8, aRegqueryvaluee_7; "RegQueryValueEx NetCfgInstanceId Failur"...
0x18001b573  jmp     short loc_18001B4FE
0x18001b575  xorps   xmm0, xmm0
0x18001b578  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18001b57c  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18001b580  lea     rcx, [rbp+57h+Data]; lpsz
0x18001b584  call    cs:__imp_CLSIDFromString
0x18001b58a  mov     ebx, eax
0x18001b58c  test    eax, eax
0x18001b58e  jns     short loc_18001B5AE
0x18001b590  and     eax, 1FFF0000h
0x18001b595  cmp     eax, 70000h
0x18001b59a  jnz     short loc_18001B59F
0x18001b59c  movzx   ebx, bx
0x18001b59f  mov     r9d, ebx
0x18001b5a2  lea     r8, aClsidfromstrin_0; "CLSIDFromString Failure [%u]"
0x18001b5a9  jmp     loc_18001B501
0x18001b5ae  movups  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x18001b5b2  movdqu  xmmword ptr [r14], xmm0
0x18001b5b7  lea     rcx, [rsp+120h+hKey]
0x18001b5bc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001b5c1  xor     ebx, ebx
0x18001b5c3  lea     rcx, [rbp+57h+var_C8]
0x18001b5c7  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x18001b5cc  mov     eax, ebx
0x18001b5ce  mov     rcx, [rbp+57h+var_30]
0x18001b5d2  xor     rcx, rsp; StackCookie
0x18001b5d5  call    __security_check_cookie
0x18001b5da  add     rsp, 100h
0x18001b5e1  pop     r14
0x18001b5e3  pop     rdi
0x18001b5e4  pop     rsi
0x18001b5e5  pop     rbx
0x18001b5e6  pop     rbp
0x18001b5e7  retn
```
