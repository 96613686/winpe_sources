# sqlite3ClearStatTables

- ea: `0x1800825e0`
- end: `0x180082688`
- name: `sqlite3ClearStatTables`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800830cc`
- `0x1800832c0`

## callees

- `0x180014434`
- `0x180067b40`
- `0x180068880`
- `0x1800825e0`
- `0x1800857c4`

## string_xrefs

- `0x18008265a`: `DELETE FROM %Q.%s WHERE %s=%Q`

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
    result = sqlite3FindTable(*a1, v10, v8);
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
0x1800825e0  push    rbx
0x1800825e2  push    rbp
0x1800825e3  push    rsi
0x1800825e4  push    rdi
0x1800825e5  push    r14
0x1800825e7  sub     rsp, 50h
0x1800825eb  mov     rax, cs:__security_cookie
0x1800825f2  xor     rax, rsp
0x1800825f5  mov     [rsp+78h+var_30], rax
0x1800825fa  mov     rax, [rcx]
0x1800825fd  mov     r14, r9
0x180082600  movsxd  r10, edx
0x180082603  mov     rbp, r8
0x180082606  shl     r10, 5
0x18008260a  mov     rdi, rcx
0x18008260d  mov     ebx, 1
0x180082612  mov     rdx, [rax+20h]
0x180082616  mov     rsi, [r10+rdx]
0x18008261a  mov     r9d, ebx
0x18008261d  lea     r8, aSqliteStatD; "sqlite_stat%d"
0x180082624  lea     rdx, [rsp+78h+var_48]
0x180082629  mov     ecx, 18h
0x18008262e  call    sqlite3_snprintf
0x180082633  mov     rcx, [rdi]
0x180082636  lea     rdx, [rsp+78h+var_48]
0x18008263b  mov     r8, rsi
0x18008263e  call    sqlite3FindTable
0x180082643  test    rax, rax
0x180082646  jz      short loc_180082669
0x180082648  mov     [rsp+78h+var_50], r14
0x18008264d  lea     r9, [rsp+78h+var_48]
0x180082652  mov     r8, rsi
0x180082655  mov     [rsp+78h+var_58], rbp
0x18008265a  lea     rdx, aDeleteFromQSWh; "DELETE FROM %Q.%s WHERE %s=%Q"
0x180082661  mov     rcx, rdi
0x180082664  call    sqlite3NestedParse
0x180082669  inc     ebx
0x18008266b  cmp     ebx, 4
0x18008266e  jle     short loc_18008261A
0x180082670  mov     rcx, [rsp+78h+var_30]
0x180082675  xor     rcx, rsp; StackCookie
0x180082678  call    __security_check_cookie
0x18008267d  add     rsp, 50h
0x180082681  pop     r14
0x180082683  pop     rdi
0x180082684  pop     rsi
0x180082685  pop     rbp
0x180082686  pop     rbx
0x180082687  retn
```
