# jsonExtractFunc

- ea: `0x180074920`
- end: `0x180074d02`
- name: `jsonExtractFunc`
- size: `994`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config`

## callees

- `0x180005810`
- `0x180028540`
- `0x180048740`
- `0x180068880`
- `0x18006910e`
- `0x180072b08`
- `0x180072cd8`
- `0x180072d28`
- `0x180072d74`
- `0x1800734f0`
- `0x180074920`
- `0x1800754f0`
- `0x180076240`
- `0x18007627c`
- `0x180076974`
- `0x180076e78`
- `0x1800772d4`
- `0x180077320`
- `0x18007750c`
- `0x18008f3f0`
- `0x18008f4f0`

## string_xrefs

- `0x180074c7b`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonExtractFunc(__int64 a1, int a2, __int64 *a3)
{
  __int64 *v3; // rsi
  __int64 result; // rax
  __int64 v7; // rdx
  __int64 v8; // r14
  __int64 v9; // rdx
  char v10; // bl
  int i; // r13d
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  _BYTE *v15; // rbx
  _BYTE *v16; // rcx
  __int64 v17; // rsi
  unsigned int v18; // esi
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
      goto LABEL_48;
    v17 = (int)sqlite3Strlen30(v12, v13, v14);
    if ( *v16 == 36 )
    {
      v18 = jsonLookupStep(v8, 0, v16 + 1, 0);
      goto LABEL_28;
    }
    if ( (v23 & 3) == 0 )
      goto LABEL_44;
    v25 = a1;
    v26 = v30;
    v29 = 1;
    v27 = 100;
    v28 = 0;
    if ( byte_18009EC50[*(_WORD *)(a3[i] + 20) & 0x3F] == 1 )
    {
      jsonAppendRawNZ(&v25, "[", 1);
      if ( *v15 == 45 )
        jsonAppendRawNZ(&v25, "#", 1);
      jsonAppendRaw(&v25, v15, (unsigned int)v17);
      v19 = 2;
      v20 = "]";
      goto LABEL_26;
    }
    v21 = 0;
    if ( (int)v17 <= 0 )
    {
LABEL_19:
      if ( (_DWORD)v21 == (_DWORD)v17 )
      {
        jsonAppendRawNZ(&v25, ".", 1);
        goto LABEL_24;
      }
    }
    else
    {
      while ( 1 )
      {
        v22 = (unsigned __int8)v15[v21];
        if ( (byte_18009E630[v22] & 6) == 0 && (_BYTE)v22 != 95 )
          break;
        v21 = (unsigned int)(v21 + 1);
        if ( (int)v21 >= (int)v17 )
          goto LABEL_19;
      }
    }
    if ( *v15 != 91 || (int)v17 < 3 || v15[v17 - 1] != 93 )
    {
      jsonAppendRawNZ(&v25, ".\"", 2);
      jsonAppendRaw(&v25, v15, (unsigned int)v17);
      v19 = 1;
      v20 = "\"";
LABEL_26:
      jsonAppendRawNZ(&v25, v20, v19);
      goto LABEL_27;
    }
LABEL_24:
    jsonAppendRaw(&v25, v15, (unsigned int)v17);
LABEL_27:
    jsonStringTerminate(&v25);
    v18 = jsonLookupStep(v8, 0, v26, 0);
    jsonStringReset(&v25);
LABEL_28:
    if ( v18 >= *(_DWORD *)(v8 + 8) )
    {
      if ( v18 != -2 )
      {
        if ( v18 == -1 )
        {
          sqlite3_result_error(a1, "malformed JSON", 0xFFFFFFFFLL);
          goto LABEL_48;
        }
LABEL_44:
        jsonBadPathError(a1, v15);
        goto LABEL_48;
      }
      if ( a2 == 2 )
        goto LABEL_48;
      jsonAppendSeparator(&v25);
      jsonAppendRawNZ(&v25, "null", 4);
      goto LABEL_40;
    }
    if ( a2 != 2 )
    {
      jsonAppendSeparator(&v25);
      jsonTranslateBlobToText(v8, v18, &v25);
LABEL_40:
      v10 = v23;
      goto LABEL_41;
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
LABEL_32:
      sqlite3_result_subtype(a1, 74);
      goto LABEL_41;
    }
    jsonReturnFromBlob((__int64 *)v8, v18, a1, 0);
    if ( (v23 & 0xA) == 0 && (*(_BYTE *)(v18 + *(_QWORD *)v8) & 0xFu) >= 0xB )
      goto LABEL_32;
LABEL_41:
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
LABEL_48:
  jsonStringReset(&v25);
  return jsonParseFree(v8);
}

```

## disassembly

```asm
0x180074920  mov     [rsp-8+arg_8], rbx
0x180074925  push    rbp
0x180074926  push    rsi
0x180074927  push    rdi
0x180074928  push    r12
0x18007492a  push    r13
0x18007492c  push    r14
0x18007492e  push    r15
0x180074930  lea     rbp, [rsp-27h]
0x180074935  sub     rsp, 0D0h
0x18007493c  mov     rax, cs:__security_cookie
0x180074943  xor     rax, rsp
0x180074946  mov     [rbp+57h+var_40], rax
0x18007494a  mov     rsi, r8
0x18007494d  mov     [rsp+100h+var_D8], r8
0x180074952  mov     r15d, edx
0x180074955  mov     rdi, rcx
0x180074958  xor     edx, edx; Val
0x18007495a  lea     rcx, [rbp+57h+var_D0]; void *
0x18007495e  mov     r8d, 88h; Size
0x180074964  call    memset_0
0x180074969  cmp     r15d, 2
0x18007496d  jl      loc_180074CDB
0x180074973  mov     rdx, [rsi]
0x180074976  xor     r8d, r8d
0x180074979  mov     rcx, rdi
0x18007497c  call    jsonParseFuncArg
0x180074981  mov     r14, rax
0x180074984  test    rax, rax
0x180074987  jz      loc_180074CDB
0x18007498d  mov     rcx, rdi
0x180074990  call    sqlite3_user_data
0x180074995  mov     [rsp+100h+var_E0], rax
0x18007499a  mov     rbx, rax
0x18007499d  mov     [rbp+57h+var_D0], rdi
0x1800749a1  lea     rax, [rbp+57h+var_AE]
0x1800749a5  mov     [rbp+57h+var_C8], rax
0x1800749a9  mov     r12d, 1
0x1800749af  mov     [rbp+57h+var_B0], 1
0x1800749b5  mov     [rbp+57h+var_C0], 64h ; 'd'
0x1800749bd  mov     [rbp+57h+var_B8], 0
0x1800749c5  cmp     r15d, 2
0x1800749c9  jle     short loc_1800749D6
0x1800749cb  mov     dl, 5Bh ; '['
0x1800749cd  lea     rcx, [rbp+57h+var_D0]
0x1800749d1  call    jsonAppendChar
0x1800749d6  mov     r13d, r12d
0x1800749d9  cmp     r13d, r15d
0x1800749dc  jge     loc_180074C99
0x1800749e2  movsxd  r12, r13d
0x1800749e5  mov     dl, 1
0x1800749e7  mov     rcx, [rsi+r12*8]
0x1800749eb  call    sqlite3ValueText
0x1800749f0  mov     rbx, rax
0x1800749f3  test    rax, rax
0x1800749f6  jz      loc_180074CCA
0x1800749fc  mov     rcx, rax
0x1800749ff  call    sqlite3Strlen30
0x180074a04  cmp     byte ptr [rcx], 24h ; '$'
0x180074a07  movsxd  rsi, eax
0x180074a0a  jnz     short loc_180074A2A
0x180074a0c  lea     r8, [rcx+1]
0x180074a10  xor     r9d, r9d
0x180074a13  mov     rcx, r14
0x180074a16  xor     edx, edx
0x180074a18  call    jsonLookupStep
0x180074a1d  mov     esi, eax
0x180074a1f  mov     r12d, 1
0x180074a25  jmp     loc_180074B83
0x180074a2a  test    byte ptr [rsp+100h+var_E0], 3
0x180074a2f  jz      loc_180074C8C
0x180074a35  lea     rax, [rbp+57h+var_AE]
0x180074a39  mov     [rbp+57h+var_D0], rdi
0x180074a3d  mov     [rbp+57h+var_C8], rax
0x180074a41  lea     r8, cs:180000000h
0x180074a48  mov     rax, [rsp+100h+var_D8]
0x180074a4d  mov     [rbp+57h+var_B0], 1
0x180074a53  mov     [rbp+57h+var_C0], 64h ; 'd'
0x180074a5b  mov     [rbp+57h+var_B8], 0
0x180074a63  mov     rax, [rax+r12*8]
0x180074a67  mov     r12d, 1
0x180074a6d  movzx   ecx, word ptr [rax+14h]
0x180074a71  and     ecx, 3Fh
0x180074a74  cmp     [rcx+r8+9EC50h], r12b
0x180074a7c  jnz     short loc_180074ACA
0x180074a7e  mov     r8d, r12d
0x180074a81  lea     rdx, asc_1800A6220; "["
0x180074a88  lea     rcx, [rbp+57h+var_D0]
0x180074a8c  call    jsonAppendRawNZ
0x180074a91  cmp     byte ptr [rbx], 2Dh ; '-'
0x180074a94  jnz     short loc_180074AA9
0x180074a96  mov     r8d, r12d
0x180074a99  lea     rdx, asc_1800A6224; "#"
0x180074aa0  lea     rcx, [rbp+57h+var_D0]
0x180074aa4  call    jsonAppendRawNZ
0x180074aa9  mov     r8d, esi
0x180074aac  lea     rcx, [rbp+57h+var_D0]
0x180074ab0  mov     rdx, rbx
0x180074ab3  call    jsonAppendRaw
0x180074ab8  mov     r8d, 2
0x180074abe  lea     rdx, asc_1800A1370; "]"
0x180074ac5  jmp     loc_180074B55
0x180074aca  xor     ecx, ecx
0x180074acc  test    esi, esi
0x180074ace  jle     short loc_180074AEB
0x180074ad0  movzx   edx, byte ptr [rcx+rbx]
0x180074ad4  test    byte ptr [rdx+r8+9E630h], 6
0x180074add  jnz     short loc_180074AE4
0x180074adf  cmp     dl, 5Fh ; '_'
0x180074ae2  jnz     short loc_180074B04
0x180074ae4  add     ecx, r12d
0x180074ae7  cmp     ecx, esi
0x180074ae9  jl      short loc_180074AD0
0x180074aeb  cmp     ecx, esi
0x180074aed  jnz     short loc_180074B04
0x180074aef  mov     r8d, r12d
0x180074af2  lea     rdx, asc_18009E5DC; "."
0x180074af9  lea     rcx, [rbp+57h+var_D0]
0x180074afd  call    jsonAppendRawNZ
0x180074b02  jmp     short loc_180074B15
0x180074b04  cmp     byte ptr [rbx], 5Bh ; '['
0x180074b07  jnz     short loc_180074B26
0x180074b09  cmp     esi, 3
0x180074b0c  jl      short loc_180074B26
0x180074b0e  cmp     byte ptr [rsi+rbx-1], 5Dh ; ']'
0x180074b13  jnz     short loc_180074B26
0x180074b15  mov     r8d, esi
0x180074b18  lea     rcx, [rbp+57h+var_D0]
0x180074b1c  mov     rdx, rbx
0x180074b1f  call    jsonAppendRaw
0x180074b24  jmp     short loc_180074B5E
0x180074b26  mov     r8d, 2
0x180074b2c  lea     rdx, asc_1800A6228; ".\""
0x180074b33  lea     rcx, [rbp+57h+var_D0]
0x180074b37  call    jsonAppendRawNZ
0x180074b3c  mov     r8d, esi
0x180074b3f  lea     rcx, [rbp+57h+var_D0]
0x180074b43  mov     rdx, rbx
0x180074b46  call    jsonAppendRaw
0x180074b4b  mov     r8d, r12d
0x180074b4e  lea     rdx, asc_1800A622C; "\""
0x180074b55  lea     rcx, [rbp+57h+var_D0]
0x180074b59  call    jsonAppendRawNZ
0x180074b5e  lea     rcx, [rbp+57h+var_D0]
0x180074b62  call    jsonStringTerminate
0x180074b67  mov     r8, [rbp+57h+var_C8]
0x180074b6b  xor     r9d, r9d
0x180074b6e  xor     edx, edx
0x180074b70  mov     rcx, r14
0x180074b73  call    jsonLookupStep
0x180074b78  lea     rcx, [rbp+57h+var_D0]
0x180074b7c  mov     esi, eax
0x180074b7e  call    jsonStringReset
0x180074b83  cmp     esi, [r14+8]
0x180074b87  jnb     loc_180074C32
0x180074b8d  cmp     r15d, 2
0x180074b91  jnz     loc_180074C19
0x180074b97  mov     rbx, [rsp+100h+var_E0]
0x180074b9c  mov     edx, esi
0x180074b9e  mov     rcx, r14
0x180074ba1  test    r12b, bl
0x180074ba4  jz      short loc_180074BF7
0x180074ba6  lea     rax, [rbp+57h+var_AE]
0x180074baa  mov     [rbp+57h+var_D0], rdi
0x180074bae  lea     r8, [rbp+57h+var_D0]
0x180074bb2  mov     [rbp+57h+var_C8], rax
0x180074bb6  mov     [rbp+57h+var_B0], 1
0x180074bbc  mov     [rbp+57h+var_C0], 64h ; 'd'
0x180074bc4  mov     [rbp+57h+var_B8], 0
0x180074bcc  call    jsonTranslateBlobToText
0x180074bd1  xor     r8d, r8d
0x180074bd4  lea     rcx, [rbp+57h+var_D0]
0x180074bd8  xor     edx, edx
0x180074bda  call    jsonReturnString
0x180074bdf  lea     rcx, [rbp+57h+var_D0]
0x180074be3  call    jsonStringReset
0x180074be8  mov     edx, 4Ah ; 'J'
0x180074bed  mov     rcx, rdi
0x180074bf0  call    sqlite3_result_subtype
0x180074bf5  jmp     short loc_180074C65
0x180074bf7  xor     r9d, r9d
0x180074bfa  mov     r8, rdi
0x180074bfd  call    jsonReturnFromBlob
0x180074c02  test    bl, 0Ah
0x180074c05  jnz     short loc_180074C65
0x180074c07  mov     rax, [r14]
0x180074c0a  mov     ecx, esi
0x180074c0c  mov     dl, [rcx+rax]
0x180074c0f  and     dl, 0Fh
0x180074c12  cmp     dl, 0Bh
0x180074c15  jb      short loc_180074C65
0x180074c17  jmp     short loc_180074BE8
0x180074c19  lea     rcx, [rbp+57h+var_D0]
0x180074c1d  call    jsonAppendSeparator
0x180074c22  lea     r8, [rbp+57h+var_D0]
0x180074c26  mov     edx, esi
0x180074c28  mov     rcx, r14
0x180074c2b  call    jsonTranslateBlobToText
0x180074c30  jmp     short loc_180074C60
0x180074c32  cmp     esi, 0FFFFFFFEh
0x180074c35  jnz     short loc_180074C72
0x180074c37  cmp     r15d, 2
0x180074c3b  jz      loc_180074CCA
0x180074c41  lea     rcx, [rbp+57h+var_D0]
0x180074c45  call    jsonAppendSeparator
0x180074c4a  mov     r8d, 4
0x180074c50  lea     rdx, aNull_2; "null"
0x180074c57  lea     rcx, [rbp+57h+var_D0]
0x180074c5b  call    jsonAppendRawNZ
0x180074c60  mov     rbx, [rsp+100h+var_E0]
0x180074c65  mov     rsi, [rsp+100h+var_D8]
0x180074c6a  add     r13d, r12d
0x180074c6d  jmp     loc_1800749D9
0x180074c72  cmp     esi, 0FFFFFFFFh
0x180074c75  jnz     short loc_180074C8C
0x180074c77  or      r8d, 0FFFFFFFFh
0x180074c7b  lea     rdx, aMalformedJson; "malformed JSON"
0x180074c82  mov     rcx, rdi
0x180074c85  call    sqlite3_result_error
0x180074c8a  jmp     short loc_180074CCA
0x180074c8c  mov     rdx, rbx
0x180074c8f  mov     rcx, rdi
0x180074c92  call    jsonBadPathError
0x180074c97  jmp     short loc_180074CCA
0x180074c99  cmp     r15d, 2
0x180074c9d  jle     short loc_180074CCA
0x180074c9f  mov     dl, 5Dh ; ']'
0x180074ca1  lea     rcx, [rbp+57h+var_D0]
0x180074ca5  call    jsonAppendChar
0x180074caa  xor     r8d, r8d
0x180074cad  lea     rcx, [rbp+57h+var_D0]
0x180074cb1  xor     edx, edx
0x180074cb3  call    jsonReturnString
0x180074cb8  test    bl, 8
0x180074cbb  jnz     short loc_180074CCA
0x180074cbd  mov     edx, 4Ah ; 'J'
0x180074cc2  mov     rcx, rdi
0x180074cc5  call    sqlite3_result_subtype
0x180074cca  lea     rcx, [rbp+57h+var_D0]
0x180074cce  call    jsonStringReset
0x180074cd3  mov     rcx, r14
0x180074cd6  call    jsonParseFree
0x180074cdb  mov     rcx, [rbp+57h+var_40]
0x180074cdf  xor     rcx, rsp; StackCookie
0x180074ce2  call    __security_check_cookie
0x180074ce7  mov     rbx, [rsp+100h+arg_8]
0x180074cef  add     rsp, 0D0h
0x180074cf6  pop     r15
0x180074cf8  pop     r14
0x180074cfa  pop     r13
0x180074cfc  pop     r12
0x180074cfe  pop     rdi
0x180074cff  pop     rsi
0x180074d00  pop     rbp
0x180074d01  retn
```
