# jsonTypeFunc

- ea: `0x180078580`
- end: `0x180078643`
- name: `jsonTypeFunc`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180028540`
- `0x1800734f0`
- `0x1800754f0`
- `0x180076240`
- `0x18007627c`
- `0x180078580`
- `0x18008f3f0`
- `0x18008f510`

## string_xrefs

- `0x1800785ec`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonTypeFunc(__int64 a1, int a2, __int64 *a3)
{
  __int64 result; // rax
  __int64 v7; // rdx
  _QWORD *v8; // rsi
  _BYTE *v9; // rax
  unsigned int v10; // eax

  result = jsonParseFuncArg(a1, *a3, 0);
  v8 = (_QWORD *)result;
  if ( result )
  {
    if ( a2 == 2 )
    {
      LOBYTE(v7) = 1;
      v9 = (_BYTE *)sqlite3ValueText(a3[1], v7);
      if ( !v9 )
        return jsonParseFree(v8);
      if ( *v9 != 36 )
        goto LABEL_9;
      v10 = jsonLookupStep(v8, 0, v9 + 1, 0);
      if ( v10 >= 0xFFFFFFFD )
      {
        if ( v10 != -2 )
        {
          if ( v10 != -3 )
          {
            sqlite3_result_error(a1, "malformed JSON", 0xFFFFFFFFLL);
            return jsonParseFree(v8);
          }
LABEL_9:
          jsonBadPathError(a1);
        }
        return jsonParseFree(v8);
      }
    }
    else
    {
      v10 = 0;
    }
    sqlite3_result_text(a1, off_18009C050[*(_BYTE *)(v10 + *v8) & 0xF], 0xFFFFFFFFLL, 0);
    return jsonParseFree(v8);
  }
  return result;
}

```

## disassembly

```asm
0x180078580  push    rbx
0x180078582  push    rbp
0x180078583  push    rsi
0x180078584  push    rdi
0x180078585  sub     rsp, 28h
0x180078589  mov     rbx, r8
0x18007858c  mov     ebp, edx
0x18007858e  xor     r8d, r8d
0x180078591  mov     rdi, rcx
0x180078594  mov     rdx, [rbx]
0x180078597  call    jsonParseFuncArg
0x18007859c  mov     rsi, rax
0x18007859f  test    rax, rax
0x1800785a2  jz      loc_18007863A
0x1800785a8  cmp     ebp, 2
0x1800785ab  jnz     short loc_18007860A
0x1800785ad  mov     rcx, [rbx+8]
0x1800785b1  mov     dl, 1
0x1800785b3  call    sqlite3ValueText
0x1800785b8  mov     rbx, rax
0x1800785bb  test    rax, rax
0x1800785be  jz      short loc_180078632
0x1800785c0  cmp     byte ptr [rax], 24h ; '$'
0x1800785c3  jnz     short loc_1800785FD
0x1800785c5  lea     r8, [rax+1]
0x1800785c9  xor     r9d, r9d
0x1800785cc  xor     edx, edx
0x1800785ce  mov     rcx, rsi
0x1800785d1  call    jsonLookupStep
0x1800785d6  mov     ecx, 0FFFFFFFDh
0x1800785db  cmp     eax, ecx
0x1800785dd  jb      short loc_18007860C
0x1800785df  cmp     eax, 0FFFFFFFEh
0x1800785e2  jz      short loc_180078632
0x1800785e4  cmp     eax, ecx
0x1800785e6  jz      short loc_1800785FD
0x1800785e8  or      r8d, 0FFFFFFFFh
0x1800785ec  lea     rdx, aMalformedJson; "malformed JSON"
0x1800785f3  mov     rcx, rdi
0x1800785f6  call    sqlite3_result_error
0x1800785fb  jmp     short loc_180078632
0x1800785fd  mov     rdx, rbx
0x180078600  mov     rcx, rdi
0x180078603  call    jsonBadPathError
0x180078608  jmp     short loc_180078632
0x18007860a  xor     eax, eax
0x18007860c  mov     ecx, eax
0x18007860e  xor     r9d, r9d
0x180078611  mov     rax, [rsi]
0x180078614  or      r8d, 0FFFFFFFFh
0x180078618  movzx   edx, byte ptr [rcx+rax]
0x18007861c  lea     rax, off_18009C050; "null"
0x180078623  and     edx, 0Fh
0x180078626  mov     rcx, rdi
0x180078629  mov     rdx, [rax+rdx*8]
0x18007862d  call    sqlite3_result_text
0x180078632  mov     rcx, rsi
0x180078635  call    jsonParseFree
0x18007863a  add     rsp, 28h
0x18007863e  pop     rdi
0x18007863f  pop     rsi
0x180078640  pop     rbp
0x180078641  pop     rbx
0x180078642  retn
```
