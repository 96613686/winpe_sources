# xpsrdr::IsMatchingSystemFonts(void)

- ea: `0x1800ab0fc`
- end: `0x1800ab184`
- name: `?IsMatchingSystemFonts@xpsrdr@@YA_NXZ`
- size: `136`
- prototype: `bool __fastcall(xpsrdr *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ac0f4`

## callees

- `0x1800ab0fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab12e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab12e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab166`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab166`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab171`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab171`

## pseudocode

```c
bool __fastcall xpsrdr::IsMatchingSystemFonts(xpsrdr *this)
{
  int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  Data = 1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows NT\\Printers", 0, 1u, &hKey) )
  {
    cbData = 4;
    RegQueryValueExW(hKey, L"XpsRasMatchSysFonts", 0, 0, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
  }
  return Data != 0;
}

```

## disassembly

```asm
0x1800ab0fc  mov     r11, rsp
0x1800ab0ff  sub     rsp, 38h
0x1800ab103  mov     r9d, 1; samDesired
0x1800ab109  mov     qword ptr [r11+18h], 0
0x1800ab111  lea     rax, [r11+18h]
0x1800ab115  mov     [r11+8], r9d
0x1800ab119  xor     r8d, r8d; ulOptions
0x1800ab11c  mov     [r11-18h], rax
0x1800ab120  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows "...
0x1800ab127  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ab12e  call    cs:__imp_RegOpenKeyExW
0x1800ab134  test    eax, eax
0x1800ab136  jnz     short loc_1800AB177
0x1800ab138  mov     rcx, [rsp+38h+hKey]; hKey
0x1800ab13d  lea     rax, [rsp+38h+cbData]
0x1800ab142  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800ab147  lea     rdx, ValueName; "XpsRasMatchSysFonts"
0x1800ab14e  lea     rax, [rsp+38h+Data]
0x1800ab153  mov     [rsp+38h+cbData], 4
0x1800ab15b  xor     r9d, r9d; lpType
0x1800ab15e  mov     [rsp+38h+lpData], rax; lpData
0x1800ab163  xor     r8d, r8d; lpReserved
0x1800ab166  call    cs:__imp_RegQueryValueExW
0x1800ab16c  mov     rcx, [rsp+38h+hKey]; hKey
0x1800ab171  call    cs:__imp_RegCloseKey
0x1800ab177  cmp     [rsp+38h+Data], 0
0x1800ab17c  setnz   al
0x1800ab17f  add     rsp, 38h
0x1800ab183  retn
```
