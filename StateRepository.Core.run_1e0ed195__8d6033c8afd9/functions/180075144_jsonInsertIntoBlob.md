# jsonInsertIntoBlob

- ea: `0x180075144`
- end: `0x1800752e8`
- name: `jsonInsertIntoBlob`
- size: `420`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180076940`
- `0x1800770d0`

## callees

- `0x180028540`
- `0x180068190`
- `0x18006910e`
- `0x1800734f0`
- `0x1800737a4`
- `0x180074dcc`
- `0x180075144`
- `0x1800754f0`
- `0x180076240`
- `0x18007627c`
- `0x1800764cc`
- `0x180076d64`
- `0x18008f3f0`

## string_xrefs

- `0x18007529f`: `malformed JSON`

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
      v12 = qword_18009EC50;
      v13 = a3[i];
      if ( *((_BYTE *)qword_18009EC50 + (*(_WORD *)(v13 + 20) & 0x3F)) != 5 )
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
0x180075144  mov     [rsp+arg_18], r9d
0x180075149  push    rbx
0x18007514a  push    rbp
0x18007514b  push    rsi
0x18007514c  push    rdi
0x18007514d  push    r12
0x18007514f  push    r13
0x180075151  push    r14
0x180075153  push    r15
0x180075155  sub     rsp, 88h
0x18007515c  mov     ebp, edx
0x18007515e  mov     r12, r8
0x180075161  xor     edx, edx; Val
0x180075163  mov     rdi, rcx
0x180075166  lea     rcx, [rsp+0C8h+var_98]; void *
0x18007516b  lea     r8d, [rdx+48h]; Size
0x18007516f  call    memset_0
0x180075174  mov     rdx, [r12]
0x180075178  xor     r8d, r8d
0x18007517b  cmp     ebp, 1
0x18007517e  mov     rcx, rdi
0x180075181  setnz   r8b
0x180075185  call    jsonParseFuncArg
0x18007518a  mov     rbx, rax
0x18007518d  test    rax, rax
0x180075190  jz      loc_1800752D4
0x180075196  xor     esi, esi
0x180075198  lea     r13d, [rbp-1]
0x18007519c  lea     r14d, [rsi+1]
0x1800751a0  cmp     r14d, r13d
0x1800751a3  jge     loc_1800752C1
0x1800751a9  movsxd  r15, r14d
0x1800751ac  lea     rdx, qword_18009EC50
0x1800751b3  mov     rcx, [r12+r15*8]
0x1800751b7  movzx   eax, word ptr [rcx+14h]
0x1800751bb  and     eax, 3Fh
0x1800751be  cmp     byte ptr [rax+rdx], 5
0x1800751c2  jz      loc_180075276
0x1800751c8  mov     dl, 1
0x1800751ca  call    sqlite3ValueText
0x1800751cf  mov     rbp, rax
0x1800751d2  test    rax, rax
0x1800751d5  jz      loc_1800752B7
0x1800751db  cmp     byte ptr [rax], 24h ; '$'
0x1800751de  jnz     loc_18007528B
0x1800751e4  mov     rdx, [r12+r15*8+8]
0x1800751e9  lea     r8, [rsp+0C8h+var_98]
0x1800751ee  mov     rcx, rdi
0x1800751f1  call    jsonFunctionArgToBlob
0x1800751f6  test    eax, eax
0x1800751f8  jnz     loc_18007527F
0x1800751fe  mov     eax, [rsp+0C8h+arg_18]
0x180075205  lea     r8, [rbp+1]
0x180075209  cmp     byte ptr [r8], 0
0x18007520d  jnz     short loc_180075238
0x18007520f  add     eax, 0FFFFFFFEh
0x180075212  test    eax, 0FFFFFFFDh
0x180075217  jnz     short loc_180075234
0x180075219  mov     eax, [rsp+0C8h+var_90]
0x18007521d  xor     edx, edx
0x18007521f  mov     r9, [rsp+0C8h+var_98]
0x180075224  mov     rcx, rbx
0x180075227  mov     r8d, [rbx+8]
0x18007522b  mov     [rsp+0C8h+var_A8], eax
0x18007522f  call    jsonBlobEdit
0x180075234  xor     esi, esi
0x180075236  jmp     short loc_180075261
0x180075238  mov     [rbx+33h], al
0x18007523b  xor     r9d, r9d
0x18007523e  mov     eax, [rsp+0C8h+var_90]
0x180075242  xor     edx, edx
0x180075244  mov     [rbx+38h], eax
0x180075247  mov     rcx, rbx
0x18007524a  mov     rax, [rsp+0C8h+var_98]
0x18007524f  mov     [rbx+40h], rax
0x180075253  mov     dword ptr [rbx+34h], 0
0x18007525a  call    jsonLookupStep
0x18007525f  mov     esi, eax
0x180075261  lea     rcx, [rsp+0C8h+var_98]
0x180075266  call    jsonParseReset
0x18007526b  lea     ecx, [rsi+3]
0x18007526e  test    ecx, 0FFFFFFFDh
0x180075274  jz      short loc_18007528B
0x180075276  add     r14d, 2
0x18007527a  jmp     loc_1800751A0
0x18007527f  lea     rcx, [rsp+0C8h+var_98]
0x180075284  call    jsonParseReset
0x180075289  jmp     short loc_1800752CC
0x18007528b  mov     rcx, rbx
0x18007528e  call    jsonParseFree
0x180075293  mov     rcx, rdi
0x180075296  cmp     esi, 0FFFFFFFFh
0x180075299  jnz     short loc_1800752AD
0x18007529b  or      r8d, 0FFFFFFFFh
0x18007529f  lea     rdx, aMalformedJson; "malformed JSON"
0x1800752a6  call    sqlite3_result_error
0x1800752ab  jmp     short loc_1800752D4
0x1800752ad  mov     rdx, rbp
0x1800752b0  call    jsonBadPathError
0x1800752b5  jmp     short loc_1800752D4
0x1800752b7  mov     rcx, rdi
0x1800752ba  call    sqlite3_result_error_nomem
0x1800752bf  jmp     short loc_1800752CC
0x1800752c1  mov     rdx, rbx
0x1800752c4  mov     rcx, rdi
0x1800752c7  call    jsonReturnParse
0x1800752cc  mov     rcx, rbx
0x1800752cf  call    jsonParseFree
0x1800752d4  add     rsp, 88h
0x1800752db  pop     r15
0x1800752dd  pop     r14
0x1800752df  pop     r13
0x1800752e1  pop     r12
0x1800752e3  pop     rdi
0x1800752e4  pop     rsi
0x1800752e5  pop     rbp
0x1800752e6  pop     rbx
0x1800752e7  retn
```
