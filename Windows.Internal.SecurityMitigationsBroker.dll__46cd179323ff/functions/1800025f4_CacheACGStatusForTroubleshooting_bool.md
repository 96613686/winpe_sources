# CacheACGStatusForTroubleshooting(bool)

- ea: `0x1800025f4`
- end: `0x1800026ec`
- name: `?CacheACGStatusForTroubleshooting@@YAX_N@Z`
- size: `248`
- prototype: `void __fastcall(char)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002288`
- `0x180003060`

## callees

- `0x1800025f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800026e0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800026e0`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800025fc`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800025fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800026cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800026da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800026cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800026da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800026c4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800026c4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002672`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002672`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000268a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000268a`
- `USERENV!GetAppContainerRegistryLocation` at `0x18000261d`
- `USERENV!GetAppContainerRegistryLocation` at `0x18000261d`

## pseudocode

```c
void __fastcall CacheACGStatusForTroubleshooting(char a1)
{
  const WCHAR *v2; // rdx
  HKEY phkResult; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp+20h] BYREF

  if ( CoImpersonateClient() >= 0 )
  {
    hKey = 0;
    if ( (int)GetAppContainerRegistryLocation(131103, &hKey) >= 0 )
    {
      phkResult = 0;
      if ( !RegCreateKeyExW(hKey, L"ACGStatus", 0, 0, 1u, 0x2001Fu, 0, &phkResult, 0) )
      {
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v2 = L"ACGOnTimestamp";
        if ( !a1 )
          v2 = L"ACGOffTimestamp";
        RegSetValueExW(phkResult, v2, 0, 3u, (const BYTE *)&SystemTimeAsFileTime, 8u);
        RegCloseKey(phkResult);
      }
      RegCloseKey(hKey);
    }
    CoRevertToSelf();
  }
}

```

## disassembly

```asm
0x1800025f4  push    rbx
0x1800025f6  sub     rsp, 50h
0x1800025fa  mov     bl, cl
0x1800025fc  call    cs:__imp_CoImpersonateClient
0x180002602  test    eax, eax
0x180002604  js      loc_1800026E6
0x18000260a  lea     rdx, [rsp+58h+hKey]
0x18000260f  mov     [rsp+58h+hKey], 0
0x180002618  mov     ecx, 2001Fh
0x18000261d  call    cs:__imp_GetAppContainerRegistryLocation
0x180002623  test    eax, eax
0x180002625  js      loc_1800026E0
0x18000262b  mov     rcx, [rsp+58h+hKey]; hKey
0x180002630  lea     rax, [rsp+58h+arg_8]
0x180002635  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18000263e  lea     rdx, SubKey; "ACGStatus"
0x180002645  mov     [rsp+58h+phkResult], rax; phkResult
0x18000264a  xor     r9d, r9d; lpClass
0x18000264d  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180002656  xor     r8d, r8d; Reserved
0x180002659  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180002661  mov     [rsp+58h+dwOptions], 1; dwOptions
0x180002669  mov     [rsp+58h+arg_8], 0
0x180002672  call    cs:__imp_RegCreateKeyExW
0x180002678  test    eax, eax
0x18000267a  jnz     short loc_1800026D5
0x18000267c  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002681  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000268a  call    cs:__imp_GetSystemTimeAsFileTime
0x180002690  mov     rcx, [rsp+58h+arg_8]; hKey
0x180002695  lea     rax, ValueName; "ACGOffTimestamp"
0x18000269c  test    bl, bl
0x18000269e  mov     [rsp+58h+samDesired], 8; cbData
0x1800026a6  lea     rdx, aAcgontimestamp; "ACGOnTimestamp"
0x1800026ad  mov     r9d, 3; dwType
0x1800026b3  cmovz   rdx, rax; lpValueName
0x1800026b7  lea     rax, [rsp+58h+SystemTimeAsFileTime]
0x1800026bc  xor     r8d, r8d; Reserved
0x1800026bf  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800026c4  call    cs:__imp_RegSetValueExW
0x1800026ca  mov     rcx, [rsp+58h+arg_8]; hKey
0x1800026cf  call    cs:__imp_RegCloseKey
0x1800026d5  mov     rcx, [rsp+58h+hKey]; hKey
0x1800026da  call    cs:__imp_RegCloseKey
0x1800026e0  call    cs:__imp_CoRevertToSelf
0x1800026e6  add     rsp, 50h
0x1800026ea  pop     rbx
0x1800026eb  retn
```
