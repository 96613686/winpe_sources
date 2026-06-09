# xpsrdr::ShouldForceWarp(void)

- ea: `0x1800ab70c`
- end: `0x1800ab7a5`
- name: `?ShouldForceWarp@xpsrdr@@YA_NXZ`
- size: `153`
- prototype: `bool __fastcall(xpsrdr *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a9ffc`

## callees

- `0x1800ab4cc`
- `0x1800ab70c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab74b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab74b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab783`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab783`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab78e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab78e`

## pseudocode

```c
bool __fastcall xpsrdr::ShouldForceWarp(xpsrdr *this)
{
  int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  Data = 0;
  if ( !xpsrdr::IsWin8OrHigherSystem(this) )
    return 1;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows NT\\Printers", 0, 1u, &hKey) )
  {
    cbData = 4;
    RegQueryValueExW(hKey, L"ForceSoftwareRasterization", 0, 0, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
  }
  return Data != 0;
}

```

## disassembly

```asm
0x1800ab70c  sub     rsp, 38h
0x1800ab710  mov     [rsp+38h+Data], 0
0x1800ab718  call    ?IsWin8OrHigherSystem@xpsrdr@@YA_NXZ; xpsrdr::IsWin8OrHigherSystem(void)
0x1800ab71d  test    al, al
0x1800ab71f  jz      short loc_1800AB79E
0x1800ab721  lea     rax, [rsp+38h+hKey]
0x1800ab726  mov     [rsp+38h+hKey], 0
0x1800ab72f  mov     r9d, 1; samDesired
0x1800ab735  mov     [rsp+38h+phkResult], rax; phkResult
0x1800ab73a  xor     r8d, r8d; ulOptions
0x1800ab73d  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows "...
0x1800ab744  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ab74b  call    cs:__imp_RegOpenKeyExW
0x1800ab751  test    eax, eax
0x1800ab753  jnz     short loc_1800AB794
0x1800ab755  mov     rcx, [rsp+38h+hKey]; hKey
0x1800ab75a  lea     rax, [rsp+38h+cbData]
0x1800ab75f  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800ab764  lea     rdx, aForcesoftwarer; "ForceSoftwareRasterization"
0x1800ab76b  lea     rax, [rsp+38h+Data]
0x1800ab770  mov     [rsp+38h+cbData], 4
0x1800ab778  xor     r9d, r9d; lpType
0x1800ab77b  mov     [rsp+38h+phkResult], rax; lpData
0x1800ab780  xor     r8d, r8d; lpReserved
0x1800ab783  call    cs:__imp_RegQueryValueExW
0x1800ab789  mov     rcx, [rsp+38h+hKey]; hKey
0x1800ab78e  call    cs:__imp_RegCloseKey
0x1800ab794  cmp     [rsp+38h+Data], 0
0x1800ab799  setnz   al
0x1800ab79c  jmp     short loc_1800AB7A0
0x1800ab79e  mov     al, 1
0x1800ab7a0  add     rsp, 38h
0x1800ab7a4  retn
```
