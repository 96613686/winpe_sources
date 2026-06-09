# openStatTable

- ea: `0x18006d36c`
- end: `0x18006d517`
- name: `openStatTable`
- size: `427`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180053130`
- `0x180053a9c`

## callees

- `0x18000b4bc`
- `0x18002817c`
- `0x180038974`
- `0x18003cc7c`
- `0x18003d480`
- `0x18004242c`
- `0x180042cd4`
- `0x1800449f0`
- `0x180044fc0`
- `0x18006d36c`

## string_xrefs

- `0x18006d428`: `CREATE TABLE %Q.%s(%s)`
- `0x18006d47f`: `DELETE FROM %Q.%s WHERE %s=%Q`

## pseudocode

```c
__int64 __fastcall openStatTable(__int64 *a1, int a2, int a3, __int64 a4, __int64 a5)
{
  __int64 v6; // rbx
  __int64 v7; // r14
  __int64 result; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rbp
  _QWORD *v12; // rdi
  int i; // ebx
  __int64 v14; // r8
  __int64 v15; // rcx
  char *v16; // r13
  __int64 Table; // rax
  int v18; // r9d
  int v19; // r12d
  _BYTE v20[4]; // [rsp+30h] [rbp-88h]
  int v21; // [rsp+34h] [rbp-84h]
  __int64 v22; // [rsp+38h] [rbp-80h]
  __int64 v23; // [rsp+40h] [rbp-78h]
  __int64 v24; // [rsp+48h] [rbp-70h]
  _DWORD v25[4]; // [rsp+50h] [rbp-68h]

  v6 = *a1;
  v24 = a5;
  v22 = v6;
  v23 = a4;
  v21 = a3;
  v7 = a2;
  result = sqlite3GetVdbe(a1);
  v11 = result;
  if ( result )
  {
    v12 = (_QWORD *)(*(_QWORD *)(v6 + 32) + 32 * v7);
    for ( i = 0; i < 3; ++i )
    {
      if ( (unsigned __int64)i >= 3 )
        _report_rangecheckfailure(v10, v9);
      v14 = *v12;
      v15 = v22;
      v20[i] = 0;
      v16 = off_1800AA490[2 * i];
      Table = sqlite3FindTable(v15, v16, v14);
      if ( Table )
      {
        v19 = *(_DWORD *)(Table + 40);
        LOBYTE(v18) = 1;
        v25[i] = v19;
        sqlite3TableLock((_DWORD)a1, v7, v19, v18, (__int64)v16);
        if ( v23 )
          sqlite3NestedParse(a1, "DELETE FROM %Q.%s WHERE %s=%Q", *v12, v16, v24, v23);
        else
          sqlite3VdbeAddOp3(v11, 145, v19, v7, 0);
      }
      else if ( i < 1 )
      {
        sqlite3NestedParse(a1, "CREATE TABLE %Q.%s(%s)", *v12, v16, off_1800AA490[2 * i + 1]);
        v25[i] = *((_DWORD *)a1 + 35);
        v20[i] = 16;
      }
    }
    sqlite3VdbeAddOp4Int(v11, 113, v21, v25[0], v7, 3);
    return sqlite3VdbeChangeP5(v11, v20[0]);
  }
  return result;
}

```

## disassembly

```asm
0x18006d36c  push    rbx
0x18006d36e  push    rbp
0x18006d36f  push    rsi
0x18006d370  push    rdi
0x18006d371  push    r12
0x18006d373  push    r13
0x18006d375  push    r14
0x18006d377  push    r15
0x18006d379  sub     rsp, 78h
0x18006d37d  mov     rax, cs:__security_cookie
0x18006d384  xor     rax, rsp
0x18006d387  mov     [rsp+0B8h+var_58], rax
0x18006d38c  mov     rax, [rsp+0B8h+arg_20]
0x18006d394  mov     r15, rcx
0x18006d397  mov     rbx, [rcx]
0x18006d39a  mov     [rsp+0B8h+var_70], rax
0x18006d39f  mov     [rsp+0B8h+var_80], rbx
0x18006d3a4  mov     [rsp+0B8h+var_78], r9
0x18006d3a9  mov     [rsp+0B8h+var_84], r8d
0x18006d3ae  movsxd  r14, edx
0x18006d3b1  call    sqlite3GetVdbe
0x18006d3b6  mov     rbp, rax
0x18006d3b9  test    rax, rax
0x18006d3bc  jz      loc_18006D4F9
0x18006d3c2  mov     rdi, r14
0x18006d3c5  shl     rdi, 5
0x18006d3c9  add     rdi, [rbx+20h]
0x18006d3cd  xor     ebx, ebx
0x18006d3cf  lea     rax, off_1800AA490; "sqlite_stat1"
0x18006d3d6  cmp     ebx, 3
0x18006d3d9  jge     loc_18006D4C8
0x18006d3df  movsxd  rsi, ebx
0x18006d3e2  cmp     rsi, 3
0x18006d3e6  jnb     loc_18006D4C2
0x18006d3ec  mov     r8, [rdi]
0x18006d3ef  mov     r12, rsi
0x18006d3f2  mov     rcx, [rsp+0B8h+var_80]
0x18006d3f7  add     r12, r12
0x18006d3fa  mov     [rsp+rsi+0B8h+var_88], 0
0x18006d3ff  mov     r13, [rax+r12*8]
0x18006d403  mov     rdx, r13
0x18006d406  call    sqlite3FindTable
0x18006d40b  test    rax, rax
0x18006d40e  jnz     short loc_18006D451
0x18006d410  cmp     ebx, 1
0x18006d413  jge     loc_18006D4BB
0x18006d419  mov     r8, [rdi]
0x18006d41c  lea     rax, off_1800AA490; "sqlite_stat1"
0x18006d423  mov     rax, [rax+r12*8+8]
0x18006d428  lea     rdx, aCreateTableQSS; "CREATE TABLE %Q.%s(%s)"
0x18006d42f  mov     r9, r13
0x18006d432  mov     [rsp+0B8h+var_98], rax
0x18006d437  mov     rcx, r15
0x18006d43a  call    sqlite3NestedParse
0x18006d43f  mov     eax, [r15+8Ch]
0x18006d446  mov     [rsp+rsi*4+0B8h+var_68], eax
0x18006d44a  mov     [rsp+rsi+0B8h+var_88], 10h
0x18006d44f  jmp     short loc_18006D4BB
0x18006d451  mov     r12d, [rax+28h]
0x18006d455  mov     r9b, 1
0x18006d458  mov     r8d, r12d
0x18006d45b  mov     [rsp+rsi*4+0B8h+var_68], r12d
0x18006d460  mov     edx, r14d
0x18006d463  mov     [rsp+0B8h+var_98], r13
0x18006d468  mov     rcx, r15
0x18006d46b  call    sqlite3TableLock
0x18006d470  mov     rsi, [rsp+0B8h+var_78]
0x18006d475  test    rsi, rsi
0x18006d478  jz      short loc_18006D4A0
0x18006d47a  mov     rax, [rsp+0B8h+var_70]
0x18006d47f  lea     rdx, aDeleteFromQSWh; "DELETE FROM %Q.%s WHERE %s=%Q"
0x18006d486  mov     r8, [rdi]
0x18006d489  mov     r9, r13
0x18006d48c  mov     [rsp+0B8h+var_90], rsi
0x18006d491  mov     rcx, r15
0x18006d494  mov     [rsp+0B8h+var_98], rax
0x18006d499  call    sqlite3NestedParse
0x18006d49e  jmp     short loc_18006D4BB
0x18006d4a0  mov     r9d, r14d
0x18006d4a3  mov     dword ptr [rsp+0B8h+var_98], 0
0x18006d4ab  mov     r8d, r12d
0x18006d4ae  mov     edx, 91h
0x18006d4b3  mov     rcx, rbp
0x18006d4b6  call    sqlite3VdbeAddOp3
0x18006d4bb  inc     ebx
0x18006d4bd  jmp     loc_18006D3CF
0x18006d4c2  call    __report_rangecheckfailure
0x18006d4c8  mov     r9d, [rsp+0B8h+var_68]
0x18006d4cd  mov     edx, 71h ; 'q'
0x18006d4d2  mov     r8d, [rsp+0B8h+var_84]
0x18006d4d7  mov     rcx, rbp
0x18006d4da  mov     dword ptr [rsp+0B8h+var_90], 3
0x18006d4e2  mov     dword ptr [rsp+0B8h+var_98], r14d
0x18006d4e7  call    sqlite3VdbeAddOp4Int
0x18006d4ec  movzx   edx, [rsp+0B8h+var_88]
0x18006d4f1  mov     rcx, rbp
0x18006d4f4  call    sqlite3VdbeChangeP5
0x18006d4f9  mov     rcx, [rsp+0B8h+var_58]
0x18006d4fe  xor     rcx, rsp; StackCookie
0x18006d501  call    __security_check_cookie
0x18006d506  add     rsp, 78h
0x18006d50a  pop     r15
0x18006d50c  pop     r14
0x18006d50e  pop     r13
0x18006d510  pop     r12
0x18006d512  pop     rdi
0x18006d513  pop     rsi
0x18006d514  pop     rbp
0x18006d515  pop     rbx
0x18006d516  retn
```
