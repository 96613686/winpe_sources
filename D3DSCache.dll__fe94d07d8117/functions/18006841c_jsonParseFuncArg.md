# jsonParseFuncArg

- ea: `0x18006841c`
- end: `0x180068663`
- name: `jsonParseFuncArg`
- size: `583`
- prototype: ``
- caller_count: `8`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x1800655c0`
- `0x180066b00`
- `0x180067314`
- `0x1800686d0`
- `0x180068780`
- `0x180068a00`
- `0x18006a710`
- `0x18006aa50`

## callees

- `0x18002b8ec`
- `0x180042dc4`
- `0x180042e1c`
- `0x180045374`
- `0x180065330`
- `0x180065b88`
- `0x180065c34`
- `0x180065d04`
- `0x180065e14`
- `0x1800683e0`
- `0x18006841c`
- `0x180088e98`
- `0x18008c97c`
- `0x180094470`
- `0x180096df0`
- `0x180096e70`
- `0x1800a6d08`

## string_xrefs

- `0x18006860d`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonParseFuncArg(__int64 a1, __int64 a2, char a3)
{
  char v6; // si
  __int64 result; // rax
  __int64 v8; // rdi
  __int64 v9; // r12
  int *v10; // rax
  int *v11; // rbx
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

  v6 = *((_BYTE *)qword_1800B9DC0 + (*(_WORD *)(a2 + 20) & 0x3F));
  v22 = v6;
  if ( v6 == 5 )
    return 0;
  result = jsonCacheSearch();
  v8 = result;
  if ( !result || (++*(_DWORD *)(result + 36), (a3 & 1) != 0) )
  {
    v9 = sqlite3_context_db_handle(a1);
    while ( 1 )
    {
      v10 = (int *)sqlite3DbMallocZero(v9, 72);
      v11 = v10;
      if ( !v10 )
        goto LABEL_24;
      memset_0(v10, 0, 0x48u);
      *((_QWORD *)v11 + 3) = v9;
      v11[9] = 1;
      if ( v8 )
        break;
      if ( v6 == 4 && (unsigned int)jsonArgIsJsonb(a2, v11) )
      {
        if ( (a3 & 1) == 0 || (unsigned int)jsonBlobMakeEditable(v11, 0) )
          return (__int64)v11;
LABEL_24:
        jsonParseFree(v8);
        jsonParseFree(v11);
        sqlite3_result_error_nomem(a1);
        return 0;
      }
      LOBYTE(v12) = 1;
      v13 = sqlite3ValueText(a2, v12);
      LOBYTE(v14) = 1;
      *((_QWORD *)v11 + 2) = v13;
      v15 = sqlite3ValueBytes(a2, v14);
      v11[8] = v15;
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
        *((_BYTE *)v11 + 46) = 1;
        return (__int64)v11;
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
        && *(__int64 (__fastcall **)())(a2 + 48) == sqlite3RCStrUnref )
      {
        ++*(_QWORD *)(*((_QWORD *)v11 + 2) - 8LL);
      }
      else
      {
        v17 = (_BYTE *)sqlite3RCStrNew(v11[8]);
        v18 = v17;
        if ( !v17 )
          goto LABEL_24;
        memcpy_0(v17, *((const void **)v11 + 2), v11[8]);
        v19 = v11[8];
        *((_QWORD *)v11 + 2) = v18;
        v18[v19] = 0;
      }
      *((_BYTE *)v11 + 48) = 1;
      if ( (unsigned int)jsonCacheInsert(a1, v11) == 7 )
        goto LABEL_24;
      if ( (a3 & 1) == 0 )
        return (__int64)v11;
      v6 = v22;
      v8 = (__int64)v11;
    }
    v20 = *(_DWORD *)(v8 + 8);
    v21 = (void *)sqlite3DbMallocRaw(v9, v20);
    *(_QWORD *)v11 = v21;
    if ( v21 )
    {
      memcpy_0(v21, *(const void **)v8, v20);
      v11[2] = v20;
      v11[3] = v20;
      *((_BYTE *)v11 + 49) = *(_BYTE *)(v8 + 49);
      jsonParseFree(v8);
      return (__int64)v11;
    }
    goto LABEL_24;
  }
  return result;
}

```

## disassembly

```asm
0x18006841c  push    rbx
0x18006841e  push    rbp
0x18006841f  push    rsi
0x180068420  push    rdi
0x180068421  push    r12
0x180068423  push    r13
0x180068425  push    r14
0x180068427  push    r15
0x180068429  sub     rsp, 28h
0x18006842d  movzx   eax, word ptr [rdx+14h]
0x180068431  lea     rsi, qword_1800B9DC0
0x180068438  and     eax, 3Fh
0x18006843b  mov     r13d, r8d
0x18006843e  mov     r15, rdx
0x180068441  mov     r14, rcx
0x180068444  mov     sil, [rax+rsi]
0x180068448  mov     [rsp+68h+arg_8], sil
0x18006844d  cmp     sil, 5
0x180068451  jz      loc_1800685DC
0x180068457  call    jsonCacheSearch
0x18006845c  mov     ebp, r13d
0x18006845f  mov     rdi, rax
0x180068462  and     ebp, 1
0x180068465  test    rax, rax
0x180068468  jz      short loc_180068475
0x18006846a  inc     dword ptr [rax+24h]
0x18006846d  test    ebp, ebp
0x18006846f  jz      loc_1800685DE
0x180068475  mov     rcx, r14
0x180068478  call    sqlite3_context_db_handle
0x18006847d  mov     r12, rax
0x180068480  mov     edx, 48h ; 'H'
0x180068485  mov     rcx, r12
0x180068488  call    sqlite3DbMallocZero
0x18006848d  mov     rbx, rax
0x180068490  test    rax, rax
0x180068493  jz      loc_1800685C4
0x180068499  xor     edx, edx; Val
0x18006849b  mov     rcx, rax; void *
0x18006849e  lea     r8d, [rdx+48h]; Size
0x1800684a2  call    memset_0
0x1800684a7  mov     [rbx+18h], r12
0x1800684ab  mov     dword ptr [rbx+24h], 1
0x1800684b2  test    rdi, rdi
0x1800684b5  jnz     loc_180068624
0x1800684bb  cmp     sil, 4
0x1800684bf  jnz     short loc_1800684D4
0x1800684c1  mov     rdx, rbx
0x1800684c4  mov     rcx, r15
0x1800684c7  call    jsonArgIsJsonb
0x1800684cc  test    eax, eax
0x1800684ce  jnz     loc_1800685AA
0x1800684d4  mov     dl, 1
0x1800684d6  mov     rcx, r15
0x1800684d9  call    sqlite3ValueText
0x1800684de  mov     dl, 1
0x1800684e0  mov     [rbx+10h], rax
0x1800684e4  mov     rcx, r15
0x1800684e7  call    sqlite3ValueBytes
0x1800684ec  mov     [rbx+20h], eax
0x1800684ef  cmp     byte ptr [r12+67h], 0
0x1800684f5  jnz     loc_1800685C4
0x1800684fb  mov     esi, r13d
0x1800684fe  and     esi, 2
0x180068501  test    eax, eax
0x180068503  jz      loc_1800685FD
0x180068509  xor     edx, edx
0x18006850b  mov     rcx, rbx
0x18006850e  test    esi, esi
0x180068510  cmovz   rdx, r14
0x180068514  call    jsonConvertTextToBlob
0x180068519  test    eax, eax
0x18006851b  jnz     loc_1800685EF
0x180068521  movzx   eax, word ptr [r15+14h]
0x180068526  mov     edx, 0Ch
0x18006852b  test    al, 12h
0x18006852d  setnz   cl
0x180068530  bt      ax, dx
0x180068534  setb    al
0x180068537  test    al, cl
0x180068539  jz      short loc_180068552
0x18006853b  lea     rax, sqlite3RCStrUnref
0x180068542  cmp     [r15+30h], rax
0x180068546  jnz     short loc_180068552
0x180068548  mov     rax, [rbx+10h]
0x18006854c  inc     qword ptr [rax-8]
0x180068550  jmp     short loc_18006857F
0x180068552  movsxd  rcx, dword ptr [rbx+20h]
0x180068556  call    sqlite3RCStrNew
0x18006855b  mov     rsi, rax
0x18006855e  test    rax, rax
0x180068561  jz      short loc_1800685C4
0x180068563  movsxd  r8, dword ptr [rbx+20h]; Size
0x180068567  mov     rcx, rax; void *
0x18006856a  mov     rdx, [rbx+10h]; Src
0x18006856e  call    memcpy_0
0x180068573  movsxd  rcx, dword ptr [rbx+20h]
0x180068577  mov     [rbx+10h], rsi
0x18006857b  mov     byte ptr [rcx+rsi], 0
0x18006857f  mov     rdx, rbx
0x180068582  mov     byte ptr [rbx+30h], 1
0x180068586  mov     rcx, r14
0x180068589  call    jsonCacheInsert
0x18006858e  cmp     eax, 7
0x180068591  jz      short loc_1800685C4
0x180068593  test    r13b, 1
0x180068597  jz      loc_18006865B
0x18006859d  mov     sil, [rsp+68h+arg_8]
0x1800685a2  mov     rdi, rbx
0x1800685a5  jmp     loc_180068480
0x1800685aa  test    ebp, ebp
0x1800685ac  jz      loc_18006865B
0x1800685b2  xor     edx, edx
0x1800685b4  mov     rcx, rbx
0x1800685b7  call    jsonBlobMakeEditable
0x1800685bc  test    eax, eax
0x1800685be  jnz     loc_18006865B
0x1800685c4  mov     rcx, rdi
0x1800685c7  call    jsonParseFree
0x1800685cc  mov     rcx, rbx
0x1800685cf  call    jsonParseFree
0x1800685d4  mov     rcx, r14
0x1800685d7  call    sqlite3_result_error_nomem
0x1800685dc  xor     eax, eax
0x1800685de  add     rsp, 28h
0x1800685e2  pop     r15
0x1800685e4  pop     r14
0x1800685e6  pop     r13
0x1800685e8  pop     r12
0x1800685ea  pop     rdi
0x1800685eb  pop     rsi
0x1800685ec  pop     rbp
0x1800685ed  pop     rbx
0x1800685ee  retn
0x1800685ef  test    esi, esi
0x1800685f1  jnz     short loc_18006861E
0x1800685f3  mov     rcx, rbx
0x1800685f6  call    jsonParseFree
0x1800685fb  jmp     short loc_1800685DC
0x1800685fd  test    esi, esi
0x1800685ff  jnz     short loc_18006861E
0x180068601  mov     rcx, rbx
0x180068604  call    jsonParseFree
0x180068609  or      r8d, 0FFFFFFFFh
0x18006860d  lea     rdx, aMalformedJson; "malformed JSON"
0x180068614  mov     rcx, r14
0x180068617  call    sqlite3_result_error
0x18006861c  jmp     short loc_1800685DC
0x18006861e  mov     byte ptr [rbx+2Eh], 1
0x180068622  jmp     short loc_18006865B
0x180068624  mov     esi, [rdi+8]
0x180068627  mov     rcx, r12
0x18006862a  mov     edx, esi
0x18006862c  call    sqlite3DbMallocRaw
0x180068631  mov     [rbx], rax
0x180068634  test    rax, rax
0x180068637  jz      short loc_1800685C4
0x180068639  mov     rdx, [rdi]; Src
0x18006863c  mov     r8d, esi; Size
0x18006863f  mov     rcx, rax; void *
0x180068642  call    memcpy_0
0x180068647  mov     [rbx+8], esi
0x18006864a  mov     rcx, rdi
0x18006864d  mov     [rbx+0Ch], esi
0x180068650  mov     al, [rdi+31h]
0x180068653  mov     [rbx+31h], al
0x180068656  call    jsonParseFree
0x18006865b  mov     rax, rbx
0x18006865e  jmp     loc_1800685DE
```
