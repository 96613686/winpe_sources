# jsonTypeFunc

- ea: `0x18006a710`
- end: `0x18006a7d3`
- name: `jsonTypeFunc`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180042dc4`
- `0x180065750`
- `0x1800676c0`
- `0x1800683e0`
- `0x18006841c`
- `0x18006a710`
- `0x180096df0`
- `0x180096fd0`

## string_xrefs

- `0x18006a77c`: `malformed JSON`

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
    sqlite3_result_text(a1, off_1800AA3D0[*(_BYTE *)(v10 + *v8) & 0xF], 0xFFFFFFFFLL, 0);
    return jsonParseFree(v8);
  }
  return result;
}

```

## disassembly

```asm
0x18006a710  push    rbx
0x18006a712  push    rbp
0x18006a713  push    rsi
0x18006a714  push    rdi
0x18006a715  sub     rsp, 28h
0x18006a719  mov     rbx, r8
0x18006a71c  mov     ebp, edx
0x18006a71e  xor     r8d, r8d
0x18006a721  mov     rdi, rcx
0x18006a724  mov     rdx, [rbx]
0x18006a727  call    jsonParseFuncArg
0x18006a72c  mov     rsi, rax
0x18006a72f  test    rax, rax
0x18006a732  jz      loc_18006A7CA
0x18006a738  cmp     ebp, 2
0x18006a73b  jnz     short loc_18006A79A
0x18006a73d  mov     rcx, [rbx+8]
0x18006a741  mov     dl, 1
0x18006a743  call    sqlite3ValueText
0x18006a748  mov     rbx, rax
0x18006a74b  test    rax, rax
0x18006a74e  jz      short loc_18006A7C2
0x18006a750  cmp     byte ptr [rax], 24h ; '$'
0x18006a753  jnz     short loc_18006A78D
0x18006a755  lea     r8, [rax+1]
0x18006a759  xor     r9d, r9d
0x18006a75c  xor     edx, edx
0x18006a75e  mov     rcx, rsi
0x18006a761  call    jsonLookupStep
0x18006a766  mov     ecx, 0FFFFFFFDh
0x18006a76b  cmp     eax, ecx
0x18006a76d  jb      short loc_18006A79C
0x18006a76f  cmp     eax, 0FFFFFFFEh
0x18006a772  jz      short loc_18006A7C2
0x18006a774  cmp     eax, ecx
0x18006a776  jz      short loc_18006A78D
0x18006a778  or      r8d, 0FFFFFFFFh
0x18006a77c  lea     rdx, aMalformedJson; "malformed JSON"
0x18006a783  mov     rcx, rdi
0x18006a786  call    sqlite3_result_error
0x18006a78b  jmp     short loc_18006A7C2
0x18006a78d  mov     rdx, rbx
0x18006a790  mov     rcx, rdi
0x18006a793  call    jsonBadPathError
0x18006a798  jmp     short loc_18006A7C2
0x18006a79a  xor     eax, eax
0x18006a79c  mov     ecx, eax
0x18006a79e  xor     r9d, r9d
0x18006a7a1  mov     rax, [rsi]
0x18006a7a4  or      r8d, 0FFFFFFFFh
0x18006a7a8  movzx   edx, byte ptr [rcx+rax]
0x18006a7ac  lea     rax, off_1800AA3D0; "null"
0x18006a7b3  and     edx, 0Fh
0x18006a7b6  mov     rcx, rdi
0x18006a7b9  mov     rdx, [rax+rdx*8]
0x18006a7bd  call    sqlite3_result_text
0x18006a7c2  mov     rcx, rsi
0x18006a7c5  call    jsonParseFree
0x18006a7ca  add     rsp, 28h
0x18006a7ce  pop     rdi
0x18006a7cf  pop     rsi
0x18006a7d0  pop     rbp
0x18006a7d1  pop     rbx
0x18006a7d2  retn
```
