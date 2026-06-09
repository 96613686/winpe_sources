# QueryRegValue

- ea: `0x1800462c0`
- end: `0x180046362`
- name: `QueryRegValue`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180044900`

## callees

- `0x1800462c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800462fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800462fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046353`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046353`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004633c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004633c`

## pseudocode

```c
_BOOL8 __fastcall QueryRegValue(__int64 a1, __int64 a2, __int64 a3)
{
  BOOL v3; // ebx
  __int64 Data; // [rsp+50h] [rbp+8h] BYREF
  __int64 cbData; // [rsp+58h] [rbp+10h] BYREF
  __int64 Type; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  Type = a3;
  cbData = a2;
  Data = a1;
  v3 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 1u, &hKey) )
  {
    LODWORD(Data) = 0;
    LODWORD(cbData) = 4;
    LODWORD(Type) = 0;
    if ( !RegQueryValueExW(hKey, L"Upgrade", 0, (LPDWORD)&Type, (LPBYTE)&Data, (LPDWORD)&cbData) )
      v3 = Type == 4;
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x1800462c0  mov     r11, rsp
0x1800462c3  mov     [r11+18h], r8
0x1800462c7  mov     [r11+10h], rdx
0x1800462cb  mov     [r11+8], rcx
0x1800462cf  push    rbx
0x1800462d0  push    rsi
0x1800462d1  sub     rsp, 38h
0x1800462d5  xor     ebx, ebx
0x1800462d7  lea     rax, [r11+20h]
0x1800462db  xor     r8d, r8d; ulOptions
0x1800462de  mov     [r11+20h], rbx
0x1800462e2  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x1800462e9  mov     [r11-28h], rax
0x1800462ed  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800462f4  lea     esi, [rbx+1]
0x1800462f7  mov     r9d, esi; samDesired
0x1800462fa  call    cs:__imp_RegOpenKeyExW
0x180046300  test    eax, eax
0x180046302  jnz     short loc_180046359
0x180046304  mov     rcx, [rsp+48h+hKey]; hKey
0x180046309  lea     rax, [rsp+48h+cbData]
0x18004630e  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180046313  lea     r9, [rsp+48h+Type]; lpType
0x180046318  lea     rax, [rsp+48h+Data]
0x18004631d  mov     dword ptr [rsp+48h+Data], ebx
0x180046321  xor     r8d, r8d; lpReserved
0x180046324  mov     [rsp+48h+lpData], rax; lpData
0x180046329  lea     rdx, aUpgrade; "Upgrade"
0x180046330  mov     dword ptr [rsp+48h+cbData], 4
0x180046338  mov     dword ptr [rsp+48h+Type], ebx
0x18004633c  call    cs:__imp_RegQueryValueExW
0x180046342  test    eax, eax
0x180046344  jnz     short loc_18004634E
0x180046346  cmp     dword ptr [rsp+48h+Type], 4
0x18004634b  cmovz   ebx, esi
0x18004634e  mov     rcx, [rsp+48h+hKey]; hKey
0x180046353  call    cs:__imp_RegCloseKey
0x180046359  mov     eax, ebx
0x18004635b  add     rsp, 38h
0x18004635f  pop     rsi
0x180046360  pop     rbx
0x180046361  retn
```
