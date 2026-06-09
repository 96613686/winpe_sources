# DCCDNUtil_SetRegistryMultiString(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x180100fd8`
- end: `0x1801011c6`
- name: `?DCCDNUtil_SetRegistryMultiString@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `494`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180086c10`
- `0x18009c3e4`
- `0x18009d6dc`
- `0x1800b85c0`
- `0x1800d32a0`
- `0x1800e3758`

## callees

- `0x1800117dc`
- `0x180018744`
- `0x180100fd8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180101169`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180101169`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801010d5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801010d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18010105c`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18010105c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180101190`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801011a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180101190`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801011a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010109b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010109b`

## pseudocode

```c
__int64 __fastcall DCCDNUtil_SetRegistryMultiString(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const BYTE *a4)
{
  __int64 v7; // rdx
  int v8; // ebx
  int v9; // r14d
  LSTATUS v10; // eax
  __int64 v11; // rax
  const unsigned __int16 *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  LSTATUS v15; // eax
  int v17; // [rsp+20h] [rbp-40h]
  DWORD cbData; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  HKEY phkResult; // [rsp+90h] [rbp+30h] BYREF

  phkResult = a1;
  hKey = 0;
  cbData = 0;
  if ( !a1 )
  {
    v7 = 575;
LABEL_3:
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)0x80070057LL,
      v17);
    return (unsigned int)v8;
  }
  if ( !a4 )
  {
    v7 = 576;
    goto LABEL_3;
  }
  v9 = 0;
  if ( !a2 )
  {
    hKey = phkResult;
    goto LABEL_19;
  }
  if ( phkResult == HKEY_CURRENT_USER )
  {
    v10 = RegOpenCurrentUser(0x20106u, &phkResult);
    v8 = v10;
    if ( v10 )
    {
      if ( v10 <= 0 )
        goto LABEL_32;
      v8 = (unsigned __int16)v10;
      goto LABEL_11;
    }
    v9 = 1;
  }
  v8 = RegOpenKeyExW(phkResult, a2, 0, 0x20106u, &hKey);
  if ( v8 == 2 )
    v8 = RegCreateKeyExW(phkResult, a2, 0, 0, 0, 0x20106u, 0, &hKey, 0);
  if ( !v8 )
  {
LABEL_19:
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&a4[2 * v11] );
    v12 = (const unsigned __int16 *)&a4[2 * v11 + 2];
    v13 = 2 * v11 + 2;
    while ( *v12 )
    {
      v14 = -1;
      do
        ++v14;
      while ( v12[v14] );
      v13 += 2 * v14 + 2;
      v12 += v14 + 1;
    }
    v8 = ULongLongToULong(v13 + 2, &cbData);
    if ( v8 >= 0 )
    {
      v15 = RegSetValueExW(hKey, a3, 0, 7u, a4, cbData);
      if ( v15 )
      {
        if ( v15 > 0 )
          v8 = (unsigned __int16)v15 | 0x80070000;
        else
          v8 = v15;
      }
    }
    if ( !a2 )
      goto LABEL_34;
    goto LABEL_32;
  }
  if ( v8 > 0 )
  {
    v8 = (unsigned __int16)v8;
LABEL_11:
    v8 |= 0x80070000;
  }
LABEL_32:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_34:
  if ( v9 == 1 && phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180100fd8  mov     [rsp-28h+arg_8], rbx
0x180100fdd  mov     [rsp-28h+arg_10], rsi
0x180100fe2  mov     [rsp-28h+phkResult], rcx
0x180100fe7  push    rbp
0x180100fe8  push    rdi
0x180100fe9  push    r12
0x180100feb  push    r14
0x180100fed  push    r15
0x180100fef  mov     rbp, rsp
0x180100ff2  sub     rsp, 60h
0x180100ff6  xor     r12d, r12d
0x180100ff9  mov     rdi, r9
0x180100ffc  mov     [rbp+hKey], r12
0x180101000  mov     r15, r8
0x180101003  mov     [rbp+cbData], r12d
0x180101007  mov     rsi, rdx
0x18010100a  test    rcx, rcx
0x18010100d  jnz     short loc_180101031
0x18010100f  mov     edx, 23Fh; void *
0x180101014  mov     rcx, [rbp+28h]; this
0x180101018  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x18010101f  mov     ebx, 80070057h
0x180101024  mov     r9d, ebx; char *
0x180101027  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010102c  jmp     loc_1801011AB
0x180101031  test    rdi, rdi
0x180101034  jnz     short loc_18010103D
0x180101036  mov     edx, 240h
0x18010103b  jmp     short loc_180101014
0x18010103d  mov     r14d, r12d
0x180101040  test    rsi, rsi
0x180101043  jz      loc_1801010EC
0x180101049  cmp     [rbp+phkResult], 0FFFFFFFF80000001h
0x180101051  jnz     short loc_180101082
0x180101053  lea     rdx, [rbp+phkResult]; phkResult
0x180101057  mov     ecx, 20106h; samDesired
0x18010105c  call    cs:__imp_RegOpenCurrentUser
0x180101062  mov     ebx, eax
0x180101064  test    eax, eax
0x180101066  jz      short loc_18010107C
0x180101068  jle     loc_180101187
0x18010106e  movzx   ebx, ax
0x180101071  or      ebx, 80070000h
0x180101077  jmp     loc_180101187
0x18010107c  mov     r14d, 1
0x180101082  mov     rcx, [rbp+phkResult]; hKey
0x180101086  lea     rax, [rbp+hKey]
0x18010108a  mov     r9d, 20106h; samDesired
0x180101090  mov     [rsp+60h+var_40], rax; phkResult
0x180101095  xor     r8d, r8d; ulOptions
0x180101098  mov     rdx, rsi; lpSubKey
0x18010109b  call    cs:__imp_RegOpenKeyExW
0x1801010a1  mov     ebx, eax
0x1801010a3  cmp     eax, 2
0x1801010a6  jnz     short loc_1801010DD
0x1801010a8  mov     rcx, [rbp+phkResult]; hKey
0x1801010ac  lea     rax, [rbp+hKey]
0x1801010b0  mov     [rsp+60h+lpdwDisposition], r12; lpdwDisposition
0x1801010b5  xor     r9d, r9d; lpClass
0x1801010b8  mov     [rsp+60h+var_28], rax; phkResult
0x1801010bd  xor     r8d, r8d; Reserved
0x1801010c0  mov     [rsp+60h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1801010c5  mov     rdx, rsi; lpSubKey
0x1801010c8  mov     [rsp+60h+samDesired], 20106h; samDesired
0x1801010d0  mov     dword ptr [rsp+60h+var_40], r12d; dwOptions
0x1801010d5  call    cs:__imp_RegCreateKeyExW
0x1801010db  mov     ebx, eax
0x1801010dd  test    ebx, ebx
0x1801010df  jz      short loc_1801010F4
0x1801010e1  jle     loc_180101187
0x1801010e7  movzx   ebx, bx
0x1801010ea  jmp     short loc_180101071
0x1801010ec  mov     rax, [rbp+phkResult]
0x1801010f0  mov     [rbp+hKey], rax
0x1801010f4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801010f8  mov     rax, r8
0x1801010fb  inc     rax
0x1801010fe  cmp     [rdi+rax*2], r12w
0x180101103  jnz     short loc_1801010FB
0x180101105  lea     rcx, [rdi+2]
0x180101109  lea     rcx, [rcx+rax*2]
0x18010110d  lea     rdx, ds:2[rax*2]
0x180101115  jmp     short loc_180101134
0x180101117  mov     rax, r8
0x18010111a  inc     rax
0x18010111d  cmp     [rcx+rax*2], r12w
0x180101122  jnz     short loc_18010111A
0x180101124  lea     rdx, [rdx+rax*2]
0x180101128  add     rdx, 2
0x18010112c  lea     rcx, [rcx+rax*2]
0x180101130  add     rcx, 2
0x180101134  cmp     r12w, [rcx]
0x180101138  jnz     short loc_180101117
0x18010113a  lea     rcx, [rdx+2]; unsigned __int64
0x18010113e  lea     rdx, [rbp+cbData]; unsigned int *
0x180101142  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180101147  mov     ebx, eax
0x180101149  test    eax, eax
0x18010114b  js      short loc_180101182
0x18010114d  mov     ecx, [rbp+cbData]
0x180101150  mov     r9d, 7; dwType
0x180101156  mov     [rsp+60h+samDesired], ecx; cbData
0x18010115a  xor     r8d, r8d; Reserved
0x18010115d  mov     rcx, [rbp+hKey]; hKey
0x180101161  mov     rdx, r15; lpValueName
0x180101164  mov     [rsp+60h+var_40], rdi; lpData
0x180101169  call    cs:__imp_RegSetValueExW
0x18010116f  test    eax, eax
0x180101171  jz      short loc_180101182
0x180101173  jg      short loc_180101179
0x180101175  mov     ebx, eax
0x180101177  jmp     short loc_180101182
0x180101179  movzx   ebx, ax
0x18010117c  or      ebx, 80070000h
0x180101182  test    rsi, rsi
0x180101185  jz      short loc_180101196
0x180101187  mov     rcx, [rbp+hKey]; hKey
0x18010118b  test    rcx, rcx
0x18010118e  jz      short loc_180101196
0x180101190  call    cs:__imp_RegCloseKey
0x180101196  cmp     r14d, 1
0x18010119a  jnz     short loc_1801011AB
0x18010119c  mov     rcx, [rbp+phkResult]; hKey
0x1801011a0  test    rcx, rcx
0x1801011a3  jz      short loc_1801011AB
0x1801011a5  call    cs:__imp_RegCloseKey
0x1801011ab  lea     r11, [rsp+60h+var_s0]
0x1801011b0  mov     eax, ebx
0x1801011b2  mov     rbx, [r11+38h]
0x1801011b6  mov     rsi, [r11+40h]
0x1801011ba  mov     rsp, r11
0x1801011bd  pop     r15
0x1801011bf  pop     r14
0x1801011c1  pop     r12
0x1801011c3  pop     rdi
0x1801011c4  pop     rbp
0x1801011c5  retn
```
