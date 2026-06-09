# accessPayload

- ea: `0x180022a7c`
- end: `0x180022e61`
- name: `accessPayload`
- size: `997`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, char *, int)`
- caller_count: `8`
- callee_count: `13`
- tags: ``

## callers

- `0x1800203a4`
- `0x180021878`
- `0x180025a20`
- `0x18003d8e4`
- `0x18003f048`
- `0x180078fe4`
- `0x180090a50`
- `0x180090a80`

## callees

- `0x180022a7c`
- `0x18002619c`
- `0x1800263c0`
- `0x180035450`
- `0x180038b18`
- `0x18003ecc0`
- `0x180045874`
- `0x180046dd0`
- `0x180048290`
- `0x18004f6a0`
- `0x180056f74`
- `0x180078968`
- `0x1800b0010`

## pseudocode

```c
__int64 __fastcall accessPayload(__int64 a1, unsigned int a2, unsigned int a3, char *a4, int a5)
{
  __int64 v5; // rdi
  __int64 v8; // rsi
  __int64 v10; // r8
  __int64 v11; // rdx
  unsigned int *v12; // r10
  unsigned int v13; // ebx
  unsigned __int64 v14; // rcx
  unsigned int v15; // r13d
  unsigned int v16; // esi
  unsigned int v17; // ebx
  __int64 v18; // rax
  __int64 v19; // r9
  unsigned int v20; // ebx
  unsigned int v21; // r15d
  bool v22; // zf
  unsigned __int32 v23; // r15d
  __int64 v24; // rcx
  __int64 v25; // rax
  unsigned int v26; // ebx
  __int64 v27; // rcx
  __int64 v28; // rcx
  unsigned int *v29; // rdx
  char *v30; // rbx
  __int64 v31; // rax
  int *v32; // rdx
  int v33; // ebx
  unsigned int OverflowPage; // eax
  __int64 v36; // r8
  __int64 v37; // rcx
  __int64 v38; // rdx
  int v39; // [rsp+30h] [rbp-30h]
  signed int v40; // [rsp+34h] [rbp-2Ch]
  unsigned int v41; // [rsp+34h] [rbp-2Ch]
  __int64 v42; // [rsp+38h] [rbp-28h] BYREF
  unsigned int v43; // [rsp+40h] [rbp-20h]
  unsigned int *v44; // [rsp+48h] [rbp-18h]
  char *v45; // [rsp+50h] [rbp-10h]
  __int64 v46; // [rsp+A0h] [rbp+40h] BYREF
  void *v47; // [rsp+B8h] [rbp+58h]

  v47 = a4;
  v5 = *(_QWORD *)(a1 + 136);
  v8 = a2;
  if ( *(_WORD *)(a1 + 86) >= *(_WORD *)(v5 + 24) )
  {
    v38 = 75873;
    return sqlite3ReportError(11, v38, "database corruption");
  }
  v44 = *(unsigned int **)(a1 + 32);
  getCellInfo();
  v11 = *(_QWORD *)(a1 + 56);
  v12 = v44;
  v13 = *(unsigned __int16 *)(a1 + 68);
  v14 = v11 - *(_QWORD *)(v5 + 80);
  v46 = v11;
  if ( v14 > v44[14] - v13 )
  {
    v38 = 75888;
    return sqlite3ReportError(11, v38, "database corruption");
  }
  v45 = a4;
  if ( (unsigned int)v8 < v13 )
  {
    if ( (unsigned int)v8 + a3 <= v13 )
      v17 = a3;
    else
      v17 = v13 - v8;
    v15 = copyPayload((void *)(v11 + v8), a4, *(_QWORD *)(v5 + 112));
    if ( v15 )
      return v15;
    v11 = v46;
    a3 -= v17;
    v12 = v44;
    v16 = 0;
    v47 = &a4[v17];
  }
  else
  {
    v15 = 0;
    v16 = v8 - v13;
  }
  if ( !a3 )
    return v15;
  v18 = *(unsigned __int16 *)(a1 + 68);
  v19 = 0;
  v20 = v12[14] - 4;
  v39 = 0;
  v43 = v20;
  v21 = *(_DWORD *)(v18 + v11);
  HIDWORD(v11) = 0;
  v22 = (*(_BYTE *)(a1 + 1) & 4) == 0;
  v23 = _byteswap_ulong(v21);
  LODWORD(v46) = v23;
  if ( v22 )
  {
    v24 = *(_QWORD *)(a1 + 16);
    LODWORD(v11) = (v20 + *(_DWORD *)(a1 + 64) - (_DWORD)v18 - 1) % v20;
    v40 = (v20 + *(_DWORD *)(a1 + 64) - (_DWORD)v18 - 1) / v20;
    if ( !v24 || 4 * v40 > (int)sqlite3MallocSize(v24, v11, v10, 0) )
    {
      if ( (unsigned int)sqlite3FaultSim(413, v11, v10, v19) )
        return 7;
      v25 = sqlite3Realloc(*(_QWORD *)(a1 + 16), 8LL * v40);
      if ( !v25 )
        return 7;
      *(_QWORD *)(a1 + 16) = v25;
    }
    memset_0(*(void **)(a1 + 16), 0, 4LL * v40);
    *(_BYTE *)(a1 + 1) |= 4u;
    LODWORD(v19) = 0;
    v12 = v44;
    goto LABEL_16;
  }
  v36 = *(_QWORD *)(a1 + 16);
  v37 = v16 / v20;
  if ( *(_DWORD *)(v36 + 4 * v37) )
  {
    LODWORD(v19) = v16 / v20;
    v39 = v16 / v20;
    v16 %= v20;
    v23 = *(_DWORD *)(v36 + 4LL * (int)v37);
    LODWORD(v46) = v23;
  }
LABEL_16:
  while ( v23 )
  {
    if ( v23 > v12[16] )
    {
      v38 = 75959;
      return sqlite3ReportError(11, v38, "database corruption");
    }
    *(_DWORD *)(*(_QWORD *)(a1 + 16) + 4LL * (int)v19) = v23;
    if ( v16 >= v20 )
    {
      v31 = *(_QWORD *)(a1 + 16);
      if ( *(_DWORD *)(v31 + 4LL * (int)v19 + 4) )
      {
        v23 = *(_DWORD *)(v31 + 4LL * (int)v19 + 4);
        LODWORD(v46) = v23;
      }
      else
      {
        OverflowPage = getOverflowPage(v12, v23, 0, &v46);
        v23 = v46;
        v15 = OverflowPage;
      }
      v16 -= v20;
      goto LABEL_39;
    }
    if ( v16 + a3 > v20 )
      v26 = v20 - v16;
    else
      v26 = a3;
    v41 = v26;
    if ( !a5 && !v16 )
    {
      v27 = *(_QWORD *)v12;
      if ( **(_QWORD **)(*(_QWORD *)v12 + 72LL) )
      {
        if ( !**(_QWORD **)(v27 + 320) && !*(_QWORD *)(v27 + 280) )
        {
          v28 = *(_QWORD *)(v27 + 328);
          if ( v28 )
          {
            LODWORD(v42) = 0;
            sqlite3WalFindFrame(v28, v23, &v42);
            if ( (_DWORD)v42 )
              goto LABEL_28;
            v12 = v44;
          }
          v32 = (int *)((char *)v47 - 4);
          v42 = (__int64)v47 - 4;
          if ( (char *)v47 - 4 >= v45 )
          {
            v33 = *v32;
            v15 = sqlite3OsRead(*(_QWORD *)(*(_QWORD *)v12 + 72LL), v32, v41 + 4, v12[13] * (unsigned __int64)(v23 - 1));
            v23 = _byteswap_ulong(*(_DWORD *)v42);
            LODWORD(v46) = v23;
            *(_DWORD *)v42 = v33;
LABEL_36:
            v30 = (char *)v47;
            goto LABEL_37;
          }
        }
      }
    }
LABEL_28:
    v42 = 0;
    v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v44 + 272LL))(
            *(_QWORD *)v44,
            v23,
            &v42,
            a5 == 0 ? 2 : 0);
    if ( v15 )
      goto LABEL_36;
    v29 = *(unsigned int **)(v42 + 8);
    v30 = (char *)v47;
    v23 = _byteswap_ulong(*v29);
    LODWORD(v46) = v23;
    v15 = copyPayload((char *)v29 + v16 + 4, v47, v42);
    sqlite3PagerUnref(v42);
    v16 = 0;
LABEL_37:
    a3 -= v41;
    if ( !a3 )
      return v15;
    v47 = &v30[v41];
    v20 = v43;
LABEL_39:
    if ( v15 )
      return v15;
    v12 = v44;
    LODWORD(v19) = ++v39;
  }
  v38 = 76043;
  return sqlite3ReportError(11, v38, "database corruption");
}

```

## disassembly

```asm
0x180022a7c  mov     [rsp-38h+arg_8], rbx
0x180022a81  mov     [rsp-38h+arg_18], r9
0x180022a86  push    rbp
0x180022a87  push    rsi
0x180022a88  push    rdi
0x180022a89  push    r12
0x180022a8b  push    r13
0x180022a8d  push    r14
0x180022a8f  push    r15
0x180022a91  mov     rbp, rsp
0x180022a94  sub     rsp, 60h
0x180022a98  mov     rdi, [rcx+88h]
0x180022a9f  mov     r15, r9
0x180022aa2  mov     r12d, r8d
0x180022aa5  mov     esi, edx
0x180022aa7  mov     r14, rcx
0x180022aaa  movzx   eax, word ptr [rdi+18h]
0x180022aae  cmp     [rcx+56h], ax
0x180022ab2  jnb     loc_180022E14
0x180022ab8  mov     r10, [rcx+20h]
0x180022abc  mov     [rbp+var_18], r10
0x180022ac0  call    getCellInfo
0x180022ac5  mov     rdx, [r14+38h]
0x180022ac9  mov     r10, [rbp+var_18]
0x180022acd  mov     rcx, rdx
0x180022ad0  movzx   ebx, word ptr [r14+44h]
0x180022ad5  sub     rcx, [rdi+50h]
0x180022ad9  mov     [rbp+arg_0], rdx
0x180022add  mov     eax, [r10+38h]
0x180022ae1  sub     eax, ebx
0x180022ae3  cmp     rcx, rax
0x180022ae6  ja      loc_180022E36
0x180022aec  mov     [rbp+var_10], r15
0x180022af0  cmp     esi, ebx
0x180022af2  jb      short loc_180022AFD
0x180022af4  xor     edi, edi
0x180022af6  mov     r13d, edi
0x180022af9  sub     esi, ebx
0x180022afb  jmp     short loc_180022B4B
0x180022afd  lea     eax, [rsi+r12]
0x180022b01  cmp     eax, ebx
0x180022b03  jbe     loc_180022E3D
0x180022b09  sub     ebx, esi
0x180022b0b  mov     rax, [rdi+70h]
0x180022b0f  lea     rcx, [rdx+rsi]; Src
0x180022b13  mov     r9d, [rbp+arg_20]
0x180022b17  mov     rdx, r15; void *
0x180022b1a  mov     r8d, ebx
0x180022b1d  mov     [rsp+60h+var_40], rax; __int64
0x180022b22  call    copyPayload
0x180022b27  xor     edi, edi
0x180022b29  mov     r13d, eax
0x180022b2c  test    eax, eax
0x180022b2e  jnz     loc_180022DAE
0x180022b34  mov     rdx, [rbp+arg_0]
0x180022b38  sub     r12d, ebx
0x180022b3b  mov     r10, [rbp+var_18]
0x180022b3f  mov     esi, edi
0x180022b41  movsxd  rax, ebx
0x180022b44  add     r15, rax
0x180022b47  mov     [rbp+arg_18], r15
0x180022b4b  test    r12d, r12d
0x180022b4e  jz      loc_180022DAE
0x180022b54  movzx   eax, word ptr [r14+44h]
0x180022b59  mov     r9d, edi
0x180022b5c  mov     ebx, [r10+38h]
0x180022b60  add     ebx, 0FFFFFFFCh
0x180022b63  mov     [rbp+var_30], edi
0x180022b66  mov     [rbp+var_20], ebx
0x180022b69  mov     r15d, [rax+rdx]
0x180022b6d  xor     edx, edx
0x180022b6f  test    byte ptr [r14+1], 4
0x180022b74  bswap   r15d
0x180022b77  mov     dword ptr [rbp+arg_0], r15d
0x180022b7b  jnz     loc_180022DE8
0x180022b81  mov     ecx, [r14+40h]
0x180022b85  sub     ecx, eax
0x180022b87  lea     eax, [rcx-1]
0x180022b8a  mov     rcx, [r14+10h]
0x180022b8e  add     eax, ebx
0x180022b90  div     ebx
0x180022b92  mov     [rbp+var_2C], eax
0x180022b95  test    rcx, rcx
0x180022b98  jnz     loc_180022DD0
0x180022b9e  mov     ecx, 19Dh
0x180022ba3  call    sqlite3FaultSim
0x180022ba8  test    eax, eax
0x180022baa  jnz     loc_180022E45
0x180022bb0  mov     eax, [rbp+var_2C]
0x180022bb3  mov     rcx, [r14+10h]
0x180022bb7  add     eax, eax
0x180022bb9  movsxd  rdx, eax
0x180022bbc  shl     rdx, 2
0x180022bc0  call    sqlite3Realloc
0x180022bc5  test    rax, rax
0x180022bc8  jz      loc_180022E45
0x180022bce  mov     [r14+10h], rax
0x180022bd2  movsxd  r8, [rbp+var_2C]
0x180022bd6  xor     edx, edx; Val
0x180022bd8  mov     rcx, [r14+10h]; void *
0x180022bdc  shl     r8, 2; Size
0x180022be0  call    memset_0
0x180022be5  or      byte ptr [r14+1], 4
0x180022bea  mov     r9d, edi
0x180022bed  mov     r10, [rbp+var_18]
0x180022bf1  test    r15d, r15d
0x180022bf4  jz      loc_180022E56
0x180022bfa  cmp     r15d, [r10+40h]
0x180022bfe  ja      loc_180022E4F
0x180022c04  mov     rax, [r14+10h]
0x180022c08  movsxd  rcx, r9d
0x180022c0b  mov     [rax+rcx*4], r15d
0x180022c0f  cmp     esi, ebx
0x180022c11  jnb     loc_180022CF6
0x180022c17  lea     eax, [rsi+r12]
0x180022c1b  cmp     eax, ebx
0x180022c1d  ja      loc_180022DC9
0x180022c23  mov     ebx, r12d
0x180022c26  mov     [rbp+var_2C], ebx
0x180022c29  cmp     [rbp+arg_20], edi
0x180022c2c  jnz     short loc_180022C7B
0x180022c2e  test    esi, esi
0x180022c30  jnz     short loc_180022C7B
0x180022c32  mov     rcx, [r10]
0x180022c35  mov     rax, [rcx+48h]
0x180022c39  cmp     [rax], rdi
0x180022c3c  jz      short loc_180022C7B
0x180022c3e  mov     rax, [rcx+140h]
0x180022c45  cmp     [rax], rdi
0x180022c48  jnz     short loc_180022C7B
0x180022c4a  cmp     [rcx+118h], rdi
0x180022c51  jnz     short loc_180022C7B
0x180022c53  mov     rcx, [rcx+148h]
0x180022c5a  test    rcx, rcx
0x180022c5d  jz      loc_180022D15
0x180022c63  lea     r8, [rbp+var_28]
0x180022c67  mov     dword ptr [rbp+var_28], edi
0x180022c6a  mov     edx, r15d
0x180022c6d  call    sqlite3WalFindFrame
0x180022c72  cmp     dword ptr [rbp+var_28], edi
0x180022c75  jz      loc_180022D11
0x180022c7b  mov     eax, [rbp+arg_20]
0x180022c7e  lea     r8, [rbp+var_28]
0x180022c82  mov     r10, [rbp+var_18]
0x180022c86  neg     eax
0x180022c88  mov     [rbp+var_28], rdi
0x180022c8c  mov     edx, r15d
0x180022c8f  sbb     r9d, r9d
0x180022c92  not     r9d
0x180022c95  mov     r10, [r10]
0x180022c98  and     r9d, 2
0x180022c9c  mov     rcx, r10
0x180022c9f  mov     rax, [r10+110h]
0x180022ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cab  mov     r13d, eax
0x180022cae  test    eax, eax
0x180022cb0  jnz     loc_180022D60
0x180022cb6  mov     r8, [rbp+var_28]
0x180022cba  lea     ecx, [rsi+4]
0x180022cbd  mov     r9d, [rbp+arg_20]
0x180022cc1  mov     [rsp+60h+var_40], r8; __int64
0x180022cc6  mov     rdx, [r8+8]
0x180022cca  mov     r8d, ebx
0x180022ccd  mov     rbx, [rbp+arg_18]
0x180022cd1  add     rcx, rdx; Src
0x180022cd4  mov     r15d, [rdx]
0x180022cd7  mov     rdx, rbx; void *
0x180022cda  bswap   r15d
0x180022cdd  mov     dword ptr [rbp+arg_0], r15d
0x180022ce1  call    copyPayload
0x180022ce6  mov     rcx, [rbp+var_28]
0x180022cea  mov     r13d, eax
0x180022ced  call    sqlite3PagerUnref
0x180022cf2  mov     esi, edi
0x180022cf4  jmp     short loc_180022D64
0x180022cf6  mov     rax, [r14+10h]
0x180022cfa  cmp     [rax+rcx*4+4], edi
0x180022cfe  jz      loc_180022D90
0x180022d04  mov     r15d, [rax+rcx*4+4]
0x180022d09  mov     dword ptr [rbp+arg_0], r15d
0x180022d0d  sub     esi, ebx
0x180022d0f  jmp     short loc_180022D77
0x180022d11  mov     r10, [rbp+var_18]
0x180022d15  mov     rdx, [rbp+arg_18]
0x180022d19  add     rdx, 0FFFFFFFFFFFFFFFCh
0x180022d1d  mov     [rbp+var_28], rdx
0x180022d21  cmp     rdx, [rbp+var_10]
0x180022d25  jb      loc_180022C7B
0x180022d2b  mov     eax, [r10+34h]
0x180022d2f  lea     r9d, [r15-1]
0x180022d33  mov     rcx, [r10]
0x180022d36  mov     r8d, [rbp+var_2C]
0x180022d3a  mov     ebx, [rdx]
0x180022d3c  add     r8d, 4
0x180022d40  imul    r9, rax
0x180022d44  mov     rcx, [rcx+48h]
0x180022d48  call    sqlite3OsRead
0x180022d4d  mov     r13d, eax
0x180022d50  mov     rax, [rbp+var_28]
0x180022d54  mov     r15d, [rax]
0x180022d57  bswap   r15d
0x180022d5a  mov     dword ptr [rbp+arg_0], r15d
0x180022d5e  mov     [rax], ebx
0x180022d60  mov     rbx, [rbp+arg_18]
0x180022d64  movsxd  rax, [rbp+var_2C]
0x180022d68  sub     r12d, eax
0x180022d6b  jz      short loc_180022DAE
0x180022d6d  add     rbx, rax
0x180022d70  mov     [rbp+arg_18], rbx
0x180022d74  mov     ebx, [rbp+var_20]
0x180022d77  test    r13d, r13d
0x180022d7a  jnz     short loc_180022DAE
0x180022d7c  mov     r9d, [rbp+var_30]
0x180022d80  mov     r10, [rbp+var_18]
0x180022d84  inc     r9d
0x180022d87  mov     [rbp+var_30], r9d
0x180022d8b  jmp     loc_180022BF1
0x180022d90  lea     r9, [rbp+arg_0]
0x180022d94  xor     r8d, r8d
0x180022d97  mov     edx, r15d
0x180022d9a  mov     rcx, r10
0x180022d9d  call    getOverflowPage
0x180022da2  mov     r15d, dword ptr [rbp+arg_0]
0x180022da6  mov     r13d, eax
0x180022da9  jmp     loc_180022D0D
0x180022dae  mov     eax, r13d
0x180022db1  mov     rbx, [rsp+60h+arg_8]
0x180022db9  add     rsp, 60h
0x180022dbd  pop     r15
0x180022dbf  pop     r14
0x180022dc1  pop     r13
0x180022dc3  pop     r12
0x180022dc5  pop     rdi
0x180022dc6  pop     rsi
0x180022dc7  pop     rbp
0x180022dc8  retn
0x180022dc9  sub     ebx, esi
0x180022dcb  jmp     loc_180022C26
0x180022dd0  call    sqlite3MallocSize
0x180022dd5  mov     ecx, [rbp+var_2C]
0x180022dd8  shl     ecx, 2
0x180022ddb  cmp     ecx, eax
0x180022ddd  jle     loc_180022BD2
0x180022de3  jmp     loc_180022B9E
0x180022de8  mov     r8, [r14+10h]
0x180022dec  mov     eax, esi
0x180022dee  div     ebx
0x180022df0  mov     ecx, eax
0x180022df2  cmp     [r8+rax*4], edi
0x180022df6  jz      loc_180022BF1
0x180022dfc  movsxd  rax, ecx
0x180022dff  mov     r9d, ecx
0x180022e02  mov     [rbp+var_30], ecx
0x180022e05  mov     esi, edx
0x180022e07  mov     r15d, [r8+rax*4]
0x180022e0b  mov     dword ptr [rbp+arg_0], r15d
0x180022e0f  jmp     loc_180022BF1
0x180022e14  mov     edx, 12861h
0x180022e19  jmp     short loc_180022E20
0x180022e1b  mov     edx, 1290Bh
0x180022e20  lea     r8, aDatabaseCorrup; "database corruption"
0x180022e27  mov     ecx, 0Bh
0x180022e2c  call    sqlite3ReportError
0x180022e31  jmp     loc_180022DB1
0x180022e36  mov     edx, 12870h
0x180022e3b  jmp     short loc_180022E20
0x180022e3d  mov     ebx, r12d
0x180022e40  jmp     loc_180022B0B
0x180022e45  mov     eax, 7
0x180022e4a  jmp     loc_180022DB1
0x180022e4f  mov     edx, 128B7h
0x180022e54  jmp     short loc_180022E20
0x180022e56  test    r12d, r12d
0x180022e59  jz      loc_180022DAE
0x180022e5f  jmp     short loc_180022E1B
```
