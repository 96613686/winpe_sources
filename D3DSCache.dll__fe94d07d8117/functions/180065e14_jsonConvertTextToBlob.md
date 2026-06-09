# jsonConvertTextToBlob

- ea: `0x180065e14`
- end: `0x180065eca`
- name: `jsonConvertTextToBlob`
- size: `182`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180066440`
- `0x1800669f0`
- `0x180066f98`
- `0x18006841c`

## callees

- `0x180064b8c`
- `0x180065e14`
- `0x18006866c`
- `0x180069bdc`
- `0x180096df0`
- `0x180096e70`

## string_xrefs

- `0x180065e83`: `malformed JSON`

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
  for ( i = *(unsigned __int8 *)(v5 + v2); *((_BYTE *)&qword_1800B6630 + i); i = *(unsigned __int8 *)(v7 + v2) )
    ++v7;
  v9 = (_BYTE *)(v2 + v7);
  if ( *v9 )
  {
    v7 += json5Whitespace(v9, &qword_1800B6630);
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
0x180065e14  push    rbx
0x180065e16  push    rbp
0x180065e17  push    rsi
0x180065e18  push    rdi
0x180065e19  push    r14
0x180065e1b  sub     rsp, 20h
0x180065e1f  mov     rbp, [rcx+10h]
0x180065e23  mov     rdi, rdx
0x180065e26  xor     edx, edx
0x180065e28  mov     rsi, rcx
0x180065e2b  call    jsonTranslateTextToBlob
0x180065e30  mov     r14b, [rsi+2Fh]
0x180065e34  movsxd  rbx, eax
0x180065e37  test    r14b, r14b
0x180065e3a  jnz     short loc_180065EB6
0x180065e3c  test    eax, eax
0x180065e3e  jle     short loc_180065EB6
0x180065e40  lfence
0x180065e43  movzx   ecx, byte ptr [rbx+rbp]
0x180065e47  lea     rdx, qword_1800B6630
0x180065e4e  jmp     short loc_180065E59
0x180065e50  inc     ebx
0x180065e52  movsxd  rax, ebx
0x180065e55  movzx   ecx, byte ptr [rax+rbp]
0x180065e59  cmp     byte ptr [rcx+rdx], 0
0x180065e5d  jnz     short loc_180065E50
0x180065e5f  movsxd  rcx, ebx
0x180065e62  add     rcx, rbp
0x180065e65  cmp     byte ptr [rcx], 0
0x180065e68  jz      short loc_180065EAE
0x180065e6a  call    json5Whitespace
0x180065e6f  add     ebx, eax
0x180065e71  movsxd  rax, ebx
0x180065e74  cmp     byte ptr [rax+rbp], 0
0x180065e78  jz      short loc_180065EAA
0x180065e7a  test    rdi, rdi
0x180065e7d  jz      short loc_180065E92
0x180065e7f  or      r8d, 0FFFFFFFFh
0x180065e83  lea     rdx, aMalformedJson; "malformed JSON"
0x180065e8a  mov     rcx, rdi
0x180065e8d  call    sqlite3_result_error
0x180065e92  mov     rcx, rsi
0x180065e95  call    jsonParseReset
0x180065e9a  mov     eax, 1
0x180065e9f  add     rsp, 20h
0x180065ea3  pop     r14
0x180065ea5  pop     rdi
0x180065ea6  pop     rsi
0x180065ea7  pop     rbp
0x180065ea8  pop     rbx
0x180065ea9  retn
0x180065eaa  mov     byte ptr [rsi+31h], 1
0x180065eae  test    ebx, ebx
0x180065eb0  jle     short loc_180065EB6
0x180065eb2  xor     eax, eax
0x180065eb4  jmp     short loc_180065E9F
0x180065eb6  test    rdi, rdi
0x180065eb9  jz      short loc_180065E92
0x180065ebb  test    r14b, r14b
0x180065ebe  jz      short loc_180065E7F
0x180065ec0  mov     rcx, rdi
0x180065ec3  call    sqlite3_result_error_nomem
0x180065ec8  jmp     short loc_180065E92
```
