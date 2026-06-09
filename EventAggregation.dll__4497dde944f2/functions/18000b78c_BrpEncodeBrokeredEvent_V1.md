# BrpEncodeBrokeredEvent_V1

- ea: `0x18000b78c`
- end: `0x18000bcc7`
- name: `BrpEncodeBrokeredEvent_V1`
- size: `1339`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009250`

## callees

- `0x18000b78c`
- `0x18000bcd0`
- `0x18000bcf8`
- `0x18000bde9`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000b8b2`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000bb50`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000b8b2`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000bb50`

## pseudocode

```c
__int64 __fastcall BrpEncodeBrokeredEvent_V1(__int64 a1, USHORT a2, __int64 a3, USHORT *a4)
{
  USHORT v5; // cx
  USHORT v6; // r13
  int v7; // r15d
  __int16 v8; // bx
  USHORT v9; // r9
  __int64 v10; // rdi
  int v11; // r11d
  USHORT v12; // r9
  USHORT v13; // cx
  int i; // eax
  USHORT v15; // cx
  __int64 v16; // rsi
  const wchar_t *v17; // rcx
  size_t v18; // rax
  USHORT v19; // cx
  USHORT v20; // r9
  __int64 v21; // r8
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  USHORT v26; // cx
  __int16 v27; // r10
  __int64 v28; // rcx
  unsigned __int16 v29; // r10
  __int64 v30; // rdx
  unsigned int v31; // r14d
  USHORT v32; // dx
  USHORT v33; // cx
  __int64 v34; // rdx
  unsigned int v35; // r14d
  USHORT v36; // dx
  const wchar_t *v37; // rcx
  size_t v38; // rax
  USHORT v39; // r10
  int v40; // r9d
  USHORT v42[2]; // [rsp+20h] [rbp-28h] BYREF
  USHORT v43[2]; // [rsp+24h] [rbp-24h] BYREF
  USHORT v44[2]; // [rsp+28h] [rbp-20h] BYREF
  USHORT v45; // [rsp+2Ch] [rbp-1Ch] BYREF
  int v46; // [rsp+30h] [rbp-18h]
  int v47; // [rsp+34h] [rbp-14h]
  int v48; // [rsp+38h] [rbp-10h]
  USHORT pusResult; // [rsp+90h] [rbp+48h] BYREF
  USHORT v50; // [rsp+98h] [rbp+50h]
  __int64 v51; // [rsp+A0h] [rbp+58h]
  USHORT *v52; // [rsp+A8h] [rbp+60h]

  v52 = a4;
  v51 = a3;
  v50 = a2;
  LOWORD(v46) = 1;
  v47 = 0;
  v5 = 0;
  v45 = 0;
  pusResult = 0;
  v6 = 0;
  v42[0] = 0;
  v7 = 0;
  v44[0] = 0;
  v43[0] = 0;
  if ( !a1 || !a4 )
    return 3221225485LL;
  v8 = v46;
  v9 = 2;
  v10 = 0;
  v11 = 0;
  while ( 2 )
  {
    v48 = v11;
    if ( (unsigned __int16)v11 >= v9 )
    {
      *v52 = v6;
      return 0;
    }
    if ( v10 )
      *(_WORD *)(v5 + v10) = v8;
    if ( UShortAdd(v5, v9, &pusResult) < 0 )
      return 3221225621LL;
    v13 = pusResult;
    if ( v10 )
      *(_WORD *)(pusResult + v10) = *(_WORD *)a1;
    if ( UShortAdd(v13, v12, &pusResult) < 0 )
      return 3221225621LL;
    for ( i = 0; ; LOWORD(i) = v46 + 1 )
    {
      v46 = i;
      if ( (unsigned __int16)i >= *(_WORD *)a1 )
        break;
      v15 = pusResult;
      v16 = 32LL * (unsigned __int16)i;
      if ( *(_QWORD *)(v16 + *(_QWORD *)(a1 + 8)) )
      {
        if ( v10 )
          *(_WORD *)(pusResult + v10) = v7;
        if ( UShortAdd(v15, v9, &pusResult) < 0 )
          return 3221225621LL;
        v17 = *(const wchar_t **)(v16 + *(_QWORD *)(a1 + 8));
        if ( !v17 )
          return 3221225485LL;
        v18 = wcsnlen(v17, 0x40u);
        if ( UIntPtrToUShort(2 * v18 + 2, v42) < 0 )
          return 3221225621LL;
        if ( v10 )
          memcpy_0((void *)(v10 + (unsigned __int16)v7), *(const void **)(v16 + *(_QWORD *)(a1 + 8)), v42[0]);
        if ( UShortAdd(v7, v42[0], v43) < 0 )
          return 3221225621LL;
        v7 = v43[0];
      }
      else
      {
        if ( v10 )
          *(_WORD *)(pusResult + v10) = 0;
        if ( UShortAdd(v15, v9, &pusResult) < 0 )
          return 3221225621LL;
      }
      v19 = pusResult;
      if ( v10 )
        *(_DWORD *)(pusResult + v10) = *(_DWORD *)(v16 + *(_QWORD *)(a1 + 8) + 8);
      if ( UShortAdd(v19, 4u, &pusResult) < 0 )
        return 3221225621LL;
      v21 = *(_QWORD *)(a1 + 8);
      v22 = *(_DWORD *)(v16 + v21 + 8);
      if ( !v22 )
      {
        LOWORD(v28) = pusResult;
        if ( v10 )
          *(_DWORD *)(pusResult + v10) = *(_DWORD *)(v16 + v21 + 16);
        v32 = 4;
LABEL_78:
        if ( UShortAdd(v28, v32, &pusResult) < 0 )
          return 3221225621LL;
        goto LABEL_79;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        LOWORD(v28) = pusResult;
        if ( v10 )
          *(_QWORD *)(pusResult + v10) = *(_QWORD *)(v16 + v21 + 16);
        v32 = 8;
        goto LABEL_78;
      }
      v24 = v23 - 1;
      if ( !v24 )
      {
        v28 = pusResult;
        if ( *(_QWORD *)(v16 + v21 + 16) )
        {
          if ( v10 )
            *(_WORD *)(pusResult + v10) = v7;
          if ( UShortAdd(v28, v20, &pusResult) < 0 )
            return 3221225621LL;
          v37 = *(const wchar_t **)(v16 + *(_QWORD *)(a1 + 8) + 16);
          v38 = v37 ? wcsnlen(v37, 0x800u) : 0LL;
          if ( UIntPtrToUShort(2 * v38 + 2, v42) < 0 )
            return 3221225621LL;
          if ( v10 )
            memcpy_0((void *)(v10 + (unsigned __int16)v7), *(const void **)(v16 + *(_QWORD *)(a1 + 8) + 16), v42[0]);
          v36 = v42[0];
          goto LABEL_59;
        }
        goto LABEL_45;
      }
      v25 = v24 - 1;
      if ( !v25 )
      {
        v33 = pusResult;
        if ( v10 )
          *(_WORD *)(pusResult + v10) = *(_WORD *)(v16 + v21 + 16);
        if ( UShortAdd(v33, v20, &pusResult) < 0 )
          return 3221225621LL;
        v28 = pusResult;
        if ( *(_QWORD *)(v16 + *(_QWORD *)(a1 + 8) + 24) )
        {
          if ( v10 )
            *(_WORD *)(pusResult + v10) = v7;
          if ( UShortAdd(v28, v20, &pusResult) < 0 )
            return 3221225621LL;
          v34 = *(_QWORD *)(a1 + 8);
          v35 = 2 * *(unsigned __int16 *)(v16 + v34 + 16);
          if ( v35 > 0xFFFF )
            return 3221225621LL;
          v42[0] = 2 * *(_WORD *)(v16 + v34 + 16);
          if ( v10 )
            memcpy_0((void *)(v10 + (unsigned __int16)v7), *(const void **)(v16 + v34 + 24), (unsigned __int16)v35);
          v36 = v35;
LABEL_59:
          if ( UShortAdd(v7, v36, v43) < 0 )
            return 3221225621LL;
          v7 = v43[0];
          goto LABEL_79;
        }
LABEL_45:
        if ( v10 )
          *(_WORD *)(v28 + v10) = 0;
        v32 = v20;
        goto LABEL_78;
      }
      if ( v25 != 1 )
        return 3221225701LL;
      v26 = pusResult;
      if ( v10 )
        *(_WORD *)(pusResult + v10) = *(_WORD *)(v16 + v21 + 16);
      if ( UShortAdd(v26, v20, &pusResult) < 0 )
        return 3221225621LL;
      v28 = pusResult;
      if ( !*(_QWORD *)(v16 + *(_QWORD *)(a1 + 8) + 24) )
        goto LABEL_45;
      if ( v10 )
        *(_WORD *)(pusResult + v10) = v27;
      if ( UShortAdd(v28, v20, &pusResult) < 0 )
        return 3221225621LL;
      v30 = *(_QWORD *)(a1 + 8);
      v31 = *(unsigned __int16 *)(v16 + v30 + 16);
      v42[0] = *(_WORD *)(v16 + v30 + 16);
      if ( v10 )
        memcpy_0((void *)(v10 + v29), *(const void **)(v16 + v30 + 24), v31);
      if ( UShortAdd(v47, v31, &v45) < 0 )
        return 3221225621LL;
      v47 = v45;
LABEL_79:
      HIWORD(i) = HIWORD(v46);
      v9 = 2;
    }
    if ( v10 )
    {
      v5 = pusResult;
      goto LABEL_88;
    }
    if ( UShortAdd(v6, pusResult, v44) < 0 || UShortAdd(v44[0], v7, v44) < 0 || UShortAdd(v44[0], v39, v44) < 0 )
      return 3221225621LL;
    v6 = v44[0];
    if ( v51 && v50 >= v44[0] )
    {
      v43[0] = v40;
      v47 = v40 + v7;
      v7 = (unsigned __int16)v40;
      v45 = v47;
      v10 = v51;
      pusResult = 0;
      v5 = 0;
      v9 = 2;
LABEL_88:
      HIWORD(v11) = HIWORD(v48);
      LOWORD(v11) = v48 + 1;
      continue;
    }
    break;
  }
  *v52 = v44[0];
  return 3221225507LL;
}

```

## disassembly

```asm
0x18000b78c  mov     [rsp-40h+arg_18], r9
0x18000b791  mov     [rsp-40h+arg_10], r8
0x18000b796  mov     [rsp-40h+arg_8], dx
0x18000b79b  push    rbp
0x18000b79c  push    rbx
0x18000b79d  push    rsi
0x18000b79e  push    rdi
0x18000b79f  push    r12
0x18000b7a1  push    r13
0x18000b7a3  push    r14
0x18000b7a5  push    r15
0x18000b7a7  mov     rbp, rsp
0x18000b7aa  sub     rsp, 48h
0x18000b7ae  xor     r10d, r10d
0x18000b7b1  mov     word ptr [rbp+var_18], 1
0x18000b7b7  mov     r12, rcx
0x18000b7ba  mov     [rbp+var_14], r10d
0x18000b7be  xor     ecx, ecx; usAugend
0x18000b7c0  mov     [rbp+var_1C], r10w
0x18000b7c5  xor     eax, eax
0x18000b7c7  mov     [rbp+pusResult], cx
0x18000b7cb  xor     r13d, r13d
0x18000b7ce  mov     [rbp+var_28], ax
0x18000b7d2  xor     r15d, r15d
0x18000b7d5  mov     [rbp+var_20], r13w
0x18000b7da  mov     [rbp+var_24], r15w
0x18000b7df  test    r12, r12
0x18000b7e2  jz      loc_18000BCB1
0x18000b7e8  test    r9, r9
0x18000b7eb  jz      loc_18000BCB1
0x18000b7f1  movzx   ebx, word ptr [rbp+var_18]
0x18000b7f5  lea     r9d, [rax+2]
0x18000b7f9  xor     edi, edi
0x18000b7fb  xor     r11d, r11d
0x18000b7fe  mov     [rbp+var_10], r11d
0x18000b802  cmp     r11w, r9w
0x18000b806  jnb     loc_18000BCA5
0x18000b80c  test    rdi, rdi
0x18000b80f  jz      short loc_18000B818
0x18000b811  movzx   eax, cx
0x18000b814  mov     [rax+rdi], bx
0x18000b818  mov     edx, r9d; usAddend
0x18000b81b  lea     r8, [rbp+pusResult]; pusResult
0x18000b81f  call    UShortAdd
0x18000b824  test    eax, eax
0x18000b826  js      loc_18000BC9E
0x18000b82c  movzx   ecx, [rbp+pusResult]; usAugend
0x18000b830  test    rdi, rdi
0x18000b833  jz      short loc_18000B83E
0x18000b835  movzx   eax, word ptr [r12]
0x18000b83a  mov     [rcx+rdi], ax
0x18000b83e  mov     edx, r9d; usAddend
0x18000b841  lea     r8, [rbp+pusResult]; pusResult
0x18000b845  call    UShortAdd
0x18000b84a  test    eax, eax
0x18000b84c  js      loc_18000BC9E
0x18000b852  xor     eax, eax
0x18000b854  mov     [rbp+var_18], eax
0x18000b857  cmp     ax, [r12]
0x18000b85c  jnb     loc_18000BBE9
0x18000b862  movzx   ecx, [rbp+pusResult]; usAugend
0x18000b866  movzx   esi, ax
0x18000b869  mov     rax, [r12+8]
0x18000b86e  shl     rsi, 5
0x18000b872  cmp     qword ptr [rsi+rax], 0
0x18000b877  jz      loc_18000B91A
0x18000b87d  test    rdi, rdi
0x18000b880  jz      short loc_18000B887
0x18000b882  mov     [rcx+rdi], r15w
0x18000b887  mov     edx, r9d; usAddend
0x18000b88a  lea     r8, [rbp+pusResult]; pusResult
0x18000b88e  call    UShortAdd
0x18000b893  test    eax, eax
0x18000b895  js      loc_18000BC9E
0x18000b89b  mov     rax, [r12+8]
0x18000b8a0  mov     rcx, [rsi+rax]; Source
0x18000b8a4  test    rcx, rcx
0x18000b8a7  jz      loc_18000BCB1
0x18000b8ad  mov     edx, 40h ; '@'; MaxCount
0x18000b8b2  call    cs:__imp_wcsnlen
0x18000b8b8  lea     rdx, [rbp+var_28]; pusResult
0x18000b8bc  lea     rcx, ds:2[rax*2]; uOperand
0x18000b8c4  call    UIntPtrToUShort
0x18000b8c9  test    eax, eax
0x18000b8cb  js      loc_18000BC9E
0x18000b8d1  test    rdi, rdi
0x18000b8d4  jz      short loc_18000B8F0
0x18000b8d6  mov     rdx, [r12+8]
0x18000b8db  movzx   r8d, [rbp+var_28]; Size
0x18000b8e0  movzx   ecx, r15w
0x18000b8e4  add     rcx, rdi; void *
0x18000b8e7  mov     rdx, [rsi+rdx]; Src
0x18000b8eb  call    memcpy_0
0x18000b8f0  movzx   edx, [rbp+var_28]; usAddend
0x18000b8f4  lea     r8, [rbp+var_24]; pusResult
0x18000b8f8  movzx   ecx, r15w; usAugend
0x18000b8fc  call    UShortAdd
0x18000b901  test    eax, eax
0x18000b903  js      loc_18000BC9E
0x18000b909  movzx   r15d, [rbp+var_24]
0x18000b90e  mov     r9d, 2
0x18000b914  mov     r10d, [rbp+var_14]
0x18000b918  jmp     short loc_18000B939
0x18000b91a  test    rdi, rdi
0x18000b91d  jz      short loc_18000B925
0x18000b91f  xor     eax, eax
0x18000b921  mov     [rcx+rdi], ax
0x18000b925  mov     edx, r9d; usAddend
0x18000b928  lea     r8, [rbp+pusResult]; pusResult
0x18000b92c  call    UShortAdd
0x18000b931  test    eax, eax
0x18000b933  js      loc_18000BC9E
0x18000b939  movzx   ecx, [rbp+pusResult]; usAugend
0x18000b93d  test    rdi, rdi
0x18000b940  jz      short loc_18000B94E
0x18000b942  mov     rax, [r12+8]
0x18000b947  mov     eax, [rsi+rax+8]
0x18000b94b  mov     [rcx+rdi], eax
0x18000b94e  mov     edx, 4; usAddend
0x18000b953  lea     r8, [rbp+pusResult]; pusResult
0x18000b957  call    UShortAdd
0x18000b95c  test    eax, eax
0x18000b95e  js      loc_18000BC9E
0x18000b964  mov     r8, [r12+8]
0x18000b969  mov     ecx, [rsi+r8+8]
0x18000b96e  test    ecx, ecx
0x18000b970  jz      loc_18000BBB1
0x18000b976  sub     ecx, 1
0x18000b979  jz      loc_18000BB98
0x18000b97f  sub     ecx, 1
0x18000b982  jz      loc_18000BB0A
0x18000b988  sub     ecx, 1
0x18000b98b  jz      loc_18000BA53
0x18000b991  cmp     ecx, 1
0x18000b994  jnz     loc_18000BC88
0x18000b99a  movzx   ecx, [rbp+pusResult]; usAugend
0x18000b99e  test    rdi, rdi
0x18000b9a1  jz      short loc_18000B9AD
0x18000b9a3  movzx   eax, word ptr [rsi+r8+10h]
0x18000b9a9  mov     [rcx+rdi], ax
0x18000b9ad  mov     edx, r9d; usAddend
0x18000b9b0  lea     r8, [rbp+pusResult]; pusResult
0x18000b9b4  call    UShortAdd
0x18000b9b9  test    eax, eax
0x18000b9bb  js      loc_18000BC9E
0x18000b9c1  mov     rax, [r12+8]
0x18000b9c6  movzx   ecx, [rbp+pusResult]; usAugend
0x18000b9ca  cmp     qword ptr [rsi+rax+18h], 0
0x18000b9d0  jz      short loc_18000BA40
0x18000b9d2  test    rdi, rdi
0x18000b9d5  jz      short loc_18000B9DC
0x18000b9d7  mov     [rcx+rdi], r10w
0x18000b9dc  mov     edx, r9d; usAddend
0x18000b9df  lea     r8, [rbp+pusResult]; pusResult
0x18000b9e3  call    UShortAdd
0x18000b9e8  test    eax, eax
0x18000b9ea  js      loc_18000BC9E
0x18000b9f0  mov     rdx, [r12+8]
0x18000b9f5  movzx   r14d, word ptr [rsi+rdx+10h]
0x18000b9fb  mov     [rbp+var_28], r14w
0x18000ba00  test    rdi, rdi
0x18000ba03  jz      short loc_18000BA19
0x18000ba05  mov     rdx, [rsi+rdx+18h]; Src
0x18000ba0a  mov     r8d, r14d; Size
0x18000ba0d  movzx   ecx, r10w
0x18000ba11  add     rcx, rdi; void *
0x18000ba14  call    memcpy_0
0x18000ba19  movzx   ecx, word ptr [rbp+var_14]; usAugend
0x18000ba1d  lea     r8, [rbp+var_1C]; pusResult
0x18000ba21  movzx   edx, r14w; usAddend
0x18000ba25  call    UShortAdd
0x18000ba2a  test    eax, eax
0x18000ba2c  js      loc_18000BC9E
0x18000ba32  movzx   r10d, [rbp+var_1C]
0x18000ba37  mov     [rbp+var_14], r10d
0x18000ba3b  jmp     loc_18000BBD8
0x18000ba40  test    rdi, rdi
0x18000ba43  jz      short loc_18000BA4B
0x18000ba45  xor     eax, eax
0x18000ba47  mov     [rcx+rdi], ax
0x18000ba4b  mov     edx, r9d
0x18000ba4e  jmp     loc_18000BBC7
0x18000ba53  movzx   ecx, [rbp+pusResult]; usAugend
0x18000ba57  test    rdi, rdi
0x18000ba5a  jz      short loc_18000BA66
0x18000ba5c  movzx   eax, word ptr [rsi+r8+10h]
0x18000ba62  mov     [rcx+rdi], ax
0x18000ba66  mov     edx, r9d; usAddend
0x18000ba69  lea     r8, [rbp+pusResult]; pusResult
0x18000ba6d  call    UShortAdd
0x18000ba72  test    eax, eax
0x18000ba74  js      loc_18000BC9E
0x18000ba7a  mov     rax, [r12+8]
0x18000ba7f  movzx   ecx, [rbp+pusResult]; usAugend
0x18000ba83  cmp     qword ptr [rsi+rax+18h], 0
0x18000ba89  jz      short loc_18000BA40
0x18000ba8b  test    rdi, rdi
0x18000ba8e  jz      short loc_18000BA95
0x18000ba90  mov     [rcx+rdi], r15w
0x18000ba95  mov     edx, r9d; usAddend
0x18000ba98  lea     r8, [rbp+pusResult]; pusResult
0x18000ba9c  call    UShortAdd
0x18000baa1  test    eax, eax
0x18000baa3  js      loc_18000BC9E
0x18000baa9  mov     rdx, [r12+8]
0x18000baae  movzx   r14d, word ptr [rsi+rdx+10h]
0x18000bab4  add     r14d, r14d
0x18000bab7  cmp     r14d, 0FFFFh
0x18000babe  ja      loc_18000BC9E
0x18000bac4  mov     [rbp+var_28], r14w
0x18000bac9  test    rdi, rdi
0x18000bacc  jz      short loc_18000BAE3
0x18000bace  mov     rdx, [rsi+rdx+18h]; Src
0x18000bad3  movzx   ecx, r15w
0x18000bad7  add     rcx, rdi; void *
0x18000bada  movzx   r8d, r14w; Size
0x18000bade  call    memcpy_0
0x18000bae3  movzx   edx, r14w; usAddend
0x18000bae7  lea     r8, [rbp+var_24]; pusResult
0x18000baeb  movzx   ecx, r15w; usAugend
0x18000baef  call    UShortAdd
0x18000baf4  test    eax, eax
0x18000baf6  js      loc_18000BC9E
0x18000bafc  movzx   r15d, [rbp+var_24]
0x18000bb01  mov     r10d, [rbp+var_14]
0x18000bb05  jmp     loc_18000BBD8
0x18000bb0a  cmp     qword ptr [rsi+r8+10h], 0
0x18000bb10  movzx   ecx, [rbp+pusResult]; usAugend
0x18000bb14  jz      loc_18000BA40
0x18000bb1a  test    rdi, rdi
0x18000bb1d  jz      short loc_18000BB24
0x18000bb1f  mov     [rcx+rdi], r15w
0x18000bb24  mov     edx, r9d; usAddend
0x18000bb27  lea     r8, [rbp+pusResult]; pusResult
0x18000bb2b  call    UShortAdd
0x18000bb30  test    eax, eax
0x18000bb32  js      loc_18000BC9E
0x18000bb38  mov     rax, [r12+8]
0x18000bb3d  mov     rcx, [rsi+rax+10h]; Source
0x18000bb42  test    rcx, rcx
0x18000bb45  jnz     short loc_18000BB4B
0x18000bb47  xor     eax, eax
0x18000bb49  jmp     short loc_18000BB56
0x18000bb4b  mov     edx, 800h; MaxCount
0x18000bb50  call    cs:__imp_wcsnlen
0x18000bb56  lea     rcx, ds:2[rax*2]; uOperand
0x18000bb5e  lea     rdx, [rbp+var_28]; pusResult
0x18000bb62  call    UIntPtrToUShort
0x18000bb67  test    eax, eax
0x18000bb69  js      loc_18000BC9E
0x18000bb6f  test    rdi, rdi
0x18000bb72  jz      short loc_18000BB8F
0x18000bb74  mov     rdx, [r12+8]
0x18000bb79  movzx   r8d, [rbp+var_28]; Size
0x18000bb7e  movzx   ecx, r15w
0x18000bb82  add     rcx, rdi; void *
0x18000bb85  mov     rdx, [rsi+rdx+10h]; Src
0x18000bb8a  call    memcpy_0
0x18000bb8f  movzx   edx, [rbp+var_28]
0x18000bb93  jmp     loc_18000BAE7
0x18000bb98  movzx   ecx, [rbp+pusResult]
0x18000bb9c  test    rdi, rdi
0x18000bb9f  jz      short loc_18000BBAA
0x18000bba1  mov     rax, [rsi+r8+10h]
0x18000bba6  mov     [rcx+rdi], rax
0x18000bbaa  mov     edx, 8
0x18000bbaf  jmp     short loc_18000BBC7
0x18000bbb1  movzx   ecx, [rbp+pusResult]; usAugend
0x18000bbb5  test    rdi, rdi
0x18000bbb8  jz      short loc_18000BBC2
0x18000bbba  mov     eax, [rsi+r8+10h]
0x18000bbbf  mov     [rcx+rdi], eax
0x18000bbc2  mov     edx, 4; usAddend
0x18000bbc7  lea     r8, [rbp+pusResult]; pusResult
0x18000bbcb  call    UShortAdd
0x18000bbd0  test    eax, eax
0x18000bbd2  js      loc_18000BC9E
0x18000bbd8  mov     eax, [rbp+var_18]
0x18000bbdb  mov     r9d, 2
0x18000bbe1  inc     ax
0x18000bbe4  jmp     loc_18000B854
0x18000bbe9  test    rdi, rdi
0x18000bbec  jnz     loc_18000BC77
0x18000bbf2  movzx   r9d, [rbp+pusResult]
0x18000bbf7  lea     r8, [rbp+var_20]; pusResult
0x18000bbfb  movzx   edx, r9w; usAddend
0x18000bbff  movzx   ecx, r13w; usAugend
0x18000bc03  call    UShortAdd
0x18000bc08  test    eax, eax
0x18000bc0a  js      loc_18000BC9E
0x18000bc10  movzx   ecx, [rbp+var_20]; usAugend
0x18000bc14  lea     r8, [rbp+var_20]; pusResult
0x18000bc18  movzx   edx, r15w; usAddend
0x18000bc1c  call    UShortAdd
0x18000bc21  test    eax, eax
0x18000bc23  js      short loc_18000BC9E
0x18000bc25  movzx   ecx, [rbp+var_20]; usAugend
0x18000bc29  lea     r8, [rbp+var_20]; pusResult
0x18000bc2d  movzx   edx, r10w; usAddend
0x18000bc31  call    UShortAdd
  ... truncated ...
```
