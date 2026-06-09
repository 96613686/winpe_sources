# GetDebugLevel(void)

- ea: `0x1400764b0`
- end: `0x14007656c`
- name: `?GetDebugLevel@@YAKXZ`
- size: `188`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140076758`

## callees

- `0x1400764b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140076556`
- `ADVAPI32!RegCloseKey` at `0x140076556`
- `ADVAPI32!RegOpenKeyExW` at `0x1400764f6`
- `ADVAPI32!RegOpenKeyExW` at `0x1400764f6`
- `ADVAPI32!RegQueryValueExW` at `0x140076535`
- `ADVAPI32!RegQueryValueExW` at `0x140076535`

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
0x1400764b0  push    rbp
0x1400764b2  mov     rbp, rsp
0x1400764b5  sub     rsp, 30h
0x1400764b9  lea     rax, [rbp+hKey]
0x1400764bd  mov     [rbp+Data], 0
0x1400764c4  mov     r9d, 20019h; samDesired
0x1400764ca  mov     [rsp+30h+phkResult], rax; phkResult
0x1400764cf  xor     r8d, r8d; ulOptions
0x1400764d2  mov     [rbp+cbData], 0
0x1400764d9  lea     rdx, SubKey; "Software\\Microsoft\\Fax\\Client"
0x1400764e0  mov     [rbp+Type], 0
0x1400764e7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400764ee  mov     [rbp+hKey], 0
0x1400764f6  call    cs:__imp_RegOpenKeyExW
0x1400764fd  nop     dword ptr [rax+rax+00h]
0x140076502  test    eax, eax
0x140076504  jz      short loc_14007650A
0x140076506  xor     eax, eax
0x140076508  jmp     short loc_140076565
0x14007650a  mov     rcx, [rbp+hKey]; hKey
0x14007650e  lea     rax, [rbp+cbData]
0x140076512  mov     [rsp+30h+lpcbData], rax; lpcbData
0x140076517  lea     r9, [rbp+Type]; lpType
0x14007651b  lea     rax, [rbp+Data]
0x14007651f  mov     [rbp+cbData], 4
0x140076526  xor     r8d, r8d; lpReserved
0x140076529  mov     [rsp+30h+phkResult], rax; lpData
0x14007652e  lea     rdx, aDebuglevel; "DebugLevel"
0x140076535  call    cs:__imp_RegQueryValueExW
0x14007653c  nop     dword ptr [rax+rax+00h]
0x140076541  test    eax, eax
0x140076543  jnz     short loc_14007654B
0x140076545  cmp     [rbp+Type], 4
0x140076549  jz      short loc_140076552
0x14007654b  mov     [rbp+Data], 0
0x140076552  mov     rcx, [rbp+hKey]; hKey
0x140076556  call    cs:__imp_RegCloseKey
0x14007655d  nop     dword ptr [rax+rax+00h]
0x140076562  mov     eax, [rbp+Data]
0x140076565  add     rsp, 30h
0x140076569  pop     rbp
0x14007656a  retn
```
