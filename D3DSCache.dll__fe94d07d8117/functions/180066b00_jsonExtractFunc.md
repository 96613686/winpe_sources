# jsonExtractFunc

- ea: `0x180066b00`
- end: `0x180066ecb`
- name: `jsonExtractFunc`
- size: `971`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config`

## callees

- `0x18002b81c`
- `0x180042dc4`
- `0x1800449f0`
- `0x180045374`
- `0x180064d60`
- `0x180064f30`
- `0x180064f80`
- `0x180064fcc`
- `0x180065750`
- `0x180066b00`
- `0x1800676c0`
- `0x1800683e0`
- `0x18006841c`
- `0x180068b14`
- `0x180069018`
- `0x180069474`
- `0x1800694c0`
- `0x1800696ac`
- `0x180096df0`
- `0x180096fb0`
- `0x180098a60`

## string_xrefs

- `0x180066e43`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonExtractFunc(__int64 a1, int a2, __int64 *a3)
{
  __int64 *v3; // rdi
  __int64 result; // rax
  __int64 v7; // rdx
  __int64 v8; // r14
  __int64 v9; // rdx
  char v10; // si
  int i; // r13d
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  _BYTE *v15; // rsi
  _BYTE *v16; // rcx
  __int64 v17; // rdi
  unsigned int v18; // edi
  __int64 v19; // r8
  const char *v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rdx
  char v23; // [rsp+20h] [rbp-89h]
  __int64 v25; // [rsp+30h] [rbp-79h] BYREF
  _BYTE *v26; // [rsp+38h] [rbp-71h]
  __int64 v27; // [rsp+40h] [rbp-69h]
  __int64 v28; // [rsp+48h] [rbp-61h]
  __int16 v29; // [rsp+50h] [rbp-59h]
  _BYTE v30[110]; // [rsp+52h] [rbp-57h] BYREF

  v3 = a3;
  result = (__int64)memset_0(&v25, 0, 0x88u);
  if ( a2 < 2 )
    return result;
  result = jsonParseFuncArg(a1, *v3, 0);
  v8 = result;
  if ( !result )
    return result;
  v23 = sqlite3_user_data(a1, v7);
  v10 = v23;
  v25 = a1;
  v26 = v30;
  v29 = 1;
  v27 = 100;
  v28 = 0;
  if ( a2 > 2 )
  {
    LOBYTE(v9) = 91;
    jsonAppendChar(&v25, v9);
  }
  for ( i = 1; i < a2; ++i )
  {
    LOBYTE(v9) = 1;
    v12 = sqlite3ValueText(v3[i], v9);
    v15 = (_BYTE *)v12;
    if ( !v12 )
      goto LABEL_46;
    v17 = (int)sqlite3Strlen30(v12, v13, v14);
    if ( *v16 == 36 )
    {
      v18 = jsonLookupStep(v8, 0, v16 + 1, 0);
      goto LABEL_26;
    }
    if ( (v23 & 3) == 0 )
      goto LABEL_42;
    v25 = a1;
    v26 = v30;
    v29 = 1;
    v27 = 100;
    v28 = 0;
    if ( *((_BYTE *)qword_1800B9DC0 + (*(_WORD *)(a3[i] + 20) & 0x3F)) == 1 )
    {
      jsonAppendRawNZ(&v25, "[", 1);
      jsonAppendRaw(&v25, v15, (unsigned int)v17);
      v19 = 2;
      v20 = "]";
LABEL_24:
      jsonAppendRawNZ(&v25, v20, v19);
      goto LABEL_25;
    }
    v21 = 0;
    if ( (int)v17 <= 0 )
    {
LABEL_17:
      if ( (_DWORD)v21 == (_DWORD)v17 )
      {
        jsonAppendRawNZ(&v25, ".", 1);
        goto LABEL_22;
      }
    }
    else
    {
      while ( 1 )
      {
        v22 = (unsigned __int8)v15[v21];
        if ( (*((_BYTE *)&qword_1800ADE90 + v22) & 6) == 0 && (_BYTE)v22 != 95 )
          break;
        v21 = (unsigned int)(v21 + 1);
        if ( (int)v21 >= (int)v17 )
          goto LABEL_17;
      }
    }
    if ( *v15 != 91 || (int)v17 < 3 || v15[v17 - 1] != 93 )
    {
      jsonAppendRawNZ(&v25, ".\"", 2);
      jsonAppendRaw(&v25, v15, (unsigned int)v17);
      v19 = 1;
      v20 = "\"";
      goto LABEL_24;
    }
LABEL_22:
    jsonAppendRaw(&v25, v15, (unsigned int)v17);
LABEL_25:
    jsonStringTerminate(&v25);
    v18 = jsonLookupStep(v8, 0, v26, 0);
    jsonStringReset(&v25);
LABEL_26:
    if ( v18 >= *(_DWORD *)(v8 + 8) )
    {
      if ( v18 != -2 )
      {
        if ( v18 == -1 )
        {
          sqlite3_result_error(a1, "malformed JSON", 0xFFFFFFFFLL);
          goto LABEL_46;
        }
LABEL_42:
        jsonBadPathError(a1, v15);
        goto LABEL_46;
      }
      if ( a2 == 2 )
        goto LABEL_46;
      jsonAppendSeparator(&v25);
      jsonAppendRawNZ(&v25, "null", 4);
      goto LABEL_38;
    }
    if ( a2 != 2 )
    {
      jsonAppendSeparator(&v25);
      jsonTranslateBlobToText(v8, v18, &v25);
LABEL_38:
      v10 = v23;
      goto LABEL_39;
    }
    v10 = v23;
    if ( (v23 & 1) != 0 )
    {
      v25 = a1;
      v26 = v30;
      v29 = 1;
      v27 = 100;
      v28 = 0;
      jsonTranslateBlobToText(v8, v18, &v25);
      jsonReturnString(&v25, 0, 0);
      jsonStringReset(&v25);
LABEL_30:
      sqlite3_result_subtype(a1, 74);
      goto LABEL_39;
    }
    jsonReturnFromBlob((__int64 *)v8, v18, a1, 0);
    if ( (v23 & 0xA) == 0 && (*(_BYTE *)(v18 + *(_QWORD *)v8) & 0xFu) >= 0xB )
      goto LABEL_30;
LABEL_39:
    v3 = a3;
  }
  if ( a2 > 2 )
  {
    LOBYTE(v9) = 93;
    jsonAppendChar(&v25, v9);
    jsonReturnString(&v25, 0, 0);
    if ( (v10 & 8) == 0 )
      sqlite3_result_subtype(a1, 74);
  }
LABEL_46:
  jsonStringReset(&v25);
  return jsonParseFree(v8);
}

```

## disassembly

```asm
0x180066b00  mov     [rsp-8+arg_8], rbx
0x180066b05  push    rbp
0x180066b06  push    rsi
0x180066b07  push    rdi
0x180066b08  push    r12
0x180066b0a  push    r13
0x180066b0c  push    r14
0x180066b0e  push    r15
0x180066b10  lea     rbp, [rsp-27h]
0x180066b15  sub     rsp, 0D0h
0x180066b1c  mov     rax, cs:__security_cookie
0x180066b23  xor     rax, rsp
0x180066b26  mov     [rbp+57h+var_40], rax
0x180066b2a  mov     rdi, r8
0x180066b2d  mov     [rsp+100h+var_D8], r8
0x180066b32  mov     r15d, edx
0x180066b35  mov     rbx, rcx
0x180066b38  xor     edx, edx; Val
0x180066b3a  lea     rcx, [rbp+57h+var_D0]; void *
0x180066b3e  mov     r8d, 88h; Size
0x180066b44  call    memset_0
0x180066b49  cmp     r15d, 2
0x180066b4d  jl      loc_180066EA4
0x180066b53  mov     rdx, [rdi]
0x180066b56  xor     r8d, r8d
0x180066b59  mov     rcx, rbx
0x180066b5c  call    jsonParseFuncArg
0x180066b61  mov     r14, rax
0x180066b64  test    rax, rax
0x180066b67  jz      loc_180066EA4
0x180066b6d  mov     rcx, rbx
0x180066b70  call    sqlite3_user_data
0x180066b75  mov     [rsp+100h+var_E0], rax
0x180066b7a  mov     rsi, rax
0x180066b7d  mov     [rbp+57h+var_D0], rbx
0x180066b81  lea     rax, [rbp+57h+var_AE]
0x180066b85  mov     [rbp+57h+var_C8], rax
0x180066b89  mov     r12d, 1
0x180066b8f  mov     [rbp+57h+var_B0], 1
0x180066b95  mov     [rbp+57h+var_C0], 64h ; 'd'
0x180066b9d  mov     [rbp+57h+var_B8], 0
0x180066ba5  cmp     r15d, 2
0x180066ba9  jle     short loc_180066BB6
0x180066bab  mov     dl, 5Bh ; '['
0x180066bad  lea     rcx, [rbp+57h+var_D0]
0x180066bb1  call    jsonAppendChar
0x180066bb6  mov     r13d, r12d
0x180066bb9  cmp     r13d, r15d
0x180066bbc  jge     loc_180066E61
0x180066bc2  movsxd  r12, r13d
0x180066bc5  mov     dl, 1
0x180066bc7  mov     rcx, [rdi+r12*8]
0x180066bcb  call    sqlite3ValueText
0x180066bd0  mov     rsi, rax
0x180066bd3  test    rax, rax
0x180066bd6  jz      loc_180066E93
0x180066bdc  mov     rcx, rax
0x180066bdf  call    sqlite3Strlen30
0x180066be4  cmp     byte ptr [rcx], 24h ; '$'
0x180066be7  movsxd  rdi, eax
0x180066bea  jnz     short loc_180066C0A
0x180066bec  lea     r8, [rcx+1]
0x180066bf0  xor     r9d, r9d
0x180066bf3  mov     rcx, r14
0x180066bf6  xor     edx, edx
0x180066bf8  call    jsonLookupStep
0x180066bfd  mov     edi, eax
0x180066bff  mov     r12d, 1
0x180066c05  jmp     loc_180066D4A
0x180066c0a  test    byte ptr [rsp+100h+var_E0], 3
0x180066c0f  jz      loc_180066E54
0x180066c15  lea     rax, [rbp+57h+var_AE]
0x180066c19  mov     [rbp+57h+var_D0], rbx
0x180066c1d  mov     [rbp+57h+var_C8], rax
0x180066c21  lea     r8, __ImageBase
0x180066c28  mov     rax, [rsp+100h+var_D8]
0x180066c2d  mov     [rbp+57h+var_B0], 1
0x180066c33  mov     [rbp+57h+var_C0], 64h ; 'd'
0x180066c3b  mov     [rbp+57h+var_B8], 0
0x180066c43  mov     rax, [rax+r12*8]
0x180066c47  mov     r12d, 1
0x180066c4d  movzx   ecx, word ptr [rax+14h]
0x180066c51  and     ecx, 3Fh
0x180066c54  cmp     [rcx+r8+0B9DC0h], r12b
0x180066c5c  jnz     short loc_180066C91
0x180066c5e  mov     r8d, r12d
0x180066c61  lea     rdx, asc_1800B5E80; "["
0x180066c68  lea     rcx, [rbp+57h+var_D0]
0x180066c6c  call    jsonAppendRawNZ
0x180066c71  mov     r8d, edi
0x180066c74  lea     rcx, [rbp+57h+var_D0]
0x180066c78  mov     rdx, rsi
0x180066c7b  call    jsonAppendRaw
0x180066c80  lea     r8d, [r12+1]
0x180066c85  lea     rdx, asc_1800B0A30; "]"
0x180066c8c  jmp     loc_180066D1C
0x180066c91  xor     ecx, ecx
0x180066c93  test    edi, edi
0x180066c95  jle     short loc_180066CB2
0x180066c97  movzx   edx, byte ptr [rcx+rsi]
0x180066c9b  test    byte ptr [rdx+r8+0ADE90h], 6
0x180066ca4  jnz     short loc_180066CAB
0x180066ca6  cmp     dl, 5Fh ; '_'
0x180066ca9  jnz     short loc_180066CCB
0x180066cab  add     ecx, r12d
0x180066cae  cmp     ecx, edi
0x180066cb0  jl      short loc_180066C97
0x180066cb2  cmp     ecx, edi
0x180066cb4  jnz     short loc_180066CCB
0x180066cb6  mov     r8d, r12d
0x180066cb9  lea     rdx, asc_1800AF338; "."
0x180066cc0  lea     rcx, [rbp+57h+var_D0]
0x180066cc4  call    jsonAppendRawNZ
0x180066cc9  jmp     short loc_180066CDC
0x180066ccb  cmp     byte ptr [rsi], 5Bh ; '['
0x180066cce  jnz     short loc_180066CED
0x180066cd0  cmp     edi, 3
0x180066cd3  jl      short loc_180066CED
0x180066cd5  cmp     byte ptr [rdi+rsi-1], 5Dh ; ']'
0x180066cda  jnz     short loc_180066CED
0x180066cdc  mov     r8d, edi
0x180066cdf  lea     rcx, [rbp+57h+var_D0]
0x180066ce3  mov     rdx, rsi
0x180066ce6  call    jsonAppendRaw
0x180066ceb  jmp     short loc_180066D25
0x180066ced  mov     r8d, 2
0x180066cf3  lea     rdx, asc_1800B5E84; ".\""
0x180066cfa  lea     rcx, [rbp+57h+var_D0]
0x180066cfe  call    jsonAppendRawNZ
0x180066d03  mov     r8d, edi
0x180066d06  lea     rcx, [rbp+57h+var_D0]
0x180066d0a  mov     rdx, rsi
0x180066d0d  call    jsonAppendRaw
0x180066d12  mov     r8d, r12d
0x180066d15  lea     rdx, asc_1800B5E88; "\""
0x180066d1c  lea     rcx, [rbp+57h+var_D0]
0x180066d20  call    jsonAppendRawNZ
0x180066d25  lea     rcx, [rbp+57h+var_D0]
0x180066d29  call    jsonStringTerminate
0x180066d2e  mov     r8, [rbp+57h+var_C8]
0x180066d32  xor     r9d, r9d
0x180066d35  xor     edx, edx
0x180066d37  mov     rcx, r14
0x180066d3a  call    jsonLookupStep
0x180066d3f  lea     rcx, [rbp+57h+var_D0]
0x180066d43  mov     edi, eax
0x180066d45  call    jsonStringReset
0x180066d4a  cmp     edi, [r14+8]
0x180066d4e  jnb     loc_180066DFA
0x180066d54  cmp     r15d, 2
0x180066d58  jnz     loc_180066DE1
0x180066d5e  mov     rsi, [rsp+100h+var_E0]
0x180066d63  mov     edx, edi
0x180066d65  mov     rcx, r14
0x180066d68  test    r12b, sil
0x180066d6b  jz      short loc_180066DBE
0x180066d6d  lea     rax, [rbp+57h+var_AE]
0x180066d71  mov     [rbp+57h+var_D0], rbx
0x180066d75  lea     r8, [rbp+57h+var_D0]
0x180066d79  mov     [rbp+57h+var_C8], rax
0x180066d7d  mov     [rbp+57h+var_B0], 1
0x180066d83  mov     [rbp+57h+var_C0], 64h ; 'd'
0x180066d8b  mov     [rbp+57h+var_B8], 0
0x180066d93  call    jsonTranslateBlobToText
0x180066d98  xor     r8d, r8d
0x180066d9b  lea     rcx, [rbp+57h+var_D0]
0x180066d9f  xor     edx, edx
0x180066da1  call    jsonReturnString
0x180066da6  lea     rcx, [rbp+57h+var_D0]
0x180066daa  call    jsonStringReset
0x180066daf  mov     edx, 4Ah ; 'J'
0x180066db4  mov     rcx, rbx
0x180066db7  call    sqlite3_result_subtype
0x180066dbc  jmp     short loc_180066E2D
0x180066dbe  xor     r9d, r9d
0x180066dc1  mov     r8, rbx
0x180066dc4  call    jsonReturnFromBlob
0x180066dc9  test    sil, 0Ah
0x180066dcd  jnz     short loc_180066E2D
0x180066dcf  mov     rax, [r14]
0x180066dd2  mov     ecx, edi
0x180066dd4  mov     dl, [rcx+rax]
0x180066dd7  and     dl, 0Fh
0x180066dda  cmp     dl, 0Bh
0x180066ddd  jb      short loc_180066E2D
0x180066ddf  jmp     short loc_180066DAF
0x180066de1  lea     rcx, [rbp+57h+var_D0]
0x180066de5  call    jsonAppendSeparator
0x180066dea  lea     r8, [rbp+57h+var_D0]
0x180066dee  mov     edx, edi
0x180066df0  mov     rcx, r14
0x180066df3  call    jsonTranslateBlobToText
0x180066df8  jmp     short loc_180066E28
0x180066dfa  cmp     edi, 0FFFFFFFEh
0x180066dfd  jnz     short loc_180066E3A
0x180066dff  cmp     r15d, 2
0x180066e03  jz      loc_180066E93
0x180066e09  lea     rcx, [rbp+57h+var_D0]
0x180066e0d  call    jsonAppendSeparator
0x180066e12  mov     r8d, 4
0x180066e18  lea     rdx, aNull_3; "null"
0x180066e1f  lea     rcx, [rbp+57h+var_D0]
0x180066e23  call    jsonAppendRawNZ
0x180066e28  mov     rsi, [rsp+100h+var_E0]
0x180066e2d  mov     rdi, [rsp+100h+var_D8]
0x180066e32  add     r13d, r12d
0x180066e35  jmp     loc_180066BB9
0x180066e3a  cmp     edi, 0FFFFFFFFh
0x180066e3d  jnz     short loc_180066E54
0x180066e3f  or      r8d, 0FFFFFFFFh
0x180066e43  lea     rdx, aMalformedJson; "malformed JSON"
0x180066e4a  mov     rcx, rbx
0x180066e4d  call    sqlite3_result_error
0x180066e52  jmp     short loc_180066E93
0x180066e54  mov     rdx, rsi
0x180066e57  mov     rcx, rbx
0x180066e5a  call    jsonBadPathError
0x180066e5f  jmp     short loc_180066E93
0x180066e61  cmp     r15d, 2
0x180066e65  jle     short loc_180066E93
0x180066e67  mov     dl, 5Dh ; ']'
0x180066e69  lea     rcx, [rbp+57h+var_D0]
0x180066e6d  call    jsonAppendChar
0x180066e72  xor     r8d, r8d
0x180066e75  lea     rcx, [rbp+57h+var_D0]
0x180066e79  xor     edx, edx
0x180066e7b  call    jsonReturnString
0x180066e80  test    sil, 8
0x180066e84  jnz     short loc_180066E93
0x180066e86  mov     edx, 4Ah ; 'J'
0x180066e8b  mov     rcx, rbx
0x180066e8e  call    sqlite3_result_subtype
0x180066e93  lea     rcx, [rbp+57h+var_D0]
0x180066e97  call    jsonStringReset
0x180066e9c  mov     rcx, r14
0x180066e9f  call    jsonParseFree
0x180066ea4  mov     rcx, [rbp+57h+var_40]
0x180066ea8  xor     rcx, rsp; StackCookie
0x180066eab  call    __security_check_cookie
0x180066eb0  mov     rbx, [rsp+100h+arg_8]
0x180066eb8  add     rsp, 0D0h
0x180066ebf  pop     r15
0x180066ec1  pop     r14
0x180066ec3  pop     r13
0x180066ec5  pop     r12
0x180066ec7  pop     rdi
0x180066ec8  pop     rsi
0x180066ec9  pop     rbp
0x180066eca  retn
```
