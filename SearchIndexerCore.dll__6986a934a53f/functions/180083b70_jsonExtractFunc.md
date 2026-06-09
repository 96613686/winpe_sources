# jsonExtractFunc

- ea: `0x180083b70`
- end: `0x180083f3b`
- name: `jsonExtractFunc`
- size: `971`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config`

## callees

- `0x18001eb90`
- `0x180024b60`
- `0x180078968`
- `0x1800789c0`
- `0x180081d70`
- `0x180081f40`
- `0x180081f90`
- `0x180081fdc`
- `0x180082760`
- `0x180083b70`
- `0x180084730`
- `0x180085450`
- `0x18008548c`
- `0x180085b84`
- `0x180086088`
- `0x1800864e4`
- `0x180086530`
- `0x18008671c`
- `0x18009d650`
- `0x18009d790`
- `0x18009ed10`

## string_xrefs

- `0x180083eb3`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonExtractFunc(__int64 a1, int a2, __int64 *a3)
{
  __int64 *v3; // rdi
  __int64 result; // rax
  __int64 v7; // r14
  __int64 v8; // rdx
  char v9; // si
  int i; // r13d
  __int64 v11; // rax
  _BYTE *v12; // rsi
  _BYTE *v13; // rcx
  __int64 v14; // rdi
  unsigned int v15; // edi
  unsigned int v16; // r8d
  const char *v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  char v20; // [rsp+20h] [rbp-89h]
  __int64 v22; // [rsp+30h] [rbp-79h] BYREF
  _BYTE *v23; // [rsp+38h] [rbp-71h]
  __int64 v24; // [rsp+40h] [rbp-69h]
  __int64 v25; // [rsp+48h] [rbp-61h]
  __int16 v26; // [rsp+50h] [rbp-59h]
  _BYTE v27[110]; // [rsp+52h] [rbp-57h] BYREF

  v3 = a3;
  result = (__int64)memset_0(&v22, 0, 0x88u);
  if ( a2 < 2 )
    return result;
  result = jsonParseFuncArg(a1, *v3, 0);
  v7 = result;
  if ( !result )
    return result;
  v20 = sqlite3_user_data(a1);
  v9 = v20;
  v22 = a1;
  v23 = v27;
  v26 = 1;
  v24 = 100;
  v25 = 0;
  if ( a2 > 2 )
    jsonAppendChar(&v22, 91);
  for ( i = 1; i < a2; ++i )
  {
    LOBYTE(v8) = 1;
    v11 = sqlite3ValueText(v3[i], v8);
    v12 = (_BYTE *)v11;
    if ( !v11 )
      goto LABEL_46;
    v14 = (int)sqlite3Strlen30(v11);
    if ( *v13 == 36 )
    {
      v15 = jsonLookupStep(v7, 0, v13 + 1, 0);
      goto LABEL_26;
    }
    if ( (v20 & 3) == 0 )
      goto LABEL_42;
    v22 = a1;
    v23 = v27;
    v26 = 1;
    v24 = 100;
    v25 = 0;
    if ( *((_BYTE *)qword_1800B5270 + (*(_WORD *)(a3[i] + 20) & 0x3F)) == 1 )
    {
      jsonAppendRawNZ(&v22, "[", 1u);
      jsonAppendRaw(&v22, v12, v14);
      v16 = 2;
      v17 = "]";
LABEL_24:
      jsonAppendRawNZ(&v22, v17, v16);
      goto LABEL_25;
    }
    v18 = 0;
    if ( (int)v14 <= 0 )
    {
LABEL_17:
      if ( (_DWORD)v18 == (_DWORD)v14 )
      {
        jsonAppendRawNZ(&v22, ".", 1u);
        goto LABEL_22;
      }
    }
    else
    {
      while ( 1 )
      {
        v19 = (unsigned __int8)v12[v18];
        if ( (*((_BYTE *)&qword_1800B4FF0 + v19) & 6) == 0 && (_BYTE)v19 != 95 )
          break;
        v18 = (unsigned int)(v18 + 1);
        if ( (int)v18 >= (int)v14 )
          goto LABEL_17;
      }
    }
    if ( *v12 != 91 || (int)v14 < 3 || v12[v14 - 1] != 93 )
    {
      jsonAppendRawNZ(&v22, ".\"", 2u);
      jsonAppendRaw(&v22, v12, v14);
      v16 = 1;
      v17 = "\"";
      goto LABEL_24;
    }
LABEL_22:
    jsonAppendRaw(&v22, v12, v14);
LABEL_25:
    jsonStringTerminate(&v22);
    v15 = jsonLookupStep(v7, 0, v23, 0);
    jsonStringReset(&v22);
LABEL_26:
    if ( v15 >= *(_DWORD *)(v7 + 8) )
    {
      if ( v15 != -2 )
      {
        if ( v15 == -1 )
        {
          sqlite3_result_error(a1, "malformed JSON", 0xFFFFFFFFLL);
          goto LABEL_46;
        }
LABEL_42:
        jsonBadPathError(a1);
        goto LABEL_46;
      }
      if ( a2 == 2 )
        goto LABEL_46;
      jsonAppendSeparator(&v22);
      jsonAppendRawNZ(&v22, "null", 4u);
      goto LABEL_38;
    }
    if ( a2 != 2 )
    {
      jsonAppendSeparator(&v22);
      jsonTranslateBlobToText(v7, v15, &v22);
LABEL_38:
      v9 = v20;
      goto LABEL_39;
    }
    v9 = v20;
    if ( (v20 & 1) != 0 )
    {
      v22 = a1;
      v23 = v27;
      v26 = 1;
      v24 = 100;
      v25 = 0;
      jsonTranslateBlobToText(v7, v15, &v22);
      jsonReturnString(&v22, 0, 0);
      jsonStringReset(&v22);
LABEL_30:
      sqlite3_result_subtype(a1, 74);
      goto LABEL_39;
    }
    jsonReturnFromBlob((__int64 *)v7, v15, a1, 0);
    if ( (v20 & 0xA) == 0 && (*(_BYTE *)(v15 + *(_QWORD *)v7) & 0xFu) >= 0xB )
      goto LABEL_30;
LABEL_39:
    v3 = a3;
  }
  if ( a2 > 2 )
  {
    jsonAppendChar(&v22, 93);
    jsonReturnString(&v22, 0, 0);
    if ( (v9 & 8) == 0 )
      sqlite3_result_subtype(a1, 74);
  }
LABEL_46:
  jsonStringReset(&v22);
  return jsonParseFree(v7);
}

```

## disassembly

```asm
0x180083b70  mov     [rsp-8+arg_8], rbx
0x180083b75  push    rbp
0x180083b76  push    rsi
0x180083b77  push    rdi
0x180083b78  push    r12
0x180083b7a  push    r13
0x180083b7c  push    r14
0x180083b7e  push    r15
0x180083b80  lea     rbp, [rsp-27h]
0x180083b85  sub     rsp, 0D0h
0x180083b8c  mov     rax, cs:__security_cookie
0x180083b93  xor     rax, rsp
0x180083b96  mov     [rbp+57h+var_40], rax
0x180083b9a  mov     rdi, r8
0x180083b9d  mov     [rsp+100h+var_D8], r8
0x180083ba2  mov     r15d, edx
0x180083ba5  mov     rbx, rcx
0x180083ba8  xor     edx, edx; Val
0x180083baa  lea     rcx, [rbp+57h+var_D0]; void *
0x180083bae  mov     r8d, 88h; Size
0x180083bb4  call    memset_0
0x180083bb9  cmp     r15d, 2
0x180083bbd  jl      loc_180083F14
0x180083bc3  mov     rdx, [rdi]
0x180083bc6  xor     r8d, r8d
0x180083bc9  mov     rcx, rbx
0x180083bcc  call    jsonParseFuncArg
0x180083bd1  mov     r14, rax
0x180083bd4  test    rax, rax
0x180083bd7  jz      loc_180083F14
0x180083bdd  mov     rcx, rbx
0x180083be0  call    sqlite3_user_data
0x180083be5  mov     [rsp+100h+var_E0], rax
0x180083bea  mov     rsi, rax
0x180083bed  mov     [rbp+57h+var_D0], rbx
0x180083bf1  lea     rax, [rbp+57h+var_AE]
0x180083bf5  mov     [rbp+57h+var_C8], rax
0x180083bf9  mov     r12d, 1
0x180083bff  mov     [rbp+57h+var_B0], 1
0x180083c05  mov     [rbp+57h+var_C0], 64h ; 'd'
0x180083c0d  mov     [rbp+57h+var_B8], 0
0x180083c15  cmp     r15d, 2
0x180083c19  jle     short loc_180083C26
0x180083c1b  mov     dl, 5Bh ; '['
0x180083c1d  lea     rcx, [rbp+57h+var_D0]
0x180083c21  call    jsonAppendChar
0x180083c26  mov     r13d, r12d
0x180083c29  cmp     r13d, r15d
0x180083c2c  jge     loc_180083ED1
0x180083c32  movsxd  r12, r13d
0x180083c35  mov     dl, 1
0x180083c37  mov     rcx, [rdi+r12*8]
0x180083c3b  call    sqlite3ValueText
0x180083c40  mov     rsi, rax
0x180083c43  test    rax, rax
0x180083c46  jz      loc_180083F03
0x180083c4c  mov     rcx, rax
0x180083c4f  call    sqlite3Strlen30
0x180083c54  cmp     byte ptr [rcx], 24h ; '$'
0x180083c57  movsxd  rdi, eax
0x180083c5a  jnz     short loc_180083C7A
0x180083c5c  lea     r8, [rcx+1]
0x180083c60  xor     r9d, r9d
0x180083c63  mov     rcx, r14
0x180083c66  xor     edx, edx
0x180083c68  call    jsonLookupStep
0x180083c6d  mov     edi, eax
0x180083c6f  mov     r12d, 1
0x180083c75  jmp     loc_180083DBA
0x180083c7a  test    byte ptr [rsp+100h+var_E0], 3
0x180083c7f  jz      loc_180083EC4
0x180083c85  lea     rax, [rbp+57h+var_AE]
0x180083c89  mov     [rbp+57h+var_D0], rbx
0x180083c8d  mov     [rbp+57h+var_C8], rax
0x180083c91  lea     r8, __ImageBase
0x180083c98  mov     rax, [rsp+100h+var_D8]
0x180083c9d  mov     [rbp+57h+var_B0], 1
0x180083ca3  mov     [rbp+57h+var_C0], 64h ; 'd'
0x180083cab  mov     [rbp+57h+var_B8], 0
0x180083cb3  mov     rax, [rax+r12*8]
0x180083cb7  mov     r12d, 1
0x180083cbd  movzx   ecx, word ptr [rax+14h]
0x180083cc1  and     ecx, 3Fh
0x180083cc4  cmp     [rcx+r8+0B5270h], r12b
0x180083ccc  jnz     short loc_180083D01
0x180083cce  mov     r8d, r12d
0x180083cd1  lea     rdx, asc_1800BCEB0; "["
0x180083cd8  lea     rcx, [rbp+57h+var_D0]
0x180083cdc  call    jsonAppendRawNZ
0x180083ce1  mov     r8d, edi
0x180083ce4  lea     rcx, [rbp+57h+var_D0]
0x180083ce8  mov     rdx, rsi
0x180083ceb  call    jsonAppendRaw
0x180083cf0  lea     r8d, [r12+1]
0x180083cf5  lea     rdx, asc_1800B8968; "]"
0x180083cfc  jmp     loc_180083D8C
0x180083d01  xor     ecx, ecx
0x180083d03  test    edi, edi
0x180083d05  jle     short loc_180083D22
0x180083d07  movzx   edx, byte ptr [rcx+rsi]
0x180083d0b  test    byte ptr [rdx+r8+0B4FF0h], 6
0x180083d14  jnz     short loc_180083D1B
0x180083d16  cmp     dl, 5Fh ; '_'
0x180083d19  jnz     short loc_180083D3B
0x180083d1b  add     ecx, r12d
0x180083d1e  cmp     ecx, edi
0x180083d20  jl      short loc_180083D07
0x180083d22  cmp     ecx, edi
0x180083d24  jnz     short loc_180083D3B
0x180083d26  mov     r8d, r12d
0x180083d29  lea     rdx, asc_1800B53A0; "."
0x180083d30  lea     rcx, [rbp+57h+var_D0]
0x180083d34  call    jsonAppendRawNZ
0x180083d39  jmp     short loc_180083D4C
0x180083d3b  cmp     byte ptr [rsi], 5Bh ; '['
0x180083d3e  jnz     short loc_180083D5D
0x180083d40  cmp     edi, 3
0x180083d43  jl      short loc_180083D5D
0x180083d45  cmp     byte ptr [rdi+rsi-1], 5Dh ; ']'
0x180083d4a  jnz     short loc_180083D5D
0x180083d4c  mov     r8d, edi
0x180083d4f  lea     rcx, [rbp+57h+var_D0]
0x180083d53  mov     rdx, rsi
0x180083d56  call    jsonAppendRaw
0x180083d5b  jmp     short loc_180083D95
0x180083d5d  mov     r8d, 2
0x180083d63  lea     rdx, asc_1800BCEB4; ".\""
0x180083d6a  lea     rcx, [rbp+57h+var_D0]
0x180083d6e  call    jsonAppendRawNZ
0x180083d73  mov     r8d, edi
0x180083d76  lea     rcx, [rbp+57h+var_D0]
0x180083d7a  mov     rdx, rsi
0x180083d7d  call    jsonAppendRaw
0x180083d82  mov     r8d, r12d
0x180083d85  lea     rdx, asc_1800BCEB8; "\""
0x180083d8c  lea     rcx, [rbp+57h+var_D0]
0x180083d90  call    jsonAppendRawNZ
0x180083d95  lea     rcx, [rbp+57h+var_D0]
0x180083d99  call    jsonStringTerminate
0x180083d9e  mov     r8, [rbp+57h+var_C8]
0x180083da2  xor     r9d, r9d
0x180083da5  xor     edx, edx
0x180083da7  mov     rcx, r14
0x180083daa  call    jsonLookupStep
0x180083daf  lea     rcx, [rbp+57h+var_D0]
0x180083db3  mov     edi, eax
0x180083db5  call    jsonStringReset
0x180083dba  cmp     edi, [r14+8]
0x180083dbe  jnb     loc_180083E6A
0x180083dc4  cmp     r15d, 2
0x180083dc8  jnz     loc_180083E51
0x180083dce  mov     rsi, [rsp+100h+var_E0]
0x180083dd3  mov     edx, edi
0x180083dd5  mov     rcx, r14
0x180083dd8  test    r12b, sil
0x180083ddb  jz      short loc_180083E2E
0x180083ddd  lea     rax, [rbp+57h+var_AE]
0x180083de1  mov     [rbp+57h+var_D0], rbx
0x180083de5  lea     r8, [rbp+57h+var_D0]
0x180083de9  mov     [rbp+57h+var_C8], rax
0x180083ded  mov     [rbp+57h+var_B0], 1
0x180083df3  mov     [rbp+57h+var_C0], 64h ; 'd'
0x180083dfb  mov     [rbp+57h+var_B8], 0
0x180083e03  call    jsonTranslateBlobToText
0x180083e08  xor     r8d, r8d
0x180083e0b  lea     rcx, [rbp+57h+var_D0]
0x180083e0f  xor     edx, edx
0x180083e11  call    jsonReturnString
0x180083e16  lea     rcx, [rbp+57h+var_D0]
0x180083e1a  call    jsonStringReset
0x180083e1f  mov     edx, 4Ah ; 'J'
0x180083e24  mov     rcx, rbx
0x180083e27  call    sqlite3_result_subtype
0x180083e2c  jmp     short loc_180083E9D
0x180083e2e  xor     r9d, r9d
0x180083e31  mov     r8, rbx
0x180083e34  call    jsonReturnFromBlob
0x180083e39  test    sil, 0Ah
0x180083e3d  jnz     short loc_180083E9D
0x180083e3f  mov     rax, [r14]
0x180083e42  mov     ecx, edi
0x180083e44  mov     dl, [rcx+rax]
0x180083e47  and     dl, 0Fh
0x180083e4a  cmp     dl, 0Bh
0x180083e4d  jb      short loc_180083E9D
0x180083e4f  jmp     short loc_180083E1F
0x180083e51  lea     rcx, [rbp+57h+var_D0]
0x180083e55  call    jsonAppendSeparator
0x180083e5a  lea     r8, [rbp+57h+var_D0]
0x180083e5e  mov     edx, edi
0x180083e60  mov     rcx, r14
0x180083e63  call    jsonTranslateBlobToText
0x180083e68  jmp     short loc_180083E98
0x180083e6a  cmp     edi, 0FFFFFFFEh
0x180083e6d  jnz     short loc_180083EAA
0x180083e6f  cmp     r15d, 2
0x180083e73  jz      loc_180083F03
0x180083e79  lea     rcx, [rbp+57h+var_D0]
0x180083e7d  call    jsonAppendSeparator
0x180083e82  mov     r8d, 4
0x180083e88  lea     rdx, aNull_2; "null"
0x180083e8f  lea     rcx, [rbp+57h+var_D0]
0x180083e93  call    jsonAppendRawNZ
0x180083e98  mov     rsi, [rsp+100h+var_E0]
0x180083e9d  mov     rdi, [rsp+100h+var_D8]
0x180083ea2  add     r13d, r12d
0x180083ea5  jmp     loc_180083C29
0x180083eaa  cmp     edi, 0FFFFFFFFh
0x180083ead  jnz     short loc_180083EC4
0x180083eaf  or      r8d, 0FFFFFFFFh
0x180083eb3  lea     rdx, aMalformedJson; "malformed JSON"
0x180083eba  mov     rcx, rbx
0x180083ebd  call    sqlite3_result_error
0x180083ec2  jmp     short loc_180083F03
0x180083ec4  mov     rdx, rsi
0x180083ec7  mov     rcx, rbx
0x180083eca  call    jsonBadPathError
0x180083ecf  jmp     short loc_180083F03
0x180083ed1  cmp     r15d, 2
0x180083ed5  jle     short loc_180083F03
0x180083ed7  mov     dl, 5Dh ; ']'
0x180083ed9  lea     rcx, [rbp+57h+var_D0]
0x180083edd  call    jsonAppendChar
0x180083ee2  xor     r8d, r8d
0x180083ee5  lea     rcx, [rbp+57h+var_D0]
0x180083ee9  xor     edx, edx
0x180083eeb  call    jsonReturnString
0x180083ef0  test    sil, 8
0x180083ef4  jnz     short loc_180083F03
0x180083ef6  mov     edx, 4Ah ; 'J'
0x180083efb  mov     rcx, rbx
0x180083efe  call    sqlite3_result_subtype
0x180083f03  lea     rcx, [rbp+57h+var_D0]
0x180083f07  call    jsonStringReset
0x180083f0c  mov     rcx, r14
0x180083f0f  call    jsonParseFree
0x180083f14  mov     rcx, [rbp+57h+var_40]
0x180083f18  xor     rcx, rsp; StackCookie
0x180083f1b  call    __security_check_cookie
0x180083f20  mov     rbx, [rsp+100h+arg_8]
0x180083f28  add     rsp, 0D0h
0x180083f2f  pop     r15
0x180083f31  pop     r14
0x180083f33  pop     r13
0x180083f35  pop     r12
0x180083f37  pop     rdi
0x180083f38  pop     rsi
0x180083f39  pop     rbp
0x180083f3a  retn
```
