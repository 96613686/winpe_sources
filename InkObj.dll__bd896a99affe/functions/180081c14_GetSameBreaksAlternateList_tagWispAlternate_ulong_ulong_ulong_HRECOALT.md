# GetSameBreaksAlternateList(tagWispAlternate *,ulong,ulong,ulong *,HRECOALT__ * *)

- ea: `0x180081c14`
- end: `0x1800822a2`
- name: `?GetSameBreaksAlternateList@@YAJPEAUtagWispAlternate@@KKPEAKPEAPEAUHRECOALT__@@@Z`
- size: `1678`
- prototype: `__int64 __fastcall(struct tagWispAlternate *, unsigned int, unsigned int, unsigned int *, HRECOALT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800803a0`

## callees

- `0x180081c14`
- `0x180083d50`
- `0x180104ece`

## import_xrefs

- `msvcrt!malloc` at `0x180081cda`
- `msvcrt!malloc` at `0x180081df0`
- `msvcrt!malloc` at `0x180081e2f`
- `msvcrt!malloc` at `0x180081cda`
- `msvcrt!malloc` at `0x180081df0`
- `msvcrt!malloc` at `0x180081e2f`
- `msvcrt!free` at `0x180081e0a`
- `msvcrt!free` at `0x180081e48`
- `msvcrt!free` at `0x18008226e`
- `msvcrt!free` at `0x180082277`
- `msvcrt!free` at `0x180082282`
- `msvcrt!free` at `0x180081e0a`
- `msvcrt!free` at `0x180081e48`
- `msvcrt!free` at `0x18008226e`
- `msvcrt!free` at `0x180082277`
- `msvcrt!free` at `0x180082282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008213c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180082184`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180082191`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008213c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180082184`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180082191`

## pseudocode

```c
__int64 __fastcall GetSameBreaksAlternateList(
        struct tagWispAlternate *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int *a4,
        HRECOALT *a5)
{
  unsigned int v5; // ebp
  unsigned int *v7; // r13
  unsigned int v8; // r12d
  unsigned int v10; // r8d
  unsigned int v11; // r10d
  unsigned int v13; // esi
  char *v14; // rax
  char *v15; // r14
  unsigned int v16; // r9d
  __int64 v17; // rbp
  __int64 v18; // r13
  __int64 v19; // r15
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r10
  __int64 v23; // r12
  __int64 v24; // r8
  __int64 v25; // rax
  unsigned int v26; // r10d
  __int64 v27; // rdx
  bool v28; // zf
  __int64 v29; // rax
  unsigned int v30; // r15d
  size_t v31; // rbx
  char *v32; // rax
  char *v33; // r12
  void *v34; // rcx
  char *v35; // rax
  unsigned int i; // edx
  char *v37; // rcx
  __int64 v38; // rax
  int v39; // ebx
  __int64 v40; // r11
  unsigned int v41; // r10d
  __int64 v42; // r9
  __int64 v43; // r8
  unsigned int v44; // r11d
  __int64 v45; // r10
  __int64 v46; // r9
  __int64 v47; // r8
  unsigned int v48; // r15d
  unsigned int v49; // r11d
  int v50; // ebp
  unsigned int k; // eax
  __int64 v52; // rcx
  int v53; // edx
  __int64 v54; // rcx
  __int64 v55; // r9
  __int64 v56; // r10
  __int64 v57; // r8
  __int64 v58; // rbx
  __int64 v59; // r9
  __int64 v60; // rcx
  __int64 v61; // rax
  __int64 v62; // rdx
  __int64 v63; // r10
  __int64 v64; // r8
  __int64 v65; // r10
  __int64 v66; // rdx
  __int64 v67; // r12
  unsigned __int64 v68; // rbx
  __int64 j; // r15
  HRECOALT v70; // rax
  HRECOALT v71; // r12
  _DWORD *v72; // rax
  __int64 v73; // r9
  __int64 v74; // r8
  __int64 v75; // r11
  __int64 v76; // rbx
  __int64 v77; // rbx
  __int64 v78; // [rsp+28h] [rbp-70h]
  __int64 v79; // [rsp+30h] [rbp-68h]
  char *v80; // [rsp+30h] [rbp-68h]
  char *v81; // [rsp+38h] [rbp-60h]
  char *Block; // [rsp+40h] [rbp-58h]
  int v85; // [rsp+B0h] [rbp+18h]

  v5 = 0;
  v7 = a4;
  v8 = a2;
  v10 = 100;
  if ( !a5 )
  {
    *a4 = 1;
    v11 = 1;
    while ( v8 <= a3 )
    {
      v11 *= *(_DWORD *)(56LL * *(unsigned int *)(*((_QWORD *)a1 + 2) + 4LL * v8)
                       + *(_QWORD *)(**(_QWORD **)a1 + 8LL)
                       + 40);
      *a4 = v11;
      if ( v11 > 0x64 )
      {
        *a4 = 100;
        return 1;
      }
      ++v8;
    }
    return v5;
  }
  if ( *a4 <= 0x64 )
  {
    if ( !*a4 )
      return 0;
    v10 = *a4;
  }
  else
  {
    *a4 = 100;
  }
  v13 = a3 - a2 + 1;
  if ( v13 <= 0x7FFFFFF && v10 <= 0x7FFFFFF )
  {
    v14 = (char *)malloc(32LL * v13);
    v81 = v14;
    v15 = v14;
    if ( !v14 )
    {
      *v7 = 0;
      return 2147942414LL;
    }
    memset_0(v14, 0, 32LL * v13);
    if ( v13 )
    {
      v16 = 0;
      v17 = *((_QWORD *)a1 + 3);
      v18 = *((_QWORD *)a1 + 2);
      v19 = *(_QWORD *)(**(_QWORD **)a1 + 8LL);
      do
      {
        v20 = v16 + v8;
        v21 = *(unsigned int *)(v17 + 4 * v20);
        v22 = 56LL * *(unsigned int *)(v18 + 4 * v20);
        v23 = 5 * v21;
        v24 = 0;
        v25 = v22 + v19;
        v79 = v22 + v19;
        do
        {
          if ( *(_DWORD *)(*(_QWORD *)(v22 + v19 + 48) + 40 * v24 + 16) == *(_DWORD *)(*(_QWORD *)(v22 + v19 + 48)
                                                                                     + 40 * v21
                                                                                     + 16) )
            break;
          v24 = (unsigned int)(v24 + 1);
        }
        while ( (unsigned int)v24 <= (unsigned int)v21 );
        v26 = *(_DWORD *)(v19 + v22 + 40);
        v27 = (unsigned int)(v24 + 1);
        v28 = v26 == (_DWORD)v27;
        if ( v26 > (unsigned int)v27 )
        {
          do
          {
            if ( *(_DWORD *)(*(_QWORD *)(v25 + 48) + 40 * v27 + 16) == *(_DWORD *)(*(_QWORD *)(v25 + 48) + 8 * v23 + 16) )
              break;
            v27 = (unsigned int)(v27 + 1);
          }
          while ( (unsigned int)v27 < v26 );
          v28 = v26 == (_DWORD)v27;
        }
        v8 = a2;
        if ( v28 )
          LODWORD(v27) = -1;
        v29 = v16++;
        v29 *= 32;
        *(_DWORD *)&v15[v29] = 0;
        *(_QWORD *)&v15[v29 + 8] = v79;
        *(_DWORD *)&v15[v29 + 16] = v24;
        *(_DWORD *)&v15[v29 + 20] = v27;
      }
      while ( v16 < v13 );
      v5 = 0;
      v7 = a4;
    }
    v30 = *v7;
    v31 = 16LL * *v7;
    v32 = (char *)malloc(v31);
    v80 = v32;
    v33 = v32;
    if ( !v32 )
    {
      *v7 = 0;
      v34 = v15;
LABEL_32:
      free(v34);
      return 2147942414LL;
    }
    memset_0(v32, 0, v31);
    v35 = (char *)malloc(4LL * v13 * v30);
    Block = v35;
    if ( !v35 )
    {
      *v7 = 0;
      free(v15);
      v34 = v33;
      goto LABEL_32;
    }
    v85 = 0;
    memset_0(v35, 0, 4LL * v13 * v30);
    for ( i = 0; i < v30; *(_QWORD *)&v33[8 * v38] = v37 )
    {
      v37 = &Block[4 * i * v13];
      v38 = 2LL * i++;
    }
    v39 = 0;
    if ( v13 )
    {
      v40 = *(_QWORD *)v33;
      v41 = 0;
      v42 = 0;
      do
      {
        ++v41;
        v43 = *(unsigned int *)&v15[32 * v42 + 16];
        v39 += *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v15[32 * v42 + 8] + 48LL) + 40 * v43);
        *(_DWORD *)(v40 + 4 * v42++) = v43;
      }
      while ( v41 < v13 );
    }
    v44 = 0;
    *((_DWORD *)v33 + 2) = v39;
    if ( v13 )
    {
      v45 = 0;
      do
      {
        v46 = 32 * v45;
        if ( *(_DWORD *)&v15[32 * v45 + 20] != -1 )
        {
          v47 = *(_QWORD *)(*(_QWORD *)&v15[v46 + 8] + 48LL);
          *(_DWORD *)&v15[v46 + 24] = v39
                                    + *(_DWORD *)(v47 + 40LL * *(unsigned int *)&v15[v46 + 20])
                                    - *(_DWORD *)(v47 + 40LL * *(unsigned int *)&v15[v46 + 16]);
        }
        ++v44;
        ++v45;
      }
      while ( v44 < v13 );
    }
    v48 = 1;
    if ( *v7 <= 1 )
    {
LABEL_81:
      v68 = 4LL * v13;
      *v7 = v48;
      if ( v68 <= 0xFFFFFFFF )
      {
        for ( j = 0; (unsigned int)j < *v7; j = (unsigned int)(j + 1) )
        {
          v70 = (HRECOALT)CoTaskMemAlloc(0x28u);
          v71 = v70;
          if ( !v70 )
          {
            v77 = 0;
            if ( (_DWORD)j )
            {
              do
              {
                DestroyAlternate(a5[v77]);
                v77 = (unsigned int)(v77 + 1);
              }
              while ( (unsigned int)v77 < (unsigned int)j );
              v15 = v81;
            }
            goto LABEL_100;
          }
          *(_OWORD *)v70 = 0;
          *((_OWORD *)v70 + 1) = 0;
          *((_QWORD *)v70 + 4) = 0;
          *(_QWORD *)v70 = *(_QWORD *)a1;
          *((_QWORD *)v70 + 4) = *((_QWORD *)a1 + 4);
          *((_DWORD *)v70 + 2) = v13;
          *((_QWORD *)v70 + 2) = CoTaskMemAlloc((unsigned int)v68);
          v72 = CoTaskMemAlloc((unsigned int)v68);
          *((_QWORD *)v71 + 3) = v72;
          if ( !v72 || (v73 = *((_QWORD *)v71 + 2)) == 0 )
          {
            v76 = 0;
            if ( (_DWORD)j )
            {
              do
              {
                DestroyAlternate(a5[v76]);
                v76 = (unsigned int)(v76 + 1);
              }
              while ( (unsigned int)v76 < (unsigned int)j );
              v15 = v81;
            }
            DestroyAlternate(v71);
LABEL_100:
            v5 = -2147024882;
            break;
          }
          if ( v13 )
          {
            v74 = 0;
            v75 = *(_QWORD *)&v80[16 * (unsigned int)j];
            do
            {
              *(_DWORD *)(v73 + 4 * v74) = *(_DWORD *)(*((_QWORD *)a1 + 2) + 4LL * ((unsigned int)v74 + a2));
              v72[v74] = *(_DWORD *)(v75 + 4 * v74);
              v74 = (unsigned int)(v74 + 1);
            }
            while ( (unsigned int)v74 < v13 );
            v5 = 0;
          }
          LODWORD(v68) = 4 * v13;
          a5[j] = v71;
        }
        v33 = v80;
      }
      else
      {
        v5 = -2147418113;
      }
      free(v15);
      free(v33);
      free(Block);
      return v5;
    }
    v49 = 0;
    v50 = 0;
    while ( 1 )
    {
      for ( k = 0; k < v13; ++k )
      {
        v52 = 32LL * k;
        if ( *(_DWORD *)&v15[v52 + 20] != -1 )
        {
          v53 = *(_DWORD *)&v15[v52 + 24];
          v49 = k;
          goto LABEL_55;
        }
      }
      if ( k == v13 )
        goto LABEL_80;
      k = v49;
      if ( v49 < v13 )
      {
        v53 = v85;
        do
        {
LABEL_55:
          v54 = 32LL * k;
          if ( *(_DWORD *)&v15[v54 + 20] != -1 && v53 > *(_DWORD *)&v15[v54 + 24] )
          {
            v53 = *(_DWORD *)&v15[v54 + 24];
            v49 = k;
          }
          ++k;
        }
        while ( k < v13 );
        v85 = v53;
        v50 = v53;
      }
      if ( v13 )
      {
        v55 = 0;
        v56 = *(_QWORD *)&v33[16 * v48];
        v57 = 2LL * *(unsigned int *)&v15[32 * v49];
        do
        {
          *(_DWORD *)(v56 + 4 * v55) = *(_DWORD *)(*(_QWORD *)&v33[8 * v57] + 4 * v55);
          v55 = (unsigned int)(v55 + 1);
        }
        while ( (unsigned int)v55 < v13 );
      }
      v58 = 4LL * v49;
      v59 = 32LL * v49;
      v78 = *(_QWORD *)&v33[16 * v48];
      v60 = *(_QWORD *)&v15[v59 + 8];
      v61 = *(unsigned int *)(v58 + v78);
      v62 = (unsigned int)(v61 + 1);
      if ( (unsigned int)v62 < *(_DWORD *)(v60 + 40) )
      {
        do
        {
          if ( *(_DWORD *)(*(_QWORD *)(v60 + 48) + 40 * v62 + 16) == *(_DWORD *)(*(_QWORD *)(v60 + 48) + 40 * v61 + 16) )
            break;
          v62 = (unsigned int)(v62 + 1);
        }
        while ( (unsigned int)v62 < *(_DWORD *)(*(_QWORD *)&v15[v59 + 8] + 40LL) );
        v33 = v80;
        v60 = *(_QWORD *)&v15[v59 + 8];
      }
      v63 = (unsigned int)++*(_DWORD *)&v15[v59];
      v64 = *(unsigned int *)&v15[v59 + 20];
      *(_DWORD *)(v58 + v78) = v62;
      v65 = 16 * v63;
      *(_DWORD *)&v33[16 * v48 + 8] = v50;
      if ( *(_DWORD *)(v58 + *(_QWORD *)&v33[v65]) != (_DWORD)v64 )
        break;
      v66 = (unsigned int)(v64 + 1);
      if ( (unsigned int)v66 < *(_DWORD *)(v60 + 40) )
      {
        v67 = *(_QWORD *)&v15[v59 + 8];
        do
        {
          if ( *(_DWORD *)(*(_QWORD *)(v67 + 48) + 40 * v66 + 16) == *(_DWORD *)(*(_QWORD *)(v67 + 48) + 40 * v64 + 16) )
            break;
          v66 = (unsigned int)(v66 + 1);
        }
        while ( (unsigned int)v66 < *(_DWORD *)(v67 + 40) );
        v33 = v80;
        v60 = *(_QWORD *)&v15[v59 + 8];
      }
      *(_DWORD *)&v15[v59 + 16] = v64;
      if ( (_DWORD)v66 != *(_DWORD *)(v60 + 40) )
      {
        *(_DWORD *)&v15[v59 + 20] = v66;
        goto LABEL_77;
      }
      *(_DWORD *)&v15[v59 + 20] = -1;
LABEL_79:
      if ( ++v48 >= *v7 )
      {
LABEL_80:
        v5 = 0;
        goto LABEL_81;
      }
    }
    LODWORD(v66) = v64;
LABEL_77:
    if ( (_DWORD)v66 != -1 )
      *(_DWORD *)&v15[v59 + 24] = *(_DWORD *)&v33[v65 + 8]
                                + *(_DWORD *)(*(_QWORD *)(v60 + 48) + 40LL * (unsigned int)v66)
                                - *(_DWORD *)(*(_QWORD *)(v60 + 48) + 40LL * *(unsigned int *)&v15[v59 + 16]);
    goto LABEL_79;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x180081c14  mov     [rsp+arg_18], r9
0x180081c19  mov     [rsp+arg_8], edx
0x180081c1d  mov     [rsp+arg_0], rcx
0x180081c22  push    rbx
0x180081c23  push    rbp
0x180081c24  push    rsi
0x180081c25  push    rdi
0x180081c26  push    r12
0x180081c28  push    r13
0x180081c2a  push    r14
0x180081c2c  push    r15
0x180081c2e  sub     rsp, 58h
0x180081c32  xor     ebp, ebp
0x180081c34  mov     esi, r8d
0x180081c37  mov     r13, r9
0x180081c3a  mov     r12d, edx
0x180081c3d  mov     r15, rcx
0x180081c40  mov     [rsp+98h+var_78], ebp
0x180081c44  lea     r8d, [rbp+64h]
0x180081c48  cmp     [rsp+98h+arg_20], rbp
0x180081c50  jnz     short loc_180081C99
0x180081c52  lea     edi, [rbp+1]
0x180081c55  mov     [r9], edi
0x180081c58  mov     r10d, edi
0x180081c5b  cmp     r12d, esi
0x180081c5e  ja      loc_180082288
0x180081c64  mov     rax, [r15+10h]
0x180081c68  mov     ecx, r12d
0x180081c6b  mov     ecx, [rax+rcx*4]
0x180081c6e  mov     rax, [r15]
0x180081c71  imul    rdx, rcx, 38h ; '8'
0x180081c75  mov     rcx, [rax]
0x180081c78  mov     rax, [rcx+8]
0x180081c7c  imul    r10d, [rdx+rax+28h]
0x180081c82  mov     [r9], r10d
0x180081c85  cmp     r10d, r8d
0x180081c88  ja      short loc_180081C8F
0x180081c8a  add     r12d, edi
0x180081c8d  jmp     short loc_180081C5B
0x180081c8f  mov     [r9], r8d
0x180081c92  mov     ebp, edi
0x180081c94  jmp     loc_180082288
0x180081c99  cmp     [r9], r8d
0x180081c9c  jbe     short loc_180081CA3
0x180081c9e  mov     [r9], r8d
0x180081ca1  jmp     short loc_180081CB2
0x180081ca3  cmp     [r9], ebp
0x180081ca6  jnz     short loc_180081CAF
0x180081ca8  xor     eax, eax
0x180081caa  jmp     loc_180082291
0x180081caf  mov     r8d, [r9]
0x180081cb2  sub     esi, edx
0x180081cb4  mov     edi, 1
0x180081cb9  add     esi, edi
0x180081cbb  mov     eax, 7FFFFFFh
0x180081cc0  cmp     esi, eax
0x180081cc2  ja      loc_18008228C
0x180081cc8  cmp     r8d, eax
0x180081ccb  ja      loc_18008228C
0x180081cd1  mov     ebx, esi
0x180081cd3  shl     rbx, 5
0x180081cd7  mov     rcx, rbx; Size
0x180081cda  call    cs:__imp_malloc
0x180081ce0  mov     [rsp+98h+var_60], rax
0x180081ce5  mov     r14, rax
0x180081ce8  test    rax, rax
0x180081ceb  jnz     short loc_180081CFB
0x180081ced  mov     [r13+0], ebp
0x180081cf1  mov     eax, 8007000Eh
0x180081cf6  jmp     loc_180082291
0x180081cfb  mov     r8, rbx; Size
0x180081cfe  xor     edx, edx; Val
0x180081d00  mov     rcx, r14; void *
0x180081d03  call    memset_0
0x180081d08  test    esi, esi
0x180081d0a  jz      loc_180081DE2
0x180081d10  mov     rax, [r15]
0x180081d13  xor     r9d, r9d
0x180081d16  mov     rbx, [rsp+98h+arg_0]
0x180081d1e  mov     rbp, [r15+18h]
0x180081d22  mov     rcx, [rax]
0x180081d25  mov     r13, [rbx+10h]
0x180081d29  mov     r15, [rcx+8]
0x180081d2d  lea     eax, [r9+r12]
0x180081d31  mov     edx, [rbp+rax*4+0]
0x180081d35  mov     eax, [r13+rax*4+0]
0x180081d3a  imul    r10, rax, 38h ; '8'
0x180081d3e  lea     r12, [rdx+rdx*4]
0x180081d42  xor     r8d, r8d
0x180081d45  mov     r11, [r10+r15+30h]
0x180081d4a  lea     rax, [r10+r15]
0x180081d4e  mov     [rsp+98h+var_68], rax
0x180081d53  mov     ebx, [r11+r12*8+10h]
0x180081d58  lea     rcx, [r8+r8*4]
0x180081d5c  cmp     [r11+rcx*8+10h], ebx
0x180081d61  jz      short loc_180081D6B
0x180081d63  add     r8d, edi
0x180081d66  cmp     r8d, edx
0x180081d69  jbe     short loc_180081D58
0x180081d6b  mov     r10d, [r15+r10+28h]
0x180081d70  lea     edx, [r8+1]
0x180081d74  cmp     r10d, edx
0x180081d77  jbe     short loc_180081D97
0x180081d79  mov     r11, [rax+30h]
0x180081d7d  mov     ebx, [r11+r12*8+10h]
0x180081d82  lea     rcx, [rdx+rdx*4]
0x180081d86  cmp     [r11+rcx*8+10h], ebx
0x180081d8b  jz      short loc_180081D94
0x180081d8d  add     edx, edi
0x180081d8f  cmp     edx, r10d
0x180081d92  jb      short loc_180081D82
0x180081d94  cmp     r10d, edx
0x180081d97  mov     rcx, [rsp+98h+var_68]
0x180081d9c  mov     eax, 0FFFFFFFFh
0x180081da1  mov     r12d, [rsp+98h+arg_8]
0x180081da9  cmovz   edx, eax
0x180081dac  mov     eax, r9d
0x180081daf  add     r9d, edi
0x180081db2  shl     rax, 5
0x180081db6  mov     dword ptr [rax+r14], 0
0x180081dbe  mov     [rax+r14+8], rcx
0x180081dc3  mov     [rax+r14+10h], r8d
0x180081dc8  mov     [rax+r14+14h], edx
0x180081dcd  cmp     r9d, esi
0x180081dd0  jb      loc_180081D2D
0x180081dd6  mov     ebp, [rsp+98h+var_78]
0x180081dda  mov     r13, [rsp+98h+arg_18]
0x180081de2  mov     r15d, [r13+0]
0x180081de6  mov     ebx, r15d
0x180081de9  shl     rbx, 4
0x180081ded  mov     rcx, rbx; Size
0x180081df0  call    cs:__imp_malloc
0x180081df6  mov     [rsp+98h+var_68], rax
0x180081dfb  mov     r12, rax
0x180081dfe  test    rax, rax
0x180081e01  jnz     short loc_180081E15
0x180081e03  mov     [r13+0], eax
0x180081e07  mov     rcx, r14; Block
0x180081e0a  call    cs:__imp_free
0x180081e10  jmp     loc_180081CF1
0x180081e15  mov     r8, rbx; Size
0x180081e18  xor     edx, edx; Val
0x180081e1a  mov     rcx, r12; void *
0x180081e1d  call    memset_0
0x180081e22  mov     ebx, r15d
0x180081e25  imul    ebx, esi
0x180081e28  shl     rbx, 2
0x180081e2c  mov     rcx, rbx; Size
0x180081e2f  call    cs:__imp_malloc
0x180081e35  xor     ecx, ecx
0x180081e37  mov     [rsp+98h+Block], rax
0x180081e3c  test    rax, rax
0x180081e3f  jnz     short loc_180081E53
0x180081e41  mov     [r13+0], ecx
0x180081e45  mov     rcx, r14; Block
0x180081e48  call    cs:__imp_free
0x180081e4e  mov     rcx, r12
0x180081e51  jmp     short loc_180081E0A
0x180081e53  mov     dword ptr [rsp+98h+var_70], ecx
0x180081e57  mov     r8, rbx; Size
0x180081e5a  mov     [rsp+98h+arg_10], ecx
0x180081e61  xor     edx, edx; Val
0x180081e63  mov     rcx, rax; void *
0x180081e66  call    memset_0
0x180081e6b  xor     edx, edx
0x180081e6d  test    r15d, r15d
0x180081e70  jz      short loc_180081E90
0x180081e72  mov     r8, [rsp+98h+Block]
0x180081e77  mov     eax, esi
0x180081e79  imul    eax, edx
0x180081e7c  lea     rcx, [r8+rax*4]
0x180081e80  mov     eax, edx
0x180081e82  add     rax, rax
0x180081e85  add     edx, edi
0x180081e87  mov     [r12+rax*8], rcx
0x180081e8b  cmp     edx, r15d
0x180081e8e  jb      short loc_180081E77
0x180081e90  xor     ebx, ebx
0x180081e92  test    esi, esi
0x180081e94  jz      short loc_180081ECB
0x180081e96  mov     r11, [r12]
0x180081e9a  xor     r10d, r10d
0x180081e9d  xor     r9d, r9d
0x180081ea0  mov     rax, r9
0x180081ea3  add     r10d, edi
0x180081ea6  shl     rax, 5
0x180081eaa  mov     r8d, [rax+r14+10h]
0x180081eaf  mov     rax, [rax+r14+8]
0x180081eb4  lea     rdx, [r8+r8*4]
0x180081eb8  mov     rcx, [rax+30h]
0x180081ebc  add     ebx, [rcx+rdx*8]
0x180081ebf  mov     [r11+r9*4], r8d
0x180081ec3  add     r9, rdi
0x180081ec6  cmp     r10d, esi
0x180081ec9  jb      short loc_180081EA0
0x180081ecb  xor     r11d, r11d
0x180081ece  mov     [r12+8], ebx
0x180081ed3  test    esi, esi
0x180081ed5  jz      short loc_180081F27
0x180081ed7  xor     r10d, r10d
0x180081eda  mov     eax, 0FFFFFFFFh
0x180081edf  mov     r9, r10
0x180081ee2  shl     r9, 5
0x180081ee6  cmp     [r9+r14+14h], eax
0x180081eeb  jz      short loc_180081F1C
0x180081eed  mov     rax, [r9+r14+8]
0x180081ef2  mov     r8, [rax+30h]
0x180081ef6  mov     eax, [r9+r14+10h]
0x180081efb  lea     rdx, [rax+rax*4]
0x180081eff  mov     eax, [r9+r14+14h]
0x180081f04  lea     rcx, [rax+rax*4]
0x180081f08  mov     eax, [r8+rcx*8]
0x180081f0c  sub     eax, [r8+rdx*8]
0x180081f10  add     eax, ebx
0x180081f12  mov     [r9+r14+18h], eax
0x180081f17  mov     eax, 0FFFFFFFFh
0x180081f1c  add     r11d, edi
0x180081f1f  add     r10, rdi
0x180081f22  cmp     r11d, esi
0x180081f25  jb      short loc_180081EDF
0x180081f27  mov     r15d, edi
0x180081f2a  cmp     [r13+0], edi
0x180081f2e  jbe     loc_180082107
0x180081f34  mov     r11d, dword ptr [rsp+98h+var_70]
0x180081f39  mov     ebp, r11d
0x180081f3c  xor     eax, eax
0x180081f3e  mov     r8d, 0FFFFFFFFh
0x180081f44  cmp     eax, esi
0x180081f46  jnb     short loc_180081F63
0x180081f48  mov     ecx, eax
0x180081f4a  shl     rcx, 5
0x180081f4e  cmp     [rcx+r14+14h], r8d
0x180081f53  jnz     short loc_180081F59
0x180081f55  add     eax, edi
0x180081f57  jmp     short loc_180081F44
0x180081f59  mov     edx, [rcx+r14+18h]
0x180081f5e  mov     r11d, eax
0x180081f61  jmp     short loc_180081F78
0x180081f63  jz      loc_180082103
0x180081f69  mov     eax, r11d
0x180081f6c  cmp     r11d, esi
0x180081f6f  jnb     short loc_180081FA3
0x180081f71  mov     edx, [rsp+98h+arg_10]
0x180081f78  mov     ecx, eax
0x180081f7a  shl     rcx, 5
0x180081f7e  cmp     [rcx+r14+14h], r8d
0x180081f83  jz      short loc_180081F94
0x180081f85  cmp     edx, [rcx+r14+18h]
0x180081f8a  jle     short loc_180081F94
0x180081f8c  mov     edx, [rcx+r14+18h]
0x180081f91  mov     r11d, eax
0x180081f94  add     eax, edi
0x180081f96  cmp     eax, esi
0x180081f98  jb      short loc_180081F78
0x180081f9a  mov     [rsp+98h+arg_10], edx
0x180081fa1  mov     ebp, edx
0x180081fa3  test    esi, esi
0x180081fa5  jz      short loc_180081FD6
0x180081fa7  mov     eax, r15d
0x180081faa  xor     r9d, r9d
0x180081fad  add     rax, rax
0x180081fb0  mov     r10, [r12+rax*8]
0x180081fb4  mov     eax, r11d
0x180081fb7  shl     rax, 5
0x180081fbb  mov     r8d, [rax+r14]
0x180081fbf  add     r8, r8
0x180081fc2  mov     rax, [r12+r8*8]
0x180081fc6  mov     ecx, [rax+r9*4]
0x180081fca  mov     [r10+r9*4], ecx
0x180081fce  add     r9d, edi
0x180081fd1  cmp     r9d, esi
0x180081fd4  jb      short loc_180081FC2
0x180081fd6  mov     r9d, r11d
0x180081fd9  mov     eax, r15d
0x180081fdc  shl     rax, 4
0x180081fe0  mov     [rsp+98h+var_50], rax
0x180081fe5  lea     rbx, ds:0[r9*4]
0x180081fed  shl     r9, 5
0x180081ff1  mov     rax, [rax+r12]
0x180081ff5  mov     [rsp+98h+var_70], rax
0x180081ffa  mov     rcx, [r9+r14+8]
0x180081fff  mov     eax, [rbx+rax]
0x180082002  lea     edx, [rax+1]
0x180082005  cmp     edx, [rcx+28h]
0x180082008  jnb     short loc_180082038
0x18008200a  mov     r8, [rcx+30h]
0x18008200e  mov     r12, rcx
0x180082011  lea     rcx, [rax+rax*4]
0x180082015  mov     r10d, [r8+rcx*8+10h]
0x18008201a  lea     rcx, [rdx+rdx*4]
0x18008201e  cmp     [r8+rcx*8+10h], r10d
0x180082023  jz      short loc_18008202E
0x180082025  add     edx, edi
0x180082027  cmp     edx, [r12+28h]
0x18008202c  jb      short loc_18008201A
0x18008202e  mov     r12, [rsp+98h+var_68]
0x180082033  mov     rcx, [r9+r14+8]
0x180082038  mov     rax, [rsp+98h+var_70]
0x18008203d  add     [r9+r14], edi
0x180082041  mov     r10d, [r9+r14]
  ... truncated ...
```
