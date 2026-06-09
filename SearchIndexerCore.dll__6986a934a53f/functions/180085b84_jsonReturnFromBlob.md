# jsonReturnFromBlob

- ea: `0x180085b84`
- end: `0x180085f6e`
- name: `jsonReturnFromBlob`
- size: `1002`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config`

## callers

- `0x180083130`
- `0x180083b70`

## callees

- `0x180014c90`
- `0x18001eb90`
- `0x180041d10`
- `0x18004bfc0`
- `0x1800501a0`
- `0x180067d84`
- `0x180070500`
- `0x180070520`
- `0x180085b84`
- `0x180086218`
- `0x18008785c`
- `0x180087c68`
- `0x18009176c`
- `0x18009d5a0`
- `0x18009d630`
- `0x18009d650`
- `0x18009d6d0`
- `0x18009d710`
- `0x18009d7b0`
- `0x18009ed10`

## string_xrefs

- `0x180085db3`: `malformed JSON`

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
  __int64 v22; // r14
  unsigned int v23; // eax
  __int64 v24; // r9
  __int64 v25; // rcx
  int v26; // ebx
  int v28; // r12d
  __int64 v29; // rdx
  char *v30; // rax
  unsigned __int64 v31; // rdx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // r12d
  __int64 v37; // r14
  __int64 v38; // rcx
  __int64 v39; // rbx
  __int64 v40; // rcx
  unsigned int v41; // r15d
  _BYTE *v42; // r9
  int v43; // eax
  unsigned int v44; // edx
  __int64 v45; // rbx
  __int64 v46; // rbx
  __int64 v47; // r9
  __int64 v48; // r8
  __int64 v49; // rdx
  unsigned int v50; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int64 v51; // [rsp+28h] [rbp-20h] BYREF
  __int64 v52; // [rsp+30h] [rbp-18h]

  v5 = a2;
  v50 = 0;
  v52 = sqlite3_context_db_handle(a3);
  v8 = v52;
  v9 = jsonbPayloadSize(a1, v5, &v50);
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
      v19 = v50;
      v51 = 0;
      if ( v50 )
      {
        v20 = v52;
        goto LABEL_12;
      }
      return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
    }
    if ( (*v13 & 0xF) == 0 )
    {
      if ( !v50 )
        return sqlite3_result_null(a3);
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
        v19 = v50;
        v51 = 0;
        if ( !v50 )
          return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
        v28 = 0;
        if ( *(_BYTE *)((unsigned int)(v5 + v9) + v12) == 45 )
        {
          if ( v50 < 2 )
            return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
          v11 = v9 + 1;
          v28 = 1;
          v19 = v50 - 1;
        }
        v29 = v12 + (unsigned int)(v11 + v5);
        v20 = v52;
        v30 = (char *)sqlite3DbStrNDup(v52, v29, v19);
        v52 = (__int64)v30;
        if ( v30 )
        {
          v50 = sqlite3DecOrHexToI64(v30);
          sqlite3DbFree(v20, v52);
          switch ( v50 )
          {
            case 0u:
              v31 = v51;
              if ( v28 )
                v31 = -(__int64)v51;
              return sqlite3_result_int64(a3, v31);
            case 3u:
              if ( v28 )
              {
                v31 = 0x8000000000000000uLL;
                return sqlite3_result_int64(a3, v31);
              }
              break;
            case 1u:
              return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
            default:
              if ( v28 )
              {
                --v11;
                ++v19;
              }
              break;
          }
LABEL_12:
          v21 = sqlite3DbStrNDup(v20, *a1 + (unsigned int)(v11 + v5), v19);
          v22 = v21;
          if ( v21 )
          {
            v23 = sqlite3Strlen30(v21);
            LOBYTE(v24) = 1;
            v26 = sqlite3AtoF(v25, &v51, v23, v24);
            sqlite3DbFree(v20, v22);
            if ( v26 > 0 )
              return sqlite3_result_double(a3);
            return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
          }
        }
        return sqlite3_result_error_nomem(a3);
      }
      if ( v50 )
        return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
    }
    else
    {
      if ( v50 )
        return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
      v10 = 1;
    }
    return sqlite3_result_int(a3, v10);
  }
  v32 = v14 - 7;
  if ( !v32 )
    goto LABEL_64;
  v33 = v32 - 1;
  if ( !v33 || (v34 = v33 - 1) == 0 )
  {
    v36 = v50;
    v37 = sqlite3DbMallocRaw(v8, v50 + 1);
    if ( !v37 )
      return sqlite3_result_error_nomem(a3);
    v38 = (unsigned int)(v11 + v5);
    v39 = 0;
    v40 = v12 + v38;
    v41 = 0;
    v52 = v40;
    if ( !v36 )
    {
LABEL_63:
      *(_BYTE *)(v39 + v37) = 0;
      v47 = (__int64)sqlite3OomClear;
      v48 = (unsigned int)v39;
      v49 = v37;
      return sqlite3_result_text(a3, v49, v48, v47);
    }
    while ( 1 )
    {
      v42 = (_BYTE *)(v40 + v41);
      if ( *v42 != 92 )
      {
        *(_BYTE *)(v39 + v37) = *v42;
        v39 = (unsigned int)(v39 + 1);
        goto LABEL_62;
      }
      v50 = 0;
      v43 = jsonUnescapeOneChar(v40 + v41, v36 - v41, &v50);
      v44 = v50;
      if ( v50 <= 0x7F )
        goto LABEL_59;
      if ( v50 <= 0x7FF )
        break;
      if ( v50 < 0x10000 )
      {
        *(_BYTE *)(v39 + v37) = (v50 >> 12) | 0xE0;
        v39 = (unsigned int)(v39 + 1);
        *(_BYTE *)(v39 + v37) = (v44 >> 6) & 0x3F | 0x80;
        goto LABEL_54;
      }
      if ( v50 != 629145 )
      {
        *(_BYTE *)(v39 + v37) = (v50 >> 18) | 0xF0;
        v45 = (unsigned int)(v39 + 1);
        *(_BYTE *)(v45 + v37) = (v44 >> 12) & 0x3F | 0x80;
        v46 = (unsigned int)(v45 + 1);
        *(_BYTE *)(v46 + v37) = (v44 >> 6) & 0x3F | 0x80;
        v39 = (unsigned int)(v46 + 1);
        LOBYTE(v44) = v44 & 0x3F | 0x80;
        goto LABEL_59;
      }
LABEL_60:
      v40 = v52;
      v41 = v43 + v41 - 1;
LABEL_62:
      if ( ++v41 >= v36 )
        goto LABEL_63;
    }
    *(_BYTE *)(v39 + v37) = (v50 >> 6) | 0xC0;
LABEL_54:
    v39 = (unsigned int)(v39 + 1);
    LOBYTE(v44) = v44 & 0x3F | 0x80;
LABEL_59:
    *(_BYTE *)(v39 + v37) = v44;
    v39 = (unsigned int)(v39 + 1);
    goto LABEL_60;
  }
  v35 = v34 - 1;
  if ( !v35 )
  {
LABEL_64:
    v48 = v50;
    v49 = v12 + (unsigned int)(v9 + v5);
    v47 = -1;
    return sqlite3_result_text(a3, v49, v48, v47);
  }
  if ( v35 - 1 >= 2 )
    return sqlite3_result_error(a3, "malformed JSON", 0xFFFFFFFFLL);
  if ( a4 || (sqlite3_user_data(a3) & 8) == 0 )
    return jsonReturnTextJsonFromBlob(a3, v13, v11 + v50);
  else
    return sqlite3_result_blob(a3, v13, v11 + v50, -1);
}

```

## disassembly

```asm
0x180085b84  mov     [rsp-40h+arg_0], rcx
0x180085b89  push    rbp
0x180085b8a  push    rbx
0x180085b8b  push    rsi
0x180085b8c  push    rdi
0x180085b8d  push    r12
0x180085b8f  push    r13
0x180085b91  push    r14
0x180085b93  push    r15
0x180085b95  mov     rbp, rsp
0x180085b98  sub     rsp, 48h
0x180085b9c  mov     rsi, rcx
0x180085b9f  mov     r15d, edx
0x180085ba2  mov     rcx, r8
0x180085ba5  mov     [rbp+var_28], 0
0x180085bac  mov     r12d, r9d
0x180085baf  mov     rdi, r8
0x180085bb2  call    sqlite3_context_db_handle
0x180085bb7  lea     r8, [rbp+var_28]
0x180085bbb  mov     [rbp+var_18], rax
0x180085bbf  mov     edx, r15d
0x180085bc2  mov     rcx, rsi
0x180085bc5  mov     r14, rax
0x180085bc8  call    jsonbPayloadSize
0x180085bcd  xor     edx, edx
0x180085bcf  mov     ebx, eax
0x180085bd1  test    eax, eax
0x180085bd3  jz      loc_180085DAF
0x180085bd9  mov     r13, [rsi]
0x180085bdc  lea     rsi, [r15+r13]
0x180085be0  movzx   ecx, byte ptr [rsi]
0x180085be3  and     ecx, 0Fh
0x180085be6  cmp     ecx, 6
0x180085be9  ja      loc_180085D89
0x180085bef  lea     esi, [rdx+1]
0x180085bf2  jz      short loc_180085C24
0x180085bf4  test    ecx, ecx
0x180085bf6  jz      loc_180085D77
0x180085bfc  sub     ecx, esi
0x180085bfe  jz      loc_180085D63
0x180085c04  sub     ecx, esi
0x180085c06  jz      loc_180085D5C
0x180085c0c  sub     ecx, esi
0x180085c0e  jz      loc_180085C9D
0x180085c14  sub     ecx, esi
0x180085c16  jz      loc_180085C9D
0x180085c1c  cmp     ecx, esi
0x180085c1e  jnz     loc_180085DAF
0x180085c24  mov     r14d, [rbp+var_28]
0x180085c28  xorps   xmm0, xmm0
0x180085c2b  movsd   [rbp+var_20], xmm0
0x180085c30  test    r14d, r14d
0x180085c33  jz      loc_180085DAF
0x180085c39  mov     r13, [rbp+var_18]
0x180085c3d  mov     rax, [rbp+arg_0]
0x180085c41  lea     edx, [rbx+r15]
0x180085c45  movsxd  r8, r14d
0x180085c48  mov     rcx, r13
0x180085c4b  add     rdx, [rax]
0x180085c4e  call    sqlite3DbStrNDup
0x180085c53  mov     r14, rax
0x180085c56  test    rax, rax
0x180085c59  jz      loc_180085E23
0x180085c5f  mov     rcx, rax
0x180085c62  call    sqlite3Strlen30
0x180085c67  mov     r8d, eax
0x180085c6a  lea     rdx, [rbp+var_20]
0x180085c6e  mov     r9b, sil
0x180085c71  call    sqlite3AtoF
0x180085c76  mov     rdx, r14
0x180085c79  mov     rcx, r13
0x180085c7c  mov     ebx, eax
0x180085c7e  call    sqlite3DbFree
0x180085c83  test    ebx, ebx
0x180085c85  jle     loc_180085DAF
0x180085c8b  movsd   xmm1, [rbp+var_20]
0x180085c90  mov     rcx, rdi
0x180085c93  call    sqlite3_result_double
0x180085c98  jmp     loc_180085F5D
0x180085c9d  mov     r14d, [rbp+var_28]
0x180085ca1  mov     [rbp+var_20], rdx
0x180085ca5  test    r14d, r14d
0x180085ca8  jz      loc_180085DAF
0x180085cae  add     eax, r15d
0x180085cb1  mov     r12d, edx
0x180085cb4  cmp     byte ptr [rax+r13], 2Dh ; '-'
0x180085cb9  jnz     short loc_180085CCD
0x180085cbb  cmp     r14d, 2
0x180085cbf  jb      loc_180085DAF
0x180085cc5  add     ebx, esi
0x180085cc7  mov     r12d, esi
0x180085cca  dec     r14d
0x180085ccd  lea     edx, [rbx+r15]
0x180085cd1  movsxd  r8, r14d
0x180085cd4  add     rdx, r13
0x180085cd7  mov     r13, [rbp+var_18]
0x180085cdb  mov     rcx, r13
0x180085cde  call    sqlite3DbStrNDup
0x180085ce3  mov     [rbp+var_18], rax
0x180085ce7  test    rax, rax
0x180085cea  jz      loc_180085E23
0x180085cf0  lea     rdx, [rbp+var_20]
0x180085cf4  mov     rcx, rax; Str
0x180085cf7  call    sqlite3DecOrHexToI64
0x180085cfc  mov     rdx, [rbp+var_18]
0x180085d00  mov     rcx, r13
0x180085d03  mov     [rbp+var_28], eax
0x180085d06  call    sqlite3DbFree
0x180085d0b  mov     eax, [rbp+var_28]
0x180085d0e  test    eax, eax
0x180085d10  jnz     short loc_180085D20
0x180085d12  mov     rdx, [rbp+var_20]
0x180085d16  test    r12d, r12d
0x180085d19  jz      short loc_180085D38
0x180085d1b  neg     rdx
0x180085d1e  jmp     short loc_180085D38
0x180085d20  cmp     eax, 3
0x180085d23  jnz     short loc_180085D45
0x180085d25  test    r12d, r12d
0x180085d28  jz      loc_180085C3D
0x180085d2e  mov     rdx, 8000000000000000h
0x180085d38  mov     rcx, rdi
0x180085d3b  call    sqlite3_result_int64
0x180085d40  jmp     loc_180085F5D
0x180085d45  cmp     eax, esi
0x180085d47  jz      short loc_180085DAF
0x180085d49  test    r12d, r12d
0x180085d4c  jz      loc_180085C3D
0x180085d52  dec     ebx
0x180085d54  add     r14d, esi
0x180085d57  jmp     loc_180085C3D
0x180085d5c  cmp     [rbp+var_28], edx
0x180085d5f  jnz     short loc_180085DAF
0x180085d61  jmp     short loc_180085D6A
0x180085d63  cmp     [rbp+var_28], edx
0x180085d66  jnz     short loc_180085DAF
0x180085d68  mov     edx, esi
0x180085d6a  mov     rcx, rdi
0x180085d6d  call    sqlite3_result_int
0x180085d72  jmp     loc_180085F5D
0x180085d77  cmp     [rbp+var_28], edx
0x180085d7a  jnz     short loc_180085DAF
0x180085d7c  mov     rcx, rdi
0x180085d7f  call    sqlite3_result_null
0x180085d84  jmp     loc_180085F5D
0x180085d89  sub     ecx, 7
0x180085d8c  jz      loc_180085F46
0x180085d92  sub     ecx, 1
0x180085d95  jz      short loc_180085E0A
0x180085d97  sub     ecx, 1
0x180085d9a  jz      short loc_180085E0A
0x180085d9c  sub     ecx, 1
0x180085d9f  jz      loc_180085F46
0x180085da5  sub     ecx, 1
0x180085da8  jz      short loc_180085DC7
0x180085daa  cmp     ecx, 1
0x180085dad  jz      short loc_180085DC7
0x180085daf  or      r8d, 0FFFFFFFFh
0x180085db3  lea     rdx, aMalformedJson; "malformed JSON"
0x180085dba  mov     rcx, rdi
0x180085dbd  call    sqlite3_result_error
0x180085dc2  jmp     loc_180085F5D
0x180085dc7  test    r12d, r12d
0x180085dca  jnz     short loc_180085DF3
0x180085dcc  mov     rcx, rdi
0x180085dcf  call    sqlite3_user_data
0x180085dd4  test    al, 8
0x180085dd6  jz      short loc_180085DF3
0x180085dd8  mov     r8d, [rbp+var_28]
0x180085ddc  or      r9, 0FFFFFFFFFFFFFFFFh
0x180085de0  add     r8d, ebx
0x180085de3  mov     rdx, rsi
0x180085de6  mov     rcx, rdi
0x180085de9  call    sqlite3_result_blob
0x180085dee  jmp     loc_180085F5D
0x180085df3  mov     r8d, [rbp+var_28]
0x180085df7  mov     rdx, rsi
0x180085dfa  add     r8d, ebx
0x180085dfd  mov     rcx, rdi
0x180085e00  call    jsonReturnTextJsonFromBlob
0x180085e05  jmp     loc_180085F5D
0x180085e0a  mov     r12d, [rbp+var_28]
0x180085e0e  mov     rcx, r14
0x180085e11  lea     edx, [r12+1]
0x180085e16  call    sqlite3DbMallocRaw
0x180085e1b  mov     r14, rax
0x180085e1e  test    rax, rax
0x180085e21  jnz     short loc_180085E30
0x180085e23  mov     rcx, rdi
0x180085e26  call    sqlite3_result_error_nomem
0x180085e2b  jmp     loc_180085F5D
0x180085e30  lea     ecx, [rbx+r15]
0x180085e34  xor     ebx, ebx
0x180085e36  add     rcx, r13
0x180085e39  xor     r15d, r15d
0x180085e3c  mov     [rbp+var_18], rcx
0x180085e40  test    r12d, r12d
0x180085e43  jz      loc_180085F32
0x180085e49  lea     esi, [rbx+1]
0x180085e4c  mov     r13b, 3Fh ; '?'
0x180085e4f  mov     r9d, r15d
0x180085e52  add     r9, rcx
0x180085e55  mov     dl, [r9]
0x180085e58  cmp     dl, 5Ch ; '\'
0x180085e5b  jnz     loc_180085F20
0x180085e61  mov     edx, r12d
0x180085e64  mov     [rbp+var_28], 0
0x180085e6b  sub     edx, r15d
0x180085e6e  lea     r8, [rbp+var_28]
0x180085e72  mov     rcx, r9
0x180085e75  call    jsonUnescapeOneChar
0x180085e7a  mov     edx, [rbp+var_28]
0x180085e7d  mov     r8d, eax
0x180085e80  cmp     edx, 7Fh
0x180085e83  jbe     loc_180085F0E
0x180085e89  cmp     edx, 7FFh
0x180085e8f  ja      short loc_180085EA7
0x180085e91  mov     ecx, edx
0x180085e93  shr     ecx, 6
0x180085e96  or      cl, 0C0h
0x180085e99  mov     [rbx+r14], cl
0x180085e9d  add     ebx, esi
0x180085e9f  and     dl, r13b
0x180085ea2  or      dl, 80h
0x180085ea5  jmp     short loc_180085F0E
0x180085ea7  cmp     edx, 10000h
0x180085ead  jnb     short loc_180085ECD
0x180085eaf  mov     ecx, edx
0x180085eb1  mov     eax, edx
0x180085eb3  shr     ecx, 0Ch
0x180085eb6  or      cl, 0E0h
0x180085eb9  shr     eax, 6
0x180085ebc  mov     [rbx+r14], cl
0x180085ec0  and     al, r13b
0x180085ec3  add     ebx, esi
0x180085ec5  or      al, 80h
0x180085ec7  mov     [rbx+r14], al
0x180085ecb  jmp     short loc_180085E9D
0x180085ecd  cmp     edx, 99999h
0x180085ed3  jz      short loc_180085F14
0x180085ed5  mov     ecx, edx
0x180085ed7  mov     eax, edx
0x180085ed9  shr     eax, 0Ch
0x180085edc  mov     r10b, 80h
0x180085edf  and     al, r13b
0x180085ee2  shr     ecx, 12h
0x180085ee5  or      al, r10b
0x180085ee8  or      cl, 0F0h
0x180085eeb  mov     [rbx+r14], cl
0x180085eef  add     ebx, esi
0x180085ef1  mov     [rbx+r14], al
0x180085ef5  mov     eax, edx
0x180085ef7  shr     eax, 6
0x180085efa  add     ebx, esi
0x180085efc  and     al, r13b
0x180085eff  and     dl, r13b
0x180085f02  or      al, r10b
0x180085f05  mov     [rbx+r14], al
0x180085f09  add     ebx, esi
0x180085f0b  or      dl, r10b
0x180085f0e  mov     [rbx+r14], dl
0x180085f12  add     ebx, esi
0x180085f14  mov     rcx, [rbp+var_18]
0x180085f18  dec     r15d
0x180085f1b  add     r15d, r8d
0x180085f1e  jmp     short loc_180085F26
0x180085f20  mov     [rbx+r14], dl
0x180085f24  add     ebx, esi
0x180085f26  add     r15d, esi
0x180085f29  cmp     r15d, r12d
0x180085f2c  jb      loc_180085E4F
0x180085f32  mov     byte ptr [rbx+r14], 0
0x180085f37  lea     r9, sqlite3OomClear
0x180085f3e  mov     r8d, ebx
0x180085f41  mov     rdx, r14
0x180085f44  jmp     short loc_180085F55
0x180085f46  mov     r8d, [rbp+var_28]
0x180085f4a  lea     edx, [rax+r15]
0x180085f4e  add     rdx, r13
0x180085f51  or      r9, 0FFFFFFFFFFFFFFFFh
0x180085f55  mov     rcx, rdi
0x180085f58  call    sqlite3_result_text
0x180085f5d  add     rsp, 48h
0x180085f61  pop     r15
0x180085f63  pop     r14
0x180085f65  pop     r13
0x180085f67  pop     r12
0x180085f69  pop     rdi
0x180085f6a  pop     rsi
0x180085f6b  pop     rbx
0x180085f6c  pop     rbp
0x180085f6d  retn
```
