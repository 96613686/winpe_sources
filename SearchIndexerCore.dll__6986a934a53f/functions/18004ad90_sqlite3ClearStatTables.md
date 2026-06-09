# sqlite3ClearStatTables

- ea: `0x18004ad90`
- end: `0x18004ae3a`
- name: `sqlite3ClearStatTables`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18004a49c`
- `0x180074d48`

## callees

- `0x18000a180`
- `0x18004a9b8`
- `0x18004ad90`
- `0x18004ae40`
- `0x1800789c0`

## string_xrefs

- `0x18004ae29`: `DELETE FROM %Q.%s WHERE %s=%Q`

## pseudocode

```c
__int64 __fastcall sqlite3ClearStatTables(__int64 *a1, int a2, __int64 a3, __int64 a4)
{
  int v7; // ebx
  _BYTE *v8; // rsi
  __int64 result; // rax
  unsigned __int8 v10[24]; // [rsp+30h] [rbp-48h] BYREF

  v7 = 1;
  v8 = *(_BYTE **)(32LL * a2 + *(_QWORD *)(*a1 + 32));
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
0x18004ad90  push    rbx
0x18004ad92  push    rbp
0x18004ad93  push    rsi
0x18004ad94  push    rdi
0x18004ad95  push    r14
0x18004ad97  sub     rsp, 50h
0x18004ad9b  mov     rax, cs:__security_cookie
0x18004ada2  xor     rax, rsp
0x18004ada5  mov     [rsp+78h+var_30], rax
0x18004adaa  mov     rax, [rcx]
0x18004adad  mov     r14, r9
0x18004adb0  movsxd  r10, edx
0x18004adb3  mov     rbp, r8
0x18004adb6  shl     r10, 5
0x18004adba  mov     rdi, rcx
0x18004adbd  mov     ebx, 1
0x18004adc2  mov     rdx, [rax+20h]
0x18004adc6  mov     rsi, [r10+rdx]
0x18004adca  mov     r9d, ebx
0x18004adcd  lea     r8, aSqliteStatD; "sqlite_stat%d"
0x18004add4  lea     rdx, [rsp+78h+var_48]
0x18004add9  mov     ecx, 18h
0x18004adde  call    sqlite3_snprintf
0x18004ade3  mov     rcx, [rdi]
0x18004ade6  lea     rdx, [rsp+78h+var_48]
0x18004adeb  mov     r8, rsi
0x18004adee  call    sqlite3FindTable
0x18004adf3  test    rax, rax
0x18004adf6  jnz     short loc_18004AE17
0x18004adf8  inc     ebx
0x18004adfa  cmp     ebx, 4
0x18004adfd  jle     short loc_18004ADCA
0x18004adff  mov     rcx, [rsp+78h+var_30]
0x18004ae04  xor     rcx, rsp; StackCookie
0x18004ae07  call    __security_check_cookie
0x18004ae0c  add     rsp, 50h
0x18004ae10  pop     r14
0x18004ae12  pop     rdi
0x18004ae13  pop     rsi
0x18004ae14  pop     rbp
0x18004ae15  pop     rbx
0x18004ae16  retn
0x18004ae17  mov     [rsp+78h+var_50], r14
0x18004ae1c  lea     r9, [rsp+78h+var_48]
0x18004ae21  mov     r8, rsi
0x18004ae24  mov     [rsp+78h+var_58], rbp
0x18004ae29  lea     rdx, aDeleteFromQSWh; "DELETE FROM %Q.%s WHERE %s=%Q"
0x18004ae30  mov     rcx, rdi
0x18004ae33  call    sqlite3NestedParse
0x18004ae38  jmp     short loc_18004ADF8
```
