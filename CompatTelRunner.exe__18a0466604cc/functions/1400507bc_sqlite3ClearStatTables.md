# sqlite3ClearStatTables

- ea: `0x1400507bc`
- end: `0x140050864`
- name: `sqlite3ClearStatTables`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140055194`
- `0x140055380`

## callees

- `0x140001ba0`
- `0x1400507bc`
- `0x14005ae90`
- `0x14006348c`
- `0x14008ccd0`

## string_xrefs

- `0x140050836`: `DELETE FROM %Q.%s WHERE %s=%Q`

## pseudocode

```c
__int64 __fastcall sqlite3ClearStatTables(__int64 *a1, int a2, __int64 a3, __int64 a4)
{
  int v7; // ebx
  __int64 v8; // rsi
  __int64 result; // rax
  _BYTE v10[24]; // [rsp+30h] [rbp-48h] BYREF

  v7 = 1;
  v8 = *(_QWORD *)(32LL * a2 + *(_QWORD *)(*a1 + 32));
  do
  {
    sqlite3_snprintf(24, v10, "sqlite_stat%d", v7);
    result = sqlite3FindTable(*a1, (__int64)v10, v8);
    if ( result )
      result = sqlite3NestedParse(a1, "DELETE FROM %Q.%s WHERE %s=%Q", v8, v10, a3, a4);
    ++v7;
  }
  while ( v7 <= 4 );
  return result;
}

```

## disassembly

```asm
0x1400507bc  push    rbx
0x1400507be  push    rbp
0x1400507bf  push    rsi
0x1400507c0  push    rdi
0x1400507c1  push    r14
0x1400507c3  sub     rsp, 50h
0x1400507c7  mov     rax, cs:__security_cookie
0x1400507ce  xor     rax, rsp
0x1400507d1  mov     [rsp+78h+var_30], rax
0x1400507d6  mov     rax, [rcx]
0x1400507d9  mov     r14, r9
0x1400507dc  movsxd  r10, edx
0x1400507df  mov     rbp, r8
0x1400507e2  shl     r10, 5
0x1400507e6  mov     rdi, rcx
0x1400507e9  mov     ebx, 1
0x1400507ee  mov     rdx, [rax+20h]
0x1400507f2  mov     rsi, [r10+rdx]
0x1400507f6  mov     r9d, ebx
0x1400507f9  lea     r8, aSqliteStatD; "sqlite_stat%d"
0x140050800  lea     rdx, [rsp+78h+var_48]
0x140050805  mov     ecx, 18h
0x14005080a  call    sqlite3_snprintf
0x14005080f  mov     rcx, [rdi]
0x140050812  lea     rdx, [rsp+78h+var_48]
0x140050817  mov     r8, rsi
0x14005081a  call    sqlite3FindTable
0x14005081f  test    rax, rax
0x140050822  jz      short loc_140050845
0x140050824  mov     [rsp+78h+var_50], r14
0x140050829  lea     r9, [rsp+78h+var_48]
0x14005082e  mov     r8, rsi
0x140050831  mov     [rsp+78h+var_58], rbp
0x140050836  lea     rdx, aDeleteFromQSWh; "DELETE FROM %Q.%s WHERE %s=%Q"
0x14005083d  mov     rcx, rdi
0x140050840  call    sqlite3NestedParse
0x140050845  inc     ebx
0x140050847  cmp     ebx, 4
0x14005084a  jle     short loc_1400507F6
0x14005084c  mov     rcx, [rsp+78h+var_30]
0x140050851  xor     rcx, rsp; StackCookie
0x140050854  call    __security_check_cookie
0x140050859  add     rsp, 50h
0x14005085d  pop     r14
0x14005085f  pop     rdi
0x140050860  pop     rsi
0x140050861  pop     rbp
0x140050862  pop     rbx
0x140050863  retn
```
