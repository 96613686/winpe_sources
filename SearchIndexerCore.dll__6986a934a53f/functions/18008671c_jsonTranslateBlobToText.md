# jsonTranslateBlobToText

- ea: `0x18008671c`
- end: `0x180086c59`
- name: `jsonTranslateBlobToText`
- size: `1341`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18008200c`
- `0x180083b70`
- `0x180085f74`
- `0x180086218`
- `0x180086570`
- `0x18008671c`

## callees

- `0x180081d70`
- `0x180081dd4`
- `0x180081f40`
- `0x180081f90`
- `0x180082178`
- `0x18008593c`
- `0x1800863f0`
- `0x18008655c`
- `0x18008671c`
- `0x180087c68`

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
        if ( !*((_BYTE *)qword_1800C11D0 + v44) && (_BYTE)v44 != 39 )
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
          && (unsigned int)jsonStringGrow(a3, 7) )
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
          if ( (_DWORD)v27 == v10 || (*((_BYTE *)&qword_1800B4FF0 + (unsigned __int8)v26[v27]) & 4) == 0 )
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
            if ( (*((_BYTE *)&qword_1800B4FF0 + v21) & 8) == 0 )
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
        jsonPrintf(100, a3, v22, v16);
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
0x18008671c  mov     rax, rsp
0x18008671f  push    rbx
0x180086720  push    rbp
0x180086721  push    rsi
0x180086722  push    rdi
0x180086723  push    r12
0x180086725  push    r13
0x180086727  push    r14
0x180086729  push    r15
0x18008672b  sub     rsp, 28h
0x18008672f  mov     rdi, r8
0x180086732  mov     r15d, edx
0x180086735  lea     r8, [rax+20h]
0x180086739  mov     dword ptr [rax+20h], 0
0x180086740  mov     r14, rcx
0x180086743  call    jsonbPayloadSize
0x180086748  mov     r13d, eax
0x18008674b  test    eax, eax
0x18008674d  jnz     short loc_18008675E
0x18008674f  or      byte ptr [rdi+21h], 2
0x180086753  mov     eax, [r14+8]
0x180086757  inc     eax
0x180086759  jmp     loc_180086C48
0x18008675e  mov     r8, [r14]
0x180086761  mov     esi, [rsp+68h+arg_18]
0x180086768  movzx   ecx, byte ptr [r15+r8]
0x18008676d  and     ecx, 0Fh
0x180086770  cmp     ecx, 6
0x180086773  ja      loc_180086952
0x180086779  jz      loc_1800868C9
0x18008677f  test    ecx, ecx
0x180086781  jz      loc_1800868AB
0x180086787  sub     ecx, 1
0x18008678a  jz      loc_1800868A2
0x180086790  sub     ecx, 1
0x180086793  jz      loc_180086893
0x180086799  sub     ecx, 1
0x18008679c  jz      short loc_1800867AC
0x18008679e  sub     ecx, 1
0x1800867a1  jz      short loc_1800867CB
0x1800867a3  cmp     ecx, 1
0x1800867a6  jnz     loc_180086980
0x1800867ac  test    esi, esi
0x1800867ae  jz      loc_180086980
0x1800867b4  lea     edx, [r15+rax]
0x1800867b8  mov     rcx, rdi
0x1800867bb  add     rdx, r8
0x1800867be  mov     r8d, esi
0x1800867c1  call    jsonAppendRaw
0x1800867c6  jmp     loc_180086C41
0x1800867cb  test    esi, esi
0x1800867cd  jz      loc_180086980
0x1800867d3  lea     r14d, [r15+rax]
0x1800867d7  xor     ebx, ebx
0x1800867d9  add     r14, r8
0x1800867dc  xor     ebp, ebp
0x1800867de  cmp     byte ptr [r14], 2Dh ; '-'
0x1800867e2  jnz     short loc_1800867F4
0x1800867e4  mov     dl, 2Dh ; '-'
0x1800867e6  mov     rcx, rdi
0x1800867e9  call    jsonAppendChar
0x1800867ee  lea     r12d, [rbx+3]
0x1800867f2  jmp     short loc_180086808
0x1800867f4  cmp     byte ptr [r14], 2Bh ; '+'
0x1800867f8  mov     eax, 2
0x1800867fd  lea     r12d, [rax+1]
0x180086801  cmovz   eax, r12d
0x180086805  mov     r12d, eax
0x180086808  cmp     r12d, esi
0x18008680b  jnb     short loc_18008686A
0x18008680d  lea     rcx, __ImageBase
0x180086814  mov     eax, r12d
0x180086817  movzx   edx, byte ptr [rax+r14]
0x18008681c  test    byte ptr [rdx+rcx+0B4FF0h], 8
0x180086824  jz      short loc_180086866
0x180086826  mov     rax, 1000000000000000h
0x180086830  cmp     rbx, rax
0x180086833  jb      short loc_18008683C
0x180086835  mov     ebp, 1
0x18008683a  jmp     short loc_18008685C
0x18008683c  mov     al, dl
0x18008683e  shl     rbx, 4
0x180086842  sar     al, 6
0x180086845  and     al, 1
0x180086847  movzx   eax, al
0x18008684a  imul    ecx, eax, 7
0x18008684d  sub     dl, cl
0x18008684f  lea     rcx, __ImageBase
0x180086856  and     edx, 0Fh
0x180086859  add     rbx, rdx
0x18008685c  inc     r12d
0x18008685f  cmp     r12d, esi
0x180086862  jb      short loc_180086814
0x180086864  jmp     short loc_18008686A
0x180086866  or      byte ptr [rdi+21h], 2
0x18008686a  test    ebp, ebp
0x18008686c  lea     rax, aLlu_0; "%llu"
0x180086873  lea     r8, a90e999; "9.0e999"
0x18008687a  mov     r9, rbx
0x18008687d  cmovz   r8, rax
0x180086881  mov     rdx, rdi
0x180086884  mov     ecx, 64h ; 'd'
0x180086889  call    jsonPrintf
0x18008688e  jmp     loc_180086C41
0x180086893  mov     r8d, 5
0x180086899  lea     rdx, aFalse; "false"
0x1800868a0  jmp     short loc_1800868B8
0x1800868a2  lea     rdx, aTrue; "true"
0x1800868a9  jmp     short loc_1800868B2
0x1800868ab  lea     rdx, aNull_2; "null"
0x1800868b2  mov     r8d, 4
0x1800868b8  mov     rcx, rdi
0x1800868bb  call    jsonAppendRawNZ
0x1800868c0  lea     eax, [r15+1]
0x1800868c4  jmp     loc_180086C48
0x1800868c9  test    esi, esi
0x1800868cb  jz      loc_180086980
0x1800868d1  lea     r14d, [r15+rax]
0x1800868d5  xor     ebp, ebp
0x1800868d7  add     r14, r8
0x1800868da  cmp     byte ptr [r14], 2Dh ; '-'
0x1800868de  jnz     short loc_1800868EF
0x1800868e0  mov     dl, 2Dh ; '-'
0x1800868e2  mov     rcx, rdi
0x1800868e5  call    jsonAppendChar
0x1800868ea  mov     ebp, 1
0x1800868ef  mov     eax, ebp
0x1800868f1  cmp     byte ptr [rax+r14], 2Eh ; '.'
0x1800868f6  jnz     short loc_180086902
0x1800868f8  mov     dl, 30h ; '0'
0x1800868fa  mov     rcx, rdi
0x1800868fd  call    jsonAppendChar
0x180086902  cmp     ebp, esi
0x180086904  jnb     loc_180086C41
0x18008690a  lea     r12, __ImageBase
0x180086911  mov     ebx, ebp
0x180086913  mov     rcx, rdi
0x180086916  mov     dl, [rbx+r14]
0x18008691a  call    jsonAppendChar
0x18008691f  cmp     byte ptr [rbx+r14], 2Eh ; '.'
0x180086924  jnz     short loc_180086947
0x180086926  lea     eax, [rbp+1]
0x180086929  cmp     eax, esi
0x18008692b  jz      short loc_18008693D
0x18008692d  movzx   ecx, byte ptr [rax+r14]
0x180086932  test    byte ptr [rcx+r12+0B4FF0h], 4
0x18008693b  jnz     short loc_180086947
0x18008693d  mov     dl, 30h ; '0'
0x18008693f  mov     rcx, rdi
0x180086942  call    jsonAppendChar
0x180086947  inc     ebp
0x180086949  cmp     ebp, esi
0x18008694b  jb      short loc_180086911
0x18008694d  jmp     loc_180086C41
0x180086952  sub     ecx, 7
0x180086955  jz      loc_180086C1B
0x18008695b  sub     ecx, 1
0x18008695e  jz      loc_180086C1B
0x180086964  sub     ecx, 1
0x180086967  jz      loc_180086A5C
0x18008696d  sub     ecx, 1
0x180086970  jz      loc_180086A45
0x180086976  sub     ecx, 1
0x180086979  jz      short loc_1800869F6
0x18008697b  cmp     ecx, 1
0x18008697e  jz      short loc_180086989
0x180086980  or      byte ptr [rdi+21h], 2
0x180086984  jmp     loc_180086C41
0x180086989  mov     dl, 7Bh ; '{'
0x18008698b  mov     rcx, rdi
0x18008698e  xor     r12d, r12d
0x180086991  call    jsonAppendChar
0x180086996  lea     ebx, [r15+r13]
0x18008699a  lea     ebp, [rbx+rsi]
0x18008699d  cmp     ebx, ebp
0x18008699f  jnb     short loc_1800869DD
0x1800869a1  cmp     byte ptr [rdi+21h], 0
0x1800869a5  jnz     short loc_1800869D5
0x1800869a7  mov     r8, rdi
0x1800869aa  mov     edx, ebx
0x1800869ac  mov     rcx, r14
0x1800869af  call    jsonTranslateBlobToText
0x1800869b4  mov     ebx, eax
0x1800869b6  mov     rcx, rdi
0x1800869b9  mov     eax, r12d
0x1800869bc  inc     r12d
0x1800869bf  and     eax, 1
0x1800869c2  neg     eax
0x1800869c4  sbb     dl, dl
0x1800869c6  and     dl, 0F2h
0x1800869c9  add     dl, 3Ah ; ':'
0x1800869cc  call    jsonAppendChar
0x1800869d1  cmp     ebx, ebp
0x1800869d3  jb      short loc_1800869A1
0x1800869d5  test    r12b, 1
0x1800869d9  jnz     short loc_1800869DF
0x1800869db  cmp     ebx, ebp
0x1800869dd  jbe     short loc_1800869E3
0x1800869df  or      byte ptr [rdi+21h], 2
0x1800869e3  test    esi, esi
0x1800869e5  jz      short loc_1800869EF
0x1800869e7  mov     rcx, rdi
0x1800869ea  call    jsonStringTrimOneChar
0x1800869ef  mov     dl, 7Dh ; '}'
0x1800869f1  jmp     loc_180086C39
0x1800869f6  mov     dl, 5Bh ; '['
0x1800869f8  mov     rcx, rdi
0x1800869fb  call    jsonAppendChar
0x180086a00  lea     ebx, [r15+r13]
0x180086a04  lea     ebp, [rbx+rsi]
0x180086a07  jmp     short loc_180086A28
0x180086a09  cmp     byte ptr [rdi+21h], 0
0x180086a0d  jnz     short loc_180086A32
0x180086a0f  mov     r8, rdi
0x180086a12  mov     edx, ebx
0x180086a14  mov     rcx, r14
0x180086a17  call    jsonTranslateBlobToText
0x180086a1c  mov     dl, 2Ch ; ','
0x180086a1e  mov     rcx, rdi
0x180086a21  mov     ebx, eax
0x180086a23  call    jsonAppendChar
0x180086a28  cmp     ebx, ebp
0x180086a2a  jb      short loc_180086A09
0x180086a2c  jbe     short loc_180086A32
0x180086a2e  or      byte ptr [rdi+21h], 2
0x180086a32  test    esi, esi
0x180086a34  jz      short loc_180086A3E
0x180086a36  mov     rcx, rdi
0x180086a39  call    jsonStringTrimOneChar
0x180086a3e  mov     dl, 5Dh ; ']'
0x180086a40  jmp     loc_180086C39
0x180086a45  lea     edx, [r15+rax]
0x180086a49  mov     rcx, rdi
0x180086a4c  add     rdx, r8
0x180086a4f  mov     r8d, esi
0x180086a52  call    jsonAppendString
0x180086a57  jmp     loc_180086C41
0x180086a5c  lea     r14d, [r15+rax]
0x180086a60  mov     dl, 22h ; '"'
0x180086a62  mov     rcx, rdi
0x180086a65  add     r14, r8
0x180086a68  mov     ebx, esi
0x180086a6a  call    jsonAppendChar
0x180086a6f  test    esi, esi
0x180086a71  jz      loc_180086C37
0x180086a77  mov     r12d, 3
0x180086a7d  lea     rdx, __ImageBase
0x180086a84  xor     ebp, ebp
0x180086a86  movzx   ecx, byte ptr [rbp+r14+0]
0x180086a8c  cmp     byte ptr [rcx+rdx+0C11D0h], 0
0x180086a94  jnz     short loc_180086A9B
0x180086a96  cmp     cl, 27h ; '''
0x180086a99  jnz     short loc_180086AA1
0x180086a9b  inc     ebp
0x180086a9d  cmp     ebp, ebx
0x180086a9f  jb      short loc_180086A86
0x180086aa1  test    ebp, ebp
0x180086aa3  jz      short loc_180086AC2
0x180086aa5  mov     r8d, ebp
0x180086aa8  mov     rdx, r14
0x180086aab  mov     rcx, rdi
0x180086aae  call    jsonAppendRawNZ
0x180086ab3  cmp     ebp, ebx
0x180086ab5  jnb     loc_180086C37
0x180086abb  mov     eax, ebp
0x180086abd  add     r14, rax
0x180086ac0  sub     ebx, ebp
0x180086ac2  cmp     byte ptr [r14], 22h ; '"'
0x180086ac6  jnz     short loc_180086AE7
0x180086ac8  mov     r8d, 2
0x180086ace  lea     rdx, asc_1800BCE74; "\\\""
0x180086ad5  mov     rcx, rdi
0x180086ad8  call    jsonAppendRawNZ
0x180086add  inc     r14
0x180086ae0  dec     ebx
0x180086ae2  jmp     loc_180086C04
0x180086ae7  cmp     byte ptr [r14], 1Fh
0x180086aeb  jg      short loc_180086B1D
0x180086aed  mov     rax, [rdi+18h]
0x180086af1  add     rax, 7
0x180086af5  cmp     rax, [rdi+10h]
0x180086af9  jbe     short loc_180086B10
0x180086afb  mov     edx, 7
0x180086b00  mov     rcx, rdi
0x180086b03  call    jsonStringGrow
0x180086b08  test    eax, eax
0x180086b0a  jnz     loc_180086C37
0x180086b10  mov     dl, [r14]
0x180086b13  mov     rcx, rdi
0x180086b16  call    jsonAppendControlChar
0x180086b1b  jmp     short loc_180086ADD
0x180086b1d  cmp     ebx, 2
0x180086b20  jb      loc_180086C15
0x180086b26  movzx   ecx, byte ptr [r14+1]
0x180086b2b  sub     ecx, 0Ah
0x180086b2e  jz      loc_180086BFD
0x180086b34  sub     ecx, r12d
0x180086b37  jz      loc_180086BEC
0x180086b3d  sub     ecx, 1Ah
0x180086b40  jz      loc_180086BE0
  ... truncated ...
```
