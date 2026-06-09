# Marshal::JsonParser::ParseNumber(void)

- ea: `0x14000b040`
- end: `0x14000b3ec`
- name: `?ParseNumber@JsonParser@Marshal@@QEAA?AUNumber@12@XZ`
- size: `940`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140004748`
- `0x14000cd1c`

## callees

- `0x140002310`
- `0x140002ed8`
- `0x140006790`
- `0x14000b040`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14000b2e1`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14000b2e1`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x14000b2ce`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x14000b2ce`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b28d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b28d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x14000b2b7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x14000b2b7`

## pseudocode

```c
__int64 __fastcall Marshal::JsonParser::ParseNumber(_QWORD *a1, __int64 a2)
{
  unsigned __int64 v4; // r9
  unsigned __int64 v5; // r8
  int v6; // ecx
  char v7; // r15
  __int64 v8; // rbx
  __int64 v9; // r10
  char v10; // si
  unsigned __int64 v11; // r11
  __int64 v12; // rdx
  __int64 v13; // rbx
  int v14; // eax
  unsigned int v15; // ecx
  char *v16; // rsi
  __int64 v17; // rax
  unsigned __int64 v18; // r8
  _DWORD *v19; // rax
  _DWORD *v20; // r15
  char *v21; // rax
  __int64 v22; // rax
  __int64 v23; // r9
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // r8
  bool v27; // cf
  int v29; // [rsp+20h] [rbp-58h] BYREF
  int v30; // [rsp+24h] [rbp-54h] BYREF
  int v31; // [rsp+28h] [rbp-50h] BYREF
  int v32; // [rsp+2Ch] [rbp-4Ch] BYREF
  int pExceptionObject; // [rsp+30h] [rbp-48h] BYREF
  char *v34; // [rsp+38h] [rbp-40h] BYREF

  v4 = a1[1];
  v5 = a1[2];
  if ( v5 >= v4 )
  {
    v6 = -1;
    goto LABEL_8;
  }
  v6 = *(unsigned __int16 *)(*a1 + 2 * v5);
  if ( v6 != 45 )
  {
LABEL_8:
    v7 = 0;
    v9 = 1;
    v8 = 1;
    goto LABEL_9;
  }
  v7 = 1;
  if ( v5 + 1 >= v4 )
    v6 = -1;
  else
    v6 = *(unsigned __int16 *)(*a1 + 2 * v5 + 2);
  v8 = 2;
  v9 = 2;
LABEL_9:
  v10 = 0;
  if ( v6 == 48 )
  {
    v11 = 0;
    if ( v5 + v8 >= v4 )
      LODWORD(v12) = -1;
    else
      LODWORD(v12) = *(unsigned __int16 *)(*a1 + 2 * (v5 + v8));
  }
  else
  {
    if ( (unsigned int)(v6 - 49) > 8 )
    {
      pExceptionObject = 14;
      throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
    }
    v8 = v9;
    v11 = v6 - 48;
    if ( v5 + v9 >= v4 )
      goto LABEL_45;
    v12 = *(unsigned __int16 *)(*a1 + 2 * (v5 + v9));
    if ( (unsigned int)v12 >= 0x30 )
    {
      while ( (unsigned int)v12 <= 0x39 )
      {
        if ( v11 > 0x1999999999999999LL || v11 == 0x1999999999999999LL && (unsigned int)(v12 - 48) > 5 )
          v10 = 1;
        v11 = v12 + 2 * (v11 + 4 * (v11 - 6));
        ++v8;
        if ( v5 + v8 >= v4 )
          goto LABEL_45;
        v12 = *(unsigned __int16 *)(*a1 + 2 * (v5 + v8));
        if ( (unsigned int)v12 < 0x30 )
          break;
      }
    }
  }
  if ( (_DWORD)v12 == 46 )
  {
    v13 = v8 + 1;
    if ( v13 + v5 >= v4 || (unsigned int)*(unsigned __int16 *)(*a1 + 2 * (v13 + v5)) - 48 > 9 )
    {
      v29 = 14;
      throw (Marshal::JsonParser::ParseException *)&v29;
    }
    v10 = 1;
    v8 = v13 + 1;
    if ( v5 + v8 >= v4 )
      goto LABEL_45;
    LODWORD(v12) = *(unsigned __int16 *)(*a1 + 2 * (v5 + v8));
    if ( (unsigned int)v12 >= 0x30 )
    {
      while ( (unsigned int)v12 <= 0x39 )
      {
        ++v8;
        if ( v5 + v8 >= v4 )
          goto LABEL_45;
        LODWORD(v12) = *(unsigned __int16 *)(*a1 + 2 * (v5 + v8));
        if ( (unsigned int)v12 < 0x30 )
          goto LABEL_33;
      }
    }
  }
  if ( (_DWORD)v12 == 101 )
    goto LABEL_34;
LABEL_33:
  if ( (_DWORD)v12 == 69 )
  {
LABEL_34:
    if ( ++v8 + v5 >= v4 )
      goto LABEL_79;
    v14 = *(unsigned __int16 *)(*a1 + 2 * (v8 + v5));
    if ( v14 == 43 || v14 == 45 )
    {
      if ( ++v8 + v5 >= v4 )
        v14 = -1;
      else
        v14 = *(unsigned __int16 *)(*a1 + 2 * (v8 + v5));
    }
    if ( (unsigned int)(v14 - 48) > 9 )
    {
LABEL_79:
      v30 = 14;
      throw (Marshal::JsonParser::ParseException *)&v30;
    }
    v10 = 1;
    do
    {
      ++v8;
      if ( v5 + v8 >= v4 )
        break;
      v15 = *(unsigned __int16 *)(*a1 + 2 * (v5 + v8));
      if ( v15 < 0x30 )
        break;
    }
    while ( v15 <= 0x39 );
  }
LABEL_45:
  if ( v7 && v11 > 0x8000000000000000uLL )
    v10 = 1;
  *(_OWORD *)a2 = 0;
  if ( v10 )
  {
    v16 = (char *)(a1 + 8);
    v17 = a1[2];
    v18 = a1[1];
    if ( v18 >= v17 + v8 )
      v18 = v17 + v8;
    std::wstring::_Assign<unsigned short>(
      (void **)a1 + 8,
      (const void *)(*a1 + 2 * v17),
      (__int64)(*a1 + 2 * v18 - (*a1 + 2 * v17)) >> 1);
    *(_DWORD *)(a2 + 8) = 2;
    v19 = (_DWORD *)_o__errno();
    v20 = v19;
    if ( a1[11] > 7u )
      v16 = *(char **)v16;
    v34 = 0;
    *v19 = 0;
    _o_wcstod(v16, &v34);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v21 = v34;
      if ( v16 == v34 )
        std::_Xinvalid_argument("invalid stod argument");
      if ( *v20 == 34 )
        std::_Xout_of_range("stod argument out of range");
      v22 = (v21 - v16) >> 1;
      *(_QWORD *)a2 = 0;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', 0) )
      {
        v32 = 14;
        throw (Marshal::JsonParser::ParseException *)&v32;
      }
    }
    if ( v22 != a1[10] )
    {
      v31 = 14;
      throw (Marshal::JsonParser::ParseException *)&v31;
    }
  }
  else
  {
    if ( v7 )
    {
      *(_DWORD *)(a2 + 8) = 1;
      v11 = -(__int64)v11;
    }
    *(_QWORD *)a2 = v11;
  }
  v23 = a1[2];
  v24 = a1[1];
  v25 = v24;
  if ( v24 >= v23 + v8 )
    v25 = v23 + v8;
  a1[3] = v25;
  while ( 1 )
  {
    v26 = v23 + v8;
    v27 = v24 < v23 + v8;
    if ( v24 <= v23 + v8 )
      break;
    if ( *(_WORD *)(*a1 + 2 * v26) != 9
      && *(_WORD *)(*a1 + 2 * v26) != 10
      && *(_WORD *)(*a1 + 2 * v26) != 13
      && *(_WORD *)(*a1 + 2 * v26) != 32 )
    {
      v27 = v24 < v26;
      break;
    }
    ++v8;
  }
  if ( !v27 )
    v24 = v23 + v8;
  a1[2] = v24;
  return a2;
}

```

## disassembly

```asm
0x14000b040  mov     [rsp+arg_10], rbx
0x14000b045  push    rsi
0x14000b046  push    rdi
0x14000b047  push    r12
0x14000b049  push    r14
0x14000b04b  push    r15
0x14000b04d  sub     rsp, 50h
0x14000b051  mov     rax, cs:__security_cookie
0x14000b058  xor     rax, rsp
0x14000b05b  mov     [rsp+78h+var_38], rax
0x14000b060  mov     r12, rdx
0x14000b063  mov     rdi, rcx
0x14000b066  mov     r9, [rcx+8]
0x14000b06a  mov     r8, [rcx+10h]
0x14000b06e  cmp     r8, r9
0x14000b071  jnb     short loc_14000B0A8
0x14000b073  mov     rax, [rcx]
0x14000b076  movzx   ecx, word ptr [rax+r8*2]
0x14000b07b  cmp     ecx, 2Dh ; '-'
0x14000b07e  jnz     short loc_14000B0AB
0x14000b080  lea     r14d, [rcx-2Ch]
0x14000b084  mov     r15b, r14b
0x14000b087  lea     rax, [r8+1]
0x14000b08b  cmp     rax, r9
0x14000b08e  jnb     short loc_14000B09B
0x14000b090  mov     rax, [rdi]
0x14000b093  movzx   ecx, word ptr [rax+r8*2+2]
0x14000b099  jmp     short loc_14000B09E
0x14000b09b  or      ecx, 0FFFFFFFFh
0x14000b09e  mov     ebx, 2
0x14000b0a3  mov     r10d, ebx
0x14000b0a6  jmp     short loc_14000B0BA
0x14000b0a8  or      ecx, 0FFFFFFFFh
0x14000b0ab  xor     r15b, r15b
0x14000b0ae  mov     r14d, 1
0x14000b0b4  mov     r10d, r14d
0x14000b0b7  mov     ebx, r14d
0x14000b0ba  xor     sil, sil
0x14000b0bd  cmp     ecx, 30h ; '0'
0x14000b0c0  jnz     short loc_14000B0DC
0x14000b0c2  xor     r11d, r11d
0x14000b0c5  lea     rcx, [r8+rbx]
0x14000b0c9  cmp     rcx, r9
0x14000b0cc  jnb     short loc_14000B0D7
0x14000b0ce  mov     rax, [rdi]
0x14000b0d1  movzx   edx, word ptr [rax+rcx*2]
0x14000b0d5  jmp     short loc_14000B153
0x14000b0d7  or      edx, 0FFFFFFFFh
0x14000b0da  jmp     short loc_14000B153
0x14000b0dc  lea     eax, [rcx-31h]
0x14000b0df  cmp     eax, 8
0x14000b0e2  ja      loc_14000B384
0x14000b0e8  mov     rbx, r10
0x14000b0eb  lea     eax, [rcx-30h]
0x14000b0ee  movsxd  r11, eax
0x14000b0f1  lea     rcx, [r8+r10]
0x14000b0f5  cmp     rcx, r9
0x14000b0f8  jnb     loc_14000B227
0x14000b0fe  mov     rax, [rdi]
0x14000b101  movzx   edx, word ptr [rax+rcx*2]
0x14000b105  cmp     edx, 30h ; '0'
0x14000b108  jb      short loc_14000B153
0x14000b10a  mov     r10, 1999999999999999h
0x14000b114  cmp     edx, 39h ; '9'
0x14000b117  ja      short loc_14000B153
0x14000b119  cmp     r11, r10
0x14000b11c  ja      short loc_14000B128
0x14000b11e  jnz     short loc_14000B12B
0x14000b120  lea     eax, [rdx-30h]
0x14000b123  cmp     eax, 5
0x14000b126  jbe     short loc_14000B12B
0x14000b128  mov     sil, r14b
0x14000b12b  lea     rcx, [r11-6]
0x14000b12f  lea     rcx, [r11+rcx*4]
0x14000b133  lea     r11, [rdx+rcx*2]
0x14000b137  add     rbx, r14
0x14000b13a  lea     rcx, [r8+rbx]
0x14000b13e  cmp     rcx, r9
0x14000b141  jnb     loc_14000B227
0x14000b147  mov     rax, [rdi]
0x14000b14a  movzx   edx, word ptr [rax+rcx*2]
0x14000b14e  cmp     edx, 30h ; '0'
0x14000b151  jnb     short loc_14000B114
0x14000b153  cmp     edx, 2Eh ; '.'
0x14000b156  jnz     short loc_14000B1B6
0x14000b158  inc     rbx
0x14000b15b  lea     rcx, [rbx+r8]
0x14000b15f  cmp     rcx, r9
0x14000b162  jnb     loc_14000B39E
0x14000b168  mov     rax, [rdi]
0x14000b16b  movzx   ecx, word ptr [rax+rcx*2]
0x14000b16f  sub     ecx, 30h ; '0'
0x14000b172  cmp     ecx, 9
0x14000b175  ja      loc_14000B39E
0x14000b17b  mov     sil, r14b
0x14000b17e  add     rbx, r14
0x14000b181  lea     rcx, [r8+rbx]
0x14000b185  cmp     rcx, r9
0x14000b188  jnb     loc_14000B227
0x14000b18e  movzx   edx, word ptr [rax+rcx*2]
0x14000b192  cmp     edx, 30h ; '0'
0x14000b195  jb      short loc_14000B1B6
0x14000b197  cmp     edx, 39h ; '9'
0x14000b19a  ja      short loc_14000B1B6
0x14000b19c  add     rbx, r14
0x14000b19f  lea     rcx, [r8+rbx]
0x14000b1a3  cmp     rcx, r9
0x14000b1a6  jnb     short loc_14000B227
0x14000b1a8  mov     rax, [rdi]
0x14000b1ab  movzx   edx, word ptr [rax+rcx*2]
0x14000b1af  cmp     edx, 30h ; '0'
0x14000b1b2  jnb     short loc_14000B197
0x14000b1b4  jmp     short loc_14000B1BB
0x14000b1b6  cmp     edx, 65h ; 'e'
0x14000b1b9  jz      short loc_14000B1C0
0x14000b1bb  cmp     edx, 45h ; 'E'
0x14000b1be  jnz     short loc_14000B227
0x14000b1c0  inc     rbx
0x14000b1c3  lea     rcx, [rbx+r8]
0x14000b1c7  cmp     rcx, r9
0x14000b1ca  jnb     loc_14000B3B8
0x14000b1d0  mov     rax, [rdi]
0x14000b1d3  movzx   eax, word ptr [rax+rcx*2]
0x14000b1d7  cmp     eax, 2Bh ; '+'
0x14000b1da  jz      short loc_14000B1E1
0x14000b1dc  cmp     eax, 2Dh ; '-'
0x14000b1df  jnz     short loc_14000B1F9
0x14000b1e1  add     rbx, r14
0x14000b1e4  lea     rcx, [rbx+r8]
0x14000b1e8  cmp     rcx, r9
0x14000b1eb  jnb     short loc_14000B1F6
0x14000b1ed  mov     rax, [rdi]
0x14000b1f0  movzx   eax, word ptr [rax+rcx*2]
0x14000b1f4  jmp     short loc_14000B1F9
0x14000b1f6  or      eax, 0FFFFFFFFh
0x14000b1f9  add     eax, 0FFFFFFD0h
0x14000b1fc  cmp     eax, 9
0x14000b1ff  ja      loc_14000B3B8
0x14000b205  mov     sil, r14b
0x14000b208  jmp     short loc_14000B20F
0x14000b20a  cmp     ecx, 39h ; '9'
0x14000b20d  ja      short loc_14000B227
0x14000b20f  add     rbx, r14
0x14000b212  lea     rcx, [r8+rbx]
0x14000b216  cmp     rcx, r9
0x14000b219  jnb     short loc_14000B227
0x14000b21b  mov     rax, [rdi]
0x14000b21e  movzx   ecx, word ptr [rax+rcx*2]
0x14000b222  cmp     ecx, 30h ; '0'
0x14000b225  jnb     short loc_14000B20A
0x14000b227  test    r15b, r15b
0x14000b22a  jz      short loc_14000B241
0x14000b22c  movzx   esi, sil
0x14000b230  mov     rax, 8000000000000000h
0x14000b23a  cmp     r11, rax
0x14000b23d  cmova   esi, r14d
0x14000b241  xorps   xmm0, xmm0
0x14000b244  movups  xmmword ptr [r12], xmm0
0x14000b249  test    sil, sil
0x14000b24c  jz      loc_14000B2FF
0x14000b252  lea     rsi, [rdi+40h]
0x14000b256  mov     r9, [rdi]
0x14000b259  mov     rax, [rdi+10h]
0x14000b25d  lea     rcx, [rax+rbx]
0x14000b261  mov     r8, [rdi+8]
0x14000b265  lea     rdx, [r9+rax*2]
0x14000b269  cmp     r8, rcx
0x14000b26c  cmovnb  r8, rcx
0x14000b270  add     r8, r8
0x14000b273  sub     r8, rdx
0x14000b276  add     r8, r9
0x14000b279  sar     r8, 1
0x14000b27c  mov     rcx, rsi
0x14000b27f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x14000b284  mov     dword ptr [r12+8], 2
0x14000b28d  call    cs:__imp__o__errno
0x14000b293  mov     r15, rax
0x14000b296  cmp     qword ptr [rsi+18h], 7
0x14000b29b  jbe     short loc_14000B2A0
0x14000b29d  mov     rsi, [rsi]
0x14000b2a0  mov     [rsp+78h+var_40], 0
0x14000b2a9  mov     dword ptr [rax], 0
0x14000b2af  lea     rdx, [rsp+78h+var_40]
0x14000b2b4  mov     rcx, rsi
0x14000b2b7  call    cs:__imp__o_wcstod
0x14000b2bd  mov     rax, [rsp+78h+var_40]
0x14000b2c2  cmp     rsi, rax
0x14000b2c5  jnz     short loc_14000B2D4
0x14000b2c7  lea     rcx, aInvalidStodArg; "invalid stod argument"
0x14000b2ce  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x14000b2d4  cmp     dword ptr [r15], 22h ; '"'
0x14000b2d8  jnz     short loc_14000B2E7
0x14000b2da  lea     rcx, aStodArgumentOu; "stod argument out of range"
0x14000b2e1  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x14000b2e7  sub     rax, rsi
0x14000b2ea  sar     rax, 1
0x14000b2ed  movsd   qword ptr [r12], xmm0
0x14000b2f3  cmp     rax, [rdi+50h]
0x14000b2f7  jnz     loc_14000B3D2
0x14000b2fd  jmp     short loc_14000B310
0x14000b2ff  test    r15b, r15b
0x14000b302  jz      short loc_14000B30C
0x14000b304  mov     [r12+8], r14d
0x14000b309  neg     r11
0x14000b30c  mov     [r12], r11
0x14000b310  mov     r9, [rdi+10h]
0x14000b314  lea     rcx, [r9+rbx]
0x14000b318  mov     rdx, [rdi+8]
0x14000b31c  mov     rax, rdx
0x14000b31f  cmp     rdx, rcx
0x14000b322  cmovnb  rax, rcx
0x14000b326  mov     [rdi+18h], rax
0x14000b32a  lea     r8, [r9+rbx]
0x14000b32e  cmp     rdx, r8
0x14000b331  jbe     short loc_14000B357
0x14000b333  mov     rax, [rdi]
0x14000b336  movzx   ecx, word ptr [rax+r8*2]
0x14000b33b  sub     ecx, 9
0x14000b33e  jz      short loc_14000B34F
0x14000b340  sub     ecx, 1
0x14000b343  jz      short loc_14000B34F
0x14000b345  sub     ecx, 3
0x14000b348  jz      short loc_14000B34F
0x14000b34a  cmp     ecx, 13h
0x14000b34d  jnz     short loc_14000B354
0x14000b34f  add     rbx, r14
0x14000b352  jmp     short loc_14000B32A
0x14000b354  cmp     rdx, r8
0x14000b357  cmovnb  rdx, r8
0x14000b35b  mov     [rdi+10h], rdx
0x14000b35f  mov     rax, r12
0x14000b362  mov     rcx, [rsp+78h+var_38]
0x14000b367  xor     rcx, rsp; StackCookie
0x14000b36a  call    __security_check_cookie
0x14000b36f  mov     rbx, [rsp+78h+arg_10]
0x14000b377  add     rsp, 50h
0x14000b37b  pop     r15
0x14000b37d  pop     r14
0x14000b37f  pop     r12
0x14000b381  pop     rdi
0x14000b382  pop     rsi
0x14000b383  retn
0x14000b384  mov     [rsp+78h+pExceptionObject], 0Eh
0x14000b38c  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14000b393  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x14000b398  call    _CxxThrowException_0
0x14000b39e  mov     [rsp+78h+var_58], 0Eh
0x14000b3a6  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14000b3ad  lea     rcx, [rsp+78h+var_58]; pExceptionObject
0x14000b3b2  call    _CxxThrowException_0
0x14000b3b8  mov     [rsp+78h+var_54], 0Eh
0x14000b3c0  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14000b3c7  lea     rcx, [rsp+78h+var_54]; pExceptionObject
0x14000b3cc  call    _CxxThrowException_0
0x14000b3d2  mov     [rsp+78h+var_50], 0Eh
0x14000b3da  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14000b3e1  lea     rcx, [rsp+78h+var_50]; pExceptionObject
0x14000b3e6  call    _CxxThrowException_0
```
