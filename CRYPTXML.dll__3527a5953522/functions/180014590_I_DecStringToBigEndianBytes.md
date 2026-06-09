# I_DecStringToBigEndianBytes

- ea: `0x180014590`
- end: `0x18001484d`
- name: `I_DecStringToBigEndianBytes`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012d90`

## callees

- `0x1800070d0`
- `0x180014590`
- `0x180014ce0`
- `0x180014df8`
- `0x180015b40`
- `0x180015cf4`
- `0x180017c58`
- `0x180017c8c`
- `0x180017df0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014777`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014777`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800147ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800147ea`

## string_xrefs

- `0x1800146e0`: `onecore\ds\security\cryptoapi\xml\lib\bignum.cpp`
- `0x180014791`: `onecore\ds\security\cryptoapi\xml\lib\bignum.cpp`
- `0x1800147c4`: `onecore\ds\security\cryptoapi\xml\lib\bignum.cpp`
- `0x180014812`: `onecore\ds\security\cryptoapi\xml\lib\bignum.cpp`

## pseudocode

```c
__int64 __fastcall I_DecStringToBigEndianBytes(_WORD *a1, unsigned int a2, _QWORD *a3, unsigned int *a4)
{
  unsigned int v6; // esi
  unsigned int v8; // ebx
  unsigned int v9; // r15d
  unsigned int v10; // eax
  unsigned int v11; // ebp
  _DWORD *v12; // rax
  _DWORD *v13; // rdi
  _DWORD *v14; // r15
  __int64 v15; // r9
  unsigned __int16 v16; // r8
  unsigned __int64 v17; // r11
  unsigned int v18; // r10d
  __int64 i; // rbp
  unsigned __int64 v20; // r11
  unsigned __int64 v21; // r10
  __int64 v22; // r8
  unsigned int v23; // edx
  unsigned __int64 v24; // r10
  const char *v25; // r8
  int v26; // r9d
  const char *v27; // rax
  bool v28; // zf
  int v29; // edx
  int v30; // esi
  __int64 v31; // rcx
  int v32; // r10d
  __int64 v33; // r9
  int v34; // r8d
  int v35; // esi
  unsigned int v36; // esi
  HLOCAL v37; // rax
  void *v38; // rbp
  int v39; // r10d
  const char *v40; // rax
  const char *v41; // rax
  int v42; // r10d

  *a3 = 0;
  *a4 = 0;
  v6 = a2;
  v8 = 1;
  if ( a2 )
  {
    if ( a2 > 1 )
    {
      do
      {
        if ( *a1 != 48 )
          break;
        ++a1;
        --v6;
      }
      while ( v6 > 1 );
    }
    v9 = (((32 * (v6 / 9 + 1)) >> 9) + ((((32 * (v6 / 9 + 1)) & 0x1FF) + 511) >> 9) + 1) << 6;
    v10 = SymCryptFdefSizeofIntFromDigits(v9);
    v11 = v10;
    if ( v10 && (v12 = (_DWORD *)SymCryptCallbackAlloc(v10), (v13 = v12) != 0) )
    {
      *v12 = 1732837376;
      v12[1] = v9;
      v12[2] = v11;
      v14 = v12 + 8;
      SymCryptWipeAsm(v12 + 8, (unsigned int)(v12[1] << 6));
      v15 = 0;
      *v14 = 0;
      while ( (unsigned int)v15 < v6 )
      {
        v16 = a1[v15] - 48;
        if ( v16 > 9u )
        {
          v8 = -2146885360;
          v25 = "";
          v26 = 92;
          while ( 1 )
          {
            v27 = v25--;
            v28 = *v25 == 92;
            if ( *v25 == 92 )
              break;
            if ( v25 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\bignum.cpp" )
            {
              v28 = *v25 == 92;
              break;
            }
          }
          if ( v28 )
            v25 = v27;
          v29 = -2146885360;
          goto LABEL_22;
        }
        v17 = 0;
        v18 = 16 * v13[1];
        for ( i = 0; (unsigned int)i < v18; v17 = HIDWORD(v20) )
        {
          v20 = v17 + 10LL * (unsigned int)v13[i + 8];
          v13[i + 8] = v20;
          i = (unsigned int)(i + 1);
        }
        v21 = v16;
        v22 = 0;
        v23 = 16 * v13[1];
        if ( v23 )
        {
          do
          {
            v24 = (unsigned int)v13[v22 + 8] + v21;
            v13[v22 + 8] = v24;
            v22 = (unsigned int)(v22 + 1);
            v21 = HIDWORD(v24);
          }
          while ( (unsigned int)v22 < v23 );
        }
        v15 = (unsigned int)(v15 + 1);
      }
      v30 = 0;
      v31 = 0;
      v32 = -1;
      LODWORD(v33) = v13[1] << 6 >> 2;
      while ( (_DWORD)v33 )
      {
        v33 = (unsigned int)(v33 - 1);
        v34 = v32 & ((unsigned __int64)-(__int64)(unsigned int)v13[v33 + 8] >> 32);
        v31 = v34 & v13[v33 + 8] | (unsigned int)v31;
        v30 |= v33 & v34;
        v32 &= ~v34;
      }
      v35 = SymCryptFdefBitsizeOfUint32(v31) + 32 * v30;
      if ( v35 )
        v36 = (unsigned int)(v35 + 7) >> 3;
      else
        v36 = 1;
      v37 = LocalAlloc(0x40u, v36);
      v38 = v37;
      if ( !v37 )
      {
        v8 = -2147024888;
        v25 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\bignum.cpp");
        v26 = 112;
        v29 = v39;
LABEL_22:
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v29, v25, v26);
        goto LABEL_34;
      }
      if ( (unsigned int)SymCryptFdefRawGetValue(v14, (unsigned int)v13[1], v37, v36) )
      {
        v40 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\bignum.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", 1, v40, 120);
        LocalFree(v38);
      }
      else
      {
        *a3 = v38;
        v8 = 0;
        *a4 = v36;
      }
LABEL_34:
      SymCryptIntFree(v13);
    }
    else
    {
      v8 = -2147024888;
      v41 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\bignum.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v42, v41, 79);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180014590  push    rbx
0x180014592  push    rbp
0x180014593  push    rsi
0x180014594  push    rdi
0x180014595  push    r12
0x180014597  push    r13
0x180014599  push    r14
0x18001459b  push    r15
0x18001459d  sub     rsp, 38h
0x1800145a1  mov     qword ptr [r8], 0
0x1800145a8  mov     r12, r9
0x1800145ab  mov     dword ptr [r9], 0
0x1800145b2  mov     r13, r8
0x1800145b5  mov     esi, edx
0x1800145b7  mov     r14, rcx
0x1800145ba  mov     ebx, 1
0x1800145bf  test    edx, edx
0x1800145c1  jz      loc_180014839
0x1800145c7  cmp     edx, ebx
0x1800145c9  jbe     short loc_1800145DC
0x1800145cb  cmp     word ptr [r14], 30h ; '0'
0x1800145d0  jnz     short loc_1800145DC
0x1800145d2  add     r14, 2
0x1800145d6  dec     esi
0x1800145d8  cmp     esi, ebx
0x1800145da  ja      short loc_1800145CB
0x1800145dc  mov     ecx, 1FFh
0x1800145e1  mov     eax, 38E38E39h
0x1800145e6  mul     esi
0x1800145e8  shr     edx, 1
0x1800145ea  add     edx, ebx
0x1800145ec  shl     edx, 5
0x1800145ef  mov     r15d, edx
0x1800145f2  shr     edx, 9
0x1800145f5  and     r15d, ecx
0x1800145f8  add     r15d, ecx
0x1800145fb  shr     r15d, 9
0x1800145ff  inc     r15d
0x180014602  add     r15d, edx
0x180014605  shl     r15d, 6
0x180014609  mov     ecx, r15d
0x18001460c  call    SymCryptFdefSizeofIntFromDigits
0x180014611  mov     ebp, eax
0x180014613  test    eax, eax
0x180014615  jz      loc_18001480C
0x18001461b  mov     ecx, ebp
0x18001461d  call    SymCryptCallbackAlloc
0x180014622  mov     rdi, rax
0x180014625  test    rax, rax
0x180014628  jz      loc_18001480C
0x18001462e  mov     dword ptr [rax], 67490000h
0x180014634  mov     [rax+4], r15d
0x180014638  mov     [rax+8], ebp
0x18001463b  mov     edx, [rax+4]
0x18001463e  lea     r15, [rax+20h]
0x180014642  shl     edx, 6
0x180014645  mov     rcx, r15
0x180014648  call    SymCryptWipeAsm
0x18001464d  xor     r9d, r9d
0x180014650  mov     dword ptr [r15], 0
0x180014657  cmp     r9d, esi
0x18001465a  jnb     loc_180014711
0x180014660  movzx   r8d, word ptr [r14+r9*2]
0x180014665  sub     r8w, 30h ; '0'
0x18001466a  cmp     r8w, 9
0x18001466f  ja      short loc_1800146CE
0x180014671  mov     r10d, [rdi+4]
0x180014675  xor     r11d, r11d
0x180014678  shl     r10d, 4
0x18001467c  xor     ebp, ebp
0x18001467e  test    r10d, r10d
0x180014681  jz      short loc_18001469F
0x180014683  mov     eax, [rdi+rbp*4+20h]
0x180014687  lea     rcx, [rax+rax*4]
0x18001468b  lea     r11, [r11+rcx*2]
0x18001468f  mov     [rdi+rbp*4+20h], r11d
0x180014694  add     ebp, ebx
0x180014696  shr     r11, 20h
0x18001469a  cmp     ebp, r10d
0x18001469d  jb      short loc_180014683
0x18001469f  mov     edx, [rdi+4]
0x1800146a2  movzx   r10d, r8w
0x1800146a6  xor     r8d, r8d
0x1800146a9  shl     edx, 4
0x1800146ac  test    edx, edx
0x1800146ae  jz      short loc_1800146C9
0x1800146b0  mov     eax, [rdi+r8*4+20h]
0x1800146b5  add     r10, rax
0x1800146b8  mov     [rdi+r8*4+20h], r10d
0x1800146bd  add     r8d, ebx
0x1800146c0  shr     r10, 20h
0x1800146c4  cmp     r8d, edx
0x1800146c7  jb      short loc_1800146B0
0x1800146c9  add     r9d, ebx
0x1800146cc  jmp     short loc_180014657
0x1800146ce  mov     ebx, 80092110h
0x1800146d3  lea     r8, aOnecoreDsSecur_4+30h; ""
0x1800146da  mov     r9d, 5Ch ; '\'
0x1800146e0  lea     rcx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800146e7  mov     rax, r8
0x1800146ea  dec     r8
0x1800146ed  cmp     [r8], r9b
0x1800146f0  jz      short loc_1800146FA
0x1800146f2  cmp     r8, rcx
0x1800146f5  ja      short loc_1800146E7
0x1800146f7  cmp     [r8], r9b
0x1800146fa  cmovz   r8, rax
0x1800146fe  mov     edx, ebx
0x180014700  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180014707  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18001470c  jmp     loc_180014802
0x180014711  mov     r9d, [rdi+4]
0x180014715  or      r11d, 0FFFFFFFFh
0x180014719  shl     r9d, 6
0x18001471d  xor     esi, esi
0x18001471f  xor     ecx, ecx
0x180014721  mov     r10d, r11d
0x180014724  shr     r9d, 2
0x180014728  jmp     short loc_180014752
0x18001472a  add     r9d, r11d
0x18001472d  mov     edx, [rdi+r9*4+20h]
0x180014732  mov     r8d, edx
0x180014735  neg     r8
0x180014738  shr     r8, 20h
0x18001473c  and     r8d, r10d
0x18001473f  and     edx, r8d
0x180014742  mov     eax, r8d
0x180014745  and     eax, r9d
0x180014748  or      ecx, edx
0x18001474a  or      esi, eax
0x18001474c  not     r8d
0x18001474f  and     r10d, r8d
0x180014752  test    r9d, r9d
0x180014755  jnz     short loc_18001472A
0x180014757  call    SymCryptFdefBitsizeOfUint32
0x18001475c  shl     esi, 5
0x18001475f  add     esi, eax
0x180014761  jnz     short loc_180014767
0x180014763  mov     esi, ebx
0x180014765  jmp     short loc_18001476D
0x180014767  add     esi, 7
0x18001476a  shr     esi, 3
0x18001476d  mov     edx, esi; uBytes
0x18001476f  mov     ecx, 40h ; '@'; uFlags
0x180014774  mov     r14d, esi
0x180014777  call    cs:__imp_LocalAlloc
0x18001477e  nop     dword ptr [rax+rax+00h]
0x180014783  mov     rbp, rax
0x180014786  test    rax, rax
0x180014789  jnz     short loc_1800147AF
0x18001478b  mov     r10d, 80070008h
0x180014791  lea     rcx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180014798  mov     ebx, r10d
0x18001479b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800147a0  mov     r8, rax
0x1800147a3  lea     r9d, [rbp+70h]
0x1800147a7  mov     edx, r10d
0x1800147aa  jmp     loc_180014700
0x1800147af  mov     edx, [rdi+4]
0x1800147b2  mov     r9, r14
0x1800147b5  mov     r8, rbp
0x1800147b8  mov     rcx, r15
0x1800147bb  call    SymCryptFdefRawGetValue
0x1800147c0  test    eax, eax
0x1800147c2  jz      short loc_1800147F8
0x1800147c4  lea     rcx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800147cb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800147d0  mov     r8, rax
0x1800147d3  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800147da  mov     edx, ebx
0x1800147dc  mov     r9d, 78h ; 'x'
0x1800147e2  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800147e7  mov     rcx, rbp; hMem
0x1800147ea  call    cs:__imp_LocalFree
0x1800147f1  nop     dword ptr [rax+rax+00h]
0x1800147f6  jmp     short loc_180014802
0x1800147f8  mov     [r13+0], rbp
0x1800147fc  xor     ebx, ebx
0x1800147fe  mov     [r12], esi
0x180014802  mov     rcx, rdi
0x180014805  call    SymCryptIntFree
0x18001480a  jmp     short loc_180014839
0x18001480c  mov     r10d, 80070008h
0x180014812  lea     rcx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180014819  mov     ebx, r10d
0x18001481c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180014821  mov     r8, rax
0x180014824  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18001482b  mov     edx, r10d
0x18001482e  mov     r9d, 4Fh ; 'O'
0x180014834  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180014839  mov     eax, ebx
0x18001483b  add     rsp, 38h
0x18001483f  pop     r15
0x180014841  pop     r14
0x180014843  pop     r13
0x180014845  pop     r12
0x180014847  pop     rdi
0x180014848  pop     rsi
0x180014849  pop     rbp
0x18001484a  pop     rbx
0x18001484b  retn
```
