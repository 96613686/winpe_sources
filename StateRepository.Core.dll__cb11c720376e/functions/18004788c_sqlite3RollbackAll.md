# sqlite3RollbackAll

- ea: `0x18004788c`
- end: `0x18004799d`
- name: `sqlite3RollbackAll`
- size: `273`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180028df4`
- `0x18002a050`
- `0x180030480`

## callees

- `0x180024468`
- `0x180046938`
- `0x18004788c`
- `0x1800479a4`
- `0x180047b8c`
- `0x180047ba4`
- `0x180047bbc`
- `0x180047c2c`
- `0x180054798`
- `0x180063a1c`
- `0x18009a010`

## pseudocode

```c
__int64 (__fastcall *__fastcall sqlite3RollbackAll(__int64 a1, unsigned int a2))(_QWORD)
{
  int v4; // ebp
  __int64 v5; // rdx
  __int64 v6; // r8
  BOOL v7; // esi
  int i; // edi
  __int64 v9; // rcx
  __int64 (__fastcall *result)(_QWORD); // rax
  __int64 v11; // rcx

  v4 = 0;
  sqlite3BeginBenignMalloc();
  sqlite3BtreeEnterAll(a1);
  v7 = (*(_BYTE *)(a1 + 44) & 1) != 0 && !*(_BYTE *)(a1 + 197);
  for ( i = 0; i < *(_DWORD *)(a1 + 40); ++i )
  {
    v9 = *(_QWORD *)(32LL * i + *(_QWORD *)(a1 + 32) + 8);
    if ( v9 )
    {
      if ( (unsigned int)sqlite3BtreeTxnState(v9, v5, v6) == 2 )
        v4 = 1;
      sqlite3BtreeRollback(v11, a2, !v7);
    }
  }
  callFinaliser(a1, 136);
  sqlite3EndBenignMalloc();
  if ( v7 )
  {
    sqlite3ExpirePreparedStatements(a1, 0);
    sqlite3ResetAllSchemasOfConnection(a1);
  }
  sqlite3BtreeLeaveAll(a1);
  *(_QWORD *)(a1 + 760) = 0;
  *(_QWORD *)(a1 + 48) &= 0xFFFFFFFDFFF7FFFFuLL;
  result = *(__int64 (__fastcall **)(_QWORD))(a1 + 304);
  *(_QWORD *)(a1 + 768) = 0;
  if ( result && (v4 || !*(_BYTE *)(a1 + 101)) )
    return (__int64 (__fastcall *)(_QWORD))result(*(_QWORD *)(a1 + 296));
  return result;
}

```

## disassembly

```asm
0x18004788c  push    rbx
0x18004788e  push    rbp
0x18004788f  push    rsi
0x180047890  push    rdi
0x180047891  push    r12
0x180047893  push    r14
0x180047895  sub     rsp, 28h
0x180047899  mov     r14d, edx
0x18004789c  mov     rbx, rcx
0x18004789f  xor     ebp, ebp
0x1800478a1  call    sqlite3BeginBenignMalloc
0x1800478a6  mov     rcx, rbx
0x1800478a9  call    sqlite3BtreeEnterAll
0x1800478ae  lea     r12d, [rbp+1]
0x1800478b2  test    [rbx+2Ch], r12b
0x1800478b6  jnz     loc_180047959
0x1800478bc  xor     esi, esi
0x1800478be  xor     edi, edi
0x1800478c0  cmp     [rbx+28h], edi
0x1800478c3  jle     short loc_1800478E2
0x1800478c5  mov     rax, [rbx+20h]
0x1800478c9  movsxd  rcx, edi
0x1800478cc  shl     rcx, 5
0x1800478d0  mov     rcx, [rcx+rax+8]
0x1800478d5  test    rcx, rcx
0x1800478d8  jnz     short loc_18004793D
0x1800478da  add     edi, r12d
0x1800478dd  cmp     edi, [rbx+28h]
0x1800478e0  jl      short loc_1800478C5
0x1800478e2  mov     edx, 88h
0x1800478e7  mov     rcx, rbx
0x1800478ea  call    callFinaliser
0x1800478ef  call    sqlite3EndBenignMalloc
0x1800478f4  test    esi, esi
0x1800478f6  jnz     short loc_18004796E
0x1800478f8  mov     rcx, rbx
0x1800478fb  call    sqlite3BtreeLeaveAll
0x180047900  mov     rax, 0FFFFFFFDFFF7FFFFh
0x18004790a  mov     qword ptr [rbx+2F8h], 0
0x180047915  and     [rbx+30h], rax
0x180047919  mov     rax, [rbx+130h]
0x180047920  mov     qword ptr [rbx+300h], 0
0x18004792b  test    rax, rax
0x18004792e  jnz     short loc_180047985
0x180047930  add     rsp, 28h
0x180047934  pop     r14
0x180047936  pop     r12
0x180047938  pop     rdi
0x180047939  pop     rsi
0x18004793a  pop     rbp
0x18004793b  pop     rbx
0x18004793c  retn
0x18004793d  call    sqlite3BtreeTxnState
0x180047942  cmp     eax, 2
0x180047945  mov     r8d, esi
0x180047948  mov     edx, r14d
0x18004794b  cmovz   ebp, r12d
0x18004794f  xor     r8d, r12d
0x180047952  call    sqlite3BtreeRollback
0x180047957  jmp     short loc_1800478DA
0x180047959  cmp     [rbx+0C5h], bpl
0x180047960  jnz     loc_1800478BC
0x180047966  mov     esi, r12d
0x180047969  jmp     loc_1800478BE
0x18004796e  xor     edx, edx
0x180047970  mov     rcx, rbx
0x180047973  call    sqlite3ExpirePreparedStatements
0x180047978  mov     rcx, rbx
0x18004797b  call    sqlite3ResetAllSchemasOfConnection
0x180047980  jmp     loc_1800478F8
0x180047985  test    ebp, ebp
0x180047987  jnz     short loc_18004798F
0x180047989  cmp     [rbx+65h], bpl
0x18004798d  jnz     short loc_180047930
0x18004798f  mov     rcx, [rbx+128h]
0x180047996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004799b  jmp     short loc_180047930
```
