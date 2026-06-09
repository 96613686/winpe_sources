# jsonParseFuncArg

- ea: `0x18007627c`
- end: `0x1800764c3`
- name: `jsonParseFuncArg`
- size: `583`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `8`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x180073360`
- `0x180074920`
- `0x180075144`
- `0x180076530`
- `0x1800765e0`
- `0x180076860`
- `0x180078580`
- `0x180078870`

## callees

- `0x18000f720`
- `0x180010c34`
- `0x180028540`
- `0x180048d20`
- `0x180048d38`
- `0x1800623c8`
- `0x180068190`
- `0x18006910e`
- `0x1800730d8`
- `0x180073928`
- `0x180073a54`
- `0x180073b24`
- `0x180073c34`
- `0x180076240`
- `0x18007627c`
- `0x18008f3f0`
- `0x180099814`

## string_xrefs

- `0x18007646d`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonParseFuncArg(__int64 a1, __int64 a2, char a3)
{
  char v6; // si
  __int64 result; // rax
  __int64 v8; // rdi
  __int64 v9; // r12
  void *v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rdx
  _BYTE *v17; // rax
  _BYTE *v18; // rsi
  __int64 v19; // rcx
  unsigned int v20; // esi
  void *v21; // rax
  char v22; // [rsp+78h] [rbp+10h]

  v6 = *((_BYTE *)qword_18009EC50 + (*(_WORD *)(a2 + 20) & 0x3F));
  v22 = v6;
  if ( v6 == 5 )
    return 0;
  result = jsonCacheSearch(a1, a2);
  v8 = result;
  if ( !result || (++*(_DWORD *)(result + 36), (a3 & 1) != 0) )
  {
    v9 = sqlite3_context_db_handle(a1);
    while ( 1 )
    {
      v10 = (void *)sqlite3DbMallocZero(v9, 72);
      v11 = (__int64)v10;
      if ( !v10 )
        goto LABEL_24;
      memset_0(v10, 0, 0x48u);
      *(_QWORD *)(v11 + 24) = v9;
      *(_DWORD *)(v11 + 36) = 1;
      if ( v8 )
        break;
      if ( v6 == 4 && (unsigned int)jsonArgIsJsonb(a2, v11) )
      {
        if ( (a3 & 1) == 0 || (unsigned int)jsonBlobMakeEditable(v11, 0) )
          return v11;
LABEL_24:
        jsonParseFree(v8);
        jsonParseFree(v11);
        sqlite3_result_error_nomem(a1);
        return 0;
      }
      LOBYTE(v12) = 1;
      v13 = sqlite3ValueText(a2, v12);
      LOBYTE(v14) = 1;
      *(_QWORD *)(v11 + 16) = v13;
      v15 = sqlite3ValueBytes(a2, v14);
      *(_DWORD *)(v11 + 32) = v15;
      if ( *(_BYTE *)(v9 + 103) )
        goto LABEL_24;
      if ( !v15 )
      {
        if ( (a3 & 2) == 0 )
        {
          jsonParseFree(v11);
          sqlite3_result_error(a1, "malformed JSON", 0xFFFFFFFFLL);
          return 0;
        }
LABEL_31:
        *(_BYTE *)(v11 + 46) = 1;
        return v11;
      }
      v16 = 0;
      if ( (a3 & 2) == 0 )
        v16 = a1;
      if ( (unsigned int)jsonConvertTextToBlob(v11, v16) )
      {
        if ( (a3 & 2) == 0 )
        {
          jsonParseFree(v11);
          return 0;
        }
        goto LABEL_31;
      }
      if ( (*(_WORD *)(a2 + 20) & 0x12) != 0
        && (*(_WORD *)(a2 + 20) & 0x1000) != 0
        && *(__int64 (__fastcall **)(_QWORD))(a2 + 48) == sqlite3RCStrUnref )
      {
        ++*(_QWORD *)(*(_QWORD *)(v11 + 16) - 8LL);
      }
      else
      {
        v17 = (_BYTE *)sqlite3RCStrNew(*(int *)(v11 + 32));
        v18 = v17;
        if ( !v17 )
          goto LABEL_24;
        memcpy_0(v17, *(const void **)(v11 + 16), *(int *)(v11 + 32));
        v19 = *(int *)(v11 + 32);
        *(_QWORD *)(v11 + 16) = v18;
        v18[v19] = 0;
      }
      *(_BYTE *)(v11 + 48) = 1;
      if ( (unsigned int)jsonCacheInsert(a1, v11) == 7 )
        goto LABEL_24;
      if ( (a3 & 1) == 0 )
        return v11;
      v6 = v22;
      v8 = v11;
    }
    v20 = *(_DWORD *)(v8 + 8);
    v21 = (void *)sqlite3DbMallocRaw(v9, v20);
    *(_QWORD *)v11 = v21;
    if ( v21 )
    {
      memcpy_0(v21, *(const void **)v8, v20);
      *(_DWORD *)(v11 + 8) = v20;
      *(_DWORD *)(v11 + 12) = v20;
      *(_BYTE *)(v11 + 49) = *(_BYTE *)(v8 + 49);
      jsonParseFree(v8);
      return v11;
    }
    goto LABEL_24;
  }
  return result;
}

```

## disassembly

```asm
0x18007627c  push    rbx
0x18007627e  push    rbp
0x18007627f  push    rsi
0x180076280  push    rdi
0x180076281  push    r12
0x180076283  push    r13
0x180076285  push    r14
0x180076287  push    r15
0x180076289  sub     rsp, 28h
0x18007628d  movzx   eax, word ptr [rdx+14h]
0x180076291  lea     rsi, qword_18009EC50
0x180076298  and     eax, 3Fh
0x18007629b  mov     r13d, r8d
0x18007629e  mov     r15, rdx
0x1800762a1  mov     r14, rcx
0x1800762a4  mov     sil, [rax+rsi]
0x1800762a8  mov     [rsp+68h+arg_8], sil
0x1800762ad  cmp     sil, 5
0x1800762b1  jz      loc_18007643C
0x1800762b7  call    jsonCacheSearch
0x1800762bc  mov     ebp, r13d
0x1800762bf  mov     rdi, rax
0x1800762c2  and     ebp, 1
0x1800762c5  test    rax, rax
0x1800762c8  jz      short loc_1800762D5
0x1800762ca  inc     dword ptr [rax+24h]
0x1800762cd  test    ebp, ebp
0x1800762cf  jz      loc_18007643E
0x1800762d5  mov     rcx, r14
0x1800762d8  call    sqlite3_context_db_handle
0x1800762dd  mov     r12, rax
0x1800762e0  mov     edx, 48h ; 'H'
0x1800762e5  mov     rcx, r12
0x1800762e8  call    sqlite3DbMallocZero
0x1800762ed  mov     rbx, rax
0x1800762f0  test    rax, rax
0x1800762f3  jz      loc_180076424
0x1800762f9  xor     edx, edx; Val
0x1800762fb  mov     rcx, rax; void *
0x1800762fe  lea     r8d, [rdx+48h]; Size
0x180076302  call    memset_0
0x180076307  mov     [rbx+18h], r12
0x18007630b  mov     dword ptr [rbx+24h], 1
0x180076312  test    rdi, rdi
0x180076315  jnz     loc_180076484
0x18007631b  cmp     sil, 4
0x18007631f  jnz     short loc_180076334
0x180076321  mov     rdx, rbx
0x180076324  mov     rcx, r15
0x180076327  call    jsonArgIsJsonb
0x18007632c  test    eax, eax
0x18007632e  jnz     loc_18007640A
0x180076334  mov     dl, 1
0x180076336  mov     rcx, r15
0x180076339  call    sqlite3ValueText
0x18007633e  mov     dl, 1
0x180076340  mov     [rbx+10h], rax
0x180076344  mov     rcx, r15
0x180076347  call    sqlite3ValueBytes
0x18007634c  mov     [rbx+20h], eax
0x18007634f  cmp     byte ptr [r12+67h], 0
0x180076355  jnz     loc_180076424
0x18007635b  mov     esi, r13d
0x18007635e  and     esi, 2
0x180076361  test    eax, eax
0x180076363  jz      loc_18007645D
0x180076369  xor     edx, edx
0x18007636b  mov     rcx, rbx
0x18007636e  test    esi, esi
0x180076370  cmovz   rdx, r14
0x180076374  call    jsonConvertTextToBlob
0x180076379  test    eax, eax
0x18007637b  jnz     loc_18007644F
0x180076381  movzx   eax, word ptr [r15+14h]
0x180076386  mov     edx, 0Ch
0x18007638b  test    al, 12h
0x18007638d  setnz   cl
0x180076390  bt      ax, dx
0x180076394  setb    al
0x180076397  test    al, cl
0x180076399  jz      short loc_1800763B2
0x18007639b  lea     rax, sqlite3RCStrUnref
0x1800763a2  cmp     [r15+30h], rax
0x1800763a6  jnz     short loc_1800763B2
0x1800763a8  mov     rax, [rbx+10h]
0x1800763ac  inc     qword ptr [rax-8]
0x1800763b0  jmp     short loc_1800763DF
0x1800763b2  movsxd  rcx, dword ptr [rbx+20h]
0x1800763b6  call    sqlite3RCStrNew
0x1800763bb  mov     rsi, rax
0x1800763be  test    rax, rax
0x1800763c1  jz      short loc_180076424
0x1800763c3  movsxd  r8, dword ptr [rbx+20h]; Size
0x1800763c7  mov     rcx, rax; void *
0x1800763ca  mov     rdx, [rbx+10h]; Src
0x1800763ce  call    memcpy_0
0x1800763d3  movsxd  rcx, dword ptr [rbx+20h]
0x1800763d7  mov     [rbx+10h], rsi
0x1800763db  mov     byte ptr [rcx+rsi], 0
0x1800763df  mov     rdx, rbx
0x1800763e2  mov     byte ptr [rbx+30h], 1
0x1800763e6  mov     rcx, r14
0x1800763e9  call    jsonCacheInsert
0x1800763ee  cmp     eax, 7
0x1800763f1  jz      short loc_180076424
0x1800763f3  test    r13b, 1
0x1800763f7  jz      loc_1800764BB
0x1800763fd  mov     sil, [rsp+68h+arg_8]
0x180076402  mov     rdi, rbx
0x180076405  jmp     loc_1800762E0
0x18007640a  test    ebp, ebp
0x18007640c  jz      loc_1800764BB
0x180076412  xor     edx, edx
0x180076414  mov     rcx, rbx
0x180076417  call    jsonBlobMakeEditable
0x18007641c  test    eax, eax
0x18007641e  jnz     loc_1800764BB
0x180076424  mov     rcx, rdi
0x180076427  call    jsonParseFree
0x18007642c  mov     rcx, rbx
0x18007642f  call    jsonParseFree
0x180076434  mov     rcx, r14
0x180076437  call    sqlite3_result_error_nomem
0x18007643c  xor     eax, eax
0x18007643e  add     rsp, 28h
0x180076442  pop     r15
0x180076444  pop     r14
0x180076446  pop     r13
0x180076448  pop     r12
0x18007644a  pop     rdi
0x18007644b  pop     rsi
0x18007644c  pop     rbp
0x18007644d  pop     rbx
0x18007644e  retn
0x18007644f  test    esi, esi
0x180076451  jnz     short loc_18007647E
0x180076453  mov     rcx, rbx
0x180076456  call    jsonParseFree
0x18007645b  jmp     short loc_18007643C
0x18007645d  test    esi, esi
0x18007645f  jnz     short loc_18007647E
0x180076461  mov     rcx, rbx
0x180076464  call    jsonParseFree
0x180076469  or      r8d, 0FFFFFFFFh
0x18007646d  lea     rdx, aMalformedJson; "malformed JSON"
0x180076474  mov     rcx, r14
0x180076477  call    sqlite3_result_error
0x18007647c  jmp     short loc_18007643C
0x18007647e  mov     byte ptr [rbx+2Eh], 1
0x180076482  jmp     short loc_1800764BB
0x180076484  mov     esi, [rdi+8]
0x180076487  mov     rcx, r12
0x18007648a  mov     edx, esi
0x18007648c  call    sqlite3DbMallocRaw
0x180076491  mov     [rbx], rax
0x180076494  test    rax, rax
0x180076497  jz      short loc_180076424
0x180076499  mov     rdx, [rdi]; Src
0x18007649c  mov     r8d, esi; Size
0x18007649f  mov     rcx, rax; void *
0x1800764a2  call    memcpy_0
0x1800764a7  mov     [rbx+8], esi
0x1800764aa  mov     rcx, rdi
0x1800764ad  mov     [rbx+0Ch], esi
0x1800764b0  mov     al, [rdi+31h]
0x1800764b3  mov     [rbx+31h], al
0x1800764b6  call    jsonParseFree
0x1800764bb  mov     rax, rbx
0x1800764be  jmp     loc_18007643E
```
