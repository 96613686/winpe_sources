# renameResolveTrigger

- ea: `0x18008d5b0`
- end: `0x18008d850`
- name: `renameResolveTrigger`
- size: `672`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x1800774f0`
- `0x1800777f0`
- `0x18008ca10`
- `0x18008d8d0`

## callees

- `0x180001980`
- `0x18000509c`
- `0x1800087d0`
- `0x18000a180`
- `0x18000a754`
- `0x180018d00`
- `0x180018e10`
- `0x18001b818`
- `0x18001f418`
- `0x18008d5b0`
- `0x18008d858`
- `0x180098920`

## pseudocode

```c
__int64 __fastcall renameResolveTrigger(unsigned __int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // r13
  unsigned int ColumnNames; // ebx
  int v5; // eax
  __int64 Table; // rax
  __int64 v7; // rdx
  _QWORD *i; // rdi
  __int64 v9; // rdx
  __int64 v10; // rax
  int *v11; // r15
  __int64 *v12; // rsi
  int *v13; // rdx
  int v14; // esi
  __int64 v15; // rdx
  bool v16; // zf
  __int64 v17; // rdx
  _QWORD *v18; // rsi
  __int128 v20; // [rsp+50h] [rbp-29h] BYREF
  __int128 v21; // [rsp+60h] [rbp-19h]
  __int128 v22; // [rsp+70h] [rbp-9h]
  __int64 v23; // [rsp+80h] [rbp+7h]

  v1 = *(_QWORD *)(a1 + 368);
  v2 = *(_QWORD *)a1;
  v20 = a1;
  v21 = 0;
  v23 = 0;
  v22 = 0;
  ColumnNames = 0;
  v5 = sqlite3SchemaToIndex(v2, *(_QWORD *)(v1 + 48));
  Table = sqlite3FindTable(v2, *(unsigned __int8 **)(v1 + 8), *(_BYTE **)(32LL * v5 + *(_QWORD *)(v2 + 32)));
  *(_QWORD *)(a1 + 184) = Table;
  *(_BYTE *)(a1 + 226) = *(_BYTE *)(v1 + 16);
  if ( !Table || (ColumnNames = sqlite3ViewGetColumnNames(a1, Table)) == 0 )
  {
    v7 = *(_QWORD *)(v1 + 24);
    if ( v7 )
      ColumnNames = sqlite3ResolveExprNames(&v20, v7);
  }
  for ( i = *(_QWORD **)(v1 + 56); !ColumnNames && i; i = (_QWORD *)i[10] )
  {
    v9 = i[2];
    if ( v9 )
    {
      sqlite3SelectPrep(a1, v9, &v20);
      if ( *(_DWORD *)(a1 + 48) )
        ColumnNames = *(_DWORD *)(a1 + 24);
    }
    if ( !ColumnNames && i[3] )
    {
      v10 = sqlite3TriggerStepSrc(a1, i);
      v11 = (int *)v10;
      if ( v10 )
      {
        v12 = (__int64 *)sqlite3SelectNew(a1, i[6], v10, 0, 0, 0, 0, 0, 0);
        if ( v12 )
        {
          renameSetENames(i[6], 1);
          sqlite3SelectPrep(a1, v12, 0);
          renameSetENames(i[6], 0);
          ColumnNames = *(_DWORD *)(a1 + 48) != 0;
          if ( i[6] )
            v12[4] = 0;
          v12[5] = 0;
          sqlite3SelectDelete((_QWORD *)v2, v12);
        }
        else
        {
          i[6] = 0;
          ColumnNames = 7;
          v11 = 0;
        }
        v13 = (int *)i[4];
        if ( v13 && *v13 > 0 && !ColumnNames )
        {
          v14 = 0;
          do
          {
            v15 = *(_QWORD *)&v13[26 * v14 + 12];
            if ( v15 )
              sqlite3SelectPrep(a1, v15, 0);
            v13 = (int *)i[4];
            ++v14;
          }
          while ( v14 < *v13 );
        }
        v16 = *(_BYTE *)(v2 + 103) == 0;
        *((_QWORD *)&v20 + 1) = v11;
        if ( v16 )
        {
          if ( !ColumnNames )
          {
            v17 = i[5];
            if ( !v17 || (ColumnNames = sqlite3ResolveExprNames(&v20, v17)) == 0 )
              ColumnNames = sqlite3ResolveExprListNames(&v20, i[6]);
          }
        }
        else
        {
          ColumnNames = 7;
        }
        v18 = (_QWORD *)i[8];
        if ( v18 && !ColumnNames )
        {
          v18[8] = v11;
          *(_QWORD *)&v21 = v18;
          DWORD2(v22) = 512;
          ColumnNames = sqlite3ResolveExprListNames(&v20, *v18);
          if ( !ColumnNames )
          {
            ColumnNames = sqlite3ResolveExprListNames(&v20, v18[2]);
            if ( !ColumnNames )
            {
              ColumnNames = sqlite3ResolveExprNames(&v20, v18[3]);
              if ( !ColumnNames )
                ColumnNames = sqlite3ResolveExprNames(&v20, v18[1]);
            }
          }
          DWORD2(v22) = 0;
        }
        *((_QWORD *)&v20 + 1) = 0;
        sqlite3SrcListDelete((_QWORD *)v2, v11);
      }
      else
      {
        ColumnNames = 7;
      }
    }
  }
  return ColumnNames;
}

```

## disassembly

```asm
0x18008d5b0  push    rbp
0x18008d5b2  push    rbx
0x18008d5b3  push    rsi
0x18008d5b4  push    rdi
0x18008d5b5  push    r12
0x18008d5b7  push    r13
0x18008d5b9  push    r14
0x18008d5bb  push    r15
0x18008d5bd  lea     rbp, [rsp-1Fh]
0x18008d5c2  sub     rsp, 98h
0x18008d5c9  mov     rdi, [rcx+170h]
0x18008d5d0  xorps   xmm0, xmm0
0x18008d5d3  mov     r13, [rcx]
0x18008d5d6  xor     eax, eax
0x18008d5d8  movups  [rbp+57h+var_80], xmm0
0x18008d5dc  mov     qword ptr [rbp+57h+var_80], rcx
0x18008d5e0  mov     r14, rcx
0x18008d5e3  movups  [rbp+57h+var_70], xmm0
0x18008d5e7  mov     [rbp+57h+var_50], rax
0x18008d5eb  xor     r12d, r12d
0x18008d5ee  movups  [rbp+57h+var_60], xmm0
0x18008d5f2  mov     rdx, [rdi+30h]
0x18008d5f6  mov     rcx, r13
0x18008d5f9  mov     ebx, r12d
0x18008d5fc  call    sqlite3SchemaToIndex
0x18008d601  mov     r8, [r13+20h]
0x18008d605  mov     rdx, [rdi+8]
0x18008d609  movsxd  rcx, eax
0x18008d60c  shl     rcx, 5
0x18008d610  mov     r8, [rcx+r8]
0x18008d614  mov     rcx, r13
0x18008d617  call    sqlite3FindTable
0x18008d61c  mov     [r14+0B8h], rax
0x18008d623  mov     cl, [rdi+10h]
0x18008d626  mov     [r14+0E2h], cl
0x18008d62d  test    rax, rax
0x18008d630  jz      short loc_18008D643
0x18008d632  mov     rdx, rax
0x18008d635  mov     rcx, r14
0x18008d638  call    sqlite3ViewGetColumnNames
0x18008d63d  mov     ebx, eax
0x18008d63f  test    eax, eax
0x18008d641  jnz     short loc_18008D657
0x18008d643  mov     rdx, [rdi+18h]
0x18008d647  test    rdx, rdx
0x18008d64a  jz      short loc_18008D657
0x18008d64c  lea     rcx, [rbp+57h+var_80]
0x18008d650  call    sqlite3ResolveExprNames
0x18008d655  mov     ebx, eax
0x18008d657  mov     rdi, [rdi+38h]
0x18008d65b  jmp     loc_18008D832
0x18008d660  test    rdi, rdi
0x18008d663  jz      loc_18008D83A
0x18008d669  mov     rdx, [rdi+10h]
0x18008d66d  test    rdx, rdx
0x18008d670  jz      short loc_18008D688
0x18008d672  lea     r8, [rbp+57h+var_80]
0x18008d676  mov     rcx, r14
0x18008d679  call    sqlite3SelectPrep
0x18008d67e  cmp     [r14+30h], r12d
0x18008d682  jz      short loc_18008D688
0x18008d684  mov     ebx, [r14+18h]
0x18008d688  test    ebx, ebx
0x18008d68a  jnz     loc_18008D82E
0x18008d690  cmp     [rdi+18h], r12
0x18008d694  jz      loc_18008D82E
0x18008d69a  mov     rdx, rdi
0x18008d69d  mov     rcx, r14
0x18008d6a0  call    sqlite3TriggerStepSrc
0x18008d6a5  mov     r15, rax
0x18008d6a8  test    rax, rax
0x18008d6ab  jz      loc_18008D829
0x18008d6b1  mov     rdx, [rdi+30h]
0x18008d6b5  xor     r9d, r9d
0x18008d6b8  mov     [rsp+0D0h+var_90], r12
0x18008d6bd  mov     r8, rax
0x18008d6c0  mov     [rsp+0D0h+var_98], r12d
0x18008d6c5  mov     rcx, r14
0x18008d6c8  mov     [rsp+0D0h+var_A0], r12
0x18008d6cd  mov     [rsp+0D0h+var_A8], r12
0x18008d6d2  mov     [rsp+0D0h+var_B0], r12
0x18008d6d7  call    sqlite3SelectNew
0x18008d6dc  mov     rsi, rax
0x18008d6df  test    rax, rax
0x18008d6e2  jnz     short loc_18008D6F0
0x18008d6e4  mov     [rdi+30h], r12
0x18008d6e8  lea     ebx, [rax+7]
0x18008d6eb  mov     r15, r12
0x18008d6ee  jmp     short loc_18008D73A
0x18008d6f0  mov     rcx, [rdi+30h]
0x18008d6f4  mov     edx, 1
0x18008d6f9  call    renameSetENames
0x18008d6fe  xor     r8d, r8d
0x18008d701  mov     rdx, rsi
0x18008d704  mov     rcx, r14
0x18008d707  call    sqlite3SelectPrep
0x18008d70c  mov     rcx, [rdi+30h]
0x18008d710  xor     edx, edx
0x18008d712  call    renameSetENames
0x18008d717  cmp     [r14+30h], r12d
0x18008d71b  mov     ebx, r12d
0x18008d71e  setnz   bl
0x18008d721  cmp     [rdi+30h], r12
0x18008d725  jz      short loc_18008D72B
0x18008d727  mov     [rsi+20h], r12
0x18008d72b  mov     rdx, rsi
0x18008d72e  mov     [rsi+28h], r12
0x18008d732  mov     rcx, r13
0x18008d735  call    sqlite3SelectDelete
0x18008d73a  mov     rdx, [rdi+20h]
0x18008d73e  test    rdx, rdx
0x18008d741  jz      short loc_18008D775
0x18008d743  cmp     [rdx], r12d
0x18008d746  jle     short loc_18008D775
0x18008d748  test    ebx, ebx
0x18008d74a  jnz     short loc_18008D775
0x18008d74c  mov     esi, r12d
0x18008d74f  movsxd  rax, esi
0x18008d752  imul    rcx, rax, 68h ; 'h'
0x18008d756  mov     rdx, [rcx+rdx+30h]
0x18008d75b  test    rdx, rdx
0x18008d75e  jz      short loc_18008D76B
0x18008d760  xor     r8d, r8d
0x18008d763  mov     rcx, r14
0x18008d766  call    sqlite3SelectPrep
0x18008d76b  mov     rdx, [rdi+20h]
0x18008d76f  inc     esi
0x18008d771  cmp     esi, [rdx]
0x18008d773  jl      short loc_18008D74F
0x18008d775  cmp     [r13+67h], r12b
0x18008d779  mov     qword ptr [rbp+57h+var_80+8], r15
0x18008d77d  jz      short loc_18008D786
0x18008d77f  mov     ebx, 7
0x18008d784  jmp     short loc_18008D7B1
0x18008d786  test    ebx, ebx
0x18008d788  jnz     short loc_18008D7B1
0x18008d78a  mov     rdx, [rdi+28h]
0x18008d78e  test    rdx, rdx
0x18008d791  jz      short loc_18008D7A2
0x18008d793  lea     rcx, [rbp+57h+var_80]
0x18008d797  call    sqlite3ResolveExprNames
0x18008d79c  mov     ebx, eax
0x18008d79e  test    eax, eax
0x18008d7a0  jnz     short loc_18008D7B1
0x18008d7a2  mov     rdx, [rdi+30h]
0x18008d7a6  lea     rcx, [rbp+57h+var_80]
0x18008d7aa  call    sqlite3ResolveExprListNames
0x18008d7af  mov     ebx, eax
0x18008d7b1  mov     rsi, [rdi+40h]
0x18008d7b5  test    rsi, rsi
0x18008d7b8  jz      short loc_18008D818
0x18008d7ba  test    ebx, ebx
0x18008d7bc  jnz     short loc_18008D818
0x18008d7be  mov     [rsi+40h], r15
0x18008d7c2  lea     rcx, [rbp+57h+var_80]
0x18008d7c6  mov     qword ptr [rbp+57h+var_70], rsi
0x18008d7ca  mov     dword ptr [rbp+57h+var_60+8], 200h
0x18008d7d1  mov     rdx, [rsi]
0x18008d7d4  call    sqlite3ResolveExprListNames
0x18008d7d9  mov     ebx, eax
0x18008d7db  test    eax, eax
0x18008d7dd  jnz     short loc_18008D814
0x18008d7df  mov     rdx, [rsi+10h]
0x18008d7e3  lea     rcx, [rbp+57h+var_80]
0x18008d7e7  call    sqlite3ResolveExprListNames
0x18008d7ec  mov     ebx, eax
0x18008d7ee  test    eax, eax
0x18008d7f0  jnz     short loc_18008D814
0x18008d7f2  mov     rdx, [rsi+18h]
0x18008d7f6  lea     rcx, [rbp+57h+var_80]
0x18008d7fa  call    sqlite3ResolveExprNames
0x18008d7ff  mov     ebx, eax
0x18008d801  test    eax, eax
0x18008d803  jnz     short loc_18008D814
0x18008d805  mov     rdx, [rsi+8]
0x18008d809  lea     rcx, [rbp+57h+var_80]
0x18008d80d  call    sqlite3ResolveExprNames
0x18008d812  mov     ebx, eax
0x18008d814  mov     dword ptr [rbp+57h+var_60+8], r12d
0x18008d818  mov     rdx, r15
0x18008d81b  mov     qword ptr [rbp+57h+var_80+8], r12
0x18008d81f  mov     rcx, r13
0x18008d822  call    sqlite3SrcListDelete
0x18008d827  jmp     short loc_18008D82E
0x18008d829  mov     ebx, 7
0x18008d82e  mov     rdi, [rdi+50h]
0x18008d832  test    ebx, ebx
0x18008d834  jz      loc_18008D660
0x18008d83a  mov     eax, ebx
0x18008d83c  add     rsp, 98h
0x18008d843  pop     r15
0x18008d845  pop     r14
0x18008d847  pop     r13
0x18008d849  pop     r12
0x18008d84b  pop     rdi
0x18008d84c  pop     rsi
0x18008d84d  pop     rbx
0x18008d84e  pop     rbp
0x18008d84f  retn
```
