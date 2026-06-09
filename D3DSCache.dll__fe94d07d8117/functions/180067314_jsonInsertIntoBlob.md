# jsonInsertIntoBlob

- ea: `0x180067314`
- end: `0x1800674b8`
- name: `jsonInsertIntoBlob`
- size: `420`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180068ae0`
- `0x180069270`

## callees

- `0x180042dc4`
- `0x180045374`
- `0x180065750`
- `0x180065a04`
- `0x180066f98`
- `0x180067314`
- `0x1800676c0`
- `0x1800683e0`
- `0x18006841c`
- `0x18006866c`
- `0x180068f04`
- `0x180096df0`
- `0x180096e70`

## string_xrefs

- `0x18006746f`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonInsertIntoBlob(__int64 a1, int a2, __int64 *a3, int a4)
{
  __int64 result; // rax
  __int64 v8; // rbx
  int v9; // esi
  int v10; // r13d
  int i; // r14d
  __int64 *v12; // rdx
  __int64 v13; // rcx
  _BYTE *v14; // rax
  _BYTE *v15; // rbp
  __int64 v16; // [rsp+30h] [rbp-98h] BYREF
  int v17; // [rsp+38h] [rbp-90h]

  memset_0(&v16, 0, 0x48u);
  result = jsonParseFuncArg(a1, *a3, a2 != 1);
  v8 = result;
  if ( result )
  {
    v9 = 0;
    v10 = a2 - 1;
    for ( i = 1; ; i += 2 )
    {
      if ( i >= v10 )
      {
        jsonReturnParse(a1, v8);
        return jsonParseFree(v8);
      }
      v12 = qword_1800B9DC0;
      v13 = a3[i];
      if ( *((_BYTE *)qword_1800B9DC0 + (*(_WORD *)(v13 + 20) & 0x3F)) != 5 )
      {
        LOBYTE(v12) = 1;
        v14 = (_BYTE *)sqlite3ValueText(v13, v12);
        v15 = v14;
        if ( !v14 )
        {
          sqlite3_result_error_nomem(a1);
          return jsonParseFree(v8);
        }
        if ( *v14 != 36 )
          break;
        if ( (unsigned int)jsonFunctionArgToBlob(a1, a3[i + 1], &v16) )
        {
          jsonParseReset(&v16);
          return jsonParseFree(v8);
        }
        if ( v15[1] )
        {
          *(_BYTE *)(v8 + 51) = a4;
          *(_DWORD *)(v8 + 56) = v17;
          *(_QWORD *)(v8 + 64) = v16;
          *(_DWORD *)(v8 + 52) = 0;
          v9 = jsonLookupStep(v8, 0, v15 + 1, 0);
        }
        else
        {
          if ( ((a4 - 2) & 0xFFFFFFFD) == 0 )
            jsonBlobEdit(v8, 0, *(unsigned int *)(v8 + 8), v16, v17);
          v9 = 0;
        }
        jsonParseReset(&v16);
        if ( ((v9 + 3) & 0xFFFFFFFD) == 0 )
          break;
      }
    }
    jsonParseFree(v8);
    if ( v9 == -1 )
      return sqlite3_result_error(a1, "malformed JSON", 0xFFFFFFFFLL);
    else
      return jsonBadPathError(a1, v15);
  }
  return result;
}

```

## disassembly

```asm
0x180067314  mov     [rsp+arg_18], r9d
0x180067319  push    rbx
0x18006731a  push    rbp
0x18006731b  push    rsi
0x18006731c  push    rdi
0x18006731d  push    r12
0x18006731f  push    r13
0x180067321  push    r14
0x180067323  push    r15
0x180067325  sub     rsp, 88h
0x18006732c  mov     ebp, edx
0x18006732e  mov     r12, r8
0x180067331  xor     edx, edx; Val
0x180067333  mov     rdi, rcx
0x180067336  lea     rcx, [rsp+0C8h+var_98]; void *
0x18006733b  lea     r8d, [rdx+48h]; Size
0x18006733f  call    memset_0
0x180067344  mov     rdx, [r12]
0x180067348  xor     r8d, r8d
0x18006734b  cmp     ebp, 1
0x18006734e  mov     rcx, rdi
0x180067351  setnz   r8b
0x180067355  call    jsonParseFuncArg
0x18006735a  mov     rbx, rax
0x18006735d  test    rax, rax
0x180067360  jz      loc_1800674A4
0x180067366  xor     esi, esi
0x180067368  lea     r13d, [rbp-1]
0x18006736c  lea     r14d, [rsi+1]
0x180067370  cmp     r14d, r13d
0x180067373  jge     loc_180067491
0x180067379  movsxd  r15, r14d
0x18006737c  lea     rdx, qword_1800B9DC0
0x180067383  mov     rcx, [r12+r15*8]
0x180067387  movzx   eax, word ptr [rcx+14h]
0x18006738b  and     eax, 3Fh
0x18006738e  cmp     byte ptr [rax+rdx], 5
0x180067392  jz      loc_180067446
0x180067398  mov     dl, 1
0x18006739a  call    sqlite3ValueText
0x18006739f  mov     rbp, rax
0x1800673a2  test    rax, rax
0x1800673a5  jz      loc_180067487
0x1800673ab  cmp     byte ptr [rax], 24h ; '$'
0x1800673ae  jnz     loc_18006745B
0x1800673b4  mov     rdx, [r12+r15*8+8]
0x1800673b9  lea     r8, [rsp+0C8h+var_98]
0x1800673be  mov     rcx, rdi
0x1800673c1  call    jsonFunctionArgToBlob
0x1800673c6  test    eax, eax
0x1800673c8  jnz     loc_18006744F
0x1800673ce  mov     eax, [rsp+0C8h+arg_18]
0x1800673d5  lea     r8, [rbp+1]
0x1800673d9  cmp     byte ptr [r8], 0
0x1800673dd  jnz     short loc_180067408
0x1800673df  add     eax, 0FFFFFFFEh
0x1800673e2  test    eax, 0FFFFFFFDh
0x1800673e7  jnz     short loc_180067404
0x1800673e9  mov     eax, [rsp+0C8h+var_90]
0x1800673ed  xor     edx, edx
0x1800673ef  mov     r9, [rsp+0C8h+var_98]
0x1800673f4  mov     rcx, rbx
0x1800673f7  mov     r8d, [rbx+8]
0x1800673fb  mov     [rsp+0C8h+var_A8], eax
0x1800673ff  call    jsonBlobEdit
0x180067404  xor     esi, esi
0x180067406  jmp     short loc_180067431
0x180067408  mov     [rbx+33h], al
0x18006740b  xor     r9d, r9d
0x18006740e  mov     eax, [rsp+0C8h+var_90]
0x180067412  xor     edx, edx
0x180067414  mov     [rbx+38h], eax
0x180067417  mov     rcx, rbx
0x18006741a  mov     rax, [rsp+0C8h+var_98]
0x18006741f  mov     [rbx+40h], rax
0x180067423  mov     dword ptr [rbx+34h], 0
0x18006742a  call    jsonLookupStep
0x18006742f  mov     esi, eax
0x180067431  lea     rcx, [rsp+0C8h+var_98]
0x180067436  call    jsonParseReset
0x18006743b  lea     ecx, [rsi+3]
0x18006743e  test    ecx, 0FFFFFFFDh
0x180067444  jz      short loc_18006745B
0x180067446  add     r14d, 2
0x18006744a  jmp     loc_180067370
0x18006744f  lea     rcx, [rsp+0C8h+var_98]
0x180067454  call    jsonParseReset
0x180067459  jmp     short loc_18006749C
0x18006745b  mov     rcx, rbx
0x18006745e  call    jsonParseFree
0x180067463  mov     rcx, rdi
0x180067466  cmp     esi, 0FFFFFFFFh
0x180067469  jnz     short loc_18006747D
0x18006746b  or      r8d, 0FFFFFFFFh
0x18006746f  lea     rdx, aMalformedJson; "malformed JSON"
0x180067476  call    sqlite3_result_error
0x18006747b  jmp     short loc_1800674A4
0x18006747d  mov     rdx, rbp
0x180067480  call    jsonBadPathError
0x180067485  jmp     short loc_1800674A4
0x180067487  mov     rcx, rdi
0x18006748a  call    sqlite3_result_error_nomem
0x18006748f  jmp     short loc_18006749C
0x180067491  mov     rdx, rbx
0x180067494  mov     rcx, rdi
0x180067497  call    jsonReturnParse
0x18006749c  mov     rcx, rbx
0x18006749f  call    jsonParseFree
0x1800674a4  add     rsp, 88h
0x1800674ab  pop     r15
0x1800674ad  pop     r14
0x1800674af  pop     r13
0x1800674b1  pop     r12
0x1800674b3  pop     rdi
0x1800674b4  pop     rsi
0x1800674b5  pop     rbp
0x1800674b6  pop     rbx
0x1800674b7  retn
```
