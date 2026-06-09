# generateSortTail

- ea: `0x180061b2c`
- end: `0x180062099`
- name: `generateSortTail`
- size: `1389`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180008860`

## callees

- `0x18000b4bc`
- `0x180038974`
- `0x18003be78`
- `0x18003bff4`
- `0x180041574`
- `0x180042cd4`
- `0x180058ebc`
- `0x180061b2c`
- `0x180083928`
- `0x180083968`
- `0x18008980c`
- `0x18008982c`
- `0x18008d4bc`

## string_xrefs

- `0x180061bd4`: `USE TEMP B-TREE FOR %sORDER BY`
- `0x180061bac`: `USE TEMP B-TREE FOR LAST %d TERMS OF ORDER BY`

## pseudocode

```c
__int64 __fastcall generateSortTail(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, unsigned __int8 *a5)
{
  __int64 v8; // rbx
  __int64 v9; // r12
  unsigned int v10; // eax
  int v11; // ecx
  int v12; // r13d
  int v13; // r15d
  const char *v14; // r9
  int v15; // r9d
  unsigned int v16; // edx
  int v17; // r10d
  unsigned int TempReg; // r13d
  unsigned int TempRange; // esi
  unsigned int v20; // ebp
  int v21; // r9d
  int v22; // ebp
  __int64 v23; // r9
  int v24; // r8d
  int v25; // ebp
  unsigned int i; // edx
  int v27; // ecx
  int v28; // r15d
  int v29; // ecx
  int v30; // r9d
  char v31; // dl
  int v32; // r8d
  unsigned int v33; // r9d
  int v34; // edx
  int v35; // r15d
  int v36; // ebp
  int v37; // r8d
  int v39; // [rsp+40h] [rbp-68h]
  int v40; // [rsp+44h] [rbp-64h]
  unsigned int v41; // [rsp+48h] [rbp-60h]
  unsigned int v42; // [rsp+4Ch] [rbp-5Ch]
  int v43; // [rsp+50h] [rbp-58h]
  __int64 v44; // [rsp+58h] [rbp-50h]
  int v45; // [rsp+B0h] [rbp+8h]
  int v47; // [rsp+B8h] [rbp+10h]
  int v48; // [rsp+B8h] [rbp+10h]
  int v50; // [rsp+C8h] [rbp+20h]

  --*(_DWORD *)(a1 + 68);
  v8 = *(_QWORD *)(a1 + 16);
  v9 = a3;
  v41 = *(_DWORD *)(a3 + 28);
  v10 = *(_DWORD *)(a1 + 68);
  v11 = *(_DWORD *)(a3 + 8);
  v12 = *a5;
  v42 = v10;
  v39 = *((_DWORD *)a5 + 1);
  v50 = v12;
  v44 = *(_QWORD *)(a2 + 32) + 8LL;
  v13 = **(_DWORD **)a3 - v11;
  if ( !v11 || v13 == 1 )
  {
    v14 = "LAST TERM OF ";
    if ( !v11 )
      v14 = (const char *)&Src;
    sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %sORDER BY", v14);
  }
  else
  {
    sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR LAST %d TERMS OF ORDER BY", v13);
  }
  v15 = *(_DWORD *)(v9 + 20);
  v16 = 0;
  if ( v15 )
  {
    sqlite3VdbeAddOp3(v8, 10, *(_DWORD *)(v9 + 16), v15, 0);
    sqlite3VdbeAddOp3(v8, 9, 0, v41, 0);
    sqlite3VdbeResolveLabel(v8, *(unsigned int *)(v9 + 20));
    v16 = 0;
  }
  v17 = *(_DWORD *)(v9 + 12);
  v40 = v17;
  if ( ((v12 - 9) & 0xFFFFFFFB) == 0 )
    goto LABEL_16;
  if ( v12 == 10 )
  {
    if ( *(_DWORD *)(a2 + 12) )
    {
      sqlite3VdbeAddOp3(v8, 75, 0, *((_DWORD *)a5 + 3), 0);
      v17 = v40;
      v16 = 0;
    }
LABEL_16:
    TempRange = *((_DWORD *)a5 + 3);
    TempReg = 0;
    goto LABEL_17;
  }
  TempReg = sqlite3GetTempReg(a1);
  if ( ((v50 - 12) & 0xFFFFFFFD) != 0 )
  {
    TempRange = sqlite3GetTempRange(a1, a4);
    v16 = 0;
  }
  else
  {
    TempRange = sqlite3GetTempReg(a1);
    a4 = v16;
  }
LABEL_17:
  if ( (*(_BYTE *)(v9 + 36) & 1) != 0 )
  {
    ++*(_DWORD *)(a1 + 56);
    v20 = v16;
    v47 = *(_DWORD *)(a1 + 56);
    v45 = *(_DWORD *)(a1 + 52);
    *(_DWORD *)(a1 + 52) = v45 + 1;
    if ( *(_DWORD *)(v9 + 20) != v16 )
      v20 = sqlite3VdbeAddOp3(v8, 15, 0, 0, v16);
    sqlite3VdbeAddOp3(v8, 121, v45, v47, a4 + v13 + 1);
    v21 = 0;
    if ( v20 )
      *(_DWORD *)(sqlite3VdbeGetOp(v8, v20) + 8) = *(_DWORD *)(v8 + 144);
    v43 = sqlite3VdbeAddOp3(v8, 34, v40, v41, v21) + 1;
    sqlite3VdbeAddOp3(v8, 133, v40, v47, v45);
    v22 = 0;
  }
  else
  {
    v43 = sqlite3VdbeAddOp3(v8, 35, v17, v41, v16) + 1;
    codeOffset(v8, *(unsigned int *)(a2 + 12), v42);
    v22 = 1;
    v45 = v40;
    if ( *(int *)(a2 + 12) > 0 )
      sqlite3VdbeAddOp3(v8, 86, *(_DWORD *)(a2 + 8), -1, 0);
  }
  v23 = v44;
  v24 = v13 + v22;
  v48 = v13 + v22;
  v25 = v13 + v22 - 1;
  for ( i = 0; (int)i < (int)a4; v25 = v27 )
  {
    v27 = v25 + 1;
    if ( *(_WORD *)(32LL * i + v44 + 24) )
      v27 = v25;
    ++i;
  }
  v28 = a4 - 1;
  if ( (int)(a4 - 1) >= 0 )
  {
    do
    {
      v29 = *(unsigned __int16 *)(32LL * (unsigned int)v28 + v23 + 24);
      if ( (_WORD)v29 )
        v30 = v29 - 1;
      else
        v30 = v25--;
      sqlite3VdbeAddOp3(v8, 94, v45, v30, v28 + TempRange);
      --v28;
      v23 = v44;
    }
    while ( v28 >= 0 );
    v9 = a3;
    v24 = v48;
  }
  v31 = v50;
  if ( v50 != 10 )
  {
    switch ( v50 )
    {
      case 11:
        sqlite3VdbeAddOp4(v8, 97, TempRange, a4, TempReg, *((_QWORD *)a5 + 3), a4);
        sqlite3VdbeAddOp4Int(v8, 138, v39, TempReg, TempRange, a4);
        break;
      case 12:
      case 14:
        sqlite3VdbeAddOp3(v8, 94, v45, v24, TempRange);
        sqlite3VdbeAddOp3(v8, 127, v39, TempReg, 0);
        sqlite3VdbeAddOp3(v8, 128, v39, TempRange, TempReg);
        sqlite3VdbeChangeP5(v8, 8);
        break;
      case 15:
        v35 = *((_DWORD *)a5 + 2);
        v36 = sqlite3GetTempReg(a1);
        sqlite3VdbeAddOp3(v8, 97, ((unsigned int)v35 >> 31) + TempRange, a4 - ((unsigned int)v35 >> 31), v36);
        if ( v35 >= 0 )
          sqlite3VdbeAddOp4Int(v8, 138, v39, v36, TempRange, v35);
        else
          sqlite3VdbeAddOp3(v8, 128, v39, v36, TempRange);
        break;
      default:
        if ( (_BYTE)v50 == 9 )
        {
          v32 = *((_DWORD *)a5 + 3);
          v33 = a4;
          v34 = 84;
        }
        else
        {
          v32 = *((_DWORD *)a5 + 1);
          v33 = 0;
          v34 = 12;
        }
        sqlite3VdbeAddOp3(v8, v34, v32, v33, 0);
        break;
    }
    v31 = v50;
  }
  if ( TempReg )
  {
    if ( v31 == 11 )
      sqlite3ReleaseTempRange(a1, TempRange, a4);
    else
      sqlite3ReleaseTempReg(a1, TempRange);
    sqlite3ReleaseTempReg(a1, TempReg);
  }
  sqlite3VdbeResolveLabel(v8, v42);
  sqlite3VdbeAddOp3(v8, 2 * ((*(_BYTE *)(v9 + 36) & 1) == 0) + 37, v40, v43, 0);
  v37 = *(_DWORD *)(v9 + 16);
  if ( v37 )
    sqlite3VdbeAddOp3(v8, 67, v37, 0, 0);
  return sqlite3VdbeResolveLabel(v8, v41);
}

```

## disassembly

```asm
0x180061b2c  mov     [rsp+arg_10], r8
0x180061b31  mov     [rsp+arg_8], rdx
0x180061b36  push    rbx
0x180061b37  push    rbp
0x180061b38  push    rsi
0x180061b39  push    rdi
0x180061b3a  push    r12
0x180061b3c  push    r13
0x180061b3e  push    r14
0x180061b40  push    r15
0x180061b42  sub     rsp, 68h
0x180061b46  dec     dword ptr [rcx+44h]
0x180061b49  mov     rdi, rcx
0x180061b4c  mov     eax, [r8+1Ch]
0x180061b50  mov     rbp, rdx
0x180061b53  mov     rsi, [rsp+0A8h+arg_20]
0x180061b5b  mov     r14d, r9d
0x180061b5e  mov     rbx, [rcx+10h]
0x180061b62  mov     r12, r8
0x180061b65  mov     [rsp+0A8h+var_60], eax
0x180061b69  mov     eax, [rcx+44h]
0x180061b6c  mov     ecx, [r8+8]
0x180061b70  movzx   r13d, byte ptr [rsi]
0x180061b74  mov     [rsp+0A8h+var_5C], eax
0x180061b78  mov     eax, [rsi+4]
0x180061b7b  mov     [rsp+0A8h+var_68], eax
0x180061b7f  mov     rax, [rdx+20h]
0x180061b83  xor     edx, edx
0x180061b85  add     rax, 8
0x180061b89  mov     [rsp+0A8h+arg_18], r13d
0x180061b91  mov     [rsp+0A8h+var_50], rax
0x180061b96  mov     rax, [r8]
0x180061b99  mov     r15d, [rax]
0x180061b9c  sub     r15d, ecx
0x180061b9f  test    ecx, ecx
0x180061ba1  jz      short loc_180061BBD
0x180061ba3  cmp     r15d, 1
0x180061ba7  jz      short loc_180061BBD
0x180061ba9  mov     r9d, r15d
0x180061bac  lea     r8, aUseTempBTreeFo; "USE TEMP B-TREE FOR LAST %d TERMS OF OR"...
0x180061bb3  mov     rcx, rdi
0x180061bb6  call    sqlite3VdbeExplain
0x180061bbb  jmp     short loc_180061BE0
0x180061bbd  test    ecx, ecx
0x180061bbf  lea     rax, Src
0x180061bc6  lea     r9, aLastTermOf; "LAST TERM OF "
0x180061bcd  mov     rcx, rdi
0x180061bd0  cmovz   r9, rax
0x180061bd4  lea     r8, aUseTempBTreeFo_1; "USE TEMP B-TREE FOR %sORDER BY"
0x180061bdb  call    sqlite3VdbeExplain
0x180061be0  mov     r9d, [r12+14h]
0x180061be5  xor     edx, edx
0x180061be7  test    r9d, r9d
0x180061bea  jz      short loc_180061C2D
0x180061bec  mov     r8d, [r12+10h]
0x180061bf1  mov     rcx, rbx
0x180061bf4  mov     [rsp+0A8h+var_88], edx
0x180061bf8  mov     edx, 0Ah
0x180061bfd  call    sqlite3VdbeAddOp3
0x180061c02  xor     r9d, r9d
0x180061c05  xor     r8d, r8d
0x180061c08  mov     [rsp+0A8h+var_88], r9d
0x180061c0d  mov     rcx, rbx
0x180061c10  mov     r9d, [rsp+0A8h+var_60]
0x180061c15  lea     edx, [r8+9]
0x180061c19  call    sqlite3VdbeAddOp3
0x180061c1e  mov     edx, [r12+14h]
0x180061c23  mov     rcx, rbx
0x180061c26  call    sqlite3VdbeResolveLabel
0x180061c2b  xor     edx, edx
0x180061c2d  mov     r10d, [r12+0Ch]
0x180061c32  lea     eax, [r13-9]
0x180061c36  mov     [rsp+0A8h+var_64], r10d
0x180061c3b  test    eax, 0FFFFFFFBh
0x180061c40  jz      short loc_180061CA5
0x180061c42  cmp     r13d, 0Ah
0x180061c46  jz      short loc_180061C82
0x180061c48  mov     rcx, rdi
0x180061c4b  call    sqlite3GetTempReg
0x180061c50  mov     ecx, [rsp+0A8h+arg_18]
0x180061c57  mov     r13d, eax
0x180061c5a  add     ecx, 0FFFFFFF4h
0x180061c5d  test    ecx, 0FFFFFFFDh
0x180061c63  mov     rcx, rdi
0x180061c66  jz      short loc_180061C76
0x180061c68  mov     edx, r14d
0x180061c6b  call    sqlite3GetTempRange
0x180061c70  mov     esi, eax
0x180061c72  xor     edx, edx
0x180061c74  jmp     short loc_180061CAB
0x180061c76  call    sqlite3GetTempReg
0x180061c7b  mov     esi, eax
0x180061c7d  mov     r14d, edx
0x180061c80  jmp     short loc_180061CAB
0x180061c82  cmp     [rbp+0Ch], edx
0x180061c85  jz      short loc_180061CA5
0x180061c87  mov     r9d, [rsi+0Ch]
0x180061c8b  xor     r8d, r8d
0x180061c8e  mov     [rsp+0A8h+var_88], edx
0x180061c92  mov     rcx, rbx
0x180061c95  lea     edx, [r8+4Bh]
0x180061c99  call    sqlite3VdbeAddOp3
0x180061c9e  mov     r10d, [rsp+0A8h+var_64]
0x180061ca3  xor     edx, edx
0x180061ca5  mov     esi, [rsi+0Ch]
0x180061ca8  mov     r13d, edx
0x180061cab  test    byte ptr [r12+24h], 1
0x180061cb1  jz      loc_180061D85
0x180061cb7  inc     dword ptr [rdi+38h]
0x180061cba  mov     ebp, edx
0x180061cbc  mov     eax, [rdi+38h]
0x180061cbf  mov     dword ptr [rsp+0A8h+arg_8], eax
0x180061cc6  mov     eax, [rdi+34h]
0x180061cc9  mov     [rsp+0A8h+arg_0], eax
0x180061cd0  inc     eax
0x180061cd2  mov     [rdi+34h], eax
0x180061cd5  cmp     [r12+14h], edx
0x180061cda  jz      short loc_180061CF4
0x180061cdc  xor     r9d, r9d
0x180061cdf  mov     [rsp+0A8h+var_88], edx
0x180061ce3  xor     r8d, r8d
0x180061ce6  mov     rcx, rbx
0x180061ce9  lea     edx, [r9+0Fh]
0x180061ced  call    sqlite3VdbeAddOp3
0x180061cf2  mov     ebp, eax
0x180061cf4  mov     r9d, dword ptr [rsp+0A8h+arg_8]
0x180061cfc  lea     ecx, [r15+1]
0x180061d00  mov     r8d, [rsp+0A8h+arg_0]
0x180061d08  add     ecx, r14d
0x180061d0b  mov     [rsp+0A8h+var_88], ecx
0x180061d0f  mov     edx, 79h ; 'y'
0x180061d14  mov     rcx, rbx
0x180061d17  call    sqlite3VdbeAddOp3
0x180061d1c  xor     r9d, r9d
0x180061d1f  test    ebp, ebp
0x180061d21  jz      short loc_180061D36
0x180061d23  mov     edx, ebp
0x180061d25  mov     rcx, rbx
0x180061d28  call    sqlite3VdbeGetOp
0x180061d2d  mov     ecx, [rbx+90h]
0x180061d33  mov     [rax+8], ecx
0x180061d36  mov     r8d, [rsp+0A8h+var_64]
0x180061d3b  mov     edx, 22h ; '"'
0x180061d40  mov     [rsp+0A8h+var_88], r9d
0x180061d45  mov     rcx, rbx
0x180061d48  mov     r9d, [rsp+0A8h+var_60]
0x180061d4d  call    sqlite3VdbeAddOp3
0x180061d52  mov     r9d, dword ptr [rsp+0A8h+arg_8]
0x180061d5a  inc     eax
0x180061d5c  mov     r8d, [rsp+0A8h+var_64]
0x180061d61  mov     edx, 85h
0x180061d66  mov     [rsp+0A8h+var_58], eax
0x180061d6a  mov     rcx, rbx
0x180061d6d  mov     eax, [rsp+0A8h+arg_0]
0x180061d74  mov     [rsp+0A8h+var_88], eax
0x180061d78  call    sqlite3VdbeAddOp3
0x180061d7d  xor     r10d, r10d
0x180061d80  mov     ebp, r10d
0x180061d83  jmp     short loc_180061DF0
0x180061d85  mov     r9d, [rsp+0A8h+var_60]
0x180061d8a  mov     r8d, r10d
0x180061d8d  mov     [rsp+0A8h+var_88], edx
0x180061d91  mov     rcx, rbx
0x180061d94  mov     edx, 23h ; '#'
0x180061d99  call    sqlite3VdbeAddOp3
0x180061d9e  mov     r8d, [rsp+0A8h+var_5C]
0x180061da3  inc     eax
0x180061da5  mov     edx, [rbp+0Ch]
0x180061da8  mov     rcx, rbx
0x180061dab  mov     [rsp+0A8h+var_58], eax
0x180061daf  call    codeOffset
0x180061db4  mov     r8, [rsp+0A8h+arg_8]
0x180061dbc  xor     r10d, r10d
0x180061dbf  mov     eax, [rsp+0A8h+var_64]
0x180061dc3  mov     ebp, 1
0x180061dc8  mov     [rsp+0A8h+arg_0], eax
0x180061dcf  cmp     [r8+0Ch], r10d
0x180061dd3  jle     short loc_180061DF0
0x180061dd5  mov     r8d, [r8+8]
0x180061dd9  lea     edx, [rbp+55h]
0x180061ddc  or      r9d, 0FFFFFFFFh
0x180061de0  mov     [rsp+0A8h+var_88], r10d
0x180061de5  mov     rcx, rbx
0x180061de8  call    sqlite3VdbeAddOp3
0x180061ded  xor     r10d, r10d
0x180061df0  mov     r9, [rsp+0A8h+var_50]
0x180061df5  lea     r8d, [r15+rbp]
0x180061df9  mov     dword ptr [rsp+0A8h+arg_8], r8d
0x180061e01  lea     ebp, [r8-1]
0x180061e05  mov     edx, r10d
0x180061e08  test    r14d, r14d
0x180061e0b  jle     short loc_180061E28
0x180061e0d  mov     eax, edx
0x180061e0f  lea     ecx, [rbp+1]
0x180061e12  shl     rax, 5
0x180061e16  cmp     [rax+r9+18h], r10w
0x180061e1c  cmovnz  ecx, ebp
0x180061e1f  inc     edx
0x180061e21  mov     ebp, ecx
0x180061e23  cmp     edx, r14d
0x180061e26  jl      short loc_180061E0D
0x180061e28  lea     r15d, [r14-1]
0x180061e2c  test    r15d, r15d
0x180061e2f  js      short loc_180061E8F
0x180061e31  mov     r12d, [rsp+0A8h+arg_0]
0x180061e39  mov     eax, r15d
0x180061e3c  shl     rax, 5
0x180061e40  movzx   ecx, word ptr [rax+r9+18h]
0x180061e46  test    cx, cx
0x180061e49  jz      short loc_180061E51
0x180061e4b  lea     r9d, [rcx-1]
0x180061e4f  jmp     short loc_180061E56
0x180061e51  mov     r9d, ebp
0x180061e54  dec     ebp
0x180061e56  lea     eax, [r15+rsi]
0x180061e5a  mov     r8d, r12d
0x180061e5d  mov     edx, 5Eh ; '^'
0x180061e62  mov     [rsp+0A8h+var_88], eax
0x180061e66  mov     rcx, rbx
0x180061e69  call    sqlite3VdbeAddOp3
0x180061e6e  sub     r15d, 1
0x180061e72  mov     r9, [rsp+0A8h+var_50]
0x180061e77  mov     r10d, 0
0x180061e7d  jns     short loc_180061E39
0x180061e7f  mov     r12, [rsp+0A8h+arg_10]
0x180061e87  mov     r8d, dword ptr [rsp+0A8h+arg_8]
0x180061e8f  mov     edx, [rsp+0A8h+arg_18]
0x180061e96  mov     ecx, edx
0x180061e98  sub     ecx, 0Ah
0x180061e9b  jz      loc_180062002
0x180061ea1  sub     ecx, 1
0x180061ea4  jz      loc_180061FAF
0x180061eaa  sub     ecx, 1
0x180061ead  jz      loc_180061F4D
0x180061eb3  sub     ecx, 2
0x180061eb6  jz      loc_180061F4D
0x180061ebc  mov     rax, [rsp+0A8h+arg_20]
0x180061ec4  cmp     ecx, 1
0x180061ec7  jz      short loc_180061EF9
0x180061ec9  mov     [rsp+0A8h+var_88], r10d
0x180061ece  mov     rcx, rbx
0x180061ed1  cmp     dl, 9
0x180061ed4  jnz     short loc_180061EEC
0x180061ed6  mov     r8d, [rax+0Ch]
0x180061eda  mov     r9d, r14d
0x180061edd  mov     edx, 54h ; 'T'
0x180061ee2  call    sqlite3VdbeAddOp3
0x180061ee7  jmp     loc_180061FFB
0x180061eec  mov     r8d, [rax+4]
0x180061ef0  xor     r9d, r9d
0x180061ef3  lea     edx, [r9+0Ch]
0x180061ef7  jmp     short loc_180061EE2
0x180061ef9  mov     r15d, [rax+8]
0x180061efd  mov     rcx, rdi
0x180061f00  call    sqlite3GetTempReg
0x180061f05  mov     ecx, r15d
0x180061f08  mov     [rsp+0A8h+var_88], eax
0x180061f0c  shr     ecx, 1Fh
0x180061f0f  mov     r9d, r14d
0x180061f12  sub     r9d, ecx
0x180061f15  mov     edx, 61h ; 'a'
0x180061f1a  mov     ebp, eax
0x180061f1c  lea     r8d, [rcx+rsi]
0x180061f20  mov     rcx, rbx
0x180061f23  call    sqlite3VdbeAddOp3
0x180061f28  mov     r8d, [rsp+0A8h+var_68]
0x180061f2d  mov     r9d, ebp
0x180061f30  mov     rcx, rbx
0x180061f33  test    r15d, r15d
0x180061f36  jns     short loc_180061F43
0x180061f38  mov     [rsp+0A8h+var_88], esi
0x180061f3c  mov     edx, 80h
0x180061f41  jmp     short loc_180061EE2
0x180061f43  mov     dword ptr [rsp+0A8h+var_80], r15d
0x180061f48  jmp     loc_180061FED
0x180061f4d  mov     r9d, r8d
0x180061f50  mov     [rsp+0A8h+var_88], esi
0x180061f54  mov     r8d, [rsp+0A8h+arg_0]
0x180061f5c  mov     edx, 5Eh ; '^'
0x180061f61  mov     rcx, rbx
0x180061f64  call    sqlite3VdbeAddOp3
0x180061f69  mov     r8d, [rsp+0A8h+var_68]
0x180061f6e  xor     r9d, r9d
0x180061f71  mov     [rsp+0A8h+var_88], r9d
0x180061f76  mov     edx, 7Fh
0x180061f7b  mov     r9d, r13d
0x180061f7e  mov     rcx, rbx
0x180061f81  call    sqlite3VdbeAddOp3
0x180061f86  mov     r8d, [rsp+0A8h+var_68]
0x180061f8b  mov     r9d, esi
0x180061f8e  mov     edx, 80h
0x180061f93  mov     [rsp+0A8h+var_88], r13d
0x180061f98  mov     rcx, rbx
0x180061f9b  call    sqlite3VdbeAddOp3
0x180061fa0  mov     edx, 8
0x180061fa5  mov     rcx, rbx
0x180061fa8  call    sqlite3VdbeChangeP5
0x180061fad  jmp     short loc_180061FFB
0x180061faf  mov     rax, [rsp+0A8h+arg_20]
0x180061fb7  mov     r9d, r14d
  ... truncated ...
```
