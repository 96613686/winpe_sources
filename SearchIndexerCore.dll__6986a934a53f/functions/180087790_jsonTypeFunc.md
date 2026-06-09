# jsonTypeFunc

- ea: `0x180087790`
- end: `0x180087853`
- name: `jsonTypeFunc`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180024b60`
- `0x180082760`
- `0x180084730`
- `0x180085450`
- `0x18008548c`
- `0x180087790`
- `0x18009d650`
- `0x18009d7b0`

## string_xrefs

- `0x1800877fc`: `malformed JSON`

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
    sqlite3_result_text(a1, off_1800B2920[*(_BYTE *)(v10 + *v8) & 0xF], 0xFFFFFFFFLL, 0);
    return jsonParseFree(v8);
  }
  return result;
}

```

## disassembly

```asm
0x180087790  push    rbx
0x180087792  push    rbp
0x180087793  push    rsi
0x180087794  push    rdi
0x180087795  sub     rsp, 28h
0x180087799  mov     rbx, r8
0x18008779c  mov     ebp, edx
0x18008779e  xor     r8d, r8d
0x1800877a1  mov     rdi, rcx
0x1800877a4  mov     rdx, [rbx]
0x1800877a7  call    jsonParseFuncArg
0x1800877ac  mov     rsi, rax
0x1800877af  test    rax, rax
0x1800877b2  jz      loc_18008784A
0x1800877b8  cmp     ebp, 2
0x1800877bb  jnz     short loc_18008781A
0x1800877bd  mov     rcx, [rbx+8]
0x1800877c1  mov     dl, 1
0x1800877c3  call    sqlite3ValueText
0x1800877c8  mov     rbx, rax
0x1800877cb  test    rax, rax
0x1800877ce  jz      short loc_180087842
0x1800877d0  cmp     byte ptr [rax], 24h ; '$'
0x1800877d3  jnz     short loc_18008780D
0x1800877d5  lea     r8, [rax+1]
0x1800877d9  xor     r9d, r9d
0x1800877dc  xor     edx, edx
0x1800877de  mov     rcx, rsi
0x1800877e1  call    jsonLookupStep
0x1800877e6  mov     ecx, 0FFFFFFFDh
0x1800877eb  cmp     eax, ecx
0x1800877ed  jb      short loc_18008781C
0x1800877ef  cmp     eax, 0FFFFFFFEh
0x1800877f2  jz      short loc_180087842
0x1800877f4  cmp     eax, ecx
0x1800877f6  jz      short loc_18008780D
0x1800877f8  or      r8d, 0FFFFFFFFh
0x1800877fc  lea     rdx, aMalformedJson; "malformed JSON"
0x180087803  mov     rcx, rdi
0x180087806  call    sqlite3_result_error
0x18008780b  jmp     short loc_180087842
0x18008780d  mov     rdx, rbx
0x180087810  mov     rcx, rdi
0x180087813  call    jsonBadPathError
0x180087818  jmp     short loc_180087842
0x18008781a  xor     eax, eax
0x18008781c  mov     ecx, eax
0x18008781e  xor     r9d, r9d
0x180087821  mov     rax, [rsi]
0x180087824  or      r8d, 0FFFFFFFFh
0x180087828  movzx   edx, byte ptr [rcx+rax]
0x18008782c  lea     rax, off_1800B2920; "null"
0x180087833  and     edx, 0Fh
0x180087836  mov     rcx, rdi
0x180087839  mov     rdx, [rax+rdx*8]
0x18008783d  call    sqlite3_result_text
0x180087842  mov     rcx, rsi
0x180087845  call    jsonParseFree
0x18008784a  add     rsp, 28h
0x18008784e  pop     rdi
0x18008784f  pop     rsi
0x180087850  pop     rbp
0x180087851  pop     rbx
0x180087852  retn
```
