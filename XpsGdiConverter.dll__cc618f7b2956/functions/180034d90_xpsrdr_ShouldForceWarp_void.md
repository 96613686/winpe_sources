# xpsrdr::ShouldForceWarp(void)

- ea: `0x180034d90`
- end: `0x180034e29`
- name: `?ShouldForceWarp@xpsrdr@@YA_NXZ`
- size: `153`
- prototype: `bool __fastcall(xpsrdr *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800336ec`

## callees

- `0x180034bd8`
- `0x180034d90`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180034e07`
- `ADVAPI32!RegQueryValueExW` at `0x180034e07`
- `ADVAPI32!RegOpenKeyExW` at `0x180034dcf`
- `ADVAPI32!RegOpenKeyExW` at `0x180034dcf`
- `ADVAPI32!RegCloseKey` at `0x180034e12`
- `ADVAPI32!RegCloseKey` at `0x180034e12`

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
0x180034d90  sub     rsp, 38h
0x180034d94  mov     [rsp+38h+Data], 0
0x180034d9c  call    ?IsWin8OrHigherSystem@xpsrdr@@YA_NXZ; xpsrdr::IsWin8OrHigherSystem(void)
0x180034da1  test    al, al
0x180034da3  jz      short loc_180034E22
0x180034da5  lea     rax, [rsp+38h+hKey]
0x180034daa  mov     [rsp+38h+hKey], 0
0x180034db3  mov     r9d, 1; samDesired
0x180034db9  mov     [rsp+38h+phkResult], rax; phkResult
0x180034dbe  xor     r8d, r8d; ulOptions
0x180034dc1  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x180034dc8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034dcf  call    cs:__imp_RegOpenKeyExW
0x180034dd5  test    eax, eax
0x180034dd7  jnz     short loc_180034E18
0x180034dd9  mov     rcx, [rsp+38h+hKey]; hKey
0x180034dde  lea     rax, [rsp+38h+cbData]
0x180034de3  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180034de8  lea     rdx, aForcesoftwarer; "ForceSoftwareRasterization"
0x180034def  lea     rax, [rsp+38h+Data]
0x180034df4  mov     [rsp+38h+cbData], 4
0x180034dfc  xor     r9d, r9d; lpType
0x180034dff  mov     [rsp+38h+phkResult], rax; lpData
0x180034e04  xor     r8d, r8d; lpReserved
0x180034e07  call    cs:__imp_RegQueryValueExW
0x180034e0d  mov     rcx, [rsp+38h+hKey]; hKey
0x180034e12  call    cs:__imp_RegCloseKey
0x180034e18  cmp     [rsp+38h+Data], 0
0x180034e1d  setnz   al
0x180034e20  jmp     short loc_180034E24
0x180034e22  mov     al, 1
0x180034e24  add     rsp, 38h
0x180034e28  retn
```
