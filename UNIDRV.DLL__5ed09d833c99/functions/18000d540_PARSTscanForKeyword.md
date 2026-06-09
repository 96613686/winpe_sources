# PARSTscanForKeyword

- ea: `0x18000d540`
- end: `0x18000daac`
- name: `PARSTscanForKeyword`
- size: `1388`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000d218`

## callees

- `0x180007150`
- `0x18000d540`
- `0x18000df40`
- `0x18000e110`
- `0x18000e17c`
- `0x18000e250`
- `0x18000e300`
- `0x180045aa4`
- `0x180072fd4`

## string_xrefs

- `0x18000d881`: `syntax error: valid keyword token expected: %0.*s.`

## pseudocode

```c
__int64 __fastcall PARSTscanForKeyword(unsigned int *a1, __int64 a2)
{
  unsigned int v2; // r8d
  __int64 v4; // rbp
  unsigned int v6; // ecx
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
  __int64 v29; // r8
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
  __int64 v42; // r8

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
              v29 = (unsigned int)(v15 + 1);
              if ( (unsigned int)v29 >= *(_DWORD *)(v14 + 12) )
              {
                vIdentifySource((_DWORD *)(56 * v12 + v4), a2, v29);
                WriteDbgTraceErrorGpd((__int64)"PARSTscanForKeyword", "Unexpected EOF encountered parsing Keyword.");
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
                  *(_DWORD *)v13 = DWidentifyKeyword(v12, a2);
                  return 3;
                }
                vIdentifySource((_DWORD *)(56 * v12 + v4), a2, v33);
                WriteDbgTraceErrorGpd(
                  (__int64)"PARSTscanForKeyword",
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
          *(_DWORD *)v13 = DWidentifyKeyword(v12, a2);
          v40 = (unsigned int)(*(_DWORD *)(a2 + 468) - 1);
          *a1 = v12 + 1;
          ++*(_DWORD *)(32 * v40 + *(_QWORD *)(a2 + 456) + 8);
          return 2;
        }
        if ( (unsigned int)BisExternKeyword(v12, a2) )
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
        vIdentifySource((_DWORD *)(v22 + v4), a2, v25);
        WriteDbgTraceErrorGpd(
          (__int64)"PARSTscanForKeyword",
          "syntax error: valid keyword token expected: %0.*s.",
          *(_DWORD *)(56LL * *a1 + v4 + 16),
          *(const char **)(56LL * *a1 + v4 + 8));
LABEL_43:
        *(_DWORD *)(56LL * *a1 + v4 + 52) = 0;
        BeatComment(a2);
      }
      if ( !(unsigned int)BisColonNext(a2) )
      {
        vIdentifySource((_DWORD *)(v4 + 56LL * *a1), a2, v42);
        WriteDbgTraceErrorGpd((__int64)"PARSTscanForKeyword", "syntax error:  Colon expected but missing.");
        goto LABEL_43;
      }
    }
  }
  v6 = v2 - 1;
  v7 = *(_DWORD *)(56LL * (v2 - 1) + v4);
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
0x18000d540  push    rbx
0x18000d542  push    rbp
0x18000d543  push    r14
0x18000d545  sub     rsp, 20h
0x18000d549  mov     r8d, [rcx]
0x18000d54c  mov     rbx, rdx
0x18000d54f  mov     rbp, [rdx+1E0h]
0x18000d556  mov     r14, rcx
0x18000d559  test    r8d, r8d
0x18000d55c  jz      loc_18000D8BE
0x18000d562  lea     ecx, [r8-1]
0x18000d566  mov     eax, ecx
0x18000d568  imul    rdx, rax, 38h ; '8'
0x18000d56c  mov     eax, [rdx+rbp]
0x18000d56f  cmp     eax, 0FF00h
0x18000d574  jnb     short loc_18000D58E
0x18000d576  mov     edx, eax
0x18000d578  lea     rax, mMainKeywordTable
0x18000d57f  shl     rdx, 5
0x18000d583  cmp     dword ptr [rdx+rax+10h], 2
0x18000d588  jz      loc_18000D9BA
0x18000d58e  cmp     r8d, [rbx+0A00h]
0x18000d595  ja      loc_18000D8C5
0x18000d59b  mov     ecx, [r14]
0x18000d59e  mov     [rbx+0A00h], ecx
0x18000d5a4  mov     r8d, [rbx+1D4h]
0x18000d5ab  mov     rdx, [rbx+1C8h]
0x18000d5b2  dec     r8d
0x18000d5b5  mov     [rsp+38h+arg_10], r15
0x18000d5ba  mov     r15, 87FFFFFE03FFh
0x18000d5c4  shl     r8, 5
0x18000d5c8  mov     eax, ecx
0x18000d5ca  imul    rcx, rax, 38h ; '8'
0x18000d5ce  mov     eax, [r8+rdx+10h]
0x18000d5d3  mov     [rsp+38h+arg_0], rsi
0x18000d5d8  mov     [rsp+38h+arg_8], rdi
0x18000d5dd  mov     [rcx+rbp+2Ch], eax
0x18000d5e1  mov     ecx, [rbx+1D4h]
0x18000d5e7  dec     ecx
0x18000d5e9  shl     rcx, 5
0x18000d5ed  add     rcx, [rbx+1C8h]
0x18000d5f4  mov     eax, [rcx+0Ch]
0x18000d5f7  cmp     [rcx+8], eax
0x18000d5fa  jnb     loc_18000D95F
0x18000d600  mov     rcx, rbx
0x18000d603  call    BeatArbitraryWhite
0x18000d608  test    eax, eax
0x18000d60a  jz      loc_18000D95F
0x18000d610  mov     ecx, [rbx+1D4h]
0x18000d616  mov     rax, [rbx+1C8h]
0x18000d61d  dec     ecx
0x18000d61f  mov     esi, [r14]
0x18000d622  imul    r9, rsi, 38h ; '8'
0x18000d626  shl     rcx, 5
0x18000d62a  lea     rdi, [r9+rbp]
0x18000d62e  mov     ecx, [rcx+rax+14h]
0x18000d632  mov     [rdi+30h], ecx
0x18000d635  mov     edx, [rbx+1D4h]
0x18000d63b  dec     edx
0x18000d63d  shl     rdx, 5
0x18000d641  add     rdx, [rbx+1C8h]
0x18000d648  mov     r8d, [rdx+8]
0x18000d64c  mov     r10, [rdx]
0x18000d64f  add     r10, r8
0x18000d652  movzx   eax, byte ptr [r10]
0x18000d656  cmp     al, 0Dh
0x18000d658  jnz     short loc_18000D69E
0x18000d65a  lea     eax, [r8+1]
0x18000d65e  mov     [rdx+8], eax
0x18000d661  mov     edx, [rbx+1D4h]
0x18000d667  dec     edx
0x18000d669  shl     rdx, 5
0x18000d66d  add     rdx, [rbx+1C8h]
0x18000d674  mov     r8d, [rdx+8]
0x18000d678  cmp     r8d, [rdx+0Ch]
0x18000d67c  jb      loc_18000D763
0x18000d682  mov     ecx, [rbx+1D4h]
0x18000d688  mov     rax, [rbx+1C8h]
0x18000d68f  dec     ecx
0x18000d691  shl     rcx, 5
0x18000d695  inc     dword ptr [rcx+rax+14h]
0x18000d699  jmp     loc_18000D5E1
0x18000d69e  cmp     al, 2Ah ; '*'
0x18000d6a0  jz      loc_18000D77D
0x18000d6a6  cmp     al, 7Dh ; '}'
0x18000d6a8  jz      loc_18000D969
0x18000d6ae  cmp     al, 0Ah
0x18000d6b0  jz      loc_18000DA77
0x18000d6b6  cmp     al, 1Ah
0x18000d6b8  jz      loc_18000DA6B
0x18000d6be  cmp     al, 7Bh ; '{'
0x18000d6c0  jz      loc_18000D969
0x18000d6c6  mov     rdx, rbx
0x18000d6c9  mov     ecx, esi
0x18000d6cb  call    BisExternKeyword
0x18000d6d0  test    eax, eax
0x18000d6d2  jnz     loc_18000DA11
0x18000d6d8  mov     edx, [rbx+1D4h]
0x18000d6de  mov     eax, [r14]
0x18000d6e1  dec     edx
0x18000d6e3  mov     rdi, [rbx+1E0h]
0x18000d6ea  imul    r11, rax, 38h ; '8'
0x18000d6ee  shl     rdx, 5
0x18000d6f2  add     rdx, [rbx+1C8h]
0x18000d6f9  mov     eax, [rdx+8]
0x18000d6fc  add     rax, [rdx]
0x18000d6ff  mov     [rdi+r11+8], rax
0x18000d704  xor     r10d, r10d
0x18000d707  nop     word ptr [rax+rax+00000000h]
0x18000d710  mov     r8d, [rbx+1D4h]
0x18000d717  dec     r8d
0x18000d71a  shl     r8, 5
0x18000d71e  add     r8, [rbx+1C8h]
0x18000d725  mov     r9d, [r8+8]
0x18000d729  cmp     r9d, [r8+0Ch]
0x18000d72d  jnb     loc_18000D864
0x18000d733  mov     rax, [r8]
0x18000d736  movzx   edx, byte ptr [r9+rax]
0x18000d73b  cmp     dl, 3Fh ; '?'
0x18000d73e  jz      loc_18000DA4B
0x18000d744  cmp     dl, 61h ; 'a'
0x18000d747  jb      loc_18000D84F
0x18000d74d  cmp     dl, 7Ah ; 'z'
0x18000d750  ja      loc_18000D864
0x18000d756  lea     eax, [r9+1]
0x18000d75a  inc     r10d
0x18000d75d  mov     [r8+8], eax
0x18000d761  jmp     short loc_18000D710
0x18000d763  mov     rax, [rdx]
0x18000d766  cmp     byte ptr [r8+rax], 0Ah
0x18000d76b  jnz     loc_18000D682
0x18000d771  lea     eax, [r8+1]
0x18000d775  mov     [rdx+8], eax
0x18000d778  jmp     loc_18000D682
0x18000d77d  inc     r8d
0x18000d780  cmp     r8d, [rdx+0Ch]
0x18000d784  jnb     loc_18000D9D7
0x18000d78a  mov     [rdx+8], r8d
0x18000d78e  mov     edx, [rbx+1D4h]
0x18000d794  mov     r11, [rbx+1E0h]
0x18000d79b  dec     edx
0x18000d79d  shl     rdx, 5
0x18000d7a1  add     r11, r9
0x18000d7a4  add     rdx, [rbx+1C8h]
0x18000d7ab  mov     eax, [rdx+8]
0x18000d7ae  add     rax, [rdx]
0x18000d7b1  mov     [r11+8], rax
0x18000d7b5  xor     r10d, r10d
0x18000d7b8  nop     dword ptr [rax+rax+00000000h]
0x18000d7c0  mov     r8d, [rbx+1D4h]
0x18000d7c7  dec     r8d
0x18000d7ca  shl     r8, 5
0x18000d7ce  add     r8, [rbx+1C8h]
0x18000d7d5  mov     r9d, [r8+8]
0x18000d7d9  cmp     r9d, [r8+0Ch]
0x18000d7dd  jnb     short loc_18000D818
0x18000d7df  mov     rax, [r8]
0x18000d7e2  movzx   edx, byte ptr [r9+rax]
0x18000d7e7  cmp     dl, 3Fh ; '?'
0x18000d7ea  jz      loc_18000DA5B
0x18000d7f0  cmp     dl, 61h ; 'a'
0x18000d7f3  jb      short loc_18000D807
0x18000d7f5  cmp     dl, 7Ah ; 'z'
0x18000d7f8  ja      short loc_18000D818
0x18000d7fa  lea     eax, [r9+1]
0x18000d7fe  inc     r10d
0x18000d801  mov     [r8+8], eax
0x18000d805  jmp     short loc_18000D7C0
0x18000d807  sub     dl, 30h ; '0'
0x18000d80a  cmp     dl, 2Fh ; '/'
0x18000d80d  ja      short loc_18000D818
0x18000d80f  movzx   eax, dl
0x18000d812  bt      r15, rax
0x18000d816  jb      short loc_18000D7FA
0x18000d818  mov     [r11+10h], r10d
0x18000d81c  mov     rdx, rbx
0x18000d81f  test    r10d, r10d
0x18000d822  jz      loc_18000D8DF
0x18000d828  mov     ecx, esi
0x18000d82a  call    DWidentifyKeyword
0x18000d82f  mov     [rdi], eax
0x18000d831  mov     eax, 3
0x18000d836  mov     rdi, [rsp+38h+arg_8]
0x18000d83b  mov     rsi, [rsp+38h+arg_0]
0x18000d840  mov     r15, [rsp+38h+arg_10]
0x18000d845  add     rsp, 20h
0x18000d849  pop     r14
0x18000d84b  pop     rbp
0x18000d84c  pop     rbx
0x18000d84d  retn
0x18000d84f  sub     dl, 30h ; '0'
0x18000d852  cmp     dl, 2Fh ; '/'
0x18000d855  ja      short loc_18000D864
0x18000d857  movzx   eax, dl
0x18000d85a  bt      r15, rax
0x18000d85e  jb      loc_18000D756
0x18000d864  mov     [rdi+r11+10h], r10d
0x18000d869  test    r10d, r10d
0x18000d86c  jnz     loc_18000D944
0x18000d872  lea     rcx, [r11+rbp]
0x18000d876  mov     rdx, rbx
0x18000d879  call    vIdentifySource
0x18000d87e  mov     eax, [r14]
0x18000d881  lea     rdx, aSyntaxErrorVal; "syntax error: valid keyword token expec"...
0x18000d888  imul    rcx, rax, 38h ; '8'
0x18000d88c  mov     r9, [rcx+rbp+8]
0x18000d891  mov     r8d, [rcx+rbp+10h]
0x18000d896  lea     rcx, aParstscanforke; "PARSTscanForKeyword"
0x18000d89d  call    WriteDbgTraceErrorGpd
0x18000d8a2  mov     eax, [r14]
0x18000d8a5  imul    rcx, rax, 38h ; '8'
0x18000d8a9  mov     dword ptr [rcx+rbp+34h], 0
0x18000d8b1  mov     rcx, rbx
0x18000d8b4  call    BeatComment
0x18000d8b9  jmp     loc_18000D5E1
0x18000d8be  xor     ecx, ecx
0x18000d8c0  jmp     loc_18000D5A4
0x18000d8c5  mov     rdx, rbx
0x18000d8c8  call    BarchiveStrings
0x18000d8cd  test    eax, eax
0x18000d8cf  jnz     loc_18000D59B
0x18000d8d5  mov     eax, 6
0x18000d8da  jmp     loc_18000D845
0x18000d8df  mov     rcx, rdi
0x18000d8e2  call    vIdentifySource
0x18000d8e7  mov     eax, [r14]
0x18000d8ea  lea     rdx, aSyntaxErrorInK; "syntax error in Keyword: %0.*s."
0x18000d8f1  imul    rcx, rax, 38h ; '8'
0x18000d8f5  mov     r9, [rcx+rbp+8]
0x18000d8fa  mov     r8d, [rcx+rbp+10h]
0x18000d8ff  dec     r9
0x18000d902  inc     r8d
0x18000d905  lea     rcx, aParstscanforke; "PARSTscanForKeyword"
0x18000d90c  call    WriteDbgTraceErrorGpd
0x18000d911  mov     eax, [r14]
0x18000d914  imul    rcx, rax, 38h ; '8'
0x18000d918  mov     dword ptr [rcx+rbp+34h], 0
0x18000d920  mov     ecx, [rbx+1D4h]
0x18000d926  mov     rax, [rbx+1C8h]
0x18000d92d  dec     ecx
0x18000d92f  shl     rcx, 5
0x18000d933  dec     dword ptr [rcx+rax+8]
0x18000d937  mov     rcx, rbx
0x18000d93a  call    BeatComment
0x18000d93f  jmp     loc_18000D5E1
0x18000d944  mov     dword ptr [r11+rbp], 0FF02h
0x18000d94c  mov     eax, 3
0x18000d951  or      dword ptr [r11+rbp+34h], 80h
0x18000d95a  jmp     loc_18000D836
0x18000d95f  mov     eax, 1
0x18000d964  jmp     loc_18000D836
0x18000d969  mov     [rdi+8], r10
0x18000d96d  mov     rdx, rbx
0x18000d970  mov     dword ptr [rdi+10h], 1
0x18000d977  mov     ecx, esi
0x18000d979  mov     qword ptr [rdi+18h], 0
0x18000d981  mov     dword ptr [rdi+20h], 0
0x18000d988  or      dword ptr [rdi+34h], 1
0x18000d98c  call    DWidentifyKeyword
0x18000d991  mov     [rdi], eax
0x18000d993  lea     eax, [rsi+1]
0x18000d996  mov     ecx, [rbx+1D4h]
0x18000d99c  dec     ecx
0x18000d99e  mov     [r14], eax
0x18000d9a1  mov     rax, [rbx+1C8h]
0x18000d9a8  shl     rcx, 5
0x18000d9ac  inc     dword ptr [rcx+rax+8]
0x18000d9b0  mov     eax, 2
0x18000d9b5  jmp     loc_18000D836
0x18000d9ba  cmp     dword ptr [rdx+rax+14h], 0Ah
0x18000d9bf  jnz     loc_18000D58E
0x18000d9c5  mov     [r14], ecx
0x18000d9c8  mov     eax, 5
0x18000d9cd  add     rsp, 20h
0x18000d9d1  pop     r14
0x18000d9d3  pop     rbp
0x18000d9d4  pop     rbx
0x18000d9d5  retn
0x18000d9d7  mov     rdx, rbx
0x18000d9da  mov     rcx, rdi
0x18000d9dd  call    vIdentifySource
0x18000d9e2  lea     rdx, aUnexpectedEofE; "Unexpected EOF encountered parsing Keyw"...
0x18000d9e9  lea     rcx, aParstscanforke; "PARSTscanForKeyword"
0x18000d9f0  call    WriteDbgTraceErrorGpd
0x18000d9f5  mov     ecx, [rbx+1D4h]
0x18000d9fb  mov     rax, [rbx+1C8h]
0x18000da02  dec     ecx
0x18000da04  shl     rcx, 5
0x18000da08  inc     dword ptr [rcx+rax+8]
0x18000da0c  jmp     loc_18000D5E1
0x18000da11  mov     rcx, rbx
0x18000da14  call    BisColonNext
0x18000da19  test    eax, eax
0x18000da1b  jnz     loc_18000D5E1
0x18000da21  mov     eax, [r14]
0x18000da24  mov     rdx, rbx
0x18000da27  imul    rcx, rax, 38h ; '8'
0x18000da2b  add     rcx, rbp
0x18000da2e  call    vIdentifySource
0x18000da33  lea     rdx, aSyntaxErrorCol; "syntax error:  Colon expected but missi"...
  ... truncated ...
```
