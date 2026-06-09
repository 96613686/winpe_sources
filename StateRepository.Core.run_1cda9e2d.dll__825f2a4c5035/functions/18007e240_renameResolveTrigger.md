# renameResolveTrigger

- ea: `0x18007e240`
- end: `0x18007e4ed`
- name: `renameResolveTrigger`
- size: `685`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x180065620`
- `0x1800659c0`
- `0x18007d6a0`
- `0x18007e570`

## callees

- `0x180002ed0`
- `0x180002fbc`
- `0x18000c850`
- `0x18000ca30`
- `0x18000f820`
- `0x180014434`
- `0x180018600`
- `0x180039850`
- `0x18003f6dc`
- `0x180066468`
- `0x18007e240`
- `0x18007e4f4`

## pseudocode

```c
__int64 __fastcall renameResolveTrigger(unsigned __int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // r13
  int v4; // eax
  __int64 Table; // rax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  _QWORD *i; // rdi
  __int64 v9; // rdx
  __int64 v10; // rax
  _DWORD *v11; // r15
  __int64 v12; // rsi
  int *v13; // rcx
  int v14; // esi
  bool v15; // zf
  __int64 v16; // rdx
  _QWORD *v17; // rsi
  __int128 v19; // [rsp+50h] [rbp-29h] BYREF
  __int128 v20; // [rsp+60h] [rbp-19h]
  __int128 v21; // [rsp+70h] [rbp-9h]
  __int64 v22; // [rsp+80h] [rbp+7h]

  v1 = *(_QWORD *)(a1 + 368);
  v2 = *(_QWORD *)a1;
  v19 = a1;
  v20 = 0;
  v22 = 0;
  v21 = 0;
  v4 = sqlite3SchemaToIndex(v2, *(_QWORD *)(v1 + 48));
  Table = sqlite3FindTable(v2, *(_BYTE **)(v1 + 8), *(_QWORD *)(32LL * v4 + *(_QWORD *)(v2 + 32)));
  *(_QWORD *)(a1 + 184) = Table;
  *(_BYTE *)(a1 + 226) = *(_BYTE *)(v1 + 16);
  if ( Table && (unsigned int)sqlite3ViewGetColumnNames(a1, Table) )
  {
    v6 = 1;
  }
  else
  {
    v7 = *(_QWORD *)(v1 + 24);
    v6 = 0;
    if ( v7 )
      v6 = sqlite3ResolveExprNames(&v19, v7);
  }
  for ( i = *(_QWORD **)(v1 + 56); !v6 && i; i = (_QWORD *)i[10] )
  {
    v9 = i[2];
    if ( v9 )
    {
      sqlite3SelectPrep(a1, v9, &v19);
      if ( *(_DWORD *)(a1 + 52) )
        v6 = *(_DWORD *)(a1 + 24);
    }
    if ( !v6 && i[3] )
    {
      v10 = sqlite3TriggerStepSrc(a1, i);
      v11 = (_DWORD *)v10;
      if ( v10 )
      {
        v12 = sqlite3SelectNew(a1, i[6], v10, 0, 0, 0, 0, 0, 0);
        if ( v12 )
        {
          renameSetENames(i[6], 1);
          sqlite3SelectPrep(a1, v12, 0);
          renameSetENames(i[6], 0);
          v6 = *(_DWORD *)(a1 + 52) != 0;
          if ( i[6] )
            *(_QWORD *)(v12 + 32) = 0;
          *(_QWORD *)(v12 + 40) = 0;
          sqlite3SelectDelete(v2, v12);
        }
        else
        {
          i[6] = 0;
          v6 = 7;
          v11 = 0;
        }
        v13 = (int *)i[4];
        if ( v13 && *v13 > 0 && !v6 )
        {
          v14 = 0;
          do
          {
            if ( (v13[20 * v14 + 9] & 4) != 0 )
              sqlite3SelectPrep(a1, **(_QWORD **)&v13[20 * v14 + 20], 0);
            v13 = (int *)i[4];
            ++v14;
          }
          while ( v14 < *v13 );
        }
        v15 = *(_BYTE *)(v2 + 103) == 0;
        *((_QWORD *)&v19 + 1) = v11;
        if ( v15 )
        {
          if ( !v6 )
          {
            v16 = i[5];
            if ( !v16 || (v6 = sqlite3ResolveExprNames(&v19, v16)) == 0 )
              v6 = sqlite3ResolveExprListNames(&v19, i[6]);
          }
        }
        else
        {
          v6 = 7;
        }
        v17 = (_QWORD *)i[8];
        if ( v17 && !v6 )
        {
          v17[8] = v11;
          *(_QWORD *)&v20 = v17;
          DWORD2(v21) = 512;
          v6 = sqlite3ResolveExprListNames(&v19, *v17);
          if ( !v6 )
          {
            v6 = sqlite3ResolveExprListNames(&v19, v17[2]);
            if ( !v6 )
            {
              v6 = sqlite3ResolveExprNames(&v19, v17[3]);
              if ( !v6 )
                v6 = sqlite3ResolveExprNames(&v19, v17[1]);
            }
          }
          DWORD2(v21) = 0;
        }
        *((_QWORD *)&v19 + 1) = 0;
        sqlite3SrcListDelete(v2, v11);
      }
      else
      {
        v6 = 7;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18007e240  push    rbp
0x18007e242  push    rbx
0x18007e243  push    rsi
0x18007e244  push    rdi
0x18007e245  push    r12
0x18007e247  push    r13
0x18007e249  push    r14
0x18007e24b  push    r15
0x18007e24d  lea     rbp, [rsp-1Fh]
0x18007e252  sub     rsp, 98h
0x18007e259  mov     rdi, [rcx+170h]
0x18007e260  xorps   xmm0, xmm0
0x18007e263  mov     r13, [rcx]
0x18007e266  xor     eax, eax
0x18007e268  movups  [rbp+57h+var_80], xmm0
0x18007e26c  mov     qword ptr [rbp+57h+var_80], rcx
0x18007e270  mov     r14, rcx
0x18007e273  movups  [rbp+57h+var_70], xmm0
0x18007e277  mov     [rbp+57h+var_50], rax
0x18007e27b  mov     rcx, r13
0x18007e27e  movups  [rbp+57h+var_60], xmm0
0x18007e282  mov     rdx, [rdi+30h]
0x18007e286  call    sqlite3SchemaToIndex
0x18007e28b  mov     r8, [r13+20h]
0x18007e28f  mov     rdx, [rdi+8]
0x18007e293  movsxd  rcx, eax
0x18007e296  shl     rcx, 5
0x18007e29a  mov     r8, [rcx+r8]
0x18007e29e  mov     rcx, r13
0x18007e2a1  call    sqlite3FindTable
0x18007e2a6  mov     [r14+0B8h], rax
0x18007e2ad  xor     r12d, r12d
0x18007e2b0  mov     cl, [rdi+10h]
0x18007e2b3  mov     [r14+0E2h], cl
0x18007e2ba  test    rax, rax
0x18007e2bd  jz      short loc_18007E2D5
0x18007e2bf  mov     rdx, rax
0x18007e2c2  mov     rcx, r14
0x18007e2c5  call    sqlite3ViewGetColumnNames
0x18007e2ca  test    eax, eax
0x18007e2cc  jz      short loc_18007E2D5
0x18007e2ce  lea     ebx, [r12+1]
0x18007e2d3  jmp     short loc_18007E2EC
0x18007e2d5  mov     rdx, [rdi+18h]
0x18007e2d9  mov     ebx, r12d
0x18007e2dc  test    rdx, rdx
0x18007e2df  jz      short loc_18007E2EC
0x18007e2e1  lea     rcx, [rbp+57h+var_80]
0x18007e2e5  call    sqlite3ResolveExprNames
0x18007e2ea  mov     ebx, eax
0x18007e2ec  mov     rdi, [rdi+38h]
0x18007e2f0  jmp     loc_18007E4CF
0x18007e2f5  test    rdi, rdi
0x18007e2f8  jz      loc_18007E4D7
0x18007e2fe  mov     rdx, [rdi+10h]
0x18007e302  test    rdx, rdx
0x18007e305  jz      short loc_18007E31D
0x18007e307  lea     r8, [rbp+57h+var_80]
0x18007e30b  mov     rcx, r14
0x18007e30e  call    sqlite3SelectPrep
0x18007e313  cmp     [r14+34h], r12d
0x18007e317  jz      short loc_18007E31D
0x18007e319  mov     ebx, [r14+18h]
0x18007e31d  test    ebx, ebx
0x18007e31f  jnz     loc_18007E4CB
0x18007e325  cmp     [rdi+18h], r12
0x18007e329  jz      loc_18007E4CB
0x18007e32f  mov     rdx, rdi
0x18007e332  mov     rcx, r14
0x18007e335  call    sqlite3TriggerStepSrc
0x18007e33a  mov     r15, rax
0x18007e33d  test    rax, rax
0x18007e340  jz      loc_18007E4C6
0x18007e346  mov     rdx, [rdi+30h]
0x18007e34a  xor     r9d, r9d
0x18007e34d  mov     [rsp+0D0h+var_90], r12
0x18007e352  mov     r8, rax
0x18007e355  mov     [rsp+0D0h+var_98], r12d
0x18007e35a  mov     rcx, r14
0x18007e35d  mov     [rsp+0D0h+var_A0], r12
0x18007e362  mov     [rsp+0D0h+var_A8], r12
0x18007e367  mov     [rsp+0D0h+var_B0], r12
0x18007e36c  call    sqlite3SelectNew
0x18007e371  mov     rsi, rax
0x18007e374  test    rax, rax
0x18007e377  jnz     short loc_18007E385
0x18007e379  mov     [rdi+30h], r12
0x18007e37d  lea     ebx, [rax+7]
0x18007e380  mov     r15, r12
0x18007e383  jmp     short loc_18007E3CF
0x18007e385  mov     rcx, [rdi+30h]
0x18007e389  mov     edx, 1
0x18007e38e  call    renameSetENames
0x18007e393  xor     r8d, r8d
0x18007e396  mov     rdx, rsi
0x18007e399  mov     rcx, r14
0x18007e39c  call    sqlite3SelectPrep
0x18007e3a1  mov     rcx, [rdi+30h]
0x18007e3a5  xor     edx, edx
0x18007e3a7  call    renameSetENames
0x18007e3ac  cmp     [r14+34h], r12d
0x18007e3b0  mov     ebx, r12d
0x18007e3b3  setnz   bl
0x18007e3b6  cmp     [rdi+30h], r12
0x18007e3ba  jz      short loc_18007E3C0
0x18007e3bc  mov     [rsi+20h], r12
0x18007e3c0  mov     rdx, rsi
0x18007e3c3  mov     [rsi+28h], r12
0x18007e3c7  mov     rcx, r13
0x18007e3ca  call    sqlite3SelectDelete
0x18007e3cf  mov     rcx, [rdi+20h]
0x18007e3d3  test    rcx, rcx
0x18007e3d6  jz      short loc_18007E412
0x18007e3d8  cmp     [rcx], r12d
0x18007e3db  jle     short loc_18007E412
0x18007e3dd  test    ebx, ebx
0x18007e3df  jnz     short loc_18007E412
0x18007e3e1  mov     esi, r12d
0x18007e3e4  movsxd  rax, esi
0x18007e3e7  lea     rdx, [rax+rax*4]
0x18007e3eb  add     rdx, rdx
0x18007e3ee  test    byte ptr [rcx+rdx*8+24h], 4
0x18007e3f3  jz      short loc_18007E408
0x18007e3f5  mov     rdx, [rcx+rdx*8+50h]
0x18007e3fa  xor     r8d, r8d
0x18007e3fd  mov     rcx, r14
0x18007e400  mov     rdx, [rdx]
0x18007e403  call    sqlite3SelectPrep
0x18007e408  mov     rcx, [rdi+20h]
0x18007e40c  inc     esi
0x18007e40e  cmp     esi, [rcx]
0x18007e410  jl      short loc_18007E3E4
0x18007e412  cmp     [r13+67h], r12b
0x18007e416  mov     qword ptr [rbp+57h+var_80+8], r15
0x18007e41a  jz      short loc_18007E423
0x18007e41c  mov     ebx, 7
0x18007e421  jmp     short loc_18007E44E
0x18007e423  test    ebx, ebx
0x18007e425  jnz     short loc_18007E44E
0x18007e427  mov     rdx, [rdi+28h]
0x18007e42b  test    rdx, rdx
0x18007e42e  jz      short loc_18007E43F
0x18007e430  lea     rcx, [rbp+57h+var_80]
0x18007e434  call    sqlite3ResolveExprNames
0x18007e439  mov     ebx, eax
0x18007e43b  test    eax, eax
0x18007e43d  jnz     short loc_18007E44E
0x18007e43f  mov     rdx, [rdi+30h]
0x18007e443  lea     rcx, [rbp+57h+var_80]
0x18007e447  call    sqlite3ResolveExprListNames
0x18007e44c  mov     ebx, eax
0x18007e44e  mov     rsi, [rdi+40h]
0x18007e452  test    rsi, rsi
0x18007e455  jz      short loc_18007E4B5
0x18007e457  test    ebx, ebx
0x18007e459  jnz     short loc_18007E4B5
0x18007e45b  mov     [rsi+40h], r15
0x18007e45f  lea     rcx, [rbp+57h+var_80]
0x18007e463  mov     qword ptr [rbp+57h+var_70], rsi
0x18007e467  mov     dword ptr [rbp+57h+var_60+8], 200h
0x18007e46e  mov     rdx, [rsi]
0x18007e471  call    sqlite3ResolveExprListNames
0x18007e476  mov     ebx, eax
0x18007e478  test    eax, eax
0x18007e47a  jnz     short loc_18007E4B1
0x18007e47c  mov     rdx, [rsi+10h]
0x18007e480  lea     rcx, [rbp+57h+var_80]
0x18007e484  call    sqlite3ResolveExprListNames
0x18007e489  mov     ebx, eax
0x18007e48b  test    eax, eax
0x18007e48d  jnz     short loc_18007E4B1
0x18007e48f  mov     rdx, [rsi+18h]
0x18007e493  lea     rcx, [rbp+57h+var_80]
0x18007e497  call    sqlite3ResolveExprNames
0x18007e49c  mov     ebx, eax
0x18007e49e  test    eax, eax
0x18007e4a0  jnz     short loc_18007E4B1
0x18007e4a2  mov     rdx, [rsi+8]
0x18007e4a6  lea     rcx, [rbp+57h+var_80]
0x18007e4aa  call    sqlite3ResolveExprNames
0x18007e4af  mov     ebx, eax
0x18007e4b1  mov     dword ptr [rbp+57h+var_60+8], r12d
0x18007e4b5  mov     rdx, r15
0x18007e4b8  mov     qword ptr [rbp+57h+var_80+8], r12
0x18007e4bc  mov     rcx, r13
0x18007e4bf  call    sqlite3SrcListDelete
0x18007e4c4  jmp     short loc_18007E4CB
0x18007e4c6  mov     ebx, 7
0x18007e4cb  mov     rdi, [rdi+50h]
0x18007e4cf  test    ebx, ebx
0x18007e4d1  jz      loc_18007E2F5
0x18007e4d7  mov     eax, ebx
0x18007e4d9  add     rsp, 98h
0x18007e4e0  pop     r15
0x18007e4e2  pop     r14
0x18007e4e4  pop     r13
0x18007e4e6  pop     r12
0x18007e4e8  pop     rdi
0x18007e4e9  pop     rsi
0x18007e4ea  pop     rbx
0x18007e4eb  pop     rbp
0x18007e4ec  retn
```
