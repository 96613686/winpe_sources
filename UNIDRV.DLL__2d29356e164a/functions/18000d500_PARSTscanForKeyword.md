# PARSTscanForKeyword

- ea: `0x18000d500`
- end: `0x18000da6a`
- name: `PARSTscanForKeyword`
- size: `1386`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000d1d8`

## callees

- `0x180007220`
- `0x18000d500`
- `0x18000def0`
- `0x18000e0c0`
- `0x18000e12c`
- `0x18000e200`
- `0x18000e2b0`
- `0x18004485c`
- `0x180070f60`

## string_xrefs

- `0x18000d840`: `syntax error: valid keyword token expected: %0.*s.`

## pseudocode

```c
__int64 __fastcall PARSTscanForKeyword(unsigned int *a1, __int64 a2)
{
  unsigned int v2; // r8d
  __int64 v4; // rbp
  __int64 v6; // rcx
  unsigned int v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // ecx
  __int64 v10; // r15
  __int64 v11; // rcx
  __int64 v12; // rsi
  __int64 v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // r8
  char *v16; // r10
  char v17; // al
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // rdi
  __int64 v22; // r11
  __int64 v23; // rdx
  int j; // r10d
  __int64 v25; // r8
  __int64 v26; // r9
  unsigned __int8 v27; // dl
  bool v28; // zf
  unsigned int v29; // r8d
  __int64 v30; // r11
  __int64 v31; // rdx
  int i; // r10d
  __int64 v33; // r8
  __int64 v34; // r9
  unsigned __int8 v35; // dl
  unsigned __int8 v36; // dl
  __int64 result; // rax
  unsigned __int8 v38; // dl
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx

  v2 = *a1;
  v4 = *(_QWORD *)(a2 + 480);
  if ( !*a1 )
  {
    v9 = 0;
LABEL_6:
    v10 = 0x87FFFFFE03FFLL;
    *(_DWORD *)(56LL * v9 + v4 + 44) = *(_DWORD *)(32LL * (unsigned int)(*(_DWORD *)(a2 + 468) - 1)
                                                 + *(_QWORD *)(a2 + 456)
                                                 + 16);
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              v11 = *(_QWORD *)(a2 + 456) + 32LL * (unsigned int)(*(_DWORD *)(a2 + 468) - 1);
              if ( *(_DWORD *)(v11 + 8) >= *(_DWORD *)(v11 + 12) || !(unsigned int)BeatArbitraryWhite(a2) )
                return 1;
              v12 = *a1;
              v13 = 56 * v12 + v4;
              *(_DWORD *)(v13 + 48) = *(_DWORD *)(32LL * (unsigned int)(*(_DWORD *)(a2 + 468) - 1)
                                                + *(_QWORD *)(a2 + 456)
                                                + 20);
              v14 = *(_QWORD *)(a2 + 456) + 32LL * (unsigned int)(*(_DWORD *)(a2 + 468) - 1);
              v15 = *(unsigned int *)(v14 + 8);
              v16 = (char *)(v15 + *(_QWORD *)v14);
              v17 = *v16;
              if ( *v16 == 13 )
              {
                *(_DWORD *)(v14 + 8) = v15 + 1;
                v18 = *(_QWORD *)(a2 + 456) + 32LL * (unsigned int)(*(_DWORD *)(a2 + 468) - 1);
                v19 = *(unsigned int *)(v18 + 8);
                if ( (unsigned int)v19 >= *(_DWORD *)(v18 + 12) )
                  goto LABEL_11;
                v28 = *(_BYTE *)(v19 + *(_QWORD *)v18) == 10;
                goto LABEL_25;
              }
              if ( v17 != 42 )
                break;
              v29 = v15 + 1;
              if ( v29 >= *(_DWORD *)(v14 + 12) )
              {
                vIdentifySource(56 * v12 + v4, a2);
                WriteDbgTraceErrorGpd("PARSTscanForKeyword", "Unexpected EOF encountered parsing Keyword.");
                v41 = 32LL * (unsigned int)(*(_DWORD *)(a2 + 468) - 1);
                ++*(_DWORD *)(v41 + *(_QWORD *)(a2 + 456) + 8);
              }
              else
              {
                *(_DWORD *)(v14 + 8) = v29;
                v30 = 56 * v12 + *(_QWORD *)(a2 + 480);
                v31 = *(_QWORD *)(a2 + 456) + 32LL * (unsigned int)(*(_DWORD *)(a2 + 468) - 1);
                *(_QWORD *)(v30 + 8) = *(_QWORD *)v31 + *(unsigned int *)(v31 + 8);
                for ( i = 0; ; ++i )
                {
                  v33 = *(_QWORD *)(a2 + 456) + 32LL * (unsigned int)(*(_DWORD *)(a2 + 468) - 1);
                  v34 = *(unsigned int *)(v33 + 8);
                  if ( (unsigned int)v34 >= *(_DWORD *)(v33 + 12) )
                    break;
                  v35 = *(_BYTE *)(v34 + *(_QWORD *)v33);
                  if ( v35 == 63 )
                  {
                    ++i;
                    *(_DWORD *)(v33 + 8) = v34 + 1;
                    break;
                  }
                  if ( v35 < 0x61u )
                  {
                    v36 = v35 - 48;
                    if ( v36 > 0x2Fu || !_bittest64(&v10, v36) )
                      break;
                  }
                  else if ( v35 > 0x7Au )
                  {
                    break;
                  }
                  *(_DWORD *)(v33 + 8) = v34 + 1;
                }
                *(_DWORD *)(v30 + 16) = i;
                if ( i )
                {
                  *(_DWORD *)v13 = DWidentifyKeyword((unsigned int)v12, a2);
                  return 3;
                }
                vIdentifySource(56 * v12 + v4, a2);
                WriteDbgTraceErrorGpd(
                  "PARSTscanForKeyword",
                  "syntax error in Keyword: %0.*s.",
                  *(_DWORD *)(56LL * *a1 + v4 + 16) + 1,
                  (const char *)(*(_QWORD *)(56LL * *a1 + v4 + 8) - 1LL));
                *(_DWORD *)(56LL * *a1 + v4 + 52) = 0;
                v39 = 32LL * (unsigned int)(*(_DWORD *)(a2 + 468) - 1);
                --*(_DWORD *)(v39 + *(_QWORD *)(a2 + 456) + 8);
                BeatComment(a2);
              }
            }
            if ( v17 == 125 )
              goto LABEL_50;
            if ( v17 != 10 )
              break;
            *(_DWORD *)(v14 + 8) = v15 + 1;
            v18 = *(_QWORD *)(a2 + 456) + 32LL * (unsigned int)(*(_DWORD *)(a2 + 468) - 1);
            v19 = *(unsigned int *)(v18 + 8);
            if ( (unsigned int)v19 >= *(_DWORD *)(v18 + 12) )
              goto LABEL_11;
            v28 = *(_BYTE *)(v19 + *(_QWORD *)v18) == 13;
LABEL_25:
            if ( v28 )
              *(_DWORD *)(v18 + 8) = v19 + 1;
LABEL_11:
            v20 = 32LL * (unsigned int)(*(_DWORD *)(a2 + 468) - 1);
            ++*(_DWORD *)(v20 + *(_QWORD *)(a2 + 456) + 20);
          }
          if ( v17 != 26 )
            break;
          *(_DWORD *)(v14 + 8) = v15 + 1;
        }
        if ( v17 == 123 )
        {
LABEL_50:
          *(_QWORD *)(v13 + 8) = v16;
          *(_DWORD *)(v13 + 16) = 1;
          *(_QWORD *)(v13 + 24) = 0;
          *(_DWORD *)(v13 + 32) = 0;
          *(_DWORD *)(v13 + 52) |= 1u;
          *(_DWORD *)v13 = DWidentifyKeyword((unsigned int)v12, a2);
          v40 = (unsigned int)(*(_DWORD *)(a2 + 468) - 1);
          *a1 = v12 + 1;
          ++*(_DWORD *)(32 * v40 + *(_QWORD *)(a2 + 456) + 8);
          return 2;
        }
        if ( (unsigned int)BisExternKeyword((unsigned int)v12, a2) )
          break;
        v21 = *(_QWORD *)(a2 + 480);
        v22 = 56LL * *a1;
        v23 = *(_QWORD *)(a2 + 456) + 32LL * (unsigned int)(*(_DWORD *)(a2 + 468) - 1);
        *(_QWORD *)(v21 + v22 + 8) = *(_QWORD *)v23 + *(unsigned int *)(v23 + 8);
        for ( j = 0; ; ++j )
        {
          v25 = *(_QWORD *)(a2 + 456) + 32LL * (unsigned int)(*(_DWORD *)(a2 + 468) - 1);
          v26 = *(unsigned int *)(v25 + 8);
          if ( (unsigned int)v26 >= *(_DWORD *)(v25 + 12) )
            break;
          v27 = *(_BYTE *)(v26 + *(_QWORD *)v25);
          if ( v27 == 63 )
          {
            ++j;
            *(_DWORD *)(v25 + 8) = v26 + 1;
            break;
          }
          if ( v27 < 0x61u )
          {
            v38 = v27 - 48;
            if ( v38 > 0x2Fu || !_bittest64(&v10, v38) )
              break;
          }
          else if ( v27 > 0x7Au )
          {
            break;
          }
          *(_DWORD *)(v25 + 8) = v26 + 1;
        }
        *(_DWORD *)(v21 + v22 + 16) = j;
        if ( j )
        {
          *(_DWORD *)(v22 + v4) = 65282;
          result = 3;
          *(_DWORD *)(v22 + v4 + 52) |= 0x80u;
          return result;
        }
        vIdentifySource(v22 + v4, a2);
        WriteDbgTraceErrorGpd(
          "PARSTscanForKeyword",
          "syntax error: valid keyword token expected: %0.*s.",
          *(_DWORD *)(56LL * *a1 + v4 + 16),
          *(const char **)(56LL * *a1 + v4 + 8));
LABEL_43:
        *(_DWORD *)(56LL * *a1 + v4 + 52) = 0;
        BeatComment(a2);
      }
      if ( !(unsigned int)BisColonNext(a2) )
      {
        vIdentifySource(v4 + 56LL * *a1, a2);
        WriteDbgTraceErrorGpd("PARSTscanForKeyword", "syntax error:  Colon expected but missing.");
        goto LABEL_43;
      }
    }
  }
  v6 = v2 - 1;
  v7 = *(_DWORD *)(56 * v6 + v4);
  if ( v7 >= 0xFF00
    || (v8 = 4LL * v7, LODWORD((&mMainKeywordTable)[v8 + 2]) != 2)
    || *((_DWORD *)&mMainKeywordTable + 2 * v8 + 5) != 10 )
  {
    if ( v2 > *(_DWORD *)(a2 + 2560) && !(unsigned int)BarchiveStrings(v6, a2) )
      return 6;
    v9 = *a1;
    *(_DWORD *)(a2 + 2560) = *a1;
    goto LABEL_6;
  }
  *a1 = v6;
  return 5;
}

```

## disassembly

```asm
0x18000d500  push    rbx
0x18000d502  push    rbp
0x18000d503  push    r14
0x18000d505  sub     rsp, 20h
0x18000d509  mov     r8d, [rcx]
0x18000d50c  mov     rbx, rdx
0x18000d50f  mov     rbp, [rdx+1E0h]
0x18000d516  mov     r14, rcx
0x18000d519  test    r8d, r8d
0x18000d51c  jz      loc_18000D87D
0x18000d522  lea     ecx, [r8-1]
0x18000d526  mov     eax, ecx
0x18000d528  imul    rdx, rax, 38h ; '8'
0x18000d52c  mov     eax, [rdx+rbp]
0x18000d52f  cmp     eax, 0FF00h
0x18000d534  jnb     short loc_18000D54E
0x18000d536  mov     edx, eax
0x18000d538  lea     rax, mMainKeywordTable
0x18000d53f  shl     rdx, 5
0x18000d543  cmp     dword ptr [rdx+rax+10h], 2
0x18000d548  jz      loc_18000D979
0x18000d54e  cmp     r8d, [rbx+0A00h]
0x18000d555  ja      loc_18000D884
0x18000d55b  mov     ecx, [r14]
0x18000d55e  mov     [rbx+0A00h], ecx
0x18000d564  mov     r8d, [rbx+1D4h]
0x18000d56b  mov     rdx, [rbx+1C8h]
0x18000d572  dec     r8d
0x18000d575  mov     [rsp+38h+arg_10], r15
0x18000d57a  mov     r15, 87FFFFFE03FFh
0x18000d584  shl     r8, 5
0x18000d588  mov     eax, ecx
0x18000d58a  imul    rcx, rax, 38h ; '8'
0x18000d58e  mov     eax, [r8+rdx+10h]
0x18000d593  mov     [rsp+38h+arg_0], rsi
0x18000d598  mov     [rsp+38h+arg_8], rdi
0x18000d59d  mov     [rcx+rbp+2Ch], eax
0x18000d5a1  mov     ecx, [rbx+1D4h]
0x18000d5a7  dec     ecx
0x18000d5a9  shl     rcx, 5
0x18000d5ad  add     rcx, [rbx+1C8h]
0x18000d5b4  mov     eax, [rcx+0Ch]
0x18000d5b7  cmp     [rcx+8], eax
0x18000d5ba  jnb     loc_18000D91E
0x18000d5c0  mov     rcx, rbx
0x18000d5c3  call    BeatArbitraryWhite
0x18000d5c8  test    eax, eax
0x18000d5ca  jz      loc_18000D91E
0x18000d5d0  mov     ecx, [rbx+1D4h]
0x18000d5d6  mov     rax, [rbx+1C8h]
0x18000d5dd  dec     ecx
0x18000d5df  mov     esi, [r14]
0x18000d5e2  imul    r9, rsi, 38h ; '8'
0x18000d5e6  shl     rcx, 5
0x18000d5ea  lea     rdi, [r9+rbp]
0x18000d5ee  mov     ecx, [rcx+rax+14h]
0x18000d5f2  mov     [rdi+30h], ecx
0x18000d5f5  mov     edx, [rbx+1D4h]
0x18000d5fb  dec     edx
0x18000d5fd  shl     rdx, 5
0x18000d601  add     rdx, [rbx+1C8h]
0x18000d608  mov     r8d, [rdx+8]
0x18000d60c  mov     r10, [rdx]
0x18000d60f  add     r10, r8
0x18000d612  movzx   eax, byte ptr [r10]
0x18000d616  cmp     al, 0Dh
0x18000d618  jnz     short loc_18000D65E
0x18000d61a  lea     eax, [r8+1]
0x18000d61e  mov     [rdx+8], eax
0x18000d621  mov     edx, [rbx+1D4h]
0x18000d627  dec     edx
0x18000d629  shl     rdx, 5
0x18000d62d  add     rdx, [rbx+1C8h]
0x18000d634  mov     r8d, [rdx+8]
0x18000d638  cmp     r8d, [rdx+0Ch]
0x18000d63c  jb      loc_18000D723
0x18000d642  mov     ecx, [rbx+1D4h]
0x18000d648  mov     rax, [rbx+1C8h]
0x18000d64f  dec     ecx
0x18000d651  shl     rcx, 5
0x18000d655  inc     dword ptr [rcx+rax+14h]
0x18000d659  jmp     loc_18000D5A1
0x18000d65e  cmp     al, 2Ah ; '*'
0x18000d660  jz      loc_18000D73D
0x18000d666  cmp     al, 7Dh ; '}'
0x18000d668  jz      loc_18000D928
0x18000d66e  cmp     al, 0Ah
0x18000d670  jz      loc_18000DA35
0x18000d676  cmp     al, 1Ah
0x18000d678  jz      loc_18000DA29
0x18000d67e  cmp     al, 7Bh ; '{'
0x18000d680  jz      loc_18000D928
0x18000d686  mov     rdx, rbx
0x18000d689  mov     ecx, esi
0x18000d68b  call    BisExternKeyword
0x18000d690  test    eax, eax
0x18000d692  jnz     loc_18000D9CF
0x18000d698  mov     edx, [rbx+1D4h]
0x18000d69e  mov     eax, [r14]
0x18000d6a1  dec     edx
0x18000d6a3  mov     rdi, [rbx+1E0h]
0x18000d6aa  imul    r11, rax, 38h ; '8'
0x18000d6ae  shl     rdx, 5
0x18000d6b2  add     rdx, [rbx+1C8h]
0x18000d6b9  mov     eax, [rdx+8]
0x18000d6bc  add     rax, [rdx]
0x18000d6bf  mov     [rdi+r11+8], rax
0x18000d6c4  xor     r10d, r10d
0x18000d6c7  nop     word ptr [rax+rax+00000000h]
0x18000d6d0  mov     r8d, [rbx+1D4h]
0x18000d6d7  dec     r8d
0x18000d6da  shl     r8, 5
0x18000d6de  add     r8, [rbx+1C8h]
0x18000d6e5  mov     r9d, [r8+8]
0x18000d6e9  cmp     r9d, [r8+0Ch]
0x18000d6ed  jnb     loc_18000D823
0x18000d6f3  mov     rax, [r8]
0x18000d6f6  movzx   edx, byte ptr [r9+rax]
0x18000d6fb  cmp     dl, 3Fh ; '?'
0x18000d6fe  jz      loc_18000DA09
0x18000d704  cmp     dl, 61h ; 'a'
0x18000d707  jb      loc_18000D80E
0x18000d70d  cmp     dl, 7Ah ; 'z'
0x18000d710  ja      loc_18000D823
0x18000d716  lea     eax, [r9+1]
0x18000d71a  inc     r10d
0x18000d71d  mov     [r8+8], eax
0x18000d721  jmp     short loc_18000D6D0
0x18000d723  mov     rax, [rdx]
0x18000d726  cmp     byte ptr [r8+rax], 0Ah
0x18000d72b  jnz     loc_18000D642
0x18000d731  lea     eax, [r8+1]
0x18000d735  mov     [rdx+8], eax
0x18000d738  jmp     loc_18000D642
0x18000d73d  inc     r8d
0x18000d740  cmp     r8d, [rdx+0Ch]
0x18000d744  jnb     loc_18000D995
0x18000d74a  mov     [rdx+8], r8d
0x18000d74e  mov     edx, [rbx+1D4h]
0x18000d754  mov     r11, [rbx+1E0h]
0x18000d75b  dec     edx
0x18000d75d  shl     rdx, 5
0x18000d761  add     r11, r9
0x18000d764  add     rdx, [rbx+1C8h]
0x18000d76b  mov     eax, [rdx+8]
0x18000d76e  add     rax, [rdx]
0x18000d771  mov     [r11+8], rax
0x18000d775  xor     r10d, r10d
0x18000d778  nop     dword ptr [rax+rax+00000000h]
0x18000d780  mov     r8d, [rbx+1D4h]
0x18000d787  dec     r8d
0x18000d78a  shl     r8, 5
0x18000d78e  add     r8, [rbx+1C8h]
0x18000d795  mov     r9d, [r8+8]
0x18000d799  cmp     r9d, [r8+0Ch]
0x18000d79d  jnb     short loc_18000D7D8
0x18000d79f  mov     rax, [r8]
0x18000d7a2  movzx   edx, byte ptr [r9+rax]
0x18000d7a7  cmp     dl, 3Fh ; '?'
0x18000d7aa  jz      loc_18000DA19
0x18000d7b0  cmp     dl, 61h ; 'a'
0x18000d7b3  jb      short loc_18000D7C7
0x18000d7b5  cmp     dl, 7Ah ; 'z'
0x18000d7b8  ja      short loc_18000D7D8
0x18000d7ba  lea     eax, [r9+1]
0x18000d7be  inc     r10d
0x18000d7c1  mov     [r8+8], eax
0x18000d7c5  jmp     short loc_18000D780
0x18000d7c7  sub     dl, 30h ; '0'
0x18000d7ca  cmp     dl, 2Fh ; '/'
0x18000d7cd  ja      short loc_18000D7D8
0x18000d7cf  movzx   eax, dl
0x18000d7d2  bt      r15, rax
0x18000d7d6  jb      short loc_18000D7BA
0x18000d7d8  mov     [r11+10h], r10d
0x18000d7dc  mov     rdx, rbx
0x18000d7df  test    r10d, r10d
0x18000d7e2  jz      loc_18000D89E
0x18000d7e8  mov     ecx, esi
0x18000d7ea  call    DWidentifyKeyword
0x18000d7ef  mov     [rdi], eax
0x18000d7f1  mov     eax, 3
0x18000d7f6  mov     rdi, [rsp+38h+arg_8]
0x18000d7fb  mov     rsi, [rsp+38h+arg_0]
0x18000d800  mov     r15, [rsp+38h+arg_10]
0x18000d805  add     rsp, 20h
0x18000d809  pop     r14
0x18000d80b  pop     rbp
0x18000d80c  pop     rbx
0x18000d80d  retn
0x18000d80e  sub     dl, 30h ; '0'
0x18000d811  cmp     dl, 2Fh ; '/'
0x18000d814  ja      short loc_18000D823
0x18000d816  movzx   eax, dl
0x18000d819  bt      r15, rax
0x18000d81d  jb      loc_18000D716
0x18000d823  mov     [rdi+r11+10h], r10d
0x18000d828  test    r10d, r10d
0x18000d82b  jnz     loc_18000D903
0x18000d831  lea     rcx, [r11+rbp]
0x18000d835  mov     rdx, rbx
0x18000d838  call    vIdentifySource
0x18000d83d  mov     eax, [r14]
0x18000d840  lea     rdx, aSyntaxErrorVal; "syntax error: valid keyword token expec"...
0x18000d847  imul    rcx, rax, 38h ; '8'
0x18000d84b  mov     r9, [rcx+rbp+8]
0x18000d850  mov     r8d, [rcx+rbp+10h]
0x18000d855  lea     rcx, aParstscanforke; "PARSTscanForKeyword"
0x18000d85c  call    WriteDbgTraceErrorGpd
0x18000d861  mov     eax, [r14]
0x18000d864  imul    rcx, rax, 38h ; '8'
0x18000d868  mov     dword ptr [rcx+rbp+34h], 0
0x18000d870  mov     rcx, rbx
0x18000d873  call    BeatComment
0x18000d878  jmp     loc_18000D5A1
0x18000d87d  xor     ecx, ecx
0x18000d87f  jmp     loc_18000D564
0x18000d884  mov     rdx, rbx
0x18000d887  call    BarchiveStrings
0x18000d88c  test    eax, eax
0x18000d88e  jnz     loc_18000D55B
0x18000d894  mov     eax, 6
0x18000d899  jmp     loc_18000D805
0x18000d89e  mov     rcx, rdi
0x18000d8a1  call    vIdentifySource
0x18000d8a6  mov     eax, [r14]
0x18000d8a9  lea     rdx, aSyntaxErrorInK; "syntax error in Keyword: %0.*s."
0x18000d8b0  imul    rcx, rax, 38h ; '8'
0x18000d8b4  mov     r9, [rcx+rbp+8]
0x18000d8b9  mov     r8d, [rcx+rbp+10h]
0x18000d8be  dec     r9
0x18000d8c1  inc     r8d
0x18000d8c4  lea     rcx, aParstscanforke; "PARSTscanForKeyword"
0x18000d8cb  call    WriteDbgTraceErrorGpd
0x18000d8d0  mov     eax, [r14]
0x18000d8d3  imul    rcx, rax, 38h ; '8'
0x18000d8d7  mov     dword ptr [rcx+rbp+34h], 0
0x18000d8df  mov     ecx, [rbx+1D4h]
0x18000d8e5  mov     rax, [rbx+1C8h]
0x18000d8ec  dec     ecx
0x18000d8ee  shl     rcx, 5
0x18000d8f2  dec     dword ptr [rcx+rax+8]
0x18000d8f6  mov     rcx, rbx
0x18000d8f9  call    BeatComment
0x18000d8fe  jmp     loc_18000D5A1
0x18000d903  mov     dword ptr [r11+rbp], 0FF02h
0x18000d90b  mov     eax, 3
0x18000d910  or      dword ptr [r11+rbp+34h], 80h
0x18000d919  jmp     loc_18000D7F6
0x18000d91e  mov     eax, 1
0x18000d923  jmp     loc_18000D7F6
0x18000d928  mov     [rdi+8], r10
0x18000d92c  mov     rdx, rbx
0x18000d92f  mov     dword ptr [rdi+10h], 1
0x18000d936  mov     ecx, esi
0x18000d938  mov     qword ptr [rdi+18h], 0
0x18000d940  mov     dword ptr [rdi+20h], 0
0x18000d947  or      dword ptr [rdi+34h], 1
0x18000d94b  call    DWidentifyKeyword
0x18000d950  mov     [rdi], eax
0x18000d952  lea     eax, [rsi+1]
0x18000d955  mov     ecx, [rbx+1D4h]
0x18000d95b  dec     ecx
0x18000d95d  mov     [r14], eax
0x18000d960  mov     rax, [rbx+1C8h]
0x18000d967  shl     rcx, 5
0x18000d96b  inc     dword ptr [rcx+rax+8]
0x18000d96f  mov     eax, 2
0x18000d974  jmp     loc_18000D7F6
0x18000d979  cmp     dword ptr [rdx+rax+14h], 0Ah
0x18000d97e  jnz     loc_18000D54E
0x18000d984  mov     [r14], ecx
0x18000d987  mov     eax, 5
0x18000d98c  add     rsp, 20h
0x18000d990  pop     r14
0x18000d992  pop     rbp
0x18000d993  pop     rbx
0x18000d994  retn
0x18000d995  mov     rdx, rbx
0x18000d998  mov     rcx, rdi
0x18000d99b  call    vIdentifySource
0x18000d9a0  lea     rdx, aUnexpectedEofE; "Unexpected EOF encountered parsing Keyw"...
0x18000d9a7  lea     rcx, aParstscanforke; "PARSTscanForKeyword"
0x18000d9ae  call    WriteDbgTraceErrorGpd
0x18000d9b3  mov     ecx, [rbx+1D4h]
0x18000d9b9  mov     rax, [rbx+1C8h]
0x18000d9c0  dec     ecx
0x18000d9c2  shl     rcx, 5
0x18000d9c6  inc     dword ptr [rcx+rax+8]
0x18000d9ca  jmp     loc_18000D5A1
0x18000d9cf  mov     rcx, rbx
0x18000d9d2  call    BisColonNext
0x18000d9d7  test    eax, eax
0x18000d9d9  jnz     loc_18000D5A1
0x18000d9df  mov     eax, [r14]
0x18000d9e2  mov     rdx, rbx
0x18000d9e5  imul    rcx, rax, 38h ; '8'
0x18000d9e9  add     rcx, rbp
0x18000d9ec  call    vIdentifySource
0x18000d9f1  lea     rdx, aSyntaxErrorCol; "syntax error:  Colon expected but missi"...
  ... truncated ...
```
