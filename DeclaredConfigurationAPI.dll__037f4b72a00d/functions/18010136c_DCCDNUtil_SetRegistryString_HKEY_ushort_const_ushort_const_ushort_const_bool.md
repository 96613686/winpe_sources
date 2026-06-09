# DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)

- ea: `0x18010136c`
- end: `0x18010153c`
- name: `?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z`
- size: `464`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `45`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006037c`
- `0x180065ce0`
- `0x180066550`
- `0x180067160`
- `0x180068ba0`
- `0x18007f370`
- `0x180080e90`
- `0x180086c10`
- `0x1800882a0`
- `0x180091eec`
- `0x18009468c`
- `0x180097f4c`
- `0x180098410`
- `0x18009b2e4`
- `0x18009bae8`
- `0x18009c3e4`
- `0x18009d6dc`
- `0x18009e3f0`
- `0x18009e728`
- `0x18009eb10`
- `0x1800aaee0`
- `0x1800ac970`
- `0x1800ae150`
- `0x1800b85c0`
- `0x1800b8fac`
- `0x1800baca4`
- `0x1800c7600`
- `0x1800d1b94`
- `0x1800d24e4`
- `0x1800d32a0`
- `0x1800d8844`
- `0x1800d943c`
- `0x1800da8b4`
- `0x1800dd884`
- `0x1800dd9b8`
- `0x1800ddd9c`
- `0x1800e3758`
- `0x1800f2040`
- `0x1800f23d0`
- `0x1800f2730`
- `0x1800f29e8`
- `0x1800f3448`
- `0x1800fe9f4`
- `0x1800fec58`
- `0x180112208`

## callees

- `0x1800117dc`
- `0x180018744`
- `0x1800fdefc`
- `0x18010136c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801014e9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801014e9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180101475`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180101475`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1801013f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1801013f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180101512`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180101527`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180101512`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180101527`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180101430`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180101430`

## pseudocode

```c
__int64 __fastcall DCCDNUtil_SetRegistryString(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        bool a5)
{
  __int64 v8; // rdx
  int v9; // ebx
  int v10; // r14d
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  int v14; // [rsp+20h] [rbp-58h]
  unsigned int v15; // [rsp+50h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-20h] BYREF
  unsigned __int64 v17[3]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]
  HKEY phkResult; // [rsp+B0h] [rbp+38h] BYREF

  phkResult = a1;
  hKey = 0;
  v17[0] = 0;
  v15 = 0;
  if ( !a1 )
  {
    v8 = 469;
LABEL_3:
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)0x80070057LL,
      v14);
    return (unsigned int)v9;
  }
  if ( !a4 )
  {
    v8 = 470;
    goto LABEL_3;
  }
  v10 = 0;
  if ( !a2 )
  {
    hKey = a1;
    goto LABEL_19;
  }
  if ( a1 == HKEY_CURRENT_USER )
  {
    v11 = RegOpenCurrentUser(0x20106u, &phkResult);
    v9 = v11;
    if ( v11 )
    {
      if ( v11 <= 0 )
        goto LABEL_28;
      v9 = (unsigned __int16)v11;
      goto LABEL_11;
    }
    a1 = phkResult;
    v10 = 1;
  }
  v9 = RegOpenKeyExW(a1, a2, 0, 0x20106u, &hKey);
  if ( v9 == 2 )
    v9 = RegCreateKeyExW(phkResult, a2, 0, 0, 0, 0x20106u, 0, &hKey, 0);
  if ( !v9 )
  {
LABEL_19:
    v9 = StringCbLengthW(a4, 0xFFFFFFFE, v17);
    if ( v9 >= 0 )
    {
      v9 = ULongLongToULong(v17[0], &v15);
      if ( v9 >= 0 )
      {
        if ( v15 + 2 >= v15 )
        {
          v12 = RegSetValueExW(hKey, a3, 0, a5 + 1, (const BYTE *)a4, v15 + 2);
          v9 = 0;
          if ( v12 )
          {
            if ( v12 > 0 )
              v9 = (unsigned __int16)v12 | 0x80070000;
            else
              v9 = v12;
          }
        }
        else
        {
          v9 = -2147024362;
        }
      }
    }
    if ( !a2 )
      goto LABEL_30;
    goto LABEL_28;
  }
  if ( v9 > 0 )
  {
    v9 = (unsigned __int16)v9;
LABEL_11:
    v9 |= 0x80070000;
  }
LABEL_28:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_30:
  if ( v10 == 1 && phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18010136c  mov     [rsp-30h+phkResult], rcx
0x180101371  push    rbp
0x180101372  push    rbx
0x180101373  push    rsi
0x180101374  push    rdi
0x180101375  push    r14
0x180101377  push    r15
0x180101379  mov     rbp, rsp
0x18010137c  sub     rsp, 78h
0x180101380  mov     [rbp+hKey], 0
0x180101388  mov     rsi, r9
0x18010138b  mov     [rbp+var_18], 0
0x180101393  mov     r15, r8
0x180101396  mov     [rbp+var_28], 0
0x18010139d  mov     rdi, rdx
0x1801013a0  test    rcx, rcx
0x1801013a3  jnz     short loc_1801013C7
0x1801013a5  mov     edx, 1D5h; void *
0x1801013aa  mov     rcx, [rbp+30h]; this
0x1801013ae  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x1801013b5  mov     ebx, 80070057h
0x1801013ba  mov     r9d, ebx; char *
0x1801013bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801013c2  jmp     loc_18010152D
0x1801013c7  test    rsi, rsi
0x1801013ca  jnz     short loc_1801013D3
0x1801013cc  mov     edx, 1D6h
0x1801013d1  jmp     short loc_1801013AA
0x1801013d3  xor     r14d, r14d
0x1801013d6  test    rdi, rdi
0x1801013d9  jz      loc_18010148F
0x1801013df  cmp     rcx, 0FFFFFFFF80000001h
0x1801013e6  jnz     short loc_18010141B
0x1801013e8  lea     rdx, [rbp+phkResult]; phkResult
0x1801013ec  mov     ecx, 20106h; samDesired
0x1801013f1  call    cs:__imp_RegOpenCurrentUser
0x1801013f7  mov     ebx, eax
0x1801013f9  test    eax, eax
0x1801013fb  jz      short loc_180101411
0x1801013fd  jle     loc_180101509
0x180101403  movzx   ebx, ax
0x180101406  or      ebx, 80070000h
0x18010140c  jmp     loc_180101509
0x180101411  mov     rcx, [rbp+phkResult]; hKey
0x180101415  mov     r14d, 1
0x18010141b  lea     rax, [rbp+hKey]
0x18010141f  mov     r9d, 20106h; samDesired
0x180101425  xor     r8d, r8d; ulOptions
0x180101428  mov     [rsp+78h+var_58], rax; phkResult
0x18010142d  mov     rdx, rdi; lpSubKey
0x180101430  call    cs:__imp_RegOpenKeyExW
0x180101436  mov     ebx, eax
0x180101438  cmp     eax, 2
0x18010143b  jnz     short loc_18010147D
0x18010143d  mov     rcx, [rbp+phkResult]; hKey
0x180101441  lea     rax, [rbp+hKey]
0x180101445  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x18010144e  xor     r9d, r9d; lpClass
0x180101451  mov     [rsp+78h+var_40], rax; phkResult
0x180101456  xor     r8d, r8d; Reserved
0x180101459  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180101462  mov     rdx, rdi; lpSubKey
0x180101465  mov     [rsp+78h+samDesired], 20106h; samDesired
0x18010146d  mov     dword ptr [rsp+78h+var_58], 0; dwOptions
0x180101475  call    cs:__imp_RegCreateKeyExW
0x18010147b  mov     ebx, eax
0x18010147d  test    ebx, ebx
0x18010147f  jz      short loc_180101493
0x180101481  jle     loc_180101509
0x180101487  movzx   ebx, bx
0x18010148a  jmp     loc_180101406
0x18010148f  mov     [rbp+hKey], rcx
0x180101493  lea     r8, [rbp+var_18]; unsigned __int64 *
0x180101497  mov     edx, 0FFFFFFFEh; unsigned __int64
0x18010149c  mov     rcx, rsi; unsigned __int16 *
0x18010149f  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1801014a4  mov     ebx, eax
0x1801014a6  test    eax, eax
0x1801014a8  js      short loc_180101504
0x1801014aa  mov     rcx, [rbp+var_18]; unsigned __int64
0x1801014ae  lea     rdx, [rbp+var_28]; unsigned int *
0x1801014b2  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1801014b7  mov     ebx, eax
0x1801014b9  test    eax, eax
0x1801014bb  js      short loc_180101504
0x1801014bd  mov     eax, [rbp+var_28]
0x1801014c0  lea     ecx, [rax+2]
0x1801014c3  cmp     ecx, eax
0x1801014c5  jnb     short loc_1801014CE
0x1801014c7  mov     ebx, 80070216h
0x1801014cc  jmp     short loc_180101504
0x1801014ce  movzx   r9d, [rbp+arg_20]
0x1801014d3  xor     r8d, r8d; Reserved
0x1801014d6  mov     [rsp+78h+samDesired], ecx; cbData
0x1801014da  inc     r9d; dwType
0x1801014dd  mov     rcx, [rbp+hKey]; hKey
0x1801014e1  mov     rdx, r15; lpValueName
0x1801014e4  mov     [rsp+78h+var_58], rsi; lpData
0x1801014e9  call    cs:__imp_RegSetValueExW
0x1801014ef  xor     ebx, ebx
0x1801014f1  test    eax, eax
0x1801014f3  jz      short loc_180101504
0x1801014f5  jg      short loc_1801014FB
0x1801014f7  mov     ebx, eax
0x1801014f9  jmp     short loc_180101504
0x1801014fb  movzx   ebx, ax
0x1801014fe  or      ebx, 80070000h
0x180101504  test    rdi, rdi
0x180101507  jz      short loc_180101518
0x180101509  mov     rcx, [rbp+hKey]; hKey
0x18010150d  test    rcx, rcx
0x180101510  jz      short loc_180101518
0x180101512  call    cs:__imp_RegCloseKey
0x180101518  cmp     r14d, 1
0x18010151c  jnz     short loc_18010152D
0x18010151e  mov     rcx, [rbp+phkResult]; hKey
0x180101522  test    rcx, rcx
0x180101525  jz      short loc_18010152D
0x180101527  call    cs:__imp_RegCloseKey
0x18010152d  mov     eax, ebx
0x18010152f  add     rsp, 78h
0x180101533  pop     r15
0x180101535  pop     r14
0x180101537  pop     rdi
0x180101538  pop     rsi
0x180101539  pop     rbx
0x18010153a  pop     rbp
0x18010153b  retn
```
