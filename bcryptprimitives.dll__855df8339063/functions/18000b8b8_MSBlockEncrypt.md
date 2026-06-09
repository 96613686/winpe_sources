# MSBlockEncrypt

- ea: `0x18000b8b8`
- end: `0x18000c033`
- name: `MSBlockEncrypt`
- size: `1915`
- prototype: `__int64 __fastcall(__int64, __int64, const void *, unsigned int, unsigned __int64, unsigned int, unsigned __int64, unsigned int, int *, int, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000b420`

## callees

- `0x18000adc0`
- `0x18000b8b8`
- `0x18000ecb0`
- `0x18000ee60`
- `0x180063170`
- `0x180063180`
- `0x18007f790`
- `0x180083010`

## string_xrefs

- `0x18000bdae`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x18000beec`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x18000bf2f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x18000bf4e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x18000bfc4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x18007fe8b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x18007ffde`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`

## pseudocode

```c
__int64 __fastcall MSBlockEncrypt(
        __int64 a1,
        __int64 a2,
        const void *a3,
        unsigned int a4,
        unsigned __int64 a5,
        unsigned int a6,
        unsigned __int64 a7,
        unsigned int a8,
        int *a9,
        int a10,
        char a11)
{
  int v11; // ebx
  unsigned int v12; // r15d
  const void *v13; // r14
  unsigned int v14; // edi
  size_t v15; // rsi
  unsigned __int64 v16; // r11
  int v17; // r10d
  __int64 v18; // r8
  unsigned __int64 v19; // r9
  int v20; // ecx
  unsigned int v21; // edx
  unsigned int v22; // r13d
  unsigned int v23; // r15d
  _DWORD *v24; // r13
  const void *v25; // r8
  __int64 v26; // rdi
  int v27; // r14d
  __int64 v28; // r10
  __int64 v29; // r12
  int v30; // ebx
  __int64 v31; // r12
  size_t v32; // rax
  int v33; // ebx
  int v34; // edx
  _BYTE *v35; // rax
  size_t v36; // rcx
  int v38; // ebx
  int v39; // ebx
  int v40; // ebx
  int v41; // edx
  __int64 v42; // rax
  __int64 v43; // r14
  size_t v44; // rdi
  _BYTE *v45; // rdx
  __int64 v46; // r9
  __int64 v47; // rcx
  __int64 v48; // r9
  __int64 v49; // rcx
  __int64 v50; // rax
  __int64 v51; // r9
  __int64 v52; // rcx
  __int64 v53; // rdx
  int v54; // eax
  int v55; // [rsp+70h] [rbp-90h]
  int v57; // [rsp+80h] [rbp-80h]
  const void *v59; // [rsp+88h] [rbp-78h]
  __int64 v60; // [rsp+90h] [rbp-70h]
  unsigned int v62; // [rsp+A8h] [rbp-58h]
  __int128 v63; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v64; // [rsp+C0h] [rbp-40h]
  __int128 v65; // [rsp+D0h] [rbp-30h]
  int *v66; // [rsp+E0h] [rbp-20h]
  _BYTE v67[16]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v68; // [rsp+F8h] [rbp-8h] BYREF
  char v69; // [rsp+108h] [rbp+8h] BYREF

  v11 = *(_DWORD *)(a1 + 12);
  v12 = *(_DWORD *)(a1 + 20);
  v13 = a3;
  v14 = a4;
  v15 = *(unsigned int *)(a1 + 16);
  v16 = a5;
  v17 = a10;
  v66 = a9;
  v18 = a1;
  v68 = a2;
  v19 = a7;
  v20 = (unsigned int)(v11 - 4) <= 1;
  v62 = v12;
  v57 = v20;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  if ( !a10 )
  {
    v21 = a6 % v12;
    v22 = a6;
    v55 = a6;
    if ( a6 % v12 )
    {
      v33 = -1073741306;
      DebugTraceError(3221225990LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c", 487);
      v34 = a6;
      goto LABEL_32;
    }
    v23 = a6;
LABEL_4:
    if ( !a7 && ((unsigned int)(v11 - 4) > 1 || a5) )
      goto LABEL_27;
    if ( v22 > a8 )
    {
      v33 = -1073741789;
      v46 = 506;
      v47 = 3221225507LL;
LABEL_118:
      DebugTraceError(v47, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c", v46);
      goto LABEL_28;
    }
    if ( !a5 && (unsigned int)(v11 - 4) > 1 || a5 + a6 < a5 || a7 + a8 < a7 )
    {
      v46 = 515;
      goto LABEL_117;
    }
    if ( a10 )
    {
      if ( (unsigned int)v15 > 0x10 )
      {
        v33 = -1073741789;
        v48 = 527;
        v49 = 3221225507LL;
        goto LABEL_93;
      }
      v43 = a6 - v23;
      v44 = v15 - (v43 & (v15 - 1));
      if ( v43 + v44 <= 0x10 )
      {
        v45 = (_BYTE *)(a5 + v23);
        if ( v67 != v45 && a6 != v23 )
          memcpy_0(v67, v45, (unsigned int)v43);
        memset_0(&v67[v43], v44, v15 - (v43 & (v15 - 1)));
        v20 = (unsigned int)(v11 - 4) <= 1;
        v16 = a5;
        v19 = a7;
        v17 = a10;
        v18 = a1;
      }
      v13 = a3;
      v14 = a4;
    }
    if ( !v23 && !v20 && !v17 )
    {
      v33 = 0;
      goto LABEL_56;
    }
    v24 = (_DWORD *)(v18 + 40);
    if ( v13 )
    {
      if ( v14 < (unsigned int)v15 && !v20 )
      {
        v33 = -1073741306;
        v46 = 570;
        v47 = 3221225990LL;
        goto LABEL_118;
      }
      if ( v11 == 2 )
      {
        v33 = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v21,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
            65);
        goto LABEL_28;
      }
      v25 = v13;
    }
    else
    {
      v25 = (const void *)(v18 + 40);
    }
    v59 = v25;
    if ( !v20 )
    {
      v26 = 0;
LABEL_17:
      v27 = 0;
      goto LABEL_18;
    }
    if ( !v17 )
    {
      v42 = validateAuthCipherModeInfo(v68);
      v26 = v42;
      if ( v42 )
      {
        v20 = (*(_DWORD *)(v42 + 80) >> 1) & 1;
        v27 = *(_DWORD *)(v42 + 80) & 1;
        if ( !v27 )
          goto LABEL_17;
        if ( !(a6 % (unsigned int)v15) )
        {
LABEL_18:
          v28 = 14LL * ((unsigned int)*(unsigned __int16 *)(a1 + 8) - 1);
          v60 = v28 * 8;
          v29 = a1 + HIDWORD(rgSymmAlgorithmDefaults[v28 + 8]);
          v30 = v11 - 1;
          if ( !v30 )
          {
            ((void (__fastcall *)(__int64, _QWORD, const void *, unsigned __int64, unsigned int, unsigned __int64, int))rgSymmAlgorithmDefaults[v28 + 10])(
              v29,
              (unsigned int)v15,
              v25,
              v16,
              v23,
              v19,
              1);
            if ( a10 )
              (*(void (__fastcall **)(__int64, _QWORD, const void *, _BYTE *, _DWORD, unsigned __int64, int))((char *)&rgSymmAlgorithmDefaults[10] + v60))(
                v29,
                (unsigned int)v15,
                v59,
                v67,
                v15,
                a7 + v23,
                1);
LABEL_21:
            v31 = a1;
            goto LABEL_22;
          }
          v38 = v30 - 1;
          if ( !v38 )
          {
            ((void (__fastcall *)(__int64, _QWORD, unsigned __int64, _QWORD, unsigned __int64, int))rgSymmAlgorithmDefaults[v28 + 9])(
              v29,
              (unsigned int)v15,
              v16,
              v23,
              v19,
              1);
            if ( a10 )
              (*(void (__fastcall **)(__int64, _QWORD, _BYTE *, _QWORD, unsigned __int64, int))((char *)&rgSymmAlgorithmDefaults[9]
                                                                                              + v60))(
                v29,
                (unsigned int)v15,
                v67,
                (unsigned int)v15,
                a7 + v23,
                1);
            goto LABEL_21;
          }
          v39 = v38 - 1;
          if ( !v39 )
          {
            ((void (__fastcall *)(__int64, _QWORD, _QWORD, const void *, unsigned __int64, unsigned int, unsigned __int64, int))rgSymmAlgorithmDefaults[v28 + 11])(
              v29,
              (unsigned int)v15,
              v62,
              v25,
              v16,
              v23,
              v19,
              1);
            if ( a10 )
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD, const void *, _BYTE *, _DWORD, unsigned __int64, int))((char *)&rgSymmAlgorithmDefaults[11] + v60))(
                v29,
                (unsigned int)v15,
                v62,
                v59,
                v67,
                v15,
                a7 + v23,
                1);
            goto LABEL_21;
          }
          v40 = v39 - 1;
          if ( v40 )
          {
            if ( v40 != 1 )
            {
              v33 = -1073741816;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  a1,
                  (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
                  (unsigned int)"Status",
                  8,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
                  59);
              }
              goto LABEL_28;
            }
            *(_QWORD *)&v63 = a1;
            if ( v27 || v20 )
            {
              if ( !*(_QWORD *)(v26 + 56) || *(_DWORD *)(v26 + 64) < (unsigned int)v15 || !a3 )
              {
                v46 = 731;
                goto LABEL_117;
              }
              *((_QWORD *)&v63 + 1) = a3;
              *(_QWORD *)&v64 = *(_QWORD *)(v26 + 56);
              *((_QWORD *)&v64 + 1) = *(unsigned int *)(v26 + 68);
              *(_QWORD *)&v65 = *(_QWORD *)(v26 + 72);
              DWORD2(v65) = v27 == 0;
            }
            else
            {
              *((_QWORD *)&v64 + 1) = 0;
              *((_QWORD *)&v63 + 1) = &v68;
              *(_QWORD *)&v64 = &v69;
              *(_QWORD *)&v65 = 0;
              DWORD2(v65) = 1;
            }
            if ( (a11 & 0x20) == 0 )
            {
              v31 = a1;
LABEL_43:
              v33 = ((__int64 (__fastcall *)(_QWORD, __int128 *, _QWORD, _QWORD, _DWORD, unsigned __int64, unsigned int, unsigned __int64, _QWORD, _DWORD, _QWORD, _DWORD, int))rgSymmAlgorithmDefaults[v28 + 13])(
                      0,
                      &v63,
                      (unsigned int)v15,
                      *(_QWORD *)(v26 + 8),
                      *(_DWORD *)(v26 + 16),
                      v16,
                      v23,
                      v19,
                      *(_QWORD *)(v26 + 24),
                      *(_DWORD *)(v26 + 32),
                      *(_QWORD *)(v26 + 40),
                      *(_DWORD *)(v26 + 48),
                      1);
              if ( v33 >= 0 )
              {
                if ( v27 )
                {
                  *(_DWORD *)(v26 + 68) = DWORD2(v64);
                  v50 = v65;
                  *(_DWORD *)(v26 + 80) |= 2u;
                  *(_QWORD *)(v26 + 72) = v50;
                }
                else
                {
                  *(_DWORD *)(v26 + 80) &= ~2u;
                  *(_DWORD *)(v26 + 68) = 0;
                  *(_QWORD *)(v26 + 72) = 0;
                }
LABEL_22:
                if ( (*(_BYTE *)(v31 + 28) & 2) == 0 )
                {
                  if ( !a3 )
                  {
                    if ( !a10 && (!v57 || v27) )
                      goto LABEL_27;
LABEL_25:
                    v32 = v15;
                    if ( (_DWORD)v15 )
                    {
                      do
                      {
                        *(_BYTE *)v24 = 0;
                        v24 = (_DWORD *)((char *)v24 + 1);
                        --v32;
                      }
                      while ( v32 );
                    }
                    goto LABEL_27;
                  }
                  if ( a10 && (!v57 || !v27) )
                    goto LABEL_25;
                  memcpy_0(v24, a3, v15);
                }
LABEL_27:
                v33 = 0;
                goto LABEL_28;
              }
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v41,
                  (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
                  (unsigned int)"Status",
                  v33,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
                  35);
              }
LABEL_28:
              if ( a10 )
              {
LABEL_29:
                v34 = v55;
                goto LABEL_30;
              }
LABEL_56:
              v34 = v55;
              goto LABEL_32;
            }
            if ( (*(_BYTE *)(a1 + 28) & 2) != 0 )
            {
              if ( *(_DWORD *)(v26 + 16) == 12 )
              {
                v53 = *(_QWORD *)(v26 + 8);
                if ( v53 )
                {
                  v31 = a1;
                  if ( v20 )
                  {
                    *(_QWORD *)v53 = *(_QWORD *)v24;
                    *(_DWORD *)(v53 + 8) = v24[2];
                  }
                  else
                  {
                    **(_QWORD **)(v26 + 8) = _InterlockedIncrement64((volatile signed __int64 *)v24);
                    *(_DWORD *)(*(_QWORD *)(v26 + 8) + 8LL) = *(_DWORD *)(a1 + 48);
                  }
                  goto LABEL_43;
                }
              }
              v46 = 767;
            }
            else
            {
              v46 = 759;
            }
          }
          else
          {
            if ( !v27 && !*(_QWORD *)(v26 + 56) )
            {
              v54 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, unsigned __int64, unsigned int, unsigned __int64, _QWORD, _DWORD, _QWORD, _DWORD, int))rgSymmAlgorithmDefaults[v28 + 12])(
                      a1 + HIDWORD(rgSymmAlgorithmDefaults[v28 + 8]),
                      0,
                      (unsigned int)v15,
                      *(_QWORD *)(v26 + 8),
                      *(_DWORD *)(v26 + 16),
                      v16,
                      v23,
                      v19,
                      *(_QWORD *)(v26 + 24),
                      *(_DWORD *)(v26 + 32),
                      *(_QWORD *)(v26 + 40),
                      *(_DWORD *)(v26 + 48),
                      1);
              v33 = v54;
              if ( v54 < 0 )
              {
                v46 = 714;
                v47 = (unsigned int)v54;
                goto LABEL_118;
              }
              goto LABEL_21;
            }
            v46 = 694;
          }
LABEL_117:
          v33 = -1073741811;
          v47 = 3221225485LL;
          goto LABEL_118;
        }
        v33 = -1073741306;
        v51 = 611;
        v52 = 3221225990LL;
      }
      else
      {
        v33 = -1073741811;
        v51 = 599;
        v52 = 3221225485LL;
      }
      DebugTraceError(v52, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c", v51);
      goto LABEL_56;
    }
    v33 = -1073741811;
    v48 = 591;
    v49 = 3221225485LL;
LABEL_93:
    DebugTraceError(v49, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c", v48);
    goto LABEL_29;
  }
  v21 = a6 % (unsigned int)v15;
  v23 = a6 - a6 % (unsigned int)v15;
  v22 = v23 + v15;
  v55 = v23 + v15;
  if ( v23 + (unsigned int)v15 >= v23 )
    goto LABEL_4;
  v34 = -1;
  v33 = -1073741675;
LABEL_30:
  v35 = v67;
  v36 = v15;
  if ( (_DWORD)v15 )
  {
    do
    {
      *v35++ = 0;
      --v36;
    }
    while ( v36 );
  }
LABEL_32:
  *v66 = v34;
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x18000b8b8  mov     [rsp-8+arg_18], rbx
0x18000b8bd  push    rbp
0x18000b8be  push    rsi
0x18000b8bf  push    rdi
0x18000b8c0  push    r12
0x18000b8c2  push    r13
0x18000b8c4  push    r14
0x18000b8c6  push    r15
0x18000b8c8  lea     rbp, [rsp-20h]
0x18000b8cd  sub     rsp, 120h
0x18000b8d4  mov     rax, cs:__security_cookie
0x18000b8db  xor     rax, rsp
0x18000b8de  mov     [rbp+50h+var_38], rax
0x18000b8e2  mov     ebx, [rcx+0Ch]
0x18000b8e5  xorps   xmm0, xmm0
0x18000b8e8  mov     r15d, [rcx+14h]
0x18000b8ec  mov     r14, r8
0x18000b8ef  mov     rax, [rbp+50h+arg_40]
0x18000b8f6  mov     edi, r9d
0x18000b8f9  mov     esi, [rcx+10h]
0x18000b8fc  mov     r11, [rbp+50h+arg_20]
0x18000b903  mov     r12d, [rbp+50h+arg_28]
0x18000b90a  mov     r10d, [rbp+50h+arg_48]
0x18000b911  mov     [rsp+150h+var_D8], rcx
0x18000b916  mov     [rbp+50h+var_70], rax
0x18000b91a  lea     eax, [rbx-4]
0x18000b91d  mov     [rbp+50h+Src], r8
0x18000b921  mov     r8, rcx
0x18000b924  xor     ecx, ecx
0x18000b926  mov     [rbp+50h+var_58], rdx
0x18000b92a  cmp     eax, 1
0x18000b92d  mov     dword ptr [rbp+50h+var_C8], r9d
0x18000b931  mov     r9, [rbp+50h+arg_30]
0x18000b938  mov     eax, r12d
0x18000b93b  setbe   cl
0x18000b93e  mov     [rbp+50h+var_C0], r11
0x18000b942  xor     edx, edx
0x18000b944  mov     [rbp+50h+var_B8], r9
0x18000b948  mov     [rbp+50h+var_A8], r15d
0x18000b94c  mov     [rbp+50h+var_D0], ecx
0x18000b94f  movups  [rbp+50h+var_A0], xmm0
0x18000b953  movups  [rbp+50h+var_90], xmm0
0x18000b957  movups  [rbp+50h+var_80], xmm0
0x18000b95b  test    r10d, r10d
0x18000b95e  jnz     loc_18000BBE7
0x18000b964  div     r15d
0x18000b967  mov     r13d, r12d
0x18000b96a  mov     [rsp+150h+var_E0], r12d
0x18000b96f  test    edx, edx
0x18000b971  jnz     loc_18000BF48
0x18000b977  mov     r15d, r12d
0x18000b97a  test    r9, r9
0x18000b97d  jz      loc_18000BD6A
0x18000b983  cmp     r13d, [rbp+50h+arg_38]
0x18000b98a  ja      loc_18000BF73
0x18000b990  test    r11, r11
0x18000b993  jz      loc_18000BF88
0x18000b999  lea     rax, [r11+r12]
0x18000b99d  cmp     rax, r11
0x18000b9a0  jb      loc_18000BF90
0x18000b9a6  mov     eax, [rbp+50h+arg_38]
0x18000b9ac  add     rax, r9
0x18000b9af  cmp     rax, r9
0x18000b9b2  jb      loc_18000BF90
0x18000b9b8  test    r10d, r10d
0x18000b9bb  jnz     loc_18000BCF0
0x18000b9c1  test    r15d, r15d
0x18000b9c4  jz      loc_18000BC55
0x18000b9ca  lea     r13, [r8+28h]
0x18000b9ce  test    r14, r14
0x18000b9d1  jz      loc_18000BAF4
0x18000b9d7  cmp     edi, esi
0x18000b9d9  jb      loc_18000BFD5
0x18000b9df  cmp     ebx, 2
0x18000b9e2  jz      loc_18000BD80
0x18000b9e8  mov     r8, r14
0x18000b9eb  mov     [rbp+50h+var_C8], r8
0x18000b9ef  test    ecx, ecx
0x18000b9f1  jnz     loc_18000BC0E
0x18000b9f7  xor     edi, edi
0x18000b9f9  xor     r14d, r14d
0x18000b9fc  mov     rdx, [rsp+150h+var_D8]
0x18000ba01  movzx   eax, word ptr [rdx+8]
0x18000ba05  dec     eax
0x18000ba07  imul    r10, rax, 70h ; 'p'
0x18000ba0b  lea     rax, rgSymmAlgorithmDefaults
0x18000ba12  mov     [rbp+50h+var_C0], r10
0x18000ba16  mov     r12d, [r10+rax+44h]
0x18000ba1b  add     r12, rdx
0x18000ba1e  sub     ebx, 1
0x18000ba21  jnz     loc_18000BAFC
0x18000ba27  mov     dword ptr [rsp+150h+var_120], 1
0x18000ba2f  lea     rbx, rgSymmAlgorithmDefaults
0x18000ba36  mov     rax, [r10+rbx+50h]
0x18000ba3b  mov     edx, esi
0x18000ba3d  mov     [rsp+150h+var_128], r9
0x18000ba42  mov     rcx, r12
0x18000ba45  mov     r9, r11
0x18000ba48  mov     dword ptr [rsp+150h+var_130], r15d
0x18000ba4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba52  cmp     [rbp+50h+arg_48], 0
0x18000ba59  jnz     loc_18000BC89
0x18000ba5f  mov     r12, [rsp+150h+var_D8]
0x18000ba64  test    byte ptr [r12+1Ch], 2
0x18000ba6a  jnz     short loc_18000BA9A
0x18000ba6c  mov     rax, [rbp+50h+Src]
0x18000ba70  test    rax, rax
0x18000ba73  jnz     loc_18000BCC1
0x18000ba79  cmp     [rbp+50h+arg_48], eax
0x18000ba7f  jz      loc_18000BC71
0x18000ba85  mov     rax, rsi
0x18000ba88  test    esi, esi
0x18000ba8a  jz      short loc_18000BA9A
0x18000ba8c  mov     byte ptr [r13+0], 0
0x18000ba91  inc     r13
0x18000ba94  sub     rax, 1
0x18000ba98  jnz     short loc_18000BA8C
0x18000ba9a  xor     ebx, ebx
0x18000ba9c  cmp     [rbp+50h+arg_48], 0
0x18000baa3  jz      loc_18000BC68
0x18000baa9  mov     edx, [rsp+150h+var_E0]
0x18000baad  lea     rax, [rbp+50h+var_68]
0x18000bab1  mov     rcx, rsi
0x18000bab4  test    esi, esi
0x18000bab6  jz      short loc_18000BAC4
0x18000bab8  mov     byte ptr [rax], 0
0x18000babb  inc     rax
0x18000babe  sub     rcx, 1
0x18000bac2  jnz     short loc_18000BAB8
0x18000bac4  mov     rax, [rbp+50h+var_70]
0x18000bac8  mov     [rax], edx
0x18000baca  mov     eax, ebx
0x18000bacc  mov     rcx, [rbp+50h+var_38]
0x18000bad0  xor     rcx, rsp; StackCookie
0x18000bad3  call    __security_check_cookie
0x18000bad8  mov     rbx, [rsp+150h+arg_18]
0x18000bae0  add     rsp, 120h
0x18000bae7  pop     r15
0x18000bae9  pop     r14
0x18000baeb  pop     r13
0x18000baed  pop     r12
0x18000baef  pop     rdi
0x18000baf0  pop     rsi
0x18000baf1  pop     rbp
0x18000baf2  retn
0x18000baf4  mov     r8, r13
0x18000baf7  jmp     loc_18000B9EB
0x18000bafc  sub     ebx, 1
0x18000baff  jz      loc_18000BE5A
0x18000bb05  sub     ebx, 1
0x18000bb08  jz      loc_18000BDD7
0x18000bb0e  sub     ebx, 1
0x18000bb11  jz      loc_18007FF53
0x18000bb17  cmp     ebx, 1
0x18000bb1a  jnz     loc_18000BF01
0x18000bb20  xor     r8d, r8d
0x18000bb23  mov     qword ptr [rbp+50h+var_A0], rdx
0x18000bb27  test    r14d, r14d
0x18000bb2a  jnz     loc_18007FE9D
0x18000bb30  test    ecx, ecx
0x18000bb32  jnz     loc_18007FE9D
0x18000bb38  lea     rax, [rbp+50h+var_58]
0x18000bb3c  mov     qword ptr [rbp+50h+var_90+8], r8
0x18000bb40  mov     qword ptr [rbp+50h+var_A0+8], rax
0x18000bb44  lea     rax, [rbp+50h+var_48]
0x18000bb48  mov     qword ptr [rbp+50h+var_90], rax
0x18000bb4c  mov     qword ptr [rbp+50h+var_80], r8
0x18000bb50  mov     dword ptr [rbp+50h+var_80+8], ebx
0x18000bb53  test    [rbp+50h+arg_50], 20h
0x18000bb5a  jnz     loc_18000C007
0x18000bb60  mov     r12, rdx
0x18000bb63  mov     rcx, [rdi+28h]
0x18000bb67  lea     rdx, [rbp+50h+var_A0]
0x18000bb6b  mov     eax, [rdi+30h]
0x18000bb6e  mov     r8d, esi
0x18000bb71  mov     [rsp+150h+var_F0], 1
0x18000bb79  mov     [rsp+150h+var_F8], eax
0x18000bb7d  lea     rax, rgSymmAlgorithmDefaults
0x18000bb84  mov     rax, [r10+rax+68h]
0x18000bb89  mov     [rsp+150h+var_100], rcx
0x18000bb8e  mov     ecx, [rdi+20h]
0x18000bb91  mov     [rsp+150h+var_108], ecx
0x18000bb95  mov     rcx, [rdi+18h]
0x18000bb99  mov     [rsp+150h+var_110], rcx
0x18000bb9e  mov     ecx, [rdi+10h]
0x18000bba1  mov     [rsp+150h+var_118], r9
0x18000bba6  mov     r9, [rdi+8]
0x18000bbaa  mov     dword ptr [rsp+150h+var_120], r15d
0x18000bbaf  mov     [rsp+150h+var_128], r11
0x18000bbb4  mov     dword ptr [rsp+150h+var_130], ecx
0x18000bbb8  xor     ecx, ecx
0x18000bbba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbbf  mov     ebx, eax
0x18000bbc1  test    eax, eax
0x18000bbc3  js      loc_18000BEC3
0x18000bbc9  test    r14d, r14d
0x18000bbcc  jnz     loc_18000C01C
0x18000bbd2  and     dword ptr [rdi+50h], 0FFFFFFFDh
0x18000bbd6  mov     [rdi+44h], r14d
0x18000bbda  mov     qword ptr [rdi+48h], 0
0x18000bbe2  jmp     loc_18000BA64
0x18000bbe7  div     esi
0x18000bbe9  mov     r15d, r12d
0x18000bbec  sub     r15d, edx
0x18000bbef  lea     r13d, [r15+rsi]
0x18000bbf3  mov     [rsp+150h+var_E0], r13d
0x18000bbf8  cmp     r13d, r15d
0x18000bbfb  jnb     loc_18000B97A
0x18000bc01  or      edx, 0FFFFFFFFh
0x18000bc04  mov     ebx, 0C0000095h
0x18000bc09  jmp     loc_18000BAAD
0x18000bc0e  test    r10d, r10d
0x18000bc11  jnz     loc_18000BFAD
0x18000bc17  mov     rcx, [rbp+50h+var_58]
0x18000bc1b  call    validateAuthCipherModeInfo
0x18000bc20  mov     rdi, rax
0x18000bc23  test    rax, rax
0x18000bc26  jz      loc_18000BFF2
0x18000bc2c  mov     ecx, [rax+50h]
0x18000bc2f  mov     r14d, ecx
0x18000bc32  shr     ecx, 1
0x18000bc34  and     ecx, 1
0x18000bc37  and     r14d, 1
0x18000bc3b  jz      loc_18000B9F9
0x18000bc41  xor     edx, edx
0x18000bc43  mov     eax, r12d
0x18000bc46  div     esi
0x18000bc48  test    edx, edx
0x18000bc4a  jz      loc_18000B9FC
0x18000bc50  jmp     loc_18007FE74
0x18000bc55  test    ecx, ecx
0x18000bc57  jnz     loc_18000B9CA
0x18000bc5d  test    r10d, r10d
0x18000bc60  jnz     loc_18000B9CA
0x18000bc66  xor     ebx, ebx
0x18000bc68  mov     edx, [rsp+150h+var_E0]
0x18000bc6c  jmp     loc_18000BAC4
0x18000bc71  cmp     [rbp+50h+var_D0], 0
0x18000bc75  jz      loc_18000BA9A
0x18000bc7b  test    r14d, r14d
0x18000bc7e  jz      loc_18000BA85
0x18000bc84  jmp     loc_18000BA9A
0x18000bc89  mov     rax, [rbp+50h+var_C0]
0x18000bc8d  lea     r9, [rbp+50h+var_68]
0x18000bc91  mov     r8, [rbp+50h+var_C8]
0x18000bc95  mov     edx, esi
0x18000bc97  mov     dword ptr [rsp+150h+var_120], 1
0x18000bc9f  mov     ecx, r15d
0x18000bca2  add     rcx, [rbp+50h+var_B8]
0x18000bca6  mov     rax, [rax+rbx+50h]
0x18000bcab  mov     [rsp+150h+var_128], rcx
0x18000bcb0  mov     rcx, r12
0x18000bcb3  mov     dword ptr [rsp+150h+var_130], esi
0x18000bcb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcbc  jmp     loc_18000BA5F
0x18000bcc1  cmp     [rbp+50h+arg_48], 0
0x18000bcc8  jz      short loc_18000BCDD
0x18000bcca  cmp     [rbp+50h+var_D0], 0
0x18000bcce  jz      loc_18000BA85
0x18000bcd4  test    r14d, r14d
0x18000bcd7  jz      loc_18000BA85
0x18000bcdd  mov     r8, rsi; Size
0x18000bce0  mov     rdx, rax; Src
0x18000bce3  mov     rcx, r13; void *
0x18000bce6  call    memcpy_0
0x18000bceb  jmp     loc_18000BA9A
0x18000bcf0  cmp     esi, 10h
0x18000bcf3  ja      loc_18000BF9B
0x18000bcf9  mov     r14d, r12d
0x18000bcfc  lea     rax, [rsi-1]
0x18000bd00  sub     r14d, r15d
0x18000bd03  mov     rdi, rsi
0x18000bd06  and     rax, r14
0x18000bd09  sub     rdi, rax
0x18000bd0c  lea     rax, [r14+rdi]
0x18000bd10  cmp     rax, 10h
0x18000bd14  ja      short loc_18000BD5E
0x18000bd16  mov     edx, r15d
0x18000bd19  lea     rax, [rbp+50h+var_68]
0x18000bd1d  add     rdx, r11; Src
0x18000bd20  cmp     rax, rdx
0x18000bd23  jz      short loc_18000BD36
0x18000bd25  test    r14, r14
0x18000bd28  jz      short loc_18000BD36
0x18000bd2a  mov     r8d, r14d; Size
0x18000bd2d  lea     rcx, [rbp+50h+var_68]; void *
0x18000bd31  call    memcpy_0
0x18000bd36  lea     rcx, [rbp+50h+var_68]
0x18000bd3a  mov     edx, edi; Val
0x18000bd3c  add     rcx, r14; void *
0x18000bd3f  mov     r8, rdi; Size
0x18000bd42  call    memset_0
0x18000bd47  mov     ecx, [rbp+50h+var_D0]
0x18000bd4a  mov     r11, [rbp+50h+var_C0]
0x18000bd4e  mov     r9, [rbp+50h+var_B8]
0x18000bd52  mov     r10d, [rbp+50h+arg_48]
0x18000bd59  mov     r8, [rsp+150h+var_D8]
0x18000bd5e  mov     r14, [rbp+50h+Src]
0x18000bd62  mov     edi, dword ptr [rbp+50h+var_C8]
0x18000bd65  jmp     loc_18000B9C1
  ... truncated ...
```
