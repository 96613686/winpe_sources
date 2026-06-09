# openStatTable

- ea: `0x1800155e4`
- end: `0x18001578f`
- name: `openStatTable`
- size: `427`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1800146b8`
- `0x180015848`

## callees

- `0x180005c54`
- `0x180010810`
- `0x1800119e0`
- `0x180014434`
- `0x1800155e4`
- `0x18003abcc`
- `0x180053ecc`
- `0x180068880`
- `0x1800688c0`
- `0x1800857c4`

## string_xrefs

- `0x1800156a0`: `CREATE TABLE %Q.%s(%s)`
- `0x1800156f7`: `DELETE FROM %Q.%s WHERE %s=%Q`

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
      v14 = off_18009C0E0[2 * i];
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
        sqlite3NestedParse(a1, "CREATE TABLE %Q.%s(%s)", *v10, v14, off_18009C0E0[2 * i + 1]);
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
0x1800155e4  push    rbx
0x1800155e6  push    rbp
0x1800155e7  push    rsi
0x1800155e8  push    rdi
0x1800155e9  push    r12
0x1800155eb  push    r13
0x1800155ed  push    r14
0x1800155ef  push    r15
0x1800155f1  sub     rsp, 78h
0x1800155f5  mov     rax, cs:__security_cookie
0x1800155fc  xor     rax, rsp
0x1800155ff  mov     [rsp+0B8h+var_58], rax
0x180015604  mov     rax, [rsp+0B8h+arg_20]
0x18001560c  mov     r15, rcx
0x18001560f  mov     rbx, [rcx]
0x180015612  mov     [rsp+0B8h+var_70], rax
0x180015617  mov     [rsp+0B8h+var_80], rbx
0x18001561c  mov     [rsp+0B8h+var_78], r9
0x180015621  mov     [rsp+0B8h+var_84], r8d
0x180015626  movsxd  r14, edx
0x180015629  call    sqlite3GetVdbe
0x18001562e  mov     rbp, rax
0x180015631  test    rax, rax
0x180015634  jz      loc_180015771
0x18001563a  mov     rdi, r14
0x18001563d  shl     rdi, 5
0x180015641  add     rdi, [rbx+20h]
0x180015645  xor     ebx, ebx
0x180015647  lea     rax, off_18009C0E0; "sqlite_stat1"
0x18001564e  cmp     ebx, 3
0x180015651  jge     loc_180015740
0x180015657  movsxd  rsi, ebx
0x18001565a  cmp     rsi, 3
0x18001565e  jnb     loc_18001573A
0x180015664  mov     r8, [rdi]
0x180015667  mov     r12, rsi
0x18001566a  mov     rcx, [rsp+0B8h+var_80]
0x18001566f  add     r12, r12
0x180015672  mov     [rsp+rsi+0B8h+var_88], 0
0x180015677  mov     r13, [rax+r12*8]
0x18001567b  mov     rdx, r13
0x18001567e  call    sqlite3FindTable
0x180015683  test    rax, rax
0x180015686  jnz     short loc_1800156C9
0x180015688  cmp     ebx, 1
0x18001568b  jge     loc_180015733
0x180015691  mov     r8, [rdi]
0x180015694  lea     rax, off_18009C0E0; "sqlite_stat1"
0x18001569b  mov     rax, [rax+r12*8+8]
0x1800156a0  lea     rdx, aCreateTableQSS; "CREATE TABLE %Q.%s(%s)"
0x1800156a7  mov     r9, r13
0x1800156aa  mov     [rsp+0B8h+var_98], rax
0x1800156af  mov     rcx, r15
0x1800156b2  call    sqlite3NestedParse
0x1800156b7  mov     eax, [r15+8Ch]
0x1800156be  mov     [rsp+rsi*4+0B8h+var_68], eax
0x1800156c2  mov     [rsp+rsi+0B8h+var_88], 10h
0x1800156c7  jmp     short loc_180015733
0x1800156c9  mov     r12d, [rax+28h]
0x1800156cd  mov     r9b, 1
0x1800156d0  mov     r8d, r12d
0x1800156d3  mov     [rsp+rsi*4+0B8h+var_68], r12d
0x1800156d8  mov     edx, r14d
0x1800156db  mov     [rsp+0B8h+var_98], r13
0x1800156e0  mov     rcx, r15
0x1800156e3  call    sqlite3TableLock
0x1800156e8  mov     rsi, [rsp+0B8h+var_78]
0x1800156ed  test    rsi, rsi
0x1800156f0  jz      short loc_180015718
0x1800156f2  mov     rax, [rsp+0B8h+var_70]
0x1800156f7  lea     rdx, aDeleteFromQSWh; "DELETE FROM %Q.%s WHERE %s=%Q"
0x1800156fe  mov     r8, [rdi]
0x180015701  mov     r9, r13
0x180015704  mov     [rsp+0B8h+var_90], rsi
0x180015709  mov     rcx, r15
0x18001570c  mov     [rsp+0B8h+var_98], rax
0x180015711  call    sqlite3NestedParse
0x180015716  jmp     short loc_180015733
0x180015718  mov     r9d, r14d
0x18001571b  mov     dword ptr [rsp+0B8h+var_98], 0
0x180015723  mov     r8d, r12d
0x180015726  mov     edx, 91h
0x18001572b  mov     rcx, rbp
0x18001572e  call    sqlite3VdbeAddOp3
0x180015733  inc     ebx
0x180015735  jmp     loc_180015647
0x18001573a  call    __report_rangecheckfailure
0x180015740  mov     r9d, [rsp+0B8h+var_68]
0x180015745  mov     edx, 71h ; 'q'
0x18001574a  mov     r8d, [rsp+0B8h+var_84]
0x18001574f  mov     rcx, rbp
0x180015752  mov     dword ptr [rsp+0B8h+var_90], 3
0x18001575a  mov     dword ptr [rsp+0B8h+var_98], r14d
0x18001575f  call    sqlite3VdbeAddOp4Int
0x180015764  movzx   edx, [rsp+0B8h+var_88]
0x180015769  mov     rcx, rbp
0x18001576c  call    sqlite3VdbeChangeP5
0x180015771  mov     rcx, [rsp+0B8h+var_58]
0x180015776  xor     rcx, rsp; StackCookie
0x180015779  call    __security_check_cookie
0x18001577e  add     rsp, 78h
0x180015782  pop     r15
0x180015784  pop     r14
0x180015786  pop     r13
0x180015788  pop     r12
0x18001578a  pop     rdi
0x18001578b  pop     rsi
0x18001578c  pop     rbp
0x18001578d  pop     rbx
0x18001578e  retn
```
