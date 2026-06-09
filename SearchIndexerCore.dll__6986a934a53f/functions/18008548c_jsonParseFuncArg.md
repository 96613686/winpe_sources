# jsonParseFuncArg

- ea: `0x18008548c`
- end: `0x1800856d3`
- name: `jsonParseFuncArg`
- size: `583`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x1800825d0`
- `0x180083b70`
- `0x180084384`
- `0x180085740`
- `0x1800857f0`
- `0x180085a70`
- `0x180087790`
- `0x180087a80`

## callees

- `0x180014c90`
- `0x180024b60`
- `0x18003d380`
- `0x180049d68`
- `0x180054ef4`
- `0x180070500`
- `0x180078968`
- `0x180082340`
- `0x180082b98`
- `0x180082cc4`
- `0x180082d94`
- `0x180082ea4`
- `0x180085450`
- `0x18008548c`
- `0x18009d650`
- `0x18009d6d0`
- `0x1800af620`

## string_xrefs

- `0x18008567d`: `malformed JSON`

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

  v6 = *((_BYTE *)qword_1800B5270 + (*(_WORD *)(a2 + 20) & 0x3F));
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
0x18008548c  push    rbx
0x18008548e  push    rbp
0x18008548f  push    rsi
0x180085490  push    rdi
0x180085491  push    r12
0x180085493  push    r13
0x180085495  push    r14
0x180085497  push    r15
0x180085499  sub     rsp, 28h
0x18008549d  movzx   eax, word ptr [rdx+14h]
0x1800854a1  lea     rsi, qword_1800B5270
0x1800854a8  and     eax, 3Fh
0x1800854ab  mov     r13d, r8d
0x1800854ae  mov     r15, rdx
0x1800854b1  mov     r14, rcx
0x1800854b4  mov     sil, [rax+rsi]
0x1800854b8  mov     [rsp+68h+arg_8], sil
0x1800854bd  cmp     sil, 5
0x1800854c1  jz      loc_18008564C
0x1800854c7  call    jsonCacheSearch
0x1800854cc  mov     ebp, r13d
0x1800854cf  mov     rdi, rax
0x1800854d2  and     ebp, 1
0x1800854d5  test    rax, rax
0x1800854d8  jz      short loc_1800854E5
0x1800854da  inc     dword ptr [rax+24h]
0x1800854dd  test    ebp, ebp
0x1800854df  jz      loc_18008564E
0x1800854e5  mov     rcx, r14
0x1800854e8  call    sqlite3_context_db_handle
0x1800854ed  mov     r12, rax
0x1800854f0  mov     edx, 48h ; 'H'
0x1800854f5  mov     rcx, r12
0x1800854f8  call    sqlite3DbMallocZero
0x1800854fd  mov     rbx, rax
0x180085500  test    rax, rax
0x180085503  jz      loc_180085634
0x180085509  xor     edx, edx; Val
0x18008550b  mov     rcx, rax; void *
0x18008550e  lea     r8d, [rdx+48h]; Size
0x180085512  call    memset_0
0x180085517  mov     [rbx+18h], r12
0x18008551b  mov     dword ptr [rbx+24h], 1
0x180085522  test    rdi, rdi
0x180085525  jnz     loc_180085694
0x18008552b  cmp     sil, 4
0x18008552f  jnz     short loc_180085544
0x180085531  mov     rdx, rbx
0x180085534  mov     rcx, r15
0x180085537  call    jsonArgIsJsonb
0x18008553c  test    eax, eax
0x18008553e  jnz     loc_18008561A
0x180085544  mov     dl, 1
0x180085546  mov     rcx, r15
0x180085549  call    sqlite3ValueText
0x18008554e  mov     dl, 1
0x180085550  mov     [rbx+10h], rax
0x180085554  mov     rcx, r15
0x180085557  call    sqlite3ValueBytes
0x18008555c  mov     [rbx+20h], eax
0x18008555f  cmp     byte ptr [r12+67h], 0
0x180085565  jnz     loc_180085634
0x18008556b  mov     esi, r13d
0x18008556e  and     esi, 2
0x180085571  test    eax, eax
0x180085573  jz      loc_18008566D
0x180085579  xor     edx, edx
0x18008557b  mov     rcx, rbx
0x18008557e  test    esi, esi
0x180085580  cmovz   rdx, r14
0x180085584  call    jsonConvertTextToBlob
0x180085589  test    eax, eax
0x18008558b  jnz     loc_18008565F
0x180085591  movzx   eax, word ptr [r15+14h]
0x180085596  mov     edx, 0Ch
0x18008559b  test    al, 12h
0x18008559d  setnz   cl
0x1800855a0  bt      ax, dx
0x1800855a4  setb    al
0x1800855a7  test    al, cl
0x1800855a9  jz      short loc_1800855C2
0x1800855ab  lea     rax, sqlite3RCStrUnref
0x1800855b2  cmp     [r15+30h], rax
0x1800855b6  jnz     short loc_1800855C2
0x1800855b8  mov     rax, [rbx+10h]
0x1800855bc  inc     qword ptr [rax-8]
0x1800855c0  jmp     short loc_1800855EF
0x1800855c2  movsxd  rcx, dword ptr [rbx+20h]
0x1800855c6  call    sqlite3RCStrNew
0x1800855cb  mov     rsi, rax
0x1800855ce  test    rax, rax
0x1800855d1  jz      short loc_180085634
0x1800855d3  movsxd  r8, dword ptr [rbx+20h]; Size
0x1800855d7  mov     rcx, rax; void *
0x1800855da  mov     rdx, [rbx+10h]; Src
0x1800855de  call    memcpy_0
0x1800855e3  movsxd  rcx, dword ptr [rbx+20h]
0x1800855e7  mov     [rbx+10h], rsi
0x1800855eb  mov     byte ptr [rcx+rsi], 0
0x1800855ef  mov     rdx, rbx
0x1800855f2  mov     byte ptr [rbx+30h], 1
0x1800855f6  mov     rcx, r14
0x1800855f9  call    jsonCacheInsert
0x1800855fe  cmp     eax, 7
0x180085601  jz      short loc_180085634
0x180085603  test    r13b, 1
0x180085607  jz      loc_1800856CB
0x18008560d  mov     sil, [rsp+68h+arg_8]
0x180085612  mov     rdi, rbx
0x180085615  jmp     loc_1800854F0
0x18008561a  test    ebp, ebp
0x18008561c  jz      loc_1800856CB
0x180085622  xor     edx, edx
0x180085624  mov     rcx, rbx
0x180085627  call    jsonBlobMakeEditable
0x18008562c  test    eax, eax
0x18008562e  jnz     loc_1800856CB
0x180085634  mov     rcx, rdi
0x180085637  call    jsonParseFree
0x18008563c  mov     rcx, rbx
0x18008563f  call    jsonParseFree
0x180085644  mov     rcx, r14
0x180085647  call    sqlite3_result_error_nomem
0x18008564c  xor     eax, eax
0x18008564e  add     rsp, 28h
0x180085652  pop     r15
0x180085654  pop     r14
0x180085656  pop     r13
0x180085658  pop     r12
0x18008565a  pop     rdi
0x18008565b  pop     rsi
0x18008565c  pop     rbp
0x18008565d  pop     rbx
0x18008565e  retn
0x18008565f  test    esi, esi
0x180085661  jnz     short loc_18008568E
0x180085663  mov     rcx, rbx
0x180085666  call    jsonParseFree
0x18008566b  jmp     short loc_18008564C
0x18008566d  test    esi, esi
0x18008566f  jnz     short loc_18008568E
0x180085671  mov     rcx, rbx
0x180085674  call    jsonParseFree
0x180085679  or      r8d, 0FFFFFFFFh
0x18008567d  lea     rdx, aMalformedJson; "malformed JSON"
0x180085684  mov     rcx, r14
0x180085687  call    sqlite3_result_error
0x18008568c  jmp     short loc_18008564C
0x18008568e  mov     byte ptr [rbx+2Eh], 1
0x180085692  jmp     short loc_1800856CB
0x180085694  mov     esi, [rdi+8]
0x180085697  mov     rcx, r12
0x18008569a  mov     edx, esi
0x18008569c  call    sqlite3DbMallocRaw
0x1800856a1  mov     [rbx], rax
0x1800856a4  test    rax, rax
0x1800856a7  jz      short loc_180085634
0x1800856a9  mov     rdx, [rdi]; Src
0x1800856ac  mov     r8d, esi; Size
0x1800856af  mov     rcx, rax; void *
0x1800856b2  call    memcpy_0
0x1800856b7  mov     [rbx+8], esi
0x1800856ba  mov     rcx, rdi
0x1800856bd  mov     [rbx+0Ch], esi
0x1800856c0  mov     al, [rdi+31h]
0x1800856c3  mov     [rbx+31h], al
0x1800856c6  call    jsonParseFree
0x1800856cb  mov     rax, rbx
0x1800856ce  jmp     loc_18008564E
```
