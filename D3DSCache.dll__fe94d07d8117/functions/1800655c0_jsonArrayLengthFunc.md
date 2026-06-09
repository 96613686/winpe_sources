# jsonArrayLengthFunc

- ea: `0x1800655c0`
- end: `0x1800656a8`
- name: `jsonArrayLengthFunc`
- size: `232`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180042dc4`
- `0x1800655c0`
- `0x180065750`
- `0x1800676c0`
- `0x1800683e0`
- `0x18006841c`
- `0x18006abd8`
- `0x180096df0`
- `0x180096f10`

## string_xrefs

- `0x180065651`: `malformed JSON`

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
0x1800655c0  push    rbx
0x1800655c2  push    rbp
0x1800655c3  push    rsi
0x1800655c4  push    rdi
0x1800655c5  push    r14
0x1800655c7  sub     rsp, 20h
0x1800655cb  mov     rbx, r8
0x1800655ce  mov     r14d, edx
0x1800655d1  xor     r8d, r8d
0x1800655d4  mov     rsi, rcx
0x1800655d7  mov     rdx, [rbx]
0x1800655da  call    jsonParseFuncArg
0x1800655df  mov     rdi, rax
0x1800655e2  test    rax, rax
0x1800655e5  jz      loc_18006569D
0x1800655eb  xor     bpl, bpl
0x1800655ee  cmp     r14d, 2
0x1800655f2  jnz     short loc_180065660
0x1800655f4  mov     rcx, [rbx+8]
0x1800655f8  mov     dl, 1
0x1800655fa  call    sqlite3ValueText
0x1800655ff  mov     rbx, rax
0x180065602  test    rax, rax
0x180065605  jz      loc_180065695
0x18006560b  cmp     byte ptr [rax], 24h ; '$'
0x18006560e  lea     r8, [rax+1]
0x180065612  jz      short loc_18006561B
0x180065614  lea     r8, asc_1800B5E7C; "@"
0x18006561b  xor     r9d, r9d
0x18006561e  xor     edx, edx
0x180065620  mov     rcx, rdi
0x180065623  call    jsonLookupStep
0x180065628  mov     r8d, eax
0x18006562b  mov     eax, 0FFFFFFFDh
0x180065630  cmp     r8d, eax
0x180065633  jb      short loc_180065663
0x180065635  cmp     r8d, 0FFFFFFFEh
0x180065639  jz      short loc_18006565D
0x18006563b  mov     rcx, rsi
0x18006563e  cmp     r8d, eax
0x180065641  jnz     short loc_18006564D
0x180065643  mov     rdx, rbx
0x180065646  call    jsonBadPathError
0x18006564b  jmp     short loc_18006565D
0x18006564d  or      r8d, 0FFFFFFFFh
0x180065651  lea     rdx, aMalformedJson; "malformed JSON"
0x180065658  call    sqlite3_result_error
0x18006565d  mov     bpl, 1
0x180065660  xor     r8d, r8d
0x180065663  mov     rax, [rdi]
0x180065666  xor     r9d, r9d
0x180065669  mov     ecx, r8d
0x18006566c  mov     dl, [rcx+rax]
0x18006566f  and     dl, 0Fh
0x180065672  cmp     dl, 0Bh
0x180065675  jnz     short loc_180065685
0x180065677  mov     edx, r8d
0x18006567a  mov     rcx, rdi
0x18006567d  call    jsonbArrayCount
0x180065682  mov     r9d, eax
0x180065685  test    bpl, bpl
0x180065688  jnz     short loc_180065695
0x18006568a  mov     rdx, r9
0x18006568d  mov     rcx, rsi
0x180065690  call    sqlite3_result_int64
0x180065695  mov     rcx, rdi
0x180065698  call    jsonParseFree
0x18006569d  add     rsp, 20h
0x1800656a1  pop     r14
0x1800656a3  pop     rdi
0x1800656a4  pop     rsi
0x1800656a5  pop     rbp
0x1800656a6  pop     rbx
0x1800656a7  retn
```
