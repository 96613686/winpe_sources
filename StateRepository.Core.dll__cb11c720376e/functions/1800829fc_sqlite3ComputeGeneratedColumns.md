# sqlite3ComputeGeneratedColumns

- ea: `0x1800829fc`
- end: `0x180082be7`
- name: `sqlite3ComputeGeneratedColumns`
- size: `491`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800167c0`
- `0x1800189c8`
- `0x18001a8dc`

## callees

- `0x18000e7f0`
- `0x180036688`
- `0x18005cc60`
- `0x180060ce8`
- `0x18006170c`
- `0x180062c04`
- `0x1800829fc`
- `0x180083948`

## pseudocode

```c
__int64 __fastcall sqlite3ComputeGeneratedColumns(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v6; // rcx
  __int64 Op; // rax
  _BYTE *v8; // r8
  int v9; // edx
  int v10; // r9d
  __int64 v11; // rax
  int i; // ecx
  __int64 v13; // r8
  __int16 v14; // ax
  int v15; // r15d
  const char **v16; // r14
  int v17; // edi
  __int64 result; // rax
  __int64 v19; // rbp
  __int16 v20; // ax
  __int64 v21; // rax
  __int16 v22; // ax
  __int128 v23; // [rsp+20h] [rbp-68h] BYREF
  __int128 v24; // [rsp+30h] [rbp-58h]
  __int128 v25; // [rsp+40h] [rbp-48h]

  v6 = *(_QWORD *)(a1 + 16);
  v23 = 0;
  v24 = 0;
  v25 = 0;
  sqlite3TableAffinity(v6, a3, a2);
  if ( (*(_BYTE *)(a3 + 48) & 0x40) != 0 )
  {
    Op = sqlite3VdbeGetOp(*(_QWORD *)(a1 + 16), (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 16) + 144LL) - 1));
    if ( *(_BYTE *)Op == 96 )
    {
      v8 = *(_BYTE **)(Op + 16);
      v9 = 0;
      v10 = 0;
      if ( *v8 )
      {
        do
        {
          v11 = *(_QWORD *)(a3 + 8);
          if ( (*(_BYTE *)(v11 + 24LL * v10 + 18) & 0x20) == 0 )
          {
            if ( (*(_BYTE *)(v11 + 24LL * v10 + 18) & 0x40) != 0 )
              v8[v9] = 64;
            ++v9;
          }
          ++v10;
        }
        while ( v8[v9] );
      }
    }
    else if ( *(_BYTE *)Op == 95 )
    {
      *(_DWORD *)(Op + 12) = 1;
    }
  }
  for ( i = 0; i < *(__int16 *)(a3 + 54); ++i )
  {
    v13 = *(_QWORD *)(a3 + 8);
    v14 = *(_WORD *)(v13 + 24LL * i + 18);
    if ( (v14 & 0x60) != 0 )
      *(_WORD *)(v13 + 24LL * i + 18) = v14 | 0x80;
  }
  *((_QWORD *)&v25 + 1) = a3;
  *((_QWORD *)&v23 + 1) = exprColumnFlagUnion;
  *(_QWORD *)&v24 = 0;
  *(_DWORD *)(a1 + 68) = -a2;
  *((_QWORD *)&v24 + 1) = 0;
  while ( 1 )
  {
    v15 = 0;
    v16 = 0;
    v17 = 0;
    result = 0;
    if ( *(__int16 *)(a3 + 54) <= 0 )
      break;
    do
    {
      v19 = *(_QWORD *)(a3 + 8) + 24LL * v17;
      v20 = *(_WORD *)(v19 + 18);
      if ( (v20 & 0x80) != 0 )
      {
        *(_WORD *)(v19 + 18) = v20 | 0x100;
        WORD2(v25) = 0;
        v21 = sqlite3ColumnExpr(a3);
        sqlite3WalkExpr(&v23, v21);
        *(_WORD *)(v19 + 18) &= ~0x100u;
        if ( (SBYTE4(v25) & 0x80u) == 0 )
        {
          v15 = 1;
          v22 = sqlite3TableColumnToStorage(a3, (unsigned __int16)v17);
          sqlite3ExprCodeGeneratedColumn(
            a1,
            a3,
            v19,
            a2 + v22,
            v23,
            *((_QWORD *)&v23 + 1),
            v24,
            *((_QWORD *)&v24 + 1),
            v25,
            *((_QWORD *)&v25 + 1));
          *(_WORD *)(v19 + 18) &= ~0x80u;
        }
        else
        {
          v16 = (const char **)v19;
        }
      }
      result = (unsigned int)*(__int16 *)(a3 + 54);
      ++v17;
    }
    while ( v17 < (int)result );
    if ( !v16 )
      break;
    if ( !v15 )
    {
      result = sqlite3ErrorMsg(a1, "generated column loop on \"%s\"", *v16);
      break;
    }
  }
  *(_DWORD *)(a1 + 68) = 0;
  return result;
}

```

## disassembly

```asm
0x1800829fc  push    rbx
0x1800829fe  push    rbp
0x1800829ff  push    rsi
0x180082a00  push    rdi
0x180082a01  push    r12
0x180082a03  push    r14
0x180082a05  push    r15
0x180082a07  sub     rsp, 50h
0x180082a0b  xorps   xmm0, xmm0
0x180082a0e  mov     rbx, r8
0x180082a11  mov     r8d, edx
0x180082a14  mov     r12d, edx
0x180082a17  mov     rsi, rcx
0x180082a1a  mov     rdx, rbx
0x180082a1d  mov     rcx, [rcx+10h]
0x180082a21  movups  [rsp+88h+var_68], xmm0
0x180082a26  movups  [rsp+88h+var_58], xmm0
0x180082a2b  movups  [rsp+88h+var_48], xmm0
0x180082a30  call    sqlite3TableAffinity
0x180082a35  test    byte ptr [rbx+30h], 40h
0x180082a39  mov     edi, 1
0x180082a3e  jz      short loc_180082A9E
0x180082a40  mov     rcx, [rsi+10h]
0x180082a44  mov     edx, [rcx+90h]
0x180082a4a  sub     edx, edi
0x180082a4c  call    sqlite3VdbeGetOp
0x180082a51  cmp     byte ptr [rax], 60h ; '`'
0x180082a54  jnz     short loc_180082A96
0x180082a56  mov     r8, [rax+10h]
0x180082a5a  xor     edx, edx
0x180082a5c  xor     r9d, r9d
0x180082a5f  cmp     [r8], dl
0x180082a62  jz      short loc_180082A9E
0x180082a64  movsxd  rax, r9d
0x180082a67  lea     rcx, [rax+rax*2]
0x180082a6b  mov     rax, [rbx+8]
0x180082a6f  test    byte ptr [rax+rcx*8+12h], 20h
0x180082a74  jnz     short loc_180082A87
0x180082a76  test    byte ptr [rax+rcx*8+12h], 40h
0x180082a7b  jz      short loc_180082A85
0x180082a7d  movsxd  rax, edx
0x180082a80  mov     byte ptr [rax+r8], 40h ; '@'
0x180082a85  add     edx, edi
0x180082a87  movsxd  rax, edx
0x180082a8a  add     r9d, edi
0x180082a8d  cmp     byte ptr [rax+r8], 0
0x180082a92  jnz     short loc_180082A64
0x180082a94  jmp     short loc_180082A9E
0x180082a96  cmp     byte ptr [rax], 5Fh ; '_'
0x180082a99  jnz     short loc_180082A9E
0x180082a9b  mov     [rax+0Ch], edi
0x180082a9e  xor     ecx, ecx
0x180082aa0  xor     eax, eax
0x180082aa2  mov     r9d, 80h
0x180082aa8  cmp     ax, [rbx+36h]
0x180082aac  jge     short loc_180082AD7
0x180082aae  mov     r8, [rbx+8]
0x180082ab2  movsxd  rax, ecx
0x180082ab5  lea     rdx, [rax+rax*2]
0x180082ab9  movzx   eax, word ptr [r8+rdx*8+12h]
0x180082abf  test    al, 60h
0x180082ac1  jz      short loc_180082ACD
0x180082ac3  or      ax, r9w
0x180082ac7  mov     [r8+rdx*8+12h], ax
0x180082acd  movsx   eax, word ptr [rbx+36h]
0x180082ad1  add     ecx, edi
0x180082ad3  cmp     ecx, eax
0x180082ad5  jl      short loc_180082AAE
0x180082ad7  lea     rax, exprColumnFlagUnion
0x180082ade  mov     qword ptr [rsp+88h+var_48+8], rbx
0x180082ae3  mov     qword ptr [rsp+88h+var_68+8], rax
0x180082ae8  mov     eax, r12d
0x180082aeb  neg     eax
0x180082aed  mov     qword ptr [rsp+88h+var_58], 0
0x180082af6  mov     [rsi+44h], eax
0x180082af9  mov     qword ptr [rsp+88h+var_58+8], 0
0x180082b02  xor     r15d, r15d
0x180082b05  xor     r14d, r14d
0x180082b08  xor     edi, edi
0x180082b0a  xor     eax, eax
0x180082b0c  cmp     ax, [rbx+36h]
0x180082b10  jge     loc_180082BD1
0x180082b16  movsxd  rax, edi
0x180082b19  lea     rcx, [rax+rax*2]
0x180082b1d  mov     rax, [rbx+8]
0x180082b21  lea     rbp, [rax+rcx*8]
0x180082b25  movzx   eax, word ptr [rbp+12h]
0x180082b29  test    r9b, al
0x180082b2c  jz      short loc_180082BA3
0x180082b2e  or      ax, 100h
0x180082b32  mov     rdx, rbp
0x180082b35  mov     [rbp+12h], ax
0x180082b39  mov     rcx, rbx
0x180082b3c  xor     eax, eax
0x180082b3e  mov     word ptr [rsp+88h+var_48+4], ax
0x180082b43  call    sqlite3ColumnExpr
0x180082b48  mov     rdx, rax
0x180082b4b  lea     rcx, [rsp+88h+var_68]
0x180082b50  call    sqlite3WalkExpr
0x180082b55  mov     eax, 0FEFFh
0x180082b5a  mov     r9d, 80h
0x180082b60  and     [rbp+12h], ax
0x180082b64  test    byte ptr [rsp+88h+var_48+4], r9b
0x180082b69  jz      short loc_180082B70
0x180082b6b  mov     r14, rbp
0x180082b6e  jmp     short loc_180082BA3
0x180082b70  movzx   edx, di
0x180082b73  mov     rcx, rbx
0x180082b76  mov     r15d, 1
0x180082b7c  call    sqlite3TableColumnToStorage
0x180082b81  movsx   r9d, ax
0x180082b85  mov     r8, rbp
0x180082b88  add     r9d, r12d
0x180082b8b  mov     rdx, rbx
0x180082b8e  mov     rcx, rsi
0x180082b91  call    sqlite3ExprCodeGeneratedColumn
0x180082b96  mov     eax, 0FF7Fh
0x180082b9b  lea     r9d, [r15+7Fh]
0x180082b9f  and     [rbp+12h], ax
0x180082ba3  movsx   eax, word ptr [rbx+36h]
0x180082ba7  inc     edi
0x180082ba9  cmp     edi, eax
0x180082bab  jl      loc_180082B16
0x180082bb1  test    r14, r14
0x180082bb4  jz      short loc_180082BD1
0x180082bb6  test    r15d, r15d
0x180082bb9  jnz     loc_180082B02
0x180082bbf  mov     r8, [r14]
0x180082bc2  lea     rdx, aGeneratedColum_0; "generated column loop on \"%s\""
0x180082bc9  mov     rcx, rsi
0x180082bcc  call    sqlite3ErrorMsg
0x180082bd1  mov     dword ptr [rsi+44h], 0
0x180082bd8  add     rsp, 50h
0x180082bdc  pop     r15
0x180082bde  pop     r14
0x180082be0  pop     r12
0x180082be2  pop     rdi
0x180082be3  pop     rsi
0x180082be4  pop     rbp
0x180082be5  pop     rbx
0x180082be6  retn
```
