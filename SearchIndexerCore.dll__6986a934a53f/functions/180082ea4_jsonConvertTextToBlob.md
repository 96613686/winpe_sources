# jsonConvertTextToBlob

- ea: `0x180082ea4`
- end: `0x180082f5a`
- name: `jsonConvertTextToBlob`
- size: `182`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800834b0`
- `0x180083a60`
- `0x180084008`
- `0x18008548c`

## callees

- `0x180081b9c`
- `0x180082ea4`
- `0x1800856dc`
- `0x180086c60`
- `0x18009d650`
- `0x18009d6d0`

## string_xrefs

- `0x180082f13`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonConvertTextToBlob(__int64 a1, __int64 a2)
{
  __int64 v2; // rbp
  int v5; // eax
  char v6; // r14
  int v7; // ebx
  __int64 i; // rcx
  _BYTE *v9; // rcx

  v2 = *(_QWORD *)(a1 + 16);
  v5 = jsonTranslateTextToBlob(a1, 0);
  v6 = *(_BYTE *)(a1 + 47);
  v7 = v5;
  if ( v6 || v5 <= 0 )
    goto LABEL_14;
  _mm_lfence();
  for ( i = *(unsigned __int8 *)(v5 + v2); *((_BYTE *)&qword_1800BD6E0 + i); i = *(unsigned __int8 *)(v7 + v2) )
    ++v7;
  v9 = (_BYTE *)(v2 + v7);
  if ( *v9 )
  {
    v7 += json5Whitespace((__int64)v9);
    if ( *(_BYTE *)(v7 + v2) )
    {
      if ( !a2 )
      {
LABEL_10:
        jsonParseReset(a1);
        return 1;
      }
LABEL_9:
      sqlite3_result_error(a2, "malformed JSON", 0xFFFFFFFFLL);
      goto LABEL_10;
    }
    *(_BYTE *)(a1 + 49) = 1;
  }
  if ( v7 <= 0 )
  {
LABEL_14:
    if ( !a2 )
      goto LABEL_10;
    if ( v6 )
    {
      sqlite3_result_error_nomem(a2);
      goto LABEL_10;
    }
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x180082ea4  push    rbx
0x180082ea6  push    rbp
0x180082ea7  push    rsi
0x180082ea8  push    rdi
0x180082ea9  push    r14
0x180082eab  sub     rsp, 20h
0x180082eaf  mov     rbp, [rcx+10h]
0x180082eb3  mov     rdi, rdx
0x180082eb6  xor     edx, edx
0x180082eb8  mov     rsi, rcx
0x180082ebb  call    jsonTranslateTextToBlob
0x180082ec0  mov     r14b, [rsi+2Fh]
0x180082ec4  movsxd  rbx, eax
0x180082ec7  test    r14b, r14b
0x180082eca  jnz     short loc_180082F46
0x180082ecc  test    eax, eax
0x180082ece  jle     short loc_180082F46
0x180082ed0  lfence
0x180082ed3  movzx   ecx, byte ptr [rbx+rbp]
0x180082ed7  lea     rdx, qword_1800BD6E0
0x180082ede  jmp     short loc_180082EE9
0x180082ee0  inc     ebx
0x180082ee2  movsxd  rax, ebx
0x180082ee5  movzx   ecx, byte ptr [rax+rbp]
0x180082ee9  cmp     byte ptr [rcx+rdx], 0
0x180082eed  jnz     short loc_180082EE0
0x180082eef  movsxd  rcx, ebx
0x180082ef2  add     rcx, rbp
0x180082ef5  cmp     byte ptr [rcx], 0
0x180082ef8  jz      short loc_180082F3E
0x180082efa  call    json5Whitespace
0x180082eff  add     ebx, eax
0x180082f01  movsxd  rax, ebx
0x180082f04  cmp     byte ptr [rax+rbp], 0
0x180082f08  jz      short loc_180082F3A
0x180082f0a  test    rdi, rdi
0x180082f0d  jz      short loc_180082F22
0x180082f0f  or      r8d, 0FFFFFFFFh
0x180082f13  lea     rdx, aMalformedJson; "malformed JSON"
0x180082f1a  mov     rcx, rdi
0x180082f1d  call    sqlite3_result_error
0x180082f22  mov     rcx, rsi
0x180082f25  call    jsonParseReset
0x180082f2a  mov     eax, 1
0x180082f2f  add     rsp, 20h
0x180082f33  pop     r14
0x180082f35  pop     rdi
0x180082f36  pop     rsi
0x180082f37  pop     rbp
0x180082f38  pop     rbx
0x180082f39  retn
0x180082f3a  mov     byte ptr [rsi+31h], 1
0x180082f3e  test    ebx, ebx
0x180082f40  jle     short loc_180082F46
0x180082f42  xor     eax, eax
0x180082f44  jmp     short loc_180082F2F
0x180082f46  test    rdi, rdi
0x180082f49  jz      short loc_180082F22
0x180082f4b  test    r14b, r14b
0x180082f4e  jz      short loc_180082F0F
0x180082f50  mov     rcx, rdi
0x180082f53  call    sqlite3_result_error_nomem
0x180082f58  jmp     short loc_180082F22
```
