# jsonReturnFromBlob

- ea: `0x180076974`
- end: `0x180076d5e`
- name: `jsonReturnFromBlob`
- size: `1002`
- prototype: `__int64 __fastcall(__int64 *, unsigned int, __int64, int)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config`

## callers

- `0x180073ec0`
- `0x180074920`

## callees

- `0x180005810`
- `0x18000a9e0`
- `0x180010c34`
- `0x180034bec`
- `0x180048740`
- `0x180048d20`
- `0x18005ede0`
- `0x18005ee00`
- `0x180066960`
- `0x180068190`
- `0x180076974`
- `0x180077008`
- `0x18007864c`
- `0x180078a58`
- `0x180080f6c`
- `0x18008f340`
- `0x18008f3d0`
- `0x18008f3f0`
- `0x18008f470`
- `0x18008f510`

## string_xrefs

- `0x180076ba3`: `malformed JSON`

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
0x180076974  mov     [rsp-40h+arg_0], rcx
0x180076979  push    rbp
0x18007697a  push    rbx
0x18007697b  push    rsi
0x18007697c  push    rdi
0x18007697d  push    r12
0x18007697f  push    r13
0x180076981  push    r14
0x180076983  push    r15
0x180076985  mov     rbp, rsp
0x180076988  sub     rsp, 48h
0x18007698c  mov     rsi, rcx
0x18007698f  mov     r15d, edx
0x180076992  mov     rcx, r8
0x180076995  mov     [rbp+var_28], 0
0x18007699c  mov     r12d, r9d
0x18007699f  mov     rdi, r8
0x1800769a2  call    sqlite3_context_db_handle
0x1800769a7  lea     r8, [rbp+var_28]
0x1800769ab  mov     [rbp+var_18], rax
0x1800769af  mov     edx, r15d
0x1800769b2  mov     rcx, rsi
0x1800769b5  mov     r14, rax
0x1800769b8  call    jsonbPayloadSize
0x1800769bd  xor     edx, edx
0x1800769bf  mov     ebx, eax
0x1800769c1  test    eax, eax
0x1800769c3  jz      loc_180076B9F
0x1800769c9  mov     r13, [rsi]
0x1800769cc  lea     rsi, [r15+r13]
0x1800769d0  movzx   ecx, byte ptr [rsi]
0x1800769d3  and     ecx, 0Fh
0x1800769d6  cmp     ecx, 6
0x1800769d9  ja      loc_180076B79
0x1800769df  lea     esi, [rdx+1]
0x1800769e2  jz      short loc_180076A14
0x1800769e4  test    ecx, ecx
0x1800769e6  jz      loc_180076B67
0x1800769ec  sub     ecx, esi
0x1800769ee  jz      loc_180076B53
0x1800769f4  sub     ecx, esi
0x1800769f6  jz      loc_180076B4C
0x1800769fc  sub     ecx, esi
0x1800769fe  jz      loc_180076A8D
0x180076a04  sub     ecx, esi
0x180076a06  jz      loc_180076A8D
0x180076a0c  cmp     ecx, esi
0x180076a0e  jnz     loc_180076B9F
0x180076a14  mov     r14d, [rbp+var_28]
0x180076a18  xorps   xmm0, xmm0
0x180076a1b  movsd   [rbp+var_20], xmm0
0x180076a20  test    r14d, r14d
0x180076a23  jz      loc_180076B9F
0x180076a29  mov     r13, [rbp+var_18]
0x180076a2d  mov     rax, [rbp+arg_0]
0x180076a31  lea     edx, [rbx+r15]
0x180076a35  movsxd  r8, r14d
0x180076a38  mov     rcx, r13
0x180076a3b  add     rdx, [rax]
0x180076a3e  call    sqlite3DbStrNDup
0x180076a43  mov     r14, rax
0x180076a46  test    rax, rax
0x180076a49  jz      loc_180076C13
0x180076a4f  mov     rcx, rax
0x180076a52  call    sqlite3Strlen30
0x180076a57  mov     r8d, eax
0x180076a5a  lea     rdx, [rbp+var_20]
0x180076a5e  mov     r9b, sil
0x180076a61  call    sqlite3AtoF
0x180076a66  mov     rdx, r14
0x180076a69  mov     rcx, r13
0x180076a6c  mov     ebx, eax
0x180076a6e  call    sqlite3DbFree
0x180076a73  test    ebx, ebx
0x180076a75  jle     loc_180076B9F
0x180076a7b  movsd   xmm1, [rbp+var_20]
0x180076a80  mov     rcx, rdi
0x180076a83  call    sqlite3_result_double
0x180076a88  jmp     loc_180076D4D
0x180076a8d  mov     r14d, [rbp+var_28]
0x180076a91  mov     [rbp+var_20], rdx
0x180076a95  test    r14d, r14d
0x180076a98  jz      loc_180076B9F
0x180076a9e  add     eax, r15d
0x180076aa1  mov     r12d, edx
0x180076aa4  cmp     byte ptr [rax+r13], 2Dh ; '-'
0x180076aa9  jnz     short loc_180076ABD
0x180076aab  cmp     r14d, 2
0x180076aaf  jb      loc_180076B9F
0x180076ab5  add     ebx, esi
0x180076ab7  mov     r12d, esi
0x180076aba  dec     r14d
0x180076abd  lea     edx, [rbx+r15]
0x180076ac1  movsxd  r8, r14d
0x180076ac4  add     rdx, r13
0x180076ac7  mov     r13, [rbp+var_18]
0x180076acb  mov     rcx, r13
0x180076ace  call    sqlite3DbStrNDup
0x180076ad3  mov     [rbp+var_18], rax
0x180076ad7  test    rax, rax
0x180076ada  jz      loc_180076C13
0x180076ae0  lea     rdx, [rbp+var_20]
0x180076ae4  mov     rcx, rax; Str
0x180076ae7  call    sqlite3DecOrHexToI64
0x180076aec  mov     rdx, [rbp+var_18]
0x180076af0  mov     rcx, r13
0x180076af3  mov     [rbp+var_28], eax
0x180076af6  call    sqlite3DbFree
0x180076afb  mov     eax, [rbp+var_28]
0x180076afe  test    eax, eax
0x180076b00  jnz     short loc_180076B10
0x180076b02  mov     rdx, [rbp+var_20]
0x180076b06  test    r12d, r12d
0x180076b09  jz      short loc_180076B28
0x180076b0b  neg     rdx
0x180076b0e  jmp     short loc_180076B28
0x180076b10  cmp     eax, 3
0x180076b13  jnz     short loc_180076B35
0x180076b15  test    r12d, r12d
0x180076b18  jz      loc_180076A2D
0x180076b1e  mov     rdx, 8000000000000000h
0x180076b28  mov     rcx, rdi
0x180076b2b  call    sqlite3_result_int64
0x180076b30  jmp     loc_180076D4D
0x180076b35  cmp     eax, esi
0x180076b37  jz      short loc_180076B9F
0x180076b39  test    r12d, r12d
0x180076b3c  jz      loc_180076A2D
0x180076b42  dec     ebx
0x180076b44  add     r14d, esi
0x180076b47  jmp     loc_180076A2D
0x180076b4c  cmp     [rbp+var_28], edx
0x180076b4f  jnz     short loc_180076B9F
0x180076b51  jmp     short loc_180076B5A
0x180076b53  cmp     [rbp+var_28], edx
0x180076b56  jnz     short loc_180076B9F
0x180076b58  mov     edx, esi
0x180076b5a  mov     rcx, rdi
0x180076b5d  call    sqlite3_result_int
0x180076b62  jmp     loc_180076D4D
0x180076b67  cmp     [rbp+var_28], edx
0x180076b6a  jnz     short loc_180076B9F
0x180076b6c  mov     rcx, rdi
0x180076b6f  call    sqlite3_result_null
0x180076b74  jmp     loc_180076D4D
0x180076b79  sub     ecx, 7
0x180076b7c  jz      loc_180076D36
0x180076b82  sub     ecx, 1
0x180076b85  jz      short loc_180076BFA
0x180076b87  sub     ecx, 1
0x180076b8a  jz      short loc_180076BFA
0x180076b8c  sub     ecx, 1
0x180076b8f  jz      loc_180076D36
0x180076b95  sub     ecx, 1
0x180076b98  jz      short loc_180076BB7
0x180076b9a  cmp     ecx, 1
0x180076b9d  jz      short loc_180076BB7
0x180076b9f  or      r8d, 0FFFFFFFFh
0x180076ba3  lea     rdx, aMalformedJson; "malformed JSON"
0x180076baa  mov     rcx, rdi
0x180076bad  call    sqlite3_result_error
0x180076bb2  jmp     loc_180076D4D
0x180076bb7  test    r12d, r12d
0x180076bba  jnz     short loc_180076BE3
0x180076bbc  mov     rcx, rdi
0x180076bbf  call    sqlite3_user_data
0x180076bc4  test    al, 8
0x180076bc6  jz      short loc_180076BE3
0x180076bc8  mov     r8d, [rbp+var_28]
0x180076bcc  or      r9, 0FFFFFFFFFFFFFFFFh
0x180076bd0  add     r8d, ebx
0x180076bd3  mov     rdx, rsi
0x180076bd6  mov     rcx, rdi
0x180076bd9  call    sqlite3_result_blob
0x180076bde  jmp     loc_180076D4D
0x180076be3  mov     r8d, [rbp+var_28]
0x180076be7  mov     rdx, rsi
0x180076bea  add     r8d, ebx
0x180076bed  mov     rcx, rdi
0x180076bf0  call    jsonReturnTextJsonFromBlob
0x180076bf5  jmp     loc_180076D4D
0x180076bfa  mov     r12d, [rbp+var_28]
0x180076bfe  mov     rcx, r14
0x180076c01  lea     edx, [r12+1]
0x180076c06  call    sqlite3DbMallocRaw
0x180076c0b  mov     r14, rax
0x180076c0e  test    rax, rax
0x180076c11  jnz     short loc_180076C20
0x180076c13  mov     rcx, rdi
0x180076c16  call    sqlite3_result_error_nomem
0x180076c1b  jmp     loc_180076D4D
0x180076c20  lea     ecx, [rbx+r15]
0x180076c24  xor     ebx, ebx
0x180076c26  add     rcx, r13
0x180076c29  xor     r15d, r15d
0x180076c2c  mov     [rbp+var_18], rcx
0x180076c30  test    r12d, r12d
0x180076c33  jz      loc_180076D22
0x180076c39  lea     esi, [rbx+1]
0x180076c3c  mov     r13b, 3Fh ; '?'
0x180076c3f  mov     r9d, r15d
0x180076c42  add     r9, rcx
0x180076c45  mov     dl, [r9]
0x180076c48  cmp     dl, 5Ch ; '\'
0x180076c4b  jnz     loc_180076D10
0x180076c51  mov     edx, r12d
0x180076c54  mov     [rbp+var_28], 0
0x180076c5b  sub     edx, r15d
0x180076c5e  lea     r8, [rbp+var_28]
0x180076c62  mov     rcx, r9
0x180076c65  call    jsonUnescapeOneChar
0x180076c6a  mov     edx, [rbp+var_28]
0x180076c6d  mov     r8d, eax
0x180076c70  cmp     edx, 7Fh
0x180076c73  jbe     loc_180076CFE
0x180076c79  cmp     edx, 7FFh
0x180076c7f  ja      short loc_180076C97
0x180076c81  mov     ecx, edx
0x180076c83  shr     ecx, 6
0x180076c86  or      cl, 0C0h
0x180076c89  mov     [rbx+r14], cl
0x180076c8d  add     ebx, esi
0x180076c8f  and     dl, r13b
0x180076c92  or      dl, 80h
0x180076c95  jmp     short loc_180076CFE
0x180076c97  cmp     edx, 10000h
0x180076c9d  jnb     short loc_180076CBD
0x180076c9f  mov     ecx, edx
0x180076ca1  mov     eax, edx
0x180076ca3  shr     ecx, 0Ch
0x180076ca6  or      cl, 0E0h
0x180076ca9  shr     eax, 6
0x180076cac  mov     [rbx+r14], cl
0x180076cb0  and     al, r13b
0x180076cb3  add     ebx, esi
0x180076cb5  or      al, 80h
0x180076cb7  mov     [rbx+r14], al
0x180076cbb  jmp     short loc_180076C8D
0x180076cbd  cmp     edx, 99999h
0x180076cc3  jz      short loc_180076D04
0x180076cc5  mov     ecx, edx
0x180076cc7  mov     eax, edx
0x180076cc9  shr     eax, 0Ch
0x180076ccc  mov     r10b, 80h
0x180076ccf  and     al, r13b
0x180076cd2  shr     ecx, 12h
0x180076cd5  or      al, r10b
0x180076cd8  or      cl, 0F0h
0x180076cdb  mov     [rbx+r14], cl
0x180076cdf  add     ebx, esi
0x180076ce1  mov     [rbx+r14], al
0x180076ce5  mov     eax, edx
0x180076ce7  shr     eax, 6
0x180076cea  add     ebx, esi
0x180076cec  and     al, r13b
0x180076cef  and     dl, r13b
0x180076cf2  or      al, r10b
0x180076cf5  mov     [rbx+r14], al
0x180076cf9  add     ebx, esi
0x180076cfb  or      dl, r10b
0x180076cfe  mov     [rbx+r14], dl
0x180076d02  add     ebx, esi
0x180076d04  mov     rcx, [rbp+var_18]
0x180076d08  dec     r15d
0x180076d0b  add     r15d, r8d
0x180076d0e  jmp     short loc_180076D16
0x180076d10  mov     [rbx+r14], dl
0x180076d14  add     ebx, esi
0x180076d16  add     r15d, esi
0x180076d19  cmp     r15d, r12d
0x180076d1c  jb      loc_180076C3F
0x180076d22  mov     byte ptr [rbx+r14], 0
0x180076d27  lea     r9, sqlite3OomClear
0x180076d2e  mov     r8d, ebx
0x180076d31  mov     rdx, r14
0x180076d34  jmp     short loc_180076D45
0x180076d36  mov     r8d, [rbp+var_28]
0x180076d3a  lea     edx, [rax+r15]
0x180076d3e  add     rdx, r13
0x180076d41  or      r9, 0FFFFFFFFFFFFFFFFh
0x180076d45  mov     rcx, rdi
0x180076d48  call    sqlite3_result_text
0x180076d4d  add     rsp, 48h
0x180076d51  pop     r15
0x180076d53  pop     r14
0x180076d55  pop     r13
0x180076d57  pop     r12
0x180076d59  pop     rdi
0x180076d5a  pop     rsi
0x180076d5b  pop     rbx
0x180076d5c  pop     rbp
0x180076d5d  retn
```
