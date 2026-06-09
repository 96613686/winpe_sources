# sqlite3GenerateRowDelete

- ea: `0x18001c254`
- end: `0x18001c611`
- name: `sqlite3GenerateRowDelete`
- size: `957`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x180019e50`
- `0x18001a8dc`

## callees

- `0x180005c54`
- `0x1800119e0`
- `0x180014b90`
- `0x180016250`
- `0x180018544`
- `0x18001861c`
- `0x18001bdf0`
- `0x18001bee8`
- `0x18001c254`
- `0x18001c618`
- `0x18001c6f8`
- `0x1800351c8`
- `0x1800370c0`
- `0x18003abcc`
- `0x180054de8`
- `0x180062c04`
- `0x180067068`
- `0x18006f250`

## pseudocode

```c
__int64 __fastcall sqlite3GenerateRowDelete(
        __int64 a1,
        __int16 *a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        __int16 a7,
        char a8,
        unsigned __int8 a9,
        char a10,
        int a11)
{
  __int64 v11; // rbp
  int v12; // r14d
  int v15; // r12d
  int v18; // r13d
  int v19; // ebx
  int v20; // eax
  int v21; // edx
  signed int v22; // ebx
  int v23; // r14d
  __int16 v24; // ax
  int v25; // ebx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 i; // rbx
  __int64 v30; // rax
  unsigned int v32; // [rsp+90h] [rbp+8h]
  int v33; // [rsp+98h] [rbp+10h]

  v11 = *(_QWORD *)(a1 + 16);
  v12 = -1;
  --*(_DWORD *)(a1 + 72);
  v15 = *((_DWORD *)a2 + 12) & 0x80;
  v32 = *(_DWORD *)(a1 + 72);
  if ( !a10 )
    sqlite3VdbeAddOp4Int(v11, v15 != 0 ? 28 : 31, a4, *(_DWORD *)(a1 + 72), a6, a7);
  if ( (unsigned int)sqlite3FkRequired(a1, a2, 0, 0) || (v18 = 0, a3) )
  {
    v19 = sqlite3TriggerColmask(a1, a3, 0, 0, 3, (__int64)a2, a9);
    v20 = sqlite3FkOldmask(a1, a2);
    v21 = *(_DWORD *)(a1 + 60);
    v33 = v20 | v19;
    v18 = v21 + 1;
    *(_DWORD *)(a1 + 60) = a2[27] + 1 + v21;
    sqlite3VdbeAddOp3(v11, 80, a6, v21 + 1, 0);
    v22 = 0;
    if ( a2[27] > 0 )
    {
      v23 = v33;
      do
      {
        if ( v33 == -1 || v22 <= 31 && _bittest(&v23, v22) )
        {
          v24 = sqlite3TableColumnToStorage(a2, (unsigned __int16)v22);
          sqlite3ExprCodeGetColumnOfTable(v11, (_DWORD)a2, a4, v22, v18 + v24 + 1);
        }
        ++v22;
      }
      while ( v22 < a2[27] );
      v12 = -1;
    }
    v25 = *(_DWORD *)(v11 + 144);
    sqlite3CodeRowTrigger(a1, a3, 129, 0, 1, (__int64)a2, v18, a9, v32);
    if ( v25 >= *(_DWORD *)(v11 + 144) )
      v12 = a11;
    else
      sqlite3VdbeAddOp4Int(v11, v15 != 0 ? 28 : 31, a4, v32, a6, a7);
    sqlite3FkCheck(a1, (_DWORD)a2, v18, 0, 0, 0);
  }
  else
  {
    v12 = a11;
  }
  if ( *((_BYTE *)a2 + 63) != 2 )
  {
    sqlite3GenerateRowIndexDelete(a1, (_DWORD)a2, a4, a5, 0, v12);
    sqlite3VdbeAddOp3(v11, 130, a4, a8 != 0, 0);
    if ( !*(_BYTE *)(a1 + 30) || !(unsigned int)sqlite3_stricmp(*(_QWORD *)a2, "sqlite_stat1") )
      sqlite3VdbeAppendP4(v11, a2, 4294967291LL);
    if ( a10 )
      sqlite3VdbeChangeP5(v11, 4, v26, v27);
    if ( v12 >= 0 && v12 != a4 )
      sqlite3VdbeAddOp3(v11, 130, v12, 0, 0);
    v28 = 2;
    if ( a10 != 2 )
      LOWORD(v28) = 0;
    sqlite3VdbeChangeP5(v11, v28, v26, v27);
  }
  if ( (*(_DWORD *)(*(_QWORD *)a1 + 48LL) & 0x4000LL) != 0 )
  {
    for ( i = *(_QWORD *)(findElementWithHash(*((_QWORD *)a2 + 12) + 80LL, *(_QWORD *)a2, 0) + 16);
          i;
          i = *(_QWORD *)(i + 24) )
    {
      v30 = fkActionTrigger(a1, a2, i, 0);
      if ( v30 )
        sqlite3CodeRowTriggerDirect(a1, v30, (_DWORD)a2, v18, 2, 0);
    }
  }
  if ( a3 )
    sqlite3CodeRowTrigger(a1, a3, 129, 0, 2, (__int64)a2, v18, a9, v32);
  return sqlite3VdbeResolveLabel(v11, v32);
}

```

## disassembly

```asm
0x18001c254  mov     [rsp+arg_18], rbx
0x18001c259  mov     [rsp+arg_10], r8
0x18001c25e  push    rbp
0x18001c25f  push    rsi
0x18001c260  push    rdi
0x18001c261  push    r12
0x18001c263  push    r13
0x18001c265  push    r14
0x18001c267  push    r15
0x18001c269  sub     rsp, 50h
0x18001c26d  mov     rbp, [rcx+10h]
0x18001c271  or      r14d, 0FFFFFFFFh
0x18001c275  add     [rcx+48h], r14d
0x18001c279  mov     rbx, r8
0x18001c27c  mov     r12d, [rdx+30h]
0x18001c280  mov     r15d, r9d
0x18001c283  mov     r8d, [rcx+48h]
0x18001c287  and     r12d, 80h
0x18001c28e  cmp     [rsp+88h+arg_48], 0
0x18001c296  mov     rdi, rdx
0x18001c299  mov     rsi, rcx
0x18001c29c  mov     [rsp+88h+arg_0], r8d
0x18001c2a4  jnz     short loc_18001C2D8
0x18001c2a6  movsx   ecx, [rsp+88h+arg_30]
0x18001c2ae  mov     eax, r12d
0x18001c2b1  neg     eax
0x18001c2b3  mov     dword ptr [rsp+88h+var_60], ecx
0x18001c2b7  mov     eax, [rsp+88h+arg_28]
0x18001c2be  mov     r9d, r8d
0x18001c2c1  sbb     edx, edx
0x18001c2c3  mov     dword ptr [rsp+88h+var_68], eax
0x18001c2c7  and     edx, 0FFFFFFFDh
0x18001c2ca  mov     r8d, r15d
0x18001c2cd  add     edx, 1Fh
0x18001c2d0  mov     rcx, rbp
0x18001c2d3  call    sqlite3VdbeAddOp4Int
0x18001c2d8  xor     r9d, r9d
0x18001c2db  xor     r8d, r8d
0x18001c2de  mov     rdx, rdi
0x18001c2e1  mov     rcx, rsi
0x18001c2e4  call    sqlite3FkRequired
0x18001c2e9  test    eax, eax
0x18001c2eb  jnz     short loc_18001C305
0x18001c2ed  xor     r13d, r13d
0x18001c2f0  test    rbx, rbx
0x18001c2f3  jnz     short loc_18001C305
0x18001c2f5  mov     r14d, [rsp+88h+arg_50]
0x18001c2fd  xor     r12d, r12d
0x18001c300  jmp     loc_18001C47B
0x18001c305  movzx   eax, [rsp+88h+arg_40]
0x18001c30d  xor     r9d, r9d
0x18001c310  mov     [rsp+88h+var_58], eax
0x18001c314  xor     r8d, r8d
0x18001c317  mov     [rsp+88h+var_60], rdi
0x18001c31c  mov     rdx, rbx
0x18001c31f  mov     rcx, rsi
0x18001c322  mov     dword ptr [rsp+88h+var_68], 3
0x18001c32a  call    sqlite3TriggerColmask
0x18001c32f  mov     rdx, rdi
0x18001c332  mov     rcx, rsi
0x18001c335  mov     ebx, eax
0x18001c337  call    sqlite3FkOldmask
0x18001c33c  mov     edx, [rsi+3Ch]
0x18001c33f  or      ebx, eax
0x18001c341  movsx   ecx, word ptr [rdi+36h]
0x18001c345  mov     r8d, [rsp+88h+arg_28]
0x18001c34d  inc     ecx
0x18001c34f  mov     [rsp+88h+arg_8], ebx
0x18001c356  lea     r13d, [rdx+1]
0x18001c35a  mov     dword ptr [rsp+88h+var_68], 0
0x18001c362  add     edx, ecx
0x18001c364  mov     r9d, r13d
0x18001c367  mov     [rsi+3Ch], edx
0x18001c36a  mov     rcx, rbp
0x18001c36d  mov     edx, 50h ; 'P'
0x18001c372  call    sqlite3VdbeAddOp3
0x18001c377  xor     eax, eax
0x18001c379  xor     ebx, ebx
0x18001c37b  cmp     ax, [rdi+36h]
0x18001c37f  jge     short loc_18001C3CE
0x18001c381  mov     r14d, [rsp+88h+arg_8]
0x18001c389  cmp     r14d, 0FFFFFFFFh
0x18001c38d  jz      short loc_18001C39A
0x18001c38f  cmp     ebx, 1Fh
0x18001c392  jg      short loc_18001C3C0
0x18001c394  bt      r14d, ebx
0x18001c398  jnb     short loc_18001C3C0
0x18001c39a  movzx   edx, bx
0x18001c39d  mov     rcx, rdi
0x18001c3a0  call    sqlite3TableColumnToStorage
0x18001c3a5  cwde
0x18001c3a6  mov     r9d, ebx
0x18001c3a9  inc     eax
0x18001c3ab  mov     r8d, r15d
0x18001c3ae  add     eax, r13d
0x18001c3b1  mov     rdx, rdi
0x18001c3b4  mov     rcx, rbp
0x18001c3b7  mov     dword ptr [rsp+88h+var_68], eax
0x18001c3bb  call    sqlite3ExprCodeGetColumnOfTable
0x18001c3c0  movsx   eax, word ptr [rdi+36h]
0x18001c3c4  inc     ebx
0x18001c3c6  cmp     ebx, eax
0x18001c3c8  jl      short loc_18001C389
0x18001c3ca  or      r14d, 0FFFFFFFFh
0x18001c3ce  mov     eax, [rsp+88h+arg_0]
0x18001c3d5  xor     r9d, r9d
0x18001c3d8  mov     rdx, [rsp+88h+arg_10]
0x18001c3e0  mov     r8d, 81h
0x18001c3e6  mov     ebx, [rbp+90h]
0x18001c3ec  mov     rcx, rsi
0x18001c3ef  mov     [rsp+88h+var_48], eax
0x18001c3f3  movzx   eax, [rsp+88h+arg_40]
0x18001c3fb  mov     [rsp+88h+var_50], eax
0x18001c3ff  mov     [rsp+88h+var_58], r13d
0x18001c404  mov     [rsp+88h+var_60], rdi
0x18001c409  mov     dword ptr [rsp+88h+var_68], 1
0x18001c411  call    sqlite3CodeRowTrigger
0x18001c416  cmp     ebx, [rbp+90h]
0x18001c41c  jge     short loc_18001C455
0x18001c41e  movsx   eax, [rsp+88h+arg_30]
0x18001c426  neg     r12d
0x18001c429  mov     r9d, [rsp+88h+arg_0]
0x18001c431  mov     r8d, r15d
0x18001c434  sbb     edx, edx
0x18001c436  mov     dword ptr [rsp+88h+var_60], eax
0x18001c43a  mov     eax, [rsp+88h+arg_28]
0x18001c441  and     edx, 0FFFFFFFDh
0x18001c444  add     edx, 1Fh
0x18001c447  mov     dword ptr [rsp+88h+var_68], eax
0x18001c44b  mov     rcx, rbp
0x18001c44e  call    sqlite3VdbeAddOp4Int
0x18001c453  jmp     short loc_18001C45D
0x18001c455  mov     r14d, [rsp+88h+arg_50]
0x18001c45d  xor     r12d, r12d
0x18001c460  xor     r9d, r9d
0x18001c463  mov     dword ptr [rsp+88h+var_60], r12d
0x18001c468  mov     r8d, r13d
0x18001c46b  mov     rdx, rdi
0x18001c46e  mov     [rsp+88h+var_68], r12
0x18001c473  mov     rcx, rsi
0x18001c476  call    sqlite3FkCheck
0x18001c47b  cmp     byte ptr [rdi+3Fh], 2
0x18001c47f  jz      loc_18001C541
0x18001c485  mov     r9d, [rsp+88h+arg_20]
0x18001c48d  mov     r8d, r15d
0x18001c490  mov     dword ptr [rsp+88h+var_60], r14d
0x18001c495  mov     rdx, rdi
0x18001c498  mov     rcx, rsi
0x18001c49b  mov     [rsp+88h+var_68], r12
0x18001c4a0  call    sqlite3GenerateRowIndexDelete
0x18001c4a5  cmp     [rsp+88h+arg_38], r12b
0x18001c4ad  mov     r9d, r12d
0x18001c4b0  mov     r8d, r15d
0x18001c4b3  mov     dword ptr [rsp+88h+var_68], r12d
0x18001c4b8  setnz   r9b
0x18001c4bc  mov     edx, 82h
0x18001c4c1  mov     rcx, rbp
0x18001c4c4  call    sqlite3VdbeAddOp3
0x18001c4c9  cmp     [rsi+1Eh], r12b
0x18001c4cd  jz      short loc_18001C4E2
0x18001c4cf  mov     rcx, [rdi]
0x18001c4d2  lea     rdx, aSqliteStat1; "sqlite_stat1"
0x18001c4d9  call    sqlite3_stricmp
0x18001c4de  test    eax, eax
0x18001c4e0  jnz     short loc_18001C4F3
0x18001c4e2  mov     r8d, 0FFFFFFFBh
0x18001c4e8  mov     rdx, rdi
0x18001c4eb  mov     rcx, rbp
0x18001c4ee  call    sqlite3VdbeAppendP4
0x18001c4f3  mov     bl, [rsp+88h+arg_48]
0x18001c4fa  test    bl, bl
0x18001c4fc  jz      short loc_18001C50B
0x18001c4fe  mov     edx, 4
0x18001c503  mov     rcx, rbp
0x18001c506  call    sqlite3VdbeChangeP5
0x18001c50b  test    r14d, r14d
0x18001c50e  js      short loc_18001C52D
0x18001c510  cmp     r14d, r15d
0x18001c513  jz      short loc_18001C52D
0x18001c515  xor     r9d, r9d
0x18001c518  mov     dword ptr [rsp+88h+var_68], r12d
0x18001c51d  mov     r8d, r14d
0x18001c520  mov     edx, 82h
0x18001c525  mov     rcx, rbp
0x18001c528  call    sqlite3VdbeAddOp3
0x18001c52d  mov     edx, 2
0x18001c532  mov     rcx, rbp
0x18001c535  cmp     bl, dl
0x18001c537  cmovnz  dx, r12w
0x18001c53c  call    sqlite3VdbeChangeP5
0x18001c541  mov     rax, [rsi]
0x18001c544  mov     ecx, [rax+30h]
0x18001c547  bt      rcx, 0Eh
0x18001c54c  jnb     short loc_18001C5A4
0x18001c54e  mov     rcx, [rdi+60h]
0x18001c552  xor     r8d, r8d
0x18001c555  mov     rdx, [rdi]
0x18001c558  add     rcx, 50h ; 'P'
0x18001c55c  call    findElementWithHash
0x18001c561  mov     rbx, [rax+10h]
0x18001c565  jmp     short loc_18001C59F
0x18001c567  xor     r9d, r9d
0x18001c56a  mov     r8, rbx
0x18001c56d  mov     rdx, rdi
0x18001c570  mov     rcx, rsi
0x18001c573  call    fkActionTrigger
0x18001c578  test    rax, rax
0x18001c57b  jz      short loc_18001C59B
0x18001c57d  mov     dword ptr [rsp+88h+var_60], r12d
0x18001c582  mov     r9d, r13d
0x18001c585  mov     r8, rdi
0x18001c588  mov     dword ptr [rsp+88h+var_68], 2
0x18001c590  mov     rdx, rax
0x18001c593  mov     rcx, rsi
0x18001c596  call    sqlite3CodeRowTriggerDirect
0x18001c59b  mov     rbx, [rbx+18h]
0x18001c59f  test    rbx, rbx
0x18001c5a2  jnz     short loc_18001C567
0x18001c5a4  mov     rdx, [rsp+88h+arg_10]
0x18001c5ac  test    rdx, rdx
0x18001c5af  jz      short loc_18001C5EB
0x18001c5b1  movzx   eax, [rsp+88h+arg_40]
0x18001c5b9  xor     r9d, r9d
0x18001c5bc  mov     ecx, [rsp+88h+arg_0]
0x18001c5c3  mov     r8d, 81h
0x18001c5c9  mov     [rsp+88h+var_48], ecx
0x18001c5cd  mov     rcx, rsi
0x18001c5d0  mov     [rsp+88h+var_50], eax
0x18001c5d4  mov     [rsp+88h+var_58], r13d
0x18001c5d9  mov     [rsp+88h+var_60], rdi
0x18001c5de  mov     dword ptr [rsp+88h+var_68], 2
0x18001c5e6  call    sqlite3CodeRowTrigger
0x18001c5eb  mov     edx, [rsp+88h+arg_0]
0x18001c5f2  mov     rcx, rbp
0x18001c5f5  mov     rbx, [rsp+88h+arg_18]
0x18001c5fd  add     rsp, 50h
0x18001c601  pop     r15
0x18001c603  pop     r14
0x18001c605  pop     r13
0x18001c607  pop     r12
0x18001c609  pop     rdi
0x18001c60a  pop     rsi
0x18001c60b  pop     rbp
0x18001c60c  jmp     sqlite3VdbeResolveLabel
```
