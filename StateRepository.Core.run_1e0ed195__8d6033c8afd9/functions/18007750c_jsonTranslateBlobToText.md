# jsonTranslateBlobToText

- ea: `0x18007750c`
- end: `0x180077a49`
- name: `jsonTranslateBlobToText`
- size: `1341`
- prototype: ``
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
__int64 __fastcall jsonTranslateBlobToText(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r15
  int v6; // eax
  __int64 v7; // rdx
  int v8; // r13d
  __int64 v10; // r8
  unsigned int v11; // esi
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned __int64 v17; // rbx
  _BYTE *v18; // r14
  int v19; // ebp
  unsigned int v20; // r12d
  int v21; // eax
  __int64 v22; // rdx
  const char *v23; // r8
  __int64 v24; // r8
  const char *v25; // rdx
  unsigned int v26; // ebp
  _BYTE *v27; // r14
  __int64 v28; // rax
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  char v34; // r12
  unsigned __int64 v35; // rdx
  unsigned int v36; // ebx
  unsigned int v37; // ebp
  bool v38; // cc
  char v39; // al
  __int64 v40; // rdx
  unsigned int v41; // ebx
  unsigned int v42; // ebp
  unsigned int v43; // eax
  __int64 v44; // rdx
  char *v45; // r14
  unsigned int v46; // ebx
  __int64 v47; // rbp
  __int64 v48; // rcx
  __int64 v49; // r8
  const char *v50; // rdx
  unsigned int v51; // [rsp+88h] [rbp+20h] BYREF

  v4 = (unsigned int)a2;
  v51 = 0;
  v6 = jsonbPayloadSize(a1, a2, &v51);
  v8 = v6;
  if ( !v6 )
  {
    *(_BYTE *)(a3 + 33) |= 2u;
    return (unsigned int)(*((_DWORD *)a1 + 2) + 1);
  }
  v10 = *a1;
  v11 = v51;
  v12 = *(_BYTE *)(v4 + *a1) & 0xF;
  if ( v12 > 6 )
  {
    v29 = v12 - 7;
    if ( !v29 || (v30 = v29 - 1) == 0 )
    {
      LOBYTE(v7) = 34;
      jsonAppendChar(a3, v7);
      jsonAppendRaw(a3, *a1 + (unsigned int)(v4 + v8), v11);
LABEL_120:
      LOBYTE(v35) = 34;
      goto LABEL_121;
    }
    v31 = v30 - 1;
    if ( v31 )
    {
      v32 = v31 - 1;
      if ( !v32 )
      {
        jsonAppendString(a3, v10 + (unsigned int)(v4 + v6), v51);
        return (unsigned int)v4 + v11 + v8;
      }
      v33 = v32 - 1;
      if ( !v33 )
      {
        LOBYTE(v7) = 91;
        jsonAppendChar(a3, v7);
        v41 = v4 + v8;
        v42 = v4 + v8 + v11;
        while ( v41 < v42 )
        {
          if ( *(_BYTE *)(a3 + 33) )
            goto LABEL_70;
          v43 = jsonTranslateBlobToText(a1, v41, a3);
          LOBYTE(v44) = 44;
          v41 = v43;
          jsonAppendChar(a3, v44);
        }
        if ( v41 > v42 )
          *(_BYTE *)(a3 + 33) |= 2u;
LABEL_70:
        if ( v11 )
          jsonStringTrimOneChar(a3);
        LOBYTE(v35) = 93;
        goto LABEL_121;
      }
      if ( v33 != 1 )
        goto LABEL_53;
      LOBYTE(v7) = 123;
      v34 = 0;
      jsonAppendChar(a3, v7);
      v36 = v4 + v8;
      v37 = v4 + v8 + v11;
      v38 = (int)v4 + v8 <= v37;
      if ( (int)v4 + v8 < v37 )
      {
        do
        {
          if ( *(_BYTE *)(a3 + 33) )
            break;
          v36 = jsonTranslateBlobToText(a1, v36, a3);
          v39 = v34++;
          LOBYTE(v40) = (v39 & 1) != 0 ? 44 : 58;
          jsonAppendChar(a3, v40);
        }
        while ( v36 < v37 );
        if ( (v34 & 1) != 0 )
          goto LABEL_60;
        v38 = v36 <= v37;
      }
      if ( v38 )
      {
LABEL_61:
        if ( v11 )
          jsonStringTrimOneChar(a3);
        LOBYTE(v35) = 125;
LABEL_121:
        jsonAppendChar(a3, v35);
        return (unsigned int)v4 + v11 + v8;
      }
LABEL_60:
      *(_BYTE *)(a3 + 33) |= 2u;
      goto LABEL_61;
    }
    LOBYTE(v7) = 34;
    v45 = (char *)(v10 + (unsigned int)(v4 + v6));
    v46 = v51;
    jsonAppendChar(a3, v7);
    if ( !v11 )
      goto LABEL_120;
    v35 = 0x180000000uLL;
    while ( 1 )
    {
      v47 = 0;
      do
      {
        v48 = (unsigned __int8)v45[v47];
        if ( !*((_BYTE *)qword_1800AA810 + v48) && (_BYTE)v48 != 39 )
          break;
        v47 = (unsigned int)(v47 + 1);
      }
      while ( (unsigned int)v47 < v46 );
      if ( (_DWORD)v47 )
      {
        jsonAppendRawNZ(a3, v45, (unsigned int)v47);
        if ( (unsigned int)v47 >= v46 )
          goto LABEL_120;
        v45 += (unsigned int)v47;
        v46 -= v47;
      }
      if ( *v45 == 34 )
      {
        jsonAppendRawNZ(a3, "\\\"", 2);
      }
      else
      {
        if ( *v45 > 31 )
        {
          if ( v46 < 2 )
          {
            *(_BYTE *)(a3 + 33) |= 2u;
            goto LABEL_120;
          }
          if ( v45[1] == 10 )
            goto LABEL_115;
          if ( v45[1] == 13 )
          {
            if ( v46 > 2 && v45[2] == 10 )
            {
              ++v45;
              --v46;
            }
            goto LABEL_115;
          }
          if ( v45[1] == 39 )
          {
            LOBYTE(v35) = 39;
            jsonAppendChar(a3, v35);
            goto LABEL_115;
          }
          if ( v45[1] == 48 )
          {
            v50 = "\\u0000";
          }
          else
          {
            if ( v45[1] != 118 )
            {
              if ( v45[1] == 120 )
              {
                if ( v46 < 4 )
                  goto LABEL_104;
                jsonAppendRawNZ(a3, "\\u00", 4);
                v45 += 2;
                jsonAppendRawNZ(a3, v45, 2);
LABEL_103:
                v46 -= 2;
              }
              else
              {
                if ( (unsigned __int8)v45[1] != 226 )
                {
                  v49 = 2;
                  v50 = v45;
                  goto LABEL_110;
                }
                if ( v46 >= 4 && v45[2] == (char)0x80 && (v45[3] == -88 || v45[3] == -87) )
                {
                  v45 += 2;
                  goto LABEL_103;
                }
LABEL_104:
                *(_BYTE *)(a3 + 33) |= 2u;
                v46 = 2;
              }
LABEL_115:
              v45 += 2;
              v46 -= 2;
              goto LABEL_116;
            }
            v50 = "\\u0009";
          }
          v49 = 6;
LABEL_110:
          jsonAppendRawNZ(a3, v50, v49);
          goto LABEL_115;
        }
        if ( (unsigned __int64)(*(_QWORD *)(a3 + 24) + 7LL) > *(_QWORD *)(a3 + 16)
          && (unsigned int)jsonStringGrow(a3, 7) )
        {
          goto LABEL_120;
        }
        LOBYTE(v35) = *v45;
        jsonAppendControlChar(a3, v35);
      }
      ++v45;
      --v46;
LABEL_116:
      v35 = 0x180000000uLL;
      if ( !v46 )
        goto LABEL_120;
    }
  }
  if ( v12 == 6 )
  {
    if ( v51 )
    {
      v26 = 0;
      v27 = (_BYTE *)(v10 + (unsigned int)(v4 + v6));
      if ( *v27 == 45 )
      {
        LOBYTE(v7) = 45;
        jsonAppendChar(a3, v7);
        v26 = 1;
      }
      if ( v27[v26] == 46 )
      {
        LOBYTE(v7) = 48;
        jsonAppendChar(a3, v7);
      }
      for ( ; v26 < v11; ++v26 )
      {
        LOBYTE(v7) = v27[v26];
        jsonAppendChar(a3, v7);
        if ( v27[v26] == 46 )
        {
          v28 = v26 + 1;
          if ( (_DWORD)v28 == v11 || (*((_BYTE *)&qword_18009E630 + (unsigned __int8)v27[v28]) & 4) == 0 )
          {
            LOBYTE(v7) = 48;
            jsonAppendChar(a3, v7);
          }
        }
      }
      return (unsigned int)v4 + v11 + v8;
    }
    goto LABEL_53;
  }
  if ( (*(_BYTE *)(v4 + *a1) & 0xF) == 0 )
  {
    v25 = "null";
    goto LABEL_33;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v25 = "true";
LABEL_33:
    v24 = 4;
    goto LABEL_34;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    v24 = 5;
    v25 = "false";
LABEL_34:
    jsonAppendRawNZ(a3, v25, v24);
    return (unsigned int)(v4 + 1);
  }
  v15 = v14 - 1;
  if ( v15 )
  {
    v16 = v15 - 1;
    if ( !v16 )
    {
      if ( v51 )
      {
        v17 = 0;
        v18 = (_BYTE *)(v10 + (unsigned int)(v4 + v6));
        v19 = 0;
        if ( *v18 == 45 )
        {
          LOBYTE(v7) = 45;
          jsonAppendChar(a3, v7);
          v20 = 3;
        }
        else
        {
          v21 = 2;
          if ( *v18 == 43 )
            v21 = 3;
          v20 = v21;
        }
        if ( v20 < v11 )
        {
          while ( 1 )
          {
            v22 = (unsigned __int8)v18[v20];
            if ( (*((_BYTE *)&qword_18009E630 + v22) & 8) == 0 )
              break;
            if ( v17 < 0x1000000000000000LL )
              v17 = (((_BYTE)v22 - 7 * (((char)v22 >> 6) & 1)) & 0xF) + 16 * v17;
            else
              v19 = 1;
            if ( ++v20 >= v11 )
              goto LABEL_27;
          }
          *(_BYTE *)(a3 + 33) |= 2u;
        }
LABEL_27:
        v23 = "9.0e999";
        if ( !v19 )
          v23 = "%llu";
        jsonPrintf(100, a3, v23, v17);
        return (unsigned int)v4 + v11 + v8;
      }
      goto LABEL_53;
    }
    if ( v16 != 1 )
      goto LABEL_53;
  }
  if ( !v51 )
  {
LABEL_53:
    *(_BYTE *)(a3 + 33) |= 2u;
    return (unsigned int)v4 + v11 + v8;
  }
  jsonAppendRaw(a3, v10 + (unsigned int)(v4 + v6), v51);
  return (unsigned int)v4 + v11 + v8;
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
