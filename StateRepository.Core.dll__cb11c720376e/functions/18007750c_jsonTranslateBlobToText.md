# jsonTranslateBlobToText

- ea: `0x18007750c`
- end: `0x180077a49`
- name: `jsonTranslateBlobToText`
- size: `1341`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `6`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180072da4`
- `0x180074920`
- `0x180076d64`
- `0x180077008`
- `0x180077360`
- `0x18007750c`

## callees

- `0x180072b08`
- `0x180072b6c`
- `0x180072cd8`
- `0x180072d28`
- `0x180072f10`
- `0x18007672c`
- `0x1800771e0`
- `0x18007734c`
- `0x18007750c`
- `0x180078a58`

## pseudocode

```c
__int64 __fastcall jsonTranslateBlobToText(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v4; // r15
  int v6; // eax
  int v7; // r13d
  __int64 v9; // r8
  unsigned int v10; // esi
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned __int64 v16; // rbx
  _BYTE *v17; // r14
  int v18; // ebp
  unsigned int v19; // r12d
  int v20; // eax
  __int64 v21; // rdx
  const char *v22; // r8
  unsigned int v23; // r8d
  const char *v24; // rdx
  unsigned int v25; // ebp
  _BYTE *v26; // r14
  __int64 v27; // rax
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  char v33; // r12
  unsigned int v34; // ebx
  unsigned int v35; // ebp
  bool v36; // cc
  char v37; // al
  char v38; // dl
  unsigned int v39; // ebx
  unsigned int v40; // ebp
  char *v41; // r14
  unsigned int v42; // ebx
  __int64 v43; // rbp
  __int64 v44; // rcx
  unsigned int v45; // r8d
  const char *v46; // rdx
  unsigned int v47; // [rsp+88h] [rbp+20h] BYREF

  v4 = a2;
  v47 = 0;
  v6 = jsonbPayloadSize((__int64 *)a1, a2, &v47);
  v7 = v6;
  if ( !v6 )
  {
    *(_BYTE *)(a3 + 33) |= 2u;
    return (unsigned int)(*(_DWORD *)(a1 + 8) + 1);
  }
  v9 = *(_QWORD *)a1;
  v10 = v47;
  v11 = *(_BYTE *)(v4 + *(_QWORD *)a1) & 0xF;
  if ( v11 > 6 )
  {
    v28 = v11 - 7;
    if ( !v28 || (v29 = v28 - 1) == 0 )
    {
      jsonAppendChar((_QWORD *)a3, 34);
      jsonAppendRaw((_QWORD *)a3, (const void *)(*(_QWORD *)a1 + (unsigned int)(v4 + v7)), v10);
LABEL_119:
      v38 = 34;
      goto LABEL_120;
    }
    v30 = v29 - 1;
    if ( v30 )
    {
      v31 = v30 - 1;
      if ( !v31 )
      {
        jsonAppendString((_QWORD *)a3, (unsigned __int8 *)(v9 + (unsigned int)(v4 + v6)), v47);
        return (unsigned int)v4 + v10 + v7;
      }
      v32 = v31 - 1;
      if ( !v32 )
      {
        jsonAppendChar((_QWORD *)a3, 91);
        v39 = v4 + v7;
        v40 = v4 + v7 + v10;
        while ( v39 < v40 )
        {
          if ( *(_BYTE *)(a3 + 33) )
            goto LABEL_70;
          v39 = jsonTranslateBlobToText(a1, v39, a3);
          jsonAppendChar((_QWORD *)a3, 44);
        }
        if ( v39 > v40 )
          *(_BYTE *)(a3 + 33) |= 2u;
LABEL_70:
        if ( v10 )
          jsonStringTrimOneChar(a3);
        v38 = 93;
        goto LABEL_120;
      }
      if ( v32 != 1 )
        goto LABEL_53;
      v33 = 0;
      jsonAppendChar((_QWORD *)a3, 123);
      v34 = v4 + v7;
      v35 = v4 + v7 + v10;
      v36 = (int)v4 + v7 <= v35;
      if ( (int)v4 + v7 < v35 )
      {
        do
        {
          if ( *(_BYTE *)(a3 + 33) )
            break;
          v34 = jsonTranslateBlobToText(a1, v34, a3);
          v37 = v33++;
          jsonAppendChar((_QWORD *)a3, (v37 & 1) != 0 ? 44 : 58);
        }
        while ( v34 < v35 );
        if ( (v33 & 1) != 0 )
          goto LABEL_60;
        v36 = v34 <= v35;
      }
      if ( v36 )
      {
LABEL_61:
        if ( v10 )
          jsonStringTrimOneChar(a3);
        v38 = 125;
LABEL_120:
        jsonAppendChar((_QWORD *)a3, v38);
        return (unsigned int)v4 + v10 + v7;
      }
LABEL_60:
      *(_BYTE *)(a3 + 33) |= 2u;
      goto LABEL_61;
    }
    v41 = (char *)(v9 + (unsigned int)(v4 + v6));
    v42 = v47;
    jsonAppendChar((_QWORD *)a3, 34);
    if ( !v10 )
      goto LABEL_119;
    while ( 1 )
    {
      v43 = 0;
      do
      {
        v44 = (unsigned __int8)v41[v43];
        if ( !*((_BYTE *)qword_1800AA810 + v44) && (_BYTE)v44 != 39 )
          break;
        v43 = (unsigned int)(v43 + 1);
      }
      while ( (unsigned int)v43 < v42 );
      if ( (_DWORD)v43 )
      {
        jsonAppendRawNZ((_QWORD *)a3, v41, v43);
        if ( (unsigned int)v43 >= v42 )
          goto LABEL_119;
        v41 += (unsigned int)v43;
        v42 -= v43;
      }
      if ( *v41 == 34 )
      {
        jsonAppendRawNZ((_QWORD *)a3, "\\\"", 2u);
      }
      else
      {
        if ( *v41 > 31 )
        {
          if ( v42 < 2 )
          {
            *(_BYTE *)(a3 + 33) |= 2u;
            goto LABEL_119;
          }
          if ( v41[1] == 10 )
            goto LABEL_114;
          if ( v41[1] == 13 )
          {
            if ( v42 > 2 && v41[2] == 10 )
            {
              ++v41;
              --v42;
            }
            goto LABEL_114;
          }
          if ( v41[1] == 39 )
          {
            jsonAppendChar((_QWORD *)a3, 39);
            goto LABEL_114;
          }
          if ( v41[1] == 48 )
          {
            v46 = "\\u0000";
          }
          else
          {
            if ( v41[1] != 118 )
            {
              if ( v41[1] == 120 )
              {
                if ( v42 < 4 )
                  goto LABEL_103;
                jsonAppendRawNZ((_QWORD *)a3, "\\u00", 4u);
                v41 += 2;
                jsonAppendRawNZ((_QWORD *)a3, v41, 2u);
LABEL_102:
                v42 -= 2;
              }
              else
              {
                if ( (unsigned __int8)v41[1] != 226 )
                {
                  v45 = 2;
                  v46 = v41;
                  goto LABEL_109;
                }
                if ( v42 >= 4 && v41[2] == (char)0x80 && (v41[3] == -88 || v41[3] == -87) )
                {
                  v41 += 2;
                  goto LABEL_102;
                }
LABEL_103:
                *(_BYTE *)(a3 + 33) |= 2u;
                v42 = 2;
              }
LABEL_114:
              v41 += 2;
              v42 -= 2;
              goto LABEL_115;
            }
            v46 = "\\u0009";
          }
          v45 = 6;
LABEL_109:
          jsonAppendRawNZ((_QWORD *)a3, v46, v45);
          goto LABEL_114;
        }
        if ( (unsigned __int64)(*(_QWORD *)(a3 + 24) + 7LL) > *(_QWORD *)(a3 + 16)
          && (unsigned int)jsonStringGrow(a3, 7u) )
        {
          goto LABEL_119;
        }
        jsonAppendControlChar(a3, *v41);
      }
      ++v41;
      --v42;
LABEL_115:
      if ( !v42 )
        goto LABEL_119;
    }
  }
  if ( v11 == 6 )
  {
    if ( v47 )
    {
      v25 = 0;
      v26 = (_BYTE *)(v9 + (unsigned int)(v4 + v6));
      if ( *v26 == 45 )
      {
        jsonAppendChar((_QWORD *)a3, 45);
        v25 = 1;
      }
      if ( v26[v25] == 46 )
        jsonAppendChar((_QWORD *)a3, 48);
      for ( ; v25 < v10; ++v25 )
      {
        jsonAppendChar((_QWORD *)a3, v26[v25]);
        if ( v26[v25] == 46 )
        {
          v27 = v25 + 1;
          if ( (_DWORD)v27 == v10 || (*((_BYTE *)&qword_18009E630 + (unsigned __int8)v26[v27]) & 4) == 0 )
            jsonAppendChar((_QWORD *)a3, 48);
        }
      }
      return (unsigned int)v4 + v10 + v7;
    }
    goto LABEL_53;
  }
  if ( (*(_BYTE *)(v4 + *(_QWORD *)a1) & 0xF) == 0 )
  {
    v24 = "null";
    goto LABEL_33;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    v24 = "true";
LABEL_33:
    v23 = 4;
    goto LABEL_34;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v23 = 5;
    v24 = "false";
LABEL_34:
    jsonAppendRawNZ((_QWORD *)a3, v24, v23);
    return (unsigned int)(v4 + 1);
  }
  v14 = v13 - 1;
  if ( v14 )
  {
    v15 = v14 - 1;
    if ( !v15 )
    {
      if ( v47 )
      {
        v16 = 0;
        v17 = (_BYTE *)(v9 + (unsigned int)(v4 + v6));
        v18 = 0;
        if ( *v17 == 45 )
        {
          jsonAppendChar((_QWORD *)a3, 45);
          v19 = 3;
        }
        else
        {
          v20 = 2;
          if ( *v17 == 43 )
            v20 = 3;
          v19 = v20;
        }
        if ( v19 < v10 )
        {
          while ( 1 )
          {
            v21 = (unsigned __int8)v17[v19];
            if ( (*((_BYTE *)&qword_18009E630 + v21) & 8) == 0 )
              break;
            if ( v16 < 0x1000000000000000LL )
              v16 = (((_BYTE)v21 - 7 * (((char)v21 >> 6) & 1)) & 0xF) + 16 * v16;
            else
              v18 = 1;
            if ( ++v19 >= v10 )
              goto LABEL_27;
          }
          *(_BYTE *)(a3 + 33) |= 2u;
        }
LABEL_27:
        v22 = "9.0e999";
        if ( !v18 )
          v22 = "%llu";
        jsonPrintf(0x64u, (_QWORD *)a3, v22, v16);
        return (unsigned int)v4 + v10 + v7;
      }
      goto LABEL_53;
    }
    if ( v15 != 1 )
      goto LABEL_53;
  }
  if ( !v47 )
  {
LABEL_53:
    *(_BYTE *)(a3 + 33) |= 2u;
    return (unsigned int)v4 + v10 + v7;
  }
  jsonAppendRaw((_QWORD *)a3, (const void *)(v9 + (unsigned int)(v4 + v6)), v47);
  return (unsigned int)v4 + v10 + v7;
}

```

## disassembly

```asm
0x18007750c  mov     rax, rsp
0x18007750f  push    rbx
0x180077510  push    rbp
0x180077511  push    rsi
0x180077512  push    rdi
0x180077513  push    r12
0x180077515  push    r13
0x180077517  push    r14
0x180077519  push    r15
0x18007751b  sub     rsp, 28h
0x18007751f  mov     rdi, r8
0x180077522  mov     r15d, edx
0x180077525  lea     r8, [rax+20h]
0x180077529  mov     dword ptr [rax+20h], 0
0x180077530  mov     r14, rcx
0x180077533  call    jsonbPayloadSize
0x180077538  mov     r13d, eax
0x18007753b  test    eax, eax
0x18007753d  jnz     short loc_18007754E
0x18007753f  or      byte ptr [rdi+21h], 2
0x180077543  mov     eax, [r14+8]
0x180077547  inc     eax
0x180077549  jmp     loc_180077A38
0x18007754e  mov     r8, [r14]
0x180077551  mov     esi, [rsp+68h+arg_18]
0x180077558  movzx   ecx, byte ptr [r15+r8]
0x18007755d  and     ecx, 0Fh
0x180077560  cmp     ecx, 6
0x180077563  ja      loc_180077742
0x180077569  jz      loc_1800776B9
0x18007756f  test    ecx, ecx
0x180077571  jz      loc_18007769B
0x180077577  sub     ecx, 1
0x18007757a  jz      loc_180077692
0x180077580  sub     ecx, 1
0x180077583  jz      loc_180077683
0x180077589  sub     ecx, 1
0x18007758c  jz      short loc_18007759C
0x18007758e  sub     ecx, 1
0x180077591  jz      short loc_1800775BB
0x180077593  cmp     ecx, 1
0x180077596  jnz     loc_180077770
0x18007759c  test    esi, esi
0x18007759e  jz      loc_180077770
0x1800775a4  lea     edx, [r15+rax]
0x1800775a8  mov     rcx, rdi
0x1800775ab  add     rdx, r8
0x1800775ae  mov     r8d, esi
0x1800775b1  call    jsonAppendRaw
0x1800775b6  jmp     loc_180077A31
0x1800775bb  test    esi, esi
0x1800775bd  jz      loc_180077770
0x1800775c3  lea     r14d, [r15+rax]
0x1800775c7  xor     ebx, ebx
0x1800775c9  add     r14, r8
0x1800775cc  xor     ebp, ebp
0x1800775ce  cmp     byte ptr [r14], 2Dh ; '-'
0x1800775d2  jnz     short loc_1800775E4
0x1800775d4  mov     dl, 2Dh ; '-'
0x1800775d6  mov     rcx, rdi
0x1800775d9  call    jsonAppendChar
0x1800775de  lea     r12d, [rbx+3]
0x1800775e2  jmp     short loc_1800775F8
0x1800775e4  cmp     byte ptr [r14], 2Bh ; '+'
0x1800775e8  mov     eax, 2
0x1800775ed  lea     r12d, [rax+1]
0x1800775f1  cmovz   eax, r12d
0x1800775f5  mov     r12d, eax
0x1800775f8  cmp     r12d, esi
0x1800775fb  jnb     short loc_18007765A
0x1800775fd  lea     rcx, cs:180000000h
0x180077604  mov     eax, r12d
0x180077607  movzx   edx, byte ptr [rax+r14]
0x18007760c  test    byte ptr [rdx+rcx+9E630h], 8
0x180077614  jz      short loc_180077656
0x180077616  mov     rax, 1000000000000000h
0x180077620  cmp     rbx, rax
0x180077623  jb      short loc_18007762C
0x180077625  mov     ebp, 1
0x18007762a  jmp     short loc_18007764C
0x18007762c  mov     al, dl
0x18007762e  shl     rbx, 4
0x180077632  sar     al, 6
0x180077635  and     al, 1
0x180077637  movzx   eax, al
0x18007763a  imul    ecx, eax, 7
0x18007763d  sub     dl, cl
0x18007763f  lea     rcx, cs:180000000h
0x180077646  and     edx, 0Fh
0x180077649  add     rbx, rdx
0x18007764c  inc     r12d
0x18007764f  cmp     r12d, esi
0x180077652  jb      short loc_180077604
0x180077654  jmp     short loc_18007765A
0x180077656  or      byte ptr [rdi+21h], 2
0x18007765a  test    ebp, ebp
0x18007765c  lea     rax, aLlu_0; "%llu"
0x180077663  lea     r8, a90e999; "9.0e999"
0x18007766a  mov     r9, rbx
0x18007766d  cmovz   r8, rax
0x180077671  mov     rdx, rdi
0x180077674  mov     ecx, 64h ; 'd'
0x180077679  call    jsonPrintf
0x18007767e  jmp     loc_180077A31
0x180077683  mov     r8d, 5
0x180077689  lea     rdx, aFalse; "false"
0x180077690  jmp     short loc_1800776A8
0x180077692  lea     rdx, aTrue; "true"
0x180077699  jmp     short loc_1800776A2
0x18007769b  lea     rdx, aNull_2; "null"
0x1800776a2  mov     r8d, 4
0x1800776a8  mov     rcx, rdi
0x1800776ab  call    jsonAppendRawNZ
0x1800776b0  lea     eax, [r15+1]
0x1800776b4  jmp     loc_180077A38
0x1800776b9  test    esi, esi
0x1800776bb  jz      loc_180077770
0x1800776c1  lea     r14d, [r15+rax]
0x1800776c5  xor     ebp, ebp
0x1800776c7  add     r14, r8
0x1800776ca  cmp     byte ptr [r14], 2Dh ; '-'
0x1800776ce  jnz     short loc_1800776DF
0x1800776d0  mov     dl, 2Dh ; '-'
0x1800776d2  mov     rcx, rdi
0x1800776d5  call    jsonAppendChar
0x1800776da  mov     ebp, 1
0x1800776df  mov     eax, ebp
0x1800776e1  cmp     byte ptr [rax+r14], 2Eh ; '.'
0x1800776e6  jnz     short loc_1800776F2
0x1800776e8  mov     dl, 30h ; '0'
0x1800776ea  mov     rcx, rdi
0x1800776ed  call    jsonAppendChar
0x1800776f2  cmp     ebp, esi
0x1800776f4  jnb     loc_180077A31
0x1800776fa  lea     r12, cs:180000000h
0x180077701  mov     ebx, ebp
0x180077703  mov     rcx, rdi
0x180077706  mov     dl, [rbx+r14]
0x18007770a  call    jsonAppendChar
0x18007770f  cmp     byte ptr [rbx+r14], 2Eh ; '.'
0x180077714  jnz     short loc_180077737
0x180077716  lea     eax, [rbp+1]
0x180077719  cmp     eax, esi
0x18007771b  jz      short loc_18007772D
0x18007771d  movzx   ecx, byte ptr [rax+r14]
0x180077722  test    byte ptr [rcx+r12+9E630h], 4
0x18007772b  jnz     short loc_180077737
0x18007772d  mov     dl, 30h ; '0'
0x18007772f  mov     rcx, rdi
0x180077732  call    jsonAppendChar
0x180077737  inc     ebp
0x180077739  cmp     ebp, esi
0x18007773b  jb      short loc_180077701
0x18007773d  jmp     loc_180077A31
0x180077742  sub     ecx, 7
0x180077745  jz      loc_180077A0B
0x18007774b  sub     ecx, 1
0x18007774e  jz      loc_180077A0B
0x180077754  sub     ecx, 1
0x180077757  jz      loc_18007784C
0x18007775d  sub     ecx, 1
0x180077760  jz      loc_180077835
0x180077766  sub     ecx, 1
0x180077769  jz      short loc_1800777E6
0x18007776b  cmp     ecx, 1
0x18007776e  jz      short loc_180077779
0x180077770  or      byte ptr [rdi+21h], 2
0x180077774  jmp     loc_180077A31
0x180077779  mov     dl, 7Bh ; '{'
0x18007777b  mov     rcx, rdi
0x18007777e  xor     r12d, r12d
0x180077781  call    jsonAppendChar
0x180077786  lea     ebx, [r15+r13]
0x18007778a  lea     ebp, [rbx+rsi]
0x18007778d  cmp     ebx, ebp
0x18007778f  jnb     short loc_1800777CD
0x180077791  cmp     byte ptr [rdi+21h], 0
0x180077795  jnz     short loc_1800777C5
0x180077797  mov     r8, rdi
0x18007779a  mov     edx, ebx
0x18007779c  mov     rcx, r14
0x18007779f  call    jsonTranslateBlobToText
0x1800777a4  mov     ebx, eax
0x1800777a6  mov     rcx, rdi
0x1800777a9  mov     eax, r12d
0x1800777ac  inc     r12d
0x1800777af  and     eax, 1
0x1800777b2  neg     eax
0x1800777b4  sbb     dl, dl
0x1800777b6  and     dl, 0F2h
0x1800777b9  add     dl, 3Ah ; ':'
0x1800777bc  call    jsonAppendChar
0x1800777c1  cmp     ebx, ebp
0x1800777c3  jb      short loc_180077791
0x1800777c5  test    r12b, 1
0x1800777c9  jnz     short loc_1800777CF
0x1800777cb  cmp     ebx, ebp
0x1800777cd  jbe     short loc_1800777D3
0x1800777cf  or      byte ptr [rdi+21h], 2
0x1800777d3  test    esi, esi
0x1800777d5  jz      short loc_1800777DF
0x1800777d7  mov     rcx, rdi
0x1800777da  call    jsonStringTrimOneChar
0x1800777df  mov     dl, 7Dh ; '}'
0x1800777e1  jmp     loc_180077A29
0x1800777e6  mov     dl, 5Bh ; '['
0x1800777e8  mov     rcx, rdi
0x1800777eb  call    jsonAppendChar
0x1800777f0  lea     ebx, [r15+r13]
0x1800777f4  lea     ebp, [rbx+rsi]
0x1800777f7  jmp     short loc_180077818
0x1800777f9  cmp     byte ptr [rdi+21h], 0
0x1800777fd  jnz     short loc_180077822
0x1800777ff  mov     r8, rdi
0x180077802  mov     edx, ebx
0x180077804  mov     rcx, r14
0x180077807  call    jsonTranslateBlobToText
0x18007780c  mov     dl, 2Ch ; ','
0x18007780e  mov     rcx, rdi
0x180077811  mov     ebx, eax
0x180077813  call    jsonAppendChar
0x180077818  cmp     ebx, ebp
0x18007781a  jb      short loc_1800777F9
0x18007781c  jbe     short loc_180077822
0x18007781e  or      byte ptr [rdi+21h], 2
0x180077822  test    esi, esi
0x180077824  jz      short loc_18007782E
0x180077826  mov     rcx, rdi
0x180077829  call    jsonStringTrimOneChar
0x18007782e  mov     dl, 5Dh ; ']'
0x180077830  jmp     loc_180077A29
0x180077835  lea     edx, [r15+rax]
0x180077839  mov     rcx, rdi
0x18007783c  add     rdx, r8
0x18007783f  mov     r8d, esi
0x180077842  call    jsonAppendString
0x180077847  jmp     loc_180077A31
0x18007784c  lea     r14d, [r15+rax]
0x180077850  mov     dl, 22h ; '"'
0x180077852  mov     rcx, rdi
0x180077855  add     r14, r8
0x180077858  mov     ebx, esi
0x18007785a  call    jsonAppendChar
0x18007785f  test    esi, esi
0x180077861  jz      loc_180077A27
0x180077867  mov     r12d, 3
0x18007786d  lea     rdx, cs:180000000h
0x180077874  xor     ebp, ebp
0x180077876  movzx   ecx, byte ptr [rbp+r14+0]
0x18007787c  cmp     byte ptr [rcx+rdx+0AA810h], 0
0x180077884  jnz     short loc_18007788B
0x180077886  cmp     cl, 27h ; '''
0x180077889  jnz     short loc_180077891
0x18007788b  inc     ebp
0x18007788d  cmp     ebp, ebx
0x18007788f  jb      short loc_180077876
0x180077891  test    ebp, ebp
0x180077893  jz      short loc_1800778B2
0x180077895  mov     r8d, ebp
0x180077898  mov     rdx, r14
0x18007789b  mov     rcx, rdi
0x18007789e  call    jsonAppendRawNZ
0x1800778a3  cmp     ebp, ebx
0x1800778a5  jnb     loc_180077A27
0x1800778ab  mov     eax, ebp
0x1800778ad  add     r14, rax
0x1800778b0  sub     ebx, ebp
0x1800778b2  cmp     byte ptr [r14], 22h ; '"'
0x1800778b6  jnz     short loc_1800778D7
0x1800778b8  mov     r8d, 2
0x1800778be  lea     rdx, asc_1800A61E4; "\\\""
0x1800778c5  mov     rcx, rdi
0x1800778c8  call    jsonAppendRawNZ
0x1800778cd  inc     r14
0x1800778d0  dec     ebx
0x1800778d2  jmp     loc_1800779F4
0x1800778d7  cmp     byte ptr [r14], 1Fh
0x1800778db  jg      short loc_18007790D
0x1800778dd  mov     rax, [rdi+18h]
0x1800778e1  add     rax, 7
0x1800778e5  cmp     rax, [rdi+10h]
0x1800778e9  jbe     short loc_180077900
0x1800778eb  mov     edx, 7
0x1800778f0  mov     rcx, rdi
0x1800778f3  call    jsonStringGrow
0x1800778f8  test    eax, eax
0x1800778fa  jnz     loc_180077A27
0x180077900  mov     dl, [r14]
0x180077903  mov     rcx, rdi
0x180077906  call    jsonAppendControlChar
0x18007790b  jmp     short loc_1800778CD
0x18007790d  cmp     ebx, 2
0x180077910  jb      loc_180077A05
0x180077916  movzx   ecx, byte ptr [r14+1]
0x18007791b  sub     ecx, 0Ah
0x18007791e  jz      loc_1800779ED
0x180077924  sub     ecx, r12d
0x180077927  jz      loc_1800779DC
0x18007792d  sub     ecx, 1Ah
0x180077930  jz      loc_1800779D0
  ... truncated ...
```
