# jsonLookupStep

- ea: `0x1800754f0`
- end: `0x180075a95`
- name: `jsonLookupStep`
- size: `1445`
- prototype: `__int64 __fastcall(__int64, unsigned int, char *, int)`
- caller_count: `9`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180073360`
- `0x180073cf0`
- `0x180074260`
- `0x180074758`
- `0x180074920`
- `0x180075144`
- `0x1800754f0`
- `0x180076860`
- `0x180078580`

## callees

- `0x18006910e`
- `0x180072aa4`
- `0x180073548`
- `0x1800737a4`
- `0x180073928`
- `0x180073cf0`
- `0x180075380`
- `0x1800754f0`
- `0x1800764cc`
- `0x1800789f8`
- `0x180078a58`
- `0x1800997fc`
- `0x180099814`

## pseudocode

```c
__int64 __fastcall jsonLookupStep(__int64 a1, unsigned int a2, char *a3, int a4)
{
  char v4; // al
  __int64 v5; // r14
  int v9; // eax
  __int64 v10; // r8
  char v11; // al
  _BYTE *v13; // rsi
  __int64 v14; // rbx
  unsigned int v15; // r12d
  __int64 v16; // r12
  __int64 v17; // r15
  unsigned int v18; // eax
  int v19; // eax
  unsigned int v20; // eax
  __int64 v21; // r12
  const void *v22; // r9
  BOOL v23; // eax
  int v24; // eax
  unsigned __int8 v25; // cl
  int v26; // eax
  int v27; // r15d
  int v28; // eax
  __int64 v29; // r9
  char *v30; // r8
  __int64 v31; // rdx
  __int64 v32; // rcx
  unsigned int v33; // ebx
  unsigned int v34; // r12d
  unsigned int v35; // esi
  int v36; // ebx
  int v37; // eax
  __int64 v38; // rdx
  int v39; // ebx
  unsigned int v40; // r15d
  __int64 v41; // r13
  __int64 v42; // rax
  __int64 v43; // rcx
  unsigned int v44; // edx
  __int64 v45; // rax
  unsigned int v46; // ebx
  unsigned int v47; // r12d
  int v48; // eax
  int v49; // [rsp+30h] [rbp-A9h] BYREF
  unsigned int v50; // [rsp+34h] [rbp-A5h]
  BOOL v51; // [rsp+38h] [rbp-A1h]
  unsigned int v52[5]; // [rsp+3Ch] [rbp-9Dh]
  void *v53; // [rsp+50h] [rbp-89h] BYREF
  size_t v54; // [rsp+58h] [rbp-81h]
  void *Src; // [rsp+A0h] [rbp-39h] BYREF
  size_t Size; // [rsp+A8h] [rbp-31h]
  __int64 v57; // [rsp+B8h] [rbp-21h]
  char v58; // [rsp+CFh] [rbp-Ah]
  char v59; // [rsp+150h] [rbp+77h]

  v4 = *a3;
  v5 = a2;
  v49 = 0;
  if ( !v4 )
  {
    if ( *(_BYTE *)(a1 + 51) && (unsigned int)jsonBlobMakeEditable(a1, *(_DWORD *)(a1 + 56)) )
    {
      v9 = jsonbPayloadSize((__int64 *)a1, v5, (unsigned int *)&v49);
      v10 = (unsigned int)(v9 + v49);
      v11 = *(_BYTE *)(a1 + 51);
      if ( v11 == 1 )
      {
        if ( a4 )
        {
          v10 = (unsigned int)(v5 + v10 - a4);
          LODWORD(v5) = a4;
        }
        jsonBlobEdit(a1, v5, v10, 0, 0);
      }
      else if ( v11 != 3 )
      {
        jsonBlobEdit(a1, v5, v10, *(const void **)(a1 + 64), *(_DWORD *)(a1 + 56));
      }
    }
    *(_DWORD *)(a1 + 60) = a4;
    return (unsigned int)v5;
  }
  if ( v4 == 46 )
  {
    v13 = a3 + 1;
    if ( a3[1] == 34 )
    {
      LODWORD(v14) = 1;
      *(_QWORD *)&v52[1] = a3 + 2;
      if ( a3[2] )
      {
        do
        {
          if ( v13[(unsigned int)v14] == 34 )
            break;
          if ( v13[(unsigned int)v14] == 92 && v13[(unsigned int)(v14 + 1)] )
            LODWORD(v14) = v14 + 1;
          v14 = (unsigned int)(v14 + 1);
        }
        while ( v13[v14] );
      }
      if ( v13[(unsigned int)v14] )
      {
        v15 = v14 - 1;
        LODWORD(v14) = v14 + 1;
        v52[0] = v15;
        v51 = memchr_0(a3 + 2, 92, v15) == 0;
        goto LABEL_27;
      }
    }
    else
    {
      LODWORD(v14) = 0;
      if ( a3[1] )
      {
        do
        {
          if ( v13[(unsigned int)v14] == 46 )
            break;
          if ( v13[(unsigned int)v14] == 91 )
            break;
          v14 = (unsigned int)(v14 + 1);
        }
        while ( v13[v14] );
        if ( (_DWORD)v14 )
        {
          v51 = 1;
          *(_QWORD *)&v52[1] = a3 + 1;
          v52[0] = v14;
LABEL_27:
          v16 = *(_QWORD *)a1;
          if ( (*(_BYTE *)(v5 + *(_QWORD *)a1) & 0xF) == 0xC )
          {
            v17 = (unsigned int)v5 + (unsigned int)jsonbPayloadSize((__int64 *)a1, v5, (unsigned int *)&v49);
            v18 = v17 + v49;
            v50 = v17 + v49;
            while ( (unsigned int)v17 < v18 )
            {
              v59 = *(_BYTE *)(v17 + v16) & 0xF;
              if ( (unsigned __int8)(v59 - 7) > 3u )
                return 0xFFFFFFFFLL;
              v19 = jsonbPayloadSize((__int64 *)a1, v17, (unsigned int *)&v49);
              if ( !v19 )
                return 0xFFFFFFFFLL;
              v20 = v17 + v19;
              v21 = v20 + v49;
              if ( (unsigned int)v21 >= v50 )
                return 0xFFFFFFFFLL;
              v22 = (const void *)(*(_QWORD *)a1 + v20);
              v23 = v59 == 7 || v59 == 10;
              v24 = jsonLabelCompare(*(const void **)&v52[1], v52[0], v51, v22, v49, v23);
              v25 = *(_BYTE *)(v21 + *(_QWORD *)a1) & 0xF;
              if ( v24 )
              {
                if ( v25 <= 0xCu )
                {
                  v28 = jsonbPayloadSize((__int64 *)a1, v21, (unsigned int *)&v49);
                  if ( v28 )
                  {
                    if ( v49 + (int)v21 + v28 <= v50 )
                    {
                      v29 = (unsigned int)v17;
                      v30 = &v13[(unsigned int)v14];
                      v31 = (unsigned int)v21;
                      v32 = a1;
                      goto LABEL_45;
                    }
                  }
                }
                return 0xFFFFFFFFLL;
              }
              if ( v25 > 0xCu )
                return 0xFFFFFFFFLL;
              v26 = jsonbPayloadSize((__int64 *)a1, v21, (unsigned int *)&v49);
              if ( !v26 )
                return 0xFFFFFFFFLL;
              v27 = v21 + v26;
              v16 = *(_QWORD *)a1;
              v17 = (unsigned int)(v49 + v27);
              v18 = v50;
            }
            if ( (unsigned int)v17 > v18 )
              return 0xFFFFFFFFLL;
            if ( *(_BYTE *)(a1 + 51) >= 3u )
            {
              memset_0(&v53, 0, 0x48u);
              memset_0(&Src, 0, 0x48u);
              v34 = v52[0];
              v57 = *(_QWORD *)(a1 + 24);
              jsonBlobAppendNode((__int64 *)&Src, v51 + 9, v52[0], 0);
              *(_BYTE *)(a1 + 47) |= v58;
              v35 = jsonCreateEditSubstructure(a1, &v53, &v13[(unsigned int)v14]);
              if ( v35 < 0xFFFFFFFD )
              {
                if ( (unsigned int)jsonBlobMakeEditable(a1, v34 + v54 + Size) )
                {
                  jsonBlobEdit(a1, v17, 0, 0, v34 + Size + v54);
                  if ( !*(_BYTE *)(a1 + 47) )
                  {
                    memcpy_0((void *)(*(_QWORD *)a1 + (unsigned int)v17), Src, (unsigned int)Size);
                    v36 = v17 + Size;
                    memcpy_0((void *)(*(_QWORD *)a1 + (unsigned int)(v17 + Size)), *(const void **)&v52[1], v34);
                    memcpy_0((void *)(*(_QWORD *)a1 + v36 + v34), v53, (unsigned int)v54);
                    if ( *(_DWORD *)(a1 + 52) )
                      jsonAfterEditSizeAdjust((_DWORD *)a1, (unsigned int)v5);
                  }
                }
              }
              jsonParseReset(&v53);
              jsonParseReset(&Src);
              return v35;
            }
          }
          return 4294967294LL;
        }
      }
    }
    return 4294967293LL;
  }
  if ( v4 != 91 )
    return 4294967293LL;
  if ( (*(_BYTE *)(a2 + *(_QWORD *)a1) & 0xF) != 0xB )
    return 4294967294LL;
  v37 = jsonbPayloadSize((__int64 *)a1, a2, (unsigned int *)&v49);
  v38 = (unsigned __int8)a3[1];
  v39 = v37;
  v40 = 0;
  LODWORD(v41) = 1;
  if ( (*((_BYTE *)&qword_18009E630 + v38) & 4) != 0 )
  {
    do
    {
      v42 = (unsigned int)v41;
      v41 = (unsigned int)(v41 + 1);
      v40 = a3[v42] + 2 * (5 * v40 - 24);
      v43 = (unsigned __int8)a3[v41];
    }
    while ( (*((_BYTE *)&qword_18009E630 + v43) & 4) != 0 );
    if ( (unsigned int)v41 >= 2 && (_BYTE)v43 == 93 )
      goto LABEL_71;
  }
  if ( (_BYTE)v38 != 35 )
    return 4294967293LL;
  v40 = jsonbArrayCount(a1, (unsigned int)v5);
  LODWORD(v41) = 2;
  if ( a3[2] == 45 && (*((_BYTE *)&qword_18009E630 + (unsigned __int8)a3[3]) & 4) != 0 )
  {
    v44 = 0;
    LODWORD(v41) = 3;
    do
    {
      v45 = (unsigned int)v41;
      v41 = (unsigned int)(v41 + 1);
      v44 = a3[v45] + 2 * (5 * v44 - 24);
    }
    while ( (*((_BYTE *)&qword_18009E630 + (unsigned __int8)a3[v41]) & 4) != 0 );
    if ( v44 <= v40 )
    {
      v40 -= v44;
      goto LABEL_70;
    }
    return 4294967294LL;
  }
LABEL_70:
  if ( a3[(unsigned int)v41] != 93 )
    return 4294967293LL;
LABEL_71:
  v46 = v5 + v39;
  v47 = v46 + v49;
  while ( v46 < v47 )
  {
    v31 = v46;
    v32 = a1;
    if ( !v40 )
    {
      v30 = &a3[(unsigned int)(v41 + 1)];
      v29 = 0;
LABEL_45:
      v33 = jsonLookupStep(v32, v31, v30, v29);
      if ( *(_DWORD *)(a1 + 52) )
        jsonAfterEditSizeAdjust((_DWORD *)a1, (unsigned int)v5);
      return v33;
    }
    v48 = jsonbPayloadSize((__int64 *)a1, v46, (unsigned int *)&v49);
    if ( !v48 )
      return 0xFFFFFFFFLL;
    --v40;
    v46 += v49 + v48;
  }
  if ( v46 > v47 )
    return 0xFFFFFFFFLL;
  if ( v40 || *(_BYTE *)(a1 + 51) < 3u )
    return 4294967294LL;
  memset_0(&v53, 0, 0x48u);
  v35 = jsonCreateEditSubstructure(a1, &v53, &a3[(unsigned int)(v41 + 1)]);
  if ( v35 < 0xFFFFFFFD && (unsigned int)jsonBlobMakeEditable(a1, v54) )
    jsonBlobEdit(a1, v46, 0, v53, v54);
  jsonParseReset(&v53);
  if ( *(_DWORD *)(a1 + 52) )
    jsonAfterEditSizeAdjust((_DWORD *)a1, (unsigned int)v5);
  return v35;
}

```

## disassembly

```asm
0x1800754f0  push    rbp
0x1800754f2  push    rbx
0x1800754f3  push    rsi
0x1800754f4  push    rdi
0x1800754f5  push    r12
0x1800754f7  push    r13
0x1800754f9  push    r14
0x1800754fb  push    r15
0x1800754fd  lea     rbp, [rsp-1Fh]
0x180075502  sub     rsp, 0F8h
0x180075509  mov     al, [r8]
0x18007550c  xor     r12d, r12d
0x18007550f  mov     r14d, edx
0x180075512  mov     ebx, r9d
0x180075515  mov     [rsp+130h+var_100], r12d
0x18007551a  mov     rsi, r8
0x18007551d  mov     rdi, rcx
0x180075520  test    al, al
0x180075522  jnz     short loc_180075591
0x180075524  cmp     [rcx+33h], r12b
0x180075528  jz      short loc_180075586
0x18007552a  mov     edx, [rcx+38h]
0x18007552d  call    jsonBlobMakeEditable
0x180075532  test    eax, eax
0x180075534  jz      short loc_180075586
0x180075536  lea     r8, [rsp+130h+var_100]
0x18007553b  mov     edx, r14d
0x18007553e  mov     rcx, rdi
0x180075541  call    jsonbPayloadSize
0x180075546  mov     r8d, [rsp+130h+var_100]
0x18007554b  add     r8d, eax
0x18007554e  mov     al, [rdi+33h]
0x180075551  cmp     al, 1
0x180075553  jnz     short loc_18007556C
0x180075555  test    ebx, ebx
0x180075557  jz      short loc_180075562
0x180075559  sub     r8d, ebx
0x18007555c  add     r8d, r14d
0x18007555f  mov     r14d, ebx
0x180075562  mov     [rsp+130h+var_110], r12d
0x180075567  xor     r9d, r9d
0x18007556a  jmp     short loc_18007557B
0x18007556c  cmp     al, 3
0x18007556e  jz      short loc_180075586
0x180075570  mov     eax, [rdi+38h]
0x180075573  mov     r9, [rdi+40h]
0x180075577  mov     [rsp+130h+var_110], eax
0x18007557b  mov     edx, r14d
0x18007557e  mov     rcx, rdi
0x180075581  call    jsonBlobEdit
0x180075586  mov     [rdi+3Ch], ebx
0x180075589  mov     eax, r14d
0x18007558c  jmp     loc_180075A81
0x180075591  cmp     al, 2Eh ; '.'
0x180075593  jnz     loc_1800758BB
0x180075599  inc     rsi
0x18007559c  mov     al, [rsi]
0x18007559e  cmp     al, 22h ; '"'
0x1800755a0  jnz     short loc_180075607
0x1800755a2  lea     r15, [rsi+1]
0x1800755a6  mov     ebx, 1
0x1800755ab  mov     qword ptr [rsp+130h+var_F4+4], r15
0x1800755b0  lea     edx, [rbx+5Bh]; Val
0x1800755b3  cmp     [r15], r12b
0x1800755b6  jz      short loc_1800755D7
0x1800755b8  mov     eax, ebx
0x1800755ba  cmp     byte ptr [rax+rsi], 22h ; '"'
0x1800755be  jz      short loc_1800755D7
0x1800755c0  cmp     [rax+rsi], dl
0x1800755c3  jnz     short loc_1800755CF
0x1800755c5  lea     ecx, [rbx+1]
0x1800755c8  cmp     [rcx+rsi], r12b
0x1800755cc  cmovnz  ebx, ecx
0x1800755cf  inc     ebx
0x1800755d1  cmp     [rbx+rsi], r12b
0x1800755d5  jnz     short loc_1800755B8
0x1800755d7  mov     eax, ebx
0x1800755d9  cmp     [rax+rsi], r12b
0x1800755dd  jz      loc_180075A7C
0x1800755e3  lea     r12d, [rbx-1]
0x1800755e7  mov     rcx, r15; Buf
0x1800755ea  mov     r8d, r12d; MaxCount
0x1800755ed  inc     ebx
0x1800755ef  mov     [rsp+130h+var_F4], r12d
0x1800755f4  call    memchr_0
0x1800755f9  xor     edx, edx
0x1800755fb  test    rax, rax
0x1800755fe  setz    dl
0x180075601  mov     [rsp+130h+var_F8], edx
0x180075605  jmp     short loc_180075641
0x180075607  mov     ebx, r12d
0x18007560a  test    al, al
0x18007560c  jz      loc_180075A7C
0x180075612  mov     eax, ebx
0x180075614  cmp     byte ptr [rax+rsi], 2Eh ; '.'
0x180075618  jz      short loc_180075628
0x18007561a  cmp     byte ptr [rax+rsi], 5Bh ; '['
0x18007561e  jz      short loc_180075628
0x180075620  inc     ebx
0x180075622  cmp     [rbx+rsi], r12b
0x180075626  jnz     short loc_180075612
0x180075628  test    ebx, ebx
0x18007562a  jz      loc_180075A7C
0x180075630  mov     [rsp+130h+var_F8], 1
0x180075638  mov     qword ptr [rsp+130h+var_F4+4], rsi
0x18007563d  mov     [rsp+130h+var_F4], ebx
0x180075641  mov     r12, [rdi]
0x180075644  mov     r13b, 0Fh
0x180075647  mov     cl, [r14+r12]
0x18007564b  and     cl, r13b
0x18007564e  cmp     cl, 0Ch
0x180075651  jnz     loc_180075A75
0x180075657  lea     r8, [rsp+130h+var_100]
0x18007565c  mov     edx, r14d
0x18007565f  mov     rcx, rdi
0x180075662  call    jsonbPayloadSize
0x180075667  lea     r15d, [r14+rax]
0x18007566b  mov     eax, [rsp+130h+var_100]
0x18007566f  add     eax, r15d
0x180075672  mov     [rsp+130h+var_FC], eax
0x180075676  cmp     r15d, eax
0x180075679  jnb     loc_18007579A
0x18007567f  mov     al, [r15+r12]
0x180075683  and     al, r13b
0x180075686  mov     [rbp+57h+arg_10], al
0x180075689  sub     al, 7
0x18007568b  cmp     al, 3
0x18007568d  ja      loc_1800759E9
0x180075693  lea     r8, [rsp+130h+var_100]
0x180075698  mov     edx, r15d
0x18007569b  mov     rcx, rdi
0x18007569e  call    jsonbPayloadSize
0x1800756a3  test    eax, eax
0x1800756a5  jz      loc_1800759E9
0x1800756ab  mov     edx, [rsp+130h+var_100]
0x1800756af  add     eax, r15d
0x1800756b2  lea     r12d, [rax+rdx]
0x1800756b6  cmp     r12d, [rsp+130h+var_FC]
0x1800756bb  jnb     loc_1800759E9
0x1800756c1  mov     r9d, eax
0x1800756c4  add     r9, [rdi]
0x1800756c7  mov     al, [rbp+57h+arg_10]
0x1800756ca  cmp     al, 7
0x1800756cc  jz      short loc_1800756D6
0x1800756ce  cmp     al, 0Ah
0x1800756d0  jz      short loc_1800756D6
0x1800756d2  xor     eax, eax
0x1800756d4  jmp     short loc_1800756DB
0x1800756d6  mov     eax, 1
0x1800756db  mov     r8d, [rsp+130h+var_F8]
0x1800756e0  mov     rcx, qword ptr [rsp+130h+var_F4+4]
0x1800756e5  mov     [rsp+130h+var_108], eax
0x1800756e9  mov     [rsp+130h+var_110], edx
0x1800756ed  mov     edx, [rsp+130h+var_F4]
0x1800756f1  call    jsonLabelCompare
0x1800756f6  mov     rcx, [rdi]
0x1800756f9  mov     cl, [r12+rcx]
0x1800756fd  and     cl, r13b
0x180075700  test    eax, eax
0x180075702  jnz     short loc_18007573A
0x180075704  cmp     cl, 0Ch
0x180075707  ja      loc_1800759E9
0x18007570d  lea     r8, [rsp+130h+var_100]
0x180075712  mov     edx, r12d
0x180075715  mov     rcx, rdi
0x180075718  call    jsonbPayloadSize
0x18007571d  test    eax, eax
0x18007571f  jz      loc_1800759E9
0x180075725  lea     r15d, [r12+rax]
0x180075729  mov     r12, [rdi]
0x18007572c  add     r15d, [rsp+130h+var_100]
0x180075731  mov     eax, [rsp+130h+var_FC]
0x180075735  jmp     loc_180075676
0x18007573a  cmp     cl, 0Ch
0x18007573d  ja      loc_1800759E9
0x180075743  lea     r8, [rsp+130h+var_100]
0x180075748  mov     edx, r12d
0x18007574b  mov     rcx, rdi
0x18007574e  call    jsonbPayloadSize
0x180075753  test    eax, eax
0x180075755  jz      loc_1800759E9
0x18007575b  add     eax, r12d
0x18007575e  add     eax, [rsp+130h+var_100]
0x180075762  cmp     eax, [rsp+130h+var_FC]
0x180075766  ja      loc_1800759E9
0x18007576c  mov     r8d, ebx
0x18007576f  mov     r9d, r15d
0x180075772  add     r8, rsi
0x180075775  mov     edx, r12d
0x180075778  mov     rcx, rdi
0x18007577b  call    jsonLookupStep
0x180075780  cmp     dword ptr [rdi+34h], 0
0x180075784  mov     ebx, eax
0x180075786  jz      short loc_180075793
0x180075788  mov     edx, r14d
0x18007578b  mov     rcx, rdi
0x18007578e  call    jsonAfterEditSizeAdjust
0x180075793  mov     eax, ebx
0x180075795  jmp     loc_180075A81
0x18007579a  ja      loc_1800759E9
0x1800757a0  cmp     byte ptr [rdi+33h], 3
0x1800757a4  jb      loc_180075A75
0x1800757aa  mov     r12d, 48h ; 'H'
0x1800757b0  lea     rcx, [rsp+130h+var_E0]; void *
0x1800757b5  mov     r8d, r12d; Size
0x1800757b8  xor     edx, edx; Val
0x1800757ba  call    memset_0
0x1800757bf  mov     r8d, r12d; Size
0x1800757c2  lea     rcx, [rbp+57h+Src]; void *
0x1800757c6  xor     edx, edx; Val
0x1800757c8  call    memset_0
0x1800757cd  mov     edx, [rsp+130h+var_F8]
0x1800757d1  lea     rcx, [rbp+57h+Src]
0x1800757d5  mov     rax, [rdi+18h]
0x1800757d9  add     dl, 9
0x1800757dc  mov     r12d, [rsp+130h+var_F4]
0x1800757e1  xor     r9d, r9d
0x1800757e4  mov     r8d, r12d
0x1800757e7  mov     [rbp+57h+var_78], rax
0x1800757eb  call    jsonBlobAppendNode
0x1800757f0  mov     al, [rbp+57h+var_61]
0x1800757f3  lea     rdx, [rsp+130h+var_E0]
0x1800757f8  or      [rdi+2Fh], al
0x1800757fb  mov     rcx, rdi
0x1800757fe  mov     r8d, ebx
0x180075801  add     r8, rsi
0x180075804  call    jsonCreateEditSubstructure
0x180075809  mov     esi, eax
0x18007580b  cmp     eax, 0FFFFFFFDh
0x18007580e  jnb     loc_1800758A1
0x180075814  mov     edx, dword ptr [rbp+57h+Size]
0x180075817  mov     rcx, rdi
0x18007581a  add     edx, dword ptr [rsp+130h+var_D8]
0x18007581e  add     edx, r12d
0x180075821  call    jsonBlobMakeEditable
0x180075826  test    eax, eax
0x180075828  jz      short loc_1800758A1
0x18007582a  mov     edx, dword ptr [rsp+130h+var_D8]
0x18007582e  xor     r9d, r9d
0x180075831  add     edx, dword ptr [rbp+57h+Size]
0x180075834  xor     r8d, r8d
0x180075837  add     edx, r12d
0x18007583a  mov     rcx, rdi
0x18007583d  mov     [rsp+130h+var_110], edx
0x180075841  mov     edx, r15d
0x180075844  call    jsonBlobEdit
0x180075849  cmp     byte ptr [rdi+2Fh], 0
0x18007584d  jnz     short loc_1800758A1
0x18007584f  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x180075853  mov     rdx, [rbp+57h+Src]; Src
0x180075857  mov     ecx, r15d
0x18007585a  add     rcx, [rdi]; void *
0x18007585d  call    memcpy_0
0x180075862  mov     ebx, dword ptr [rbp+57h+Size]
0x180075865  mov     r8d, r12d; Size
0x180075868  mov     rdx, qword ptr [rsp+130h+var_F4+4]; Src
0x18007586d  add     ebx, r15d
0x180075870  mov     ecx, ebx
0x180075872  add     rcx, [rdi]; void *
0x180075875  call    memcpy_0
0x18007587a  mov     r8d, dword ptr [rsp+130h+var_D8]; Size
0x18007587f  lea     ecx, [rbx+r12]
0x180075883  add     rcx, [rdi]; void *
0x180075886  mov     rdx, [rsp+130h+var_E0]; Src
0x18007588b  call    memcpy_0
0x180075890  cmp     dword ptr [rdi+34h], 0
0x180075894  jz      short loc_1800758A1
0x180075896  mov     edx, r14d
0x180075899  mov     rcx, rdi
0x18007589c  call    jsonAfterEditSizeAdjust
0x1800758a1  lea     rcx, [rsp+130h+var_E0]
0x1800758a6  call    jsonParseReset
0x1800758ab  lea     rcx, [rbp+57h+Src]
0x1800758af  call    jsonParseReset
0x1800758b4  mov     eax, esi
0x1800758b6  jmp     loc_180075A81
0x1800758bb  cmp     al, 5Bh ; '['
0x1800758bd  jnz     loc_180075A7C
0x1800758c3  mov     rax, [rcx]
0x1800758c6  mov     dl, [r14+rax]
0x1800758ca  and     dl, 0Fh
0x1800758cd  cmp     dl, 0Bh
0x1800758d0  jnz     loc_180075A75
0x1800758d6  lea     r8, [rsp+130h+var_100]
0x1800758db  mov     edx, r14d
0x1800758de  call    jsonbPayloadSize
0x1800758e3  movzx   edx, byte ptr [rsi+1]
0x1800758e7  lea     r8, qword_18009E630
0x1800758ee  mov     ebx, eax
0x1800758f0  mov     r15d, r12d
0x1800758f3  mov     r13d, 1
0x1800758f9  test    byte ptr [rdx+r8], 4
0x1800758fe  jz      short loc_18007592E
0x180075900  mov     eax, r13d
0x180075903  lea     r15d, [r15+r15*4]
0x180075907  inc     r13d
0x18007590a  lea     r15d, [r15-18h]
0x18007590e  movsx   ecx, byte ptr [rax+rsi]
0x180075912  lea     r15d, [rcx+r15*2]
0x180075916  movzx   ecx, byte ptr [r13+rsi+0]
  ... truncated ...
```
