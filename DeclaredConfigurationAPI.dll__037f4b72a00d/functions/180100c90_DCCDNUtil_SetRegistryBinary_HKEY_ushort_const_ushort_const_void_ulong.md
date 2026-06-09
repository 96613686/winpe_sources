# DCCDNUtil_SetRegistryBinary(HKEY__ *,ushort const *,ushort const *,void *,ulong)

- ea: `0x180100c90`
- end: `0x180100e35`
- name: `?DCCDNUtil_SetRegistryBinary@@YAJPEAUHKEY__@@PEBG1PEAXK@Z`
- size: `421`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, void *, unsigned int)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18009c3e4`
- `0x18009d6dc`
- `0x1800b85c0`
- `0x1800bd94c`
- `0x1800d32a0`
- `0x1800e3758`
- `0x1800e82c0`

## callees

- `0x1800117dc`
- `0x180100c90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180100dd8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180100dd8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180100d9a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180100d9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180100d0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180100d0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180100e00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180100e18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180100e00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180100e18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180100d50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180100d50`

## pseudocode

```c
__int64 __fastcall DCCDNUtil_SetRegistryBinary(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const BYTE *a4,
        DWORD cbData)
{
  __int64 v8; // rdx
  int Key; // ebx
  int v10; // ebp
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  int v14; // [rsp+20h] [rbp-58h]
  HKEY hKey[2]; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  HKEY phkResult; // [rsp+80h] [rbp+8h] BYREF

  phkResult = a1;
  hKey[0] = 0;
  if ( !a1 )
  {
    v8 = 882;
LABEL_3:
    Key = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)0x80070057LL,
      v14);
    return (unsigned int)Key;
  }
  if ( !a4 )
  {
    v8 = 883;
    goto LABEL_3;
  }
  v10 = 0;
  if ( !a2 )
  {
    hKey[0] = a1;
LABEL_20:
    Key = 0;
    v12 = RegSetValueExW(a1, a3, 0, 3u, a4, cbData);
    if ( v12 )
    {
      if ( v12 > 0 )
        Key = (unsigned __int16)v12 | 0x80070000;
      else
        Key = v12;
    }
    if ( !a2 )
      goto LABEL_27;
    goto LABEL_25;
  }
  if ( a1 == HKEY_CURRENT_USER )
  {
    v11 = RegOpenCurrentUser(0x20106u, &phkResult);
    Key = v11;
    if ( v11 )
    {
      if ( v11 <= 0 )
        goto LABEL_25;
      Key = (unsigned __int16)v11;
      goto LABEL_11;
    }
    a1 = phkResult;
    v10 = 1;
  }
  Key = RegOpenKeyExW(a1, a2, 0, 0x20106u, hKey);
  if ( Key == 2 )
    Key = RegCreateKeyExW(phkResult, a2, 0, 0, 0, 0x20106u, 0, hKey, 0);
  if ( !Key )
  {
    a1 = hKey[0];
    goto LABEL_20;
  }
  if ( Key > 0 )
  {
    Key = (unsigned __int16)Key;
LABEL_11:
    Key |= 0x80070000;
  }
LABEL_25:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
LABEL_27:
  if ( v10 == 1 && phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x180100c90  mov     rax, rsp
0x180100c93  mov     [rax+10h], rbx
0x180100c97  mov     [rax+18h], rbp
0x180100c9b  mov     [rax+8], rcx
0x180100c9f  push    rsi
0x180100ca0  push    rdi
0x180100ca1  push    r14
0x180100ca3  sub     rsp, 60h
0x180100ca7  mov     qword ptr [rax-28h], 0
0x180100caf  mov     rsi, r9
0x180100cb2  mov     r14, r8
0x180100cb5  mov     rdi, rdx
0x180100cb8  test    rcx, rcx
0x180100cbb  jnz     short loc_180100CE0
0x180100cbd  mov     edx, 372h; void *
0x180100cc2  mov     rcx, [rsp+78h]; this
0x180100cc7  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x180100cce  mov     ebx, 80070057h
0x180100cd3  mov     r9d, ebx; char *
0x180100cd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180100cdb  jmp     loc_180100E1E
0x180100ce0  test    rsi, rsi
0x180100ce3  jnz     short loc_180100CEC
0x180100ce5  mov     edx, 373h
0x180100cea  jmp     short loc_180100CC2
0x180100cec  xor     ebp, ebp
0x180100cee  test    rdi, rdi
0x180100cf1  jz      loc_180100DB7
0x180100cf7  cmp     rcx, 0FFFFFFFF80000001h
0x180100cfe  jnz     short loc_180100D3A
0x180100d00  lea     rdx, [rsp+78h+phkResult]; phkResult
0x180100d08  mov     ecx, 20106h; samDesired
0x180100d0d  call    cs:__imp_RegOpenCurrentUser
0x180100d13  mov     ebx, eax
0x180100d15  test    eax, eax
0x180100d17  jz      short loc_180100D2D
0x180100d19  jle     loc_180100DF6
0x180100d1f  movzx   ebx, ax
0x180100d22  or      ebx, 80070000h
0x180100d28  jmp     loc_180100DF6
0x180100d2d  mov     rcx, [rsp+78h+phkResult]; hKey
0x180100d35  mov     ebp, 1
0x180100d3a  lea     rax, [rsp+78h+hKey]
0x180100d3f  mov     r9d, 20106h; samDesired
0x180100d45  xor     r8d, r8d; ulOptions
0x180100d48  mov     [rsp+78h+var_58], rax; phkResult
0x180100d4d  mov     rdx, rdi; lpSubKey
0x180100d50  call    cs:__imp_RegOpenKeyExW
0x180100d56  mov     ebx, eax
0x180100d58  cmp     eax, 2
0x180100d5b  jnz     short loc_180100DA2
0x180100d5d  mov     rcx, [rsp+78h+phkResult]; hKey
0x180100d65  lea     rax, [rsp+78h+hKey]
0x180100d6a  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x180100d73  xor     r9d, r9d; lpClass
0x180100d76  mov     [rsp+78h+var_40], rax; phkResult
0x180100d7b  xor     r8d, r8d; Reserved
0x180100d7e  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180100d87  mov     rdx, rdi; lpSubKey
0x180100d8a  mov     [rsp+78h+samDesired], 20106h; samDesired
0x180100d92  mov     dword ptr [rsp+78h+var_58], 0; dwOptions
0x180100d9a  call    cs:__imp_RegCreateKeyExW
0x180100da0  mov     ebx, eax
0x180100da2  test    ebx, ebx
0x180100da4  jz      short loc_180100DB0
0x180100da6  jle     short loc_180100DF6
0x180100da8  movzx   ebx, bx
0x180100dab  jmp     loc_180100D22
0x180100db0  mov     rcx, [rsp+78h+hKey]; hKey
0x180100db5  jmp     short loc_180100DBC
0x180100db7  mov     [rsp+78h+hKey], rcx
0x180100dbc  mov     eax, [rsp+78h+cbData]
0x180100dc3  xor     ebx, ebx
0x180100dc5  mov     [rsp+78h+samDesired], eax; cbData
0x180100dc9  xor     r8d, r8d; Reserved
0x180100dcc  mov     rdx, r14; lpValueName
0x180100dcf  mov     [rsp+78h+var_58], rsi; lpData
0x180100dd4  lea     r9d, [rbx+3]; dwType
0x180100dd8  call    cs:__imp_RegSetValueExW
0x180100dde  test    eax, eax
0x180100de0  jz      short loc_180100DF1
0x180100de2  jg      short loc_180100DE8
0x180100de4  mov     ebx, eax
0x180100de6  jmp     short loc_180100DF1
0x180100de8  movzx   ebx, ax
0x180100deb  or      ebx, 80070000h
0x180100df1  test    rdi, rdi
0x180100df4  jz      short loc_180100E06
0x180100df6  mov     rcx, [rsp+78h+hKey]; hKey
0x180100dfb  test    rcx, rcx
0x180100dfe  jz      short loc_180100E06
0x180100e00  call    cs:__imp_RegCloseKey
0x180100e06  cmp     ebp, 1
0x180100e09  jnz     short loc_180100E1E
0x180100e0b  mov     rcx, [rsp+78h+phkResult]; hKey
0x180100e13  test    rcx, rcx
0x180100e16  jz      short loc_180100E1E
0x180100e18  call    cs:__imp_RegCloseKey
0x180100e1e  lea     r11, [rsp+78h+var_18]
0x180100e23  mov     eax, ebx
0x180100e25  mov     rbx, [r11+28h]
0x180100e29  mov     rbp, [r11+30h]
0x180100e2d  mov     rsp, r11
0x180100e30  pop     r14
0x180100e32  pop     rdi
0x180100e33  pop     rsi
0x180100e34  retn
```
