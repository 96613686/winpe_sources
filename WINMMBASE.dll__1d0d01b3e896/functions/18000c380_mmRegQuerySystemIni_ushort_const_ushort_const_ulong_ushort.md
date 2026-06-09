# mmRegQuerySystemIni(ushort const *,ushort const *,ulong,ushort *)

- ea: `0x18000c380`
- end: `0x18000c568`
- name: `?mmRegQuerySystemIni@@YAHPEBG0KPEAG@Z`
- size: `488`
- prototype: `_BOOL8 __fastcall(PCNZWCH lpString1, LPCWSTR lpValue, DWORD, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800039d0`

## callees

- `0x18000c380`
- `0x18000f52c`
- `0x1800106c0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000c4ab`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000c4ab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c4f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c535`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c4f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c535`

## pseudocode

```c
_BOOL8 __fastcall mmRegQuerySystemIni(PCNZWCH lpString1, LPCWSTR lpValue, DWORD a3, unsigned __int16 *a4)
{
  __int64 v4; // r11
  __int64 v5; // r10
  WCHAR *v9; // r9
  const wchar_t *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  WCHAR *v14; // rcx
  WCHAR *i; // rax
  PCNZWCH v16; // rcx
  _WORD *v17; // rdx
  _WORD *v18; // rcx
  HKEY v20; // rcx
  HKEY v21; // rax
  DWORD pcbData[4]; // [rsp+40h] [rbp-258h] BYREF
  WCHAR SubKey[260]; // [rsp+50h] [rbp-248h] BYREF
  _BYTE v24[8]; // [rsp+258h] [rbp-40h] BYREF

  v4 = 2147483646;
  v5 = 260;
  v9 = SubKey;
  v11 = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\";
  v12 = 2147483646;
  v13 = 260;
  do
  {
    if ( !v12 )
      break;
    if ( !*v11 )
      break;
    *v9++ = *v11++;
    --v12;
    --v13;
  }
  while ( v13 );
  v14 = v9 - 1;
  if ( v13 )
    v14 = v9;
  *v14 = 0;
  if ( !v13 )
    return 0;
  for ( i = SubKey; *i; ++i )
  {
    if ( !--v5 )
      return 0;
  }
  v16 = lpString1;
  v17 = &v24[-2 * v5];
  do
  {
    if ( !v4 )
      break;
    if ( !*v16 )
      break;
    *v17++ = *v16++;
    --v4;
    --v5;
  }
  while ( v5 );
  v18 = v17 - 1;
  if ( v5 )
    v18 = v17;
  *v18 = 0;
  if ( !v5 )
    return 0;
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, wszDrivers, -1) == 2 )
  {
    v21 = Drivers32Handle;
    if ( !Drivers32Handle )
    {
      v21 = mmRegOpenSubkey(v20, SubKey);
      Drivers32Handle = v21;
      if ( !v21 )
        return 0;
    }
    pcbData[0] = a3;
    return RegGetValueW(v21, 0, lpValue, 2u, 0, a4, pcbData) == 0;
  }
  else
  {
    pcbData[0] = a3;
    return RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, lpValue, 2u, 0, a4, pcbData) == 0;
  }
}

```

## disassembly

```asm
0x18000c380  push    rbx
0x18000c382  push    rbp
0x18000c383  push    rsi
0x18000c384  push    rdi
0x18000c385  sub     rsp, 278h
0x18000c38c  mov     rax, cs:__security_cookie
0x18000c393  xor     rax, rsp
0x18000c396  mov     [rsp+298h+var_38], rax
0x18000c39e  mov     r11d, 7FFFFFFEh
0x18000c3a4  mov     r10d, 104h
0x18000c3aa  mov     rbp, r9
0x18000c3ad  mov     esi, r8d
0x18000c3b0  mov     rdi, rdx
0x18000c3b3  lea     r9, [rsp+298h+SubKey]
0x18000c3b8  mov     rbx, rcx
0x18000c3bb  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000c3c2  mov     ecx, r11d
0x18000c3c5  mov     r8d, r10d
0x18000c3c8  test    rcx, rcx
0x18000c3cb  jz      short loc_18000C3EA
0x18000c3cd  movzx   eax, word ptr [rdx]
0x18000c3d0  test    ax, ax
0x18000c3d3  jz      short loc_18000C3EA
0x18000c3d5  mov     [r9], ax
0x18000c3d9  add     rdx, 2
0x18000c3dd  add     r9, 2
0x18000c3e1  dec     rcx
0x18000c3e4  sub     r8, 1
0x18000c3e8  jnz     short loc_18000C3C8
0x18000c3ea  test    r8, r8
0x18000c3ed  lea     rcx, [r9-2]
0x18000c3f1  cmovnz  rcx, r9
0x18000c3f5  xor     eax, eax
0x18000c3f7  mov     [rcx], ax
0x18000c3fa  test    r8, r8
0x18000c3fd  jz      short loc_18000C466
0x18000c3ff  lea     rax, [rsp+298h+SubKey]
0x18000c404  cmp     word ptr [rax], 0
0x18000c408  jz      short loc_18000C416
0x18000c40a  add     rax, 2
0x18000c40e  sub     r10, 1
0x18000c412  jnz     short loc_18000C404
0x18000c414  jmp     short loc_18000C466
0x18000c416  lea     rax, [r10+r10]
0x18000c41a  mov     rcx, rbx
0x18000c41d  lea     rdx, [rsp+298h+var_40]
0x18000c425  sub     rdx, rax
0x18000c428  test    r10, r10
0x18000c42b  jz      short loc_18000C451
0x18000c42d  nop     dword ptr [rax]
0x18000c430  test    r11, r11
0x18000c433  jz      short loc_18000C451
0x18000c435  movzx   eax, word ptr [rcx]
0x18000c438  test    ax, ax
0x18000c43b  jz      short loc_18000C451
0x18000c43d  mov     [rdx], ax
0x18000c440  add     rcx, 2
0x18000c444  add     rdx, 2
0x18000c448  dec     r11
0x18000c44b  sub     r10, 1
0x18000c44f  jnz     short loc_18000C430
0x18000c451  test    r10, r10
0x18000c454  lea     rcx, [rdx-2]
0x18000c458  cmovnz  rcx, rdx
0x18000c45c  xor     eax, eax
0x18000c45e  mov     [rcx], ax
0x18000c461  test    r10, r10
0x18000c464  jnz     short loc_18000C484
0x18000c466  xor     eax, eax
0x18000c468  mov     rcx, [rsp+298h+var_38]
0x18000c470  xor     rcx, rsp; StackCookie
0x18000c473  call    __security_check_cookie
0x18000c478  add     rsp, 278h
0x18000c47f  pop     rdi
0x18000c480  pop     rsi
0x18000c481  pop     rbp
0x18000c482  pop     rbx
0x18000c483  retn
0x18000c484  lea     rax, wszDrivers; "DRIVERS32"
0x18000c48b  mov     [rsp+298h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000c493  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000c499  mov     [rsp+298h+lpString2], rax; lpString2
0x18000c49e  mov     r8, rbx; lpString1
0x18000c4a1  mov     edx, 1; dwCmpFlags
0x18000c4a6  mov     ecx, 7Fh; Locale
0x18000c4ab  call    cs:__imp_CompareStringW
0x18000c4b1  cmp     eax, 2
0x18000c4b4  jnz     short loc_18000C504
0x18000c4b6  mov     rax, cs:?Drivers32Handle@@3PEAUHKEY__@@EA; HKEY__ * Drivers32Handle
0x18000c4bd  test    rax, rax
0x18000c4c0  jz      loc_18000C549
0x18000c4c6  lea     rcx, [rsp+298h+var_258]
0x18000c4cb  mov     [rsp+298h+var_258], esi
0x18000c4cf  mov     [rsp+298h+pcbData], rcx; pcbData
0x18000c4d4  mov     r9d, 2; dwFlags
0x18000c4da  mov     qword ptr [rsp+298h+cchCount2], rbp; pvData
0x18000c4df  mov     rcx, rax; hkey
0x18000c4e2  mov     r8, rdi; lpValue
0x18000c4e5  mov     [rsp+298h+lpString2], 0; pdwType
0x18000c4ee  xor     edx, edx; lpSubKey
0x18000c4f0  call    cs:__imp_RegGetValueW
0x18000c4f6  xor     ecx, ecx
0x18000c4f8  test    eax, eax
0x18000c4fa  setz    cl
0x18000c4fd  mov     eax, ecx
0x18000c4ff  jmp     loc_18000C468
0x18000c504  lea     rax, [rsp+298h+var_258]
0x18000c509  mov     [rsp+298h+var_258], esi
0x18000c50d  mov     [rsp+298h+pcbData], rax; pcbData
0x18000c512  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x18000c517  mov     qword ptr [rsp+298h+cchCount2], rbp; pvData
0x18000c51c  mov     r9d, 2; dwFlags
0x18000c522  mov     r8, rdi; lpValue
0x18000c525  mov     [rsp+298h+lpString2], 0; pdwType
0x18000c52e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000c535  call    cs:__imp_RegGetValueW
0x18000c53b  xor     ecx, ecx
0x18000c53d  test    eax, eax
0x18000c53f  setz    cl
0x18000c542  mov     eax, ecx
0x18000c544  jmp     loc_18000C468
0x18000c549  lea     rdx, [rsp+298h+SubKey]; unsigned __int16 *
0x18000c54e  call    ?mmRegOpenSubkey@@YAPEAUHKEY__@@PEAU1@PEBG@Z; mmRegOpenSubkey(HKEY__ *,ushort const *)
0x18000c553  mov     cs:?Drivers32Handle@@3PEAUHKEY__@@EA, rax; HKEY__ * Drivers32Handle
0x18000c55a  test    rax, rax
0x18000c55d  jz      loc_18000C466
0x18000c563  jmp     loc_18000C4C6
```
