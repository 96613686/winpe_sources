# jsonReturnFromBlob

- ea: `0x180068b14`
- end: `0x180068efe`
- name: `jsonReturnFromBlob`
- size: `1002`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config`

## callers

- `0x1800660a0`
- `0x180066b00`

## callees

- `0x18002b81c`
- `0x18003f5a8`
- `0x180042bb0`
- `0x180042e1c`
- `0x180068b14`
- `0x1800691a8`
- `0x18006a7dc`
- `0x18006ac38`
- `0x180077f4c`
- `0x18007d988`
- `0x180094470`
- `0x180096d40`
- `0x180096dd0`
- `0x180096df0`
- `0x180096e70`
- `0x180096ef0`
- `0x180096f10`
- `0x180096f30`
- `0x180096fd0`
- `0x180098a60`

## string_xrefs

- `0x180068d43`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonReturnFromBlob(__int64 *a1, unsigned int a2, __int64 a3, int a4)
{
  __int64 v5; // r15
  __int64 v8; // r14
  int v9; // eax
  __int64 v10; // rdx
  int v11; // ebx
  __int64 v12; // r13
  _BYTE *v13; // rsi
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  signed int v19; // r14d
  __int64 v20; // r13
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r14
  unsigned int v25; // eax
  __int64 v26; // r9
  __int64 v27; // rcx
  int v28; // ebx
  int v30; // r12d
  __int64 v31; // rdx
  char *v32; // rax
  unsigned __int64 v33; // rdx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // r12d
  __int64 v39; // r14
  __int64 v40; // rcx
  __int64 v41; // rbx
  __int64 v42; // rcx
  unsigned int v43; // r15d
  _BYTE *v44; // r9
  int v45; // eax
  unsigned int v46; // edx
  __int64 v47; // rbx
  __int64 v48; // rbx
  __int64 v49; // r9
  __int64 v50; // r8
  __int64 v51; // rdx
  unsigned int v52; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int64 v53; // [rsp+28h] [rbp-20h] BYREF
  __int64 v54; // [rsp+30h] [rbp-18h]

  v5 = a2;
  v52 = 0;
  v54 = sqlite3_context_db_handle(a3);
  v8 = v54;
  v9 = jsonbPayloadSize(a1, (unsigned int)v5, &v52);
  v10 = 0;
  v11 = v9;
  if ( !v9 )
    return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
  v12 = *a1;
  v13 = (_BYTE *)(v5 + *a1);
  v14 = *v13 & 0xF;
  if ( v14 <= 6 )
  {
    if ( v14 == 6 )
    {
LABEL_10:
      v19 = v52;
      v53 = 0;
      if ( v52 )
      {
        v20 = v54;
        goto LABEL_12;
      }
      return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
    }
    if ( (*v13 & 0xF) == 0 )
    {
      if ( !v52 )
        return sqlite3_result_null(a3, 0);
      return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
    }
    v15 = v14 - 1;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( v18 )
          {
            if ( v18 != 1 )
              return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
            goto LABEL_10;
          }
        }
        v19 = v52;
        v53 = 0;
        if ( !v52 )
          return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
        v30 = 0;
        if ( *(_BYTE *)((unsigned int)(v5 + v9) + v12) == 45 )
        {
          if ( v52 < 2 )
            return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
          v11 = v9 + 1;
          v30 = 1;
          v19 = v52 - 1;
        }
        v31 = v12 + (unsigned int)(v11 + v5);
        v20 = v54;
        v32 = (char *)sqlite3DbStrNDup(v54, v31, v19);
        v54 = (__int64)v32;
        if ( v32 )
        {
          v52 = sqlite3DecOrHexToI64(v32);
          sqlite3DbFree(v20, v54);
          switch ( v52 )
          {
            case 0u:
              v33 = v53;
              if ( v30 )
                v33 = -(__int64)v53;
              return sqlite3_result_int64(a3, v33);
            case 3u:
              if ( v30 )
              {
                v33 = 0x8000000000000000uLL;
                return sqlite3_result_int64(a3, v33);
              }
              break;
            case 1u:
              return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
            default:
              if ( v30 )
              {
                --v11;
                ++v19;
              }
              break;
          }
LABEL_12:
          v21 = sqlite3DbStrNDup(v20, *a1 + (unsigned int)(v11 + v5), v19);
          v24 = v21;
          if ( v21 )
          {
            v25 = sqlite3Strlen30(v21, v22, v23);
            LOBYTE(v26) = 1;
            v28 = sqlite3AtoF(v27, &v53, v25, v26);
            sqlite3DbFree(v20, v24);
            if ( v28 > 0 )
              return sqlite3_result_double(a3);
            return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
          }
        }
        return sqlite3_result_error_nomem(a3);
      }
      if ( v52 )
        return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
    }
    else
    {
      if ( v52 )
        return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
      v10 = 1;
    }
    return sqlite3_result_int(a3, v10);
  }
  v34 = v14 - 7;
  if ( !v34 )
    goto LABEL_64;
  v35 = v34 - 1;
  if ( !v35 || (v36 = v35 - 1) == 0 )
  {
    v38 = v52;
    v39 = sqlite3DbMallocRaw(v8, v52 + 1);
    if ( !v39 )
      return sqlite3_result_error_nomem(a3);
    v40 = (unsigned int)(v11 + v5);
    v41 = 0;
    v42 = v12 + v40;
    v43 = 0;
    v54 = v42;
    if ( !v38 )
    {
LABEL_63:
      *(_BYTE *)(v41 + v39) = 0;
      v49 = (__int64)sqlite3OomClear;
      v50 = (unsigned int)v41;
      v51 = v39;
      return sqlite3_result_text(a3, v51, v50, v49);
    }
    while ( 1 )
    {
      v44 = (_BYTE *)(v42 + v43);
      if ( *v44 != 92 )
      {
        *(_BYTE *)(v41 + v39) = *v44;
        v41 = (unsigned int)(v41 + 1);
        goto LABEL_62;
      }
      v52 = 0;
      v45 = jsonUnescapeOneChar(v42 + v43, v38 - v43, &v52);
      v46 = v52;
      if ( v52 <= 0x7F )
        goto LABEL_59;
      if ( v52 <= 0x7FF )
        break;
      if ( v52 < 0x10000 )
      {
        *(_BYTE *)(v41 + v39) = (v52 >> 12) | 0xE0;
        v41 = (unsigned int)(v41 + 1);
        *(_BYTE *)(v41 + v39) = (v46 >> 6) & 0x3F | 0x80;
        goto LABEL_54;
      }
      if ( v52 != 629145 )
      {
        *(_BYTE *)(v41 + v39) = (v52 >> 18) | 0xF0;
        v47 = (unsigned int)(v41 + 1);
        *(_BYTE *)(v47 + v39) = (v46 >> 12) & 0x3F | 0x80;
        v48 = (unsigned int)(v47 + 1);
        *(_BYTE *)(v48 + v39) = (v46 >> 6) & 0x3F | 0x80;
        v41 = (unsigned int)(v48 + 1);
        LOBYTE(v46) = v46 & 0x3F | 0x80;
        goto LABEL_59;
      }
LABEL_60:
      v42 = v54;
      v43 = v45 + v43 - 1;
LABEL_62:
      if ( ++v43 >= v38 )
        goto LABEL_63;
    }
    *(_BYTE *)(v41 + v39) = (v52 >> 6) | 0xC0;
LABEL_54:
    v41 = (unsigned int)(v41 + 1);
    LOBYTE(v46) = v46 & 0x3F | 0x80;
LABEL_59:
    *(_BYTE *)(v41 + v39) = v46;
    v41 = (unsigned int)(v41 + 1);
    goto LABEL_60;
  }
  v37 = v36 - 1;
  if ( !v37 )
  {
LABEL_64:
    v50 = v52;
    v51 = v12 + (unsigned int)(v9 + v5);
    v49 = -1;
    return sqlite3_result_text(a3, v51, v50, v49);
  }
  if ( v37 - 1 >= 2 )
    return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
  if ( a4 || (sqlite3_user_data(a3, 0) & 8) == 0 )
    return jsonReturnTextJsonFromBlob(a3, v13, v11 + v52);
  else
    return sqlite3_result_blob(a3, v13, v11 + v52, -1);
}

```

## disassembly

```asm
0x180068b14  mov     [rsp-40h+arg_0], rcx
0x180068b19  push    rbp
0x180068b1a  push    rbx
0x180068b1b  push    rsi
0x180068b1c  push    rdi
0x180068b1d  push    r12
0x180068b1f  push    r13
0x180068b21  push    r14
0x180068b23  push    r15
0x180068b25  mov     rbp, rsp
0x180068b28  sub     rsp, 48h
0x180068b2c  mov     rsi, rcx
0x180068b2f  mov     r15d, edx
0x180068b32  mov     rcx, r8
0x180068b35  mov     [rbp+var_28], 0
0x180068b3c  mov     r12d, r9d
0x180068b3f  mov     rdi, r8
0x180068b42  call    sqlite3_context_db_handle
0x180068b47  lea     r8, [rbp+var_28]
0x180068b4b  mov     [rbp+var_18], rax
0x180068b4f  mov     edx, r15d
0x180068b52  mov     rcx, rsi
0x180068b55  mov     r14, rax
0x180068b58  call    jsonbPayloadSize
0x180068b5d  xor     edx, edx
0x180068b5f  mov     ebx, eax
0x180068b61  test    eax, eax
0x180068b63  jz      loc_180068D3F
0x180068b69  mov     r13, [rsi]
0x180068b6c  lea     rsi, [r15+r13]
0x180068b70  movzx   ecx, byte ptr [rsi]
0x180068b73  and     ecx, 0Fh
0x180068b76  cmp     ecx, 6
0x180068b79  ja      loc_180068D19
0x180068b7f  lea     esi, [rdx+1]
0x180068b82  jz      short loc_180068BB4
0x180068b84  test    ecx, ecx
0x180068b86  jz      loc_180068D07
0x180068b8c  sub     ecx, esi
0x180068b8e  jz      loc_180068CF3
0x180068b94  sub     ecx, esi
0x180068b96  jz      loc_180068CEC
0x180068b9c  sub     ecx, esi
0x180068b9e  jz      loc_180068C2D
0x180068ba4  sub     ecx, esi
0x180068ba6  jz      loc_180068C2D
0x180068bac  cmp     ecx, esi
0x180068bae  jnz     loc_180068D3F
0x180068bb4  mov     r14d, [rbp+var_28]
0x180068bb8  xorps   xmm0, xmm0
0x180068bbb  movsd   [rbp+var_20], xmm0
0x180068bc0  test    r14d, r14d
0x180068bc3  jz      loc_180068D3F
0x180068bc9  mov     r13, [rbp+var_18]
0x180068bcd  mov     rax, [rbp+arg_0]
0x180068bd1  lea     edx, [rbx+r15]
0x180068bd5  movsxd  r8, r14d
0x180068bd8  mov     rcx, r13
0x180068bdb  add     rdx, [rax]
0x180068bde  call    sqlite3DbStrNDup
0x180068be3  mov     r14, rax
0x180068be6  test    rax, rax
0x180068be9  jz      loc_180068DB3
0x180068bef  mov     rcx, rax
0x180068bf2  call    sqlite3Strlen30
0x180068bf7  mov     r8d, eax
0x180068bfa  lea     rdx, [rbp+var_20]
0x180068bfe  mov     r9b, sil
0x180068c01  call    sqlite3AtoF
0x180068c06  mov     rdx, r14
0x180068c09  mov     rcx, r13
0x180068c0c  mov     ebx, eax
0x180068c0e  call    sqlite3DbFree
0x180068c13  test    ebx, ebx
0x180068c15  jle     loc_180068D3F
0x180068c1b  movsd   xmm1, [rbp+var_20]
0x180068c20  mov     rcx, rdi
0x180068c23  call    sqlite3_result_double
0x180068c28  jmp     loc_180068EED
0x180068c2d  mov     r14d, [rbp+var_28]
0x180068c31  mov     [rbp+var_20], rdx
0x180068c35  test    r14d, r14d
0x180068c38  jz      loc_180068D3F
0x180068c3e  add     eax, r15d
0x180068c41  mov     r12d, edx
0x180068c44  cmp     byte ptr [rax+r13], 2Dh ; '-'
0x180068c49  jnz     short loc_180068C5D
0x180068c4b  cmp     r14d, 2
0x180068c4f  jb      loc_180068D3F
0x180068c55  add     ebx, esi
0x180068c57  mov     r12d, esi
0x180068c5a  dec     r14d
0x180068c5d  lea     edx, [rbx+r15]
0x180068c61  movsxd  r8, r14d
0x180068c64  add     rdx, r13
0x180068c67  mov     r13, [rbp+var_18]
0x180068c6b  mov     rcx, r13
0x180068c6e  call    sqlite3DbStrNDup
0x180068c73  mov     [rbp+var_18], rax
0x180068c77  test    rax, rax
0x180068c7a  jz      loc_180068DB3
0x180068c80  lea     rdx, [rbp+var_20]
0x180068c84  mov     rcx, rax; Str
0x180068c87  call    sqlite3DecOrHexToI64
0x180068c8c  mov     rdx, [rbp+var_18]
0x180068c90  mov     rcx, r13
0x180068c93  mov     [rbp+var_28], eax
0x180068c96  call    sqlite3DbFree
0x180068c9b  mov     eax, [rbp+var_28]
0x180068c9e  test    eax, eax
0x180068ca0  jnz     short loc_180068CB0
0x180068ca2  mov     rdx, [rbp+var_20]
0x180068ca6  test    r12d, r12d
0x180068ca9  jz      short loc_180068CC8
0x180068cab  neg     rdx
0x180068cae  jmp     short loc_180068CC8
0x180068cb0  cmp     eax, 3
0x180068cb3  jnz     short loc_180068CD5
0x180068cb5  test    r12d, r12d
0x180068cb8  jz      loc_180068BCD
0x180068cbe  mov     rdx, 8000000000000000h
0x180068cc8  mov     rcx, rdi
0x180068ccb  call    sqlite3_result_int64
0x180068cd0  jmp     loc_180068EED
0x180068cd5  cmp     eax, esi
0x180068cd7  jz      short loc_180068D3F
0x180068cd9  test    r12d, r12d
0x180068cdc  jz      loc_180068BCD
0x180068ce2  dec     ebx
0x180068ce4  add     r14d, esi
0x180068ce7  jmp     loc_180068BCD
0x180068cec  cmp     [rbp+var_28], edx
0x180068cef  jnz     short loc_180068D3F
0x180068cf1  jmp     short loc_180068CFA
0x180068cf3  cmp     [rbp+var_28], edx
0x180068cf6  jnz     short loc_180068D3F
0x180068cf8  mov     edx, esi
0x180068cfa  mov     rcx, rdi
0x180068cfd  call    sqlite3_result_int
0x180068d02  jmp     loc_180068EED
0x180068d07  cmp     [rbp+var_28], edx
0x180068d0a  jnz     short loc_180068D3F
0x180068d0c  mov     rcx, rdi
0x180068d0f  call    sqlite3_result_null
0x180068d14  jmp     loc_180068EED
0x180068d19  sub     ecx, 7
0x180068d1c  jz      loc_180068ED6
0x180068d22  sub     ecx, 1
0x180068d25  jz      short loc_180068D9A
0x180068d27  sub     ecx, 1
0x180068d2a  jz      short loc_180068D9A
0x180068d2c  sub     ecx, 1
0x180068d2f  jz      loc_180068ED6
0x180068d35  sub     ecx, 1
0x180068d38  jz      short loc_180068D57
0x180068d3a  cmp     ecx, 1
0x180068d3d  jz      short loc_180068D57
0x180068d3f  or      r8d, 0FFFFFFFFh
0x180068d43  lea     rdx, aMalformedJson; "malformed JSON"
0x180068d4a  mov     rcx, rdi
0x180068d4d  call    sqlite3_result_error
0x180068d52  jmp     loc_180068EED
0x180068d57  test    r12d, r12d
0x180068d5a  jnz     short loc_180068D83
0x180068d5c  mov     rcx, rdi
0x180068d5f  call    sqlite3_user_data
0x180068d64  test    al, 8
0x180068d66  jz      short loc_180068D83
0x180068d68  mov     r8d, [rbp+var_28]
0x180068d6c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180068d70  add     r8d, ebx
0x180068d73  mov     rdx, rsi
0x180068d76  mov     rcx, rdi
0x180068d79  call    sqlite3_result_blob
0x180068d7e  jmp     loc_180068EED
0x180068d83  mov     r8d, [rbp+var_28]
0x180068d87  mov     rdx, rsi
0x180068d8a  add     r8d, ebx
0x180068d8d  mov     rcx, rdi
0x180068d90  call    jsonReturnTextJsonFromBlob
0x180068d95  jmp     loc_180068EED
0x180068d9a  mov     r12d, [rbp+var_28]
0x180068d9e  mov     rcx, r14
0x180068da1  lea     edx, [r12+1]
0x180068da6  call    sqlite3DbMallocRaw
0x180068dab  mov     r14, rax
0x180068dae  test    rax, rax
0x180068db1  jnz     short loc_180068DC0
0x180068db3  mov     rcx, rdi
0x180068db6  call    sqlite3_result_error_nomem
0x180068dbb  jmp     loc_180068EED
0x180068dc0  lea     ecx, [rbx+r15]
0x180068dc4  xor     ebx, ebx
0x180068dc6  add     rcx, r13
0x180068dc9  xor     r15d, r15d
0x180068dcc  mov     [rbp+var_18], rcx
0x180068dd0  test    r12d, r12d
0x180068dd3  jz      loc_180068EC2
0x180068dd9  lea     esi, [rbx+1]
0x180068ddc  mov     r13b, 3Fh ; '?'
0x180068ddf  mov     r9d, r15d
0x180068de2  add     r9, rcx
0x180068de5  mov     dl, [r9]
0x180068de8  cmp     dl, 5Ch ; '\'
0x180068deb  jnz     loc_180068EB0
0x180068df1  mov     edx, r12d
0x180068df4  mov     [rbp+var_28], 0
0x180068dfb  sub     edx, r15d
0x180068dfe  lea     r8, [rbp+var_28]
0x180068e02  mov     rcx, r9
0x180068e05  call    jsonUnescapeOneChar
0x180068e0a  mov     edx, [rbp+var_28]
0x180068e0d  mov     r8d, eax
0x180068e10  cmp     edx, 7Fh
0x180068e13  jbe     loc_180068E9E
0x180068e19  cmp     edx, 7FFh
0x180068e1f  ja      short loc_180068E37
0x180068e21  mov     ecx, edx
0x180068e23  shr     ecx, 6
0x180068e26  or      cl, 0C0h
0x180068e29  mov     [rbx+r14], cl
0x180068e2d  add     ebx, esi
0x180068e2f  and     dl, r13b
0x180068e32  or      dl, 80h
0x180068e35  jmp     short loc_180068E9E
0x180068e37  cmp     edx, 10000h
0x180068e3d  jnb     short loc_180068E5D
0x180068e3f  mov     ecx, edx
0x180068e41  mov     eax, edx
0x180068e43  shr     ecx, 0Ch
0x180068e46  or      cl, 0E0h
0x180068e49  shr     eax, 6
0x180068e4c  mov     [rbx+r14], cl
0x180068e50  and     al, r13b
0x180068e53  add     ebx, esi
0x180068e55  or      al, 80h
0x180068e57  mov     [rbx+r14], al
0x180068e5b  jmp     short loc_180068E2D
0x180068e5d  cmp     edx, 99999h
0x180068e63  jz      short loc_180068EA4
0x180068e65  mov     ecx, edx
0x180068e67  mov     eax, edx
0x180068e69  shr     eax, 0Ch
0x180068e6c  mov     r10b, 80h
0x180068e6f  and     al, r13b
0x180068e72  shr     ecx, 12h
0x180068e75  or      al, r10b
0x180068e78  or      cl, 0F0h
0x180068e7b  mov     [rbx+r14], cl
0x180068e7f  add     ebx, esi
0x180068e81  mov     [rbx+r14], al
0x180068e85  mov     eax, edx
0x180068e87  shr     eax, 6
0x180068e8a  add     ebx, esi
0x180068e8c  and     al, r13b
0x180068e8f  and     dl, r13b
0x180068e92  or      al, r10b
0x180068e95  mov     [rbx+r14], al
0x180068e99  add     ebx, esi
0x180068e9b  or      dl, r10b
0x180068e9e  mov     [rbx+r14], dl
0x180068ea2  add     ebx, esi
0x180068ea4  mov     rcx, [rbp+var_18]
0x180068ea8  dec     r15d
0x180068eab  add     r15d, r8d
0x180068eae  jmp     short loc_180068EB6
0x180068eb0  mov     [rbx+r14], dl
0x180068eb4  add     ebx, esi
0x180068eb6  add     r15d, esi
0x180068eb9  cmp     r15d, r12d
0x180068ebc  jb      loc_180068DDF
0x180068ec2  mov     byte ptr [rbx+r14], 0
0x180068ec7  lea     r9, sqlite3OomClear
0x180068ece  mov     r8d, ebx
0x180068ed1  mov     rdx, r14
0x180068ed4  jmp     short loc_180068EE5
0x180068ed6  mov     r8d, [rbp+var_28]
0x180068eda  lea     edx, [rax+r15]
0x180068ede  add     rdx, r13
0x180068ee1  or      r9, 0FFFFFFFFFFFFFFFFh
0x180068ee5  mov     rcx, rdi
0x180068ee8  call    sqlite3_result_text
0x180068eed  add     rsp, 48h
0x180068ef1  pop     r15
0x180068ef3  pop     r14
0x180068ef5  pop     r13
0x180068ef7  pop     r12
0x180068ef9  pop     rdi
0x180068efa  pop     rsi
0x180068efb  pop     rbx
0x180068efc  pop     rbp
0x180068efd  retn
```
