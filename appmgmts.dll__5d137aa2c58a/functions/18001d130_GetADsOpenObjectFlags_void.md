# GetADsOpenObjectFlags(void)

- ea: `0x18001d130`
- end: `0x18001d22b`
- name: `?GetADsOpenObjectFlags@@YAKXZ`
- size: `251`
- prototype: `__int64(void)`
- caller_count: `21`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c258`
- `0x18001e8ac`
- `0x18001eec0`
- `0x18001f0b0`
- `0x18001f570`
- `0x18001f800`
- `0x18001fa10`
- `0x1800205f4`
- `0x180021dd0`
- `0x1800223b4`
- `0x180022610`
- `0x1800226f0`
- `0x180022870`
- `0x180022940`
- `0x180022e00`
- `0x180023050`
- `0x180023330`
- `0x18002371c`
- `0x180023bc0`
- `0x180023cdc`
- `0x180028190`

## callees

- `0x18001d130`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d15f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d15f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d1b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d1b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d1f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d1f9`

## string_xrefs

- `0x18001d1a7`: `ADsOpenObjectFlags`

## pseudocode

```c
__int64 GetADsOpenObjectFlags(void)
{
  char v0; // di
  LSTATUS v1; // eax
  signed int v2; // ebx
  HKEY v3; // rcx
  LSTATUS v4; // eax
  unsigned int v5; // ecx
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  v0 = 0;
  hKey = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\AdminDebug", 0, 1u, &hKey);
  v2 = v1;
  if ( v1 )
  {
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
  }
  else
  {
    v3 = hKey;
    if ( hKey )
    {
      Type = 0;
      Data = 0;
      cbData = 4;
      v4 = RegQueryValueExW(hKey, L"ADsOpenObjectFlags", 0, &Type, (LPBYTE)&Data, &cbData);
      v2 = v4;
      if ( v4 )
      {
        if ( v4 > 0 )
          v2 = (unsigned __int16)v4 | 0x80070000;
        v3 = hKey;
      }
      else
      {
        v3 = hKey;
        if ( Type - 4 <= 1 )
        {
          v0 = Data;
          v2 = 0;
        }
        else
        {
          v2 = -2147024895;
        }
      }
    }
    else
    {
      v2 = -2147467259;
    }
    if ( v3 )
      RegCloseKey(v3);
  }
  if ( v2 < 0 )
  {
    return 192;
  }
  else
  {
    v5 = (((v0 & 1) == 0) << 6) | 0x80;
    if ( (v0 & 2) != 0 )
      return (unsigned __int8)((v0 & 1) == 0) << 6;
  }
  return v5;
}

```

## disassembly

```asm
0x18001d130  push    rbp
0x18001d132  push    rbx
0x18001d133  push    rdi
0x18001d134  mov     rbp, rsp
0x18001d137  sub     rsp, 30h
0x18001d13b  xor     edi, edi
0x18001d13d  lea     rax, [rbp+hKey]
0x18001d141  xor     r8d, r8d; ulOptions
0x18001d144  mov     [rbp+hKey], rdi
0x18001d148  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001d14f  mov     [rsp+30h+phkResult], rax; phkResult
0x18001d154  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d15b  lea     r9d, [rdi+1]; samDesired
0x18001d15f  call    cs:__imp_RegOpenKeyExW
0x18001d165  mov     ebx, eax
0x18001d167  test    eax, eax
0x18001d169  jz      short loc_18001D17F
0x18001d16b  jle     loc_18001D1FF
0x18001d171  movzx   ebx, ax
0x18001d174  or      ebx, 80070000h
0x18001d17a  jmp     loc_18001D1FF
0x18001d17f  mov     rcx, [rbp+hKey]; hKey
0x18001d183  test    rcx, rcx
0x18001d186  jz      short loc_18001D1EF
0x18001d188  lea     rax, [rbp+cbData]
0x18001d18c  mov     [rbp+Type], edi
0x18001d18f  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001d194  lea     r9, [rbp+Type]; lpType
0x18001d198  lea     rax, [rbp+Data]
0x18001d19c  mov     [rbp+Data], edi
0x18001d19f  xor     r8d, r8d; lpReserved
0x18001d1a2  mov     [rsp+30h+phkResult], rax; lpData
0x18001d1a7  lea     rdx, aAdsopenobjectf; "ADsOpenObjectFlags"
0x18001d1ae  mov     [rbp+cbData], 4
0x18001d1b5  call    cs:__imp_RegQueryValueExW
0x18001d1bb  mov     ebx, eax
0x18001d1bd  test    eax, eax
0x18001d1bf  jnz     short loc_18001D1DE
0x18001d1c1  mov     eax, [rbp+Type]
0x18001d1c4  mov     rcx, [rbp+hKey]
0x18001d1c8  add     eax, 0FFFFFFFCh
0x18001d1cb  cmp     eax, 1
0x18001d1ce  jbe     short loc_18001D1D7
0x18001d1d0  mov     ebx, 80070001h
0x18001d1d5  jmp     short loc_18001D1F4
0x18001d1d7  mov     edi, [rbp+Data]
0x18001d1da  xor     ebx, ebx
0x18001d1dc  jmp     short loc_18001D1F4
0x18001d1de  jle     short loc_18001D1E9
0x18001d1e0  movzx   ebx, ax
0x18001d1e3  or      ebx, 80070000h
0x18001d1e9  mov     rcx, [rbp+hKey]
0x18001d1ed  jmp     short loc_18001D1F4
0x18001d1ef  mov     ebx, 80004005h
0x18001d1f4  test    rcx, rcx
0x18001d1f7  jz      short loc_18001D1FF
0x18001d1f9  call    cs:__imp_RegCloseKey
0x18001d1ff  test    ebx, ebx
0x18001d201  js      short loc_18001D21C
0x18001d203  mov     eax, edi
0x18001d205  not     eax
0x18001d207  and     eax, 1
0x18001d20a  shl     eax, 6
0x18001d20d  mov     ecx, eax
0x18001d20f  bts     ecx, 7
0x18001d213  test    dil, 2
0x18001d217  cmovnz  ecx, eax
0x18001d21a  jmp     short loc_18001D221
0x18001d21c  mov     ecx, 0C0h
0x18001d221  mov     eax, ecx
0x18001d223  add     rsp, 30h
0x18001d227  pop     rdi
0x18001d228  pop     rbx
0x18001d229  pop     rbp
0x18001d22a  retn
```
