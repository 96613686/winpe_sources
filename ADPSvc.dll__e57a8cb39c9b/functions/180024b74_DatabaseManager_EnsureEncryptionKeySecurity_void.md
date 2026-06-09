# DatabaseManager::EnsureEncryptionKeySecurity(void)

- ea: `0x180024b74`
- end: `0x180024d2e`
- name: `?EnsureEncryptionKeySecurity@DatabaseManager@@AEAAXXZ`
- size: `442`
- prototype: `void __fastcall(DatabaseManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800249b0`

## callees

- `0x18000f148`
- `0x180024b74`
- `0x180025558`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c27`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024be4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024be4`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180024ca9`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180024ca9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024ccd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024ccd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024c32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024cbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024c32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024cbd`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180024c80`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180024c80`

## string_xrefs

- `0x180024b83`: `DatabaseManager::EnsureEncryptionKeySecurity.`
- `0x180024bef`: `Registry key for storing database encryption keys already exists.`
- `0x180024b8f`: `Getting or creating the registry key that'll store the database encryption keys.`
- `0x180024c08`: `Getting the security descriptor from the ADPSvc object.`
- `0x180024ce3`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\databasemanager.cpp`
- `0x180024cfd`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\databasemanager.cpp`
- `0x180024d17`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\databasemanager.cpp`
- `0x180024c8e`: `Setting the security descriptor for the registry key that stores the database encryption keys.`

## pseudocode

```c
void __fastcall DatabaseManager::EnsureEncryptionKeySecurity(DatabaseManager *this)
{
  unsigned int v1; // eax
  HLOCAL v2; // rdi
  DWORD LastError; // ebx
  unsigned int v4; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-38h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HLOCAL hMem; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hMem = this;
  ADPTraceLoggingProvider::TraceLoggingInfo("DatabaseManager::EnsureEncryptionKeySecurity.");
  ADPTraceLoggingProvider::TraceLoggingInfo("Getting or creating the registry key that'll store the database encryption keys.");
  hKey = 0;
  v1 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\AggregatedDataPlatform\\Keys",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         0);
  if ( v1 == 5 )
  {
    ADPTraceLoggingProvider::TraceLoggingInfo("Registry key for storing database encryption keys already exists.");
  }
  else
  {
    if ( v1 )
      wil::details::in1diag3::_FailFast_Win32(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\databasemanager.cpp",
        (const char *)v1,
        dwOptions);
    hMem = 0;
    ADPTraceLoggingProvider::TraceLoggingInfo("Getting the security descriptor from the ADPSvc object.");
    v2 = hMem;
    if ( hMem )
    {
      LastError = GetLastError();
      LocalFree(v2);
      SetLastError(LastError);
    }
    hMem = 0;
    if ( GetNamedSecurityInfoW(L"ADPSvc", SE_SERVICE, 7u, 0, 0, 0, 0, &hMem) )
      wil::details::in1diag3::_FailFast_Win32(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\databasemanager.cpp",
        (const char *)1,
        dwOptionsa);
    ADPTraceLoggingProvider::TraceLoggingInfo("Setting the security descriptor for the registry key that stores the database encryption keys.");
    v4 = RegSetKeySecurity(hKey, 4u, hMem);
    if ( v4 )
      wil::details::in1diag3::_FailFast_Win32(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\databasemanager.cpp",
        (const char *)v4,
        dwOptionsa);
    if ( hMem )
      LocalFree(hMem);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180024b74  mov     [rsp+arg_10], rbx
0x180024b79  mov     [rsp+hMem], rcx
0x180024b7e  push    rdi
0x180024b7f  sub     rsp, 50h
0x180024b83  lea     rcx, aDatabasemanage; "DatabaseManager::EnsureEncryptionKeySec"...
0x180024b8a  call    ?TraceLoggingInfo@ADPTraceLoggingProvider@@SAXPEBDZZ; ADPTraceLoggingProvider::TraceLoggingInfo(char const *,...)
0x180024b8f  lea     rcx, aGettingOrCreat; "Getting or creating the registry key th"...
0x180024b96  call    ?TraceLoggingInfo@ADPTraceLoggingProvider@@SAXPEBDZZ; ADPTraceLoggingProvider::TraceLoggingInfo(char const *,...)
0x180024b9b  mov     rdx, cs:lpSubKey; lpSubKey
0x180024ba2  lea     rax, [rsp+58h+hKey]
0x180024ba7  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180024bb0  xor     r9d, r9d; lpClass
0x180024bb3  mov     [rsp+58h+phkResult], rax; phkResult
0x180024bb8  xor     r8d, r8d; Reserved
0x180024bbb  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180024bc4  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180024bcb  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180024bd3  mov     [rsp+58h+dwOptions], 0; unsigned int
0x180024bdb  mov     [rsp+58h+hKey], 0
0x180024be4  call    cs:__imp_RegCreateKeyExW
0x180024bea  cmp     eax, 5
0x180024bed  jnz     short loc_180024C00
0x180024bef  lea     rcx, aRegistryKeyFor; "Registry key for storing database encry"...
0x180024bf6  call    ?TraceLoggingInfo@ADPTraceLoggingProvider@@SAXPEBDZZ; ADPTraceLoggingProvider::TraceLoggingInfo(char const *,...)
0x180024bfb  jmp     loc_180024CC3
0x180024c00  test    eax, eax
0x180024c02  jnz     loc_180024CF8
0x180024c08  lea     rcx, aGettingTheSecu; "Getting the security descriptor from th"...
0x180024c0f  mov     [rsp+58h+hMem], 0
0x180024c18  call    ?TraceLoggingInfo@ADPTraceLoggingProvider@@SAXPEBDZZ; ADPTraceLoggingProvider::TraceLoggingInfo(char const *,...)
0x180024c1d  mov     rdi, [rsp+58h+hMem]
0x180024c22  test    rdi, rdi
0x180024c25  jz      short loc_180024C40
0x180024c27  call    cs:__imp_GetLastError
0x180024c2d  mov     rcx, rdi; hMem
0x180024c30  mov     ebx, eax
0x180024c32  call    cs:__imp_LocalFree
0x180024c38  mov     ecx, ebx; dwErrCode
0x180024c3a  call    cs:__imp_SetLastError
0x180024c40  xor     r9d, r9d; ppsidOwner
0x180024c43  mov     [rsp+58h+hMem], 0
0x180024c4c  lea     rax, [rsp+58h+hMem]
0x180024c51  mov     [rsp+58h+phkResult], rax; ppSecurityDescriptor
0x180024c56  lea     rcx, pObjectName; "ADPSvc"
0x180024c5d  mov     [rsp+58h+lpSecurityAttributes], 0; ppSacl
0x180024c66  lea     edx, [r9+2]; ObjectType
0x180024c6a  mov     qword ptr [rsp+58h+samDesired], 0; ppDacl
0x180024c73  lea     r8d, [r9+7]; SecurityInfo
0x180024c77  mov     qword ptr [rsp+58h+dwOptions], 0; unsigned int
0x180024c80  call    cs:__imp_GetNamedSecurityInfoW
0x180024c86  test    eax, eax
0x180024c88  jnz     loc_180024D12
0x180024c8e  lea     rcx, aSettingTheSecu; "Setting the security descriptor for the"...
0x180024c95  call    ?TraceLoggingInfo@ADPTraceLoggingProvider@@SAXPEBDZZ; ADPTraceLoggingProvider::TraceLoggingInfo(char const *,...)
0x180024c9a  mov     r8, [rsp+58h+hMem]; pSecurityDescriptor
0x180024c9f  mov     edx, 4; SecurityInformation
0x180024ca4  mov     rcx, [rsp+58h+hKey]; hKey
0x180024ca9  call    cs:__imp_RegSetKeySecurity
0x180024caf  test    eax, eax
0x180024cb1  jnz     short loc_180024CDE
0x180024cb3  mov     rcx, [rsp+58h+hMem]; hMem
0x180024cb8  test    rcx, rcx
0x180024cbb  jz      short loc_180024CC3
0x180024cbd  call    cs:__imp_LocalFree
0x180024cc3  mov     rcx, [rsp+58h+hKey]; hKey
0x180024cc8  test    rcx, rcx
0x180024ccb  jz      short loc_180024CD3
0x180024ccd  call    cs:__imp_RegCloseKey
0x180024cd3  mov     rbx, [rsp+58h+arg_10]
0x180024cd8  add     rsp, 50h
0x180024cdc  pop     rdi
0x180024cdd  retn
0x180024cde  mov     rcx, [rsp+58h]; this
0x180024ce3  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180024cea  mov     r9d, eax; char *
0x180024ced  mov     edx, 46h ; 'F'; void *
0x180024cf2  call    ?_FailFast_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_FailFast_Win32(void *,uint,char const *,ulong)
0x180024cf8  mov     rcx, [rsp+58h]; this
0x180024cfd  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180024d04  mov     r9d, eax; char *
0x180024d07  mov     edx, 30h ; '0'; void *
0x180024d0c  call    ?_FailFast_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_FailFast_Win32(void *,uint,char const *,ulong)
0x180024d12  mov     rcx, [rsp+58h]; this
0x180024d17  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180024d1e  mov     r9d, 1; char *
0x180024d24  lea     edx, [r9+3Fh]; void *
0x180024d28  call    ?_FailFast_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_FailFast_Win32(void *,uint,char const *,ulong)
```
