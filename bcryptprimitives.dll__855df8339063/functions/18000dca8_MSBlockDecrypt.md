# MSBlockDecrypt

- ea: `0x18000dca8`
- end: `0x18000e311`
- name: `MSBlockDecrypt`
- size: `1641`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000d630`

## callees

- `0x18000adc0`
- `0x18000dca8`
- `0x18000ecb0`
- `0x18000ee60`
- `0x1800491e0`
- `0x180063170`
- `0x18007f790`
- `0x180083010`

## string_xrefs

- `0x18000e12c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x18000e1d2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x18000e228`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x18000e271`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x1800802e6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x18008035a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`

## pseudocode

```c
__int64 __fastcall MSBlockDecrypt(
        _DWORD *a1,
        __int64 a2,
        void *a3,
        unsigned int a4,
        unsigned __int64 a5,
        unsigned int a6,
        unsigned __int64 a7,
        unsigned int a8,
        unsigned int *a9,
        char a10)
{
  unsigned int v10; // esi
  _DWORD *v14; // r9
  int v15; // r8d
  int v16; // ebx
  unsigned __int64 v17; // rdx
  size_t v18; // rsi
  _BYTE *v19; // r15
  _DWORD *v20; // r11
  __int64 v21; // rax
  unsigned int v22; // r10d
  __int64 v23; // rdi
  int v24; // ecx
  int v25; // r14d
  int v26; // ebx
  __int64 v27; // r10
  __int64 v28; // r13
  int v29; // r8d
  _DWORD *v30; // rdi
  size_t v32; // rax
  __int64 v33; // r9
  __int64 v34; // rcx
  int v35; // r8d
  int v36; // r8d
  int v37; // r8d
  _DWORD *v38; // r12
  _QWORD *v39; // r13
  int v40; // edx
  size_t v41; // rdi
  __int64 v42; // r9
  unsigned __int64 i; // r8
  int v44; // eax
  __int64 v45; // rdx
  __int64 v46; // rcx
  _BYTE *v47; // rax
  __int64 v48; // r9
  __int64 v49; // rax
  __int64 v50; // rcx
  int v51; // eax
  unsigned int v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v54; // [rsp+80h] [rbp-80h]
  unsigned __int64 v55; // [rsp+88h] [rbp-78h]
  unsigned int v56; // [rsp+90h] [rbp-70h]
  _DWORD *v57; // [rsp+98h] [rbp-68h]
  void *Src; // [rsp+A0h] [rbp-60h]
  __int128 v59; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v60; // [rsp+B8h] [rbp-48h]
  __int128 v61; // [rsp+C8h] [rbp-38h]
  __int64 v62; // [rsp+D8h] [rbp-28h]
  _DWORD *v63; // [rsp+E0h] [rbp-20h]
  unsigned int *v64; // [rsp+E8h] [rbp-18h]
  _QWORD v65[2]; // [rsp+F0h] [rbp-10h] BYREF
  char v66; // [rsp+100h] [rbp+0h] BYREF
  char v67; // [rsp+110h] [rbp+10h] BYREF
  int v68; // [rsp+1B8h] [rbp+B8h]

  v10 = a1[5];
  v14 = a1;
  v55 = a7;
  v64 = a9;
  v63 = a1;
  Src = a3;
  v15 = a1[3];
  v65[0] = a5;
  v56 = a6;
  v59 = 0;
  v52 = a6;
  v54 = v10;
  v16 = a10 & 1;
  v68 = v16;
  v60 = 0;
  v61 = 0;
  if ( a6 % v10 )
  {
    v48 = 915;
LABEL_83:
    v26 = -1073741306;
    v50 = 3221225990LL;
LABEL_92:
    DebugTraceError(v50, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c", v48);
    goto LABEL_21;
  }
  v17 = v55;
  if ( !v55 && ((unsigned int)(v15 - 4) > 1 || a5) || !a6 && (unsigned int)(v15 - 4) > 1 )
  {
    v26 = 0;
    goto LABEL_21;
  }
  if ( !v16 && a6 > a8 )
  {
    v26 = -1073741789;
    v33 = 943;
    v34 = 3221225507LL;
LABEL_86:
    DebugTraceError(v34, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c", v33);
    goto LABEL_22;
  }
  v18 = (unsigned int)a1[4];
  if ( !v16 )
  {
LABEL_6:
    if ( !a5 && (unsigned int)(v15 - 4) > 1 || (v62 = a6, a5 + a6 < a5) || v55 + a8 < v55 )
    {
      v48 = 963;
      goto LABEL_91;
    }
    v19 = a1 + 10;
    if ( a3 )
    {
      if ( a4 < (unsigned int)v18 && (unsigned int)(v15 - 4) > 1 )
      {
        v48 = 980;
        goto LABEL_83;
      }
      if ( v15 == 2 )
      {
        v48 = 987;
        goto LABEL_91;
      }
      v20 = a3;
    }
    else
    {
      v20 = a1 + 10;
    }
    v57 = v20;
    if ( (unsigned int)(v15 - 4) > 1 )
    {
      v23 = 0;
      v24 = 0;
    }
    else
    {
      if ( v16 )
      {
        v26 = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v55,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
            232);
        goto LABEL_50;
      }
      v21 = validateAuthCipherModeInfo(a2);
      v23 = v21;
      if ( !v21 )
      {
        v26 = -1073741811;
        v33 = 1008;
        v34 = 3221225485LL;
        goto LABEL_86;
      }
      v24 = (*(_DWORD *)(v21 + 80) >> 1) & 1;
      v25 = *(_DWORD *)(v21 + 80) & 1;
      if ( v25 )
      {
        if ( v22 % (unsigned int)v18 )
        {
          v26 = -1073741306;
          v33 = 1020;
          v34 = 3221225990LL;
          goto LABEL_86;
        }
        v17 = v55;
LABEL_18:
        v26 = 0;
        v27 = 14LL * ((unsigned int)*((unsigned __int16 *)v14 + 4) - 1);
        v53 = v27 * 8;
        v28 = (__int64)v14 + HIDWORD(qword_180084120[v27]);
        v29 = v15 - 1;
        if ( !v29 )
        {
          ((void (__fastcall *)(__int64, _QWORD, _DWORD *, unsigned __int64, unsigned int, unsigned __int64, _DWORD))qword_180084120[v27 + 2])(
            v28,
            (unsigned int)v18,
            v20,
            a5,
            v52,
            v17,
            0);
          if ( !v68 )
            goto LABEL_20;
          (*(void (__fastcall **)(__int64, _QWORD, _DWORD *, unsigned __int64, _DWORD, _QWORD *, _DWORD))((char *)&qword_180084120[2] + v53))(
            v28,
            (unsigned int)v18,
            v57,
            a5 + v52,
            v18,
            v65,
            0);
          goto LABEL_46;
        }
        v35 = v29 - 1;
        if ( !v35 )
        {
          ((void (__fastcall *)(__int64, _QWORD, unsigned __int64, _QWORD, unsigned __int64, _DWORD))qword_180084120[v27 + 1])(
            v28,
            (unsigned int)v18,
            a5,
            v52,
            v17,
            0);
          if ( v68 )
          {
            (*(void (__fastcall **)(__int64, _QWORD, unsigned __int64, _QWORD, _QWORD *, _DWORD))((char *)&qword_180084120[1]
                                                                                                + v53))(
              v28,
              (unsigned int)v18,
              a5 + v52,
              (unsigned int)v18,
              v65,
              0);
            goto LABEL_46;
          }
          goto LABEL_20;
        }
        v36 = v35 - 1;
        if ( !v36 )
        {
          ((void (__fastcall *)(__int64, _QWORD, _QWORD, _DWORD *, unsigned __int64, unsigned int, unsigned __int64, _DWORD))qword_180084120[v27 + 3])(
            v28,
            (unsigned int)v18,
            v54,
            v20,
            a5,
            v52,
            v17,
            0);
          if ( v68 )
          {
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _DWORD *, unsigned __int64, _DWORD, _QWORD *, _DWORD))((char *)&qword_180084120[3] + v53))(
              v28,
              (unsigned int)v18,
              v54,
              v57,
              a5 + v52,
              v18,
              v65,
              0);
            goto LABEL_46;
          }
LABEL_20:
          v30 = v63;
          if ( (v63[7] & 2) == 0 )
          {
            if ( Src && ((unsigned int)(v63[3] - 4) > 1 || v25) )
              memcpy_0(v19, Src, v18);
            if ( (unsigned int)(v30[3] - 4) <= 1 && !v25 )
            {
              v32 = v18;
              if ( (_DWORD)v18 )
              {
                do
                {
                  *v19++ = 0;
                  --v32;
                }
                while ( v32 );
              }
            }
          }
          goto LABEL_21;
        }
        v37 = v36 - 1;
        if ( v37 )
        {
          if ( v37 != 1 )
          {
            v26 = -1073741816;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v17,
                (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
                (unsigned int)"Status",
                8,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
                177);
            goto LABEL_21;
          }
          *(_QWORD *)&v59 = v14;
          if ( !v25 && !v24 )
          {
            *((_QWORD *)&v60 + 1) = 0;
            *((_QWORD *)&v59 + 1) = &v66;
            v38 = (_DWORD *)(v23 + 68);
            *(_QWORD *)&v61 = 0;
            *(_QWORD *)&v60 = &v67;
            v39 = (_QWORD *)(v23 + 72);
            DWORD2(v61) = 1;
LABEL_42:
            v26 = ((__int64 (__fastcall *)(_QWORD, __int128 *, _QWORD, _QWORD, _DWORD, _QWORD, unsigned int, unsigned __int64, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD))qword_180084120[v27 + 5])(
                    0,
                    &v59,
                    (unsigned int)v18,
                    *(_QWORD *)(v23 + 8),
                    *(_DWORD *)(v23 + 16),
                    v65[0],
                    v52,
                    v17,
                    *(_QWORD *)(v23 + 24),
                    *(_DWORD *)(v23 + 32),
                    *(_QWORD *)(v23 + 40),
                    *(_DWORD *)(v23 + 48),
                    0);
            if ( v26 >= 0 )
            {
              if ( v25 )
              {
                *v38 = DWORD2(v60);
                v49 = v61;
                *(_DWORD *)(v23 + 80) |= 2u;
                *v39 = v49;
              }
              else
              {
                *(_DWORD *)(v23 + 80) &= ~2u;
                *v38 = 0;
                *v39 = 0;
              }
              goto LABEL_45;
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v40,
                (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
                (unsigned int)"Status",
                v26,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
                153);
LABEL_21:
            if ( !v68 )
              goto LABEL_22;
            goto LABEL_50;
          }
          if ( *(_QWORD *)(v23 + 56) && *(_DWORD *)(v23 + 64) >= (unsigned int)v18 )
          {
            v38 = (_DWORD *)(v23 + 68);
            *((_QWORD *)&v59 + 1) = Src;
            v39 = (_QWORD *)(v23 + 72);
            *(_QWORD *)&v60 = *(_QWORD *)(v23 + 56);
            *((_QWORD *)&v60 + 1) = *(unsigned int *)(v23 + 68);
            *(_QWORD *)&v61 = *(_QWORD *)(v23 + 72);
            DWORD2(v61) = v25 == 0;
            goto LABEL_42;
          }
          v48 = 1142;
        }
        else
        {
          if ( !v25 && !*(_QWORD *)(v23 + 56) )
          {
            v51 = ((__int64 (__fastcall *)(char *, _QWORD, _QWORD, _QWORD, _DWORD, unsigned __int64, unsigned int, unsigned __int64, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD))qword_180084120[v27 + 4])(
                    (char *)v14 + HIDWORD(qword_180084120[v27]),
                    0,
                    (unsigned int)v18,
                    *(_QWORD *)(v23 + 8),
                    *(_DWORD *)(v23 + 16),
                    a5,
                    v52,
                    v55,
                    *(_QWORD *)(v23 + 24),
                    *(_DWORD *)(v23 + 32),
                    *(_QWORD *)(v23 + 40),
                    *(_DWORD *)(v23 + 48),
                    0);
            v26 = v51;
            if ( v51 < 0 )
            {
              v48 = 1128;
              v50 = (unsigned int)v51;
              goto LABEL_92;
            }
LABEL_45:
            if ( v68 )
            {
LABEL_46:
              v41 = v18;
              v53 = 0;
              v42 = (unsigned int)SymCryptPaddingPkcs7Remove(
                                    v41,
                                    v65,
                                    v41,
                                    v55 + v62 - v41,
                                    a8 + (_DWORD)v18 - v56,
                                    &v53);
              v26 = -1073741823;
              v52 += v53;
              for ( i = 0; i < 3; ++i )
              {
                v44 = dword_18008D884[2 * i] ^ v26;
                v45 = -(v42 ^ (unsigned int)BlockDecryptErrorMap[2 * i]);
                v26 ^= v44 & ~HIDWORD(v45);
              }
              if ( v18 )
              {
                do
                {
                  *v19++ = 0;
                  --v41;
                }
                while ( v41 );
              }
              goto LABEL_50;
            }
            goto LABEL_20;
          }
          v48 = 1108;
        }
LABEL_91:
        v50 = 3221225485LL;
        v26 = -1073741811;
        goto LABEL_92;
      }
    }
    v25 = 0;
    goto LABEL_18;
  }
  if ( a6 - (unsigned int)v18 <= a8 )
  {
    v52 = a6 - v18;
    goto LABEL_6;
  }
  v26 = -1073741789;
  DebugTraceError(3221225507LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c", 949);
LABEL_50:
  v46 = 16;
  v47 = v65;
  do
  {
    *v47++ = 0;
    --v46;
  }
  while ( v46 );
LABEL_22:
  *v64 = v52;
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x18000dca8  mov     [rsp-8+arg_18], rbx
0x18000dcad  push    rbp
0x18000dcae  push    rsi
0x18000dcaf  push    rdi
0x18000dcb0  push    r12
0x18000dcb2  push    r13
0x18000dcb4  push    r14
0x18000dcb6  push    r15
0x18000dcb8  lea     rbp, [rsp-30h]
0x18000dcbd  sub     rsp, 130h
0x18000dcc4  mov     rax, cs:__security_cookie
0x18000dccb  xor     rax, rsp
0x18000dcce  mov     [rbp+60h+var_40], rax
0x18000dcd2  mov     esi, [rcx+14h]
0x18000dcd5  mov     r14, rdx
0x18000dcd8  mov     r10d, [rbp+60h+arg_28]
0x18000dcdf  mov     rdi, r8
0x18000dce2  mov     rax, [rbp+60h+arg_30]
0x18000dce9  mov     r11d, r9d
0x18000dcec  mov     ebx, [rbp+60h+arg_48]
0x18000dcf2  mov     r9, rcx
0x18000dcf5  mov     r12, [rbp+60h+arg_20]
0x18000dcfc  xorps   xmm0, xmm0
0x18000dcff  mov     [rbp+60h+var_D8], rax
0x18000dd03  mov     rax, [rbp+60h+arg_40]
0x18000dd0a  mov     [rbp+60h+var_78], rax
0x18000dd0e  mov     [rbp+60h+var_80], rcx
0x18000dd12  mov     [rbp+60h+Src], r8
0x18000dd16  mov     r8d, [rcx+0Ch]
0x18000dd1a  xor     ecx, ecx
0x18000dd1c  mov     [rbp+60h+var_70], r12
0x18000dd20  mov     [rbp+60h+var_D0], r10d
0x18000dd24  movups  [rbp+60h+var_B8], xmm0
0x18000dd28  lea     eax, [r8-4]
0x18000dd2c  mov     [rsp+160h+var_F0], r10d
0x18000dd31  cmp     eax, 1
0x18000dd34  mov     [rbp+60h+var_E0], esi
0x18000dd37  mov     eax, r10d
0x18000dd3a  setbe   cl
0x18000dd3d  and     ebx, 1
0x18000dd40  xor     edx, edx
0x18000dd42  mov     [rbp+60h+arg_48], ebx
0x18000dd48  div     esi
0x18000dd4a  movups  [rbp+60h+var_A8], xmm0
0x18000dd4e  movups  [rbp+60h+var_98], xmm0
0x18000dd52  test    edx, edx
0x18000dd54  jnz     loc_18000E23D
0x18000dd5a  mov     rdx, [rbp+60h+var_D8]
0x18000dd5e  test    rdx, rdx
0x18000dd61  jz      loc_18000E248
0x18000dd67  test    r10d, r10d
0x18000dd6a  jz      loc_18000E25E
0x18000dd70  mov     r15d, [rbp+60h+arg_38]
0x18000dd77  test    ebx, ebx
0x18000dd79  jz      loc_18000DF38
0x18000dd7f  mov     esi, [r9+10h]
0x18000dd83  test    ebx, ebx
0x18000dd85  jnz     loc_18000E155
0x18000dd8b  test    r12, r12
0x18000dd8e  jz      loc_18000E293
0x18000dd94  mov     rax, r10
0x18000dd97  mov     [rbp+60h+var_88], rax
0x18000dd9b  add     rax, r12
0x18000dd9e  cmp     rax, r12
0x18000dda1  jb      loc_18000E29B
0x18000dda7  lea     rax, [rdx+r15]
0x18000ddab  cmp     rax, rdx
0x18000ddae  jb      loc_18000E29B
0x18000ddb4  lea     r15, [r9+28h]
0x18000ddb8  test    rdi, rdi
0x18000ddbb  jz      loc_18000DED5
0x18000ddc1  cmp     r11d, esi
0x18000ddc4  jb      loc_18000E2A6
0x18000ddca  cmp     r8d, 2
0x18000ddce  jz      loc_18000E2B3
0x18000ddd4  mov     r11, rdi
0x18000ddd7  mov     [rbp+60h+var_C8], r11
0x18000dddb  test    ecx, ecx
0x18000dddd  jz      loc_18000DECC
0x18000dde3  test    ebx, ebx
0x18000dde5  jnz     loc_18000E1A8
0x18000ddeb  mov     rcx, r14
0x18000ddee  call    validateAuthCipherModeInfo
0x18000ddf3  mov     rdi, rax
0x18000ddf6  test    rax, rax
0x18000ddf9  jz      loc_18000E2BE
0x18000ddff  mov     ecx, [rax+50h]
0x18000de02  mov     r14d, ecx
0x18000de05  shr     ecx, 1
0x18000de07  and     ecx, 1
0x18000de0a  and     r14d, 1
0x18000de0e  jnz     loc_18000E2D3
0x18000de14  xor     r14d, r14d
0x18000de17  movzx   eax, word ptr [r9+8]
0x18000de1c  xor     ebx, ebx
0x18000de1e  dec     eax
0x18000de20  imul    r10, rax, 70h ; 'p'
0x18000de24  lea     rax, cs:180000000h
0x18000de2b  mov     [rsp+160h+var_E8], r10
0x18000de30  mov     r13d, [r10+rax+84124h]
0x18000de38  add     r13, r9
0x18000de3b  sub     r8d, 1
0x18000de3f  jnz     loc_18000DF56
0x18000de45  mov     edi, [rsp+160h+var_F0]
0x18000de49  lea     rax, cs:180000000h
0x18000de50  mov     rax, [r10+rax+84130h]
0x18000de58  mov     r9, r12
0x18000de5b  mov     dword ptr [rsp+160h+var_130], ebx
0x18000de5f  mov     r8, r11
0x18000de62  mov     [rsp+160h+var_138], rdx
0x18000de67  mov     rcx, r13
0x18000de6a  mov     edx, esi
0x18000de6c  mov     dword ptr [rsp+160h+var_140], edi
0x18000de70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de75  cmp     [rbp+60h+arg_48], ebx
0x18000de7b  jnz     loc_18000E16C
0x18000de81  mov     rdi, [rbp+60h+var_80]
0x18000de85  test    byte ptr [rdi+1Ch], 2
0x18000de89  jz      short loc_18000DEDD
0x18000de8b  cmp     [rbp+60h+arg_48], 0
0x18000de92  jnz     loc_18000E0E4
0x18000de98  mov     eax, [rsp+160h+var_F0]
0x18000de9c  mov     rcx, [rbp+60h+var_78]
0x18000dea0  mov     [rcx], eax
0x18000dea2  mov     eax, ebx
0x18000dea4  mov     rcx, [rbp+60h+var_40]
0x18000dea8  xor     rcx, rsp; StackCookie
0x18000deab  call    __security_check_cookie
0x18000deb0  mov     rbx, [rsp+160h+arg_18]
0x18000deb8  add     rsp, 130h
0x18000debf  pop     r15
0x18000dec1  pop     r14
0x18000dec3  pop     r13
0x18000dec5  pop     r12
0x18000dec7  pop     rdi
0x18000dec8  pop     rsi
0x18000dec9  pop     rbp
0x18000deca  retn
0x18000decc  xor     edi, edi
0x18000dece  xor     ecx, ecx
0x18000ded0  jmp     loc_18000DE14
0x18000ded5  mov     r11, r15
0x18000ded8  jmp     loc_18000DDD7
0x18000dedd  mov     rcx, [rbp+60h+Src]
0x18000dee1  test    rcx, rcx
0x18000dee4  jz      short loc_18000DF03
0x18000dee6  mov     eax, [rdi+0Ch]
0x18000dee9  sub     eax, 4
0x18000deec  cmp     eax, 1
0x18000deef  jbe     loc_18000E303
0x18000def5  mov     rdx, rcx; Src
0x18000def8  mov     r8, rsi; Size
0x18000defb  mov     rcx, r15; void *
0x18000defe  call    memcpy_0
0x18000df03  mov     eax, [rdi+0Ch]
0x18000df06  sub     eax, 4
0x18000df09  cmp     eax, 1
0x18000df0c  ja      loc_18000DE8B
0x18000df12  test    r14d, r14d
0x18000df15  jnz     loc_18000DE8B
0x18000df1b  mov     rax, rsi
0x18000df1e  test    esi, esi
0x18000df20  jz      loc_18000DE8B
0x18000df26  mov     byte ptr [r15], 0
0x18000df2a  inc     r15
0x18000df2d  sub     rax, 1
0x18000df31  jnz     short loc_18000DF26
0x18000df33  jmp     loc_18000DE8B
0x18000df38  cmp     r10d, r15d
0x18000df3b  jbe     loc_18000DD7F
0x18000df41  mov     ebx, 0C0000023h
0x18000df46  mov     r9d, 3AFh
0x18000df4c  mov     ecx, 0C0000023h
0x18000df51  jmp     loc_1800802E6
0x18000df56  sub     r8d, 1
0x18000df5a  jz      loc_180080489
0x18000df60  sub     r8d, 1
0x18000df64  jz      loc_180080401
0x18000df6a  sub     r8d, 1
0x18000df6e  jz      loc_180080373
0x18000df74  cmp     r8d, 1
0x18000df78  jnz     loc_18000E0FE
0x18000df7e  mov     qword ptr [rbp+60h+var_B8], r9
0x18000df82  test    r14d, r14d
0x18000df85  jnz     loc_1800802FF
0x18000df8b  test    ecx, ecx
0x18000df8d  jnz     loc_1800802FF
0x18000df93  lea     rax, [rbp+60h+var_60]
0x18000df97  mov     qword ptr [rbp+60h+var_A8+8], rbx
0x18000df9b  mov     qword ptr [rbp+60h+var_B8+8], rax
0x18000df9f  lea     r12, [rdi+44h]
0x18000dfa3  lea     rax, [rbp+60h+var_50]
0x18000dfa7  mov     qword ptr [rbp+60h+var_98], rbx
0x18000dfab  mov     qword ptr [rbp+60h+var_A8], rax
0x18000dfaf  lea     r13, [rdi+48h]
0x18000dfb3  mov     dword ptr [rbp+60h+var_98+8], r8d
0x18000dfb7  mov     eax, [rdi+30h]
0x18000dfba  mov     r8d, esi
0x18000dfbd  mov     r9, [rdi+8]
0x18000dfc1  xor     ecx, ecx
0x18000dfc3  mov     [rsp+160h+var_100], ebx
0x18000dfc7  mov     [rsp+160h+var_108], eax
0x18000dfcb  mov     rax, [rdi+28h]
0x18000dfcf  mov     [rsp+160h+var_110], rax
0x18000dfd4  mov     eax, [rdi+20h]
0x18000dfd7  mov     [rsp+160h+var_118], eax
0x18000dfdb  mov     rax, [rdi+18h]
0x18000dfdf  mov     [rsp+160h+var_120], rax
0x18000dfe4  mov     eax, [rsp+160h+var_F0]
0x18000dfe8  mov     [rsp+160h+var_128], rdx
0x18000dfed  lea     rdx, [rbp+60h+var_B8]
0x18000dff1  mov     dword ptr [rsp+160h+var_130], eax
0x18000dff5  mov     rax, [rbp+60h+var_70]
0x18000dff9  mov     [rsp+160h+var_138], rax
0x18000dffe  mov     eax, [rdi+10h]
0x18000e001  mov     dword ptr [rsp+160h+var_140], eax
0x18000e005  lea     rax, cs:180000000h
0x18000e00c  mov     rax, [r10+rax+84148h]
0x18000e014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e019  mov     ebx, eax
0x18000e01b  test    eax, eax
0x18000e01d  js      loc_18000E1FF
0x18000e023  test    r14d, r14d
0x18000e026  jnz     loc_18000E2EB
0x18000e02c  and     dword ptr [rdi+50h], 0FFFFFFFDh
0x18000e030  mov     [r12], r14d
0x18000e034  mov     qword ptr [r13+0], 0
0x18000e03c  cmp     [rbp+60h+arg_48], 0
0x18000e043  jz      loc_18000DE81
0x18000e049  lea     r14, cs:180000000h
0x18000e050  mov     r9, [rbp+60h+var_88]
0x18000e054  lea     rdx, [rsp+160h+var_E8]
0x18000e059  mov     rdi, rsi
0x18000e05c  mov     [rsp+160h+var_138], rdx
0x18000e061  sub     esi, [rbp+60h+var_D0]
0x18000e064  lea     rdx, [rbp+60h+var_70]
0x18000e068  add     esi, [rbp+60h+arg_38]
0x18000e06e  sub     r9, rdi
0x18000e071  add     r9, [rbp+60h+var_D8]
0x18000e075  mov     r8, rdi
0x18000e078  mov     eax, esi
0x18000e07a  mov     rcx, rdi
0x18000e07d  mov     [rsp+160h+var_140], rax
0x18000e082  mov     [rsp+160h+var_E8], 0
0x18000e08b  call    SymCryptPaddingPkcs7Remove
0x18000e090  mov     r9d, eax
0x18000e093  mov     ebx, 0C0000001h
0x18000e098  mov     eax, [rsp+160h+var_F0]
0x18000e09c  add     eax, dword ptr [rsp+160h+var_E8]
0x18000e0a0  mov     [rsp+160h+var_F0], eax
0x18000e0a4  xor     r8d, r8d
0x18000e0a7  mov     edx, ds:rva BlockDecryptErrorMap[r14+r8*8]
0x18000e0af  mov     eax, ebx
0x18000e0b1  xor     eax, ds:rva dword_18008D884[r14+r8*8]
0x18000e0b9  xor     rdx, r9
0x18000e0bc  neg     rdx
0x18000e0bf  inc     r8
0x18000e0c2  sar     rdx, 20h
0x18000e0c6  not     edx
0x18000e0c8  and     edx, eax
0x18000e0ca  xor     ebx, edx
0x18000e0cc  cmp     r8, 3
0x18000e0d0  jb      short loc_18000E0A7
0x18000e0d2  test    rdi, rdi
0x18000e0d5  jz      short loc_18000E0E4
0x18000e0d7  mov     byte ptr [r15], 0
0x18000e0db  inc     r15
0x18000e0de  sub     rdi, 1
0x18000e0e2  jnz     short loc_18000E0D7
0x18000e0e4  mov     ecx, 10h
0x18000e0e9  lea     rax, [rbp+60h+var_70]
0x18000e0ed  mov     byte ptr [rax], 0
0x18000e0f0  inc     rax
0x18000e0f3  sub     rcx, 1
0x18000e0f7  jnz     short loc_18000E0ED
0x18000e0f9  jmp     loc_18000DE98
0x18000e0fe  mov     ebx, 0C0000008h
0x18000e103  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e10a  lea     rax, WPP_GLOBAL_Control
0x18000e111  cmp     rcx, rax
0x18000e114  jz      loc_18000DE8B
0x18000e11a  test    byte ptr [rcx+1Ch], 1
0x18000e11e  jz      loc_18000DE8B
0x18000e124  mov     dword ptr [rsp+160h+var_130], 4B1h
0x18000e12c  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e133  mov     [rsp+160h+var_138], r8
0x18000e138  mov     dword ptr [rsp+160h+var_140], 0C0000008h
0x18000e140  mov     rcx, [rcx+10h]
0x18000e144  lea     r9, aStatus; "Status"
0x18000e14b  call    WPP_SF_sDsd
0x18000e150  jmp     loc_18000DE8B
0x18000e155  mov     eax, r10d
0x18000e158  sub     eax, esi
0x18000e15a  cmp     eax, r15d
0x18000e15d  ja      loc_18000E26B
0x18000e163  mov     [rsp+160h+var_F0], eax
0x18000e167  jmp     loc_18000DD8B
0x18000e16c  mov     r8, [rbp+60h+var_C8]
0x18000e170  lea     rax, [rbp+60h+var_70]
0x18000e174  mov     dword ptr [rsp+160h+var_130], ebx
  ... truncated ...
```
