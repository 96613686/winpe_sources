# jsonParseFuncArg

- ea: `0x180050b6c`
- end: `0x180050e73`
- name: `jsonParseFuncArg`
- size: `775`
- prototype: ``
- caller_count: `8`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x18004db80`
- `0x18004f190`
- `0x18004f97c`
- `0x180050ef0`
- `0x180050fb0`
- `0x180051230`
- `0x1800533b0`
- `0x180053800`

## callees

- `0x180002cf8`
- `0x1800034f2`
- `0x18004e178`
- `0x18004e224`
- `0x18004e2f0`
- `0x18004e400`
- `0x180050b30`
- `0x180050b6c`
- `0x1800539e0`
- `0x1800717b0`
- `0x1800718ac`
- `0x180080b94`
- `0x180092290`
- `0x18009b4ec`
- `0x1800aa490`
- `0x1800ab280`
- `0x1800ae6c0`
- `0x1800ae720`

## string_xrefs

- `0x180050df9`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonParseFuncArg(_DWORD *a1, __int64 a2, char a3)
{
  char v6; // si
  __int64 result; // rax
  _QWORD *v8; // rdi
  __int64 v9; // r15
  _QWORD *v10; // rbx
  __int64 v11; // rdx
  int v12; // eax
  int v13; // r12d
  unsigned __int8 v14; // si
  int v15; // eax
  int v16; // eax
  _DWORD *v17; // rdx
  _QWORD *v18; // rax
  _QWORD *v19; // rsi
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r9
  size_t v23; // rsi
  void *v24; // rax
  char v25; // [rsp+78h] [rbp+10h]
  int v26; // [rsp+88h] [rbp+20h] BYREF

  v6 = *((_BYTE *)qword_1800FE430 + (*(_WORD *)(a2 + 20) & 0x3F));
  v25 = v6;
  if ( v6 == 5 )
    return 0;
  result = jsonCacheSearch();
  v8 = (_QWORD *)result;
  if ( !result || (++*(_DWORD *)(result + 36), (a3 & 1) != 0) )
  {
    v9 = *(_QWORD *)(*(_QWORD *)a1 + 24LL);
    v10 = (_QWORD *)sqlite3DbMallocZero(v9, 72);
    if ( !v10 )
      goto LABEL_33;
    while ( 1 )
    {
      memset_0(v10, 0, 0x48u);
      v10[3] = v9;
      *((_DWORD *)v10 + 9) = 1;
      if ( v8 )
      {
        v23 = *((unsigned int *)v8 + 2);
        if ( v9 )
          v24 = (void *)sqlite3DbMallocRawNN(v9, (unsigned int)v23);
        else
          v24 = (void *)sqlite3Malloc(*((unsigned int *)v8 + 2));
        *v10 = v24;
        if ( v24 )
        {
          memcpy_0(v24, (const void *)*v8, v23);
          *((_DWORD *)v10 + 2) = v23;
          *((_DWORD *)v10 + 3) = v23;
          *((_BYTE *)v10 + 49) = *((_BYTE *)v8 + 49);
          jsonParseFree(v8);
          return (__int64)v10;
        }
LABEL_33:
        jsonParseFree(v8);
        jsonParseFree(v10);
        sqlite3_result_error_nomem(a1);
        return 0;
      }
      if ( v6 == 4 )
      {
        v26 = 0;
        *v10 = sqlite3_value_blob(a2);
        v12 = sqlite3_value_bytes(a2);
        *((_DWORD *)v10 + 2) = v12;
        v13 = v12;
        if ( v12 )
        {
          if ( !*v10 )
            goto LABEL_16;
          v14 = *(_BYTE *)*v10 & 0xF;
          if ( v14 <= 0xCu )
          {
            v15 = jsonbPayloadSize(v10, 0, &v26);
            if ( v15 )
            {
              if ( v26 + v15 == v13 && (v14 > 2u || !v26) )
              {
                if ( (a3 & 1) == 0 || (unsigned int)jsonBlobMakeEditable(v10, 0) )
                  return (__int64)v10;
                goto LABEL_33;
              }
            }
          }
          *((_DWORD *)v10 + 2) = 0;
        }
        *v10 = 0;
      }
LABEL_16:
      LOBYTE(v11) = 1;
      v10[2] = sqlite3ValueText(a2, v11);
      v16 = sqlite3_value_bytes(a2);
      *((_DWORD *)v10 + 8) = v16;
      if ( *(_BYTE *)(v9 + 103) )
        goto LABEL_33;
      if ( !v16 )
      {
        if ( (a3 & 2) == 0 )
        {
          jsonParseFree(v10);
          v21 = *(_QWORD *)a1;
          a1[9] = 1;
          LOBYTE(v22) = 1;
          sqlite3VdbeMemSetStr(v21, "malformed JSON", -1, v22, -1);
          return 0;
        }
LABEL_40:
        *((_BYTE *)v10 + 46) = 1;
        return (__int64)v10;
      }
      v17 = 0;
      if ( (a3 & 2) == 0 )
        v17 = a1;
      if ( (unsigned int)jsonConvertTextToBlob(v10, v17) )
      {
        if ( (a3 & 2) == 0 )
        {
          jsonParseFree(v10);
          return 0;
        }
        goto LABEL_40;
      }
      if ( (*(_WORD *)(a2 + 20) & 0x12) != 0
        && (*(_WORD *)(a2 + 20) & 0x1000) != 0
        && *(__int64 (__fastcall **)())(a2 + 48) == sqlite3RCStrUnref )
      {
        ++*(_QWORD *)(v10[2] - 8LL);
      }
      else
      {
        v18 = (_QWORD *)sqlite3_malloc64(*((int *)v10 + 8) + 9LL);
        if ( !v18 )
          goto LABEL_33;
        v19 = v18 + 1;
        *v18 = 1;
        if ( v18 == (_QWORD *)-8LL )
          goto LABEL_33;
        memcpy_0(v18 + 1, (const void *)v10[2], *((int *)v10 + 8));
        v20 = *((int *)v10 + 8);
        v10[2] = v19;
        *((_BYTE *)v19 + v20) = 0;
      }
      *((_BYTE *)v10 + 48) = 1;
      if ( (unsigned int)jsonCacheInsert(a1, v10) == 7 )
        goto LABEL_33;
      if ( (a3 & 1) == 0 )
        return (__int64)v10;
      v8 = v10;
      v10 = (_QWORD *)sqlite3DbMallocZero(v9, 72);
      if ( !v10 )
        goto LABEL_33;
      v6 = v25;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180050b6c  mov     [rsp+arg_0], rbx
0x180050b71  push    rbp
0x180050b72  push    rsi
0x180050b73  push    rdi
0x180050b74  push    r12
0x180050b76  push    r13
0x180050b78  push    r14
0x180050b7a  push    r15
0x180050b7c  sub     rsp, 30h
0x180050b80  movzx   eax, word ptr [rdx+14h]
0x180050b84  lea     rsi, qword_1800FE430
0x180050b8b  and     eax, 3Fh
0x180050b8e  mov     r13d, r8d
0x180050b91  mov     rbp, rdx
0x180050b94  mov     r14, rcx
0x180050b97  mov     sil, [rax+rsi]
0x180050b9b  mov     [rsp+68h+arg_8], sil
0x180050ba0  cmp     sil, 5
0x180050ba4  jz      loc_180050DC5
0x180050baa  call    jsonCacheSearch
0x180050baf  mov     rdi, rax
0x180050bb2  test    rax, rax
0x180050bb5  jz      short loc_180050BC4
0x180050bb7  inc     dword ptr [rax+24h]
0x180050bba  test    r13b, 1
0x180050bbe  jz      loc_180050DC7
0x180050bc4  mov     rax, [r14]
0x180050bc7  mov     edx, 48h ; 'H'
0x180050bcc  mov     r15, [rax+18h]
0x180050bd0  mov     rcx, r15
0x180050bd3  call    sqlite3DbMallocZero
0x180050bd8  mov     rbx, rax
0x180050bdb  test    rax, rax
0x180050bde  jz      loc_180050DAD
0x180050be4  mov     r12d, 0Ch
0x180050bea  xor     edx, edx; Val
0x180050bec  mov     rcx, rbx; void *
0x180050bef  lea     r8d, [rdx+48h]; Size
0x180050bf3  call    memset_0
0x180050bf8  mov     [rbx+18h], r15
0x180050bfc  mov     dword ptr [rbx+24h], 1
0x180050c03  test    rdi, rdi
0x180050c06  jnz     loc_180050E21
0x180050c0c  cmp     sil, 4
0x180050c10  jnz     loc_180050C99
0x180050c16  mov     rcx, rbp
0x180050c19  mov     [rsp+68h+arg_18], edi
0x180050c20  call    sqlite3_value_blob
0x180050c25  mov     rcx, rbp
0x180050c28  mov     [rbx], rax
0x180050c2b  call    sqlite3_value_bytes
0x180050c30  mov     [rbx+8], eax
0x180050c33  mov     r12d, eax
0x180050c36  test    eax, eax
0x180050c38  jz      short loc_180050C8C
0x180050c3a  mov     rsi, [rbx]
0x180050c3d  test    rsi, rsi
0x180050c40  jz      short loc_180050C93
0x180050c42  mov     sil, [rsi]
0x180050c45  and     sil, 0Fh
0x180050c49  cmp     sil, 0Ch
0x180050c4d  ja      short loc_180050C85
0x180050c4f  lea     r8, [rsp+68h+arg_18]
0x180050c57  xor     edx, edx
0x180050c59  mov     rcx, rbx
0x180050c5c  call    jsonbPayloadSize
0x180050c61  test    eax, eax
0x180050c63  jz      short loc_180050C85
0x180050c65  mov     ecx, [rsp+68h+arg_18]
0x180050c6c  add     eax, ecx
0x180050c6e  cmp     eax, r12d
0x180050c71  jnz     short loc_180050C85
0x180050c73  cmp     sil, 2
0x180050c77  ja      loc_180050D91
0x180050c7d  test    ecx, ecx
0x180050c7f  jz      loc_180050D91
0x180050c85  mov     dword ptr [rbx+8], 0
0x180050c8c  mov     qword ptr [rbx], 0
0x180050c93  mov     r12d, 0Ch
0x180050c99  mov     dl, 1
0x180050c9b  mov     rcx, rbp
0x180050c9e  call    sqlite3ValueText
0x180050ca3  mov     rcx, rbp
0x180050ca6  mov     [rbx+10h], rax
0x180050caa  call    sqlite3_value_bytes
0x180050caf  mov     [rbx+20h], eax
0x180050cb2  cmp     byte ptr [r15+67h], 0
0x180050cb7  jnz     loc_180050DAD
0x180050cbd  mov     esi, r13d
0x180050cc0  and     esi, 2
0x180050cc3  test    eax, eax
0x180050cc5  jz      loc_180050DEA
0x180050ccb  xor     edx, edx
0x180050ccd  mov     rcx, rbx
0x180050cd0  test    esi, esi
0x180050cd2  cmovz   rdx, r14
0x180050cd6  call    jsonConvertTextToBlob
0x180050cdb  test    eax, eax
0x180050cdd  jnz     loc_180050DDC
0x180050ce3  movzx   eax, word ptr [rbp+14h]
0x180050ce7  test    al, 12h
0x180050ce9  setnz   cl
0x180050cec  bt      ax, r12w
0x180050cf1  setb    al
0x180050cf4  test    al, cl
0x180050cf6  jz      short loc_180050D0F
0x180050cf8  lea     rax, sqlite3RCStrUnref
0x180050cff  cmp     [rbp+30h], rax
0x180050d03  jnz     short loc_180050D0F
0x180050d05  mov     rax, [rbx+10h]
0x180050d09  inc     qword ptr [rax-8]
0x180050d0d  jmp     short loc_180050D51
0x180050d0f  movsxd  rcx, dword ptr [rbx+20h]
0x180050d13  add     rcx, 9
0x180050d17  call    sqlite3_malloc64
0x180050d1c  test    rax, rax
0x180050d1f  jz      loc_180050DAD
0x180050d25  lea     rsi, [rax+8]
0x180050d29  mov     qword ptr [rax], 1
0x180050d30  test    rsi, rsi
0x180050d33  jz      short loc_180050DAD
0x180050d35  movsxd  r8, dword ptr [rbx+20h]; Size
0x180050d39  mov     rcx, rsi; void *
0x180050d3c  mov     rdx, [rbx+10h]; Src
0x180050d40  call    memcpy_0
0x180050d45  movsxd  rax, dword ptr [rbx+20h]
0x180050d49  mov     [rbx+10h], rsi
0x180050d4d  mov     byte ptr [rax+rsi], 0
0x180050d51  mov     rdx, rbx
0x180050d54  mov     byte ptr [rbx+30h], 1
0x180050d58  mov     rcx, r14
0x180050d5b  call    jsonCacheInsert
0x180050d60  cmp     eax, 7
0x180050d63  jz      short loc_180050DAD
0x180050d65  test    r13b, 1
0x180050d69  jz      loc_180050E6B
0x180050d6f  mov     edx, 48h ; 'H'
0x180050d74  mov     rcx, r15
0x180050d77  mov     rdi, rbx
0x180050d7a  call    sqlite3DbMallocZero
0x180050d7f  mov     rbx, rax
0x180050d82  test    rax, rax
0x180050d85  jz      short loc_180050DAD
0x180050d87  mov     sil, [rsp+68h+arg_8]
0x180050d8c  jmp     loc_180050BEA
0x180050d91  test    r13b, 1
0x180050d95  jz      loc_180050E6B
0x180050d9b  xor     edx, edx
0x180050d9d  mov     rcx, rbx
0x180050da0  call    jsonBlobMakeEditable
0x180050da5  test    eax, eax
0x180050da7  jnz     loc_180050E6B
0x180050dad  mov     rcx, rdi
0x180050db0  call    jsonParseFree
0x180050db5  mov     rcx, rbx
0x180050db8  call    jsonParseFree
0x180050dbd  mov     rcx, r14
0x180050dc0  call    sqlite3_result_error_nomem
0x180050dc5  xor     eax, eax
0x180050dc7  mov     rbx, [rsp+68h+arg_0]
0x180050dcc  add     rsp, 30h
0x180050dd0  pop     r15
0x180050dd2  pop     r14
0x180050dd4  pop     r13
0x180050dd6  pop     r12
0x180050dd8  pop     rdi
0x180050dd9  pop     rsi
0x180050dda  pop     rbp
0x180050ddb  retn
0x180050ddc  test    esi, esi
0x180050dde  jnz     short loc_180050E1B
0x180050de0  mov     rcx, rbx
0x180050de3  call    jsonParseFree
0x180050de8  jmp     short loc_180050DC5
0x180050dea  test    esi, esi
0x180050dec  jnz     short loc_180050E1B
0x180050dee  mov     rcx, rbx
0x180050df1  call    jsonParseFree
0x180050df6  mov     rcx, [r14]
0x180050df9  lea     rdx, aMalformedJson; "malformed JSON"
0x180050e00  or      r8, 0FFFFFFFFFFFFFFFFh
0x180050e04  mov     dword ptr [r14+24h], 1
0x180050e0c  mov     r9b, 1
0x180050e0f  mov     [rsp+68h+var_48], r8
0x180050e14  call    sqlite3VdbeMemSetStr
0x180050e19  jmp     short loc_180050DC5
0x180050e1b  mov     byte ptr [rbx+2Eh], 1
0x180050e1f  jmp     short loc_180050E6B
0x180050e21  mov     esi, [rdi+8]
0x180050e24  test    r15, r15
0x180050e27  jz      short loc_180050E35
0x180050e29  mov     edx, esi
0x180050e2b  mov     rcx, r15
0x180050e2e  call    sqlite3DbMallocRawNN
0x180050e33  jmp     short loc_180050E3D
0x180050e35  mov     rcx, rsi
0x180050e38  call    sqlite3Malloc
0x180050e3d  mov     [rbx], rax
0x180050e40  test    rax, rax
0x180050e43  jz      loc_180050DAD
0x180050e49  mov     rdx, [rdi]; Src
0x180050e4c  mov     r8, rsi; Size
0x180050e4f  mov     rcx, rax; void *
0x180050e52  call    memcpy_0
0x180050e57  mov     [rbx+8], esi
0x180050e5a  mov     rcx, rdi
0x180050e5d  mov     [rbx+0Ch], esi
0x180050e60  mov     al, [rdi+31h]
0x180050e63  mov     [rbx+31h], al
0x180050e66  call    jsonParseFree
0x180050e6b  mov     rax, rbx
0x180050e6e  jmp     loc_180050DC7
```
