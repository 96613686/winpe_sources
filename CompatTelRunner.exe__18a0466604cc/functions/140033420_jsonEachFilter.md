# jsonEachFilter

- ea: `0x140033420`
- end: `0x140033702`
- name: `jsonEachFilter`
- size: `738`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x1400026c0`
- `0x1400333a0`
- `0x140033420`
- `0x140034114`
- `0x140034c00`
- `0x14003513c`
- `0x140073758`
- `0x14008ac90`
- `0x14008b820`
- `0x14008b8d0`
- `0x14008f900`
- `0x1400a7308`

## string_xrefs

- `0x14003352d`: `malformed JSON`
- `0x140033626`: `JSON path error near '%q'`

## pseudocode

```c
__int64 __fastcall jsonEachFilter(__int64 *a1, int a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  __int64 v7; // rdx
  _QWORD *v8; // r14
  _QWORD *v9; // rbx
  __int64 v10; // r8
  __int64 v11; // r15
  _QWORD *v12; // rax
  void *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // esi
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v19; // rcx
  _BYTE *v20; // rbx
  __int64 v21; // rbp
  void *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rdx
  unsigned __int8 v26; // al
  int v27; // eax
  __int64 v28; // rdx
  bool v29; // zf
  __int64 v30; // r8
  unsigned int v31; // edx
  _BYTE *v32; // [rsp+60h] [rbp+8h] BYREF

  ((void (*)(void))jsonEachCursorReset)();
  if ( !a2 )
    return 0;
  v8 = a5;
  LOBYTE(v7) = 1;
  v9 = (_QWORD *)sqlite3ValueText(*a5, v7);
  if ( !v9 )
    return 0;
  memset_0(a1 + 6, 0, 0x50u);
  *((_DWORD *)a1 + 26) = 1;
  v10 = *v8;
  if ( *v8
    && (*(_WORD *)(v10 + 20) & 0x12) != 0
    && (*(_WORD *)(v10 + 20) & 0x1000) != 0
    && *(__int64 (__fastcall **)())(v10 + 48) == sqlite3RCStrUnref )
  {
    ++*(v9 - 1);
    a1[8] = (__int64)v9;
  }
  else
  {
    v11 = (int)sqlite3_value_bytes(*v8);
    v12 = (_QWORD *)sqlite3_malloc64(v11 + 10);
    if ( v12 )
    {
      *v12 = 1;
      v13 = v12 + 1;
    }
    else
    {
      v13 = 0;
    }
    a1[8] = (__int64)v13;
    if ( !v13 )
      return 7;
    memcpy_0(v13, v9, v11 + 1);
  }
  a1[4] = a1[8];
  *((_BYTE *)a1 + 100) = 1;
  if ( (unsigned int)jsonParse(a1 + 6, 0) )
  {
    v15 = 7;
    if ( !*((_BYTE *)a1 + 99) )
    {
      sqlite3_free(*(_QWORD *)(*a1 + 16));
      v16 = *a1;
      *(_QWORD *)(v16 + 16) = sqlite3_mprintf("malformed JSON");
      if ( *(_QWORD *)(*a1 + 16) )
        v15 = 1;
    }
    goto LABEL_20;
  }
  if ( *((_BYTE *)a1 + 25) )
  {
    v17 = sqlite3_malloc64(4LL * *((unsigned int *)a1 + 12));
    a1[10] = v17;
    if ( !v17 )
    {
      *((_BYTE *)a1 + 99) = 1;
      v15 = 7;
LABEL_20:
      jsonEachCursorReset(a1);
      return v15;
    }
    jsonParseFillInParentage(a1 + 6, 0, 0);
  }
  if ( a2 != 3 )
  {
    v23 = a1[7];
LABEL_33:
    v25 = (v23 - a1[7]) >> 4;
    *((_DWORD *)a1 + 4) = v25;
    *((_DWORD *)a1 + 3) = v25;
    v26 = *(_BYTE *)v23;
    *((_BYTE *)a1 + 24) = *(_BYTE *)v23;
    if ( v26 < 7u )
    {
      *((_DWORD *)a1 + 5) = v25 + 1;
    }
    else
    {
      v27 = *(_DWORD *)(v23 + 4);
      *(_DWORD *)(v23 + 8) = 0;
      v28 = *((unsigned int *)a1 + 4);
      v29 = *((_BYTE *)a1 + 25) == 0;
      *((_DWORD *)a1 + 5) = v27 + v28 + 1;
      if ( v29 )
      {
        *((_DWORD *)a1 + 4) = v28 + 1;
      }
      else
      {
        v30 = a1[7];
        *((_BYTE *)a1 + 24) = *(_BYTE *)(v30 + 16LL * *(unsigned int *)(a1[10] + 4 * v28));
        if ( (_DWORD)v28 )
        {
          v31 = v28 - 1;
          if ( (*(_BYTE *)(v30 + 16LL * v31 + 1) & 0x20) != 0 )
            *((_DWORD *)a1 + 4) = v31;
        }
      }
    }
    return 0;
  }
  v19 = v8[1];
  LOBYTE(v14) = 1;
  v32 = 0;
  v20 = (_BYTE *)sqlite3ValueText(v19, v14);
  if ( !v20 )
    return 0;
  v21 = (int)sqlite3_value_bytes(v8[1]);
  v22 = (void *)sqlite3_malloc64(v21 + 1);
  a1[5] = (__int64)v22;
  if ( v22 )
  {
    memcpy_0(v22, v20, v21 + 1);
    if ( *v20 == 36 )
    {
      v24 = jsonLookupStep((int)a1 + 48, 0, *((_DWORD *)a1 + 10) + 1, 0, (__int64)&v32);
      v20 = v32;
      v23 = v24;
    }
    else
    {
      v23 = 0;
    }
    if ( v20 )
    {
      sqlite3_free(*(_QWORD *)(*a1 + 16));
      *(_QWORD *)(*a1 + 16) = sqlite3_mprintf("JSON path error near '%q'", v20);
      jsonEachCursorReset(a1);
      return *(_QWORD *)(*a1 + 16) != 0 ? 1 : 7;
    }
    if ( !v23 )
      return 0;
    goto LABEL_33;
  }
  return 7;
}

```

## disassembly

```asm
0x140033420  mov     [rsp+arg_8], rbx
0x140033425  mov     [rsp+arg_10], rbp
0x14003342a  push    rsi
0x14003342b  push    rdi
0x14003342c  push    r13
0x14003342e  push    r14
0x140033430  push    r15
0x140033432  sub     rsp, 30h
0x140033436  mov     ebp, edx
0x140033438  mov     rdi, rcx
0x14003343b  call    jsonEachCursorReset
0x140033440  test    ebp, ebp
0x140033442  jz      loc_14003365A
0x140033448  mov     r14, [rsp+58h+arg_20]
0x140033450  mov     r13d, 1
0x140033456  mov     dl, r13b
0x140033459  mov     rcx, [r14]
0x14003345c  call    sqlite3ValueText
0x140033461  mov     rbx, rax
0x140033464  test    rax, rax
0x140033467  jz      loc_14003365A
0x14003346d  lea     rsi, [rdi+30h]
0x140033471  xor     edx, edx; Val
0x140033473  mov     rcx, rsi; void *
0x140033476  lea     r8d, [r13+4Fh]; Size
0x14003347a  call    memset_0
0x14003347f  mov     [rdi+68h], r13d
0x140033483  mov     r8, [r14]
0x140033486  test    r8, r8
0x140033489  jz      short loc_1400334BC
0x14003348b  movzx   edx, word ptr [r8+14h]
0x140033490  lea     eax, [r13+0Bh]
0x140033494  test    dl, 12h
0x140033497  setnz   cl
0x14003349a  bt      dx, ax
0x14003349e  setb    al
0x1400334a1  test    al, cl
0x1400334a3  jz      short loc_1400334BC
0x1400334a5  lea     rax, sqlite3RCStrUnref
0x1400334ac  cmp     [r8+30h], rax
0x1400334b0  jnz     short loc_1400334BC
0x1400334b2  add     [rbx-8], r13
0x1400334b6  mov     [rdi+40h], rbx
0x1400334ba  jmp     short loc_1400334F9
0x1400334bc  mov     rcx, r8
0x1400334bf  call    sqlite3_value_bytes
0x1400334c4  movsxd  r15, eax
0x1400334c7  lea     rcx, [r15+0Ah]
0x1400334cb  call    sqlite3_malloc64
0x1400334d0  test    rax, rax
0x1400334d3  jnz     short loc_1400334D9
0x1400334d5  xor     ecx, ecx
0x1400334d7  jmp     short loc_1400334E0
0x1400334d9  mov     [rax], r13
0x1400334dc  lea     rcx, [rax+8]; void *
0x1400334e0  mov     [rdi+40h], rcx
0x1400334e4  test    rcx, rcx
0x1400334e7  jz      loc_1400336F8
0x1400334ed  lea     r8, [r15+1]; Size
0x1400334f1  mov     rdx, rbx; Src
0x1400334f4  call    memcpy_0
0x1400334f9  mov     rax, [rdi+40h]
0x1400334fd  xor     edx, edx
0x1400334ff  mov     rcx, rsi
0x140033502  mov     [rdi+20h], rax
0x140033506  mov     [rdi+64h], r13b
0x14003350a  call    jsonParse
0x14003350f  test    eax, eax
0x140033511  jz      short loc_14003354B
0x140033513  cmp     byte ptr [rdi+63h], 0
0x140033517  mov     esi, 7
0x14003351c  jnz     short loc_14003356C
0x14003351e  mov     rcx, [rdi]
0x140033521  mov     rcx, [rcx+10h]
0x140033525  call    sqlite3_free
0x14003352a  mov     rbx, [rdi]
0x14003352d  lea     rcx, aMalformedJson; "malformed JSON"
0x140033534  call    sqlite3_mprintf
0x140033539  mov     [rbx+10h], rax
0x14003353d  mov     rax, [rdi]
0x140033540  cmp     qword ptr [rax+10h], 0
0x140033545  cmovnz  esi, r13d
0x140033549  jmp     short loc_14003356C
0x14003354b  cmp     byte ptr [rdi+19h], 0
0x14003354f  jz      short loc_140033588
0x140033551  mov     ecx, [rsi]
0x140033553  shl     rcx, 2
0x140033557  call    sqlite3_malloc64
0x14003355c  mov     [rsi+20h], rax
0x140033560  test    rax, rax
0x140033563  jnz     short loc_14003357B
0x140033565  mov     [rsi+33h], r13b
0x140033569  lea     esi, [rax+7]
0x14003356c  mov     rcx, rdi
0x14003356f  call    jsonEachCursorReset
0x140033574  mov     eax, esi
0x140033576  jmp     loc_14003365C
0x14003357b  xor     r8d, r8d
0x14003357e  xor     edx, edx
0x140033580  mov     rcx, rsi
0x140033583  call    jsonParseFillInParentage
0x140033588  cmp     ebp, 3
0x14003358b  jnz     loc_140033673
0x140033591  mov     rcx, [r14+8]
0x140033595  mov     dl, r13b
0x140033598  mov     [rsp+58h+arg_0], 0
0x1400335a1  call    sqlite3ValueText
0x1400335a6  mov     rbx, rax
0x1400335a9  test    rax, rax
0x1400335ac  jz      loc_14003365A
0x1400335b2  mov     rcx, [r14+8]
0x1400335b6  call    sqlite3_value_bytes
0x1400335bb  movsxd  rbp, eax
0x1400335be  lea     rcx, [rbp+1]
0x1400335c2  call    sqlite3_malloc64
0x1400335c7  mov     [rdi+28h], rax
0x1400335cb  test    rax, rax
0x1400335ce  jz      loc_1400336F8
0x1400335d4  lea     r8, [rbp+1]; Size
0x1400335d8  mov     rdx, rbx; Src
0x1400335db  mov     rcx, rax; void *
0x1400335de  call    memcpy_0
0x1400335e3  cmp     byte ptr [rbx], 24h ; '$'
0x1400335e6  jz      short loc_1400335EC
0x1400335e8  xor     ecx, ecx
0x1400335ea  jmp     short loc_140033612
0x1400335ec  mov     r8, [rdi+28h]
0x1400335f0  lea     rax, [rsp+58h+arg_0]
0x1400335f5  add     r8, r13
0x1400335f8  mov     [rsp+58h+var_38], rax
0x1400335fd  xor     r9d, r9d
0x140033600  xor     edx, edx
0x140033602  mov     rcx, rsi
0x140033605  call    jsonLookupStep
0x14003360a  mov     rbx, [rsp+58h+arg_0]
0x14003360f  mov     rcx, rax
0x140033612  test    rbx, rbx
0x140033615  jz      short loc_140033655
0x140033617  mov     rcx, [rdi]
0x14003361a  mov     rcx, [rcx+10h]
0x14003361e  call    sqlite3_free
0x140033623  mov     rdx, rbx
0x140033626  lea     rcx, aJsonPathErrorN; "JSON path error near '%q'"
0x14003362d  call    sqlite3_mprintf
0x140033632  mov     rcx, [rdi]
0x140033635  mov     [rcx+10h], rax
0x140033639  mov     rcx, rdi
0x14003363c  call    jsonEachCursorReset
0x140033641  mov     rax, [rdi]
0x140033644  mov     rcx, [rax+10h]
0x140033648  neg     rcx
0x14003364b  sbb     eax, eax
0x14003364d  and     eax, 0FFFFFFFAh
0x140033650  add     eax, 7
0x140033653  jmp     short loc_14003365C
0x140033655  test    rcx, rcx
0x140033658  jnz     short loc_140033677
0x14003365a  xor     eax, eax
0x14003365c  mov     rbx, [rsp+58h+arg_8]
0x140033661  mov     rbp, [rsp+58h+arg_10]
0x140033666  add     rsp, 30h
0x14003366a  pop     r15
0x14003366c  pop     r14
0x14003366e  pop     r13
0x140033670  pop     rdi
0x140033671  pop     rsi
0x140033672  retn
0x140033673  mov     rcx, [rdi+38h]
0x140033677  mov     rdx, rcx
0x14003367a  mov     esi, 7
0x14003367f  sub     rdx, [rdi+38h]
0x140033683  sar     rdx, 4
0x140033687  mov     [rdi+10h], edx
0x14003368a  mov     [rdi+0Ch], edx
0x14003368d  mov     al, [rcx]
0x14003368f  mov     [rdi+18h], al
0x140033692  cmp     al, sil
0x140033695  jb      short loc_1400336ED
0x140033697  mov     eax, [rcx+4]
0x14003369a  mov     dword ptr [rcx+8], 0
0x1400336a1  mov     edx, [rdi+10h]
0x1400336a4  lea     ecx, [rdx+1]
0x1400336a7  add     ecx, eax
0x1400336a9  cmp     byte ptr [rdi+19h], 0
0x1400336ad  mov     [rdi+14h], ecx
0x1400336b0  jz      short loc_1400336E2
0x1400336b2  mov     rax, [rdi+50h]
0x1400336b6  mov     r8, [rdi+38h]
0x1400336ba  mov     eax, [rax+rdx*4]
0x1400336bd  add     rax, rax
0x1400336c0  mov     al, [r8+rax*8]
0x1400336c4  mov     [rdi+18h], al
0x1400336c7  test    edx, edx
0x1400336c9  jz      short loc_14003365A
0x1400336cb  dec     edx
0x1400336cd  mov     eax, edx
0x1400336cf  add     rax, rax
0x1400336d2  test    byte ptr [r8+rax*8+1], 20h
0x1400336d8  jz      short loc_14003365A
0x1400336da  mov     [rdi+10h], edx
0x1400336dd  jmp     loc_14003365A
0x1400336e2  lea     eax, [rdx+1]
0x1400336e5  mov     [rdi+10h], eax
0x1400336e8  jmp     loc_14003365A
0x1400336ed  lea     eax, [rdx+1]
0x1400336f0  mov     [rdi+14h], eax
0x1400336f3  jmp     loc_14003365A
0x1400336f8  mov     eax, 7
0x1400336fd  jmp     loc_14003365C
```
