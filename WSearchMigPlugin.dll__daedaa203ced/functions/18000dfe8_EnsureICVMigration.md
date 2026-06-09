# EnsureICVMigration

- ea: `0x18000dfe8`
- end: `0x18000e10b`
- name: `EnsureICVMigration`
- size: `291`
- prototype: `LSTATUS __fastcall(struct IUnknown *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014c50`

## callees

- `0x1800026f0`
- `0x18000dfe8`
- `0x180011220`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e094`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e094`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e053`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e053`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e0ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e0ed`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18000e0e2`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18000e0e2`

## pseudocode

```c
LSTATUS __fastcall EnsureICVMigration(struct IUnknown *a1)
{
  LSTATUS result; // eax
  bool v2; // sf
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD pvData[2]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  MapRegKeyPathIfNeeded(a1, (OLECHAR *)L"SOFTWARE\\Microsoft\\Windows Search", SubKey);
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 3u, &hKey);
  v2 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v2 = result < 0;
  }
  if ( !v2 )
  {
    if ( RegQueryValueExW(hKey, L"IndexerCatalogVersion", 0, &Type, 0, &cbData) == 2 )
    {
      cbData = 26;
      pvData[0] = *(_OWORD *)L"RebuildIndex";
      *(_OWORD *)((char *)pvData + 10) = *(_OWORD *)L"ldIndex";
      SHSetValueW(hKey, 0, L"IndexerCatalogVersion", 1u, pvData, 0x1Au);
    }
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x18000dfe8  push    rbp
0x18000dfea  lea     rbp, [rsp-190h]
0x18000dff2  sub     rsp, 290h
0x18000dff9  mov     rax, cs:__security_cookie
0x18000e000  xor     rax, rsp
0x18000e003  mov     [rbp+190h+var_10], rax
0x18000e00a  lea     r8, [rsp+290h+SubKey]
0x18000e00f  mov     [rsp+290h+hKey], 0
0x18000e018  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Search"
0x18000e01f  mov     [rsp+290h+Type], 0
0x18000e027  mov     [rsp+290h+cbData], 0
0x18000e02f  call    MapRegKeyPathIfNeeded
0x18000e034  lea     rax, [rsp+290h+hKey]
0x18000e039  mov     r9d, 3; samDesired
0x18000e03f  xor     r8d, r8d; ulOptions
0x18000e042  mov     [rsp+290h+phkResult], rax; phkResult
0x18000e047  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x18000e04c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e053  call    cs:__imp_RegOpenKeyExW
0x18000e059  test    eax, eax
0x18000e05b  jle     short loc_18000E067
0x18000e05d  movzx   eax, ax
0x18000e060  or      eax, 80070000h
0x18000e065  test    eax, eax
0x18000e067  js      loc_18000E0F3
0x18000e06d  mov     rcx, [rsp+290h+hKey]; hKey
0x18000e072  lea     rax, [rsp+290h+cbData]
0x18000e077  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18000e07c  lea     r9, [rsp+290h+Type]; lpType
0x18000e081  xor     r8d, r8d; lpReserved
0x18000e084  mov     [rsp+290h+phkResult], 0; lpData
0x18000e08d  lea     rdx, ValueName; "IndexerCatalogVersion"
0x18000e094  call    cs:__imp_RegQueryValueExW
0x18000e09a  cmp     eax, 2
0x18000e09d  jnz     short loc_18000E0E8
0x18000e09f  movups  xmm0, xmmword ptr cs:aRebuildindex; "RebuildIndex"
0x18000e0a6  mov     rcx, [rsp+290h+hKey]; hkey
0x18000e0ab  mov     eax, 1Ah
0x18000e0b0  movups  xmm1, xmmword ptr cs:aRebuildindex+0Ah; "ldIndex"
0x18000e0b7  mov     dword ptr [rsp+290h+lpcbData], eax; cbData
0x18000e0bb  lea     r8, ValueName; "IndexerCatalogVersion"
0x18000e0c2  mov     [rsp+290h+cbData], eax
0x18000e0c6  mov     r9d, 1; dwType
0x18000e0cc  lea     rax, [rsp+290h+pvData]
0x18000e0d1  xor     edx, edx; pszSubKey
0x18000e0d3  movups  xmmword ptr [rsp+290h+pvData], xmm0
0x18000e0d8  mov     [rsp+290h+phkResult], rax; pvData
0x18000e0dd  movups  xmmword ptr [rsp+290h+pvData+0Ah], xmm1
0x18000e0e2  call    cs:__imp_SHSetValueW
0x18000e0e8  mov     rcx, [rsp+290h+hKey]; hKey
0x18000e0ed  call    cs:__imp_RegCloseKey
0x18000e0f3  mov     rcx, [rbp+190h+var_10]
0x18000e0fa  xor     rcx, rsp; StackCookie
0x18000e0fd  call    __security_check_cookie
0x18000e102  add     rsp, 290h
0x18000e109  pop     rbp
0x18000e10a  retn
```
