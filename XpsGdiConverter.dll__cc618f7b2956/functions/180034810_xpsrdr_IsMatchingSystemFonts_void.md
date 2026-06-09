# xpsrdr::IsMatchingSystemFonts(void)

- ea: `0x180034810`
- end: `0x180034898`
- name: `?IsMatchingSystemFonts@xpsrdr@@YA_NXZ`
- size: `136`
- prototype: `bool __fastcall(xpsrdr *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003c42c`

## callees

- `0x180034810`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18003487a`
- `ADVAPI32!RegQueryValueExW` at `0x18003487a`
- `ADVAPI32!RegOpenKeyExW` at `0x180034842`
- `ADVAPI32!RegOpenKeyExW` at `0x180034842`
- `ADVAPI32!RegCloseKey` at `0x180034885`
- `ADVAPI32!RegCloseKey` at `0x180034885`

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
0x180034810  mov     r11, rsp
0x180034813  sub     rsp, 38h
0x180034817  mov     r9d, 1; samDesired
0x18003481d  mov     qword ptr [r11+18h], 0
0x180034825  lea     rax, [r11+18h]
0x180034829  mov     [r11+8], r9d
0x18003482d  xor     r8d, r8d; ulOptions
0x180034830  mov     [r11-18h], rax
0x180034834  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x18003483b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034842  call    cs:__imp_RegOpenKeyExW
0x180034848  test    eax, eax
0x18003484a  jnz     short loc_18003488B
0x18003484c  mov     rcx, [rsp+38h+hKey]; hKey
0x180034851  lea     rax, [rsp+38h+cbData]
0x180034856  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18003485b  lea     rdx, ValueName; "XpsRasMatchSysFonts"
0x180034862  lea     rax, [rsp+38h+Data]
0x180034867  mov     [rsp+38h+cbData], 4
0x18003486f  xor     r9d, r9d; lpType
0x180034872  mov     [rsp+38h+lpData], rax; lpData
0x180034877  xor     r8d, r8d; lpReserved
0x18003487a  call    cs:__imp_RegQueryValueExW
0x180034880  mov     rcx, [rsp+38h+hKey]; hKey
0x180034885  call    cs:__imp_RegCloseKey
0x18003488b  cmp     [rsp+38h+Data], 0
0x180034890  setnz   al
0x180034893  add     rsp, 38h
0x180034897  retn
```
