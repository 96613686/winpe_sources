# BExpandMemConfig

- ea: `0x1800711c0`
- end: `0x180071545`
- name: `BExpandMemConfig`
- size: `901`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800352c8`

## callees

- `0x180007220`
- `0x180008a10`
- `0x18000aa88`
- `0x1800335c8`
- `0x1800363ac`
- `0x18004485c`
- `0x1800711c0`
- `0x18007154c`

## string_xrefs

- `0x1800714f7`: `Syntax error in value of *MemConfig shortcut: %0.*s.`
- `0x1800714da`: `BExpandMemConfig`
- `0x180071502`: `BExpandMemConfig`

## pseudocode

```c
__int64 __fastcall BExpandMemConfig(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  int v4; // r13d
  int *v6; // rdi
  const char *v7; // rax
  int v9; // r12d
  int v10; // eax
  __int64 v11; // rsi
  _DWORD *v12; // rsi
  _DWORD *v13; // rsi
  __int64 v14; // rax
  __int64 v15; // rsi
  __int64 v16; // rcx
  _DWORD *v17; // rsi
  __int64 result; // rax
  __int128 v19; // [rsp+20h] [rbp-50h] BYREF
  __int128 v20; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v21[2]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-20h] BYREF
  __int128 v23; // [rsp+60h] [rbp-10h] BYREF
  int v24; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v25; // [rsp+C0h] [rbp+50h] BYREF

  v4 = a4[630];
  v21[0] = "\"";
  v20 = 0;
  v19 = 0;
  v25 = 0;
  v6 = (int *)(a1 + 56LL * a3);
  v24 = 0;
  v7 = "MB";
  v22[1] = 2;
  v21[1] = 1;
  v9 = *v6;
  if ( *v6 != v4 )
    v7 = "KB";
  v22[0] = v7;
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v25, a4) )
    goto LABEL_28;
  v23 = *(_OWORD *)(v6 + 6);
  if ( !(unsigned int)BdelimitToken(&v23, "(", &v20, &v24)
    || v24
    || !(unsigned int)BdelimitToken(&v23, ",", &v20, &v24)
    || v24
    || !(unsigned int)BeatSurroundingWhiteSpaces(&v20) )
  {
    vIdentifySource(v6, a4);
    WriteDbgTraceErrorGpd(
      "BExpandMemConfig",
      "Syntax error in value of *MemConfig shortcut: %0.*s.",
      v6[8],
      *((const char **)v6 + 3));
    return 0;
  }
  v10 = a4[631];
  v11 = a2 + 56LL * v25;
  DWORD2(v19) = 0;
  *(_DWORD *)v11 = v10;
  if ( !(unsigned int)BInitKeywordField(v11, a4)
    || !(unsigned int)BCatToTmpHeap(&v19, &v20, a4)
    || !(unsigned int)BCatToTmpHeap(&v19, v22, a4) )
  {
    goto LABEL_26;
  }
  *(_OWORD *)(v11 + 24) = v19;
  *(_DWORD *)(v11 + 44) = v6[11];
  *(_DWORD *)(v11 + 48) = v6[12];
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v25, a4) )
    goto LABEL_28;
  v12 = (_DWORD *)(a2 + 56LL * v25);
  *v12 = a4[632];
  v12[8] = 0;
  if ( !(unsigned int)BInitKeywordField(v12, a4) )
    return 0;
  v12[11] = v6[11];
  v12[12] = v6[12];
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v25, a4) )
  {
LABEL_28:
    a4[554] = 21;
    a4[555] = 2;
    a4[556] = 2;
    return 0;
  }
  v13 = (_DWORD *)(a2 + 56LL * v25);
  *v13 = a4[638];
  v13[8] = 0;
  if ( !(unsigned int)BInitKeywordField(v13, a4)
    || !(unsigned int)BCatToTmpHeap(v13 + 6, v21, a4)
    || !(unsigned int)BCatToTmpHeap(v13 + 6, &v19, a4)
    || !(unsigned int)BCatToTmpHeap(v13 + 6, v21, a4) )
  {
LABEL_26:
    vIdentifySource(v6, a4);
    WriteDbgTraceErrorGpd("BExpandMemConfig", "Concatenation to synthesize Memory option name failed.");
    return 0;
  }
  v13[11] = v6[11];
  v13[12] = v6[12];
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v25, a4) )
    goto LABEL_28;
  v14 = 634;
  v15 = a2 + 56LL * v25;
  if ( v9 != v4 )
    v14 = 635;
  v16 = a2 + 56LL * v25;
  *(_DWORD *)v15 = a4[v14];
  *(_OWORD *)(v15 + 24) = *(_OWORD *)(v6 + 6);
  if ( !(unsigned int)BInitKeywordField(v16, a4) )
    return 0;
  *(_DWORD *)(v15 + 44) = v6[11];
  *(_DWORD *)(v15 + 48) = v6[12];
  if ( !(unsigned int)BallocElementFromMasterTable(21, &v25, a4) )
    goto LABEL_28;
  v17 = (_DWORD *)(a2 + 56LL * v25);
  *v17 = a4[633];
  v17[8] = 0;
  if ( (unsigned int)BInitKeywordField(v17, a4) )
  {
    result = 1;
    v17[11] = v6[11];
    v17[12] = v6[12];
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x1800711c0  mov     [rsp-38h+arg_8], rbx
0x1800711c5  push    rbp
0x1800711c6  push    rsi
0x1800711c7  push    rdi
0x1800711c8  push    r12
0x1800711ca  push    r13
0x1800711cc  push    r14
0x1800711ce  push    r15
0x1800711d0  mov     rbp, rsp
0x1800711d3  sub     rsp, 70h
0x1800711d7  mov     r13d, [r9+9D8h]
0x1800711de  lea     rax, asc_18007C920; "\""
0x1800711e5  mov     [rbp+var_30], rax
0x1800711e9  xor     r14d, r14d
0x1800711ec  mov     eax, r8d
0x1800711ef  mov     r15, rdx
0x1800711f2  imul    rdi, rax, 38h ; '8'
0x1800711f6  xorps   xmm0, xmm0
0x1800711f9  xorps   xmm1, xmm1
0x1800711fc  movups  [rbp+var_40], xmm0
0x180071200  movups  [rbp+var_50], xmm1
0x180071204  lea     rdx, aKb; "KB"
0x18007120b  mov     [rbp+arg_10], r14d
0x18007120f  add     rdi, rcx
0x180071212  mov     [rbp+arg_0], r14d
0x180071216  lea     rax, aMb; "MB"
0x18007121d  mov     [rbp+var_18], 2
0x180071225  mov     r8, r9
0x180071228  mov     [rbp+var_28], 1
0x180071230  lea     ecx, [r14+15h]
0x180071234  mov     rbx, r9
0x180071237  mov     r12d, [rdi]
0x18007123a  cmp     r12d, r13d
0x18007123d  cmovnz  rax, rdx
0x180071241  lea     rdx, [rbp+arg_10]
0x180071245  mov     [rbp+var_20], rax
0x180071249  call    BallocElementFromMasterTable
0x18007124e  test    eax, eax
0x180071250  jz      loc_180071510
0x180071256  movups  xmm0, xmmword ptr [rdi+18h]
0x18007125a  lea     r9, [rbp+arg_0]
0x18007125e  lea     r8, [rbp+var_40]
0x180071262  lea     rdx, asc_18007C82C; "("
0x180071269  lea     rcx, [rbp+var_10]
0x18007126d  movdqu  [rbp+var_10], xmm0
0x180071272  call    BdelimitToken
0x180071277  test    eax, eax
0x180071279  jz      loc_1800714E8
0x18007127f  cmp     [rbp+arg_0], r14d
0x180071283  jnz     loc_1800714E8
0x180071289  lea     r9, [rbp+arg_0]
0x18007128d  lea     r8, [rbp+var_40]
0x180071291  lea     rdx, asc_18007FAE4; ","
0x180071298  lea     rcx, [rbp+var_10]
0x18007129c  call    BdelimitToken
0x1800712a1  test    eax, eax
0x1800712a3  jz      loc_1800714E8
0x1800712a9  cmp     [rbp+arg_0], r14d
0x1800712ad  jnz     loc_1800714E8
0x1800712b3  lea     rcx, [rbp+var_40]
0x1800712b7  call    BeatSurroundingWhiteSpaces
0x1800712bc  test    eax, eax
0x1800712be  jz      loc_1800714E8
0x1800712c4  mov     eax, [rbp+arg_10]
0x1800712c7  mov     rdx, rbx
0x1800712ca  imul    rsi, rax, 38h ; '8'
0x1800712ce  mov     eax, [rbx+9DCh]
0x1800712d4  add     rsi, r15
0x1800712d7  mov     dword ptr [rbp+var_50+8], r14d
0x1800712db  mov     rcx, rsi
0x1800712de  mov     [rsi], eax
0x1800712e0  call    BInitKeywordField
0x1800712e5  test    eax, eax
0x1800712e7  jz      loc_1800714C8
0x1800712ed  mov     r8, rbx
0x1800712f0  lea     rdx, [rbp+var_40]
0x1800712f4  lea     rcx, [rbp+var_50]
0x1800712f8  call    BCatToTmpHeap
0x1800712fd  test    eax, eax
0x1800712ff  jz      loc_1800714C8
0x180071305  mov     r8, rbx
0x180071308  lea     rdx, [rbp+var_20]
0x18007130c  lea     rcx, [rbp+var_50]
0x180071310  call    BCatToTmpHeap
0x180071315  test    eax, eax
0x180071317  jz      loc_1800714C8
0x18007131d  movups  xmm0, [rbp+var_50]
0x180071321  mov     r8, rbx
0x180071324  lea     rdx, [rbp+arg_10]
0x180071328  lea     ecx, [r14+15h]
0x18007132c  movdqu  xmmword ptr [rsi+18h], xmm0
0x180071331  mov     eax, [rdi+2Ch]
0x180071334  mov     [rsi+2Ch], eax
0x180071337  mov     eax, [rdi+30h]
0x18007133a  mov     [rsi+30h], eax
0x18007133d  call    BallocElementFromMasterTable
0x180071342  test    eax, eax
0x180071344  jz      loc_180071510
0x18007134a  mov     eax, [rbp+arg_10]
0x18007134d  mov     rdx, rbx
0x180071350  imul    rsi, rax, 38h ; '8'
0x180071354  mov     eax, [rbx+9E0h]
0x18007135a  add     rsi, r15
0x18007135d  mov     rcx, rsi
0x180071360  mov     [rsi], eax
0x180071362  mov     [rsi+20h], r14d
0x180071366  call    BInitKeywordField
0x18007136b  test    eax, eax
0x18007136d  jz      loc_18007152B
0x180071373  mov     eax, [rdi+2Ch]
0x180071376  lea     rdx, [rbp+arg_10]
0x18007137a  mov     [rsi+2Ch], eax
0x18007137d  lea     ecx, [r14+15h]
0x180071381  mov     eax, [rdi+30h]
0x180071384  mov     r8, rbx
0x180071387  mov     [rsi+30h], eax
0x18007138a  call    BallocElementFromMasterTable
0x18007138f  test    eax, eax
0x180071391  jz      loc_180071510
0x180071397  mov     eax, [rbp+arg_10]
0x18007139a  mov     rdx, rbx
0x18007139d  imul    rsi, rax, 38h ; '8'
0x1800713a1  mov     eax, [rbx+9F8h]
0x1800713a7  add     rsi, r15
0x1800713aa  mov     rcx, rsi
0x1800713ad  mov     [rsi], eax
0x1800713af  mov     [rsi+20h], r14d
0x1800713b3  call    BInitKeywordField
0x1800713b8  test    eax, eax
0x1800713ba  jz      loc_1800714C8
0x1800713c0  lea     r14, [rsi+18h]
0x1800713c4  mov     r8, rbx
0x1800713c7  mov     rcx, r14
0x1800713ca  lea     rdx, [rbp+var_30]
0x1800713ce  call    BCatToTmpHeap
0x1800713d3  test    eax, eax
0x1800713d5  jz      loc_1800714C8
0x1800713db  mov     r8, rbx
0x1800713de  lea     rdx, [rbp+var_50]
0x1800713e2  mov     rcx, r14
0x1800713e5  call    BCatToTmpHeap
0x1800713ea  test    eax, eax
0x1800713ec  jz      loc_1800714C8
0x1800713f2  mov     r8, rbx
0x1800713f5  lea     rdx, [rbp+var_30]
0x1800713f9  mov     rcx, r14
0x1800713fc  call    BCatToTmpHeap
0x180071401  test    eax, eax
0x180071403  jz      loc_1800714C8
0x180071409  mov     eax, [rdi+2Ch]
0x18007140c  lea     rdx, [rbp+arg_10]
0x180071410  mov     [rsi+2Ch], eax
0x180071413  mov     r14d, 15h
0x180071419  mov     eax, [rdi+30h]
0x18007141c  mov     ecx, r14d
0x18007141f  mov     r8, rbx
0x180071422  mov     [rsi+30h], eax
0x180071425  call    BallocElementFromMasterTable
0x18007142a  test    eax, eax
0x18007142c  jz      loc_180071510
0x180071432  mov     eax, [rbp+arg_10]
0x180071435  mov     rdx, rbx
0x180071438  imul    rsi, rax, 38h ; '8'
0x18007143c  mov     eax, 9E8h
0x180071441  add     rsi, r15
0x180071444  cmp     r12d, r13d
0x180071447  lea     ecx, [rax+4]
0x18007144a  cmovnz  eax, ecx
0x18007144d  mov     rcx, rsi
0x180071450  mov     eax, [rax+rbx]
0x180071453  mov     [rsi], eax
0x180071455  movups  xmm0, xmmword ptr [rdi+18h]
0x180071459  movdqu  xmmword ptr [rsi+18h], xmm0
0x18007145e  call    BInitKeywordField
0x180071463  test    eax, eax
0x180071465  jz      loc_18007152B
0x18007146b  mov     eax, [rdi+2Ch]
0x18007146e  lea     rdx, [rbp+arg_10]
0x180071472  mov     [rsi+2Ch], eax
0x180071475  mov     r8, rbx
0x180071478  mov     eax, [rdi+30h]
0x18007147b  mov     ecx, r14d
0x18007147e  mov     [rsi+30h], eax
0x180071481  call    BallocElementFromMasterTable
0x180071486  test    eax, eax
0x180071488  jz      loc_180071510
0x18007148e  mov     ecx, [rbx+9E4h]
0x180071494  mov     rdx, rbx
0x180071497  mov     eax, [rbp+arg_10]
0x18007149a  imul    rsi, rax, 38h ; '8'
0x18007149e  add     rsi, r15
0x1800714a1  mov     [rsi], ecx
0x1800714a3  mov     rcx, rsi
0x1800714a6  mov     dword ptr [rsi+20h], 0
0x1800714ad  call    BInitKeywordField
0x1800714b2  test    eax, eax
0x1800714b4  jz      short loc_18007152B
0x1800714b6  mov     ecx, [rdi+2Ch]
0x1800714b9  lea     eax, [r14-14h]
0x1800714bd  mov     [rsi+2Ch], ecx
0x1800714c0  mov     ecx, [rdi+30h]
0x1800714c3  mov     [rsi+30h], ecx
0x1800714c6  jmp     short loc_18007152D
0x1800714c8  mov     rdx, rbx
0x1800714cb  mov     rcx, rdi
0x1800714ce  call    vIdentifySource
0x1800714d3  lea     rdx, aConcatenationT; "Concatenation to synthesize Memory opti"...
0x1800714da  lea     rcx, aBexpandmemconf; "BExpandMemConfig"
0x1800714e1  call    WriteDbgTraceErrorGpd
0x1800714e6  jmp     short loc_18007152B
0x1800714e8  mov     rdx, rbx
0x1800714eb  mov     rcx, rdi
0x1800714ee  call    vIdentifySource
0x1800714f3  mov     r9, [rdi+18h]
0x1800714f7  lea     rdx, aSyntaxErrorInV_0; "Syntax error in value of *MemConfig sho"...
0x1800714fe  mov     r8d, [rdi+20h]
0x180071502  lea     rcx, aBexpandmemconf; "BExpandMemConfig"
0x180071509  call    WriteDbgTraceErrorGpd
0x18007150e  jmp     short loc_18007152B
0x180071510  mov     eax, 2
0x180071515  mov     dword ptr [rbx+8A8h], 15h
0x18007151f  mov     [rbx+8ACh], eax
0x180071525  mov     [rbx+8B0h], eax
0x18007152b  xor     eax, eax
0x18007152d  mov     rbx, [rsp+70h+arg_8]
0x180071535  add     rsp, 70h
0x180071539  pop     r15
0x18007153b  pop     r14
0x18007153d  pop     r13
0x18007153f  pop     r12
0x180071541  pop     rdi
0x180071542  pop     rsi
0x180071543  pop     rbp
0x180071544  retn
```
