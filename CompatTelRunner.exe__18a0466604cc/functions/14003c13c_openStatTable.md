# openStatTable

- ea: `0x14003c13c`
- end: `0x14003c2df`
- name: `openStatTable`
- size: `419`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14001c538`
- `0x14001ce94`

## callees

- `0x140001e80`
- `0x14003c13c`
- `0x14005ae90`
- `0x14005f5fc`
- `0x14006348c`
- `0x140070918`
- `0x1400738a0`
- `0x14007399c`

## string_xrefs

- `0x14003c1df`: `CREATE TABLE %Q.%s(%s)`
- `0x14003c234`: `DELETE FROM %Q.%s WHERE %s=%Q`

## pseudocode

```c
__int64 __fastcall openStatTable(__int64 *a1, int a2, int a3, __int64 a4, __int64 a5)
{
  __int64 v6; // rbx
  __int64 v7; // r14
  __int64 result; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rsi
  _QWORD *v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // r8
  __int64 v15; // rcx
  char *v16; // r13
  __int64 Table; // rax
  int v18; // r9d
  int v19; // r12d
  __int64 v20; // rcx
  _BYTE v21[4]; // [rsp+30h] [rbp-78h]
  int v22; // [rsp+34h] [rbp-74h]
  __int64 v23; // [rsp+38h] [rbp-70h]
  __int64 v24; // [rsp+40h] [rbp-68h]
  __int64 v25; // [rsp+48h] [rbp-60h]
  _DWORD v26[22]; // [rsp+50h] [rbp-58h]

  v6 = *a1;
  v25 = a5;
  v23 = v6;
  v24 = a4;
  v22 = a3;
  v7 = a2;
  result = sqlite3GetVdbe(a1);
  v11 = result;
  if ( result )
  {
    v12 = (_QWORD *)(*(_QWORD *)(v6 + 32) + 32 * v7);
    v13 = 0;
    do
    {
      if ( (unsigned int)v13 >= 3uLL )
        _report_rangecheckfailure(v10, v9);
      v14 = *v12;
      v15 = v23;
      v21[v13] = 0;
      v16 = off_1400AA360[2 * (unsigned int)v13];
      Table = sqlite3FindTable(v15, v16, v14);
      if ( Table )
      {
        v19 = *(_DWORD *)(Table + 40);
        LOBYTE(v18) = 1;
        v26[v13] = v19;
        sqlite3TableLock((_DWORD)a1, v7, v19, v18, (__int64)v16);
        if ( v24 )
          sqlite3NestedParse(a1, "DELETE FROM %Q.%s WHERE %s=%Q", *v12, v16, v25, v24);
        else
          sqlite3VdbeAddOp3(v11, 145, v19, v7, 0);
      }
      else if ( !(_DWORD)v13 )
      {
        sqlite3NestedParse(a1, "CREATE TABLE %Q.%s(%s)", *v12, v16, off_1400AA360[2 * (unsigned int)v13 + 1]);
        v26[v13] = *((_DWORD *)a1 + 33);
        v21[v13] = 16;
      }
      v13 = (unsigned int)(v13 + 1);
    }
    while ( (int)v13 < 3 );
    sqlite3VdbeAddOp4Int(v11, 113, v22, v26[0], v7, 3);
    result = *(int *)(v11 + 144);
    if ( (int)result > 0 )
    {
      v20 = 3 * result;
      result = *(_QWORD *)(v11 + 136);
      *(_WORD *)(result + 8 * v20 - 22) = v21[0];
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003c13c  push    rbx
0x14003c13e  push    rbp
0x14003c13f  push    rsi
0x14003c140  push    rdi
0x14003c141  push    r12
0x14003c143  push    r13
0x14003c145  push    r14
0x14003c147  push    r15
0x14003c149  sub     rsp, 68h
0x14003c14d  mov     rax, [rsp+0A8h+arg_20]
0x14003c155  mov     r15, rcx
0x14003c158  mov     rbx, [rcx]
0x14003c15b  mov     [rsp+0A8h+var_60], rax
0x14003c160  mov     [rsp+0A8h+var_70], rbx
0x14003c165  mov     [rsp+0A8h+var_68], r9
0x14003c16a  mov     [rsp+0A8h+var_74], r8d
0x14003c16f  movsxd  r14, edx
0x14003c172  call    sqlite3GetVdbe
0x14003c177  mov     rsi, rax
0x14003c17a  test    rax, rax
0x14003c17d  jz      loc_14003C2C8
0x14003c183  mov     rdi, r14
0x14003c186  lea     rax, off_1400AA360; "sqlite_stat1"
0x14003c18d  shl     rdi, 5
0x14003c191  add     rdi, [rbx+20h]
0x14003c195  xor     ebx, ebx
0x14003c197  mov     ebp, ebx
0x14003c199  cmp     rbp, 3
0x14003c19d  jnb     loc_14003C2D9
0x14003c1a3  mov     r8, [rdi]
0x14003c1a6  mov     r12d, ebp
0x14003c1a9  mov     rcx, [rsp+0A8h+var_70]
0x14003c1ae  add     r12, r12
0x14003c1b1  mov     [rsp+rbx+0A8h+var_78], 0
0x14003c1b6  mov     r13, [rax+r12*8]
0x14003c1ba  mov     rdx, r13
0x14003c1bd  call    sqlite3FindTable
0x14003c1c2  test    rax, rax
0x14003c1c5  jnz     short loc_14003C208
0x14003c1c7  cmp     ebx, 1
0x14003c1ca  jnb     loc_14003C272
0x14003c1d0  mov     r8, [rdi]
0x14003c1d3  lea     rax, off_1400AA360; "sqlite_stat1"
0x14003c1da  mov     rax, [rax+r12*8+8]
0x14003c1df  lea     rdx, aCreateTableQSS; "CREATE TABLE %Q.%s(%s)"
0x14003c1e6  mov     r9, r13
0x14003c1e9  mov     [rsp+0A8h+var_88], rax
0x14003c1ee  mov     rcx, r15
0x14003c1f1  call    sqlite3NestedParse
0x14003c1f6  mov     eax, [r15+84h]
0x14003c1fd  mov     [rsp+rbx*4+0A8h+var_58], eax
0x14003c201  mov     [rsp+rbx+0A8h+var_78], 10h
0x14003c206  jmp     short loc_14003C272
0x14003c208  mov     r12d, [rax+28h]
0x14003c20c  mov     r9b, 1
0x14003c20f  mov     r8d, r12d
0x14003c212  mov     [rsp+rbx*4+0A8h+var_58], r12d
0x14003c217  mov     edx, r14d
0x14003c21a  mov     [rsp+0A8h+var_88], r13
0x14003c21f  mov     rcx, r15
0x14003c222  call    sqlite3TableLock
0x14003c227  mov     rax, [rsp+0A8h+var_68]
0x14003c22c  test    rax, rax
0x14003c22f  jz      short loc_14003C257
0x14003c231  mov     r8, [rdi]
0x14003c234  lea     rdx, aDeleteFromQSWh; "DELETE FROM %Q.%s WHERE %s=%Q"
0x14003c23b  mov     [rsp+0A8h+var_80], rax
0x14003c240  mov     r9, r13
0x14003c243  mov     rax, [rsp+0A8h+var_60]
0x14003c248  mov     rcx, r15
0x14003c24b  mov     [rsp+0A8h+var_88], rax
0x14003c250  call    sqlite3NestedParse
0x14003c255  jmp     short loc_14003C272
0x14003c257  mov     r9d, r14d
0x14003c25a  mov     dword ptr [rsp+0A8h+var_88], 0
0x14003c262  mov     r8d, r12d
0x14003c265  mov     edx, 91h
0x14003c26a  mov     rcx, rsi
0x14003c26d  call    sqlite3VdbeAddOp3
0x14003c272  inc     ebx
0x14003c274  lea     rax, off_1400AA360; "sqlite_stat1"
0x14003c27b  cmp     ebx, 3
0x14003c27e  jl      loc_14003C197
0x14003c284  mov     r9d, [rsp+0A8h+var_58]
0x14003c289  mov     edx, 71h ; 'q'
0x14003c28e  mov     r8d, [rsp+0A8h+var_74]
0x14003c293  mov     rcx, rsi
0x14003c296  mov     dword ptr [rsp+0A8h+var_80], 3
0x14003c29e  mov     dword ptr [rsp+0A8h+var_88], r14d
0x14003c2a3  call    sqlite3VdbeAddOp4Int
0x14003c2a8  movsxd  rax, dword ptr [rsi+90h]
0x14003c2af  test    eax, eax
0x14003c2b1  jle     short loc_14003C2C8
0x14003c2b3  movzx   edx, [rsp+0A8h+var_78]
0x14003c2b8  lea     rcx, [rax+rax*2]
0x14003c2bc  mov     rax, [rsi+88h]
0x14003c2c3  mov     [rax+rcx*8-16h], dx
0x14003c2c8  add     rsp, 68h
0x14003c2cc  pop     r15
0x14003c2ce  pop     r14
0x14003c2d0  pop     r13
0x14003c2d2  pop     r12
0x14003c2d4  pop     rdi
0x14003c2d5  pop     rsi
0x14003c2d6  pop     rbp
0x14003c2d7  pop     rbx
0x14003c2d8  retn
0x14003c2d9  call    __report_rangecheckfailure
```
