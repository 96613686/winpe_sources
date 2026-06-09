# GetDebugLevel(void)

- ea: `0x180017230`
- end: `0x1800172ec`
- name: `?GetDebugLevel@@YAKXZ`
- size: `188`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800174d8`

## callees

- `0x180017230`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800172d6`
- `ADVAPI32!RegCloseKey` at `0x1800172d6`
- `ADVAPI32!RegOpenKeyExW` at `0x180017276`
- `ADVAPI32!RegOpenKeyExW` at `0x180017276`
- `ADVAPI32!RegQueryValueExW` at `0x1800172b5`
- `ADVAPI32!RegQueryValueExW` at `0x1800172b5`

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
0x180017230  push    rbp
0x180017232  mov     rbp, rsp
0x180017235  sub     rsp, 30h
0x180017239  lea     rax, [rbp+hKey]
0x18001723d  mov     [rbp+Data], 0
0x180017244  mov     r9d, 20019h; samDesired
0x18001724a  mov     [rsp+30h+phkResult], rax; phkResult
0x18001724f  xor     r8d, r8d; ulOptions
0x180017252  mov     [rbp+cbData], 0
0x180017259  lea     rdx, SubKey; "Software\\Microsoft\\Fax\\Client"
0x180017260  mov     [rbp+Type], 0
0x180017267  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001726e  mov     [rbp+hKey], 0
0x180017276  call    cs:__imp_RegOpenKeyExW
0x18001727d  nop     dword ptr [rax+rax+00h]
0x180017282  test    eax, eax
0x180017284  jz      short loc_18001728A
0x180017286  xor     eax, eax
0x180017288  jmp     short loc_1800172E5
0x18001728a  mov     rcx, [rbp+hKey]; hKey
0x18001728e  lea     rax, [rbp+cbData]
0x180017292  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180017297  lea     r9, [rbp+Type]; lpType
0x18001729b  lea     rax, [rbp+Data]
0x18001729f  mov     [rbp+cbData], 4
0x1800172a6  xor     r8d, r8d; lpReserved
0x1800172a9  mov     [rsp+30h+phkResult], rax; lpData
0x1800172ae  lea     rdx, aDebuglevel; "DebugLevel"
0x1800172b5  call    cs:__imp_RegQueryValueExW
0x1800172bc  nop     dword ptr [rax+rax+00h]
0x1800172c1  test    eax, eax
0x1800172c3  jnz     short loc_1800172CB
0x1800172c5  cmp     [rbp+Type], 4
0x1800172c9  jz      short loc_1800172D2
0x1800172cb  mov     [rbp+Data], 0
0x1800172d2  mov     rcx, [rbp+hKey]; hKey
0x1800172d6  call    cs:__imp_RegCloseKey
0x1800172dd  nop     dword ptr [rax+rax+00h]
0x1800172e2  mov     eax, [rbp+Data]
0x1800172e5  add     rsp, 30h
0x1800172e9  pop     rbp
0x1800172ea  retn
```
