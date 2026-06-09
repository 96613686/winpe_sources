# jsonEachFilter

- ea: `0x1800083b0`
- end: `0x180008768`
- name: `jsonEachFilter`
- size: `952`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x180005450`
- `0x180005740`
- `0x180005980`
- `0x1800083b0`
- `0x18000a9b0`
- `0x180047e30`
- `0x180048300`
- `0x180048dd0`
- `0x1800495c0`
- `0x1800496e0`
- `0x180088560`
- `0x1800935a0`
- `0x1800bf820`
- `0x1800c34f0`
- `0x1800c3e10`
- `0x1800e4dfe`

## string_xrefs

- `0x180008546`: `malformed JSON`
- `0x1800086a5`: `JSON path error near '%q'`

## pseudocode

```c
__int64 __fastcall jsonEachFilter(__int64 *a1, int a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  _QWORD *v7; // r15
  __int64 v8; // rcx
  __int64 v9; // rdx
  _QWORD *v10; // rbx
  int v11; // r14d
  __int64 v12; // r8
  __int16 v13; // ax
  int v14; // ecx
  __int64 v15; // rbp
  void *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned int v19; // esi
  __int64 v20; // rbx
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int16 v25; // dx
  _BYTE *v26; // rbx
  __int64 v27; // rbp
  void *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rax
  unsigned int v31; // esi
  __int64 v32; // rcx
  unsigned __int8 v33; // al
  __int64 v34; // r8
  __int64 v35; // rdx
  unsigned int v36; // r8d
  _BYTE *v37; // [rsp+80h] [rbp+8h] BYREF

  sqlite3_free(a1[5]);
  jsonParseReset(a1 + 6);
  *((_DWORD *)a1 + 2) = 0;
  a1[2] = 0;
  *((_BYTE *)a1 + 24) = 0;
  a1[4] = 0;
  a1[5] = 0;
  if ( !a2 )
    return 0;
  v7 = a5;
  v8 = *a5;
  if ( !*a5 )
    return 0;
  v9 = *(unsigned __int16 *)(v8 + 20);
  if ( (v9 & 0x202) == 0x202 && *(_BYTE *)(v8 + 22) == 1 )
  {
    v10 = *(_QWORD **)(v8 + 8);
  }
  else
  {
    if ( (v9 & 1) != 0 )
      return 0;
    LOBYTE(v9) = 1;
    v10 = (_QWORD *)valueToText(v8, v9);
  }
  if ( !v10 )
    return 0;
  v11 = 1;
  *((_OWORD *)a1 + 3) = 0;
  *((_OWORD *)a1 + 4) = 0;
  *((_OWORD *)a1 + 5) = 0;
  *((_OWORD *)a1 + 6) = 0;
  *((_OWORD *)a1 + 7) = 0;
  *((_DWORD *)a1 + 26) = 1;
  v12 = *v7;
  if ( *v7
    && (*(_WORD *)(v12 + 20) & 0x12) != 0
    && (*(_WORD *)(v12 + 20) & 0x1000) != 0
    && *(__int64 (__fastcall **)())(v12 + 48) == sqlite3RCStrUnref )
  {
    ++*(v10 - 1);
    a1[8] = (__int64)v10;
  }
  else
  {
    v13 = *(_WORD *)(v12 + 20);
    if ( (v13 & 2) != 0 && *(_BYTE *)(v12 + 22) == 1 )
    {
      v14 = *(_DWORD *)(v12 + 16);
    }
    else if ( (v13 & 0x10) != 0 )
    {
      v14 = *(_DWORD *)(v12 + 16);
      if ( (v13 & 0x400) != 0 )
        v14 += *(_DWORD *)v12;
    }
    else if ( (v13 & 1) != 0 )
    {
      v14 = 0;
    }
    else
    {
      v14 = valueBytes(*v7, 1);
    }
    v15 = v14;
    v16 = (void *)sqlite3RCStrNew(v14 + 1LL);
    a1[8] = (__int64)v16;
    if ( !v16 )
      return 7;
    memcpy_0(v16, v10, v15 + 1);
  }
  a1[4] = a1[8];
  *((_BYTE *)a1 + 100) = 1;
  if ( (unsigned int)jsonParse(a1 + 6, 0) )
  {
    v19 = 7;
    if ( !*((_BYTE *)a1 + 99) )
    {
      sqlite3_free(*(_QWORD *)(*a1 + 16));
      v20 = *a1;
      *(_QWORD *)(v20 + 16) = sqlite3_mprintf("malformed JSON");
      if ( !*(_QWORD *)(*a1 + 16) )
        v11 = 7;
      v19 = v11;
    }
    jsonEachCursorReset(a1);
    return v19;
  }
  if ( *((_BYTE *)a1 + 25) )
  {
    v22 = *((unsigned int *)a1 + 12);
    if ( (unsigned int)sqlite3_initialize(v18, v17) )
    {
      a1[10] = 0;
LABEL_34:
      *((_BYTE *)a1 + 99) = 1;
      jsonEachCursorReset(a1);
      return 7;
    }
    v23 = sqlite3Malloc(4 * v22);
    a1[10] = v23;
    if ( !v23 )
      goto LABEL_34;
    jsonParseFillInParentage(a1 + 6, 0, 0);
  }
  if ( a2 != 3 )
  {
    v29 = a1[7];
    goto LABEL_56;
  }
  v24 = v7[1];
  v37 = 0;
  if ( !v24 )
    return 0;
  v25 = *(_WORD *)(v24 + 20);
  if ( (v25 & 0x202) == 0x202 && *(_BYTE *)(v24 + 22) == 1 )
  {
    v26 = *(_BYTE **)(v24 + 8);
  }
  else
  {
    if ( (v25 & 1) != 0 )
      return 0;
    v26 = (_BYTE *)valueToText(v24, 1);
  }
  if ( !v26 )
    return 0;
  v27 = (int)sqlite3_value_bytes(v7[1]);
  v28 = (void *)sqlite3_malloc64(v27 + 1);
  a1[5] = (__int64)v28;
  if ( !v28 )
    return 7;
  memcpy_0(v28, v26, v27 + 1);
  if ( *v26 == 36 )
  {
    v30 = jsonLookupStep((int)a1 + 48, 0, *((_DWORD *)a1 + 10) + 1, 0, (__int64)&v37);
    v26 = v37;
    v29 = v30;
  }
  else
  {
    v29 = 0;
    v37 = v26;
  }
  if ( !v26 )
  {
    if ( v29 )
    {
LABEL_56:
      v32 = (v29 - a1[7]) >> 4;
      *((_DWORD *)a1 + 4) = v32;
      *((_DWORD *)a1 + 3) = v32;
      v33 = *(_BYTE *)v29;
      *((_BYTE *)a1 + 24) = *(_BYTE *)v29;
      if ( v33 < 7u )
      {
        *((_DWORD *)a1 + 5) = v32 + 1;
      }
      else
      {
        *(_DWORD *)(v29 + 8) = 0;
        v34 = *((unsigned int *)a1 + 4);
        *((_DWORD *)a1 + 5) = *(_DWORD *)(v29 + 4) + v34 + 1;
        if ( *((_BYTE *)a1 + 25) )
        {
          v35 = a1[7];
          *((_BYTE *)a1 + 24) = *(_BYTE *)(v35 + 16LL * *(unsigned int *)(a1[10] + 4 * v34));
          if ( (_DWORD)v34 )
          {
            v36 = v34 - 1;
            if ( (*(_BYTE *)(v35 + 16LL * v36 + 1) & 0x20) != 0 )
              *((_DWORD *)a1 + 4) = v36;
          }
        }
        else
        {
          *((_DWORD *)a1 + 4) = v34 + 1;
        }
      }
      return 0;
    }
    return 0;
  }
  sqlite3_free(*(_QWORD *)(*a1 + 16));
  *(_QWORD *)(*a1 + 16) = sqlite3_mprintf("JSON path error near '%q'", v37);
  jsonEachCursorReset(a1);
  v31 = 7;
  if ( *(_QWORD *)(*a1 + 16) )
    return 1;
  return v31;
}

```

## disassembly

```asm
0x1800083b0  push    rbx
0x1800083b2  push    rbp
0x1800083b3  push    rsi
0x1800083b4  push    rdi
0x1800083b5  push    r12
0x1800083b7  push    r13
0x1800083b9  push    r14
0x1800083bb  push    r15
0x1800083bd  sub     rsp, 38h
0x1800083c1  mov     rdi, rcx
0x1800083c4  mov     r12d, edx
0x1800083c7  mov     rcx, [rcx+28h]
0x1800083cb  call    sqlite3_free
0x1800083d0  lea     rcx, [rdi+30h]
0x1800083d4  call    jsonParseReset
0x1800083d9  xor     r13d, r13d
0x1800083dc  mov     [rdi+8], r13d
0x1800083e0  mov     [rdi+10h], r13
0x1800083e4  mov     [rdi+18h], r13b
0x1800083e8  mov     [rdi+20h], r13
0x1800083ec  mov     [rdi+28h], r13
0x1800083f0  test    r12d, r12d
0x1800083f3  jz      loc_180008755
0x1800083f9  mov     r15, [rsp+78h+arg_20]
0x180008401  mov     rcx, [r15]
0x180008404  test    rcx, rcx
0x180008407  jz      loc_180008755
0x18000840d  movzx   edx, word ptr [rcx+14h]
0x180008411  mov     ebp, 202h
0x180008416  movzx   eax, dx
0x180008419  and     ax, bp
0x18000841c  cmp     ax, bp
0x18000841f  jnz     short loc_18000842D
0x180008421  cmp     byte ptr [rcx+16h], 1
0x180008425  jnz     short loc_18000842D
0x180008427  mov     rbx, [rcx+8]
0x18000842b  jmp     short loc_180008440
0x18000842d  test    dl, 1
0x180008430  jnz     loc_180008755
0x180008436  mov     dl, 1
0x180008438  call    valueToText
0x18000843d  mov     rbx, rax
0x180008440  test    rbx, rbx
0x180008443  jz      loc_180008755
0x180008449  xorps   xmm0, xmm0
0x18000844c  mov     r14d, 1
0x180008452  movups  xmmword ptr [rdi+30h], xmm0
0x180008456  movups  xmmword ptr [rdi+40h], xmm0
0x18000845a  movups  xmmword ptr [rdi+50h], xmm0
0x18000845e  movups  xmmword ptr [rdi+60h], xmm0
0x180008462  movups  xmmword ptr [rdi+70h], xmm0
0x180008466  mov     [rdi+68h], r14d
0x18000846a  mov     r8, [r15]
0x18000846d  test    r8, r8
0x180008470  jz      short loc_1800084A3
0x180008472  movzx   eax, word ptr [r8+14h]
0x180008477  mov     edx, 0Ch
0x18000847c  test    al, 12h
0x18000847e  setnz   cl
0x180008481  bt      ax, dx
0x180008485  setb    al
0x180008488  test    al, cl
0x18000848a  jz      short loc_1800084A3
0x18000848c  lea     rax, sqlite3RCStrUnref
0x180008493  cmp     [r8+30h], rax
0x180008497  jnz     short loc_1800084A3
0x180008499  inc     qword ptr [rbx-8]
0x18000849d  mov     [rdi+40h], rbx
0x1800084a1  jmp     short loc_180008511
0x1800084a3  movzx   eax, word ptr [r8+14h]
0x1800084a8  test    al, 2
0x1800084aa  jz      short loc_1800084B8
0x1800084ac  cmp     [r8+16h], r14b
0x1800084b0  jnz     short loc_1800084B8
0x1800084b2  mov     ecx, [r8+10h]
0x1800084b6  jmp     short loc_1800084E4
0x1800084b8  test    al, 10h
0x1800084ba  jz      short loc_1800084CC
0x1800084bc  bt      ax, 0Ah
0x1800084c1  mov     ecx, [r8+10h]
0x1800084c5  jnb     short loc_1800084E4
0x1800084c7  add     ecx, [r8]
0x1800084ca  jmp     short loc_1800084E4
0x1800084cc  test    r14b, al
0x1800084cf  jz      short loc_1800084D6
0x1800084d1  mov     ecx, r13d
0x1800084d4  jmp     short loc_1800084E4
0x1800084d6  movzx   edx, r14b
0x1800084da  mov     rcx, r8
0x1800084dd  call    valueBytes
0x1800084e2  mov     ecx, eax
0x1800084e4  movsxd  rbp, ecx
0x1800084e7  lea     rcx, [rbp+1]
0x1800084eb  call    sqlite3RCStrNew
0x1800084f0  mov     [rdi+40h], rax
0x1800084f4  test    rax, rax
0x1800084f7  jz      loc_1800085AC
0x1800084fd  lea     r8, [rbp+1]; Size
0x180008501  mov     rdx, rbx; Src
0x180008504  mov     rcx, rax; void *
0x180008507  call    memcpy_0
0x18000850c  mov     ebp, 202h
0x180008511  mov     rax, [rdi+40h]
0x180008515  lea     rcx, [rdi+30h]
0x180008519  xor     edx, edx
0x18000851b  mov     [rdi+20h], rax
0x18000851f  mov     [rdi+64h], r14b
0x180008523  call    jsonParse
0x180008528  test    eax, eax
0x18000852a  jz      short loc_180008573
0x18000852c  mov     esi, 7
0x180008531  cmp     [rdi+63h], r13b
0x180008535  jnz     short loc_180008564
0x180008537  mov     rcx, [rdi]
0x18000853a  mov     rcx, [rcx+10h]
0x18000853e  call    sqlite3_free
0x180008543  mov     rbx, [rdi]
0x180008546  lea     rcx, aMalformedJson; "malformed JSON"
0x18000854d  call    sqlite3_mprintf
0x180008552  mov     [rbx+10h], rax
0x180008556  mov     rcx, [rdi]
0x180008559  cmp     [rcx+10h], r13
0x18000855d  cmovz   r14d, esi
0x180008561  mov     esi, r14d
0x180008564  mov     rcx, rdi
0x180008567  call    jsonEachCursorReset
0x18000856c  mov     eax, esi
0x18000856e  jmp     loc_180008757
0x180008573  cmp     [rdi+19h], r13b
0x180008577  jz      short loc_1800085C4
0x180008579  mov     ebx, [rdi+30h]
0x18000857c  call    sqlite3_initialize
0x180008581  test    eax, eax
0x180008583  jz      short loc_18000858B
0x180008585  mov     [rdi+50h], r13
0x180008589  jmp     short loc_1800085A0
0x18000858b  mov     rcx, rbx
0x18000858e  shl     rcx, 2
0x180008592  call    sqlite3Malloc
0x180008597  mov     [rdi+50h], rax
0x18000859b  test    rax, rax
0x18000859e  jnz     short loc_1800085B6
0x1800085a0  mov     rcx, rdi
0x1800085a3  mov     [rdi+63h], r14b
0x1800085a7  call    jsonEachCursorReset
0x1800085ac  mov     eax, 7
0x1800085b1  jmp     loc_180008757
0x1800085b6  xor     r8d, r8d
0x1800085b9  lea     rcx, [rdi+30h]
0x1800085bd  xor     edx, edx
0x1800085bf  call    jsonParseFillInParentage
0x1800085c4  cmp     r12d, 3
0x1800085c8  jnz     loc_1800086DE
0x1800085ce  mov     rcx, [r15+8]
0x1800085d2  mov     [rsp+78h+arg_0], r13
0x1800085da  test    rcx, rcx
0x1800085dd  jz      loc_180008755
0x1800085e3  movzx   edx, word ptr [rcx+14h]
0x1800085e7  movzx   eax, dx
0x1800085ea  and     ax, bp
0x1800085ed  cmp     ax, bp
0x1800085f0  jnz     short loc_1800085FE
0x1800085f2  cmp     [rcx+16h], r14b
0x1800085f6  jnz     short loc_1800085FE
0x1800085f8  mov     rbx, [rcx+8]
0x1800085fc  jmp     short loc_180008613
0x1800085fe  test    r14b, dl
0x180008601  jnz     loc_180008755
0x180008607  movzx   edx, r14b
0x18000860b  call    valueToText
0x180008610  mov     rbx, rax
0x180008613  test    rbx, rbx
0x180008616  jz      loc_180008755
0x18000861c  mov     rcx, [r15+8]
0x180008620  call    sqlite3_value_bytes
0x180008625  movsxd  rbp, eax
0x180008628  lea     rcx, [rbp+1]
0x18000862c  call    sqlite3_malloc64
0x180008631  mov     [rdi+28h], rax
0x180008635  test    rax, rax
0x180008638  jz      loc_1800085AC
0x18000863e  lea     r8, [rbp+1]; Size
0x180008642  mov     rdx, rbx; Src
0x180008645  mov     rcx, rax; void *
0x180008648  call    memcpy_0
0x18000864d  cmp     byte ptr [rbx], 24h ; '$'
0x180008650  jz      short loc_18000865F
0x180008652  mov     rdx, r13
0x180008655  mov     [rsp+78h+arg_0], rbx
0x18000865d  jmp     short loc_18000868C
0x18000865f  mov     r8, [rdi+28h]
0x180008663  lea     rax, [rsp+78h+arg_0]
0x18000866b  inc     r8
0x18000866e  mov     [rsp+78h+var_58], rax
0x180008673  xor     r9d, r9d
0x180008676  lea     rcx, [rdi+30h]
0x18000867a  xor     edx, edx
0x18000867c  call    jsonLookupStep
0x180008681  mov     rbx, [rsp+78h+arg_0]
0x180008689  mov     rdx, rax
0x18000868c  test    rbx, rbx
0x18000868f  jz      short loc_1800086D7
0x180008691  mov     rcx, [rdi]
0x180008694  mov     rcx, [rcx+10h]
0x180008698  call    sqlite3_free
0x18000869d  mov     rdx, [rsp+78h+arg_0]
0x1800086a5  lea     rcx, aJsonPathErrorN; "JSON path error near '%q'"
0x1800086ac  call    sqlite3_mprintf
0x1800086b1  mov     rcx, [rdi]
0x1800086b4  mov     [rcx+10h], rax
0x1800086b8  mov     rcx, rdi
0x1800086bb  call    jsonEachCursorReset
0x1800086c0  mov     rax, [rdi]
0x1800086c3  mov     esi, 7
0x1800086c8  cmp     [rax+10h], r13
0x1800086cc  cmovnz  esi, r14d
0x1800086d0  mov     eax, esi
0x1800086d2  jmp     loc_180008757
0x1800086d7  test    rdx, rdx
0x1800086da  jz      short loc_180008755
0x1800086dc  jmp     short loc_1800086E2
0x1800086de  mov     rdx, [rdi+38h]
0x1800086e2  mov     rcx, rdx
0x1800086e5  sub     rcx, [rdi+38h]
0x1800086e9  sar     rcx, 4
0x1800086ed  mov     [rdi+10h], ecx
0x1800086f0  mov     [rdi+0Ch], ecx
0x1800086f3  movzx   eax, byte ptr [rdx]
0x1800086f6  mov     [rdi+18h], al
0x1800086f9  cmp     al, 7
0x1800086fb  jb      short loc_18000874F
0x1800086fd  mov     [rdx+8], r13d
0x180008701  mov     r8d, [rdi+10h]
0x180008705  lea     ecx, [r8+1]
0x180008709  add     ecx, [rdx+4]
0x18000870c  mov     [rdi+14h], ecx
0x18000870f  cmp     [rdi+19h], r13b
0x180008713  jz      short loc_180008746
0x180008715  mov     rax, [rdi+50h]
0x180008719  mov     rdx, [rdi+38h]
0x18000871d  mov     eax, [rax+r8*4]
0x180008721  add     rax, rax
0x180008724  movzx   eax, byte ptr [rdx+rax*8]
0x180008728  mov     [rdi+18h], al
0x18000872b  test    r8d, r8d
0x18000872e  jz      short loc_180008755
0x180008730  dec     r8d
0x180008733  mov     eax, r8d
0x180008736  add     rax, rax
0x180008739  test    byte ptr [rdx+rax*8+1], 20h
0x18000873e  jz      short loc_180008755
0x180008740  mov     [rdi+10h], r8d
0x180008744  jmp     short loc_180008755
0x180008746  lea     eax, [r8+1]
0x18000874a  mov     [rdi+10h], eax
0x18000874d  jmp     short loc_180008755
0x18000874f  lea     eax, [rcx+1]
0x180008752  mov     [rdi+14h], eax
0x180008755  xor     eax, eax
0x180008757  add     rsp, 38h
0x18000875b  pop     r15
0x18000875d  pop     r14
0x18000875f  pop     r13
0x180008761  pop     r12
0x180008763  pop     rdi
0x180008764  pop     rsi
0x180008765  pop     rbp
0x180008766  pop     rbx
0x180008767  retn
```
