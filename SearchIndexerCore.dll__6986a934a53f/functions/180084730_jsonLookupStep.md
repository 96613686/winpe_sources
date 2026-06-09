# jsonLookupStep

- ea: `0x180084730`
- end: `0x180084cb0`
- name: `jsonLookupStep`
- size: `1408`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800825d0`
- `0x180082f60`
- `0x1800834b0`
- `0x1800839a8`
- `0x180083b70`
- `0x180084384`
- `0x180084730`
- `0x180085a70`
- `0x180087790`

## callees

- `0x180078968`
- `0x180081d0c`
- `0x1800827b8`
- `0x180082a14`
- `0x180082b98`
- `0x180082f60`
- `0x1800845c0`
- `0x180084730`
- `0x1800856dc`
- `0x180087c08`
- `0x180087c68`
- `0x1800af608`
- `0x1800af620`

## pseudocode

```c
__int64 __fastcall jsonLookupStep(__int64 a1, unsigned int a2, char *a3, int a4)
{
  char v4; // al
  __int64 v5; // r14
  int v9; // eax
  __int64 v10; // r8
  char v11; // al
  _BYTE *v13; // rbx
  __int64 v14; // rsi
  size_t v15; // r8
  __int64 v16; // r12
  __int64 v17; // r15
  unsigned int v18; // eax
  int v19; // eax
  unsigned int v20; // eax
  __int64 v21; // r12
  __int64 v22; // r9
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
  int v39; // esi
  unsigned int v40; // r15d
  __int64 v41; // r13
  __int64 v42; // rax
  __int64 v43; // rcx
  unsigned int v44; // edx
  __int64 v45; // rax
  unsigned int v46; // esi
  unsigned int v47; // r12d
  int v48; // eax
  unsigned int v49; // [rsp+30h] [rbp-A9h] BYREF
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
  if ( v4 )
  {
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
            v14 = (unsigned int)(v14 + 1);
          }
          while ( v13[v14] );
        }
        if ( v13[(unsigned int)v14] )
        {
          v15 = (unsigned int)(v14 - 1);
          v52[0] = v14 - 1;
          LODWORD(v14) = v14 + 1;
          v51 = memchr_0(v13 + 1, 92, v15) == 0;
          goto LABEL_24;
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
LABEL_24:
            v16 = *(_QWORD *)a1;
            if ( (*(_BYTE *)(v5 + *(_QWORD *)a1) & 0xF) == 0xC )
            {
              v17 = (unsigned int)v5 + (unsigned int)jsonbPayloadSize((__int64 *)a1, v5, &v49);
              v18 = v17 + v49;
              v50 = v17 + v49;
              while ( (unsigned int)v17 < v18 )
              {
                v59 = *(_BYTE *)(v17 + v16) & 0xF;
                if ( (unsigned __int8)(v59 - 7) > 3u )
                  return 0xFFFFFFFFLL;
                v19 = jsonbPayloadSize((__int64 *)a1, v17, &v49);
                if ( !v19 )
                  return 0xFFFFFFFFLL;
                v20 = v17 + v19;
                v21 = v20 + v49;
                if ( (unsigned int)v21 >= v50 )
                  return 0xFFFFFFFFLL;
                v22 = *(_QWORD *)a1 + v20;
                v23 = v59 == 7 || v59 == 10;
                v24 = jsonLabelCompare(*(_QWORD *)&v52[1], v52[0], v51, v22, v49, v23);
                v25 = *(_BYTE *)(v21 + *(_QWORD *)a1) & 0xF;
                if ( v24 )
                {
                  if ( v25 <= 0xCu )
                  {
                    v28 = jsonbPayloadSize((__int64 *)a1, v21, &v49);
                    if ( v28 )
                    {
                      if ( v49 + (_DWORD)v21 + v28 <= v50 )
                      {
                        v29 = (unsigned int)v17;
                        v30 = &v13[(unsigned int)v14];
                        v31 = (unsigned int)v21;
                        v32 = a1;
                        goto LABEL_42;
                      }
                    }
                  }
                  return 0xFFFFFFFFLL;
                }
                if ( v25 > 0xCu )
                  return 0xFFFFFFFFLL;
                v26 = jsonbPayloadSize((__int64 *)a1, v21, &v49);
                if ( !v26 )
                  return 0xFFFFFFFFLL;
                v27 = v21 + v26;
                v16 = *(_QWORD *)a1;
                v17 = v49 + v27;
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
    if ( (*(_BYTE *)(a2 + *(_QWORD *)a1) & 0xF) == 0xB )
    {
      v37 = jsonbPayloadSize((__int64 *)a1, a2, &v49);
      v38 = (unsigned __int8)a3[1];
      v39 = v37;
      v40 = 0;
      LODWORD(v41) = 1;
      if ( (*((_BYTE *)&qword_1800B4FF0 + v38) & 4) != 0 )
      {
        do
        {
          v42 = (unsigned int)v41;
          v41 = (unsigned int)(v41 + 1);
          v40 = a3[v42] + 2 * (5 * v40 - 24);
          v43 = (unsigned __int8)a3[v41];
        }
        while ( (*((_BYTE *)&qword_1800B4FF0 + v43) & 4) != 0 );
        if ( (unsigned int)v41 >= 2 && (_BYTE)v43 == 93 )
          goto LABEL_68;
      }
      if ( (_BYTE)v38 != 35 )
        return 4294967293LL;
      v40 = jsonbArrayCount(a1, (unsigned int)v5);
      LODWORD(v41) = 2;
      if ( a3[2] != 45 || (*((_BYTE *)&qword_1800B4FF0 + (unsigned __int8)a3[3]) & 4) == 0 )
      {
LABEL_67:
        if ( a3[(unsigned int)v41] != 93 )
          return 4294967293LL;
LABEL_68:
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
LABEL_42:
            v33 = jsonLookupStep(v32, v31, v30, v29);
            goto LABEL_43;
          }
          v48 = jsonbPayloadSize((__int64 *)a1, v46, &v49);
          if ( !v48 )
            return 0xFFFFFFFFLL;
          --v40;
          v46 += v49 + v48;
        }
        if ( v46 > v47 )
          return 0xFFFFFFFFLL;
        if ( !v40 && *(_BYTE *)(a1 + 51) >= 3u )
        {
          memset_0(&v53, 0, 0x48u);
          v33 = jsonCreateEditSubstructure(a1, &v53, &a3[(unsigned int)(v41 + 1)]);
          if ( v33 < 0xFFFFFFFD && (unsigned int)jsonBlobMakeEditable(a1, v54) )
            jsonBlobEdit(a1, v46, 0, v53, v54);
          jsonParseReset(&v53);
LABEL_43:
          if ( *(_DWORD *)(a1 + 52) )
            jsonAfterEditSizeAdjust((_DWORD *)a1, (unsigned int)v5);
          return v33;
        }
        return 4294967294LL;
      }
      v44 = 0;
      LODWORD(v41) = 3;
      do
      {
        v45 = (unsigned int)v41;
        v41 = (unsigned int)(v41 + 1);
        v44 = a3[v45] + 2 * (5 * v44 - 24);
      }
      while ( (*((_BYTE *)&qword_1800B4FF0 + (unsigned __int8)a3[v41]) & 4) != 0 );
      if ( v44 <= v40 )
      {
        v40 -= v44;
        goto LABEL_67;
      }
    }
    return 4294967294LL;
  }
  if ( *(_BYTE *)(a1 + 51) && (unsigned int)jsonBlobMakeEditable(a1, *(_DWORD *)(a1 + 56)) )
  {
    v9 = jsonbPayloadSize((__int64 *)a1, v5, &v49);
    v10 = v9 + v49;
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

```

## disassembly

```asm
0x180084730  push    rbp
0x180084732  push    rbx
0x180084733  push    rsi
0x180084734  push    rdi
0x180084735  push    r12
0x180084737  push    r13
0x180084739  push    r14
0x18008473b  push    r15
0x18008473d  lea     rbp, [rsp-1Fh]
0x180084742  sub     rsp, 0F8h
0x180084749  mov     al, [r8]
0x18008474c  xor     r12d, r12d
0x18008474f  mov     r14d, edx
0x180084752  mov     esi, r9d
0x180084755  mov     [rsp+130h+var_100], r12d
0x18008475a  mov     rbx, r8
0x18008475d  mov     rdi, rcx
0x180084760  test    al, al
0x180084762  jnz     short loc_1800847D1
0x180084764  cmp     [rcx+33h], r12b
0x180084768  jz      short loc_1800847C6
0x18008476a  mov     edx, [rcx+38h]
0x18008476d  call    jsonBlobMakeEditable
0x180084772  test    eax, eax
0x180084774  jz      short loc_1800847C6
0x180084776  lea     r8, [rsp+130h+var_100]
0x18008477b  mov     edx, r14d
0x18008477e  mov     rcx, rdi
0x180084781  call    jsonbPayloadSize
0x180084786  mov     r8d, [rsp+130h+var_100]
0x18008478b  add     r8d, eax
0x18008478e  mov     al, [rdi+33h]
0x180084791  cmp     al, 1
0x180084793  jnz     short loc_1800847AC
0x180084795  test    esi, esi
0x180084797  jz      short loc_1800847A2
0x180084799  sub     r8d, esi
0x18008479c  add     r8d, r14d
0x18008479f  mov     r14d, esi
0x1800847a2  mov     [rsp+130h+var_110], r12d
0x1800847a7  xor     r9d, r9d
0x1800847aa  jmp     short loc_1800847BB
0x1800847ac  cmp     al, 3
0x1800847ae  jz      short loc_1800847C6
0x1800847b0  mov     eax, [rdi+38h]
0x1800847b3  mov     r9, [rdi+40h]
0x1800847b7  mov     [rsp+130h+var_110], eax
0x1800847bb  mov     edx, r14d
0x1800847be  mov     rcx, rdi
0x1800847c1  call    jsonBlobEdit
0x1800847c6  mov     [rdi+3Ch], esi
0x1800847c9  mov     eax, r14d
0x1800847cc  jmp     loc_180084C9C
0x1800847d1  cmp     al, 2Eh ; '.'
0x1800847d3  jnz     loc_180084AEE
0x1800847d9  inc     rbx
0x1800847dc  mov     al, [rbx]
0x1800847de  cmp     al, 22h ; '"'
0x1800847e0  jnz     short loc_18008483A
0x1800847e2  lea     r15, [rbx+1]
0x1800847e6  mov     esi, 1
0x1800847eb  mov     qword ptr [rsp+130h+var_F4+4], r15
0x1800847f0  cmp     [r15], r12b
0x1800847f3  jz      short loc_180084805
0x1800847f5  mov     eax, esi
0x1800847f7  cmp     byte ptr [rax+rbx], 22h ; '"'
0x1800847fb  jz      short loc_180084805
0x1800847fd  inc     esi
0x1800847ff  cmp     [rsi+rbx], r12b
0x180084803  jnz     short loc_1800847F5
0x180084805  mov     eax, esi
0x180084807  cmp     [rax+rbx], r12b
0x18008480b  jz      loc_180084C97
0x180084811  lea     r12d, [rsi-1]
0x180084815  mov     edx, 5Ch ; '\'; Val
0x18008481a  mov     r8d, r12d; MaxCount
0x18008481d  mov     rcx, r15; Buf
0x180084820  mov     [rsp+130h+var_F4], r12d
0x180084825  inc     esi
0x180084827  call    memchr_0
0x18008482c  xor     edx, edx
0x18008482e  test    rax, rax
0x180084831  setz    dl
0x180084834  mov     [rsp+130h+var_F8], edx
0x180084838  jmp     short loc_180084874
0x18008483a  mov     esi, r12d
0x18008483d  test    al, al
0x18008483f  jz      loc_180084C97
0x180084845  mov     eax, esi
0x180084847  cmp     byte ptr [rax+rbx], 2Eh ; '.'
0x18008484b  jz      short loc_18008485B
0x18008484d  cmp     byte ptr [rax+rbx], 5Bh ; '['
0x180084851  jz      short loc_18008485B
0x180084853  inc     esi
0x180084855  cmp     [rsi+rbx], r12b
0x180084859  jnz     short loc_180084845
0x18008485b  test    esi, esi
0x18008485d  jz      loc_180084C97
0x180084863  mov     [rsp+130h+var_F8], 1
0x18008486b  mov     qword ptr [rsp+130h+var_F4+4], rbx
0x180084870  mov     [rsp+130h+var_F4], esi
0x180084874  mov     r12, [rdi]
0x180084877  mov     r13b, 0Fh
0x18008487a  mov     cl, [r14+r12]
0x18008487e  and     cl, r13b
0x180084881  cmp     cl, 0Ch
0x180084884  jnz     loc_180084C90
0x18008488a  lea     r8, [rsp+130h+var_100]
0x18008488f  mov     edx, r14d
0x180084892  mov     rcx, rdi
0x180084895  call    jsonbPayloadSize
0x18008489a  lea     r15d, [r14+rax]
0x18008489e  mov     eax, [rsp+130h+var_100]
0x1800848a2  add     eax, r15d
0x1800848a5  mov     [rsp+130h+var_FC], eax
0x1800848a9  cmp     r15d, eax
0x1800848ac  jnb     loc_1800849CD
0x1800848b2  mov     al, [r15+r12]
0x1800848b6  and     al, r13b
0x1800848b9  mov     [rbp+57h+arg_10], al
0x1800848bc  sub     al, 7
0x1800848be  cmp     al, 3
0x1800848c0  ja      loc_180084C1C
0x1800848c6  lea     r8, [rsp+130h+var_100]
0x1800848cb  mov     edx, r15d
0x1800848ce  mov     rcx, rdi
0x1800848d1  call    jsonbPayloadSize
0x1800848d6  test    eax, eax
0x1800848d8  jz      loc_180084C1C
0x1800848de  mov     edx, [rsp+130h+var_100]
0x1800848e2  add     eax, r15d
0x1800848e5  lea     r12d, [rax+rdx]
0x1800848e9  cmp     r12d, [rsp+130h+var_FC]
0x1800848ee  jnb     loc_180084C1C
0x1800848f4  mov     r9d, eax
0x1800848f7  add     r9, [rdi]
0x1800848fa  mov     al, [rbp+57h+arg_10]
0x1800848fd  cmp     al, 7
0x1800848ff  jz      short loc_180084909
0x180084901  cmp     al, 0Ah
0x180084903  jz      short loc_180084909
0x180084905  xor     eax, eax
0x180084907  jmp     short loc_18008490E
0x180084909  mov     eax, 1
0x18008490e  mov     r8d, [rsp+130h+var_F8]
0x180084913  mov     rcx, qword ptr [rsp+130h+var_F4+4]
0x180084918  mov     [rsp+130h+var_108], eax
0x18008491c  mov     [rsp+130h+var_110], edx
0x180084920  mov     edx, [rsp+130h+var_F4]
0x180084924  call    jsonLabelCompare
0x180084929  mov     rcx, [rdi]
0x18008492c  mov     cl, [r12+rcx]
0x180084930  and     cl, r13b
0x180084933  test    eax, eax
0x180084935  jnz     short loc_18008496D
0x180084937  cmp     cl, 0Ch
0x18008493a  ja      loc_180084C1C
0x180084940  lea     r8, [rsp+130h+var_100]
0x180084945  mov     edx, r12d
0x180084948  mov     rcx, rdi
0x18008494b  call    jsonbPayloadSize
0x180084950  test    eax, eax
0x180084952  jz      loc_180084C1C
0x180084958  lea     r15d, [r12+rax]
0x18008495c  mov     r12, [rdi]
0x18008495f  add     r15d, [rsp+130h+var_100]
0x180084964  mov     eax, [rsp+130h+var_FC]
0x180084968  jmp     loc_1800848A9
0x18008496d  cmp     cl, 0Ch
0x180084970  ja      loc_180084C1C
0x180084976  lea     r8, [rsp+130h+var_100]
0x18008497b  mov     edx, r12d
0x18008497e  mov     rcx, rdi
0x180084981  call    jsonbPayloadSize
0x180084986  test    eax, eax
0x180084988  jz      loc_180084C1C
0x18008498e  add     eax, r12d
0x180084991  add     eax, [rsp+130h+var_100]
0x180084995  cmp     eax, [rsp+130h+var_FC]
0x180084999  ja      loc_180084C1C
0x18008499f  mov     r8d, esi
0x1800849a2  mov     r9d, r15d
0x1800849a5  add     r8, rbx
0x1800849a8  mov     edx, r12d
0x1800849ab  mov     rcx, rdi
0x1800849ae  call    jsonLookupStep
0x1800849b3  mov     ebx, eax
0x1800849b5  cmp     dword ptr [rdi+34h], 0
0x1800849b9  jz      short loc_1800849C6
0x1800849bb  mov     edx, r14d
0x1800849be  mov     rcx, rdi
0x1800849c1  call    jsonAfterEditSizeAdjust
0x1800849c6  mov     eax, ebx
0x1800849c8  jmp     loc_180084C9C
0x1800849cd  ja      loc_180084C1C
0x1800849d3  cmp     byte ptr [rdi+33h], 3
0x1800849d7  jb      loc_180084C90
0x1800849dd  mov     r12d, 48h ; 'H'
0x1800849e3  lea     rcx, [rsp+130h+var_E0]; void *
0x1800849e8  mov     r8d, r12d; Size
0x1800849eb  xor     edx, edx; Val
0x1800849ed  call    memset_0
0x1800849f2  mov     r8d, r12d; Size
0x1800849f5  lea     rcx, [rbp+57h+Src]; void *
0x1800849f9  xor     edx, edx; Val
0x1800849fb  call    memset_0
0x180084a00  mov     edx, [rsp+130h+var_F8]
0x180084a04  lea     rcx, [rbp+57h+Src]
0x180084a08  mov     rax, [rdi+18h]
0x180084a0c  add     dl, 9
0x180084a0f  mov     r12d, [rsp+130h+var_F4]
0x180084a14  xor     r9d, r9d
0x180084a17  mov     r8d, r12d
0x180084a1a  mov     [rbp+57h+var_78], rax
0x180084a1e  call    jsonBlobAppendNode
0x180084a23  mov     al, [rbp+57h+var_61]
0x180084a26  lea     rdx, [rsp+130h+var_E0]
0x180084a2b  or      [rdi+2Fh], al
0x180084a2e  mov     rcx, rdi
0x180084a31  mov     r8d, esi
0x180084a34  add     r8, rbx
0x180084a37  call    jsonCreateEditSubstructure
0x180084a3c  mov     esi, eax
0x180084a3e  cmp     eax, 0FFFFFFFDh
0x180084a41  jnb     loc_180084AD4
0x180084a47  mov     edx, dword ptr [rbp+57h+Size]
0x180084a4a  mov     rcx, rdi
0x180084a4d  add     edx, dword ptr [rsp+130h+var_D8]
0x180084a51  add     edx, r12d
0x180084a54  call    jsonBlobMakeEditable
0x180084a59  test    eax, eax
0x180084a5b  jz      short loc_180084AD4
0x180084a5d  mov     edx, dword ptr [rsp+130h+var_D8]
0x180084a61  xor     r9d, r9d
0x180084a64  add     edx, dword ptr [rbp+57h+Size]
0x180084a67  xor     r8d, r8d
0x180084a6a  add     edx, r12d
0x180084a6d  mov     rcx, rdi
0x180084a70  mov     [rsp+130h+var_110], edx
0x180084a74  mov     edx, r15d
0x180084a77  call    jsonBlobEdit
0x180084a7c  cmp     byte ptr [rdi+2Fh], 0
0x180084a80  jnz     short loc_180084AD4
0x180084a82  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x180084a86  mov     rdx, [rbp+57h+Src]; Src
0x180084a8a  mov     ecx, r15d
0x180084a8d  add     rcx, [rdi]; void *
0x180084a90  call    memcpy_0
0x180084a95  mov     ebx, dword ptr [rbp+57h+Size]
0x180084a98  mov     r8d, r12d; Size
0x180084a9b  mov     rdx, qword ptr [rsp+130h+var_F4+4]; Src
0x180084aa0  add     ebx, r15d
0x180084aa3  mov     ecx, ebx
0x180084aa5  add     rcx, [rdi]; void *
0x180084aa8  call    memcpy_0
0x180084aad  mov     r8d, dword ptr [rsp+130h+var_D8]; Size
0x180084ab2  lea     ecx, [rbx+r12]
0x180084ab6  add     rcx, [rdi]; void *
0x180084ab9  mov     rdx, [rsp+130h+var_E0]; Src
0x180084abe  call    memcpy_0
0x180084ac3  cmp     dword ptr [rdi+34h], 0
0x180084ac7  jz      short loc_180084AD4
0x180084ac9  mov     edx, r14d
0x180084acc  mov     rcx, rdi
0x180084acf  call    jsonAfterEditSizeAdjust
0x180084ad4  lea     rcx, [rsp+130h+var_E0]
0x180084ad9  call    jsonParseReset
0x180084ade  lea     rcx, [rbp+57h+Src]
0x180084ae2  call    jsonParseReset
0x180084ae7  mov     eax, esi
0x180084ae9  jmp     loc_180084C9C
0x180084aee  cmp     al, 5Bh ; '['
0x180084af0  jnz     loc_180084C97
0x180084af6  mov     rax, [rcx]
0x180084af9  mov     dl, [r14+rax]
0x180084afd  and     dl, 0Fh
0x180084b00  cmp     dl, 0Bh
0x180084b03  jnz     loc_180084C90
0x180084b09  lea     r8, [rsp+130h+var_100]
0x180084b0e  mov     edx, r14d
0x180084b11  call    jsonbPayloadSize
0x180084b16  movzx   edx, byte ptr [rbx+1]
0x180084b1a  lea     r8, qword_1800B4FF0
0x180084b21  mov     esi, eax
0x180084b23  mov     r15d, r12d
0x180084b26  mov     r13d, 1
0x180084b2c  test    byte ptr [rdx+r8], 4
0x180084b31  jz      short loc_180084B61
0x180084b33  mov     eax, r13d
0x180084b36  lea     r15d, [r15+r15*4]
0x180084b3a  inc     r13d
0x180084b3d  lea     r15d, [r15-18h]
0x180084b41  movsx   ecx, byte ptr [rax+rbx]
0x180084b45  lea     r15d, [rcx+r15*2]
0x180084b49  movzx   ecx, byte ptr [r13+rbx+0]
0x180084b4f  test    byte ptr [rcx+r8], 4
0x180084b54  jnz     short loc_180084B33
0x180084b56  cmp     r13d, 2
0x180084b5a  jb      short loc_180084B61
0x180084b5c  cmp     cl, 5Dh ; ']'
  ... truncated ...
```
