# jsonEachFilter

- ea: `0x1800af290`
- end: `0x1800af6ef`
- name: `jsonEachFilter`
- size: `1119`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x1800af290`
- `0x1800db900`
- `0x1800dca90`
- `0x1800dcce0`
- `0x1800dce90`
- `0x1800ddba0`
- `0x1800e0840`
- `0x1800e2d20`
- `0x1801089d0`
- `0x18011de20`
- `0x180155860`
- `0x180156350`
- `0x180158e20`
- `0x18015cf80`
- `0x18015db30`
- `0x180242d80`

## string_xrefs

- `0x1800af497`: `malformed JSON`
- `0x1800af4f5`: `bad JSON path: %Q`
- `0x1800af58e`: `bad JSON path: %Q`

## pseudocode

```c
__int64 __fastcall jsonEachFilter(__int64 *a1, int a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  _QWORD *v7; // rbx
  int v8; // eax
  __int64 v9; // rcx
  __int16 v10; // ax
  int v11; // edx
  __int64 v12; // rcx
  __int16 v13; // dx
  __int64 v14; // rsi
  __int64 v15; // rax
  __int16 v16; // dx
  __int64 v17; // rcx
  __int16 v18; // ax
  int v19; // eax
  __int64 result; // rax
  __int64 v21; // rbx
  unsigned int v22; // edx
  unsigned int v23; // edx
  unsigned int v24; // ebp
  _BYTE *v25; // rbx
  unsigned int v26; // eax
  unsigned int v27; // eax
  _DWORD *v28; // r14
  __int64 v29; // rdx
  int v30; // eax
  _BYTE *v31; // r8
  __int64 v32; // rcx
  _QWORD *v33; // rax
  int v34; // [rsp+58h] [rbp+10h] BYREF

  ((void (*)(void))jsonEachCursorReset)();
  if ( !a2 )
    return 0;
  v7 = a5;
  a1[24] = 0;
  a1[25] = 0;
  a1[26] = 0;
  *((_DWORD *)a1 + 56) = 0;
  a1[29] = 0;
  a1[30] = 0;
  a1[31] = 0;
  a1[32] = 0;
  a1[27] = a1[6];
  *((_DWORD *)a1 + 57) = 1;
  v8 = jsonFuncArgMightBeBinary(*v7);
  v9 = *v7;
  if ( v8 )
  {
    v10 = *(_WORD *)(v9 + 20);
    if ( (v10 & 2) != 0 && *(_BYTE *)(v9 + 22) == 1 )
    {
      v11 = *(_DWORD *)(v9 + 16);
    }
    else if ( (v10 & 0x10) != 0 )
    {
      v11 = *(_DWORD *)(v9 + 16);
      if ( (v10 & 0x400) != 0 )
        v11 += *(_DWORD *)v9;
    }
    else if ( (v10 & 1) != 0 )
    {
      v11 = 0;
    }
    else
    {
      v11 = valueBytes(v9, 1);
    }
    *((_DWORD *)a1 + 50) = v11;
    a1[24] = sqlite3_value_blob(*v7);
    goto LABEL_13;
  }
  if ( v9 )
  {
    v16 = *(_WORD *)(v9 + 20);
    if ( (v16 & 0x202) == 0x202 && *(_BYTE *)(v9 + 22) == 1 )
    {
      v15 = *(_QWORD *)(v9 + 8);
    }
    else if ( (v16 & 1) != 0 )
    {
      v15 = 0;
    }
    else
    {
      v15 = valueToText(v9, 1);
    }
  }
  else
  {
    v15 = 0;
  }
  a1[26] = v15;
  v17 = *v7;
  v18 = *(_WORD *)(*v7 + 20LL);
  if ( (v18 & 2) != 0 && *(_BYTE *)(v17 + 22) == 1 )
    goto LABEL_28;
  if ( (v18 & 0x10) == 0 )
  {
    if ( (v18 & 1) != 0 )
      v19 = 0;
    else
      v19 = valueBytes(v17, 1);
    goto LABEL_35;
  }
  if ( (v18 & 0x400) == 0 )
LABEL_28:
    v19 = *(_DWORD *)(v17 + 16);
  else
    v19 = *(_DWORD *)(v17 + 16) + *(_DWORD *)v17;
LABEL_35:
  *((_DWORD *)a1 + 56) = v19;
  if ( !a1[26] )
  {
    *(__int64 *)((char *)a1 + 12) = 0;
    return 0;
  }
  if ( (unsigned int)jsonConvertTextToBlob(a1 + 24, 0) )
  {
    if ( *((_BYTE *)a1 + 239) )
      return 7;
    sqlite3_free(*(_QWORD *)(*a1 + 16));
    v21 = *a1;
    *(_QWORD *)(v21 + 16) = sqlite3_mprintf("malformed JSON");
    jsonEachCursorReset(a1);
    v22 = 7;
    if ( *(_QWORD *)(*a1 + 16) )
      return 1;
    return v22;
  }
LABEL_13:
  if ( a2 != 3 )
  {
    *((_DWORD *)a1 + 3) = 0;
    *((_DWORD *)a1 + 5) = 1;
    v28 = (_DWORD *)a1 + 3;
    v24 = 0;
    v25 = a1 + 3;
    *((_BYTE *)a1 + 24) = 0;
    v29 = a1[10];
    if ( v29 + 1 < (unsigned __int64)a1[9] )
    {
      *(_BYTE *)(v29 + a1[8]) = 36;
      ++a1[10];
    }
    else
    {
      jsonStringExpandAndAppend(a1 + 7, "$", 1);
    }
    goto LABEL_65;
  }
  v12 = v7[1];
  if ( !v12 )
    return 0;
  v13 = *(_WORD *)(v12 + 20);
  if ( (v13 & 0x202) == 0x202 && *(_BYTE *)(v12 + 22) == 1 )
  {
    v14 = *(_QWORD *)(v12 + 8);
    goto LABEL_45;
  }
  if ( (v13 & 1) != 0 )
    return 0;
  v14 = valueToText(v12, 1);
LABEL_45:
  if ( !v14 )
    return 0;
  if ( *(_BYTE *)v14 != 36 )
  {
    sqlite3_free(*(_QWORD *)(*a1 + 16));
    *(_QWORD *)(*a1 + 16) = sqlite3_mprintf("bad JSON path: %Q", v14);
    jsonEachCursorReset(a1);
    v23 = 7;
    if ( *(_QWORD *)(*a1 + 16) )
      return 1;
    return v23;
  }
  *((_DWORD *)a1 + 5) = strlen((const char *)v14) & 0x3FFFFFFF;
  if ( !*(_BYTE *)(v14 + 1) )
  {
    v24 = 0;
    v25 = a1 + 3;
    *((_BYTE *)a1 + 24) = 0;
    v26 = 0;
LABEL_61:
    *((_DWORD *)a1 + 3) = v26;
    v28 = (_DWORD *)a1 + 3;
    jsonAppendRaw(a1 + 7, v14, *((unsigned int *)a1 + 5));
LABEL_65:
    *((_DWORD *)a1 + 7) = 0;
    v30 = jsonbPayloadSize(a1 + 24, v24, &v34);
    v31 = (_BYTE *)(a1[24] + v24);
    *((_DWORD *)a1 + 4) = v24 + v30 + v34;
    if ( (*v31 & 0xFu) < 0xB || *((_BYTE *)a1 + 25) )
      return 0;
    v32 = a1[6];
    *v28 = v24 + v30;
    *v25 = *v31 & 0xF;
    if ( v32 )
      v33 = (_QWORD *)sqlite3DbMallocRawNN(v32, 24);
    else
      v33 = (_QWORD *)sqlite3Malloc(24);
    if ( v33 )
    {
      *v33 = 0;
      v33[1] = 0;
      a1[5] = (__int64)v33;
      *((_DWORD *)a1 + 7) = 1;
      *((_DWORD *)a1 + 8) = 1;
      v33[2] = 0;
      *(_DWORD *)(a1[5] + 8) = *((_DWORD *)a1 + 4);
      *(_DWORD *)a1[5] = *((_DWORD *)a1 + 3);
      *(_DWORD *)(a1[5] + 4) = v24;
      return 0;
    }
    a1[5] = 0;
    return 7;
  }
  v27 = jsonLookupStep(a1 + 24, 0, v14 + 1, 0);
  v24 = v27;
  if ( v27 < 0xFFFFFFFD )
  {
    v26 = *((_DWORD *)a1 + 63);
    v25 = a1 + 3;
    if ( v26 )
    {
      *v25 = 12;
    }
    else
    {
      *v25 = 11;
      v26 = v24;
    }
    goto LABEL_61;
  }
  if ( v27 == -2 )
  {
    *(__int64 *)((char *)a1 + 12) = 0;
    *((_BYTE *)a1 + 24) = 0;
    return 0;
  }
  _mm_lfence();
  sqlite3_free(*(_QWORD *)(*a1 + 16));
  *(_QWORD *)(*a1 + 16) = sqlite3_mprintf("bad JSON path: %Q", v14);
  jsonEachCursorReset(a1);
  result = 7;
  if ( *(_QWORD *)(*a1 + 16) )
    return 1;
  return result;
}

```

## disassembly

```asm
0x1800af290  mov     [rsp+arg_0], rbx
0x1800af295  mov     [rsp+arg_10], rbp
0x1800af29a  mov     [rsp+arg_18], rsi
0x1800af29f  push    rdi
0x1800af2a0  push    r12
0x1800af2a2  push    r13
0x1800af2a4  push    r14
0x1800af2a6  push    r15
0x1800af2a8  sub     rsp, 20h
0x1800af2ac  mov     esi, edx
0x1800af2ae  mov     rdi, rcx
0x1800af2b1  call    jsonEachCursorReset
0x1800af2b6  test    esi, esi
0x1800af2b8  jz      loc_1800AF446
0x1800af2be  mov     rbx, [rsp+48h+arg_20]
0x1800af2c3  xor     r12d, r12d
0x1800af2c6  mov     [rdi+0C0h], r12
0x1800af2cd  mov     r13d, 1
0x1800af2d3  mov     [rdi+0C8h], r12
0x1800af2da  mov     [rdi+0D0h], r12
0x1800af2e1  mov     [rdi+0E0h], r12d
0x1800af2e8  mov     [rdi+0E8h], r12
0x1800af2ef  mov     [rdi+0F0h], r12
0x1800af2f6  mov     [rdi+0F8h], r12
0x1800af2fd  mov     [rdi+100h], r12
0x1800af304  mov     rax, [rdi+30h]
0x1800af308  mov     [rdi+0D8h], rax
0x1800af30f  mov     [rdi+0E4h], r13d
0x1800af316  mov     rcx, [rbx]
0x1800af319  call    jsonFuncArgMightBeBinary
0x1800af31e  mov     rcx, [rbx]
0x1800af321  mov     ebp, 202h
0x1800af326  test    eax, eax
0x1800af328  jz      loc_1800AF3B9
0x1800af32e  movzx   eax, word ptr [rcx+14h]
0x1800af332  test    al, 2
0x1800af334  jz      short loc_1800AF341
0x1800af336  cmp     [rcx+16h], r13b
0x1800af33a  jnz     short loc_1800AF341
0x1800af33c  mov     edx, [rcx+10h]
0x1800af33f  jmp     short loc_1800AF368
0x1800af341  test    al, 10h
0x1800af343  jz      short loc_1800AF353
0x1800af345  bt      ax, 0Ah
0x1800af34a  mov     edx, [rcx+10h]
0x1800af34d  jnb     short loc_1800AF368
0x1800af34f  add     edx, [rcx]
0x1800af351  jmp     short loc_1800AF368
0x1800af353  test    r13b, al
0x1800af356  jz      short loc_1800AF35D
0x1800af358  mov     edx, r12d
0x1800af35b  jmp     short loc_1800AF368
0x1800af35d  movzx   edx, r13b
0x1800af361  call    valueBytes
0x1800af366  mov     edx, eax
0x1800af368  mov     [rdi+0C8h], edx
0x1800af36e  mov     rcx, [rbx]
0x1800af371  call    sqlite3_value_blob
0x1800af376  mov     [rdi+0C0h], rax
0x1800af37d  cmp     esi, 3
0x1800af380  jnz     loc_1800AF5EF
0x1800af386  mov     rcx, [rbx+8]
0x1800af38a  test    rcx, rcx
0x1800af38d  jz      loc_1800AF446
0x1800af393  movzx   edx, word ptr [rcx+14h]
0x1800af397  movzx   eax, dx
0x1800af39a  and     ax, bp
0x1800af39d  cmp     ax, bp
0x1800af3a0  jnz     loc_1800AF4C3
0x1800af3a6  cmp     [rcx+16h], r13b
0x1800af3aa  jnz     loc_1800AF4C3
0x1800af3b0  mov     rsi, [rcx+8]
0x1800af3b4  jmp     loc_1800AF4D8
0x1800af3b9  test    rcx, rcx
0x1800af3bc  jnz     short loc_1800AF3C3
0x1800af3be  mov     rax, r12
0x1800af3c1  jmp     short loc_1800AF3F1
0x1800af3c3  movzx   edx, word ptr [rcx+14h]
0x1800af3c7  movzx   eax, dx
0x1800af3ca  and     ax, bp
0x1800af3cd  cmp     ax, bp
0x1800af3d0  jnz     short loc_1800AF3DE
0x1800af3d2  cmp     [rcx+16h], r13b
0x1800af3d6  jnz     short loc_1800AF3DE
0x1800af3d8  mov     rax, [rcx+8]
0x1800af3dc  jmp     short loc_1800AF3F1
0x1800af3de  test    r13b, dl
0x1800af3e1  jz      short loc_1800AF3E8
0x1800af3e3  mov     rax, r12
0x1800af3e6  jmp     short loc_1800AF3F1
0x1800af3e8  movzx   edx, r13b
0x1800af3ec  call    valueToText
0x1800af3f1  mov     [rdi+0D0h], rax
0x1800af3f8  mov     rcx, [rbx]
0x1800af3fb  movzx   eax, word ptr [rcx+14h]
0x1800af3ff  test    al, 2
0x1800af401  jz      short loc_1800AF40E
0x1800af403  cmp     [rcx+16h], r13b
0x1800af407  jnz     short loc_1800AF40E
0x1800af409  mov     eax, [rcx+10h]
0x1800af40c  jmp     short loc_1800AF433
0x1800af40e  test    al, 10h
0x1800af410  jz      short loc_1800AF420
0x1800af412  bt      ax, 0Ah
0x1800af417  jnb     short loc_1800AF409
0x1800af419  mov     eax, [rcx]
0x1800af41b  add     eax, [rcx+10h]
0x1800af41e  jmp     short loc_1800AF433
0x1800af420  test    r13b, al
0x1800af423  jz      short loc_1800AF42A
0x1800af425  mov     eax, r12d
0x1800af428  jmp     short loc_1800AF433
0x1800af42a  movzx   edx, r13b
0x1800af42e  call    valueBytes
0x1800af433  mov     [rdi+0E0h], eax
0x1800af439  cmp     [rdi+0D0h], r12
0x1800af440  jnz     short loc_1800AF465
0x1800af442  mov     [rdi+0Ch], r12
0x1800af446  xor     eax, eax
0x1800af448  mov     rbx, [rsp+48h+arg_0]
0x1800af44d  mov     rbp, [rsp+48h+arg_10]
0x1800af452  mov     rsi, [rsp+48h+arg_18]
0x1800af457  add     rsp, 20h
0x1800af45b  pop     r15
0x1800af45d  pop     r14
0x1800af45f  pop     r13
0x1800af461  pop     r12
0x1800af463  pop     rdi
0x1800af464  retn
0x1800af465  xor     edx, edx
0x1800af467  lea     rcx, [rdi+0C0h]
0x1800af46e  call    jsonConvertTextToBlob
0x1800af473  test    eax, eax
0x1800af475  jz      loc_1800AF37D
0x1800af47b  cmp     [rdi+0EFh], r12b
0x1800af482  jnz     loc_1800AF6E5
0x1800af488  mov     rcx, [rdi]
0x1800af48b  mov     rcx, [rcx+10h]
0x1800af48f  call    sqlite3_free
0x1800af494  mov     rbx, [rdi]
0x1800af497  lea     rcx, aMalformedJson; "malformed JSON"
0x1800af49e  call    sqlite3_mprintf
0x1800af4a3  mov     rcx, rdi
0x1800af4a6  mov     [rbx+10h], rax
0x1800af4aa  call    jsonEachCursorReset
0x1800af4af  mov     rax, [rdi]
0x1800af4b2  mov     edx, 7
0x1800af4b7  cmp     [rax+10h], r12
0x1800af4bb  cmovnz  edx, r13d
0x1800af4bf  mov     eax, edx
0x1800af4c1  jmp     short loc_1800AF448
0x1800af4c3  test    r13b, dl
0x1800af4c6  jnz     loc_1800AF446
0x1800af4cc  movzx   edx, r13b
0x1800af4d0  call    valueToText
0x1800af4d5  mov     rsi, rax
0x1800af4d8  test    rsi, rsi
0x1800af4db  jz      loc_1800AF446
0x1800af4e1  cmp     byte ptr [rsi], 24h ; '$'
0x1800af4e4  jz      short loc_1800AF527
0x1800af4e6  mov     rcx, [rdi]
0x1800af4e9  mov     rcx, [rcx+10h]
0x1800af4ed  call    sqlite3_free
0x1800af4f2  mov     rdx, rsi
0x1800af4f5  lea     rcx, aBadJsonPathQ; "bad JSON path: %Q"
0x1800af4fc  call    sqlite3_mprintf
0x1800af501  mov     rcx, [rdi]
0x1800af504  mov     [rcx+10h], rax
0x1800af508  mov     rcx, rdi
0x1800af50b  call    jsonEachCursorReset
0x1800af510  mov     rax, [rdi]
0x1800af513  mov     edx, 7
0x1800af518  cmp     [rax+10h], r12
0x1800af51c  cmovnz  edx, r13d
0x1800af520  mov     eax, edx
0x1800af522  jmp     loc_1800AF448
0x1800af527  mov     rcx, rsi; Str
0x1800af52a  call    strlen
0x1800af52f  and     eax, 3FFFFFFFh
0x1800af534  lea     r8, [rsi+1]
0x1800af538  mov     [rdi+14h], eax
0x1800af53b  cmp     [r8], r12b
0x1800af53e  jnz     short loc_1800AF552
0x1800af540  mov     ebp, r12d
0x1800af543  lea     rbx, [rdi+18h]
0x1800af547  mov     [rbx], bpl
0x1800af54a  mov     eax, r12d
0x1800af54d  jmp     loc_1800AF5D6
0x1800af552  xor     r9d, r9d
0x1800af555  lea     rcx, [rdi+0C0h]
0x1800af55c  xor     edx, edx
0x1800af55e  call    jsonLookupStep
0x1800af563  mov     ebp, eax
0x1800af565  cmp     eax, 0FFFFFFFDh
0x1800af568  jb      short loc_1800AF5BE
0x1800af56a  cmp     eax, 0FFFFFFFEh
0x1800af56d  jnz     short loc_1800AF57C
0x1800af56f  mov     [rdi+0Ch], r12
0x1800af573  mov     [rdi+18h], r12b
0x1800af577  jmp     loc_1800AF446
0x1800af57c  lfence
0x1800af57f  mov     rcx, [rdi]
0x1800af582  mov     rcx, [rcx+10h]
0x1800af586  call    sqlite3_free
0x1800af58b  mov     rdx, rsi
0x1800af58e  lea     rcx, aBadJsonPathQ; "bad JSON path: %Q"
0x1800af595  call    sqlite3_mprintf
0x1800af59a  mov     rcx, [rdi]
0x1800af59d  mov     [rcx+10h], rax
0x1800af5a1  mov     rcx, rdi
0x1800af5a4  call    jsonEachCursorReset
0x1800af5a9  mov     rcx, [rdi]
0x1800af5ac  mov     eax, 7
0x1800af5b1  cmp     [rcx+10h], r12
0x1800af5b5  cmovnz  eax, r13d
0x1800af5b9  jmp     loc_1800AF448
0x1800af5be  mov     eax, [rdi+0FCh]
0x1800af5c4  lea     rbx, [rdi+18h]
0x1800af5c8  test    eax, eax
0x1800af5ca  jz      short loc_1800AF5D1
0x1800af5cc  mov     byte ptr [rbx], 0Ch
0x1800af5cf  jmp     short loc_1800AF5D6
0x1800af5d1  mov     byte ptr [rbx], 0Bh
0x1800af5d4  mov     eax, ebp
0x1800af5d6  mov     [rdi+0Ch], eax
0x1800af5d9  lea     r14, [rdi+0Ch]
0x1800af5dd  mov     r8d, [rdi+14h]
0x1800af5e1  lea     rcx, [rdi+38h]
0x1800af5e5  mov     rdx, rsi
0x1800af5e8  call    jsonAppendRaw
0x1800af5ed  jmp     short loc_1800AF634
0x1800af5ef  lea     rcx, [rdi+38h]
0x1800af5f3  mov     [rdi+0Ch], r12d
0x1800af5f7  mov     [rdi+14h], r13d
0x1800af5fb  lea     r14, [rdi+0Ch]
0x1800af5ff  mov     ebp, r12d
0x1800af602  lea     rbx, [rdi+18h]
0x1800af606  mov     [rbx], bpl
0x1800af609  mov     rdx, [rcx+18h]
0x1800af60d  lea     rax, [rdx+1]
0x1800af611  cmp     rax, [rcx+10h]
0x1800af615  jb      short loc_1800AF628
0x1800af617  mov     r8d, r13d
0x1800af61a  lea     rdx, asc_180273F30; "$"
0x1800af621  call    jsonStringExpandAndAppend
0x1800af626  jmp     short loc_1800AF634
0x1800af628  mov     rax, [rcx+8]
0x1800af62c  mov     byte ptr [rdx+rax], 24h ; '$'
0x1800af630  inc     qword ptr [rcx+18h]
0x1800af634  lea     r8, [rsp+48h+arg_8]
0x1800af639  mov     [rdi+1Ch], r12d
0x1800af63d  mov     edx, ebp
0x1800af63f  lea     rcx, [rdi+0C0h]
0x1800af646  call    jsonbPayloadSize
0x1800af64b  mov     edx, [rsp+48h+arg_8]
0x1800af64f  add     edx, eax
0x1800af651  mov     r8d, ebp
0x1800af654  add     r8, [rdi+0C0h]
0x1800af65b  add     edx, ebp
0x1800af65d  mov     [rdi+10h], edx
0x1800af660  movzx   ecx, byte ptr [r8]
0x1800af664  and     cl, 0Fh
0x1800af667  cmp     cl, 0Bh
0x1800af66a  jb      loc_1800AF446
0x1800af670  cmp     [rdi+19h], r12b
0x1800af674  jnz     loc_1800AF446
0x1800af67a  mov     rcx, [rdi+30h]
0x1800af67e  add     eax, ebp
0x1800af680  mov     [r14], eax
0x1800af683  movzx   eax, byte ptr [r8]
0x1800af687  and     al, 0Fh
0x1800af689  mov     [rbx], al
0x1800af68b  test    rcx, rcx
0x1800af68e  jz      short loc_1800AF69C
0x1800af690  mov     edx, 18h
0x1800af695  call    sqlite3DbMallocRawNN
0x1800af69a  jmp     short loc_1800AF6A6
0x1800af69c  mov     ecx, 18h
0x1800af6a1  call    sqlite3Malloc
0x1800af6a6  test    rax, rax
0x1800af6a9  jz      short loc_1800AF6E1
0x1800af6ab  mov     [rax], r12
0x1800af6ae  mov     [rax+8], r12
0x1800af6b2  mov     [rdi+28h], rax
0x1800af6b6  mov     [rdi+1Ch], r13d
0x1800af6ba  mov     [rdi+20h], r13d
0x1800af6be  mov     [rax+10h], r12
0x1800af6c2  mov     eax, [rdi+10h]
0x1800af6c5  mov     rcx, [rdi+28h]
0x1800af6c9  mov     [rcx+8], eax
0x1800af6cc  mov     eax, [rdi+0Ch]
0x1800af6cf  mov     rcx, [rdi+28h]
0x1800af6d3  mov     [rcx], eax
0x1800af6d5  mov     rax, [rdi+28h]
0x1800af6d9  mov     [rax+4], ebp
0x1800af6dc  jmp     loc_1800AF446
0x1800af6e1  mov     [rdi+28h], rax
0x1800af6e5  mov     eax, 7
0x1800af6ea  jmp     loc_1800AF448
```
