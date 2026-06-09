# ReadKeyBool

- ea: `0x1800ea5e4`
- end: `0x1800ea679`
- name: `ReadKeyBool`
- size: `149`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800e9b00`

## callees

- `0x1800ea5e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ea618`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ea618`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ea650`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ea650`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ea666`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ea666`

## pseudocode

```c
bool __fastcall ReadKeyBool(LPCWSTR lpSubKey, LPCWSTR lpValueName)
{
  bool v3; // bl
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  int Data; // [rsp+60h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  v3 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey) )
  {
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, lpValueName, 0, 0, (LPBYTE)&Data, &cbData) )
      v3 = Data != 0;
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x1800ea5e4  mov     r11, rsp
0x1800ea5e7  mov     [r11+8], rbx
0x1800ea5eb  push    rdi
0x1800ea5ec  sub     rsp, 40h
0x1800ea5f0  mov     rdi, rdx
0x1800ea5f3  mov     qword ptr [r11-18h], 0
0x1800ea5fb  mov     rdx, rcx; lpSubKey
0x1800ea5fe  lea     rax, [r11-18h]
0x1800ea602  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ea609  mov     [r11-28h], rax
0x1800ea60d  mov     r9d, 20019h; samDesired
0x1800ea613  xor     r8d, r8d; ulOptions
0x1800ea616  xor     bl, bl
0x1800ea618  call    cs:__imp_RegOpenKeyExW
0x1800ea61e  test    eax, eax
0x1800ea620  jnz     short loc_1800EA66C
0x1800ea622  mov     rcx, [rsp+48h+hKey]; hKey
0x1800ea627  xor     r9d, r9d; lpType
0x1800ea62a  mov     [rsp+48h+Data], eax
0x1800ea62e  xor     r8d, r8d; lpReserved
0x1800ea631  lea     rax, [rsp+48h+cbData]
0x1800ea636  mov     [rsp+48h+cbData], 4
0x1800ea63e  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800ea643  mov     rdx, rdi; lpValueName
0x1800ea646  lea     rax, [rsp+48h+Data]
0x1800ea64b  mov     [rsp+48h+lpData], rax; lpData
0x1800ea650  call    cs:__imp_RegQueryValueExW
0x1800ea656  test    eax, eax
0x1800ea658  jnz     short loc_1800EA661
0x1800ea65a  cmp     [rsp+48h+Data], eax
0x1800ea65e  setnz   bl
0x1800ea661  mov     rcx, [rsp+48h+hKey]; hKey
0x1800ea666  call    cs:__imp_RegCloseKey
0x1800ea66c  mov     al, bl
0x1800ea66e  mov     rbx, [rsp+48h+arg_0]
0x1800ea673  add     rsp, 40h
0x1800ea677  pop     rdi
0x1800ea678  retn
```
