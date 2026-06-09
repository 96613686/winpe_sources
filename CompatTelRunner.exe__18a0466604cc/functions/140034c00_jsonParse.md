# jsonParse

- ea: `0x140034c00`
- end: `0x140034cc0`
- name: `jsonParse`
- size: `192`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140033420`
- `0x140034ef4`

## callees

- `0x1400321a4`
- `0x140034c00`
- `0x140035234`
- `0x140035308`
- `0x14007c6ac`
- `0x14008c3e0`

## string_xrefs

- `0x140034c89`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonParse(__int64 a1, __int64 *a2)
{
  __int64 v2; // rbp
  int v5; // eax
  __int64 v6; // r9
  char v7; // r14
  int v8; // ebx
  __int64 i; // rcx
  _BYTE *v10; // rcx
  __int64 v12; // rcx

  v2 = *(_QWORD *)(a1 + 16);
  v5 = jsonParseValue(a1, 0);
  v7 = *(_BYTE *)(a1 + 51);
  v8 = v5;
  if ( v7 || v5 <= 0 )
  {
LABEL_11:
    if ( a2 )
    {
      if ( v7 )
      {
        sqlite3_result_error_nomem(a2);
      }
      else
      {
        v12 = *a2;
        *((_DWORD *)a2 + 9) = 1;
        LOBYTE(v6) = 1;
        sqlite3VdbeMemSetStr(v12, "malformed JSON", -1, v6, -1);
      }
    }
    goto LABEL_15;
  }
  _mm_lfence();
  for ( i = *(unsigned __int8 *)(v5 + v2); *((_BYTE *)&qword_1400B17A0 + i); i = *(unsigned __int8 *)(v8 + v2) )
    ++v8;
  v10 = (_BYTE *)(v2 + v8);
  if ( !*v10 )
  {
LABEL_9:
    if ( v8 > 0 )
      return 0;
    goto LABEL_11;
  }
  v8 += json5Whitespace(v10, &qword_1400B17A0);
  if ( !*(_BYTE *)(v8 + v2) )
  {
    *(_BYTE *)(a1 + 53) = 1;
    goto LABEL_9;
  }
LABEL_15:
  jsonParseReset(a1);
  return 1;
}

```

## disassembly

```asm
0x140034c00  push    rbx
0x140034c02  push    rbp
0x140034c03  push    rsi
0x140034c04  push    rdi
0x140034c05  push    r14
0x140034c07  sub     rsp, 30h
0x140034c0b  mov     rbp, [rcx+10h]
0x140034c0f  mov     rdi, rdx
0x140034c12  xor     edx, edx
0x140034c14  mov     rsi, rcx
0x140034c17  call    jsonParseValue
0x140034c1c  mov     r14b, [rsi+33h]
0x140034c20  movsxd  rbx, eax
0x140034c23  test    r14b, r14b
0x140034c26  jnz     short loc_140034C72
0x140034c28  test    eax, eax
0x140034c2a  jle     short loc_140034C72
0x140034c2c  lfence
0x140034c2f  movzx   ecx, byte ptr [rbx+rbp]
0x140034c33  lea     rdx, qword_1400B17A0
0x140034c3a  jmp     short loc_140034C45
0x140034c3c  inc     ebx
0x140034c3e  movsxd  rax, ebx
0x140034c41  movzx   ecx, byte ptr [rax+rbp]
0x140034c45  cmp     byte ptr [rcx+rdx], 0
0x140034c49  jnz     short loc_140034C3C
0x140034c4b  movsxd  rcx, ebx
0x140034c4e  add     rcx, rbp
0x140034c51  cmp     byte ptr [rcx], 0
0x140034c54  jz      short loc_140034C6A
0x140034c56  call    json5Whitespace
0x140034c5b  add     ebx, eax
0x140034c5d  movsxd  rax, ebx
0x140034c60  cmp     byte ptr [rax+rbp], 0
0x140034c64  jnz     short loc_140034CA8
0x140034c66  mov     byte ptr [rsi+35h], 1
0x140034c6a  test    ebx, ebx
0x140034c6c  jle     short loc_140034C72
0x140034c6e  xor     eax, eax
0x140034c70  jmp     short loc_140034CB5
0x140034c72  test    rdi, rdi
0x140034c75  jz      short loc_140034CA8
0x140034c77  test    r14b, r14b
0x140034c7a  jz      short loc_140034C86
0x140034c7c  mov     rcx, rdi
0x140034c7f  call    sqlite3_result_error_nomem
0x140034c84  jmp     short loc_140034CA8
0x140034c86  mov     rcx, [rdi]
0x140034c89  lea     rdx, aMalformedJson; "malformed JSON"
0x140034c90  or      r8, 0FFFFFFFFFFFFFFFFh
0x140034c94  mov     dword ptr [rdi+24h], 1
0x140034c9b  mov     r9b, 1
0x140034c9e  mov     [rsp+58h+var_38], r8
0x140034ca3  call    sqlite3VdbeMemSetStr
0x140034ca8  mov     rcx, rsi
0x140034cab  call    jsonParseReset
0x140034cb0  mov     eax, 1
0x140034cb5  add     rsp, 30h
0x140034cb9  pop     r14
0x140034cbb  pop     rdi
0x140034cbc  pop     rsi
0x140034cbd  pop     rbp
0x140034cbe  pop     rbx
0x140034cbf  retn
```
