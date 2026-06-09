# I_BigEndianBytesToDecString

- ea: `0x180011eec`
- end: `0x1800122d6`
- name: `I_BigEndianBytesToDecString`
- size: `1002`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011a40`

## callees

- `0x1800070d0`
- `0x180011eec`
- `0x180014ce0`
- `0x180014df8`
- `0x180015b40`
- `0x180015cf4`
- `0x180017c58`
- `0x180017d58`
- `0x180017e74`
- `0x180017ea8`
- `0x180017f34`
- `0x180017fec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011f46`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011f46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800121d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012264`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800122af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800121d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012264`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800122af`

## string_xrefs

- `0x180011f6a`: `onecore\ds\security\cryptoapi\xml\lib\bignum.cpp`
- `0x180012036`: `onecore\ds\security\cryptoapi\xml\lib\bignum.cpp`
- `0x18001207a`: `onecore\ds\security\cryptoapi\xml\lib\bignum.cpp`
- `0x1800121ef`: `onecore\ds\security\cryptoapi\xml\lib\bignum.cpp`
- `0x180012226`: `onecore\ds\security\cryptoapi\xml\lib\bignum.cpp`
- `0x180012285`: `onecore\ds\security\cryptoapi\xml\lib\bignum.cpp`

## pseudocode

```c
__int64 __fastcall I_BigEndianBytesToDecString(_BYTE *a1, unsigned int a2, __int16 **a3, _DWORD *a4)
{
  unsigned int v4; // ebp
  unsigned int i; // edi
  __int16 *v7; // rax
  __int16 *v8; // r14
  const char *v9; // r8
  const char *v10; // rax
  bool v11; // zf
  unsigned int v12; // eax
  unsigned int v13; // esi
  unsigned int v14; // eax
  unsigned int v15; // r12d
  _DWORD *v16; // rax
  int v17; // r8d
  _DWORD *v18; // rbx
  _DWORD *v19; // r13
  const char *v20; // rax
  int v21; // edx
  int v22; // r9d
  char *v23; // r15
  int v24; // r10d
  unsigned int v25; // eax
  unsigned int v26; // ebp
  _DWORD *v27; // rax
  _DWORD *v28; // rsi
  unsigned int v29; // ebp
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rbp
  __int64 v33; // r12
  int IsEqualUint32; // eax
  __int16 v35; // r11
  unsigned int j; // r9d
  __int64 v37; // r8
  int v38; // eax
  __int64 v39; // rax
  __int16 v40; // dx
  const char *v41; // rax
  int v42; // r10d
  const char *v43; // rax
  int v44; // r10d
  const char *v45; // rax
  int v46; // r10d
  _DWORD *v48; // [rsp+30h] [rbp-48h]

  v4 = a2;
  *a3 = 0;
  *a4 = 0;
  for ( i = 1; v4; --v4 )
  {
    if ( *a1 )
      break;
    ++a1;
  }
  v7 = (__int16 *)LocalAlloc(0x40u, 20 * (v4 >> 2) + 22);
  v8 = v7;
  if ( v7 )
  {
    SymCryptWipeAsm(v7, 20 * (v4 >> 2) + 22);
    v12 = 8 * v4;
    if ( 8 * v4 )
    {
      if ( v12 <= 0x100000 )
        v13 = (v12 >> 9) + (((v12 & 0x1FF) + 511) >> 9);
      else
        v13 = 0;
    }
    else
    {
      v13 = 1;
    }
    v14 = SymCryptFdefSizeofIntFromDigits(v13);
    v15 = v14;
    if ( !v14 || (v16 = (_DWORD *)SymCryptCallbackAlloc(v14), (v18 = v16) == 0) )
    {
      i = -2147024888;
      v45 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\bignum.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v46, v45, 213);
LABEL_44:
      LocalFree(v8);
      return i;
    }
    *v16 = 1732837376;
    v16[1] = v13;
    v16[2] = v15;
    v19 = v16 + 1;
    v48 = v16 + 8;
    if ( (unsigned int)SymCryptFdefRawSetValue((_DWORD)a1, v4, v17, (int)v16 + 32, v16[1]) )
    {
      v20 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\bignum.cpp");
      v21 = 1;
      v22 = 221;
    }
    else
    {
      v23 = (char *)SymCryptCallbackAlloc((unsigned int)((*v19 + 1) << 6));
      if ( v23 )
      {
        v25 = SymCryptFdefSizeofIntFromDigits(1);
        v26 = v25;
        if ( v25 && (v27 = (_DWORD *)SymCryptCallbackAlloc(v25), (v28 = v27) != 0) )
        {
          *v27 = 1732837376;
          v27[1] = 1;
          v27[2] = v26;
          SymCryptWipeAsm(v27 + 8, 64);
          v28[8] = 10;
          v29 = v26 + 32;
          if ( v29
            && (v30 = SymCryptCallbackAlloc(v29)) != 0
            && (v31 = SymCryptFdefDivisorCreate(v30, v29), (v32 = v31) != 0) )
          {
            v33 = 0;
            SymCryptFdefIntToDivisor(v28, v31);
            IsEqualUint32 = SymCryptFdefRawIsEqualUint32(v48, (unsigned int)*v19);
            v35 = 48;
            while ( !IsEqualUint32 )
            {
              SymCryptFdefIntDivMod((int)v18, v32, (int)v18, (int)v28, v23);
              v8[v33] = *((_WORD *)v28 + 16) + 48;
              v33 = (unsigned int)(v33 + 1);
              IsEqualUint32 = SymCryptFdefRawIsEqualUint32(v48, (unsigned int)*v19);
            }
            for ( j = 0; j < (unsigned int)v33 >> 1; v8[(unsigned int)v39] = v40 )
            {
              v37 = j;
              v38 = v33 - j++;
              v39 = (unsigned int)(v38 - 1);
              v40 = v8[v37];
              v8[v37] = v8[v39];
            }
            if ( !(_DWORD)v33 )
            {
              *v8 = v35;
              LODWORD(v33) = 1;
            }
            *a3 = v8;
            *a4 = v33;
            SymCryptWipeAsm(v32, *(unsigned int *)(v32 + 8));
            LocalFree((HLOCAL)(v32 - *(unsigned int *)(v32 - 4)));
            i = 0;
            v8 = 0;
          }
          else
          {
            i = -2147024888;
            v41 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\bignum.cpp");
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v42, v41, 253);
          }
          SymCryptIntFree(v28);
        }
        else
        {
          i = -2147024888;
          v43 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\bignum.cpp");
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v44, v43, 242);
        }
        SymCryptWipeAsm(v23, 8);
        LocalFree(&v23[-*((unsigned int *)v23 - 1)]);
LABEL_41:
        SymCryptIntFree(v18);
        if ( !v8 )
          return i;
        goto LABEL_44;
      }
      i = -2147024888;
      v20 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\bignum.cpp");
      v21 = v24;
      v22 = 232;
    }
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v21, v20, v22);
    goto LABEL_41;
  }
  v9 = "";
  i = -2147024888;
  while ( 1 )
  {
    v10 = v9--;
    v11 = *v9 == 92;
    if ( *v9 == 92 )
      break;
    if ( v9 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\bignum.cpp" )
    {
      v11 = *v9 == 92;
      break;
    }
  }
  if ( v11 )
    v9 = v10;
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024888, v9, 202);
  return i;
}

```

## disassembly

```asm
0x180011eec  mov     [rsp+arg_0], rbx
0x180011ef1  mov     [rsp+arg_18], r9
0x180011ef6  mov     [rsp+arg_10], r8
0x180011efb  push    rbp
0x180011efc  push    rsi
0x180011efd  push    rdi
0x180011efe  push    r12
0x180011f00  push    r13
0x180011f02  push    r14
0x180011f04  push    r15
0x180011f06  sub     rsp, 40h
0x180011f0a  xor     r13d, r13d
0x180011f0d  mov     ebp, edx
0x180011f0f  mov     r15, rcx
0x180011f12  mov     [r8], r13
0x180011f15  mov     [r9], r13d
0x180011f18  lea     edi, [r13+1]
0x180011f1c  cmp     edx, edi
0x180011f1e  jb      short loc_180011F2E
0x180011f20  cmp     [r15], r13b
0x180011f23  jnz     short loc_180011F2E
0x180011f25  add     r15, rdi
0x180011f28  dec     ebp
0x180011f2a  cmp     ebp, edi
0x180011f2c  jnb     short loc_180011F20
0x180011f2e  mov     eax, ebp
0x180011f30  mov     ecx, 40h ; '@'; uFlags
0x180011f35  shr     eax, 2
0x180011f38  lea     eax, [rax+rax*4]
0x180011f3b  lea     eax, ds:16h[rax*4]
0x180011f42  mov     edx, eax; uBytes
0x180011f44  mov     ebx, eax
0x180011f46  call    cs:__imp_LocalAlloc
0x180011f4d  nop     dword ptr [rax+rax+00h]
0x180011f52  mov     r14, rax
0x180011f55  test    rax, rax
0x180011f58  jnz     short loc_180011FA4
0x180011f5a  mov     r10d, 80070008h
0x180011f60  lea     r8, aOnecoreDsSecur_4+30h; ""
0x180011f67  mov     edi, r10d
0x180011f6a  lea     rcx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180011f71  mov     rax, r8
0x180011f74  dec     r8
0x180011f77  cmp     byte ptr [r8], 5Ch ; '\'
0x180011f7b  jz      short loc_180011F86
0x180011f7d  cmp     r8, rcx
0x180011f80  ja      short loc_180011F71
0x180011f82  cmp     byte ptr [r8], 5Ch ; '\'
0x180011f86  cmovz   r8, rax
0x180011f8a  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180011f91  mov     r9d, 0CAh
0x180011f97  mov     edx, r10d
0x180011f9a  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180011f9f  jmp     loc_1800122BB
0x180011fa4  mov     rdx, rbx
0x180011fa7  mov     rcx, r14
0x180011faa  call    SymCryptWipeAsm
0x180011faf  lea     eax, ds:0[rbp*8]
0x180011fb6  test    eax, eax
0x180011fb8  jnz     short loc_180011FBE
0x180011fba  mov     esi, edi
0x180011fbc  jmp     short loc_180011FDD
0x180011fbe  cmp     eax, 100000h
0x180011fc3  jbe     short loc_180011FCA
0x180011fc5  mov     esi, r13d
0x180011fc8  jmp     short loc_180011FDD
0x180011fca  mov     esi, eax
0x180011fcc  mov     ecx, 1FFh
0x180011fd1  and     esi, ecx
0x180011fd3  shr     eax, 9
0x180011fd6  add     esi, ecx
0x180011fd8  shr     esi, 9
0x180011fdb  add     esi, eax
0x180011fdd  mov     ecx, esi
0x180011fdf  call    SymCryptFdefSizeofIntFromDigits
0x180011fe4  mov     r12d, eax
0x180011fe7  test    eax, eax
0x180011fe9  jz      loc_18001227F
0x180011fef  mov     ecx, r12d
0x180011ff2  call    SymCryptCallbackAlloc
0x180011ff7  mov     rbx, rax
0x180011ffa  test    rax, rax
0x180011ffd  jz      loc_18001227F
0x180012003  mov     dword ptr [rax], 67490000h
0x180012009  mov     [rax+4], esi
0x18001200c  mov     [rax+8], r12d
0x180012010  lea     rcx, [rax+20h]
0x180012014  mov     edx, ebp
0x180012016  lea     r13, [rax+4]
0x18001201a  mov     [rsp+78h+var_48], rcx
0x18001201f  mov     eax, [r13+0]
0x180012023  mov     r9, rcx
0x180012026  mov     rcx, r15
0x180012029  mov     dword ptr [rsp+78h+var_58], eax
0x18001202d  call    SymCryptFdefRawSetValue
0x180012032  test    eax, eax
0x180012034  jz      short loc_18001205E
0x180012036  lea     rcx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001203d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180012042  mov     edx, edi
0x180012044  mov     r9d, 0DDh
0x18001204a  mov     r8, rax
0x18001204d  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180012054  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180012059  jmp     loc_180012270
0x18001205e  mov     ecx, [r13+0]
0x180012062  add     ecx, edi
0x180012064  shl     ecx, 6
0x180012067  call    SymCryptCallbackAlloc
0x18001206c  mov     r15, rax
0x18001206f  test    rax, rax
0x180012072  jnz     short loc_180012094
0x180012074  mov     r10d, 80070008h
0x18001207a  lea     rcx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180012081  mov     edi, r10d
0x180012084  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180012089  mov     edx, r10d
0x18001208c  mov     r9d, 0E8h
0x180012092  jmp     short loc_18001204A
0x180012094  mov     ecx, edi
0x180012096  call    SymCryptFdefSizeofIntFromDigits
0x18001209b  mov     ebp, eax
0x18001209d  test    eax, eax
0x18001209f  jz      loc_180012220
0x1800120a5  mov     ecx, ebp
0x1800120a7  call    SymCryptCallbackAlloc
0x1800120ac  mov     rsi, rax
0x1800120af  test    rax, rax
0x1800120b2  jz      loc_180012220
0x1800120b8  mov     dword ptr [rax], 67490000h
0x1800120be  mov     [rax+4], edi
0x1800120c1  mov     [rax+8], ebp
0x1800120c4  mov     edx, edi
0x1800120c6  lea     rcx, [rax+20h]
0x1800120ca  shl     edx, 6
0x1800120cd  call    SymCryptWipeAsm
0x1800120d2  mov     dword ptr [rsi+20h], 0Ah
0x1800120d9  add     ebp, 20h ; ' '
0x1800120dc  jz      loc_1800121E9
0x1800120e2  mov     ecx, ebp
0x1800120e4  call    SymCryptCallbackAlloc
0x1800120e9  test    rax, rax
0x1800120ec  jz      loc_1800121E9
0x1800120f2  mov     edx, ebp
0x1800120f4  mov     rcx, rax
0x1800120f7  call    SymCryptFdefDivisorCreate
0x1800120fc  mov     rbp, rax
0x1800120ff  test    rax, rax
0x180012102  jz      loc_1800121E9
0x180012108  mov     rdx, rax
0x18001210b  mov     rcx, rsi
0x18001210e  xor     r12d, r12d
0x180012111  call    SymCryptFdefIntToDivisor
0x180012116  mov     edx, [r13+0]
0x18001211a  mov     rcx, [rsp+78h+var_48]
0x18001211f  call    SymCryptFdefRawIsEqualUint32
0x180012124  lea     r11d, [r12+30h]
0x180012129  jmp     short loc_180012165
0x18001212b  mov     r9, rsi; int
0x18001212e  mov     [rsp+78h+var_58], r15; void *
0x180012133  mov     r8, rbx; int
0x180012136  mov     rdx, rbp; int
0x180012139  mov     rcx, rbx; int
0x18001213c  call    SymCryptFdefIntDivMod
0x180012141  movzx   ecx, word ptr [rsi+20h]
0x180012145  mov     r11d, 30h ; '0'
0x18001214b  add     cx, r11w
0x18001214f  mov     [r14+r12*2], cx
0x180012154  add     r12d, edi
0x180012157  mov     edx, [r13+0]
0x18001215b  mov     rcx, [rsp+78h+var_48]
0x180012160  call    SymCryptFdefRawIsEqualUint32
0x180012165  test    eax, eax
0x180012167  jz      short loc_18001212B
0x180012169  mov     r10d, r12d
0x18001216c  mov     r9d, 0
0x180012172  shr     r10d, 1
0x180012175  jz      short loc_1800121A0
0x180012177  mov     r8d, r9d
0x18001217a  mov     eax, r12d
0x18001217d  sub     eax, r9d
0x180012180  add     r9d, edi
0x180012183  sub     eax, edi
0x180012185  mov     ecx, eax
0x180012187  movzx   edx, word ptr [r14+r8*2]
0x18001218c  movzx   eax, word ptr [r14+rax*2]
0x180012191  mov     [r14+r8*2], ax
0x180012196  mov     [r14+rcx*2], dx
0x18001219b  cmp     r9d, r10d
0x18001219e  jb      short loc_180012177
0x1800121a0  test    r12d, r12d
0x1800121a3  jnz     short loc_1800121AC
0x1800121a5  mov     [r14], r11w
0x1800121a9  mov     r12d, edi
0x1800121ac  mov     rax, [rsp+78h+arg_10]
0x1800121b4  mov     rcx, rbp
0x1800121b7  mov     [rax], r14
0x1800121ba  mov     rax, [rsp+78h+arg_18]
0x1800121c2  mov     [rax], r12d
0x1800121c5  mov     edx, [rbp+8]
0x1800121c8  call    SymCryptWipeAsm
0x1800121cd  mov     eax, [rbp-4]
0x1800121d0  sub     rbp, rax
0x1800121d3  mov     rcx, rbp; hMem
0x1800121d6  call    cs:__imp_LocalFree
0x1800121dd  nop     dword ptr [rax+rax+00h]
0x1800121e2  xor     edi, edi
0x1800121e4  xor     r14d, r14d
0x1800121e7  jmp     short loc_180012216
0x1800121e9  mov     r10d, 80070008h
0x1800121ef  lea     rcx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800121f6  mov     edi, r10d
0x1800121f9  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800121fe  mov     r8, rax
0x180012201  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180012208  mov     edx, r10d
0x18001220b  mov     r9d, 0FDh
0x180012211  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180012216  mov     rcx, rsi
0x180012219  call    SymCryptIntFree
0x18001221e  jmp     short loc_18001224D
0x180012220  mov     r10d, 80070008h
0x180012226  lea     rcx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001222d  mov     edi, r10d
0x180012230  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180012235  mov     r8, rax
0x180012238  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18001223f  mov     edx, r10d
0x180012242  mov     r9d, 0F2h
0x180012248  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18001224d  mov     edx, 8
0x180012252  mov     rcx, r15
0x180012255  call    SymCryptWipeAsm
0x18001225a  mov     eax, [r15-4]
0x18001225e  sub     r15, rax
0x180012261  mov     rcx, r15; hMem
0x180012264  call    cs:__imp_LocalFree
0x18001226b  nop     dword ptr [rax+rax+00h]
0x180012270  mov     rcx, rbx
0x180012273  call    SymCryptIntFree
0x180012278  test    r14, r14
0x18001227b  jnz     short loc_1800122AC
0x18001227d  jmp     short loc_1800122BB
0x18001227f  mov     r10d, 80070008h
0x180012285  lea     rcx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001228c  mov     edi, r10d
0x18001228f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180012294  mov     r8, rax
0x180012297  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18001229e  mov     edx, r10d
0x1800122a1  mov     r9d, 0D5h
0x1800122a7  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800122ac  mov     rcx, r14; hMem
0x1800122af  call    cs:__imp_LocalFree
0x1800122b6  nop     dword ptr [rax+rax+00h]
0x1800122bb  mov     rbx, [rsp+78h+arg_0]
0x1800122c3  mov     eax, edi
0x1800122c5  add     rsp, 40h
0x1800122c9  pop     r15
0x1800122cb  pop     r14
0x1800122cd  pop     r13
0x1800122cf  pop     r12
0x1800122d1  pop     rdi
0x1800122d2  pop     rsi
0x1800122d3  pop     rbp
0x1800122d4  retn
```
