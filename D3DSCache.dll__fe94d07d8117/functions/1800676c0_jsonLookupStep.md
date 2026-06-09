# jsonLookupStep

- ea: `0x1800676c0`
- end: `0x180067c40`
- name: `jsonLookupStep`
- size: `1408`
- prototype: ``
- caller_count: `9`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800655c0`
- `0x180065ed0`
- `0x180066440`
- `0x180066938`
- `0x180066b00`
- `0x180067314`
- `0x1800676c0`
- `0x180068a00`
- `0x18006a710`

## callees

- `0x180045374`
- `0x180064cfc`
- `0x1800657a8`
- `0x180065a04`
- `0x180065b88`
- `0x180065ed0`
- `0x180067550`
- `0x1800676c0`
- `0x18006866c`
- `0x18006abd8`
- `0x18006ac38`
- `0x1800a6cf0`
- `0x1800a6d08`

## pseudocode

```c
__int64 __fastcall jsonLookupStep(__int64 *a1, unsigned int a2, char *a3, int a4)
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
  __int64 *v32; // rcx
  unsigned int v33; // ebx
  __int64 v34; // rdx
  unsigned int v35; // r12d
  unsigned int v36; // esi
  int v37; // ebx
  int v38; // eax
  __int64 v39; // rdx
  int v40; // esi
  unsigned int v41; // r15d
  __int64 v42; // r13
  __int64 v43; // rax
  __int64 v44; // rcx
  unsigned int v45; // edx
  __int64 v46; // rax
  unsigned int v47; // esi
  unsigned int v48; // r12d
  int v49; // eax
  int v50; // [rsp+30h] [rbp-A9h] BYREF
  unsigned int v51; // [rsp+34h] [rbp-A5h]
  BOOL v52; // [rsp+38h] [rbp-A1h]
  _DWORD v53[5]; // [rsp+3Ch] [rbp-9Dh]
  void *v54; // [rsp+50h] [rbp-89h] BYREF
  size_t v55; // [rsp+58h] [rbp-81h]
  void *Src; // [rsp+A0h] [rbp-39h] BYREF
  size_t Size; // [rsp+A8h] [rbp-31h]
  __int64 v58; // [rsp+B8h] [rbp-21h]
  char v59; // [rsp+CFh] [rbp-Ah]
  char v60; // [rsp+150h] [rbp+77h]

  v4 = *a3;
  v5 = a2;
  v50 = 0;
  if ( v4 )
  {
    if ( v4 == 46 )
    {
      v13 = a3 + 1;
      if ( a3[1] == 34 )
      {
        LODWORD(v14) = 1;
        *(_QWORD *)&v53[1] = a3 + 2;
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
          v53[0] = v14 - 1;
          LODWORD(v14) = v14 + 1;
          v52 = memchr_0(v13 + 1, 92, v15) == 0;
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
            v52 = 1;
            *(_QWORD *)&v53[1] = a3 + 1;
            v53[0] = v14;
LABEL_24:
            v16 = *a1;
            if ( (*(_BYTE *)(v5 + *a1) & 0xF) == 0xC )
            {
              v17 = (unsigned int)v5 + (unsigned int)jsonbPayloadSize(a1, (unsigned int)v5, &v50);
              v18 = v17 + v50;
              v51 = v17 + v50;
              while ( (unsigned int)v17 < v18 )
              {
                v60 = *(_BYTE *)(v17 + v16) & 0xF;
                if ( (unsigned __int8)(v60 - 7) > 3u )
                  return 0xFFFFFFFFLL;
                v19 = jsonbPayloadSize(a1, (unsigned int)v17, &v50);
                if ( !v19 )
                  return 0xFFFFFFFFLL;
                v20 = v17 + v19;
                v21 = v20 + v50;
                if ( (unsigned int)v21 >= v51 )
                  return 0xFFFFFFFFLL;
                v22 = *a1 + v20;
                v23 = v60 == 7 || v60 == 10;
                v24 = jsonLabelCompare(*(_QWORD *)&v53[1], v53[0], v52, v22, v50, v23);
                v25 = *(_BYTE *)(v21 + *a1) & 0xF;
                if ( v24 )
                {
                  if ( v25 <= 0xCu )
                  {
                    v28 = jsonbPayloadSize(a1, (unsigned int)v21, &v50);
                    if ( v28 )
                    {
                      if ( v50 + (int)v21 + v28 <= v51 )
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
                v26 = jsonbPayloadSize(a1, (unsigned int)v21, &v50);
                if ( !v26 )
                  return 0xFFFFFFFFLL;
                v27 = v21 + v26;
                v16 = *a1;
                v17 = (unsigned int)(v50 + v27);
                v18 = v51;
              }
              if ( (unsigned int)v17 > v18 )
                return 0xFFFFFFFFLL;
              if ( *((_BYTE *)a1 + 51) >= 3u )
              {
                memset_0(&v54, 0, 0x48u);
                memset_0(&Src, 0, 0x48u);
                v34 = v52;
                LOBYTE(v34) = v52 + 9;
                v35 = v53[0];
                v58 = a1[3];
                jsonBlobAppendNode(&Src, v34, v53[0], 0);
                *((_BYTE *)a1 + 47) |= v59;
                v36 = jsonCreateEditSubstructure(a1, &v54, &v13[(unsigned int)v14]);
                if ( v36 < 0xFFFFFFFD )
                {
                  if ( (unsigned int)jsonBlobMakeEditable(a1, v35 + (_DWORD)v55 + (_DWORD)Size) )
                  {
                    jsonBlobEdit(a1, (unsigned int)v17, 0, 0, v35 + Size + v55);
                    if ( !*((_BYTE *)a1 + 47) )
                    {
                      memcpy_0((void *)(*a1 + (unsigned int)v17), Src, (unsigned int)Size);
                      v37 = v17 + Size;
                      memcpy_0((void *)(*a1 + (unsigned int)(v17 + Size)), *(const void **)&v53[1], v35);
                      memcpy_0((void *)(*a1 + v37 + v35), v54, (unsigned int)v55);
                      if ( *((_DWORD *)a1 + 13) )
                        jsonAfterEditSizeAdjust(a1, (unsigned int)v5);
                    }
                  }
                }
                jsonParseReset(&v54);
                jsonParseReset(&Src);
                return v36;
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
    if ( (*(_BYTE *)(a2 + *a1) & 0xF) == 0xB )
    {
      v38 = jsonbPayloadSize(a1, a2, &v50);
      v39 = (unsigned __int8)a3[1];
      v40 = v38;
      v41 = 0;
      LODWORD(v42) = 1;
      if ( (*((_BYTE *)&qword_1800ADE90 + v39) & 4) != 0 )
      {
        do
        {
          v43 = (unsigned int)v42;
          v42 = (unsigned int)(v42 + 1);
          v41 = a3[v43] + 2 * (5 * v41 - 24);
          v44 = (unsigned __int8)a3[v42];
        }
        while ( (*((_BYTE *)&qword_1800ADE90 + v44) & 4) != 0 );
        if ( (unsigned int)v42 >= 2 && (_BYTE)v44 == 93 )
          goto LABEL_68;
      }
      if ( (_BYTE)v39 != 35 )
        return 4294967293LL;
      v41 = jsonbArrayCount(a1, (unsigned int)v5);
      LODWORD(v42) = 2;
      if ( a3[2] != 45 || (*((_BYTE *)&qword_1800ADE90 + (unsigned __int8)a3[3]) & 4) == 0 )
      {
LABEL_67:
        if ( a3[(unsigned int)v42] != 93 )
          return 4294967293LL;
LABEL_68:
        v47 = v5 + v40;
        v48 = v47 + v50;
        while ( v47 < v48 )
        {
          v31 = v47;
          v32 = a1;
          if ( !v41 )
          {
            v30 = &a3[(unsigned int)(v42 + 1)];
            v29 = 0;
LABEL_42:
            v33 = jsonLookupStep(v32, v31, v30, v29);
            goto LABEL_43;
          }
          v49 = jsonbPayloadSize(a1, v47, &v50);
          if ( !v49 )
            return 0xFFFFFFFFLL;
          --v41;
          v47 += v50 + v49;
        }
        if ( v47 > v48 )
          return 0xFFFFFFFFLL;
        if ( !v41 && *((_BYTE *)a1 + 51) >= 3u )
        {
          memset_0(&v54, 0, 0x48u);
          v33 = jsonCreateEditSubstructure(a1, &v54, &a3[(unsigned int)(v42 + 1)]);
          if ( v33 < 0xFFFFFFFD && (unsigned int)jsonBlobMakeEditable(a1, (unsigned int)v55) )
            jsonBlobEdit(a1, v47, 0, v54, v55);
          jsonParseReset(&v54);
LABEL_43:
          if ( *((_DWORD *)a1 + 13) )
            jsonAfterEditSizeAdjust(a1, (unsigned int)v5);
          return v33;
        }
        return 4294967294LL;
      }
      v45 = 0;
      LODWORD(v42) = 3;
      do
      {
        v46 = (unsigned int)v42;
        v42 = (unsigned int)(v42 + 1);
        v45 = a3[v46] + 2 * (5 * v45 - 24);
      }
      while ( (*((_BYTE *)&qword_1800ADE90 + (unsigned __int8)a3[v42]) & 4) != 0 );
      if ( v45 <= v41 )
      {
        v41 -= v45;
        goto LABEL_67;
      }
    }
    return 4294967294LL;
  }
  if ( *((_BYTE *)a1 + 51) && (unsigned int)jsonBlobMakeEditable(a1, *((unsigned int *)a1 + 14)) )
  {
    v9 = jsonbPayloadSize(a1, (unsigned int)v5, &v50);
    v10 = (unsigned int)(v9 + v50);
    v11 = *((_BYTE *)a1 + 51);
    if ( v11 == 1 )
    {
      if ( a4 )
      {
        v10 = (unsigned int)(v5 + v10 - a4);
        LODWORD(v5) = a4;
      }
      jsonBlobEdit(a1, (unsigned int)v5, v10, 0, 0);
    }
    else if ( v11 != 3 )
    {
      jsonBlobEdit(a1, (unsigned int)v5, v10, a1[8], *((_DWORD *)a1 + 14));
    }
  }
  *((_DWORD *)a1 + 15) = a4;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800676c0  push    rbp
0x1800676c2  push    rbx
0x1800676c3  push    rsi
0x1800676c4  push    rdi
0x1800676c5  push    r12
0x1800676c7  push    r13
0x1800676c9  push    r14
0x1800676cb  push    r15
0x1800676cd  lea     rbp, [rsp-1Fh]
0x1800676d2  sub     rsp, 0F8h
0x1800676d9  mov     al, [r8]
0x1800676dc  xor     r12d, r12d
0x1800676df  mov     r14d, edx
0x1800676e2  mov     esi, r9d
0x1800676e5  mov     [rsp+130h+var_100], r12d
0x1800676ea  mov     rbx, r8
0x1800676ed  mov     rdi, rcx
0x1800676f0  test    al, al
0x1800676f2  jnz     short loc_180067761
0x1800676f4  cmp     [rcx+33h], r12b
0x1800676f8  jz      short loc_180067756
0x1800676fa  mov     edx, [rcx+38h]
0x1800676fd  call    jsonBlobMakeEditable
0x180067702  test    eax, eax
0x180067704  jz      short loc_180067756
0x180067706  lea     r8, [rsp+130h+var_100]
0x18006770b  mov     edx, r14d
0x18006770e  mov     rcx, rdi
0x180067711  call    jsonbPayloadSize
0x180067716  mov     r8d, [rsp+130h+var_100]
0x18006771b  add     r8d, eax
0x18006771e  mov     al, [rdi+33h]
0x180067721  cmp     al, 1
0x180067723  jnz     short loc_18006773C
0x180067725  test    esi, esi
0x180067727  jz      short loc_180067732
0x180067729  sub     r8d, esi
0x18006772c  add     r8d, r14d
0x18006772f  mov     r14d, esi
0x180067732  mov     [rsp+130h+var_110], r12d
0x180067737  xor     r9d, r9d
0x18006773a  jmp     short loc_18006774B
0x18006773c  cmp     al, 3
0x18006773e  jz      short loc_180067756
0x180067740  mov     eax, [rdi+38h]
0x180067743  mov     r9, [rdi+40h]
0x180067747  mov     [rsp+130h+var_110], eax
0x18006774b  mov     edx, r14d
0x18006774e  mov     rcx, rdi
0x180067751  call    jsonBlobEdit
0x180067756  mov     [rdi+3Ch], esi
0x180067759  mov     eax, r14d
0x18006775c  jmp     loc_180067C2C
0x180067761  cmp     al, 2Eh ; '.'
0x180067763  jnz     loc_180067A7E
0x180067769  inc     rbx
0x18006776c  mov     al, [rbx]
0x18006776e  cmp     al, 22h ; '"'
0x180067770  jnz     short loc_1800677CA
0x180067772  lea     r15, [rbx+1]
0x180067776  mov     esi, 1
0x18006777b  mov     qword ptr [rsp+130h+var_F4+4], r15
0x180067780  cmp     [r15], r12b
0x180067783  jz      short loc_180067795
0x180067785  mov     eax, esi
0x180067787  cmp     byte ptr [rax+rbx], 22h ; '"'
0x18006778b  jz      short loc_180067795
0x18006778d  inc     esi
0x18006778f  cmp     [rsi+rbx], r12b
0x180067793  jnz     short loc_180067785
0x180067795  mov     eax, esi
0x180067797  cmp     [rax+rbx], r12b
0x18006779b  jz      loc_180067C27
0x1800677a1  lea     r12d, [rsi-1]
0x1800677a5  mov     edx, 5Ch ; '\'; Val
0x1800677aa  mov     r8d, r12d; MaxCount
0x1800677ad  mov     rcx, r15; Buf
0x1800677b0  mov     [rsp+130h+var_F4], r12d
0x1800677b5  inc     esi
0x1800677b7  call    memchr_0
0x1800677bc  xor     edx, edx
0x1800677be  test    rax, rax
0x1800677c1  setz    dl
0x1800677c4  mov     [rsp+130h+var_F8], edx
0x1800677c8  jmp     short loc_180067804
0x1800677ca  mov     esi, r12d
0x1800677cd  test    al, al
0x1800677cf  jz      loc_180067C27
0x1800677d5  mov     eax, esi
0x1800677d7  cmp     byte ptr [rax+rbx], 2Eh ; '.'
0x1800677db  jz      short loc_1800677EB
0x1800677dd  cmp     byte ptr [rax+rbx], 5Bh ; '['
0x1800677e1  jz      short loc_1800677EB
0x1800677e3  inc     esi
0x1800677e5  cmp     [rsi+rbx], r12b
0x1800677e9  jnz     short loc_1800677D5
0x1800677eb  test    esi, esi
0x1800677ed  jz      loc_180067C27
0x1800677f3  mov     [rsp+130h+var_F8], 1
0x1800677fb  mov     qword ptr [rsp+130h+var_F4+4], rbx
0x180067800  mov     [rsp+130h+var_F4], esi
0x180067804  mov     r12, [rdi]
0x180067807  mov     r13b, 0Fh
0x18006780a  mov     cl, [r14+r12]
0x18006780e  and     cl, r13b
0x180067811  cmp     cl, 0Ch
0x180067814  jnz     loc_180067C20
0x18006781a  lea     r8, [rsp+130h+var_100]
0x18006781f  mov     edx, r14d
0x180067822  mov     rcx, rdi
0x180067825  call    jsonbPayloadSize
0x18006782a  lea     r15d, [r14+rax]
0x18006782e  mov     eax, [rsp+130h+var_100]
0x180067832  add     eax, r15d
0x180067835  mov     [rsp+130h+var_FC], eax
0x180067839  cmp     r15d, eax
0x18006783c  jnb     loc_18006795D
0x180067842  mov     al, [r15+r12]
0x180067846  and     al, r13b
0x180067849  mov     [rbp+57h+arg_10], al
0x18006784c  sub     al, 7
0x18006784e  cmp     al, 3
0x180067850  ja      loc_180067BAC
0x180067856  lea     r8, [rsp+130h+var_100]
0x18006785b  mov     edx, r15d
0x18006785e  mov     rcx, rdi
0x180067861  call    jsonbPayloadSize
0x180067866  test    eax, eax
0x180067868  jz      loc_180067BAC
0x18006786e  mov     edx, [rsp+130h+var_100]
0x180067872  add     eax, r15d
0x180067875  lea     r12d, [rax+rdx]
0x180067879  cmp     r12d, [rsp+130h+var_FC]
0x18006787e  jnb     loc_180067BAC
0x180067884  mov     r9d, eax
0x180067887  add     r9, [rdi]
0x18006788a  mov     al, [rbp+57h+arg_10]
0x18006788d  cmp     al, 7
0x18006788f  jz      short loc_180067899
0x180067891  cmp     al, 0Ah
0x180067893  jz      short loc_180067899
0x180067895  xor     eax, eax
0x180067897  jmp     short loc_18006789E
0x180067899  mov     eax, 1
0x18006789e  mov     r8d, [rsp+130h+var_F8]
0x1800678a3  mov     rcx, qword ptr [rsp+130h+var_F4+4]
0x1800678a8  mov     [rsp+130h+var_108], eax
0x1800678ac  mov     [rsp+130h+var_110], edx
0x1800678b0  mov     edx, [rsp+130h+var_F4]
0x1800678b4  call    jsonLabelCompare
0x1800678b9  mov     rcx, [rdi]
0x1800678bc  mov     cl, [r12+rcx]
0x1800678c0  and     cl, r13b
0x1800678c3  test    eax, eax
0x1800678c5  jnz     short loc_1800678FD
0x1800678c7  cmp     cl, 0Ch
0x1800678ca  ja      loc_180067BAC
0x1800678d0  lea     r8, [rsp+130h+var_100]
0x1800678d5  mov     edx, r12d
0x1800678d8  mov     rcx, rdi
0x1800678db  call    jsonbPayloadSize
0x1800678e0  test    eax, eax
0x1800678e2  jz      loc_180067BAC
0x1800678e8  lea     r15d, [r12+rax]
0x1800678ec  mov     r12, [rdi]
0x1800678ef  add     r15d, [rsp+130h+var_100]
0x1800678f4  mov     eax, [rsp+130h+var_FC]
0x1800678f8  jmp     loc_180067839
0x1800678fd  cmp     cl, 0Ch
0x180067900  ja      loc_180067BAC
0x180067906  lea     r8, [rsp+130h+var_100]
0x18006790b  mov     edx, r12d
0x18006790e  mov     rcx, rdi
0x180067911  call    jsonbPayloadSize
0x180067916  test    eax, eax
0x180067918  jz      loc_180067BAC
0x18006791e  add     eax, r12d
0x180067921  add     eax, [rsp+130h+var_100]
0x180067925  cmp     eax, [rsp+130h+var_FC]
0x180067929  ja      loc_180067BAC
0x18006792f  mov     r8d, esi
0x180067932  mov     r9d, r15d
0x180067935  add     r8, rbx
0x180067938  mov     edx, r12d
0x18006793b  mov     rcx, rdi
0x18006793e  call    jsonLookupStep
0x180067943  mov     ebx, eax
0x180067945  cmp     dword ptr [rdi+34h], 0
0x180067949  jz      short loc_180067956
0x18006794b  mov     edx, r14d
0x18006794e  mov     rcx, rdi
0x180067951  call    jsonAfterEditSizeAdjust
0x180067956  mov     eax, ebx
0x180067958  jmp     loc_180067C2C
0x18006795d  ja      loc_180067BAC
0x180067963  cmp     byte ptr [rdi+33h], 3
0x180067967  jb      loc_180067C20
0x18006796d  mov     r12d, 48h ; 'H'
0x180067973  lea     rcx, [rsp+130h+var_E0]; void *
0x180067978  mov     r8d, r12d; Size
0x18006797b  xor     edx, edx; Val
0x18006797d  call    memset_0
0x180067982  mov     r8d, r12d; Size
0x180067985  lea     rcx, [rbp+57h+Src]; void *
0x180067989  xor     edx, edx; Val
0x18006798b  call    memset_0
0x180067990  mov     edx, [rsp+130h+var_F8]
0x180067994  lea     rcx, [rbp+57h+Src]
0x180067998  mov     rax, [rdi+18h]
0x18006799c  add     dl, 9
0x18006799f  mov     r12d, [rsp+130h+var_F4]
0x1800679a4  xor     r9d, r9d
0x1800679a7  mov     r8d, r12d
0x1800679aa  mov     [rbp+57h+var_78], rax
0x1800679ae  call    jsonBlobAppendNode
0x1800679b3  mov     al, [rbp+57h+var_61]
0x1800679b6  lea     rdx, [rsp+130h+var_E0]
0x1800679bb  or      [rdi+2Fh], al
0x1800679be  mov     rcx, rdi
0x1800679c1  mov     r8d, esi
0x1800679c4  add     r8, rbx
0x1800679c7  call    jsonCreateEditSubstructure
0x1800679cc  mov     esi, eax
0x1800679ce  cmp     eax, 0FFFFFFFDh
0x1800679d1  jnb     loc_180067A64
0x1800679d7  mov     edx, dword ptr [rbp+57h+Size]
0x1800679da  mov     rcx, rdi
0x1800679dd  add     edx, dword ptr [rsp+130h+var_D8]
0x1800679e1  add     edx, r12d
0x1800679e4  call    jsonBlobMakeEditable
0x1800679e9  test    eax, eax
0x1800679eb  jz      short loc_180067A64
0x1800679ed  mov     edx, dword ptr [rsp+130h+var_D8]
0x1800679f1  xor     r9d, r9d
0x1800679f4  add     edx, dword ptr [rbp+57h+Size]
0x1800679f7  xor     r8d, r8d
0x1800679fa  add     edx, r12d
0x1800679fd  mov     rcx, rdi
0x180067a00  mov     [rsp+130h+var_110], edx
0x180067a04  mov     edx, r15d
0x180067a07  call    jsonBlobEdit
0x180067a0c  cmp     byte ptr [rdi+2Fh], 0
0x180067a10  jnz     short loc_180067A64
0x180067a12  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x180067a16  mov     rdx, [rbp+57h+Src]; Src
0x180067a1a  mov     ecx, r15d
0x180067a1d  add     rcx, [rdi]; void *
0x180067a20  call    memcpy_0
0x180067a25  mov     ebx, dword ptr [rbp+57h+Size]
0x180067a28  mov     r8d, r12d; Size
0x180067a2b  mov     rdx, qword ptr [rsp+130h+var_F4+4]; Src
0x180067a30  add     ebx, r15d
0x180067a33  mov     ecx, ebx
0x180067a35  add     rcx, [rdi]; void *
0x180067a38  call    memcpy_0
0x180067a3d  mov     r8d, dword ptr [rsp+130h+var_D8]; Size
0x180067a42  lea     ecx, [rbx+r12]
0x180067a46  add     rcx, [rdi]; void *
0x180067a49  mov     rdx, [rsp+130h+var_E0]; Src
0x180067a4e  call    memcpy_0
0x180067a53  cmp     dword ptr [rdi+34h], 0
0x180067a57  jz      short loc_180067A64
0x180067a59  mov     edx, r14d
0x180067a5c  mov     rcx, rdi
0x180067a5f  call    jsonAfterEditSizeAdjust
0x180067a64  lea     rcx, [rsp+130h+var_E0]
0x180067a69  call    jsonParseReset
0x180067a6e  lea     rcx, [rbp+57h+Src]
0x180067a72  call    jsonParseReset
0x180067a77  mov     eax, esi
0x180067a79  jmp     loc_180067C2C
0x180067a7e  cmp     al, 5Bh ; '['
0x180067a80  jnz     loc_180067C27
0x180067a86  mov     rax, [rcx]
0x180067a89  mov     dl, [r14+rax]
0x180067a8d  and     dl, 0Fh
0x180067a90  cmp     dl, 0Bh
0x180067a93  jnz     loc_180067C20
0x180067a99  lea     r8, [rsp+130h+var_100]
0x180067a9e  mov     edx, r14d
0x180067aa1  call    jsonbPayloadSize
0x180067aa6  movzx   edx, byte ptr [rbx+1]
0x180067aaa  lea     r8, qword_1800ADE90
0x180067ab1  mov     esi, eax
0x180067ab3  mov     r15d, r12d
0x180067ab6  mov     r13d, 1
0x180067abc  test    byte ptr [rdx+r8], 4
0x180067ac1  jz      short loc_180067AF1
0x180067ac3  mov     eax, r13d
0x180067ac6  lea     r15d, [r15+r15*4]
0x180067aca  inc     r13d
0x180067acd  lea     r15d, [r15-18h]
0x180067ad1  movsx   ecx, byte ptr [rax+rbx]
0x180067ad5  lea     r15d, [rcx+r15*2]
0x180067ad9  movzx   ecx, byte ptr [r13+rbx+0]
0x180067adf  test    byte ptr [rcx+r8], 4
0x180067ae4  jnz     short loc_180067AC3
0x180067ae6  cmp     r13d, 2
0x180067aea  jb      short loc_180067AF1
0x180067aec  cmp     cl, 5Dh ; ']'
  ... truncated ...
```
