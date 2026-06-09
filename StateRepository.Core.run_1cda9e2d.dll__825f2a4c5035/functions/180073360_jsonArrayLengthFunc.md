# jsonArrayLengthFunc

- ea: `0x180073360`
- end: `0x180073448`
- name: `jsonArrayLengthFunc`
- size: `232`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180028540`
- `0x18005ee00`
- `0x180073360`
- `0x1800734f0`
- `0x1800754f0`
- `0x180076240`
- `0x18007627c`
- `0x1800789f8`
- `0x18008f3f0`

## string_xrefs

- `0x1800733f1`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonArrayLengthFunc(__int64 a1, int a2, __int64 *a3)
{
  __int64 result; // rax
  __int64 v7; // rdx
  _QWORD *v8; // rdi
  char v9; // bp
  _BYTE *v10; // rax
  const char *v11; // r8
  unsigned int v12; // r8d
  __int64 v13; // r9

  result = jsonParseFuncArg(a1, *a3, 0);
  v8 = (_QWORD *)result;
  if ( result )
  {
    v9 = 0;
    if ( a2 == 2 )
    {
      LOBYTE(v7) = 1;
      v10 = (_BYTE *)sqlite3ValueText(a3[1], v7);
      if ( !v10 )
        return jsonParseFree(v8);
      v11 = v10 + 1;
      if ( *v10 != 36 )
        v11 = "@";
      v12 = jsonLookupStep(v8, 0, v11, 0);
      if ( v12 < 0xFFFFFFFD )
      {
LABEL_13:
        v13 = 0;
        if ( (*(_BYTE *)(v12 + *v8) & 0xF) == 0xB )
          v13 = (unsigned int)jsonbArrayCount(v8, v12);
        if ( !v9 )
          sqlite3_result_int64(a1, v13);
        return jsonParseFree(v8);
      }
      if ( v12 != -2 )
      {
        if ( v12 == -3 )
          jsonBadPathError(a1);
        else
          sqlite3_result_error(a1, "malformed JSON", 0xFFFFFFFFLL);
      }
      v9 = 1;
    }
    v12 = 0;
    goto LABEL_13;
  }
  return result;
}

```

## disassembly

```asm
0x180073360  push    rbx
0x180073362  push    rbp
0x180073363  push    rsi
0x180073364  push    rdi
0x180073365  push    r14
0x180073367  sub     rsp, 20h
0x18007336b  mov     rbx, r8
0x18007336e  mov     r14d, edx
0x180073371  xor     r8d, r8d
0x180073374  mov     rsi, rcx
0x180073377  mov     rdx, [rbx]
0x18007337a  call    jsonParseFuncArg
0x18007337f  mov     rdi, rax
0x180073382  test    rax, rax
0x180073385  jz      loc_18007343D
0x18007338b  xor     bpl, bpl
0x18007338e  cmp     r14d, 2
0x180073392  jnz     short loc_180073400
0x180073394  mov     rcx, [rbx+8]
0x180073398  mov     dl, 1
0x18007339a  call    sqlite3ValueText
0x18007339f  mov     rbx, rax
0x1800733a2  test    rax, rax
0x1800733a5  jz      loc_180073435
0x1800733ab  cmp     byte ptr [rax], 24h ; '$'
0x1800733ae  lea     r8, [rax+1]
0x1800733b2  jz      short loc_1800733BB
0x1800733b4  lea     r8, asc_1800A621C; "@"
0x1800733bb  xor     r9d, r9d
0x1800733be  xor     edx, edx
0x1800733c0  mov     rcx, rdi
0x1800733c3  call    jsonLookupStep
0x1800733c8  mov     r8d, eax
0x1800733cb  mov     eax, 0FFFFFFFDh
0x1800733d0  cmp     r8d, eax
0x1800733d3  jb      short loc_180073403
0x1800733d5  cmp     r8d, 0FFFFFFFEh
0x1800733d9  jz      short loc_1800733FD
0x1800733db  mov     rcx, rsi
0x1800733de  cmp     r8d, eax
0x1800733e1  jnz     short loc_1800733ED
0x1800733e3  mov     rdx, rbx
0x1800733e6  call    jsonBadPathError
0x1800733eb  jmp     short loc_1800733FD
0x1800733ed  or      r8d, 0FFFFFFFFh
0x1800733f1  lea     rdx, aMalformedJson; "malformed JSON"
0x1800733f8  call    sqlite3_result_error
0x1800733fd  mov     bpl, 1
0x180073400  xor     r8d, r8d
0x180073403  mov     rax, [rdi]
0x180073406  xor     r9d, r9d
0x180073409  mov     ecx, r8d
0x18007340c  mov     dl, [rcx+rax]
0x18007340f  and     dl, 0Fh
0x180073412  cmp     dl, 0Bh
0x180073415  jnz     short loc_180073425
0x180073417  mov     edx, r8d
0x18007341a  mov     rcx, rdi
0x18007341d  call    jsonbArrayCount
0x180073422  mov     r9d, eax
0x180073425  test    bpl, bpl
0x180073428  jnz     short loc_180073435
0x18007342a  mov     rdx, r9
0x18007342d  mov     rcx, rsi
0x180073430  call    sqlite3_result_int64
0x180073435  mov     rcx, rdi
0x180073438  call    jsonParseFree
0x18007343d  add     rsp, 20h
0x180073441  pop     r14
0x180073443  pop     rdi
0x180073444  pop     rsi
0x180073445  pop     rbp
0x180073446  pop     rbx
0x180073447  retn
```
