# BExpandMemConfig

- ea: `0x180073234`
- end: `0x1800735ba`
- name: `BExpandMemConfig`
- size: `902`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180035ca0`

## callees

- `0x180007150`
- `0x18000898c`
- `0x18000aa88`
- `0x180033f3c`
- `0x1800365d8`
- `0x180045aa4`
- `0x180073234`
- `0x1800735c0`

## string_xrefs

- `0x18007356b`: `Syntax error in value of *MemConfig shortcut: %0.*s.`
- `0x18007354e`: `BExpandMemConfig`
- `0x180073576`: `BExpandMemConfig`

## pseudocode

```c
__int64 __fastcall BExpandMemConfig(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  int v4; // r13d
  int *v6; // rdi
  const char *v7; // rax
  int v9; // r12d
  __int64 v10; // r8
  int v11; // eax
  __int64 v12; // rsi
  __int64 v13; // r8
  unsigned int *v14; // rsi
  unsigned int *v15; // rsi
  __int64 v16; // rax
  __int64 v17; // rsi
  unsigned int *v18; // rcx
  unsigned int *v19; // rsi
  __int64 result; // rax
  __int128 v21; // [rsp+20h] [rbp-50h] BYREF
  __int128 v22; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v24[2]; // [rsp+50h] [rbp-20h] BYREF
  __int128 v25; // [rsp+60h] [rbp-10h] BYREF
  int v26; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v27; // [rsp+C0h] [rbp+50h] BYREF

  v4 = a4[630];
  v23[0] = "\"";
  v22 = 0;
  v21 = 0;
  v27 = 0;
  v6 = (int *)(a1 + 56LL * a3);
  v26 = 0;
  v7 = "MB";
  v24[1] = 2;
  v23[1] = 1;
  v9 = *v6;
  if ( *v6 != v4 )
    v7 = "KB";
  v24[0] = v7;
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v27, a4) )
    goto LABEL_28;
  v25 = *(_OWORD *)(v6 + 6);
  if ( !(unsigned int)BdelimitToken((__int64)&v25, (__int64)"(", (__int64)&v22, &v26)
    || v26
    || !(unsigned int)BdelimitToken((__int64)&v25, (__int64)",", (__int64)&v22, &v26)
    || v26
    || !(unsigned int)BeatSurroundingWhiteSpaces((__int64)&v22) )
  {
    vIdentifySource(v6, (__int64)a4, v10);
    WriteDbgTraceErrorGpd(
      (__int64)"BExpandMemConfig",
      "Syntax error in value of *MemConfig shortcut: %0.*s.",
      v6[8],
      *((const char **)v6 + 3));
    return 0;
  }
  v11 = a4[631];
  v12 = a2 + 56LL * v27;
  DWORD2(v21) = 0;
  *(_DWORD *)v12 = v11;
  if ( !(unsigned int)BInitKeywordField((unsigned int *)v12, (__int64)a4)
    || !(unsigned int)BCatToTmpHeap((__int64)&v21, (__int64)&v22, (__int64)a4)
    || !(unsigned int)BCatToTmpHeap((__int64)&v21, (__int64)v24, (__int64)a4) )
  {
    goto LABEL_26;
  }
  *(_OWORD *)(v12 + 24) = v21;
  *(_DWORD *)(v12 + 44) = v6[11];
  *(_DWORD *)(v12 + 48) = v6[12];
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v27, a4) )
    goto LABEL_28;
  v14 = (unsigned int *)(a2 + 56LL * v27);
  *v14 = a4[632];
  v14[8] = 0;
  if ( !(unsigned int)BInitKeywordField(v14, (__int64)a4) )
    return 0;
  v14[11] = v6[11];
  v14[12] = v6[12];
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v27, a4) )
  {
LABEL_28:
    a4[554] = 21;
    a4[555] = 2;
    a4[556] = 2;
    return 0;
  }
  v15 = (unsigned int *)(a2 + 56LL * v27);
  *v15 = a4[638];
  v15[8] = 0;
  if ( !(unsigned int)BInitKeywordField(v15, (__int64)a4)
    || !(unsigned int)BCatToTmpHeap((__int64)(v15 + 6), (__int64)v23, (__int64)a4)
    || !(unsigned int)BCatToTmpHeap((__int64)(v15 + 6), (__int64)&v21, (__int64)a4)
    || !(unsigned int)BCatToTmpHeap((__int64)(v15 + 6), (__int64)v23, (__int64)a4) )
  {
LABEL_26:
    vIdentifySource(v6, (__int64)a4, v13);
    WriteDbgTraceErrorGpd((__int64)"BExpandMemConfig", "Concatenation to synthesize Memory option name failed.");
    return 0;
  }
  v15[11] = v6[11];
  v15[12] = v6[12];
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v27, a4) )
    goto LABEL_28;
  v16 = 634;
  v17 = a2 + 56LL * v27;
  if ( v9 != v4 )
    v16 = 635;
  v18 = (unsigned int *)(a2 + 56LL * v27);
  *(_DWORD *)v17 = a4[v16];
  *(_OWORD *)(v17 + 24) = *(_OWORD *)(v6 + 6);
  if ( !(unsigned int)BInitKeywordField(v18, (__int64)a4) )
    return 0;
  *(_DWORD *)(v17 + 44) = v6[11];
  *(_DWORD *)(v17 + 48) = v6[12];
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v27, a4) )
    goto LABEL_28;
  v19 = (unsigned int *)(a2 + 56LL * v27);
  *v19 = a4[633];
  v19[8] = 0;
  if ( (unsigned int)BInitKeywordField(v19, (__int64)a4) )
  {
    result = 1;
    v19[11] = v6[11];
    v19[12] = v6[12];
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x180073234  mov     [rsp-38h+arg_8], rbx
0x180073239  push    rbp
0x18007323a  push    rsi
0x18007323b  push    rdi
0x18007323c  push    r12
0x18007323e  push    r13
0x180073240  push    r14
0x180073242  push    r15
0x180073244  mov     rbp, rsp
0x180073247  sub     rsp, 70h
0x18007324b  mov     r13d, [r9+9D8h]
0x180073252  lea     rax, asc_18007E920; "\""
0x180073259  mov     [rbp+var_30], rax
0x18007325d  xor     r14d, r14d
0x180073260  mov     eax, r8d
0x180073263  mov     r15, rdx
0x180073266  imul    rdi, rax, 38h ; '8'
0x18007326a  xorps   xmm0, xmm0
0x18007326d  xorps   xmm1, xmm1
0x180073270  movups  [rbp+var_40], xmm0
0x180073274  movups  [rbp+var_50], xmm1
0x180073278  lea     rdx, aKb; "KB"
0x18007327f  mov     [rbp+arg_10], r14d
0x180073283  add     rdi, rcx
0x180073286  mov     [rbp+arg_0], r14d
0x18007328a  lea     rax, aMb; "MB"
0x180073291  mov     [rbp+var_18], 2
0x180073299  mov     r8, r9
0x18007329c  mov     [rbp+var_28], 1
0x1800732a4  lea     ecx, [r14+15h]
0x1800732a8  mov     rbx, r9
0x1800732ab  mov     r12d, [rdi]
0x1800732ae  cmp     r12d, r13d
0x1800732b1  cmovnz  rax, rdx
0x1800732b5  lea     rdx, [rbp+arg_10]
0x1800732b9  mov     [rbp+var_20], rax
0x1800732bd  call    BallocElementFromMasterTable
0x1800732c2  test    eax, eax
0x1800732c4  jz      loc_180073584
0x1800732ca  movups  xmm0, xmmword ptr [rdi+18h]
0x1800732ce  lea     r9, [rbp+arg_0]
0x1800732d2  lea     r8, [rbp+var_40]
0x1800732d6  lea     rdx, asc_18007E82C; "("
0x1800732dd  lea     rcx, [rbp+var_10]
0x1800732e1  movdqu  [rbp+var_10], xmm0
0x1800732e6  call    BdelimitToken
0x1800732eb  test    eax, eax
0x1800732ed  jz      loc_18007355C
0x1800732f3  cmp     [rbp+arg_0], r14d
0x1800732f7  jnz     loc_18007355C
0x1800732fd  lea     r9, [rbp+arg_0]
0x180073301  lea     r8, [rbp+var_40]
0x180073305  lea     rdx, asc_180081AE4; ","
0x18007330c  lea     rcx, [rbp+var_10]
0x180073310  call    BdelimitToken
0x180073315  test    eax, eax
0x180073317  jz      loc_18007355C
0x18007331d  cmp     [rbp+arg_0], r14d
0x180073321  jnz     loc_18007355C
0x180073327  lea     rcx, [rbp+var_40]
0x18007332b  call    BeatSurroundingWhiteSpaces
0x180073330  test    eax, eax
0x180073332  jz      loc_18007355C
0x180073338  mov     eax, [rbp+arg_10]
0x18007333b  mov     rdx, rbx
0x18007333e  imul    rsi, rax, 38h ; '8'
0x180073342  mov     eax, [rbx+9DCh]
0x180073348  add     rsi, r15
0x18007334b  mov     dword ptr [rbp+var_50+8], r14d
0x18007334f  mov     rcx, rsi
0x180073352  mov     [rsi], eax
0x180073354  call    BInitKeywordField
0x180073359  test    eax, eax
0x18007335b  jz      loc_18007353C
0x180073361  mov     r8, rbx
0x180073364  lea     rdx, [rbp+var_40]
0x180073368  lea     rcx, [rbp+var_50]
0x18007336c  call    BCatToTmpHeap
0x180073371  test    eax, eax
0x180073373  jz      loc_18007353C
0x180073379  mov     r8, rbx
0x18007337c  lea     rdx, [rbp+var_20]
0x180073380  lea     rcx, [rbp+var_50]
0x180073384  call    BCatToTmpHeap
0x180073389  test    eax, eax
0x18007338b  jz      loc_18007353C
0x180073391  movups  xmm0, [rbp+var_50]
0x180073395  mov     r8, rbx
0x180073398  lea     rdx, [rbp+arg_10]
0x18007339c  lea     ecx, [r14+15h]
0x1800733a0  movdqu  xmmword ptr [rsi+18h], xmm0
0x1800733a5  mov     eax, [rdi+2Ch]
0x1800733a8  mov     [rsi+2Ch], eax
0x1800733ab  mov     eax, [rdi+30h]
0x1800733ae  mov     [rsi+30h], eax
0x1800733b1  call    BallocElementFromMasterTable
0x1800733b6  test    eax, eax
0x1800733b8  jz      loc_180073584
0x1800733be  mov     eax, [rbp+arg_10]
0x1800733c1  mov     rdx, rbx
0x1800733c4  imul    rsi, rax, 38h ; '8'
0x1800733c8  mov     eax, [rbx+9E0h]
0x1800733ce  add     rsi, r15
0x1800733d1  mov     rcx, rsi
0x1800733d4  mov     [rsi], eax
0x1800733d6  mov     [rsi+20h], r14d
0x1800733da  call    BInitKeywordField
0x1800733df  test    eax, eax
0x1800733e1  jz      loc_18007359F
0x1800733e7  mov     eax, [rdi+2Ch]
0x1800733ea  lea     rdx, [rbp+arg_10]
0x1800733ee  mov     [rsi+2Ch], eax
0x1800733f1  lea     ecx, [r14+15h]
0x1800733f5  mov     eax, [rdi+30h]
0x1800733f8  mov     r8, rbx
0x1800733fb  mov     [rsi+30h], eax
0x1800733fe  call    BallocElementFromMasterTable
0x180073403  test    eax, eax
0x180073405  jz      loc_180073584
0x18007340b  mov     eax, [rbp+arg_10]
0x18007340e  mov     rdx, rbx
0x180073411  imul    rsi, rax, 38h ; '8'
0x180073415  mov     eax, [rbx+9F8h]
0x18007341b  add     rsi, r15
0x18007341e  mov     rcx, rsi
0x180073421  mov     [rsi], eax
0x180073423  mov     [rsi+20h], r14d
0x180073427  call    BInitKeywordField
0x18007342c  test    eax, eax
0x18007342e  jz      loc_18007353C
0x180073434  lea     r14, [rsi+18h]
0x180073438  mov     r8, rbx
0x18007343b  mov     rcx, r14
0x18007343e  lea     rdx, [rbp+var_30]
0x180073442  call    BCatToTmpHeap
0x180073447  test    eax, eax
0x180073449  jz      loc_18007353C
0x18007344f  mov     r8, rbx
0x180073452  lea     rdx, [rbp+var_50]
0x180073456  mov     rcx, r14
0x180073459  call    BCatToTmpHeap
0x18007345e  test    eax, eax
0x180073460  jz      loc_18007353C
0x180073466  mov     r8, rbx
0x180073469  lea     rdx, [rbp+var_30]
0x18007346d  mov     rcx, r14
0x180073470  call    BCatToTmpHeap
0x180073475  test    eax, eax
0x180073477  jz      loc_18007353C
0x18007347d  mov     eax, [rdi+2Ch]
0x180073480  lea     rdx, [rbp+arg_10]
0x180073484  mov     [rsi+2Ch], eax
0x180073487  mov     r14d, 15h
0x18007348d  mov     eax, [rdi+30h]
0x180073490  mov     ecx, r14d
0x180073493  mov     r8, rbx
0x180073496  mov     [rsi+30h], eax
0x180073499  call    BallocElementFromMasterTable
0x18007349e  test    eax, eax
0x1800734a0  jz      loc_180073584
0x1800734a6  mov     eax, [rbp+arg_10]
0x1800734a9  mov     rdx, rbx
0x1800734ac  imul    rsi, rax, 38h ; '8'
0x1800734b0  mov     eax, 9E8h
0x1800734b5  add     rsi, r15
0x1800734b8  cmp     r12d, r13d
0x1800734bb  lea     ecx, [rax+4]
0x1800734be  cmovnz  eax, ecx
0x1800734c1  mov     rcx, rsi
0x1800734c4  mov     eax, [rax+rbx]
0x1800734c7  mov     [rsi], eax
0x1800734c9  movups  xmm0, xmmword ptr [rdi+18h]
0x1800734cd  movdqu  xmmword ptr [rsi+18h], xmm0
0x1800734d2  call    BInitKeywordField
0x1800734d7  test    eax, eax
0x1800734d9  jz      loc_18007359F
0x1800734df  mov     eax, [rdi+2Ch]
0x1800734e2  lea     rdx, [rbp+arg_10]
0x1800734e6  mov     [rsi+2Ch], eax
0x1800734e9  mov     r8, rbx
0x1800734ec  mov     eax, [rdi+30h]
0x1800734ef  mov     ecx, r14d
0x1800734f2  mov     [rsi+30h], eax
0x1800734f5  call    BallocElementFromMasterTable
0x1800734fa  test    eax, eax
0x1800734fc  jz      loc_180073584
0x180073502  mov     ecx, [rbx+9E4h]
0x180073508  mov     rdx, rbx
0x18007350b  mov     eax, [rbp+arg_10]
0x18007350e  imul    rsi, rax, 38h ; '8'
0x180073512  add     rsi, r15
0x180073515  mov     [rsi], ecx
0x180073517  mov     rcx, rsi
0x18007351a  mov     dword ptr [rsi+20h], 0
0x180073521  call    BInitKeywordField
0x180073526  test    eax, eax
0x180073528  jz      short loc_18007359F
0x18007352a  mov     ecx, [rdi+2Ch]
0x18007352d  lea     eax, [r14-14h]
0x180073531  mov     [rsi+2Ch], ecx
0x180073534  mov     ecx, [rdi+30h]
0x180073537  mov     [rsi+30h], ecx
0x18007353a  jmp     short loc_1800735A1
0x18007353c  mov     rdx, rbx
0x18007353f  mov     rcx, rdi
0x180073542  call    vIdentifySource
0x180073547  lea     rdx, aConcatenationT; "Concatenation to synthesize Memory opti"...
0x18007354e  lea     rcx, aBexpandmemconf; "BExpandMemConfig"
0x180073555  call    WriteDbgTraceErrorGpd
0x18007355a  jmp     short loc_18007359F
0x18007355c  mov     rdx, rbx
0x18007355f  mov     rcx, rdi
0x180073562  call    vIdentifySource
0x180073567  mov     r9, [rdi+18h]
0x18007356b  lea     rdx, aSyntaxErrorInV_0; "Syntax error in value of *MemConfig sho"...
0x180073572  mov     r8d, [rdi+20h]
0x180073576  lea     rcx, aBexpandmemconf; "BExpandMemConfig"
0x18007357d  call    WriteDbgTraceErrorGpd
0x180073582  jmp     short loc_18007359F
0x180073584  mov     eax, 2
0x180073589  mov     dword ptr [rbx+8A8h], 15h
0x180073593  mov     [rbx+8ACh], eax
0x180073599  mov     [rbx+8B0h], eax
0x18007359f  xor     eax, eax
0x1800735a1  mov     rbx, [rsp+70h+arg_8]
0x1800735a9  add     rsp, 70h
0x1800735ad  pop     r15
0x1800735af  pop     r14
0x1800735b1  pop     r13
0x1800735b3  pop     r12
0x1800735b5  pop     rdi
0x1800735b6  pop     rsi
0x1800735b7  pop     rbp
0x1800735b8  retn
```
