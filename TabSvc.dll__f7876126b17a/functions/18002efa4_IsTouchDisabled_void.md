# IsTouchDisabled(void)

- ea: `0x18002efa4`
- end: `0x18002f04e`
- name: `?IsTouchDisabled@@YA_NXZ`
- size: `170`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010fc0`
- `0x18001477c`

## callees

- `0x18002efa4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f03f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f03f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f017`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f017`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002efd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002efd8`

## pseudocode

```c
bool IsTouchDisabled(void)
{
  bool v0; // bl
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  v0 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\TabletPC", 0, 0x20019u, &hKey) )
  {
    Data = 0;
    Type = 4;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"TurnOffTouchInput", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && cbData == 4
      && Data )
    {
      v0 = Data == 1;
    }
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x18002efa4  push    rbp
0x18002efa6  push    rbx
0x18002efa7  mov     rbp, rsp
0x18002efaa  sub     rsp, 38h
0x18002efae  lea     rax, [rbp+hKey]
0x18002efb2  mov     [rbp+hKey], 0
0x18002efba  mov     r9d, 20019h; samDesired
0x18002efc0  mov     [rsp+38h+phkResult], rax; phkResult
0x18002efc5  xor     r8d, r8d; ulOptions
0x18002efc8  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\TabletPC"
0x18002efcf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002efd6  xor     bl, bl
0x18002efd8  call    cs:__imp_RegOpenKeyExW
0x18002efde  test    eax, eax
0x18002efe0  jnz     short loc_18002F045
0x18002efe2  mov     rcx, [rbp+hKey]; hKey
0x18002efe6  lea     r9, [rbp+Type]; lpType
0x18002efea  mov     [rbp+Data], eax
0x18002efed  lea     rdx, aTurnofftouchin; "TurnOffTouchInput"
0x18002eff4  lea     rax, [rbp+cbData]
0x18002eff8  mov     [rbp+Type], 4
0x18002efff  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002f004  xor     r8d, r8d; lpReserved
0x18002f007  lea     rax, [rbp+Data]
0x18002f00b  mov     [rbp+cbData], 4
0x18002f012  mov     [rsp+38h+phkResult], rax; lpData
0x18002f017  call    cs:__imp_RegQueryValueExW
0x18002f01d  test    eax, eax
0x18002f01f  jnz     short loc_18002F03B
0x18002f021  cmp     [rbp+Type], 4
0x18002f025  jnz     short loc_18002F03B
0x18002f027  cmp     [rbp+cbData], 4
0x18002f02b  jnz     short loc_18002F03B
0x18002f02d  mov     eax, [rbp+Data]
0x18002f030  test    eax, eax
0x18002f032  jz      short loc_18002F03B
0x18002f034  cmp     eax, 1
0x18002f037  jnz     short loc_18002F03B
0x18002f039  mov     bl, al
0x18002f03b  mov     rcx, [rbp+hKey]; hKey
0x18002f03f  call    cs:__imp_RegCloseKey
0x18002f045  mov     al, bl
0x18002f047  add     rsp, 38h
0x18002f04b  pop     rbx
0x18002f04c  pop     rbp
0x18002f04d  retn
```
