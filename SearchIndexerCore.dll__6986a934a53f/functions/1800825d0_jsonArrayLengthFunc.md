# jsonArrayLengthFunc

- ea: `0x1800825d0`
- end: `0x1800826b8`
- name: `jsonArrayLengthFunc`
- size: `232`
- prototype: `__int64 __fastcall(__int64, int, _QWORD *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180024b60`
- `0x1800501a0`
- `0x1800825d0`
- `0x180082760`
- `0x180084730`
- `0x180085450`
- `0x18008548c`
- `0x180087c08`
- `0x18009d650`

## string_xrefs

- `0x180082661`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonArrayLengthFunc(__int64 a1, int a2, _QWORD *a3)
{
  __int64 result; // rax
  __int64 v7; // rdx
  _QWORD *v8; // rdi
  char v9; // bp
  _BYTE *v10; // rax
  _BYTE *v11; // rbx
  const char *v12; // r8
  unsigned int v13; // r8d
  __int64 v14; // r9

  result = jsonParseFuncArg(a1, *a3, 0);
  v8 = (_QWORD *)result;
  if ( result )
  {
    v9 = 0;
    if ( a2 == 2 )
    {
      LOBYTE(v7) = 1;
      v10 = (_BYTE *)sqlite3ValueText(a3[1], v7);
      v11 = v10;
      if ( !v10 )
        return jsonParseFree(v8);
      v12 = v10 + 1;
      if ( *v10 != 36 )
        v12 = "@";
      v13 = jsonLookupStep(v8, 0, v12, 0);
      if ( v13 < 0xFFFFFFFD )
      {
LABEL_13:
        v14 = 0;
        if ( (*(_BYTE *)(v13 + *v8) & 0xF) == 0xB )
          v14 = (unsigned int)jsonbArrayCount(v8, v13);
        if ( !v9 )
          sqlite3_result_int64(a1, v14);
        return jsonParseFree(v8);
      }
      if ( v13 != -2 )
      {
        if ( v13 == -3 )
          jsonBadPathError(a1, v11);
        else
          sqlite3_result_error(a1, "malformed JSON", 0xFFFFFFFFLL);
      }
      v9 = 1;
    }
    v13 = 0;
    goto LABEL_13;
  }
  return result;
}

```

## disassembly

```asm
0x1800825d0  push    rbx
0x1800825d2  push    rbp
0x1800825d3  push    rsi
0x1800825d4  push    rdi
0x1800825d5  push    r14
0x1800825d7  sub     rsp, 20h
0x1800825db  mov     rbx, r8
0x1800825de  mov     r14d, edx
0x1800825e1  xor     r8d, r8d
0x1800825e4  mov     rsi, rcx
0x1800825e7  mov     rdx, [rbx]
0x1800825ea  call    jsonParseFuncArg
0x1800825ef  mov     rdi, rax
0x1800825f2  test    rax, rax
0x1800825f5  jz      loc_1800826AD
0x1800825fb  xor     bpl, bpl
0x1800825fe  cmp     r14d, 2
0x180082602  jnz     short loc_180082670
0x180082604  mov     rcx, [rbx+8]
0x180082608  mov     dl, 1
0x18008260a  call    sqlite3ValueText
0x18008260f  mov     rbx, rax
0x180082612  test    rax, rax
0x180082615  jz      loc_1800826A5
0x18008261b  cmp     byte ptr [rax], 24h ; '$'
0x18008261e  lea     r8, [rax+1]
0x180082622  jz      short loc_18008262B
0x180082624  lea     r8, asc_1800BCEAC; "@"
0x18008262b  xor     r9d, r9d
0x18008262e  xor     edx, edx
0x180082630  mov     rcx, rdi
0x180082633  call    jsonLookupStep
0x180082638  mov     r8d, eax
0x18008263b  mov     eax, 0FFFFFFFDh
0x180082640  cmp     r8d, eax
0x180082643  jb      short loc_180082673
0x180082645  cmp     r8d, 0FFFFFFFEh
0x180082649  jz      short loc_18008266D
0x18008264b  mov     rcx, rsi
0x18008264e  cmp     r8d, eax
0x180082651  jnz     short loc_18008265D
0x180082653  mov     rdx, rbx
0x180082656  call    jsonBadPathError
0x18008265b  jmp     short loc_18008266D
0x18008265d  or      r8d, 0FFFFFFFFh
0x180082661  lea     rdx, aMalformedJson; "malformed JSON"
0x180082668  call    sqlite3_result_error
0x18008266d  mov     bpl, 1
0x180082670  xor     r8d, r8d
0x180082673  mov     rax, [rdi]
0x180082676  xor     r9d, r9d
0x180082679  mov     ecx, r8d
0x18008267c  mov     dl, [rcx+rax]
0x18008267f  and     dl, 0Fh
0x180082682  cmp     dl, 0Bh
0x180082685  jnz     short loc_180082695
0x180082687  mov     edx, r8d
0x18008268a  mov     rcx, rdi
0x18008268d  call    jsonbArrayCount
0x180082692  mov     r9d, eax
0x180082695  test    bpl, bpl
0x180082698  jnz     short loc_1800826A5
0x18008269a  mov     rdx, r9
0x18008269d  mov     rcx, rsi
0x1800826a0  call    sqlite3_result_int64
0x1800826a5  mov     rcx, rdi
0x1800826a8  call    jsonParseFree
0x1800826ad  add     rsp, 20h
0x1800826b1  pop     r14
0x1800826b3  pop     rdi
0x1800826b4  pop     rsi
0x1800826b5  pop     rbp
0x1800826b6  pop     rbx
0x1800826b7  retn
```
