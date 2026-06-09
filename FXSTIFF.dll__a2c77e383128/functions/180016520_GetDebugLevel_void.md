# GetDebugLevel(void)

- ea: `0x180016520`
- end: `0x1800165c9`
- name: `?GetDebugLevel@@YAKXZ`
- size: `169`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016794`

## callees

- `0x180016520`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800165ba`
- `ADVAPI32!RegCloseKey` at `0x1800165ba`
- `ADVAPI32!RegOpenKeyExW` at `0x180016566`
- `ADVAPI32!RegOpenKeyExW` at `0x180016566`
- `ADVAPI32!RegQueryValueExW` at `0x18001659f`
- `ADVAPI32!RegQueryValueExW` at `0x18001659f`

## pseudocode

```c
__int64 GetDebugLevel(void)
{
  unsigned int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  Data = 0;
  cbData = 0;
  Type = 0;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Client", 0, 0x20019u, &hKey) )
    return 0;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"DebugLevel", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
    Data = 0;
  RegCloseKey(hKey);
  return Data;
}

```

## disassembly

```asm
0x180016520  push    rbp
0x180016522  mov     rbp, rsp
0x180016525  sub     rsp, 30h
0x180016529  lea     rax, [rbp+hKey]
0x18001652d  mov     [rbp+Data], 0
0x180016534  mov     r9d, 20019h; samDesired
0x18001653a  mov     [rsp+30h+phkResult], rax; phkResult
0x18001653f  xor     r8d, r8d; ulOptions
0x180016542  mov     [rbp+cbData], 0
0x180016549  lea     rdx, SubKey; "Software\\Microsoft\\Fax\\Client"
0x180016550  mov     [rbp+Type], 0
0x180016557  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001655e  mov     [rbp+hKey], 0
0x180016566  call    cs:__imp_RegOpenKeyExW
0x18001656c  test    eax, eax
0x18001656e  jz      short loc_180016574
0x180016570  xor     eax, eax
0x180016572  jmp     short loc_1800165C3
0x180016574  mov     rcx, [rbp+hKey]; hKey
0x180016578  lea     rax, [rbp+cbData]
0x18001657c  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180016581  lea     r9, [rbp+Type]; lpType
0x180016585  lea     rax, [rbp+Data]
0x180016589  mov     [rbp+cbData], 4
0x180016590  xor     r8d, r8d; lpReserved
0x180016593  mov     [rsp+30h+phkResult], rax; lpData
0x180016598  lea     rdx, aDebuglevel; "DebugLevel"
0x18001659f  call    cs:__imp_RegQueryValueExW
0x1800165a5  test    eax, eax
0x1800165a7  jnz     short loc_1800165AF
0x1800165a9  cmp     [rbp+Type], 4
0x1800165ad  jz      short loc_1800165B6
0x1800165af  mov     [rbp+Data], 0
0x1800165b6  mov     rcx, [rbp+hKey]; hKey
0x1800165ba  call    cs:__imp_RegCloseKey
0x1800165c0  mov     eax, [rbp+Data]
0x1800165c3  add     rsp, 30h
0x1800165c7  pop     rbp
0x1800165c8  retn
```
