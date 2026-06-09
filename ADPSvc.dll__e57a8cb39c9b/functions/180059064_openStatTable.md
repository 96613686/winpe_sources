# openStatTable

- ea: `0x180059064`
- end: `0x180059207`
- name: `openStatTable`
- size: `419`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180036a78`
- `0x180037414`

## callees

- `0x1800028f0`
- `0x180059064`
- `0x180078c74`
- `0x18007d478`
- `0x1800817f4`
- `0x18008f3d8`
- `0x1800923d8`
- `0x1800924d4`

## string_xrefs

- `0x18005915c`: `DELETE FROM %Q.%s WHERE %s=%Q`
- `0x180059107`: `CREATE TABLE %Q.%s(%s)`

## pseudocode

```c
__int64 __fastcall openStatTable(__int64 *a1, int a2, int a3, __int64 a4, __int64 a5)
{
  __int64 v6; // rbx
  __int64 v7; // r14
  __int64 result; // rax
  __int64 v9; // rsi
  _QWORD *v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // r8
  __int64 v13; // rcx
  char *v14; // r13
  __int64 Table; // rax
  int v16; // r9d
  int v17; // r12d
  __int64 v18; // rcx
  _BYTE v19[4]; // [rsp+30h] [rbp-78h]
  int v20; // [rsp+34h] [rbp-74h]
  __int64 v21; // [rsp+38h] [rbp-70h]
  __int64 v22; // [rsp+40h] [rbp-68h]
  __int64 v23; // [rsp+48h] [rbp-60h]
  _DWORD v24[22]; // [rsp+50h] [rbp-58h]

  v6 = *a1;
  v23 = a5;
  v21 = v6;
  v22 = a4;
  v20 = a3;
  v7 = a2;
  result = sqlite3GetVdbe(a1);
  v9 = result;
  if ( result )
  {
    v10 = (_QWORD *)(*(_QWORD *)(v6 + 32) + 32 * v7);
    v11 = 0;
    do
    {
      if ( (unsigned int)v11 >= 3uLL )
        _report_rangecheckfailure();
      v12 = *v10;
      v13 = v21;
      v19[v11] = 0;
      v14 = off_1800CC980[2 * (unsigned int)v11];
      Table = sqlite3FindTable(v13, v14, v12);
      if ( Table )
      {
        v17 = *(_DWORD *)(Table + 40);
        LOBYTE(v16) = 1;
        v24[v11] = v17;
        sqlite3TableLock((_DWORD)a1, v7, v17, v16, (__int64)v14);
        if ( v22 )
          sqlite3NestedParse(a1, "DELETE FROM %Q.%s WHERE %s=%Q", *v10, v14, v23, v22);
        else
          sqlite3VdbeAddOp3(v9, 145, v17, v7, 0);
      }
      else if ( !(_DWORD)v11 )
      {
        sqlite3NestedParse(a1, "CREATE TABLE %Q.%s(%s)", *v10, v14, off_1800CC980[2 * (unsigned int)v11 + 1]);
        v24[v11] = *((_DWORD *)a1 + 35);
        v19[v11] = 16;
      }
      v11 = (unsigned int)(v11 + 1);
    }
    while ( (int)v11 < 3 );
    sqlite3VdbeAddOp4Int(v9, 113, v20, v24[0], v7, 3);
    result = *(int *)(v9 + 144);
    if ( (int)result > 0 )
    {
      v18 = 3 * result;
      result = *(_QWORD *)(v9 + 136);
      *(_WORD *)(result + 8 * v18 - 22) = v19[0];
    }
  }
  return result;
}

```

## disassembly

```asm
0x180059064  push    rbx
0x180059066  push    rbp
0x180059067  push    rsi
0x180059068  push    rdi
0x180059069  push    r12
0x18005906b  push    r13
0x18005906d  push    r14
0x18005906f  push    r15
0x180059071  sub     rsp, 68h
0x180059075  mov     rax, [rsp+0A8h+arg_20]
0x18005907d  mov     r15, rcx
0x180059080  mov     rbx, [rcx]
0x180059083  mov     [rsp+0A8h+var_60], rax
0x180059088  mov     [rsp+0A8h+var_70], rbx
0x18005908d  mov     [rsp+0A8h+var_68], r9
0x180059092  mov     [rsp+0A8h+var_74], r8d
0x180059097  movsxd  r14, edx
0x18005909a  call    sqlite3GetVdbe
0x18005909f  mov     rsi, rax
0x1800590a2  test    rax, rax
0x1800590a5  jz      loc_1800591F0
0x1800590ab  mov     rdi, r14
0x1800590ae  lea     rax, off_1800CC980; "sqlite_stat1"
0x1800590b5  shl     rdi, 5
0x1800590b9  add     rdi, [rbx+20h]
0x1800590bd  xor     ebx, ebx
0x1800590bf  mov     ebp, ebx
0x1800590c1  cmp     rbp, 3
0x1800590c5  jnb     loc_180059201
0x1800590cb  mov     r8, [rdi]
0x1800590ce  mov     r12d, ebp
0x1800590d1  mov     rcx, [rsp+0A8h+var_70]
0x1800590d6  add     r12, r12
0x1800590d9  mov     [rsp+rbx+0A8h+var_78], 0
0x1800590de  mov     r13, [rax+r12*8]
0x1800590e2  mov     rdx, r13
0x1800590e5  call    sqlite3FindTable
0x1800590ea  test    rax, rax
0x1800590ed  jnz     short loc_180059130
0x1800590ef  cmp     ebx, 1
0x1800590f2  jnb     loc_18005919A
0x1800590f8  mov     r8, [rdi]
0x1800590fb  lea     rax, off_1800CC980; "sqlite_stat1"
0x180059102  mov     rax, [rax+r12*8+8]
0x180059107  lea     rdx, aCreateTableQSS; "CREATE TABLE %Q.%s(%s)"
0x18005910e  mov     r9, r13
0x180059111  mov     [rsp+0A8h+var_88], rax
0x180059116  mov     rcx, r15
0x180059119  call    sqlite3NestedParse
0x18005911e  mov     eax, [r15+8Ch]
0x180059125  mov     [rsp+rbx*4+0A8h+var_58], eax
0x180059129  mov     [rsp+rbx+0A8h+var_78], 10h
0x18005912e  jmp     short loc_18005919A
0x180059130  mov     r12d, [rax+28h]
0x180059134  mov     r9b, 1
0x180059137  mov     r8d, r12d
0x18005913a  mov     [rsp+rbx*4+0A8h+var_58], r12d
0x18005913f  mov     edx, r14d
0x180059142  mov     [rsp+0A8h+var_88], r13
0x180059147  mov     rcx, r15
0x18005914a  call    sqlite3TableLock
0x18005914f  mov     rax, [rsp+0A8h+var_68]
0x180059154  test    rax, rax
0x180059157  jz      short loc_18005917F
0x180059159  mov     r8, [rdi]
0x18005915c  lea     rdx, aDeleteFromQSWh; "DELETE FROM %Q.%s WHERE %s=%Q"
0x180059163  mov     [rsp+0A8h+var_80], rax
0x180059168  mov     r9, r13
0x18005916b  mov     rax, [rsp+0A8h+var_60]
0x180059170  mov     rcx, r15
0x180059173  mov     [rsp+0A8h+var_88], rax
0x180059178  call    sqlite3NestedParse
0x18005917d  jmp     short loc_18005919A
0x18005917f  mov     r9d, r14d
0x180059182  mov     dword ptr [rsp+0A8h+var_88], 0
0x18005918a  mov     r8d, r12d
0x18005918d  mov     edx, 91h
0x180059192  mov     rcx, rsi
0x180059195  call    sqlite3VdbeAddOp3
0x18005919a  inc     ebx
0x18005919c  lea     rax, off_1800CC980; "sqlite_stat1"
0x1800591a3  cmp     ebx, 3
0x1800591a6  jl      loc_1800590BF
0x1800591ac  mov     r9d, [rsp+0A8h+var_58]
0x1800591b1  mov     edx, 71h ; 'q'
0x1800591b6  mov     r8d, [rsp+0A8h+var_74]
0x1800591bb  mov     rcx, rsi
0x1800591be  mov     dword ptr [rsp+0A8h+var_80], 3
0x1800591c6  mov     dword ptr [rsp+0A8h+var_88], r14d
0x1800591cb  call    sqlite3VdbeAddOp4Int
0x1800591d0  movsxd  rax, dword ptr [rsi+90h]
0x1800591d7  test    eax, eax
0x1800591d9  jle     short loc_1800591F0
0x1800591db  movzx   edx, [rsp+0A8h+var_78]
0x1800591e0  lea     rcx, [rax+rax*2]
0x1800591e4  mov     rax, [rsi+88h]
0x1800591eb  mov     [rax+rcx*8-16h], dx
0x1800591f0  add     rsp, 68h
0x1800591f4  pop     r15
0x1800591f6  pop     r14
0x1800591f8  pop     r13
0x1800591fa  pop     r12
0x1800591fc  pop     rdi
0x1800591fd  pop     rsi
0x1800591fe  pop     rbp
0x1800591ff  pop     rbx
0x180059200  retn
0x180059201  call    __report_rangecheckfailure
```
