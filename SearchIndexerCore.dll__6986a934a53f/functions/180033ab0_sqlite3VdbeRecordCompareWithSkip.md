# sqlite3VdbeRecordCompareWithSkip

- ea: `0x180033ab0`
- end: `0x180033f7a`
- name: `sqlite3VdbeRecordCompareWithSkip`
- size: `1226`
- prototype: ``
- caller_count: `9`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180025a20`
- `0x1800286a4`
- `0x180033760`
- `0x1800338c0`
- `0x180033aa0`
- `0x180072f58`
- `0x180073fb0`
- `0x1800a2950`
- `0x1800a2ad0`

## callees

- `0x1800201c0`
- `0x1800205e0`
- `0x180024ba0`
- `0x18002619c`
- `0x180031f24`
- `0x180033610`
- `0x180033ab0`
- `0x1800348b0`
- `0x18005ec74`
- `0x18008ef40`
- `0x180092b48`
- `0x1800af614`

## pseudocode

```c
__int64 __fastcall sqlite3VdbeRecordCompareWithSkip(unsigned int a1, unsigned __int8 *a2, __int64 *a3, int a4)
{
  __int64 v4; // r12
  unsigned __int8 *v6; // r10
  unsigned int v7; // r11d
  __int64 v8; // rcx
  int v9; // eax
  int v10; // r8d
  int v11; // edx
  unsigned int v12; // esi
  unsigned int v13; // edx
  __int16 v14; // r13
  unsigned __int8 *v15; // rcx
  unsigned int v16; // ebx
  __int64 v17; // rax
  unsigned int v18; // edx
  int v19; // r13d
  int v20; // eax
  unsigned int v21; // r11d
  int v22; // eax
  int v23; // edx
  char v24; // r8
  __int64 result; // rax
  unsigned int v26; // edx
  signed int v27; // r15d
  __int64 v28; // r8
  signed int v29; // eax
  int v30; // eax
  signed int v31; // eax
  unsigned __int8 Varint32; // al
  unsigned __int8 v33; // al
  __int64 v34; // rdx
  unsigned __int8 *v35; // rcx
  int v36; // eax
  int v37; // edx
  int v38; // eax
  unsigned int v39; // [rsp+20h] [rbp-48h] BYREF
  unsigned int v40; // [rsp+24h] [rbp-44h]
  __int128 v41; // [rsp+28h] [rbp-40h] BYREF
  __int128 v42; // [rsp+38h] [rbp-30h]
  __int128 v43; // [rsp+48h] [rbp-20h]
  __int64 v44; // [rsp+58h] [rbp-10h]
  int v47; // [rsp+C0h] [rbp+58h]
  int v48; // [rsp+C8h] [rbp+60h] BYREF

  v4 = a3[1];
  v44 = 0;
  v6 = a2;
  v7 = a1;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  if ( a4 )
  {
    v8 = a2[1];
    v48 = v8;
    if ( (unsigned int)v8 >= 0x80 )
    {
      Varint32 = sqlite3GetVarint32(a2 + 1, &v48);
      v8 = (unsigned int)v48;
      v6 = a2;
      v47 = Varint32 + 1;
    }
    else
    {
      v47 = 2;
    }
    v40 = *v6;
    v9 = sqlite3VdbeSerialTypeLen(v8);
    v10 = 1;
    v4 += 56;
    v12 = v11 + v9;
  }
  else
  {
    v26 = *a2;
    v40 = v26;
    v48 = v26;
    if ( v26 >= 0x80 )
    {
      v33 = sqlite3GetVarint32(v6, &v48);
      v26 = v48;
      v6 = a2;
      v7 = a1;
      v47 = v33;
      v40 = v48;
    }
    else
    {
      v47 = 1;
    }
    v12 = v26;
    v10 = 0;
  }
  v48 = v10;
  if ( v12 > v7 )
  {
    v34 = 89860;
LABEL_63:
    *((_BYTE *)a3 + 31) = sqlite3ReportError(11, v34, "database corruption");
    return 0;
  }
  v13 = v47;
  while ( 1 )
  {
    v14 = *(_WORD *)(v4 + 20);
    v15 = &v6[v13];
    if ( (v14 & 0x24) != 0 )
    {
      v16 = *v15;
      if ( (unsigned __int8)v16 < 0xAu )
      {
        if ( !(_BYTE)v16 )
          goto LABEL_21;
        if ( (_BYTE)v16 == 7 )
        {
          serialGet7(&v6[v12], &v41);
          v18 = -(int)sqlite3IntFloatCompare(*(_QWORD *)v4);
          goto LABEL_14;
        }
        v17 = vdbeRecordDecodeInt(*v15, &v6[v12]);
        if ( v17 < *(_QWORD *)v4 )
          goto LABEL_21;
        if ( v17 > *(_QWORD *)v4 )
        {
          v18 = 1;
LABEL_14:
          v19 = v48;
          goto LABEL_15;
        }
LABEL_16:
        v10 = v48;
        goto LABEL_17;
      }
      goto LABEL_64;
    }
    if ( (v14 & 8) != 0 )
    {
      v16 = *v15;
      if ( (unsigned __int8)v16 < 0xAu )
      {
        if ( !(_BYTE)v16 )
          goto LABEL_21;
        v35 = &v6[v12];
        if ( (_BYTE)v16 != 7 )
        {
          sqlite3VdbeSerialGet(v35, v16, &v41);
          v18 = sqlite3IntFloatCompare(v41);
          goto LABEL_14;
        }
        if ( (unsigned int)serialGet7(v35, &v41) || *(double *)v4 > *(double *)&v41 )
          goto LABEL_21;
        if ( *(double *)&v41 > *(double *)v4 )
          goto LABEL_44;
        goto LABEL_16;
      }
LABEL_64:
      v18 = -1;
      if ( (_BYTE)v16 != 10 )
        v18 = 1;
      goto LABEL_14;
    }
    v16 = *v15;
    v39 = v16;
    if ( (v14 & 2) != 0 )
    {
      if ( v16 >= 0x80 )
      {
        sqlite3GetVarint32(v15, &v39);
        v6 = a2;
        v7 = a1;
        v16 = v39;
      }
      if ( v16 < 0xC )
      {
LABEL_21:
        v18 = -1;
LABEL_22:
        v19 = v48;
        goto LABEL_23;
      }
      if ( (v16 & 1) == 0 )
        goto LABEL_44;
      v27 = (v16 - 12) >> 1;
      LODWORD(v42) = v27;
      if ( v27 + v12 > v7 || (v28 = *a3, v19 = v48, *(unsigned __int16 *)(*a3 + 8) <= v48) )
      {
        v34 = 89941;
        goto LABEL_63;
      }
      if ( !*(_QWORD *)(v28 + 8LL * v48 + 32) )
      {
        v31 = *(_DWORD *)(v4 + 16);
        if ( v27 < v31 )
          v31 = (v16 - 12) >> 1;
        v30 = memcmp_0(&v6[v12], *(const void **)(v4 + 8), v31);
        goto LABEL_54;
      }
      BYTE6(v42) = *(_BYTE *)(v28 + 4);
      *((_QWORD *)&v42 + 1) = *(_QWORD *)(v28 + 16);
      WORD2(v42) = 2;
      *((_QWORD *)&v41 + 1) = &v6[v12];
      v18 = vdbeCompareMemString(&v41, v4, *(_QWORD *)(v28 + 8LL * v48 + 32), (char *)a3 + 31);
LABEL_15:
      if ( v18 )
        goto LABEL_23;
      goto LABEL_16;
    }
    if ( (v14 & 0x10) != 0 )
      break;
    if ( (_BYTE)v16 && (_BYTE)v16 != 10 )
    {
      if ( (_BYTE)v16 != 7 || !(unsigned int)serialGet7(&v6[v12], &v41) )
      {
LABEL_44:
        v18 = 1;
        goto LABEL_22;
      }
      goto LABEL_16;
    }
LABEL_17:
    v20 = *((unsigned __int16 *)a3 + 14);
    v48 = v10 + 1;
    if ( v10 + 1 == v20 || (v12 += sqlite3VdbeSerialTypeLen(v16), v12 > v21) )
    {
      result = (unsigned int)*((char *)a3 + 30);
      *((_BYTE *)a3 + 34) = 1;
      return result;
    }
    v22 = sqlite3VarintLen_0(v16);
    v13 = v22 + v23;
    if ( v13 >= v40 )
    {
      v34 = 90022;
      goto LABEL_63;
    }
    v4 += 56;
  }
  if ( v16 >= 0x80 )
  {
    sqlite3GetVarint32(v15, &v39);
    v6 = a2;
    v7 = a1;
    v16 = v39;
  }
  if ( v16 < 0xC || (v16 & 1) != 0 )
  {
    v18 = -1;
    goto LABEL_14;
  }
  v27 = (v16 - 12) >> 1;
  if ( v27 + v12 > v7 )
  {
    v34 = 89971;
    goto LABEL_63;
  }
  if ( (v14 & 0x400) == 0 )
  {
    v29 = *(_DWORD *)(v4 + 16);
    if ( v27 < v29 )
      v29 = (v16 - 12) >> 1;
    v30 = memcmp_0(&v6[v12], *(const void **)(v4 + 8), v29);
    v19 = v48;
LABEL_54:
    v18 = v30;
    if ( v30 )
      goto LABEL_23;
    v18 = v27 - *(_DWORD *)(v4 + 16);
    goto LABEL_15;
  }
  v36 = isAllZero(&v6[v12], (unsigned int)v27);
  v19 = v48;
  if ( v36 )
  {
    v18 = v37 - *(_DWORD *)v4;
    goto LABEL_15;
  }
  v18 = 1;
LABEL_23:
  v24 = *(_BYTE *)(*(_QWORD *)(*a3 + 24) + v19);
  if ( v24 )
  {
    if ( (v24 & 2) == 0 )
      return -v18;
    v38 = !v16 || (*(_BYTE *)(v4 + 20) & 1) != 0;
    if ( (v24 & 1) != v38 )
      return -v18;
  }
  return v18;
}

```

## disassembly

```asm
0x180033ab0  mov     [rsp-40h+arg_8], rdx
0x180033ab5  mov     [rsp-40h+arg_0], ecx
0x180033ab9  push    rbp
0x180033aba  push    rbx
0x180033abb  push    rsi
0x180033abc  push    rdi
0x180033abd  push    r12
0x180033abf  push    r13
0x180033ac1  push    r14
0x180033ac3  push    r15
0x180033ac5  mov     rbp, rsp
0x180033ac8  sub     rsp, 68h
0x180033acc  mov     r12, [r8+8]
0x180033ad0  xor     eax, eax
0x180033ad2  mov     [rbp+var_10], rax
0x180033ad6  xorps   xmm0, xmm0
0x180033ad9  mov     r14, r8
0x180033adc  mov     r10, rdx
0x180033adf  mov     r11d, ecx
0x180033ae2  lea     ebx, [rax+2]
0x180033ae5  lea     r15d, [rbx+7Eh]
0x180033ae9  lea     edi, [rax+1]
0x180033aec  movups  [rbp+var_40], xmm0
0x180033af0  movups  [rbp+var_30], xmm0
0x180033af4  movups  [rbp+var_20], xmm0
0x180033af8  test    r9d, r9d
0x180033afb  jz      loc_180033C28
0x180033b01  movzx   ecx, byte ptr [rdx+1]
0x180033b05  mov     [rbp+arg_18], ecx
0x180033b08  cmp     ecx, r15d
0x180033b0b  jnb     loc_180033DCA
0x180033b11  mov     [rbp+arg_10], ebx
0x180033b14  movzx   edx, byte ptr [r10]
0x180033b18  mov     [rbp+var_44], edx
0x180033b1b  call    sqlite3VdbeSerialTypeLen
0x180033b20  mov     r8d, edi
0x180033b23  add     r12, 38h ; '8'
0x180033b27  lea     esi, [rdx+rax]
0x180033b2a  mov     [rbp+arg_18], r8d
0x180033b2e  cmp     esi, r11d
0x180033b31  ja      loc_180033E14
0x180033b37  mov     edx, [rbp+arg_10]
0x180033b3a  movzx   r13d, word ptr [r12+14h]
0x180033b40  mov     ecx, edx
0x180033b42  add     rcx, r10
0x180033b45  test    r13b, 24h
0x180033b49  jz      loc_180033C47
0x180033b4f  movzx   ebx, byte ptr [rcx]
0x180033b52  cmp     bl, 0Ah
0x180033b55  jnb     loc_180033E3C
0x180033b5b  test    bl, bl
0x180033b5d  jz      loc_180033BF0
0x180033b63  mov     ecx, esi
0x180033b65  add     rcx, r10
0x180033b68  cmp     bl, 7
0x180033b6b  jz      loc_180033E4A
0x180033b71  mov     rdx, rcx
0x180033b74  mov     ecx, ebx
0x180033b76  call    vdbeRecordDecodeInt
0x180033b7b  cmp     rax, [r12]
0x180033b7f  jl      short loc_180033BF0
0x180033b81  jle     short loc_180033B9B
0x180033b83  mov     edx, edi
0x180033b85  mov     r13d, [rbp+arg_18]
0x180033b89  mov     r15d, 2
0x180033b8f  test    edx, edx
0x180033b91  jnz     short loc_180033BFD
0x180033b93  mov     r10, [rbp+arg_8]
0x180033b97  mov     r11d, [rbp+arg_0]
0x180033b9b  mov     r8d, [rbp+arg_18]
0x180033b9f  mov     edx, [rbp+arg_10]
0x180033ba2  movzx   eax, word ptr [r14+1Ch]
0x180033ba7  add     r8d, edi
0x180033baa  mov     [rbp+arg_18], r8d
0x180033bae  cmp     r8d, eax
0x180033bb1  jz      loc_180033CEF
0x180033bb7  mov     ecx, ebx
0x180033bb9  call    sqlite3VdbeSerialTypeLen
0x180033bbe  add     esi, eax
0x180033bc0  cmp     esi, r11d
0x180033bc3  ja      loc_180033CEF
0x180033bc9  mov     ecx, ebx
0x180033bcb  call    sqlite3VarintLen_0
0x180033bd0  add     edx, eax
0x180033bd2  mov     [rbp+arg_10], edx
0x180033bd5  cmp     edx, [rbp+var_44]
0x180033bd8  jnb     loc_180033E1B
0x180033bde  mov     ebx, 2
0x180033be3  add     r12, 38h ; '8'
0x180033be7  lea     r15d, [rbx+7Eh]
0x180033beb  jmp     loc_180033B3A
0x180033bf0  or      edx, 0FFFFFFFFh
0x180033bf3  mov     r13d, [rbp+arg_18]
0x180033bf7  mov     r15d, 2
0x180033bfd  mov     rax, [r14]
0x180033c00  movsxd  rcx, r13d
0x180033c03  mov     rax, [rax+18h]
0x180033c07  movzx   r8d, byte ptr [rax+rcx]
0x180033c0c  test    r8d, r8d
0x180033c0f  jnz     loc_180033F51
0x180033c15  mov     eax, edx
0x180033c17  add     rsp, 68h
0x180033c1b  pop     r15
0x180033c1d  pop     r14
0x180033c1f  pop     r13
0x180033c21  pop     r12
0x180033c23  pop     rdi
0x180033c24  pop     rsi
0x180033c25  pop     rbx
0x180033c26  pop     rbp
0x180033c27  retn
0x180033c28  movzx   edx, byte ptr [rdx]
0x180033c2b  mov     [rbp+var_44], edx
0x180033c2e  mov     [rbp+arg_18], edx
0x180033c31  cmp     edx, r15d
0x180033c34  jnb     loc_180033DEF
0x180033c3a  mov     [rbp+arg_10], edi
0x180033c3d  mov     esi, edx
0x180033c3f  xor     r8d, r8d
0x180033c42  jmp     loc_180033B2A
0x180033c47  test    r13b, 8
0x180033c4b  jnz     loc_180033E6A
0x180033c51  test    bl, r13b
0x180033c54  movzx   ebx, byte ptr [rcx]
0x180033c57  mov     [rbp+var_48], ebx
0x180033c5a  jz      loc_180033CFD
0x180033c60  cmp     ebx, r15d
0x180033c63  jnb     loc_180033EDA
0x180033c69  cmp     ebx, 0Ch
0x180033c6c  jb      short loc_180033BF0
0x180033c6e  test    dil, bl
0x180033c71  jz      loc_180033D2F
0x180033c77  lea     r15d, [rbx-0Ch]
0x180033c7b  shr     r15d, 1
0x180033c7e  mov     dword ptr [rbp+var_30], r15d
0x180033c82  lea     eax, [r15+rsi]
0x180033c86  cmp     eax, r11d
0x180033c89  ja      loc_180033F36
0x180033c8f  mov     r8, [r14]
0x180033c92  movsxd  r13, [rbp+arg_18]
0x180033c96  movzx   eax, word ptr [r8+8]
0x180033c9b  cmp     eax, r13d
0x180033c9e  jle     loc_180033F36
0x180033ca4  cmp     qword ptr [r8+r13*8+20h], 0
0x180033caa  jz      loc_180033DAA
0x180033cb0  mov     al, [r8+4]
0x180033cb4  lea     r9, [r14+1Fh]
0x180033cb8  mov     byte ptr [rbp+var_30+6], al
0x180033cbb  lea     rcx, [rbp+var_40]
0x180033cbf  mov     rax, [r8+10h]
0x180033cc3  mov     r15d, 2
0x180033cc9  mov     qword ptr [rbp+var_30+8], rax
0x180033ccd  mov     rdx, r12
0x180033cd0  mov     word ptr [rbp+var_30+4], r15w
0x180033cd5  mov     eax, esi
0x180033cd7  add     rax, r10
0x180033cda  mov     qword ptr [rbp+var_40+8], rax
0x180033cde  mov     r8, [r8+r13*8+20h]
0x180033ce3  call    vdbeCompareMemString
0x180033ce8  mov     edx, eax
0x180033cea  jmp     loc_180033B8F
0x180033cef  movsx   eax, byte ptr [r14+1Eh]
0x180033cf4  mov     [r14+22h], dil
0x180033cf8  jmp     loc_180033C17
0x180033cfd  test    r13b, 10h
0x180033d01  jnz     short loc_180033D36
0x180033d03  test    bl, bl
0x180033d05  jz      loc_180033BA2
0x180033d0b  cmp     bl, 0Ah
0x180033d0e  jz      loc_180033BA2
0x180033d14  cmp     bl, 7
0x180033d17  jnz     short loc_180033D2F
0x180033d19  mov     ecx, esi
0x180033d1b  lea     rdx, [rbp+var_40]
0x180033d1f  add     rcx, r10
0x180033d22  call    serialGet7
0x180033d27  test    eax, eax
0x180033d29  jnz     loc_180033B9B
0x180033d2f  mov     edx, edi
0x180033d31  jmp     loc_180033BF3
0x180033d36  cmp     ebx, r15d
0x180033d39  jnb     loc_180033EF3
0x180033d3f  cmp     ebx, 0Ch
0x180033d42  jb      loc_180033F2E
0x180033d48  test    dil, bl
0x180033d4b  jnz     loc_180033F2E
0x180033d51  lea     r15d, [rbx-0Ch]
0x180033d55  shr     r15d, 1
0x180033d58  lea     eax, [r15+rsi]
0x180033d5c  cmp     eax, r11d
0x180033d5f  ja      loc_180033F47
0x180033d65  bt      r13w, 0Ah
0x180033d6b  mov     ecx, esi
0x180033d6d  jb      loc_180033F0C
0x180033d73  mov     eax, [r12+10h]
0x180033d78  cmp     r15d, eax
0x180033d7b  mov     rdx, [r12+8]; Buf2
0x180033d80  cmovl   eax, r15d
0x180033d84  add     rcx, r10; Buf1
0x180033d87  movsxd  r8, eax; Size
0x180033d8a  call    memcmp_0
0x180033d8f  mov     r13d, [rbp+arg_18]
0x180033d93  mov     edx, eax
0x180033d95  test    eax, eax
0x180033d97  jnz     loc_180033BF7
0x180033d9d  mov     edx, r15d
0x180033da0  sub     edx, [r12+10h]
0x180033da5  jmp     loc_180033B89
0x180033daa  mov     eax, [r12+10h]
0x180033daf  cmp     r15d, eax
0x180033db2  mov     rdx, [r12+8]; Buf2
0x180033db7  cmovl   eax, r15d
0x180033dbb  mov     ecx, esi
0x180033dbd  movsxd  r8, eax; Size
0x180033dc0  add     rcx, r10; Buf1
0x180033dc3  call    memcmp_0
0x180033dc8  jmp     short loc_180033D93
0x180033dca  lea     rdx, [rbp+arg_18]
0x180033dce  lea     rcx, [r10+1]
0x180033dd2  call    sqlite3GetVarint32
0x180033dd7  mov     ecx, [rbp+arg_18]
0x180033dda  mov     r10, [rbp+arg_8]
0x180033dde  mov     r11d, [rbp+arg_0]
0x180033de2  movzx   edx, al
0x180033de5  add     edx, edi
0x180033de7  mov     [rbp+arg_10], edx
0x180033dea  jmp     loc_180033B14
0x180033def  lea     rdx, [rbp+arg_18]
0x180033df3  mov     rcx, r10
0x180033df6  call    sqlite3GetVarint32
0x180033dfb  mov     edx, [rbp+arg_18]
0x180033dfe  mov     r10, [rbp+arg_8]
0x180033e02  mov     r11d, [rbp+arg_0]
0x180033e06  movzx   eax, al
0x180033e09  mov     [rbp+arg_10], eax
0x180033e0c  mov     [rbp+var_44], edx
0x180033e0f  jmp     loc_180033C3D
0x180033e14  mov     edx, 15F04h
0x180033e19  jmp     short loc_180033E20
0x180033e1b  mov     edx, 15FA6h
0x180033e20  lea     r8, aDatabaseCorrup; "database corruption"
0x180033e27  mov     ecx, 0Bh
0x180033e2c  call    sqlite3ReportError
0x180033e31  mov     [r14+1Fh], al
0x180033e35  xor     eax, eax
0x180033e37  jmp     loc_180033C17
0x180033e3c  or      edx, 0FFFFFFFFh
0x180033e3f  cmp     bl, 0Ah
0x180033e42  cmovnz  edx, edi
0x180033e45  jmp     loc_180033B85
0x180033e4a  lea     rdx, [rbp+var_40]
0x180033e4e  call    serialGet7
0x180033e53  mov     rcx, [r12]
0x180033e57  movsd   xmm1, qword ptr [rbp+var_40]
0x180033e5c  call    sqlite3IntFloatCompare
0x180033e61  mov     edx, eax
0x180033e63  neg     edx
0x180033e65  jmp     loc_180033B85
0x180033e6a  movzx   ebx, byte ptr [rcx]
0x180033e6d  cmp     bl, 0Ah
0x180033e70  jnb     short loc_180033E3C
0x180033e72  test    bl, bl
0x180033e74  jz      loc_180033BF0
0x180033e7a  mov     ecx, esi
0x180033e7c  add     rcx, r10
0x180033e7f  cmp     bl, 7
0x180033e82  jnz     short loc_180033EB9
0x180033e84  lea     rdx, [rbp+var_40]
0x180033e88  call    serialGet7
0x180033e8d  test    eax, eax
0x180033e8f  jnz     loc_180033BF0
0x180033e95  movsd   xmm0, qword ptr [r12]
0x180033e9b  movsd   xmm1, qword ptr [rbp+var_40]
0x180033ea0  comisd  xmm0, xmm1
0x180033ea4  ja      loc_180033BF0
0x180033eaa  comisd  xmm1, xmm0
0x180033eae  ja      loc_180033D2F
0x180033eb4  jmp     loc_180033B9B
0x180033eb9  lea     r8, [rbp+var_40]
0x180033ebd  mov     edx, ebx
0x180033ebf  call    sqlite3VdbeSerialGet
0x180033ec4  mov     rcx, qword ptr [rbp+var_40]
0x180033ec8  movsd   xmm1, qword ptr [r12]
0x180033ece  call    sqlite3IntFloatCompare
0x180033ed3  mov     edx, eax
0x180033ed5  jmp     loc_180033B85
0x180033eda  lea     rdx, [rbp+var_48]
0x180033ede  call    sqlite3GetVarint32
0x180033ee3  mov     r10, [rbp+arg_8]
0x180033ee7  mov     r11d, [rbp+arg_0]
0x180033eeb  mov     ebx, [rbp+var_48]
0x180033eee  jmp     loc_180033C69
0x180033ef3  lea     rdx, [rbp+var_48]
0x180033ef7  call    sqlite3GetVarint32
0x180033efc  mov     r10, [rbp+arg_8]
0x180033f00  mov     r11d, [rbp+arg_0]
0x180033f04  mov     ebx, [rbp+var_48]
0x180033f07  jmp     loc_180033D3F
0x180033f0c  add     rcx, r10
0x180033f0f  mov     edx, r15d
  ... truncated ...
```
