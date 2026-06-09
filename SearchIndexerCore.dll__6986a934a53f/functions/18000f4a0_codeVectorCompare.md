# codeVectorCompare

- ea: `0x18000f4a0`
- end: `0x18000f9eb`
- name: `codeVectorCompare`
- size: `1355`
- prototype: `__int64 __fastcall(__int64, __int64, int, unsigned __int8, char)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180017938`

## callees

- `0x18000e318`
- `0x18000e934`
- `0x18000e990`
- `0x18000f4a0`
- `0x18001001c`
- `0x180010c70`
- `0x180011bcc`
- `0x1800168c0`
- `0x180016c60`
- `0x180018aac`
- `0x18001e0c4`

## pseudocode

```c
__int64 __fastcall codeVectorCompare(__int64 a1, __int64 a2, int a3, unsigned __int8 a4, char a5)
{
  char *v5; // r12
  char *v7; // r13
  int v8; // ebp
  __int64 result; // rax
  unsigned int v10; // r14d
  int v11; // r15d
  int v12; // eax
  __int64 v13; // rdx
  char v14; // r9
  int v15; // r8d
  char v16; // cl
  __int64 v17; // rsi
  int v18; // ebx
  int v19; // r9d
  int v20; // ebp
  __int64 *v21; // rax
  char v22; // al
  __int64 v23; // rbp
  char v24; // al
  __int64 v25; // rbx
  bool v26; // zf
  __int64 v27; // r8
  __int64 v28; // rdx
  char v29; // bl
  char v30; // bp
  char v31; // bp
  __int64 v32; // rbx
  unsigned int v33; // eax
  __int64 v34; // r8
  __int64 v35; // rax
  int v36; // ecx
  int v37; // r8d
  unsigned __int8 v38; // dl
  __int64 *v39; // r8
  int v40; // r15d
  __int64 v41; // rcx
  char v42; // bp
  int v43; // ecx
  int v44; // ecx
  __int64 v45; // rax
  __int64 v46; // rax
  unsigned __int8 v47; // [rsp+30h] [rbp-78h]
  int v48; // [rsp+34h] [rbp-74h]
  int v49; // [rsp+38h] [rbp-70h]
  int v50; // [rsp+3Ch] [rbp-6Ch] BYREF
  int v51; // [rsp+40h] [rbp-68h] BYREF
  int v52; // [rsp+44h] [rbp-64h]
  int v53; // [rsp+48h] [rbp-60h]
  int v54; // [rsp+4Ch] [rbp-5Ch]
  int v55; // [rsp+50h] [rbp-58h]
  int v56; // [rsp+54h] [rbp-54h]
  __int64 v57; // [rsp+58h] [rbp-50h]
  int v58; // [rsp+B0h] [rbp+8h]
  int v59; // [rsp+B8h] [rbp+10h]

  v5 = *(char **)(a2 + 16);
  v7 = *(char **)(a2 + 24);
  v8 = a3;
  result = sqlite3ExprVectorSize(v5);
  --*(_DWORD *)(a1 + 68);
  v10 = 0;
  v11 = *(_DWORD *)(a1 + 68);
  v54 = result;
  if ( *(_DWORD *)(a1 + 48) )
    return result;
  v12 = sqlite3ExprVectorSize(v7);
  if ( v15 != v12 )
    return sqlite3ErrorMsg(a1, "row value misused");
  v16 = 56;
  v17 = *(_QWORD *)(a1 + 16);
  v55 = *(_DWORD *)(v13 + 4) & 0x400;
  v18 = 0;
  if ( v14 != 55 )
    v16 = v14;
  if ( v14 == 57 )
  {
    v47 = 54;
  }
  else
  {
    v42 = v16;
    if ( v14 == 52 )
      v42 = 53;
    v47 = v42;
    v8 = a3;
  }
  v48 = 0;
  if ( *v5 == -118 )
    v48 = sqlite3CodeSubselect(a1, v5);
  v49 = 0;
  if ( *v7 == -118 )
    v49 = sqlite3CodeSubselect(a1, v7);
  v19 = v8;
  v20 = 71;
  sqlite3VdbeAddOp3(v17, 71, 1, v19, 0);
  if ( a5 != (char)0x80 )
    v20 = 92;
  v56 = v20;
  v53 = v54 - 1;
  while ( 1 )
  {
    v50 = 0;
    v51 = 0;
    if ( v18 )
    {
      if ( *(_BYTE *)(*(_QWORD *)v17 + 103LL) )
        v21 = qword_1800D1220;
      else
        v21 = (__int64 *)(*(_QWORD *)(v17 + 136) + 24LL * v18);
      *((_DWORD *)v21 + 2) = *(_DWORD *)(v17 + 144);
    }
    v22 = *v5;
    if ( *v5 == -80 )
    {
      v45 = sqlite3VectorFieldSubexpr(v5, v10);
      v43 = *((_DWORD *)v5 + 11);
      v23 = v45;
      goto LABEL_68;
    }
    if ( v22 == -118 )
    {
      v23 = *(_QWORD *)(32LL * (int)v10 + *(_QWORD *)(*((_QWORD *)v5 + 4) + 32LL) + 8);
      v43 = v48;
LABEL_68:
      v59 = v10 + v43;
      goto LABEL_22;
    }
    if ( v22 == -79 )
    {
      v23 = *(_QWORD *)(32LL * (int)v10 + *((_QWORD *)v5 + 4) + 8);
      v59 = sqlite3ExprCodeTemp(a1, v23, &v50);
    }
    else
    {
      v23 = 0;
      v59 = 0;
    }
LABEL_22:
    v24 = *v7;
    if ( *v7 == -80 )
    {
      v46 = sqlite3VectorFieldSubexpr(v7, v10);
      v44 = *((_DWORD *)v7 + 11);
      v25 = v46;
      goto LABEL_70;
    }
    if ( v24 == -118 )
    {
      v25 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 4) + 32LL) + 32LL * (int)v10 + 8);
      v44 = v49;
LABEL_70:
      v58 = v10 + v44;
      goto LABEL_26;
    }
    if ( v24 == -79 )
    {
      v25 = *(_QWORD *)(32LL * (int)v10 + *((_QWORD *)v7 + 4) + 8);
      v58 = sqlite3ExprCodeTemp(a1, v25, &v51);
    }
    else
    {
      v25 = 0;
      v58 = 0;
    }
LABEL_26:
    v26 = *(_DWORD *)(a1 + 48) == 0;
    v52 = *(_DWORD *)(v17 + 144);
    if ( !v26 )
      goto LABEL_34;
    v27 = v23;
    v28 = v25;
    if ( !v55 )
    {
      v27 = v25;
      v28 = v23;
    }
    v57 = sqlite3BinaryCompareCollSeq(a1, v28, v27);
    v29 = sqlite3ExprAffinity(v25);
    v30 = sqlite3ExprAffinity(v23);
    if ( v30 <= 64 )
    {
      v30 = v29;
LABEL_31:
      v31 = v30 | 0x40;
      goto LABEL_32;
    }
    if ( v29 <= 64 )
      goto LABEL_31;
    v31 = v29 >= 67 || v30 >= 67 ? 67 : 65;
LABEL_32:
    v32 = *(_QWORD *)(a1 + 16);
    v33 = sqlite3VdbeAddOp3(v32, v47, v58, v11, v59);
    sqlite3VdbeChangeP4(v32, v33, v57, 4294967294LL);
    v34 = *(_QWORD *)(a1 + 16);
    v35 = *(int *)(v34 + 144);
    if ( (int)v35 > 0 )
      *(_WORD *)(*(_QWORD *)(v34 + 136) + 24 * v35 - 22) = (unsigned __int8)(a5 | v31);
LABEL_34:
    if ( v50 && *(_BYTE *)(a1 + 31) < 8u )
      *(_DWORD *)(a1 + 4LL * (unsigned __int8)(*(_BYTE *)(a1 + 31))++ + 232) = v50;
    if ( v51 && *(_BYTE *)(a1 + 31) < 8u )
      *(_DWORD *)(a1 + 4LL * (unsigned __int8)(*(_BYTE *)(a1 + 31))++ + 232) = v51;
    if ( ((v47 - 54) & 0xFD) != 0 || (int)v10 >= v53 )
      v18 = v52;
    else
      v18 = sqlite3VdbeAddOp3(v17, 58, 0, 0, 0);
    v36 = 0;
    if ( a5 != (char)0x80 )
      v36 = v58;
    v37 = 0;
    if ( a5 != (char)0x80 )
      v37 = v59;
    sqlite3VdbeAddOp3(v17, v56, v37, a3, v36);
    if ( v10 == v53 )
      break;
    if ( v47 == 53 )
    {
      sqlite3VdbeAddOp3(v17, 51, a3, v11, 0);
    }
    else
    {
      sqlite3VdbeAddOp3(v17, 9, 0, v11, 0);
      v38 = v47;
      if ( v10 == v54 - 2 )
        v38 = a4;
      v47 = v38;
    }
    ++v10;
  }
  if ( *(_BYTE *)(*(_QWORD *)v17 + 103LL) )
    v39 = qword_1800D1220;
  else
    v39 = (__int64 *)(*(_QWORD *)(v17 + 136) + 24LL * v18);
  *((_DWORD *)v39 + 2) = *(_DWORD *)(v17 + 144);
  v40 = ~v11;
  v41 = *(_QWORD *)(v17 + 24);
  if ( *(_DWORD *)(v41 + 68) + *(_DWORD *)(v41 + 72) < 0 )
  {
    result = resizeResolveLabel(v41, v17, (unsigned int)v40);
  }
  else
  {
    result = *(unsigned int *)(v17 + 144);
    *(_DWORD *)(*(_QWORD *)(v41 + 80) + 4LL * v40) = result;
  }
  if ( a4 == 52 )
    return sqlite3VdbeAddOp3(v17, 19, a3, a3, 0);
  return result;
}

```

## disassembly

```asm
0x18000f4a0  mov     [rsp+arg_18], r9b
0x18000f4a5  mov     [rsp+arg_10], r8d
0x18000f4aa  push    rbx
0x18000f4ab  push    rbp
0x18000f4ac  push    rsi
0x18000f4ad  push    rdi
0x18000f4ae  push    r12
0x18000f4b0  push    r13
0x18000f4b2  push    r14
0x18000f4b4  push    r15
0x18000f4b6  sub     rsp, 68h
0x18000f4ba  mov     r12, [rdx+10h]
0x18000f4be  mov     rdi, rcx
0x18000f4c1  mov     r13, [rdx+18h]
0x18000f4c5  mov     rcx, r12
0x18000f4c8  mov     ebp, r8d
0x18000f4cb  call    sqlite3ExprVectorSize
0x18000f4d0  dec     dword ptr [rdi+44h]
0x18000f4d3  xor     r14d, r14d
0x18000f4d6  mov     r8d, eax
0x18000f4d9  mov     r15d, [rdi+44h]
0x18000f4dd  mov     [rsp+0A8h+var_5C], eax
0x18000f4e1  cmp     [rdi+30h], r14d
0x18000f4e5  jnz     loc_18000F8B7
0x18000f4eb  mov     rcx, r13
0x18000f4ee  call    sqlite3ExprVectorSize
0x18000f4f3  cmp     r8d, eax
0x18000f4f6  jnz     loc_18000F8F8
0x18000f4fc  mov     eax, [rdx+4]
0x18000f4ff  lea     ecx, [r14+38h]
0x18000f503  mov     rsi, [rdi+10h]
0x18000f507  and     eax, 400h
0x18000f50c  mov     [rsp+0A8h+var_58], eax
0x18000f510  cmp     r9b, 37h ; '7'
0x18000f514  movzx   eax, r9b
0x18000f518  mov     ebx, r14d
0x18000f51b  cmovnz  ecx, eax
0x18000f51e  lea     eax, [r14+35h]
0x18000f522  cmp     r9b, 39h ; '9'
0x18000f526  jnz     loc_18000F8D1
0x18000f52c  mov     byte ptr [rsp+0A8h+var_78], 36h ; '6'
0x18000f531  cmp     byte ptr [r12], 8Ah
0x18000f536  mov     [rsp+0A8h+var_74], r14d
0x18000f53b  jnz     short loc_18000F54C
0x18000f53d  mov     rdx, r12
0x18000f540  mov     rcx, rdi
0x18000f543  call    sqlite3CodeSubselect
0x18000f548  mov     [rsp+0A8h+var_74], eax
0x18000f54c  cmp     byte ptr [r13+0], 8Ah
0x18000f551  mov     [rsp+0A8h+var_70], r14d
0x18000f556  jnz     short loc_18000F567
0x18000f558  mov     rdx, r13
0x18000f55b  mov     rcx, rdi
0x18000f55e  call    sqlite3CodeSubselect
0x18000f563  mov     [rsp+0A8h+var_70], eax
0x18000f567  mov     r9d, ebp
0x18000f56a  mov     [rsp+0A8h+var_88], r14d
0x18000f56f  mov     ebp, 47h ; 'G'
0x18000f574  mov     rcx, rsi
0x18000f577  mov     edx, ebp
0x18000f579  lea     r8d, [rbp-46h]
0x18000f57d  call    sqlite3VdbeAddOp3
0x18000f582  cmp     [rsp+0A8h+arg_20], 80h
0x18000f58a  lea     eax, [rbp+15h]
0x18000f58d  cmovnz  ebp, eax
0x18000f590  mov     eax, [rsp+0A8h+var_5C]
0x18000f594  dec     eax
0x18000f596  mov     [rsp+0A8h+var_54], ebp
0x18000f59a  mov     [rsp+0A8h+var_60], eax
0x18000f59e  mov     [rsp+0A8h+var_6C], 0
0x18000f5a6  lea     rcx, qword_1800D1220
0x18000f5ad  mov     [rsp+0A8h+var_68], 0
0x18000f5b5  test    ebx, ebx
0x18000f5b7  jz      short loc_18000F5E1
0x18000f5b9  mov     rax, [rsi]
0x18000f5bc  mov     edx, [rsi+90h]
0x18000f5c2  cmp     byte ptr [rax+67h], 0
0x18000f5c6  jnz     loc_18000F9B4
0x18000f5cc  movsxd  rax, ebx
0x18000f5cf  lea     rcx, [rax+rax*2]
0x18000f5d3  mov     rax, [rsi+88h]
0x18000f5da  lea     rax, [rax+rcx*8]
0x18000f5de  mov     [rax+8], edx
0x18000f5e1  mov     al, [r12]
0x18000f5e5  cmp     al, 0B0h
0x18000f5e7  jz      loc_18000F96F
0x18000f5ed  cmp     al, 8Ah
0x18000f5ef  jz      loc_18000F920
0x18000f5f5  cmp     al, 0B1h
0x18000f5f7  jnz     loc_18000F998
0x18000f5fd  mov     rax, [r12+20h]
0x18000f602  lea     r8, [rsp+0A8h+var_6C]
0x18000f607  movsxd  rcx, r14d
0x18000f60a  shl     rcx, 5
0x18000f60e  mov     rbp, [rcx+rax+8]
0x18000f613  mov     rcx, rdi
0x18000f616  mov     rdx, rbp
0x18000f619  call    sqlite3ExprCodeTemp
0x18000f61e  mov     [rsp+0A8h+arg_8], eax
0x18000f625  mov     al, [r13+0]
0x18000f629  cmp     al, 0B0h
0x18000f62b  jz      loc_18000F984
0x18000f631  cmp     al, 8Ah
0x18000f633  jz      loc_18000F948
0x18000f639  cmp     al, 0B1h
0x18000f63b  jnz     loc_18000F9A6
0x18000f641  mov     rax, [r13+20h]
0x18000f645  lea     r8, [rsp+0A8h+var_68]
0x18000f64a  movsxd  rcx, r14d
0x18000f64d  shl     rcx, 5
0x18000f651  mov     rbx, [rcx+rax+8]
0x18000f656  mov     rcx, rdi
0x18000f659  mov     rdx, rbx
0x18000f65c  call    sqlite3ExprCodeTemp
0x18000f661  mov     [rsp+0A8h+arg_0], eax
0x18000f668  cmp     dword ptr [rdi+30h], 0
0x18000f66c  mov     eax, [rsi+90h]
0x18000f672  mov     [rsp+0A8h+var_64], eax
0x18000f676  jnz     loc_18000F72A
0x18000f67c  mov     eax, [rsp+0A8h+var_58]
0x18000f680  mov     r8, rbp
0x18000f683  test    eax, eax
0x18000f685  mov     rdx, rbx
0x18000f688  mov     rcx, rdi
0x18000f68b  cmovz   r8, rbx
0x18000f68f  cmovz   rdx, rbp
0x18000f693  call    sqlite3BinaryCompareCollSeq
0x18000f698  mov     rcx, rbx
0x18000f69b  mov     [rsp+0A8h+var_50], rax
0x18000f6a0  call    sqlite3ExprAffinity
0x18000f6a5  mov     rcx, rbp
0x18000f6a8  mov     bl, al
0x18000f6aa  call    sqlite3ExprAffinity
0x18000f6af  mov     bpl, al
0x18000f6b2  mov     al, 40h ; '@'
0x18000f6b4  cmp     bpl, al
0x18000f6b7  jg      loc_18000F9C8
0x18000f6bd  mov     bpl, bl
0x18000f6c0  or      bpl, al
0x18000f6c3  mov     rbx, [rdi+10h]
0x18000f6c7  mov     r9d, r15d
0x18000f6ca  mov     eax, [rsp+0A8h+arg_8]
0x18000f6d1  mov     rcx, rbx
0x18000f6d4  movzx   edx, byte ptr [rsp+0A8h+var_78]
0x18000f6d9  mov     r8d, [rsp+0A8h+arg_0]
0x18000f6e1  mov     [rsp+0A8h+var_88], eax
0x18000f6e5  call    sqlite3VdbeAddOp3
0x18000f6ea  mov     r8, [rsp+0A8h+var_50]
0x18000f6ef  mov     r9d, 0FFFFFFFEh
0x18000f6f5  mov     edx, eax
0x18000f6f7  mov     rcx, rbx
0x18000f6fa  call    sqlite3VdbeChangeP4
0x18000f6ff  mov     r8, [rdi+10h]
0x18000f703  movsxd  rax, dword ptr [r8+90h]
0x18000f70a  test    eax, eax
0x18000f70c  jle     short loc_18000F72A
0x18000f70e  or      bpl, [rsp+0A8h+arg_20]
0x18000f716  lea     rcx, [rax+rax*2]
0x18000f71a  mov     rax, [r8+88h]
0x18000f721  movzx   edx, bpl
0x18000f725  mov     [rax+rcx*8-16h], dx
0x18000f72a  mov     ecx, [rsp+0A8h+var_6C]
0x18000f72e  test    ecx, ecx
0x18000f730  jnz     loc_18000F80A
0x18000f736  mov     ecx, [rsp+0A8h+var_68]
0x18000f73a  test    ecx, ecx
0x18000f73c  jnz     loc_18000F827
0x18000f742  mov     ebp, [rsp+0A8h+var_78]
0x18000f746  lea     eax, [rbp-36h]
0x18000f749  test    al, 0FDh
0x18000f74b  jnz     loc_18000F8C8
0x18000f751  cmp     r14d, [rsp+0A8h+var_60]
0x18000f756  jge     loc_18000F8C8
0x18000f75c  xor     r9d, r9d
0x18000f75f  mov     [rsp+0A8h+var_88], 0
0x18000f767  xor     r8d, r8d
0x18000f76a  mov     rcx, rsi
0x18000f76d  lea     edx, [r9+3Ah]
0x18000f771  call    sqlite3VdbeAddOp3
0x18000f776  mov     ebx, eax
0x18000f778  mov     r9d, [rsp+0A8h+arg_10]
0x18000f780  xor     ecx, ecx
0x18000f782  cmp     [rsp+0A8h+arg_20], 80h
0x18000f78a  mov     edx, [rsp+0A8h+var_54]
0x18000f78e  cmovnz  ecx, [rsp+0A8h+arg_0]
0x18000f796  xor     r8d, r8d
0x18000f799  cmp     [rsp+0A8h+arg_20], 80h
0x18000f7a1  mov     [rsp+0A8h+var_88], ecx
0x18000f7a5  mov     rcx, rsi
0x18000f7a8  cmovnz  r8d, [rsp+0A8h+arg_8]
0x18000f7b1  call    sqlite3VdbeAddOp3
0x18000f7b6  cmp     r14d, [rsp+0A8h+var_60]
0x18000f7bb  jz      loc_18000F844
0x18000f7c1  mov     [rsp+0A8h+var_88], 0
0x18000f7c9  mov     r9d, r15d
0x18000f7cc  mov     rcx, rsi
0x18000f7cf  cmp     bpl, 35h ; '5'
0x18000f7d3  jz      loc_18000F909
0x18000f7d9  xor     r8d, r8d
0x18000f7dc  lea     edx, [r8+9]
0x18000f7e0  call    sqlite3VdbeAddOp3
0x18000f7e5  mov     ecx, [rsp+0A8h+var_5C]
0x18000f7e9  movzx   eax, [rsp+0A8h+arg_18]
0x18000f7f1  add     ecx, 0FFFFFFFEh
0x18000f7f4  cmp     r14d, ecx
0x18000f7f7  movzx   edx, bpl
0x18000f7fb  cmovz   edx, eax
0x18000f7fe  mov     byte ptr [rsp+0A8h+var_78], dl
0x18000f802  inc     r14d
0x18000f805  jmp     loc_18000F59E
0x18000f80a  cmp     byte ptr [rdi+1Fh], 8
0x18000f80e  jnb     loc_18000F736
0x18000f814  movzx   eax, byte ptr [rdi+1Fh]
0x18000f818  mov     [rdi+rax*4+0E8h], ecx
0x18000f81f  inc     byte ptr [rdi+1Fh]
0x18000f822  jmp     loc_18000F736
0x18000f827  cmp     byte ptr [rdi+1Fh], 8
0x18000f82b  jnb     loc_18000F742
0x18000f831  movzx   eax, byte ptr [rdi+1Fh]
0x18000f835  mov     [rdi+rax*4+0E8h], ecx
0x18000f83c  inc     byte ptr [rdi+1Fh]
0x18000f83f  jmp     loc_18000F742
0x18000f844  mov     rax, [rsi]
0x18000f847  mov     edx, [rsi+90h]
0x18000f84d  cmp     byte ptr [rax+67h], 0
0x18000f851  jnz     loc_18000F9BC
0x18000f857  movsxd  rax, ebx
0x18000f85a  lea     rcx, [rax+rax*2]
0x18000f85e  mov     rax, [rsi+88h]
0x18000f865  lea     r8, [rax+rcx*8]
0x18000f869  mov     [r8+8], edx
0x18000f86d  not     r15d
0x18000f870  mov     rcx, [rsi+18h]
0x18000f874  mov     eax, [rcx+48h]
0x18000f877  add     eax, [rcx+44h]
0x18000f87a  js      short loc_18000F8EB
0x18000f87c  mov     rdx, [rcx+50h]
0x18000f880  mov     eax, [rsi+90h]
0x18000f886  movsxd  r8, r15d
0x18000f889  mov     [rdx+r8*4], eax
0x18000f88d  cmp     [rsp+0A8h+arg_18], 34h ; '4'
0x18000f895  jnz     short loc_18000F8B7
0x18000f897  mov     r9d, [rsp+0A8h+arg_10]
0x18000f89f  mov     edx, 13h
0x18000f8a4  mov     r8d, r9d
0x18000f8a7  mov     [rsp+0A8h+var_88], 0
0x18000f8af  mov     rcx, rsi
0x18000f8b2  call    sqlite3VdbeAddOp3
0x18000f8b7  add     rsp, 68h
0x18000f8bb  pop     r15
0x18000f8bd  pop     r14
0x18000f8bf  pop     r13
0x18000f8c1  pop     r12
0x18000f8c3  pop     rdi
0x18000f8c4  pop     rsi
0x18000f8c5  pop     rbp
0x18000f8c6  pop     rbx
0x18000f8c7  retn
0x18000f8c8  mov     ebx, [rsp+0A8h+var_64]
0x18000f8cc  jmp     loc_18000F778
0x18000f8d1  cmp     r9b, 34h ; '4'
0x18000f8d5  movzx   ebp, cl
0x18000f8d8  cmovz   ebp, eax
0x18000f8db  mov     [rsp+0A8h+var_78], ebp
0x18000f8df  mov     ebp, [rsp+0A8h+arg_10]
0x18000f8e6  jmp     loc_18000F531
0x18000f8eb  mov     r8d, r15d
0x18000f8ee  mov     rdx, rsi
0x18000f8f1  call    resizeResolveLabel
0x18000f8f6  jmp     short loc_18000F88D
0x18000f8f8  lea     rdx, aRowValueMisuse; "row value misused"
0x18000f8ff  mov     rcx, rdi
0x18000f902  call    sqlite3ErrorMsg
0x18000f907  jmp     short loc_18000F8B7
0x18000f909  mov     r8d, [rsp+0A8h+arg_10]
0x18000f911  mov     edx, 33h ; '3'
0x18000f916  call    sqlite3VdbeAddOp3
0x18000f91b  jmp     loc_18000F802
0x18000f920  mov     rax, [r12+20h]
0x18000f925  movsxd  rdx, r14d
0x18000f928  shl     rdx, 5
0x18000f92c  mov     rcx, [rax+20h]
0x18000f930  mov     rbp, [rdx+rcx+8]
0x18000f935  mov     ecx, [rsp+0A8h+var_74]
0x18000f939  add     ecx, r14d
0x18000f93c  mov     [rsp+0A8h+arg_8], ecx
0x18000f943  jmp     loc_18000F625
0x18000f948  mov     rax, [r13+20h]
0x18000f94c  movsxd  rcx, r14d
0x18000f94f  shl     rcx, 5
0x18000f953  mov     rax, [rax+20h]
0x18000f957  mov     rbx, [rax+rcx+8]
0x18000f95c  mov     ecx, [rsp+0A8h+var_70]
0x18000f960  add     ecx, r14d
0x18000f963  mov     [rsp+0A8h+arg_0], ecx
0x18000f96a  jmp     loc_18000F668
0x18000f96f  mov     edx, r14d
0x18000f972  mov     rcx, r12
0x18000f975  call    sqlite3VectorFieldSubexpr
0x18000f97a  mov     ecx, [r12+2Ch]
  ... truncated ...
```
