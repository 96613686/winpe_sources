# QueryRegValue

- ea: `0x18002ff94`
- end: `0x180030036`
- name: `QueryRegValue`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18001fd50`

## callees

- `0x18002ff94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ffce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ffce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030027`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030027`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030010`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030010`

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
0x18002ff94  mov     r11, rsp
0x18002ff97  mov     [r11+18h], r8
0x18002ff9b  mov     [r11+10h], rdx
0x18002ff9f  mov     [r11+8], rcx
0x18002ffa3  push    rbx
0x18002ffa4  push    rsi
0x18002ffa5  sub     rsp, 38h
0x18002ffa9  xor     ebx, ebx
0x18002ffab  lea     rax, [r11+20h]
0x18002ffaf  xor     r8d, r8d; ulOptions
0x18002ffb2  mov     [r11+20h], rbx
0x18002ffb6  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x18002ffbd  mov     [r11-28h], rax
0x18002ffc1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ffc8  lea     esi, [rbx+1]
0x18002ffcb  mov     r9d, esi; samDesired
0x18002ffce  call    cs:__imp_RegOpenKeyExW
0x18002ffd4  test    eax, eax
0x18002ffd6  jnz     short loc_18003002D
0x18002ffd8  mov     rcx, [rsp+48h+hKey]; hKey
0x18002ffdd  lea     rax, [rsp+48h+cbData]
0x18002ffe2  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18002ffe7  lea     r9, [rsp+48h+Type]; lpType
0x18002ffec  lea     rax, [rsp+48h+Data]
0x18002fff1  mov     dword ptr [rsp+48h+Data], ebx
0x18002fff5  xor     r8d, r8d; lpReserved
0x18002fff8  mov     [rsp+48h+lpData], rax; lpData
0x18002fffd  lea     rdx, aUpgrade; "Upgrade"
0x180030004  mov     dword ptr [rsp+48h+cbData], 4
0x18003000c  mov     dword ptr [rsp+48h+Type], ebx
0x180030010  call    cs:__imp_RegQueryValueExW
0x180030016  test    eax, eax
0x180030018  jnz     short loc_180030022
0x18003001a  cmp     dword ptr [rsp+48h+Type], 4
0x18003001f  cmovz   ebx, esi
0x180030022  mov     rcx, [rsp+48h+hKey]; hKey
0x180030027  call    cs:__imp_RegCloseKey
0x18003002d  mov     eax, ebx
0x18003002f  add     rsp, 38h
0x180030033  pop     rsi
0x180030034  pop     rbx
0x180030035  retn
```
