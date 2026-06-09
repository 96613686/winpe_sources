# sqlite3VdbeRecordCompareWithSkip

- ea: `0x18002c520`
- end: `0x18002ca70`
- name: `sqlite3VdbeRecordCompareWithSkip`
- size: `1360`
- prototype: ``
- caller_count: `9`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180010de0`
- `0x180021aa0`
- `0x18008d848`
- `0x18008eba0`
- `0x18008ed84`
- `0x18009e0a0`
- `0x18009e280`
- `0x18009e640`
- `0x18009e7c0`

## callees

- `0x18002c520`
- `0x180033ba0`
- `0x180037320`
- `0x18003a860`
- `0x18003af40`
- `0x180042160`
- `0x180064134`
- `0x180076054`
- `0x180085290`
- `0x18009cf54`
- `0x18009e374`
- `0x1800a6cfc`

## pseudocode

```c
__int64 __fastcall sqlite3VdbeRecordCompareWithSkip(unsigned int a1, unsigned __int8 *a2, __int64 *a3, int a4)
{
  __int64 v4; // r14
  unsigned __int8 *v5; // r10
  __int64 *v6; // r13
  unsigned int v7; // edx
  __int64 v8; // rcx
  unsigned int v9; // esi
  unsigned __int8 Varint32; // al
  int v11; // eax
  __int64 v12; // r8
  int v13; // r11d
  int v14; // r12d
  unsigned int v15; // r15d
  unsigned __int8 v16; // al
  __int64 result; // rax
  __int64 *v18; // r9
  __int16 v19; // di
  unsigned __int8 *v20; // rcx
  unsigned int v21; // ebx
  unsigned int v22; // edx
  __int64 v23; // rax
  unsigned __int8 *v24; // rcx
  signed int v25; // edi
  __int64 v26; // r8
  signed int v27; // r13d
  signed int v28; // eax
  unsigned int v29; // r13d
  int v30; // eax
  int v31; // edx
  signed int v32; // edi
  signed int v33; // eax
  unsigned int v34; // eax
  int v35; // ecx
  unsigned __int64 i; // rax
  char v37; // r8
  unsigned int v38; // [rsp+30h] [rbp-29h] BYREF
  __int128 v39; // [rsp+38h] [rbp-21h] BYREF
  __int128 v40; // [rsp+48h] [rbp-11h]
  __int128 v41; // [rsp+58h] [rbp-1h]
  __int64 v42; // [rsp+68h] [rbp+Fh]
  unsigned int v46; // [rsp+D8h] [rbp+7Fh] BYREF

  v4 = a3[1];
  v5 = a2;
  v42 = 0;
  v6 = a3;
  v7 = a1;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  if ( a4 )
  {
    v8 = v5[1];
    v46 = v8;
    if ( (unsigned int)v8 >= 0x80 )
    {
      Varint32 = sqlite3GetVarint32(v5 + 1, &v46, a3);
      v8 = v46;
      v5 = a2;
      v9 = Varint32 + 1;
    }
    else
    {
      v9 = 2;
    }
    v46 = *v5;
    v11 = sqlite3VdbeSerialTypeLen(v8);
    v13 = 1;
    v4 += 56;
    v14 = 1;
    v15 = v12 + v11;
  }
  else
  {
    v12 = *v5;
    v13 = 1;
    v46 = v12;
    v38 = v12;
    if ( (unsigned int)v12 >= 0x80 )
    {
      v16 = sqlite3GetVarint32(v5, &v38, v12);
      v12 = v38;
      v13 = 1;
      v7 = a1;
      v5 = a2;
      v46 = v38;
      v9 = v16;
    }
    else
    {
      v9 = 1;
    }
    v15 = v12;
    v14 = 0;
  }
  if ( v15 > v7 )
  {
    *((_BYTE *)v6 + 31) = sqlite3ReportError(11, 89579, "database corruption");
    return 0;
  }
  v18 = qword_1800AE060;
  while ( 1 )
  {
    v19 = *(_WORD *)(v4 + 20);
    v20 = &v5[v9];
    v21 = *v20;
    if ( (v19 & 0x24) != 0 )
    {
      if ( (unsigned __int8)v21 >= 0xAu )
      {
        v22 = -1;
        if ( (_BYTE)v21 != 10 )
          v22 = v13;
        goto LABEL_66;
      }
      if ( !(_BYTE)v21 )
        goto LABEL_83;
      if ( (_BYTE)v21 == 7 )
      {
        serialGet7(&v5[v15], &v39, v12, v18);
        v22 = -(int)sqlite3IntFloatCompare(*(_QWORD *)v4);
        goto LABEL_64;
      }
      v23 = vdbeRecordDecodeInt(*v20, &v5[v15], v12, v18);
      if ( v23 < *(_QWORD *)v4 )
        goto LABEL_83;
      if ( v23 > *(_QWORD *)v4 )
      {
LABEL_23:
        v22 = v13;
        goto LABEL_88;
      }
      goto LABEL_72;
    }
    if ( (v19 & 8) == 0 )
      break;
    if ( (unsigned __int8)v21 >= 0xAu )
    {
      v22 = -1;
      if ( (_BYTE)v21 != 10 )
        v22 = v13;
      goto LABEL_66;
    }
    if ( !(_BYTE)v21 )
      goto LABEL_83;
    v24 = &v5[v15];
    if ( (_BYTE)v21 != 7 )
    {
      sqlite3VdbeSerialGet(v24, v21, &v39);
      v22 = sqlite3IntFloatCompare(v39);
      goto LABEL_63;
    }
    if ( (unsigned int)serialGet7(v24, &v39, v12, v18) || *(double *)v4 > *(double *)&v39 )
      goto LABEL_83;
    if ( *(double *)&v39 > *(double *)v4 )
      goto LABEL_23;
LABEL_72:
    v12 = v46;
    v18 = qword_1800AE060;
LABEL_73:
    v7 = a1;
LABEL_74:
    if ( ++v14 == *((unsigned __int16 *)v6 + 14)
      || (v21 < 0x80 ? (v34 = *((unsigned __int8 *)v18 + v21)) : (v34 = (v21 - 12) >> 1), v15 += v34, v15 > v7) )
    {
      result = (unsigned int)*((char *)v6 + 30);
      *((_BYTE *)v6 + 34) = 1;
      return result;
    }
    v35 = v13;
    for ( i = (unsigned __int64)v21 >> 7; i; i >>= 7 )
      ++v35;
    v9 += v35;
    if ( v9 >= (unsigned int)v12 )
    {
      sqlite3_log(
        11,
        "%s at line %d of [%.10s]",
        "database corruption",
        89741,
        "96c92aba00c8375bc32fafcdf12429c58bd8aabfcadab6683e35bbb9cdebf19e");
      result = 0;
      *((_BYTE *)v6 + 31) = 11;
      return result;
    }
    v4 += 56;
  }
  v38 = *v20;
  if ( (v19 & 2) != 0 )
  {
    if ( v21 >= 0x80 )
    {
      sqlite3GetVarint32(v20, &v38, v12);
      v7 = a1;
      v13 = 1;
      v5 = a2;
      v21 = v38;
    }
    if ( v21 < 0xC )
      goto LABEL_83;
    if ( (v21 & 1) == 0 )
      goto LABEL_23;
    v25 = (v21 - 12) >> 1;
    LODWORD(v40) = v25;
    if ( v25 + v15 > v7 || (v26 = *v6, *(unsigned __int16 *)(*v6 + 8) <= v14) )
    {
      *((_BYTE *)v6 + 31) = sqlite3ReportError(11, 89660, "database corruption");
      return 0;
    }
    if ( *(_QWORD *)(v26 + 8LL * v14 + 32) )
    {
      BYTE6(v40) = *(_BYTE *)(v26 + 4);
      *((_QWORD *)&v40 + 1) = *(_QWORD *)(v26 + 16);
      WORD2(v40) = 2;
      *((_QWORD *)&v39 + 1) = &v5[v15];
      v22 = vdbeCompareMemString(&v39, v4, *(_QWORD *)(v26 + 8LL * v14 + 32), (char *)v6 + 31);
      goto LABEL_62;
    }
    v27 = *(_DWORD *)(v4 + 16);
    v28 = v27;
    if ( v25 < v27 )
      v28 = (v21 - 12) >> 1;
    v22 = memcmp_0(&v5[v15], *(const void **)(v4 + 8), v28);
    v13 = 1;
    if ( v22 )
      goto LABEL_87;
    v22 = v25 - v27;
    v6 = a3;
LABEL_63:
    v5 = a2;
LABEL_64:
    v18 = qword_1800AE060;
LABEL_65:
    v12 = v46;
LABEL_66:
    if ( v22 )
      goto LABEL_88;
    goto LABEL_73;
  }
  if ( (v19 & 0x10) == 0 )
  {
    if ( !(_BYTE)v21 || (_BYTE)v21 == 10 )
      goto LABEL_74;
    if ( (_BYTE)v21 != 7 || !(unsigned int)serialGet7(&v5[v15], &v39, v12, v18) )
      goto LABEL_23;
    goto LABEL_72;
  }
  if ( v21 >= 0x80 )
  {
    sqlite3GetVarint32(v20, &v38, v12);
    v7 = a1;
    v18 = qword_1800AE060;
    v5 = a2;
    v13 = 1;
    v21 = v38;
  }
  if ( v21 < 0xC || (v21 & 1) != 0 )
  {
LABEL_83:
    v22 = -1;
    goto LABEL_88;
  }
  v29 = (v21 - 12) >> 1;
  if ( v15 + v29 > v7 )
  {
    *((_BYTE *)a3 + 31) = sqlite3ReportError(11, 89690, "database corruption");
    return 0;
  }
  if ( (v19 & 0x400) != 0 )
  {
    v30 = isAllZero(&v5[v15], v29, v12, v18);
    v6 = a3;
    if ( !v30 )
      goto LABEL_23;
    v22 = v31 - *(_DWORD *)v4;
    goto LABEL_65;
  }
  v32 = *(_DWORD *)(v4 + 16);
  v33 = v32;
  if ( (int)v29 < v32 )
    v33 = (v21 - 12) >> 1;
  v22 = memcmp_0(&v5[v15], *(const void **)(v4 + 8), v33);
  if ( !v22 )
  {
    v6 = a3;
    v22 = ((v21 - 12) >> 1) - v32;
LABEL_62:
    v13 = 1;
    goto LABEL_63;
  }
  v13 = 1;
LABEL_87:
  v6 = a3;
LABEL_88:
  v37 = *(_BYTE *)(*(_QWORD *)(*v6 + 24) + v14);
  if ( v37 )
  {
    if ( (v37 & 2) == 0 )
      return -v22;
    if ( v21 && (*(_BYTE *)(v4 + 20) & 1) == 0 )
      v13 = 0;
    if ( (v37 & 1) != v13 )
      return -v22;
  }
  return v22;
}

```

## disassembly

```asm
0x18002c520  mov     [rsp-8+arg_10], r8
0x18002c525  mov     [rsp-8+arg_8], rdx
0x18002c52a  mov     [rsp-8+arg_0], ecx
0x18002c52e  push    rbp
0x18002c52f  push    rsi
0x18002c530  push    r12
0x18002c532  push    r13
0x18002c534  push    r14
0x18002c536  push    r15
0x18002c538  lea     rbp, [rsp-2Fh]
0x18002c53d  sub     rsp, 88h
0x18002c544  mov     r14, [r8+8]
0x18002c548  xorps   xmm0, xmm0
0x18002c54b  xor     eax, eax
0x18002c54d  mov     r10, rdx
0x18002c550  mov     [rbp+57h+var_48], rax
0x18002c554  mov     r13, r8
0x18002c557  mov     edx, ecx
0x18002c559  movups  [rbp+57h+var_78], xmm0
0x18002c55d  movups  [rbp+57h+var_68], xmm0
0x18002c561  movups  [rbp+57h+var_58], xmm0
0x18002c565  test    r9d, r9d
0x18002c568  jz      short loc_18002C5BD
0x18002c56a  movzx   ecx, byte ptr [r10+1]
0x18002c56f  mov     [rbp+57h+arg_18], ecx
0x18002c572  cmp     ecx, 80h
0x18002c578  jnb     short loc_18002C581
0x18002c57a  mov     esi, 2
0x18002c57f  jmp     short loc_18002C59D
0x18002c581  lea     rdx, [rbp+57h+arg_18]
0x18002c585  lea     rcx, [r10+1]
0x18002c589  call    sqlite3GetVarint32
0x18002c58e  mov     ecx, [rbp+57h+arg_18]
0x18002c591  mov     edx, [rbp+57h+arg_0]
0x18002c594  mov     r10, [rbp+57h+arg_8]
0x18002c598  movzx   esi, al
0x18002c59b  inc     esi
0x18002c59d  movzx   r8d, byte ptr [r10]
0x18002c5a1  mov     [rbp+57h+arg_18], r8d
0x18002c5a5  call    sqlite3VdbeSerialTypeLen
0x18002c5aa  mov     r11d, 1
0x18002c5b0  add     r14, 38h ; '8'
0x18002c5b4  mov     r12d, r11d
0x18002c5b7  lea     r15d, [r8+rax]
0x18002c5bb  jmp     short loc_18002C607
0x18002c5bd  movzx   r8d, byte ptr [r10]
0x18002c5c1  mov     r11d, 1
0x18002c5c7  mov     [rbp+57h+arg_18], r8d
0x18002c5cb  mov     [rbp+57h+var_80], r8d
0x18002c5cf  cmp     r8d, 80h
0x18002c5d6  jnb     short loc_18002C5DD
0x18002c5d8  mov     esi, r11d
0x18002c5db  jmp     short loc_18002C601
0x18002c5dd  lea     rdx, [rbp+57h+var_80]
0x18002c5e1  mov     rcx, r10
0x18002c5e4  call    sqlite3GetVarint32
0x18002c5e9  mov     r8d, [rbp+57h+var_80]
0x18002c5ed  mov     r11d, 1
0x18002c5f3  mov     edx, [rbp+57h+arg_0]
0x18002c5f6  mov     r10, [rbp+57h+arg_8]
0x18002c5fa  mov     [rbp+57h+arg_18], r8d
0x18002c5fe  movzx   esi, al
0x18002c601  mov     r15d, r8d
0x18002c604  xor     r12d, r12d
0x18002c607  cmp     r15d, edx
0x18002c60a  jbe     short loc_18002C62D
0x18002c60c  lea     r8, aDatabaseCorrup; "database corruption"
0x18002c613  mov     edx, 15DEBh
0x18002c618  mov     ecx, 0Bh
0x18002c61d  call    sqlite3ReportError
0x18002c622  mov     [r13+1Fh], al
0x18002c626  xor     eax, eax
0x18002c628  jmp     loc_18002CA5E
0x18002c62d  mov     [rsp+0B0h+var_38], rdi
0x18002c632  lea     r9, qword_1800AE060
0x18002c639  mov     [rsp+0B0h+var_30], rbx
0x18002c641  movzx   edi, word ptr [r14+14h]
0x18002c646  mov     ecx, esi
0x18002c648  add     rcx, r10
0x18002c64b  movzx   ebx, byte ptr [rcx]
0x18002c64e  test    dil, 24h
0x18002c652  jz      short loc_18002C6BA
0x18002c654  cmp     bl, 0Ah
0x18002c657  jb      short loc_18002C667
0x18002c659  mov     edx, 0FFFFFFFFh
0x18002c65e  cmovnz  edx, r11d
0x18002c662  jmp     loc_18002C8E5
0x18002c667  test    bl, bl
0x18002c669  jz      loc_18002C986
0x18002c66f  mov     ecx, r15d
0x18002c672  add     rcx, r10
0x18002c675  cmp     bl, 7
0x18002c678  jnz     short loc_18002C699
0x18002c67a  lea     rdx, [rbp+57h+var_78]
0x18002c67e  call    serialGet7
0x18002c683  mov     rcx, [r14]
0x18002c686  movsd   xmm1, qword ptr [rbp+57h+var_78]
0x18002c68b  call    sqlite3IntFloatCompare
0x18002c690  mov     edx, eax
0x18002c692  neg     edx
0x18002c694  jmp     loc_18002C8DA
0x18002c699  mov     rdx, rcx
0x18002c69c  mov     ecx, ebx
0x18002c69e  call    vdbeRecordDecodeInt
0x18002c6a3  cmp     rax, [r14]
0x18002c6a6  jl      loc_18002C986
0x18002c6ac  jle     loc_18002C918
0x18002c6b2  mov     edx, r11d
0x18002c6b5  jmp     loc_18002C9DC
0x18002c6ba  test    dil, 8
0x18002c6be  jz      short loc_18002C737
0x18002c6c0  cmp     bl, 0Ah
0x18002c6c3  jb      short loc_18002C6D3
0x18002c6c5  mov     edx, 0FFFFFFFFh
0x18002c6ca  cmovnz  edx, r11d
0x18002c6ce  jmp     loc_18002C8E5
0x18002c6d3  test    bl, bl
0x18002c6d5  jz      loc_18002C986
0x18002c6db  mov     ecx, r15d
0x18002c6de  add     rcx, r10
0x18002c6e1  cmp     bl, 7
0x18002c6e4  jnz     short loc_18002C717
0x18002c6e6  lea     rdx, [rbp+57h+var_78]
0x18002c6ea  call    serialGet7
0x18002c6ef  test    eax, eax
0x18002c6f1  jnz     loc_18002C986
0x18002c6f7  movsd   xmm0, qword ptr [r14]
0x18002c6fc  movsd   xmm1, qword ptr [rbp+57h+var_78]
0x18002c701  comisd  xmm0, xmm1
0x18002c705  ja      loc_18002C986
0x18002c70b  comisd  xmm1, xmm0
0x18002c70f  jbe     loc_18002C918
0x18002c715  jmp     short loc_18002C6B2
0x18002c717  lea     r8, [rbp+57h+var_78]
0x18002c71b  mov     edx, ebx
0x18002c71d  call    sqlite3VdbeSerialGet
0x18002c722  mov     rcx, qword ptr [rbp+57h+var_78]
0x18002c726  movsd   xmm1, qword ptr [r14]
0x18002c72b  call    sqlite3IntFloatCompare
0x18002c730  mov     edx, eax
0x18002c732  jmp     loc_18002C8D6
0x18002c737  mov     [rbp+57h+var_80], ebx
0x18002c73a  test    dil, 2
0x18002c73e  jz      loc_18002C824
0x18002c744  cmp     ebx, 80h
0x18002c74a  jb      short loc_18002C765
0x18002c74c  lea     rdx, [rbp+57h+var_80]
0x18002c750  call    sqlite3GetVarint32
0x18002c755  mov     edx, [rbp+57h+arg_0]
0x18002c758  mov     r11d, 1
0x18002c75e  mov     r10, [rbp+57h+arg_8]
0x18002c762  mov     ebx, [rbp+57h+var_80]
0x18002c765  cmp     ebx, 0Ch
0x18002c768  jb      loc_18002C986
0x18002c76e  test    bl, 1
0x18002c771  jz      loc_18002C6B2
0x18002c777  lea     edi, [rbx-0Ch]
0x18002c77a  shr     edi, 1
0x18002c77c  mov     dword ptr [rbp+57h+var_68], edi
0x18002c77f  lea     eax, [rdi+r15]
0x18002c783  cmp     eax, edx
0x18002c785  ja      loc_18002C98D
0x18002c78b  mov     r8, [r13+0]
0x18002c78f  movzx   eax, word ptr [r8+8]
0x18002c794  cmp     eax, r12d
0x18002c797  jle     loc_18002C98D
0x18002c79d  movsxd  rcx, r12d
0x18002c7a0  cmp     qword ptr [r8+rcx*8+20h], 0
0x18002c7a6  jz      short loc_18002C7E7
0x18002c7a8  movzx   eax, byte ptr [r8+4]
0x18002c7ad  lea     r9, [r13+1Fh]
0x18002c7b1  mov     byte ptr [rbp+57h+var_68+6], al
0x18002c7b4  mov     rdx, r14
0x18002c7b7  mov     rax, [r8+10h]
0x18002c7bb  mov     qword ptr [rbp+57h+var_68+8], rax
0x18002c7bf  mov     eax, 2
0x18002c7c4  mov     word ptr [rbp+57h+var_68+4], ax
0x18002c7c8  mov     eax, r15d
0x18002c7cb  add     rax, r10
0x18002c7ce  mov     qword ptr [rbp+57h+var_78+8], rax
0x18002c7d2  mov     r8, [r8+rcx*8+20h]
0x18002c7d7  lea     rcx, [rbp+57h+var_78]
0x18002c7db  call    vdbeCompareMemString
0x18002c7e0  mov     edx, eax
0x18002c7e2  jmp     loc_18002C8D0
0x18002c7e7  mov     r13d, [r14+10h]
0x18002c7eb  mov     eax, r13d
0x18002c7ee  mov     rdx, [r14+8]; Buf2
0x18002c7f2  cmp     edi, r13d
0x18002c7f5  mov     ecx, r15d
0x18002c7f8  cmovl   eax, edi
0x18002c7fb  add     rcx, r10; Buf1
0x18002c7fe  movsxd  r8, eax; Size
0x18002c801  call    memcmp_0
0x18002c806  mov     edx, eax
0x18002c808  mov     r11d, 1
0x18002c80e  test    eax, eax
0x18002c810  jnz     loc_18002C9D8
0x18002c816  mov     edx, edi
0x18002c818  sub     edx, r13d
0x18002c81b  mov     r13, [rbp+57h+arg_10]
0x18002c81f  jmp     loc_18002C8D6
0x18002c824  test    dil, 10h
0x18002c828  jz      loc_18002C8EF
0x18002c82e  cmp     ebx, 80h
0x18002c834  jb      short loc_18002C856
0x18002c836  lea     rdx, [rbp+57h+var_80]
0x18002c83a  call    sqlite3GetVarint32
0x18002c83f  mov     edx, [rbp+57h+arg_0]
0x18002c842  lea     r9, qword_1800AE060
0x18002c849  mov     r10, [rbp+57h+arg_8]
0x18002c84d  mov     r11d, 1
0x18002c853  mov     ebx, [rbp+57h+var_80]
0x18002c856  cmp     ebx, 0Ch
0x18002c859  jb      loc_18002C986
0x18002c85f  test    bl, 1
0x18002c862  jnz     loc_18002C986
0x18002c868  lea     r13d, [rbx-0Ch]
0x18002c86c  shr     r13d, 1
0x18002c86f  lea     eax, [r15+r13]
0x18002c873  cmp     eax, edx
0x18002c875  ja      loc_18002C9AE
0x18002c87b  bt      di, 0Ah
0x18002c880  mov     ecx, r15d
0x18002c883  jnb     short loc_18002C8A1
0x18002c885  add     rcx, r10
0x18002c888  mov     edx, r13d
0x18002c88b  call    isAllZero
0x18002c890  mov     r13, [rbp+57h+arg_10]
0x18002c894  test    eax, eax
0x18002c896  jz      loc_18002C6B2
0x18002c89c  sub     edx, [r14]
0x18002c89f  jmp     short loc_18002C8E1
0x18002c8a1  mov     edi, [r14+10h]
0x18002c8a5  mov     eax, edi
0x18002c8a7  mov     rdx, [r14+8]; Buf2
0x18002c8ab  cmp     r13d, edi
0x18002c8ae  cmovl   eax, r13d
0x18002c8b2  add     rcx, r10; Buf1
0x18002c8b5  movsxd  r8, eax; Size
0x18002c8b8  call    memcmp_0
0x18002c8bd  mov     edx, eax
0x18002c8bf  test    eax, eax
0x18002c8c1  jnz     loc_18002C9D2
0x18002c8c7  mov     edx, r13d
0x18002c8ca  mov     r13, [rbp+57h+arg_10]
0x18002c8ce  sub     edx, edi
0x18002c8d0  mov     r11d, 1
0x18002c8d6  mov     r10, [rbp+57h+arg_8]
0x18002c8da  lea     r9, qword_1800AE060
0x18002c8e1  mov     r8d, [rbp+57h+arg_18]
0x18002c8e5  test    edx, edx
0x18002c8e7  jnz     loc_18002C9DC
0x18002c8ed  jmp     short loc_18002C923
0x18002c8ef  test    bl, bl
0x18002c8f1  jz      short loc_18002C926
0x18002c8f3  cmp     bl, 0Ah
0x18002c8f6  jz      short loc_18002C926
0x18002c8f8  cmp     bl, 7
0x18002c8fb  jnz     loc_18002C6B2
0x18002c901  mov     ecx, r15d
0x18002c904  lea     rdx, [rbp+57h+var_78]
0x18002c908  add     rcx, r10
0x18002c90b  call    serialGet7
0x18002c910  test    eax, eax
0x18002c912  jz      loc_18002C6B2
0x18002c918  mov     r8d, [rbp+57h+arg_18]
0x18002c91c  lea     r9, qword_1800AE060
0x18002c923  mov     edx, [rbp+57h+arg_0]
0x18002c926  movzx   eax, word ptr [r13+1Ch]
0x18002c92b  inc     r12d
0x18002c92e  cmp     r12d, eax
0x18002c931  jz      loc_18002CA47
0x18002c937  cmp     ebx, 80h
0x18002c93d  jb      short loc_18002C946
0x18002c93f  lea     eax, [rbx-0Ch]
0x18002c942  shr     eax, 1
0x18002c944  jmp     short loc_18002C94D
0x18002c946  mov     eax, ebx
0x18002c948  movzx   eax, byte ptr [rax+r9]
0x18002c94d  add     r15d, eax
0x18002c950  cmp     r15d, edx
0x18002c953  ja      loc_18002CA47
0x18002c959  mov     eax, ebx
0x18002c95b  mov     ecx, r11d
0x18002c95e  shr     rax, 7
0x18002c962  test    rax, rax
0x18002c965  jz      short loc_18002C972
0x18002c967  inc     ecx
0x18002c969  shr     rax, 7
0x18002c96d  test    rax, rax
0x18002c970  jnz     short loc_18002C967
0x18002c972  add     esi, ecx
0x18002c974  cmp     esi, r8d
0x18002c977  jnb     loc_18002CA14
0x18002c97d  add     r14, 38h ; '8'
0x18002c981  jmp     loc_18002C641
0x18002c986  mov     edx, 0FFFFFFFFh
0x18002c98b  jmp     short loc_18002C9DC
0x18002c98d  lea     r8, aDatabaseCorrup; "database corruption"
  ... truncated ...
```
