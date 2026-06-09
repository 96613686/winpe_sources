# jsonConvertTextToBlob

- ea: `0x180073c34`
- end: `0x180073cea`
- name: `jsonConvertTextToBlob`
- size: `182`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180074260`
- `0x180074810`
- `0x180074dcc`
- `0x18007627c`

## callees

- `0x180068190`
- `0x180072934`
- `0x180073c34`
- `0x1800764cc`
- `0x180077a50`
- `0x18008f3f0`

## string_xrefs

- `0x180073ca3`: `malformed JSON`

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
  for ( i = *(unsigned __int8 *)(v5 + v2); byte_1800A6970[i]; i = *(unsigned __int8 *)(v7 + v2) )
    ++v7;
  v9 = (_BYTE *)(v2 + v7);
  if ( *v9 )
  {
    v7 += json5Whitespace(v9, byte_1800A6970);
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
0x180073c34  push    rbx
0x180073c36  push    rbp
0x180073c37  push    rsi
0x180073c38  push    rdi
0x180073c39  push    r14
0x180073c3b  sub     rsp, 20h
0x180073c3f  mov     rbp, [rcx+10h]
0x180073c43  mov     rdi, rdx
0x180073c46  xor     edx, edx
0x180073c48  mov     rsi, rcx
0x180073c4b  call    jsonTranslateTextToBlob
0x180073c50  mov     r14b, [rsi+2Fh]
0x180073c54  movsxd  rbx, eax
0x180073c57  test    r14b, r14b
0x180073c5a  jnz     short loc_180073CD6
0x180073c5c  test    eax, eax
0x180073c5e  jle     short loc_180073CD6
0x180073c60  lfence
0x180073c63  movzx   ecx, byte ptr [rbx+rbp]
0x180073c67  lea     rdx, byte_1800A6970
0x180073c6e  jmp     short loc_180073C79
0x180073c70  inc     ebx
0x180073c72  movsxd  rax, ebx
0x180073c75  movzx   ecx, byte ptr [rax+rbp]
0x180073c79  cmp     byte ptr [rcx+rdx], 0
0x180073c7d  jnz     short loc_180073C70
0x180073c7f  movsxd  rcx, ebx
0x180073c82  add     rcx, rbp
0x180073c85  cmp     byte ptr [rcx], 0
0x180073c88  jz      short loc_180073CCE
0x180073c8a  call    json5Whitespace
0x180073c8f  add     ebx, eax
0x180073c91  movsxd  rax, ebx
0x180073c94  cmp     byte ptr [rax+rbp], 0
0x180073c98  jz      short loc_180073CCA
0x180073c9a  test    rdi, rdi
0x180073c9d  jz      short loc_180073CB2
0x180073c9f  or      r8d, 0FFFFFFFFh
0x180073ca3  lea     rdx, aMalformedJson; "malformed JSON"
0x180073caa  mov     rcx, rdi
0x180073cad  call    sqlite3_result_error
0x180073cb2  mov     rcx, rsi
0x180073cb5  call    jsonParseReset
0x180073cba  mov     eax, 1
0x180073cbf  add     rsp, 20h
0x180073cc3  pop     r14
0x180073cc5  pop     rdi
0x180073cc6  pop     rsi
0x180073cc7  pop     rbp
0x180073cc8  pop     rbx
0x180073cc9  retn
0x180073cca  mov     byte ptr [rsi+31h], 1
0x180073cce  test    ebx, ebx
0x180073cd0  jle     short loc_180073CD6
0x180073cd2  xor     eax, eax
0x180073cd4  jmp     short loc_180073CBF
0x180073cd6  test    rdi, rdi
0x180073cd9  jz      short loc_180073CB2
0x180073cdb  test    r14b, r14b
0x180073cde  jz      short loc_180073C9F
0x180073ce0  mov     rcx, rdi
0x180073ce3  call    sqlite3_result_error_nomem
0x180073ce8  jmp     short loc_180073CB2
```
