# DestroyWSearchIdleObject

- ea: `0x18000dec0`
- end: `0x18000dfe1`
- name: `DestroyWSearchIdleObject`
- size: `289`
- prototype: `LSTATUS __fastcall(struct IUnknown *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800149a0`

## callees

- `0x1800026f0`
- `0x18000dec0`
- `0x180011220`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dfa4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dfa4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000df76`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000df76`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000df24`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000df24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dfc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dfc3`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18000dfb8`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18000dfb8`

## string_xrefs

- `0x18000df67`: `MigPluginHandle`
- `0x18000dfaf`: `MigPluginHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LSTATUS __fastcall DestroyWSearchIdleObject(struct IUnknown *a1)
{
  LSTATUS result; // eax
  bool v2; // sf
  LSTATUS v3; // eax
  bool v4; // sf
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  *(_QWORD *)Data = 0;
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
    cbData = 8;
    Type = 0;
    v3 = RegQueryValueExW(hKey, L"MigPluginHandle", 0, &Type, Data, &cbData);
    v4 = v3 < 0;
    if ( v3 > 0 )
      v4 = 1;
    if ( !v4 && Type == 3 && cbData == 8 )
    {
      if ( *(_QWORD *)Data )
      {
        CloseHandle(*(HANDLE *)Data);
        SHDeleteValueW(hKey, 0, L"MigPluginHandle");
      }
    }
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x18000dec0  push    rbp
0x18000dec2  lea     rbp, [rsp-170h]
0x18000deca  sub     rsp, 270h
0x18000ded1  mov     rax, cs:__security_cookie
0x18000ded8  xor     rax, rsp
0x18000dedb  mov     [rbp+170h+var_10], rax
0x18000dee2  lea     r8, [rsp+270h+SubKey]
0x18000dee7  mov     [rsp+270h+hKey], 0
0x18000def0  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Search"
0x18000def7  mov     qword ptr [rsp+270h+Data], 0
0x18000df00  call    MapRegKeyPathIfNeeded
0x18000df05  lea     rax, [rsp+270h+hKey]
0x18000df0a  mov     r9d, 3; samDesired
0x18000df10  xor     r8d, r8d; ulOptions
0x18000df13  mov     [rsp+270h+phkResult], rax; phkResult
0x18000df18  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x18000df1d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000df24  call    cs:__imp_RegOpenKeyExW
0x18000df2a  test    eax, eax
0x18000df2c  jle     short loc_18000DF38
0x18000df2e  movzx   eax, ax
0x18000df31  or      eax, 80070000h
0x18000df36  test    eax, eax
0x18000df38  js      loc_18000DFC9
0x18000df3e  mov     rcx, [rsp+270h+hKey]; hKey
0x18000df43  lea     rax, [rsp+270h+cbData]
0x18000df48  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000df4d  lea     r9, [rsp+270h+Type]; lpType
0x18000df52  lea     rax, [rsp+270h+Data]
0x18000df57  mov     [rsp+270h+cbData], 8
0x18000df5f  xor     r8d, r8d; lpReserved
0x18000df62  mov     [rsp+270h+phkResult], rax; lpData
0x18000df67  lea     rdx, pszValue; "MigPluginHandle"
0x18000df6e  mov     [rsp+270h+Type], 0
0x18000df76  call    cs:__imp_RegQueryValueExW
0x18000df7c  test    eax, eax
0x18000df7e  jle     short loc_18000DF8A
0x18000df80  movzx   eax, ax
0x18000df83  or      eax, 80070000h
0x18000df88  test    eax, eax
0x18000df8a  js      short loc_18000DFBE
0x18000df8c  cmp     [rsp+270h+Type], 3
0x18000df91  jnz     short loc_18000DFBE
0x18000df93  cmp     [rsp+270h+cbData], 8
0x18000df98  jnz     short loc_18000DFBE
0x18000df9a  mov     rcx, qword ptr [rsp+270h+Data]; hObject
0x18000df9f  test    rcx, rcx
0x18000dfa2  jz      short loc_18000DFBE
0x18000dfa4  call    cs:__imp_CloseHandle
0x18000dfaa  mov     rcx, [rsp+270h+hKey]; hkey
0x18000dfaf  lea     r8, pszValue; "MigPluginHandle"
0x18000dfb6  xor     edx, edx; pszSubKey
0x18000dfb8  call    cs:__imp_SHDeleteValueW
0x18000dfbe  mov     rcx, [rsp+270h+hKey]; hKey
0x18000dfc3  call    cs:__imp_RegCloseKey
0x18000dfc9  mov     rcx, [rbp+170h+var_10]
0x18000dfd0  xor     rcx, rsp; StackCookie
0x18000dfd3  call    __security_check_cookie
0x18000dfd8  add     rsp, 270h
0x18000dfdf  pop     rbp
0x18000dfe0  retn
```
