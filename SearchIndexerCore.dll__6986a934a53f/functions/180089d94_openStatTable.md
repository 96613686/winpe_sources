# openStatTable

- ea: `0x180089d94`
- end: `0x180089f3f`
- name: `openStatTable`
- size: `427`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180079760`
- `0x18007a0cc`

## callees

- `0x180008be8`
- `0x180009ac0`
- `0x18000a180`
- `0x180015eb0`
- `0x1800168c0`
- `0x18004a9b8`
- `0x1800588ac`
- `0x1800789c0`
- `0x180078a00`
- `0x180089d94`

## string_xrefs

- `0x180089e50`: `CREATE TABLE %Q.%s(%s)`
- `0x180089ea7`: `DELETE FROM %Q.%s WHERE %s=%Q`

## pseudocode

```c
__int64 __fastcall openStatTable(__int64 *a1, int a2, int a3, __int64 a4, __int64 a5)
{
  __int64 v6; // rbx
  __int64 v7; // r14
  __int64 result; // rax
  __int64 v9; // rbp
  _QWORD *v10; // rdi
  int i; // ebx
  __int64 v12; // r8
  __int64 v13; // rcx
  char *v14; // r13
  __int64 Table; // rax
  __int64 v16; // r9
  unsigned int v17; // r12d
  _BYTE v18[4]; // [rsp+30h] [rbp-88h]
  int v19; // [rsp+34h] [rbp-84h]
  __int64 v20; // [rsp+38h] [rbp-80h]
  __int64 v21; // [rsp+40h] [rbp-78h]
  __int64 v22; // [rsp+48h] [rbp-70h]
  _DWORD v23[4]; // [rsp+50h] [rbp-68h]

  v6 = *a1;
  v22 = a5;
  v20 = v6;
  v21 = a4;
  v19 = a3;
  v7 = a2;
  result = sqlite3GetVdbe(a1);
  v9 = result;
  if ( result )
  {
    v10 = (_QWORD *)(*(_QWORD *)(v6 + 32) + 32 * v7);
    for ( i = 0; i < 3; ++i )
    {
      if ( (unsigned __int64)i >= 3 )
        _report_rangecheckfailure();
      v12 = *v10;
      v13 = v20;
      v18[i] = 0;
      v14 = off_1800B29B0[2 * i];
      Table = sqlite3FindTable(v13, v14, v12);
      if ( Table )
      {
        v17 = *(_DWORD *)(Table + 40);
        LOBYTE(v16) = 1;
        v23[i] = v17;
        sqlite3TableLock(a1, (unsigned int)v7, v17, v16, v14);
        if ( v21 )
          sqlite3NestedParse(a1, "DELETE FROM %Q.%s WHERE %s=%Q", *v10, v14, v22, v21);
        else
          sqlite3VdbeAddOp3(v9, 145, v17, v7, 0);
      }
      else if ( i < 1 )
      {
        sqlite3NestedParse(a1, "CREATE TABLE %Q.%s(%s)", *v10, v14, off_1800B29B0[2 * i + 1]);
        v23[i] = *((_DWORD *)a1 + 35);
        v18[i] = 16;
      }
    }
    sqlite3VdbeAddOp4Int(v9, 113, v19, v23[0], v7, 3);
    return sqlite3VdbeChangeP5(v9, v18[0]);
  }
  return result;
}

```

## disassembly

```asm
0x180089d94  push    rbx
0x180089d96  push    rbp
0x180089d97  push    rsi
0x180089d98  push    rdi
0x180089d99  push    r12
0x180089d9b  push    r13
0x180089d9d  push    r14
0x180089d9f  push    r15
0x180089da1  sub     rsp, 78h
0x180089da5  mov     rax, cs:__security_cookie
0x180089dac  xor     rax, rsp
0x180089daf  mov     [rsp+0B8h+var_58], rax
0x180089db4  mov     rax, [rsp+0B8h+arg_20]
0x180089dbc  mov     r15, rcx
0x180089dbf  mov     rbx, [rcx]
0x180089dc2  mov     [rsp+0B8h+var_70], rax
0x180089dc7  mov     [rsp+0B8h+var_80], rbx
0x180089dcc  mov     [rsp+0B8h+var_78], r9
0x180089dd1  mov     [rsp+0B8h+var_84], r8d
0x180089dd6  movsxd  r14, edx
0x180089dd9  call    sqlite3GetVdbe
0x180089dde  mov     rbp, rax
0x180089de1  test    rax, rax
0x180089de4  jz      loc_180089F21
0x180089dea  mov     rdi, r14
0x180089ded  shl     rdi, 5
0x180089df1  add     rdi, [rbx+20h]
0x180089df5  xor     ebx, ebx
0x180089df7  lea     rax, off_1800B29B0; "sqlite_stat1"
0x180089dfe  cmp     ebx, 3
0x180089e01  jge     loc_180089EF0
0x180089e07  movsxd  rsi, ebx
0x180089e0a  cmp     rsi, 3
0x180089e0e  jnb     loc_180089EEA
0x180089e14  mov     r8, [rdi]
0x180089e17  mov     r12, rsi
0x180089e1a  mov     rcx, [rsp+0B8h+var_80]
0x180089e1f  add     r12, r12
0x180089e22  mov     [rsp+rsi+0B8h+var_88], 0
0x180089e27  mov     r13, [rax+r12*8]
0x180089e2b  mov     rdx, r13
0x180089e2e  call    sqlite3FindTable
0x180089e33  test    rax, rax
0x180089e36  jnz     short loc_180089E79
0x180089e38  cmp     ebx, 1
0x180089e3b  jge     loc_180089EE3
0x180089e41  mov     r8, [rdi]
0x180089e44  lea     rax, off_1800B29B0; "sqlite_stat1"
0x180089e4b  mov     rax, [rax+r12*8+8]
0x180089e50  lea     rdx, aCreateTableQSS; "CREATE TABLE %Q.%s(%s)"
0x180089e57  mov     r9, r13
0x180089e5a  mov     [rsp+0B8h+var_98], rax
0x180089e5f  mov     rcx, r15
0x180089e62  call    sqlite3NestedParse
0x180089e67  mov     eax, [r15+8Ch]
0x180089e6e  mov     [rsp+rsi*4+0B8h+var_68], eax
0x180089e72  mov     [rsp+rsi+0B8h+var_88], 10h
0x180089e77  jmp     short loc_180089EE3
0x180089e79  mov     r12d, [rax+28h]
0x180089e7d  mov     r9b, 1
0x180089e80  mov     r8d, r12d
0x180089e83  mov     [rsp+rsi*4+0B8h+var_68], r12d
0x180089e88  mov     edx, r14d
0x180089e8b  mov     [rsp+0B8h+var_98], r13
0x180089e90  mov     rcx, r15
0x180089e93  call    sqlite3TableLock
0x180089e98  mov     rsi, [rsp+0B8h+var_78]
0x180089e9d  test    rsi, rsi
0x180089ea0  jz      short loc_180089EC8
0x180089ea2  mov     rax, [rsp+0B8h+var_70]
0x180089ea7  lea     rdx, aDeleteFromQSWh; "DELETE FROM %Q.%s WHERE %s=%Q"
0x180089eae  mov     r8, [rdi]
0x180089eb1  mov     r9, r13
0x180089eb4  mov     [rsp+0B8h+var_90], rsi
0x180089eb9  mov     rcx, r15
0x180089ebc  mov     [rsp+0B8h+var_98], rax
0x180089ec1  call    sqlite3NestedParse
0x180089ec6  jmp     short loc_180089EE3
0x180089ec8  mov     r9d, r14d
0x180089ecb  mov     dword ptr [rsp+0B8h+var_98], 0
0x180089ed3  mov     r8d, r12d
0x180089ed6  mov     edx, 91h
0x180089edb  mov     rcx, rbp
0x180089ede  call    sqlite3VdbeAddOp3
0x180089ee3  inc     ebx
0x180089ee5  jmp     loc_180089DF7
0x180089eea  call    __report_rangecheckfailure
0x180089ef0  mov     r9d, [rsp+0B8h+var_68]
0x180089ef5  mov     edx, 71h ; 'q'
0x180089efa  mov     r8d, [rsp+0B8h+var_84]
0x180089eff  mov     rcx, rbp
0x180089f02  mov     dword ptr [rsp+0B8h+var_90], 3
0x180089f0a  mov     dword ptr [rsp+0B8h+var_98], r14d
0x180089f0f  call    sqlite3VdbeAddOp4Int
0x180089f14  movzx   edx, [rsp+0B8h+var_88]
0x180089f19  mov     rcx, rbp
0x180089f1c  call    sqlite3VdbeChangeP5
0x180089f21  mov     rcx, [rsp+0B8h+var_58]
0x180089f26  xor     rcx, rsp; StackCookie
0x180089f29  call    __security_check_cookie
0x180089f2e  add     rsp, 78h
0x180089f32  pop     r15
0x180089f34  pop     r14
0x180089f36  pop     r13
0x180089f38  pop     r12
0x180089f3a  pop     rdi
0x180089f3b  pop     rsi
0x180089f3c  pop     rbp
0x180089f3d  pop     rbx
0x180089f3e  retn
```
