# MSCryptSetProperty

- ea: `0x18000cfb0`
- end: `0x18000d61b`
- name: `MSCryptSetProperty`
- size: `1643`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000cfb0`
- `0x18000ecb0`
- `0x18000ee60`
- `0x18002d800`
- `0x180063170`
- `0x18007f765`

## string_xrefs

- `0x18000d1f9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000d27a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000d340`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000d3ba`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000d3ea`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000d45d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000d532`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000d580`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000d5f5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180080244`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180080276`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptSetProperty(_DWORD *a1, const wchar_t *a2, char *a3, int a4, int a5)
{
  char *v6; // rdi
  int v9; // r15d
  unsigned int v10; // r14d
  unsigned int v11; // r9d
  char *v12; // r8
  char *v13; // rax
  int v14; // ecx
  int v15; // edx
  char *v16; // rax
  int v17; // ecx
  int v18; // edx
  char *v19; // rax
  int v20; // ecx
  int v21; // edx
  char *v22; // rax
  int v23; // ecx
  int v24; // edx
  char *v25; // rcx
  int v26; // edx
  int v27; // eax
  char *v28; // rdx
  int v29; // eax
  int v30; // ecx
  int v31; // edx
  int v32; // eax
  int v33; // ecx
  int v34; // eax
  int v36; // edx
  int v37; // r8d
  int v38; // r15d
  int v39; // edx
  int v40; // r8d
  _QWORD *v41; // rcx
  int v42; // ecx
  unsigned int v43; // eax
  unsigned int v44; // r14d
  unsigned int v45; // esi
  __int64 v46; // r9
  __int64 v47; // rcx
  int v48; // r9d
  __int64 v49; // r8
  __int64 v50; // r9
  __int64 v51; // rcx
  int v52; // ecx
  int v53; // eax
  __int64 v54; // r9

  v6 = a3;
  if ( !a1 || (v9 = a1[1], v9 != 1297306433) && v9 != 1297306443 )
  {
    v10 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        133);
    return v10;
  }
  if ( !a2 || !a3 || a5 )
  {
    v46 = 2446;
    goto LABEL_91;
  }
  if ( !wcscmp_0(a2, L"ChainingMode") )
  {
    v10 = 0;
    v11 = 0;
    v12 = (char *)((char *)rgpszChainModeNameArray[0] - v6);
    v13 = v6;
    do
    {
      v14 = *(unsigned __int16 *)&v12[(_QWORD)v13];
      v15 = *(unsigned __int16 *)v13 - v14;
      if ( v15 )
        break;
      v13 += 2;
    }
    while ( v14 );
    if ( !v15 )
      goto LABEL_31;
    v11 = 1;
    v12 = (char *)((char *)L"ChainingModeCBC" - v6);
    v16 = v6;
    do
    {
      v17 = *(unsigned __int16 *)&v12[(_QWORD)v16];
      v18 = *(unsigned __int16 *)v16 - v17;
      if ( v18 )
        break;
      v16 += 2;
    }
    while ( v17 );
    if ( !v18 )
      goto LABEL_31;
    v11 = 2;
    v12 = (char *)((char *)L"ChainingModeECB" - v6);
    v19 = v6;
    do
    {
      v20 = *(unsigned __int16 *)&v12[(_QWORD)v19];
      v21 = *(unsigned __int16 *)v19 - v20;
      if ( v21 )
        break;
      v19 += 2;
    }
    while ( v20 );
    if ( !v21 )
      goto LABEL_31;
    v11 = 3;
    v12 = (char *)((char *)L"ChainingModeCFB" - v6);
    v22 = v6;
    do
    {
      v23 = *(unsigned __int16 *)&v12[(_QWORD)v22];
      v24 = *(unsigned __int16 *)v22 - v23;
      if ( v24 )
        break;
      v22 += 2;
    }
    while ( v23 );
    if ( !v24 )
      goto LABEL_31;
    v11 = 4;
    v12 = (char *)((char *)L"ChainingModeCCM" - v6);
    v25 = v6;
    do
    {
      v26 = *(unsigned __int16 *)&v12[(_QWORD)v25];
      v27 = *(unsigned __int16 *)v25 - v26;
      if ( v27 )
        break;
      v25 += 2;
    }
    while ( v26 );
    if ( !v27 )
      goto LABEL_31;
    v11 = 5;
    v28 = (char *)((char *)L"ChainingModeGCM" - v6);
    do
    {
      v29 = *(unsigned __int16 *)&v28[(_QWORD)v6];
      v30 = *(unsigned __int16 *)v6 - v29;
      if ( v30 )
        break;
      v6 += 2;
    }
    while ( v29 );
    if ( v30 )
    {
      v10 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)v28,
          (_DWORD)v12,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
          166);
    }
    else
    {
LABEL_31:
      v31 = a1[2];
      v32 = qword_180084120[14 * (unsigned int)(unsigned __int16)v31 - 14];
      if ( _bittest(&v32, v11) )
      {
        a1[3] = v11;
        v33 = rgdwDefaultMsgBlockSize[v11];
        a1[5] = v33;
        if ( !v33 )
          a1[5] = a1[4];
        if ( v9 == 1297306433 && v31 == 65538 )
        {
          v34 = 3200;
          if ( v11 != 5 )
            v34 = 592;
          a1[7] = v34;
        }
      }
      else
      {
        v10 = -1073741637;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v31,
            (_DWORD)v12,
            (unsigned int)"Status",
            187,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
            173);
      }
    }
    return v10;
  }
  if ( !wcscmp_0(a2, L"MessageBlockLength") )
  {
    v52 = a1[2];
    if ( v52 != 65544 && a1[3] != 3 )
    {
      v10 = -1073741637;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v36,
          v37,
          (unsigned int)"Status",
          187,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
          208);
      return v10;
    }
    if ( a4 == 4 )
    {
      v53 = *(_DWORD *)v6;
      if ( v52 == 65544 )
      {
        if ( (v53 & 0xF) != 0 || !v53 )
        {
          v46 = 2530;
          goto LABEL_91;
        }
      }
      else if ( v53 != 1 && v53 != a1[4] )
      {
        v46 = 2537;
        goto LABEL_91;
      }
      a1[5] = v53;
      return 0;
    }
    v46 = 2519;
LABEL_91:
    v44 = -1073741811;
    v47 = 3221225485LL;
    goto LABEL_66;
  }
  v38 = v9 - 1297306433;
  if ( !v38 )
  {
    if ( wcscmp_0(a2, L"EffectiveKeyLength") )
    {
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_45;
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v39,
        v40,
        (unsigned int)"Status",
        187,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        143);
LABEL_61:
      v41 = WPP_GLOBAL_Control;
LABEL_45:
      v10 = -1073741637;
LABEL_46:
      if ( v41 != &WPP_GLOBAL_Control && (*((_BYTE *)v41 + 28) & 1) != 0 )
        WPP_SF_sDsd(
          v41[2],
          v39,
          v40,
          (unsigned int)"Status",
          v10,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
          253);
      return v10;
    }
    if ( a1[2] != 65543 )
    {
      DebugTraceError(3221225659LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", 2158);
      goto LABEL_61;
    }
    if ( a4 != 4 )
    {
      v54 = 2168;
LABEL_112:
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v54);
      v41 = WPP_GLOBAL_Control;
      v10 = -1073741811;
      goto LABEL_46;
    }
    if ( (unsigned int)(*(_DWORD *)v6 - 16) > 0x3F0 )
    {
      v54 = 2179;
      goto LABEL_112;
    }
    a1[9] = *(_DWORD *)v6;
    return 0;
  }
  if ( v38 != 10 )
  {
    v44 = -1073741816;
    v46 = 2577;
    v47 = 3221225480LL;
    goto LABEL_66;
  }
  v10 = 0;
  v42 = *a2 - 73;
  if ( *a2 == 73 )
  {
    v42 = a2[1] - 86;
    if ( a2[1] == 86 )
      v42 = a2[2];
  }
  if ( !v42 )
  {
    if ( a1[2] == 65537 )
    {
      v44 = -1073741637;
      v45 = -1073741637;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v36,
          v37,
          (unsigned int)"Status",
          187,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
          9);
    }
    else
    {
      v43 = a1[4];
      if ( a4 == v43 )
      {
        memcpy_0(a1 + 10, v6, v43);
        return 0;
      }
      v44 = -1073741811;
      v45 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v36,
          v37,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
          16);
    }
    goto LABEL_65;
  }
  if ( !wcscmp_0(a2, L"EffectiveKeyLength") )
  {
    if ( a1[2] == 65543 )
    {
      if ( a4 == 4 )
      {
        v48 = *(_DWORD *)v6;
        if ( (unsigned int)(*(_DWORD *)v6 - 16) > 0x3F0 )
        {
          v44 = -1073741811;
          v50 = 1844;
          v51 = 3221225485LL;
        }
        else
        {
          v49 = (unsigned int)a1[14];
          a1[84] = v48;
          a1[6] = v48;
          if ( !(unsigned int)SymCryptRc2ExpandKeyEx(a1 + 48, a1 + 15, v49) )
            return v10;
          v44 = -1073741811;
          v50 = 1864;
          v51 = 3221225485LL;
        }
      }
      else
      {
        v44 = -1073741811;
        v50 = 1833;
        v51 = 3221225485LL;
      }
      goto LABEL_108;
    }
    v50 = 1823;
  }
  else
  {
    v50 = 1874;
  }
  v44 = -1073741637;
  v51 = 3221225659LL;
LABEL_108:
  v45 = v44;
  DebugTraceError(v51, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v50);
LABEL_65:
  v46 = 2570;
  v47 = v45;
LABEL_66:
  DebugTraceError(v47, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v46);
  return v44;
}

```

## disassembly

```asm
0x18000cfb0  push    rbx
0x18000cfb2  push    rbp
0x18000cfb3  push    rsi
0x18000cfb4  push    rdi
0x18000cfb5  push    r14
0x18000cfb7  push    r15
0x18000cfb9  sub     rsp, 48h
0x18000cfbd  mov     esi, r9d
0x18000cfc0  mov     rdi, r8
0x18000cfc3  mov     rbx, rdx
0x18000cfc6  mov     rbp, rcx
0x18000cfc9  test    rcx, rcx
0x18000cfcc  jz      loc_18000D38B
0x18000cfd2  mov     r15d, [rcx+4]
0x18000cfd6  cmp     r15d, 4D535341h
0x18000cfdd  jnz     loc_18000D37E
0x18000cfe3  test    rbx, rbx
0x18000cfe6  jz      loc_18000D55C
0x18000cfec  test    rdi, rdi
0x18000cfef  jz      loc_18000D55C
0x18000cff5  cmp     [rsp+78h+arg_20], 0
0x18000cffd  jnz     loc_18000D55C
0x18000d003  lea     rdx, aChainingmode; "ChainingMode"
0x18000d00a  mov     rcx, rbx; String1
0x18000d00d  call    wcscmp_0
0x18000d012  test    eax, eax
0x18000d014  jnz     loc_18000D1B0
0x18000d01a  mov     r8, cs:rgpszChainModeNameArray
0x18000d021  xor     r14d, r14d
0x18000d024  mov     r9d, r14d
0x18000d027  sub     r8, rdi
0x18000d02a  mov     rax, rdi
0x18000d02d  nop     dword ptr [rax]
0x18000d030  movzx   edx, word ptr [rax]
0x18000d033  movzx   ecx, word ptr [rax+r8]
0x18000d038  sub     edx, ecx
0x18000d03a  jnz     short loc_18000D044
0x18000d03c  add     rax, 2
0x18000d040  test    ecx, ecx
0x18000d042  jnz     short loc_18000D030
0x18000d044  test    edx, edx
0x18000d046  jz      loc_18000D13B
0x18000d04c  mov     r8, cs:off_180084008; "ChainingModeCBC"
0x18000d053  mov     r9d, 1
0x18000d059  sub     r8, rdi
0x18000d05c  mov     rax, rdi
0x18000d05f  nop
0x18000d060  movzx   edx, word ptr [rax]
0x18000d063  movzx   ecx, word ptr [rax+r8]
0x18000d068  sub     edx, ecx
0x18000d06a  jnz     short loc_18000D074
0x18000d06c  add     rax, 2
0x18000d070  test    ecx, ecx
0x18000d072  jnz     short loc_18000D060
0x18000d074  test    edx, edx
0x18000d076  jz      loc_18000D13B
0x18000d07c  mov     r8, cs:off_180084010; "ChainingModeECB"
0x18000d083  mov     r9d, 2
0x18000d089  sub     r8, rdi
0x18000d08c  mov     rax, rdi
0x18000d08f  nop
0x18000d090  movzx   edx, word ptr [rax]
0x18000d093  movzx   ecx, word ptr [rax+r8]
0x18000d098  sub     edx, ecx
0x18000d09a  jnz     short loc_18000D0A3
0x18000d09c  add     rax, r9
0x18000d09f  test    ecx, ecx
0x18000d0a1  jnz     short loc_18000D090
0x18000d0a3  test    edx, edx
0x18000d0a5  jz      loc_18000D13B
0x18000d0ab  mov     r8, cs:off_180084018; "ChainingModeCFB"
0x18000d0b2  mov     r9d, 3
0x18000d0b8  sub     r8, rdi
0x18000d0bb  mov     rax, rdi
0x18000d0be  xchg    ax, ax
0x18000d0c0  movzx   edx, word ptr [rax]
0x18000d0c3  movzx   ecx, word ptr [rax+r8]
0x18000d0c8  sub     edx, ecx
0x18000d0ca  jnz     short loc_18000D0D4
0x18000d0cc  add     rax, 2
0x18000d0d0  test    ecx, ecx
0x18000d0d2  jnz     short loc_18000D0C0
0x18000d0d4  test    edx, edx
0x18000d0d6  jz      short loc_18000D13B
0x18000d0d8  mov     r8, cs:off_180084020; "ChainingModeCCM"
0x18000d0df  mov     r9d, 4
0x18000d0e5  sub     r8, rdi
0x18000d0e8  mov     rcx, rdi
0x18000d0eb  nop     dword ptr [rax+rax+00h]
0x18000d0f0  movzx   eax, word ptr [rcx]
0x18000d0f3  movzx   edx, word ptr [rcx+r8]
0x18000d0f8  sub     eax, edx
0x18000d0fa  jnz     short loc_18000D104
0x18000d0fc  add     rcx, 2
0x18000d100  test    edx, edx
0x18000d102  jnz     short loc_18000D0F0
0x18000d104  test    eax, eax
0x18000d106  jz      short loc_18000D13B
0x18000d108  mov     rdx, cs:off_180084028; "ChainingModeGCM"
0x18000d10f  mov     r9d, 5
0x18000d115  sub     rdx, rdi
0x18000d118  nop     dword ptr [rax+rax+00000000h]
0x18000d120  movzx   ecx, word ptr [rdi]
0x18000d123  movzx   eax, word ptr [rdi+rdx]
0x18000d127  sub     ecx, eax
0x18000d129  jnz     short loc_18000D133
0x18000d12b  add     rdi, 2
0x18000d12f  test    eax, eax
0x18000d131  jnz     short loc_18000D120
0x18000d133  test    ecx, ecx
0x18000d135  jnz     loc_18000D24B
0x18000d13b  mov     edx, [rbp+8]
0x18000d13e  lea     rcx, cs:180000000h
0x18000d145  movzx   eax, dx
0x18000d148  dec     eax
0x18000d14a  imul    rax, 70h ; 'p'
0x18000d14e  mov     eax, [rax+rcx+84120h]
0x18000d155  bt      eax, r9d
0x18000d159  jnb     loc_18000D42E
0x18000d15f  mov     eax, r9d
0x18000d162  mov     [rbp+0Ch], r9d
0x18000d166  mov     ecx, ds:rva rgdwDefaultMsgBlockSize[rcx+rax*4]
0x18000d16d  mov     [rbp+14h], ecx
0x18000d170  test    ecx, ecx
0x18000d172  jnz     short loc_18000D17A
0x18000d174  mov     eax, [rbp+10h]
0x18000d177  mov     [rbp+14h], eax
0x18000d17a  cmp     r15d, 4D535341h
0x18000d181  jnz     short loc_18000D19F
0x18000d183  cmp     edx, 10002h
0x18000d189  jnz     short loc_18000D19F
0x18000d18b  cmp     r9d, 5
0x18000d18f  mov     eax, 0C80h
0x18000d194  mov     ecx, 250h
0x18000d199  cmovnz  eax, ecx
0x18000d19c  mov     [rbp+1Ch], eax
0x18000d19f  mov     eax, r14d
0x18000d1a2  add     rsp, 48h
0x18000d1a6  pop     r15
0x18000d1a8  pop     r14
0x18000d1aa  pop     rdi
0x18000d1ab  pop     rsi
0x18000d1ac  pop     rbp
0x18000d1ad  pop     rbx
0x18000d1ae  retn
0x18000d1b0  lea     rdx, aMessageblockle; "MessageBlockLength"
0x18000d1b7  mov     rcx, rbx; String1
0x18000d1ba  call    wcscmp_0
0x18000d1bf  test    eax, eax
0x18000d1c1  jz      loc_18000D4F2
0x18000d1c7  sub     r15d, 4D535341h
0x18000d1ce  jnz     loc_18000D290
0x18000d1d4  lea     rdx, aEffectivekeyle; "EffectiveKeyLength"
0x18000d1db  mov     rcx, rbx; String1
0x18000d1de  call    wcscmp_0
0x18000d1e3  lea     rbx, WPP_GLOBAL_Control
0x18000d1ea  test    eax, eax
0x18000d1ec  jz      loc_18000D5E8
0x18000d1f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1f9  lea     rdi, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d200  cmp     rcx, rbx
0x18000d203  jz      short loc_18000D20F
0x18000d205  test    byte ptr [rcx+1Ch], 1
0x18000d209  jnz     loc_18000D2F8
0x18000d20f  mov     r14d, 0C00000BBh
0x18000d215  cmp     rcx, rbx
0x18000d218  jz      short loc_18000D19F
0x18000d21a  test    byte ptr [rcx+1Ch], 1
0x18000d21e  jz      loc_18000D19F
0x18000d224  mov     [rsp+78h+var_48], 9FDh
0x18000d22c  mov     [rsp+78h+var_50], rdi
0x18000d231  mov     [rsp+78h+var_58], r14d
0x18000d236  mov     rcx, [rcx+10h]
0x18000d23a  lea     r9, aStatus; "Status"
0x18000d241  call    WPP_SF_sDsd
0x18000d246  jmp     loc_18000D19F
0x18000d24b  mov     r14d, 0C000000Dh
0x18000d251  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d258  lea     rbx, WPP_GLOBAL_Control
0x18000d25f  cmp     rcx, rbx
0x18000d262  jz      loc_18000D19F
0x18000d268  test    byte ptr [rcx+1Ch], 1
0x18000d26c  jz      loc_18000D19F
0x18000d272  mov     [rsp+78h+var_48], 9A6h
0x18000d27a  lea     rdi, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d281  mov     [rsp+78h+var_50], rdi
0x18000d286  mov     [rsp+78h+var_58], 0C000000Dh
0x18000d28e  jmp     short loc_18000D236
0x18000d290  cmp     r15d, 0Ah
0x18000d294  jnz     loc_18000D56F
0x18000d29a  movzx   ecx, word ptr [rbx]
0x18000d29d  mov     eax, 49h ; 'I'
0x18000d2a2  xor     r14d, r14d
0x18000d2a5  sub     ecx, eax
0x18000d2a7  jnz     short loc_18000D2BC
0x18000d2a9  movzx   ecx, word ptr [rbx+2]
0x18000d2ad  sub     ecx, 56h ; 'V'
0x18000d2b0  jnz     short loc_18000D2BC
0x18000d2b2  movzx   ecx, word ptr [rbx+4]
0x18000d2b6  movzx   eax, r14w
0x18000d2ba  sub     ecx, eax
0x18000d2bc  test    ecx, ecx
0x18000d2be  jnz     loc_18000D476
0x18000d2c4  cmp     dword ptr [rbp+8], 10001h
0x18000d2cb  jz      short loc_18000D329
0x18000d2cd  mov     eax, [rbp+10h]
0x18000d2d0  cmp     esi, eax
0x18000d2d2  jnz     loc_18000D3D3
0x18000d2d8  mov     r8d, eax; Size
0x18000d2db  lea     rcx, [rbp+28h]; void *
0x18000d2df  mov     rdx, rdi; Src
0x18000d2e2  call    memcpy_0
0x18000d2e7  mov     eax, r14d
0x18000d2ea  add     rsp, 48h
0x18000d2ee  pop     r15
0x18000d2f0  pop     r14
0x18000d2f2  pop     rdi
0x18000d2f3  pop     rsi
0x18000d2f4  pop     rbp
0x18000d2f5  pop     rbx
0x18000d2f6  retn
0x18000d2f8  mov     rcx, [rcx+10h]
0x18000d2fc  lea     r9, aStatus; "Status"
0x18000d303  mov     [rsp+78h+var_48], 88Fh
0x18000d30b  mov     [rsp+78h+var_50], rdi
0x18000d310  mov     [rsp+78h+var_58], 0C00000BBh
0x18000d318  call    WPP_SF_sDsd
0x18000d31d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d324  jmp     loc_18000D20F
0x18000d329  mov     r14d, 0C00000BBh
0x18000d32f  mov     esi, r14d
0x18000d332  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d339  lea     rbx, WPP_GLOBAL_Control
0x18000d340  lea     rdi, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d347  cmp     rcx, rbx
0x18000d34a  jz      short loc_18000D356
0x18000d34c  test    byte ptr [rcx+1Ch], 1
0x18000d350  jnz     loc_18000D58C
0x18000d356  mov     r9d, 0A0Ah
0x18000d35c  mov     r8, rdi
0x18000d35f  mov     ecx, esi
0x18000d361  lea     rdx, aStatus; "Status"
0x18000d368  call    DebugTraceError
0x18000d36d  mov     eax, r14d
0x18000d370  add     rsp, 48h
0x18000d374  pop     r15
0x18000d376  pop     r14
0x18000d378  pop     rdi
0x18000d379  pop     rsi
0x18000d37a  pop     rbp
0x18000d37b  pop     rbx
0x18000d37c  retn
0x18000d37e  cmp     r15d, 4D53534Bh
0x18000d385  jz      loc_18000CFE3
0x18000d38b  mov     r14d, 0C0000008h
0x18000d391  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d398  lea     rbx, WPP_GLOBAL_Control
0x18000d39f  cmp     rcx, rbx
0x18000d3a2  jz      loc_18000D19F
0x18000d3a8  test    byte ptr [rcx+1Ch], 1
0x18000d3ac  jz      loc_18000D19F
0x18000d3b2  mov     [rsp+78h+var_48], 985h
0x18000d3ba  lea     rdi, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d3c1  mov     [rsp+78h+var_50], rdi
0x18000d3c6  mov     [rsp+78h+var_58], 0C0000008h
0x18000d3ce  jmp     loc_18000D236
0x18000d3d3  mov     r14d, 0C000000Dh
0x18000d3d9  mov     esi, r14d
0x18000d3dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3e3  lea     rbx, WPP_GLOBAL_Control
0x18000d3ea  lea     rdi, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d3f1  cmp     rcx, rbx
0x18000d3f4  jz      loc_18000D356
0x18000d3fa  test    byte ptr [rcx+1Ch], 1
0x18000d3fe  jz      loc_18000D356
0x18000d404  mov     [rsp+78h+var_48], 710h
0x18000d40c  mov     [rsp+78h+var_50], rdi
0x18000d411  mov     [rsp+78h+var_58], 0C000000Dh
0x18000d419  mov     rcx, [rcx+10h]
0x18000d41d  lea     r9, aStatus; "Status"
0x18000d424  call    WPP_SF_sDsd
0x18000d429  jmp     loc_18000D356
0x18000d42e  mov     r14d, 0C00000BBh
0x18000d434  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d43b  lea     rbx, WPP_GLOBAL_Control
0x18000d442  cmp     rcx, rbx
0x18000d445  jz      loc_18000D19F
0x18000d44b  test    byte ptr [rcx+1Ch], 1
0x18000d44f  jz      loc_18000D19F
0x18000d455  mov     [rsp+78h+var_48], 9ADh
0x18000d45d  lea     rdi, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d464  mov     [rsp+78h+var_50], rdi
0x18000d469  mov     [rsp+78h+var_58], 0C00000BBh
0x18000d471  jmp     loc_18000D236
0x18000d476  lea     rdx, aEffectivekeyle; "EffectiveKeyLength"
0x18000d47d  mov     rcx, rbx; String1
0x18000d480  call    wcscmp_0
0x18000d485  test    eax, eax
0x18000d487  jnz     loc_18000D5DD
0x18000d48d  cmp     dword ptr [rbp+8], 10007h
  ... truncated ...
```
