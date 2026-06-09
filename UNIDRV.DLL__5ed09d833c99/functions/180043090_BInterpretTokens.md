# BInterpretTokens

- ea: `0x180043090`
- end: `0x1800433d1`
- name: `BInterpretTokens`
- size: `833`
- prototype: `_BOOL8 __fastcall(__int64, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800721d0`

## callees

- `0x180007150`
- `0x180008f8c`
- `0x18000a0b0`
- `0x18000a2d0`
- `0x18000af00`
- `0x1800382a4`
- `0x180043090`
- `0x1800433e0`
- `0x180045898`
- `0x180045aa4`
- `0x180072d78`
- `0x180076630`

## string_xrefs

- `0x1800432a4`: `BInterpretTokens`
- `0x180043344`: `BInterpretTokens`
- `0x180043384`: `BInterpretTokens`

## pseudocode

```c
_BOOL8 __fastcall BInterpretTokens(__int64 a1, unsigned int a2, _DWORD *a3)
{
  unsigned __int16 i; // di
  __int64 v7; // rdx
  __int64 v8; // rax
  const char *v9; // rcx
  size_t v10; // r8
  __int64 v11; // r8
  int v12; // eax
  __int64 v13; // r8
  unsigned __int16 v14; // si
  unsigned int *v15; // rdi
  unsigned int v16; // ecx
  int v17; // edx
  __int64 v19; // r8
  __int64 v20; // rdx
  int v21; // ecx
  int v22; // ecx
  bool v23; // zf
  unsigned int *v24; // rcx
  int v25; // eax
  __int64 v26; // r8
  int v27; // eax
  const char *v28; // [rsp+50h] [rbp-10h] BYREF
  __int64 v29; // [rsp+58h] [rbp-8h]
  int v30; // [rsp+98h] [rbp+38h] BYREF
  __int64 v31; // [rsp+A0h] [rbp+40h] BYREF

  if ( a2 )
  {
    v29 = 8;
    v28 = "InputBin";
    for ( i = 0; ; ++i )
    {
      v7 = 56LL * i;
      if ( *(_DWORD *)(v7 + a1) == 65283 )
        break;
      if ( *(_DWORD *)(v7 + a1) < 0xFF00u )
      {
        v8 = 4LL * *(unsigned int *)(v7 + a1);
        if ( !LODWORD((&mMainKeywordTable)[v8 + 2]) && *((_DWORD *)&mMainKeywordTable + 2 * v8 + 5) == 1 )
        {
          v9 = *(const char **)(v7 + a1 + 24);
          if ( v9 )
          {
            v10 = *(unsigned int *)(v7 + a1 + 32);
            if ( (_DWORD)v10 == 8 && !strncmp_0(v9, "InputBin", v10) )
            {
              v12 = DWregisterSymbol((__int64)&v28, 1, v11, -1, (__int64)a3);
              if ( v12 != -1 )
              {
                LODWORD(v29) = 10;
                v28 = "FORMSOURCE";
                DWregisterSymbol((__int64)&v28, 2, v13, v12, (__int64)a3);
              }
              break;
            }
          }
        }
      }
    }
  }
  else
  {
    v31 = 0;
    v30 = 0;
    BwriteToHeap((_DWORD *)&v31 + 1, &qword_18007F1D0, 2u, 4u, (__int64)a3);
    LODWORD(v31) = 0;
    BexchangeArbDataInFOATNode(0, 0, 0x68u, 8u, 0, &v31, &v30, 0, (__int64)a3);
  }
  v14 = 0;
  while ( (int)a3[555] < 2 )
  {
    v15 = (unsigned int *)(a1 + 56LL * v14);
    v16 = *v15;
    if ( *v15 == a3[558] )
    {
      v17 = 1;
LABEL_40:
      VIgnoreBlock((_DWORD *)(a1 + 56LL * v14), v17, (__int64)a3);
      goto LABEL_41;
    }
    switch ( v16 )
    {
      case 0xFF00u:
        goto LABEL_41;
      case 0xFF01u:
        if ( !(unsigned int)BidentifyAttributeKeyword(a1 + 56LL * v14, (__int64)a3) )
        {
          if ( !a2 )
            goto LABEL_41;
          vIdentifySource((_DWORD *)(a1 + 56LL * v14), (__int64)a3, v19);
          WriteDbgTraceErrorGpd(
            (__int64)"BInterpretTokens",
            "Warning, unrecognized keyword: %0.*s",
            v15[4],
            *((const char **)v15 + 1));
          v17 = 0;
          goto LABEL_40;
        }
        v16 = *v15;
        break;
      case 0xFF02u:
        goto LABEL_41;
      case 0xFF03u:
        return a3[153] == 0;
    }
    v20 = 4LL * v16;
    v21 = (int)(&mMainKeywordTable)[v20 + 2];
    if ( v21 )
    {
      v22 = v21 - 1;
      if ( v22 )
      {
        v23 = v22 == 1;
        v24 = (unsigned int *)(a1 + 56LL * v14);
        if ( !v23 )
        {
          vIdentifySource(v24, (__int64)a3, (__int64)&mMainKeywordTable);
          WriteDbgTraceErrorGpd(
            (__int64)"BInterpretTokens",
            "Internal Error: unrecognized keyword type! %0.*s.",
            v15[4],
            *((const char **)v15 + 1));
          a3[555] = 3;
          a3[556] = 4;
          goto LABEL_41;
        }
        v25 = BprocessSpecialKeyword(v24, a2, a3);
      }
      else
      {
        if ( a2 )
          goto LABEL_41;
        v25 = BprocessAttribute((unsigned int *)(a1 + 56LL * v14), (__int64)a3);
      }
      goto LABEL_29;
    }
    if ( *((_DWORD *)&mMainKeywordTable + 2 * v20 + 5) != 14 )
    {
      v25 = BpushState((unsigned int *)(a1 + 56LL * v14), a2, (__int64)a3);
LABEL_29:
      if ( !v25 )
        vIdentifySource((_DWORD *)(a1 + 56LL * v14), (__int64)a3, v26);
      goto LABEL_41;
    }
    v27 = a3[153];
    if ( v27 )
    {
      a3[153] = v27 - 1;
    }
    else
    {
      a3[556] = 1;
      a3[555] = 3;
      vIdentifySource((_DWORD *)(a1 + 56LL * v14), (__int64)a3, (__int64)&mMainKeywordTable);
      WriteDbgTraceErrorGpd((__int64)"BInterpretTokens", "Unmatched closing brace!");
    }
LABEL_41:
    ++v14;
  }
  return 0;
}

```

## disassembly

```asm
0x180043090  mov     [rsp-28h+arg_0], rbx
0x180043095  mov     [rsp-28h+arg_18], rsi
0x18004309a  push    rbp
0x18004309b  push    rdi
0x18004309c  push    r13
0x18004309e  push    r14
0x1800430a0  push    r15
0x1800430a2  mov     rbp, rsp
0x1800430a5  sub     rsp, 60h
0x1800430a9  mov     rbx, r8
0x1800430ac  lea     r8, mMainKeywordTable
0x1800430b3  mov     r14d, edx
0x1800430b6  mov     r15, rcx
0x1800430b9  mov     r13d, 1
0x1800430bf  test    edx, edx
0x1800430c1  jz      loc_180043189
0x1800430c7  lea     rsi, aInputbin; "InputBin"
0x1800430ce  mov     [rbp+var_8], 8
0x1800430d6  mov     [rbp+var_10], rsi
0x1800430da  xor     edi, edi
0x1800430dc  movzx   eax, di
0x1800430df  imul    rdx, rax, 38h ; '8'
0x1800430e3  cmp     dword ptr [rdx+r15], 0FF03h
0x1800430eb  jz      loc_1800431FE
0x1800430f1  cmp     dword ptr [rdx+r15], 0FF00h
0x1800430f9  jnb     short loc_18004313A
0x1800430fb  mov     eax, [rdx+r15]
0x1800430ff  shl     rax, 5
0x180043103  cmp     dword ptr [rax+r8+10h], 0
0x180043109  jnz     short loc_18004313A
0x18004310b  cmp     [rax+r8+14h], r13d
0x180043110  jnz     short loc_18004313A
0x180043112  mov     rcx, [rdx+r15+18h]; Str1
0x180043117  test    rcx, rcx
0x18004311a  jz      short loc_18004313A
0x18004311c  mov     r8d, [rdx+r15+20h]; MaxCount
0x180043121  cmp     r8d, 8
0x180043125  jnz     short loc_180043133
0x180043127  mov     rdx, rsi; Str2
0x18004312a  call    strncmp_0
0x18004312f  test    eax, eax
0x180043131  jz      short loc_180043140
0x180043133  lea     r8, mMainKeywordTable
0x18004313a  add     di, r13w
0x18004313e  jmp     short loc_1800430DC
0x180043140  or      edi, 0FFFFFFFFh
0x180043143  mov     [rsp+60h+var_40], rbx
0x180043148  mov     r9d, edi
0x18004314b  lea     rcx, [rbp+var_10]
0x18004314f  mov     edx, r13d
0x180043152  call    DWregisterSymbol
0x180043157  cmp     eax, edi
0x180043159  jz      loc_1800431F7
0x18004315f  lea     rcx, aFormsource; "FORMSOURCE"
0x180043166  mov     dword ptr [rbp+var_8], 0Ah
0x18004316d  mov     [rbp+var_10], rcx
0x180043171  mov     r9d, eax
0x180043174  lea     rcx, [rbp+var_10]
0x180043178  mov     [rsp+60h+var_40], rbx
0x18004317d  mov     edx, 2
0x180043182  call    DWregisterSymbol
0x180043187  jmp     short loc_1800431F7
0x180043189  mov     r9d, 4
0x18004318f  mov     [rbp+arg_10], 0
0x180043197  lea     rdx, qword_18007F1D0
0x18004319e  mov     [rbp+arg_8], 0
0x1800431a5  lea     rcx, [rbp+arg_10+4]
0x1800431a9  mov     [rsp+60h+var_40], rbx
0x1800431ae  lea     r8d, [r9-2]
0x1800431b2  call    BwriteToHeap
0x1800431b7  mov     [rsp+60h+var_20], rbx
0x1800431bc  lea     rax, [rbp+arg_8]
0x1800431c0  xor     edx, edx
0x1800431c2  mov     [rsp+60h+var_28], 0
0x1800431ca  mov     [rsp+60h+var_30], rax
0x1800431cf  xor     ecx, ecx
0x1800431d1  lea     rax, [rbp+arg_10]
0x1800431d5  mov     dword ptr [rbp+arg_10], 0
0x1800431dc  mov     [rsp+60h+var_38], rax
0x1800431e1  lea     r9d, [rdx+8]
0x1800431e5  mov     [rsp+60h+var_40], 0
0x1800431ee  lea     r8d, [rdx+68h]
0x1800431f2  call    BexchangeArbDataInFOATNode
0x1800431f7  lea     r8, mMainKeywordTable
0x1800431fe  xor     esi, esi
0x180043200  jmp     loc_1800433A8
0x180043205  movzx   eax, si
0x180043208  imul    rdi, rax, 38h ; '8'
0x18004320c  add     rdi, r15
0x18004320f  mov     ecx, [rdi]
0x180043211  cmp     ecx, [rbx+8B8h]
0x180043217  jnz     short loc_180043221
0x180043219  mov     edx, r13d
0x18004321c  jmp     loc_180043392
0x180043221  mov     eax, ecx
0x180043223  sub     eax, 0FF00h
0x180043228  jz      loc_1800433A4
0x18004322e  sub     eax, r13d
0x180043231  jz      short loc_180043251
0x180043233  sub     eax, r13d
0x180043236  jz      loc_1800433A4
0x18004323c  cmp     eax, r13d
0x18004323f  jnz     short loc_18004326D
0x180043241  xor     eax, eax
0x180043243  cmp     [rbx+264h], eax
0x180043249  setz    al
0x18004324c  jmp     loc_1800433B7
0x180043251  mov     rdx, rbx
0x180043254  mov     rcx, rdi
0x180043257  call    BidentifyAttributeKeyword
0x18004325c  test    eax, eax
0x18004325e  jz      loc_180043365
0x180043264  mov     ecx, [rdi]
0x180043266  lea     r8, mMainKeywordTable
0x18004326d  mov     edx, ecx
0x18004326f  shl     rdx, 5
0x180043273  mov     ecx, [rdx+r8+10h]
0x180043278  test    ecx, ecx
0x18004327a  jz      loc_180043302
0x180043280  sub     ecx, r13d
0x180043283  jz      short loc_1800432EC
0x180043285  cmp     ecx, r13d
0x180043288  mov     rcx, rdi
0x18004328b  jz      short loc_1800432C9
0x18004328d  mov     rdx, rbx
0x180043290  call    vIdentifySource
0x180043295  mov     r9, [rdi+8]
0x180043299  lea     rdx, aInternalErrorU_0; "Internal Error: unrecognized keyword ty"...
0x1800432a0  mov     r8d, [rdi+10h]
0x1800432a4  lea     rcx, aBinterprettoke; "BInterpretTokens"
0x1800432ab  call    WriteDbgTraceErrorGpd
0x1800432b0  mov     dword ptr [rbx+8ACh], 3
0x1800432ba  mov     dword ptr [rbx+8B0h], 4
0x1800432c4  jmp     loc_18004339D
0x1800432c9  mov     r8, rbx
0x1800432cc  mov     edx, r14d
0x1800432cf  call    BprocessSpecialKeyword
0x1800432d4  test    eax, eax
0x1800432d6  jnz     loc_18004339D
0x1800432dc  mov     rdx, rbx
0x1800432df  mov     rcx, rdi
0x1800432e2  call    vIdentifySource
0x1800432e7  jmp     loc_18004339D
0x1800432ec  test    r14d, r14d
0x1800432ef  jnz     loc_1800433A4
0x1800432f5  mov     rdx, rbx
0x1800432f8  mov     rcx, rdi
0x1800432fb  call    BprocessAttribute
0x180043300  jmp     short loc_1800432D4
0x180043302  cmp     dword ptr [rdx+r8+14h], 0Eh
0x180043308  jnz     short loc_180043352
0x18004330a  mov     eax, [rbx+264h]
0x180043310  test    eax, eax
0x180043312  jz      short loc_180043321
0x180043314  dec     eax
0x180043316  mov     [rbx+264h], eax
0x18004331c  jmp     loc_1800433A4
0x180043321  mov     rdx, rbx
0x180043324  mov     [rbx+8B0h], r13d
0x18004332b  mov     rcx, rdi
0x18004332e  mov     dword ptr [rbx+8ACh], 3
0x180043338  call    vIdentifySource
0x18004333d  lea     rdx, aUnmatchedClosi; "Unmatched closing brace!"
0x180043344  lea     rcx, aBinterprettoke; "BInterpretTokens"
0x18004334b  call    WriteDbgTraceErrorGpd
0x180043350  jmp     short loc_18004339D
0x180043352  mov     r8, rbx
0x180043355  mov     edx, r14d
0x180043358  mov     rcx, rdi
0x18004335b  call    BpushState
0x180043360  jmp     loc_1800432D4
0x180043365  test    r14d, r14d
0x180043368  jz      short loc_18004339D
0x18004336a  mov     rdx, rbx
0x18004336d  mov     rcx, rdi
0x180043370  call    vIdentifySource
0x180043375  mov     r9, [rdi+8]
0x180043379  lea     rdx, aWarningUnrecog; "Warning, unrecognized keyword: %0.*s"
0x180043380  mov     r8d, [rdi+10h]
0x180043384  lea     rcx, aBinterprettoke; "BInterpretTokens"
0x18004338b  call    WriteDbgTraceErrorGpd
0x180043390  xor     edx, edx
0x180043392  mov     r8, rbx
0x180043395  mov     rcx, rdi
0x180043398  call    VIgnoreBlock
0x18004339d  lea     r8, mMainKeywordTable
0x1800433a4  add     si, r13w
0x1800433a8  cmp     dword ptr [rbx+8ACh], 2
0x1800433af  jl      loc_180043205
0x1800433b5  xor     eax, eax
0x1800433b7  lea     r11, [rsp+60h+var_s0]
0x1800433bc  mov     rbx, [r11+30h]
0x1800433c0  mov     rsi, [r11+48h]
0x1800433c4  mov     rsp, r11
0x1800433c7  pop     r15
0x1800433c9  pop     r14
0x1800433cb  pop     r13
0x1800433cd  pop     rdi
0x1800433ce  pop     rbp
0x1800433cf  retn
```
