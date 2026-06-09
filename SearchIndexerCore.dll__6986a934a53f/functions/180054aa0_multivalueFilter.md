# multivalueFilter

- ea: `0x180054aa0`
- end: `0x180054d9a`
- name: `multivalueFilter`
- size: `762`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x180024770`
- `0x180024b60`
- `0x180041eb0`
- `0x180047da0`
- `0x18004c5f0`
- `0x1800543d0`
- `0x180054aa0`
- `0x180054e70`
- `0x180054ef4`
- `0x180054fd0`
- `0x1800551dc`
- `0x180063f08`
- `0x18006f290`
- `0x1800789c0`
- `0x1800af620`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180054c61`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180054c61`

## string_xrefs

- `0x180054c15`: `invalid multivalue blob (not enough bytes are left to read the entire varint)`

## pseudocode

```c
__int64 __fastcall multivalueFilter(__int64 *a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5)
{
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rsi
  int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rsi
  int v14; // ebx
  int v15; // ebx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rax
  int v20; // eax
  size_t v21; // rbx
  const void *v22; // rax
  __int64 v23; // r14
  const void *v24; // r12
  unsigned __int8 Varint; // cl
  const char *v26; // rdx
  const char *v27; // r15
  const char *v28; // r13
  __int64 v29; // rax
  __int64 v30; // rbx
  void *v31; // rax
  __int64 v32; // rsi
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  const char *v36; // [rsp+20h] [rbp-58h] BYREF
  __int128 v37; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v38[24]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v39; // [rsp+50h] [rbp-28h] BYREF

  sqlite3ValueFree(a1[3]);
  v6 = a1[5];
  a1[3] = 0;
  sqlite3_free(v6);
  a1[5] = 0;
  *((_DWORD *)a1 + 4) = 0;
  a1[6] = 5;
  *((_BYTE *)a1 + 20) = 0;
  a1[4] = 0;
  a1[7] = 0;
  a1[8] = 0;
  a1[9] = 0;
  a1[10] = 0;
  a1[11] = 0;
  a1[12] = 0;
  v8 = *a5;
  v9 = *((unsigned __int8 *)qword_1800B5270 + (*(_WORD *)(*a5 + 20) & 0x3F));
  v10 = *a5;
  if ( v9 != 4 )
  {
    v11 = sqlite3_value_dup(v10);
    v13 = v11;
    if ( v11 )
    {
      v14 = v9 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          if ( v15 == 1 )
          {
            LOBYTE(v12) = 1;
            *((_DWORD *)a1 + 12) = 3;
            v16 = sqlite3ValueBytes(v11, v12);
            LOBYTE(v17) = 1;
            a1[7] = v16;
            v18 = sqlite3ValueText(v13, v17);
LABEL_11:
            a1[8] = v18;
            a1[3] = v13;
            return 0;
          }
          *((_DWORD *)a1 + 12) = 5;
          a1[7] = 0;
        }
        else
        {
          *((_DWORD *)a1 + 12) = 2;
          *((double *)a1 + 7) = sqlite3VdbeRealValue(v11);
        }
      }
      else
      {
        *((_DWORD *)a1 + 12) = 1;
        a1[7] = sqlite3VdbeIntValue(v11);
      }
      v18 = 0;
      goto LABEL_11;
    }
    return 7;
  }
  LOBYTE(v7) = 1;
  v20 = sqlite3ValueBytes(v10, v7);
  v21 = v20;
  if ( !v20 )
  {
LABEL_14:
    *((_BYTE *)a1 + 20) = 1;
    return 0;
  }
  v22 = (const void *)sqlite3_value_blob(v8);
  v23 = *a1;
  v24 = v22;
  v36 = 0;
  if ( v21 >= 9 )
  {
    Varint = sqlite3GetVarint(v22, &v36);
  }
  else
  {
    *(_QWORD *)&v39 = 0;
    BYTE8(v39) = 0;
    memcpy_0(&v39, v22, v21);
    Varint = sqlite3GetVarint(&v39, &v36);
    if ( Varint > v21 )
    {
      v26 = "invalid multivalue blob (not enough bytes are left to read the entire varint)";
      goto LABEL_24;
    }
  }
  v27 = v36;
  v28 = (const char *)Varint;
  if ( Varint > (unsigned __int64)v36 )
  {
    v29 = sqlite3_malloc64(62);
    v30 = v29;
    if ( v29 )
    {
      _o_strncpy_s(v29, 62, "invalid multivalue blob (has a header size that is too small)", 61);
      sqlite3_free(*(_QWORD *)(v23 + 16));
      *(_QWORD *)(v23 + 16) = v30;
      return 1;
    }
    return 7;
  }
  if ( v21 < (unsigned __int64)v36 )
  {
    v26 = "invalid multivalue blob (is shorter than the header size indicates)";
LABEL_24:
    if ( (unsigned __int8)try_set_error_message(v23, v26) )
      return 1;
    return 7;
  }
  v31 = (void *)sqlite3_malloc64(v21);
  v32 = (__int64)v31;
  if ( !v31 )
    return 7;
  memcpy_0(v31, v24, v21);
  if ( v27 == v28 && v21 == (_QWORD)v27 )
  {
    a1[4] = v21;
    a1[5] = v32;
    goto LABEL_14;
  }
  *((_QWORD *)&v39 + 1) = v27 - v28;
  *(_QWORD *)&v39 = &v28[v32];
  *((_QWORD *)&v37 + 1) = v21 - (_QWORD)v27;
  *(_QWORD *)&v37 = &v27[v32];
  v36 = 0;
  *(_QWORD *)v38 = 5;
  *(_OWORD *)&v38[8] = 0;
  if ( try_move_next(&v39, (char **)&v37, (__int64)v38, &v36) )
  {
    v33 = v39;
    a1[4] = v21;
    v34 = v37;
    a1[5] = v32;
    *(_OWORD *)(a1 + 9) = v33;
    v35 = *(_OWORD *)v38;
    *(_OWORD *)(a1 + 11) = v34;
    *(_QWORD *)&v34 = *(_QWORD *)&v38[16];
    *((_OWORD *)a1 + 3) = v35;
    a1[8] = v34;
    return 0;
  }
  sqlite3_free(v32);
  return (unsigned __int8)try_set_error_message(v23, v36) != 0 ? 1 : 7;
}

```

## disassembly

```asm
0x180054aa0  push    rbp
0x180054aa2  push    rbx
0x180054aa3  push    rsi
0x180054aa4  push    rdi
0x180054aa5  push    r12
0x180054aa7  push    r13
0x180054aa9  push    r14
0x180054aab  push    r15
0x180054aad  mov     rbp, rsp
0x180054ab0  sub     rsp, 78h
0x180054ab4  mov     rax, cs:__security_cookie
0x180054abb  xor     rax, rsp
0x180054abe  mov     [rbp+var_18], rax
0x180054ac2  mov     rbx, [rbp+arg_20]
0x180054ac6  mov     rdi, rcx
0x180054ac9  mov     rcx, [rcx+18h]
0x180054acd  call    sqlite3ValueFree
0x180054ad2  mov     rcx, [rdi+28h]
0x180054ad6  xor     r15d, r15d
0x180054ad9  mov     [rdi+18h], r15
0x180054add  call    sqlite3_free
0x180054ae2  mov     [rdi+28h], r15
0x180054ae6  lea     rcx, qword_1800B5270
0x180054aed  mov     [rdi+10h], r15d
0x180054af1  lea     r14d, [r15+5]
0x180054af5  mov     [rdi+30h], r14
0x180054af9  mov     [rdi+14h], r15b
0x180054afd  mov     [rdi+20h], r15
0x180054b01  mov     [rdi+38h], r15
0x180054b05  mov     [rdi+40h], r15
0x180054b09  mov     [rdi+48h], r15
0x180054b0d  mov     [rdi+50h], r15
0x180054b11  mov     [rdi+58h], r15
0x180054b15  mov     [rdi+60h], r15
0x180054b19  mov     rsi, [rbx]
0x180054b1c  movzx   eax, word ptr [rsi+14h]
0x180054b20  and     eax, 3Fh
0x180054b23  movzx   ebx, byte ptr [rax+rcx]
0x180054b27  mov     rcx, rsi
0x180054b2a  cmp     ebx, 4
0x180054b2d  jz      loc_180054BBC
0x180054b33  call    sqlite3_value_dup
0x180054b38  mov     rsi, rax
0x180054b3b  test    rax, rax
0x180054b3e  jz      loc_180054D78
0x180054b44  sub     ebx, 1
0x180054b47  jz      short loc_180054B97
0x180054b49  sub     ebx, 1
0x180054b4c  jz      short loc_180054B81
0x180054b4e  cmp     ebx, 1
0x180054b51  jz      short loc_180054B5D
0x180054b53  mov     [rdi+30h], r14d
0x180054b57  mov     [rdi+38h], r15
0x180054b5b  jmp     short loc_180054BAA
0x180054b5d  mov     dl, 1
0x180054b5f  mov     dword ptr [rdi+30h], 3
0x180054b66  mov     rcx, rsi
0x180054b69  call    sqlite3ValueBytes
0x180054b6e  movsxd  rcx, eax
0x180054b71  mov     dl, 1
0x180054b73  mov     [rdi+38h], rcx
0x180054b77  mov     rcx, rsi
0x180054b7a  call    sqlite3ValueText
0x180054b7f  jmp     short loc_180054BAD
0x180054b81  mov     rcx, rsi
0x180054b84  mov     dword ptr [rdi+30h], 2
0x180054b8b  call    sqlite3VdbeRealValue
0x180054b90  movsd   qword ptr [rdi+38h], xmm0
0x180054b95  jmp     short loc_180054BAA
0x180054b97  mov     rcx, rsi
0x180054b9a  mov     dword ptr [rdi+30h], 1
0x180054ba1  call    sqlite3VdbeIntValue
0x180054ba6  mov     [rdi+38h], rax
0x180054baa  mov     rax, r15
0x180054bad  mov     [rdi+40h], rax
0x180054bb1  mov     [rdi+18h], rsi
0x180054bb5  xor     eax, eax
0x180054bb7  jmp     loc_180054D7D
0x180054bbc  mov     dl, 1
0x180054bbe  call    sqlite3ValueBytes
0x180054bc3  movsxd  rbx, eax
0x180054bc6  test    eax, eax
0x180054bc8  jnz     short loc_180054BD0
0x180054bca  mov     byte ptr [rdi+14h], 1
0x180054bce  jmp     short loc_180054BB5
0x180054bd0  mov     rcx, rsi
0x180054bd3  call    sqlite3_value_blob
0x180054bd8  mov     r14, [rdi]
0x180054bdb  mov     r12, rax
0x180054bde  mov     [rbp+var_58], r15
0x180054be2  cmp     rbx, 9
0x180054be6  jnb     short loc_180054C1E
0x180054be8  xor     eax, eax
0x180054bea  lea     rcx, [rbp+var_28]; void *
0x180054bee  mov     r8, rbx; Size
0x180054bf1  mov     qword ptr [rbp+var_28], rax
0x180054bf5  mov     rdx, r12; Src
0x180054bf8  mov     byte ptr [rbp+var_28+8], al
0x180054bfb  call    memcpy_0
0x180054c00  lea     rdx, [rbp+var_58]
0x180054c04  lea     rcx, [rbp+var_28]
0x180054c08  call    sqlite3GetVarint
0x180054c0d  movzx   ecx, al
0x180054c10  cmp     rcx, rbx
0x180054c13  jbe     short loc_180054C2C
0x180054c15  lea     rdx, aInvalidMultiva; "invalid multivalue blob (not enough byt"...
0x180054c1c  jmp     short loc_180054C82
0x180054c1e  lea     rdx, [rbp+var_58]
0x180054c22  mov     rcx, r12
0x180054c25  call    sqlite3GetVarint
0x180054c2a  mov     cl, al
0x180054c2c  mov     r15, [rbp+var_58]
0x180054c30  movzx   r13d, cl
0x180054c34  cmp     r13, r15
0x180054c37  jbe     short loc_180054C76
0x180054c39  mov     edi, 3Eh ; '>'
0x180054c3e  mov     ecx, edi
0x180054c40  call    sqlite3_malloc64
0x180054c45  mov     rbx, rax
0x180054c48  test    rax, rax
0x180054c4b  jz      loc_180054D78
0x180054c51  lea     r9d, [rdi-1]
0x180054c55  mov     edx, edi
0x180054c57  lea     r8, aInvalidMultiva_0; "invalid multivalue blob (has a header s"...
0x180054c5e  mov     rcx, rax
0x180054c61  call    cs:__imp__o_strncpy_s
0x180054c67  mov     rcx, [r14+10h]
0x180054c6b  call    sqlite3_free
0x180054c70  mov     [r14+10h], rbx
0x180054c74  jmp     short loc_180054C92
0x180054c76  cmp     rbx, r15
0x180054c79  jnb     short loc_180054C9C
0x180054c7b  lea     rdx, aInvalidMultiva_4; "invalid multivalue blob (is shorter tha"...
0x180054c82  mov     rcx, r14
0x180054c85  call    try_set_error_message
0x180054c8a  test    al, al
0x180054c8c  jz      loc_180054D78
0x180054c92  mov     eax, 1
0x180054c97  jmp     loc_180054D7D
0x180054c9c  mov     rcx, rbx
0x180054c9f  call    sqlite3_malloc64
0x180054ca4  mov     rsi, rax
0x180054ca7  test    rax, rax
0x180054caa  jz      loc_180054D78
0x180054cb0  mov     r8, rbx; Size
0x180054cb3  mov     rdx, r12; Src
0x180054cb6  mov     rcx, rax; void *
0x180054cb9  call    memcpy_0
0x180054cbe  mov     rcx, rbx
0x180054cc1  mov     rdx, r15
0x180054cc4  sub     rcx, r15
0x180054cc7  sub     rdx, r13
0x180054cca  jnz     short loc_180054CDE
0x180054ccc  test    rcx, rcx
0x180054ccf  jnz     short loc_180054CDE
0x180054cd1  mov     [rdi+20h], rbx
0x180054cd5  mov     [rdi+28h], rsi
0x180054cd9  jmp     loc_180054BCA
0x180054cde  lea     rax, [rsi+r13]
0x180054ce2  mov     qword ptr [rbp+var_28+8], rdx
0x180054ce6  mov     qword ptr [rbp+var_28], rax
0x180054cea  lea     r9, [rbp+var_58]
0x180054cee  lea     rax, [rsi+r15]
0x180054cf2  mov     qword ptr [rbp+var_50+8], rcx
0x180054cf6  xorps   xmm0, xmm0
0x180054cf9  mov     qword ptr [rbp+var_50], rax
0x180054cfd  lea     r8, [rbp+var_40]
0x180054d01  mov     [rbp+var_58], 0
0x180054d09  lea     rdx, [rbp+var_50]
0x180054d0d  mov     qword ptr [rbp+var_40], 5
0x180054d15  lea     rcx, [rbp+var_28]
0x180054d19  movdqu  [rbp+var_40+8], xmm0
0x180054d1e  call    try_move_next
0x180054d23  test    al, al
0x180054d25  jnz     short loc_180054D47
0x180054d27  mov     rcx, rsi
0x180054d2a  call    sqlite3_free
0x180054d2f  mov     rdx, [rbp+var_58]
0x180054d33  mov     rcx, r14
0x180054d36  call    try_set_error_message
0x180054d3b  neg     al
0x180054d3d  sbb     eax, eax
0x180054d3f  and     eax, 0FFFFFFFAh
0x180054d42  add     eax, 7
0x180054d45  jmp     short loc_180054D7D
0x180054d47  movups  xmm0, [rbp+var_28]
0x180054d4b  mov     [rdi+20h], rbx
0x180054d4f  movups  xmm1, [rbp+var_50]
0x180054d53  mov     [rdi+28h], rsi
0x180054d57  movdqu  xmmword ptr [rdi+48h], xmm0
0x180054d5c  movups  xmm0, [rbp+var_40]
0x180054d60  movdqu  xmmword ptr [rdi+58h], xmm1
0x180054d65  movsd   xmm1, [rbp+var_30]
0x180054d6a  movups  xmmword ptr [rdi+30h], xmm0
0x180054d6e  movsd   qword ptr [rdi+40h], xmm1
0x180054d73  jmp     loc_180054BB5
0x180054d78  mov     eax, 7
0x180054d7d  mov     rcx, [rbp+var_18]
0x180054d81  xor     rcx, rsp; StackCookie
0x180054d84  call    __security_check_cookie
0x180054d89  add     rsp, 78h
0x180054d8d  pop     r15
0x180054d8f  pop     r14
0x180054d91  pop     r13
0x180054d93  pop     r12
0x180054d95  pop     rdi
0x180054d96  pop     rsi
0x180054d97  pop     rbx
0x180054d98  pop     rbp
0x180054d99  retn
```
