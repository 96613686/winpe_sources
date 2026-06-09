# jsonInsertIntoBlob

- ea: `0x180084384`
- end: `0x180084528`
- name: `jsonInsertIntoBlob`
- size: `420`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180085b50`
- `0x1800862e0`

## callees

- `0x180024b60`
- `0x180078968`
- `0x180082760`
- `0x180082a14`
- `0x180084008`
- `0x180084384`
- `0x180084730`
- `0x180085450`
- `0x18008548c`
- `0x1800856dc`
- `0x180085f74`
- `0x18009d650`
- `0x18009d6d0`

## string_xrefs

- `0x1800844df`: `malformed JSON`

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
  const void *v16; // [rsp+30h] [rbp-98h] BYREF
  unsigned int v17; // [rsp+38h] [rbp-90h]

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
      v12 = qword_1800B5270;
      v13 = a3[i];
      if ( *((_BYTE *)qword_1800B5270 + (*(_WORD *)(v13 + 20) & 0x3F)) != 5 )
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
        if ( (unsigned int)jsonFunctionArgToBlob(a1, a3[i + 1], (__int64 *)&v16) )
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
      return jsonBadPathError(a1);
  }
  return result;
}

```

## disassembly

```asm
0x180084384  mov     [rsp+arg_18], r9d
0x180084389  push    rbx
0x18008438a  push    rbp
0x18008438b  push    rsi
0x18008438c  push    rdi
0x18008438d  push    r12
0x18008438f  push    r13
0x180084391  push    r14
0x180084393  push    r15
0x180084395  sub     rsp, 88h
0x18008439c  mov     ebp, edx
0x18008439e  mov     r12, r8
0x1800843a1  xor     edx, edx; Val
0x1800843a3  mov     rdi, rcx
0x1800843a6  lea     rcx, [rsp+0C8h+var_98]; void *
0x1800843ab  lea     r8d, [rdx+48h]; Size
0x1800843af  call    memset_0
0x1800843b4  mov     rdx, [r12]
0x1800843b8  xor     r8d, r8d
0x1800843bb  cmp     ebp, 1
0x1800843be  mov     rcx, rdi
0x1800843c1  setnz   r8b
0x1800843c5  call    jsonParseFuncArg
0x1800843ca  mov     rbx, rax
0x1800843cd  test    rax, rax
0x1800843d0  jz      loc_180084514
0x1800843d6  xor     esi, esi
0x1800843d8  lea     r13d, [rbp-1]
0x1800843dc  lea     r14d, [rsi+1]
0x1800843e0  cmp     r14d, r13d
0x1800843e3  jge     loc_180084501
0x1800843e9  movsxd  r15, r14d
0x1800843ec  lea     rdx, qword_1800B5270
0x1800843f3  mov     rcx, [r12+r15*8]
0x1800843f7  movzx   eax, word ptr [rcx+14h]
0x1800843fb  and     eax, 3Fh
0x1800843fe  cmp     byte ptr [rax+rdx], 5
0x180084402  jz      loc_1800844B6
0x180084408  mov     dl, 1
0x18008440a  call    sqlite3ValueText
0x18008440f  mov     rbp, rax
0x180084412  test    rax, rax
0x180084415  jz      loc_1800844F7
0x18008441b  cmp     byte ptr [rax], 24h ; '$'
0x18008441e  jnz     loc_1800844CB
0x180084424  mov     rdx, [r12+r15*8+8]
0x180084429  lea     r8, [rsp+0C8h+var_98]
0x18008442e  mov     rcx, rdi
0x180084431  call    jsonFunctionArgToBlob
0x180084436  test    eax, eax
0x180084438  jnz     loc_1800844BF
0x18008443e  mov     eax, [rsp+0C8h+arg_18]
0x180084445  lea     r8, [rbp+1]
0x180084449  cmp     byte ptr [r8], 0
0x18008444d  jnz     short loc_180084478
0x18008444f  add     eax, 0FFFFFFFEh
0x180084452  test    eax, 0FFFFFFFDh
0x180084457  jnz     short loc_180084474
0x180084459  mov     eax, [rsp+0C8h+var_90]
0x18008445d  xor     edx, edx
0x18008445f  mov     r9, [rsp+0C8h+var_98]
0x180084464  mov     rcx, rbx
0x180084467  mov     r8d, [rbx+8]
0x18008446b  mov     [rsp+0C8h+var_A8], eax
0x18008446f  call    jsonBlobEdit
0x180084474  xor     esi, esi
0x180084476  jmp     short loc_1800844A1
0x180084478  mov     [rbx+33h], al
0x18008447b  xor     r9d, r9d
0x18008447e  mov     eax, [rsp+0C8h+var_90]
0x180084482  xor     edx, edx
0x180084484  mov     [rbx+38h], eax
0x180084487  mov     rcx, rbx
0x18008448a  mov     rax, [rsp+0C8h+var_98]
0x18008448f  mov     [rbx+40h], rax
0x180084493  mov     dword ptr [rbx+34h], 0
0x18008449a  call    jsonLookupStep
0x18008449f  mov     esi, eax
0x1800844a1  lea     rcx, [rsp+0C8h+var_98]
0x1800844a6  call    jsonParseReset
0x1800844ab  lea     ecx, [rsi+3]
0x1800844ae  test    ecx, 0FFFFFFFDh
0x1800844b4  jz      short loc_1800844CB
0x1800844b6  add     r14d, 2
0x1800844ba  jmp     loc_1800843E0
0x1800844bf  lea     rcx, [rsp+0C8h+var_98]
0x1800844c4  call    jsonParseReset
0x1800844c9  jmp     short loc_18008450C
0x1800844cb  mov     rcx, rbx
0x1800844ce  call    jsonParseFree
0x1800844d3  mov     rcx, rdi
0x1800844d6  cmp     esi, 0FFFFFFFFh
0x1800844d9  jnz     short loc_1800844ED
0x1800844db  or      r8d, 0FFFFFFFFh
0x1800844df  lea     rdx, aMalformedJson; "malformed JSON"
0x1800844e6  call    sqlite3_result_error
0x1800844eb  jmp     short loc_180084514
0x1800844ed  mov     rdx, rbp
0x1800844f0  call    jsonBadPathError
0x1800844f5  jmp     short loc_180084514
0x1800844f7  mov     rcx, rdi
0x1800844fa  call    sqlite3_result_error_nomem
0x1800844ff  jmp     short loc_18008450C
0x180084501  mov     rdx, rbx
0x180084504  mov     rcx, rdi
0x180084507  call    jsonReturnParse
0x18008450c  mov     rcx, rbx
0x18008450f  call    jsonParseFree
0x180084514  add     rsp, 88h
0x18008451b  pop     r15
0x18008451d  pop     r14
0x18008451f  pop     r13
0x180084521  pop     r12
0x180084523  pop     rdi
0x180084524  pop     rsi
0x180084525  pop     rbp
0x180084526  pop     rbx
0x180084527  retn
```
