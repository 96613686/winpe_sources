# sqlite3ClearStatTables

- ea: `0x18007b4bc`
- end: `0x18007b564`
- name: `sqlite3ClearStatTables`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18007e6c8`
- `0x18007e8bc`

## callees

- `0x18002817c`
- `0x18003cc7c`
- `0x18003f650`
- `0x1800449f0`
- `0x18007b4bc`

## string_xrefs

- `0x18007b536`: `DELETE FROM %Q.%s WHERE %s=%Q`

## pseudocode

```c
__int64 __fastcall sqlite3ClearStatTables(__int64 *a1, int a2, __int64 a3, __int64 a4)
{
  int v7; // ebx
  __int64 v8; // rsi
  __int64 result; // rax
  unsigned __int8 v10[24]; // [rsp+30h] [rbp-48h] BYREF

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
0x18007b4bc  push    rbx
0x18007b4be  push    rbp
0x18007b4bf  push    rsi
0x18007b4c0  push    rdi
0x18007b4c1  push    r14
0x18007b4c3  sub     rsp, 50h
0x18007b4c7  mov     rax, cs:__security_cookie
0x18007b4ce  xor     rax, rsp
0x18007b4d1  mov     [rsp+78h+var_30], rax
0x18007b4d6  mov     rax, [rcx]
0x18007b4d9  mov     r14, r9
0x18007b4dc  movsxd  r10, edx
0x18007b4df  mov     rbp, r8
0x18007b4e2  shl     r10, 5
0x18007b4e6  mov     rdi, rcx
0x18007b4e9  mov     ebx, 1
0x18007b4ee  mov     rdx, [rax+20h]
0x18007b4f2  mov     rsi, [r10+rdx]
0x18007b4f6  mov     r9d, ebx
0x18007b4f9  lea     r8, aSqliteStatD; "sqlite_stat%d"
0x18007b500  lea     rdx, [rsp+78h+var_48]
0x18007b505  mov     ecx, 18h
0x18007b50a  call    sqlite3_snprintf
0x18007b50f  mov     rcx, [rdi]
0x18007b512  lea     rdx, [rsp+78h+var_48]
0x18007b517  mov     r8, rsi
0x18007b51a  call    sqlite3FindTable
0x18007b51f  test    rax, rax
0x18007b522  jz      short loc_18007B545
0x18007b524  mov     [rsp+78h+var_50], r14
0x18007b529  lea     r9, [rsp+78h+var_48]
0x18007b52e  mov     r8, rsi
0x18007b531  mov     [rsp+78h+var_58], rbp
0x18007b536  lea     rdx, aDeleteFromQSWh; "DELETE FROM %Q.%s WHERE %s=%Q"
0x18007b53d  mov     rcx, rdi
0x18007b540  call    sqlite3NestedParse
0x18007b545  inc     ebx
0x18007b547  cmp     ebx, 4
0x18007b54a  jle     short loc_18007B4F6
0x18007b54c  mov     rcx, [rsp+78h+var_30]
0x18007b551  xor     rcx, rsp; StackCookie
0x18007b554  call    __security_check_cookie
0x18007b559  add     rsp, 50h
0x18007b55d  pop     r14
0x18007b55f  pop     rdi
0x18007b560  pop     rsi
0x18007b561  pop     rbp
0x18007b562  pop     rbx
0x18007b563  retn
```
