# sqlite3RollbackAll

- ea: `0x18003f560`
- end: `0x18003f68a`
- name: `sqlite3RollbackAll`
- size: `298`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180023780`
- `0x1800286a4`
- `0x18003fbf8`

## callees

- `0x18001fe30`
- `0x1800208d0`
- `0x180031f78`
- `0x18003f560`
- `0x18003f690`
- `0x18003f890`
- `0x18003f8b0`
- `0x18003f974`
- `0x180059d90`
- `0x1800b0010`

## pseudocode

```c
__int64 (__fastcall *__fastcall sqlite3RollbackAll(__int64 a1, unsigned int a2))(_QWORD)
{
  int v4; // ebp
  BOOL v5; // esi
  int i; // edi
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 (__fastcall *result)(_QWORD); // rax

  v4 = 0;
  sqlite3BeginBenignMalloc();
  if ( !*(_BYTE *)(a1 + 111) )
    btreeEnterAll(a1);
  v5 = (*(_BYTE *)(a1 + 44) & 1) != 0 && !*(_BYTE *)(a1 + 197);
  for ( i = 0; i < *(_DWORD *)(a1 + 40); ++i )
  {
    v7 = *(_QWORD *)(32LL * i + *(_QWORD *)(a1 + 32) + 8);
    if ( v7 )
    {
      if ( *(_BYTE *)(v7 + 16) == 2 )
        v4 = 1;
      sqlite3BtreeRollback(v7, a2, !v5);
    }
  }
  callFinaliser(a1, 136);
  sqlite3EndBenignMalloc();
  if ( v5 )
  {
    sqlite3ExpirePreparedStatements(a1, 0, v8);
    sqlite3ResetAllSchemasOfConnection(a1);
  }
  if ( !*(_BYTE *)(a1 + 111) )
    btreeLeaveAll(a1);
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
0x18003f560  push    rbx
0x18003f562  push    rbp
0x18003f563  push    rsi
0x18003f564  push    rdi
0x18003f565  push    r12
0x18003f567  push    r14
0x18003f569  sub     rsp, 28h
0x18003f56d  mov     r14d, edx
0x18003f570  mov     rbx, rcx
0x18003f573  xor     ebp, ebp
0x18003f575  call    sqlite3BeginBenignMalloc
0x18003f57a  cmp     [rbx+6Fh], bpl
0x18003f57e  jz      loc_18003F62D
0x18003f584  mov     r12d, 1
0x18003f58a  test    [rbx+2Ch], r12b
0x18003f58e  jnz     loc_18003F656
0x18003f594  xor     esi, esi
0x18003f596  xor     edi, edi
0x18003f598  cmp     [rbx+28h], edi
0x18003f59b  jle     short loc_18003F5D0
0x18003f59d  mov     rax, [rbx+20h]
0x18003f5a1  movsxd  rcx, edi
0x18003f5a4  shl     rcx, 5
0x18003f5a8  mov     rcx, [rcx+rax+8]
0x18003f5ad  test    rcx, rcx
0x18003f5b0  jz      short loc_18003F5C8
0x18003f5b2  cmp     byte ptr [rcx+10h], 2
0x18003f5b6  mov     r8d, esi
0x18003f5b9  mov     edx, r14d
0x18003f5bc  cmovz   ebp, r12d
0x18003f5c0  xor     r8d, r12d
0x18003f5c3  call    sqlite3BtreeRollback
0x18003f5c8  add     edi, r12d
0x18003f5cb  cmp     edi, [rbx+28h]
0x18003f5ce  jl      short loc_18003F59D
0x18003f5d0  mov     edx, 88h
0x18003f5d5  mov     rcx, rbx
0x18003f5d8  call    callFinaliser
0x18003f5dd  call    sqlite3EndBenignMalloc
0x18003f5e2  test    esi, esi
0x18003f5e4  jnz     loc_18003F66B
0x18003f5ea  cmp     byte ptr [rbx+6Fh], 0
0x18003f5ee  jz      short loc_18003F63A
0x18003f5f0  mov     rax, 0FFFFFFFDFFF7FFFFh
0x18003f5fa  mov     qword ptr [rbx+2F8h], 0
0x18003f605  and     [rbx+30h], rax
0x18003f609  mov     rax, [rbx+130h]
0x18003f610  mov     qword ptr [rbx+300h], 0
0x18003f61b  test    rax, rax
0x18003f61e  jnz     short loc_18003F644
0x18003f620  add     rsp, 28h
0x18003f624  pop     r14
0x18003f626  pop     r12
0x18003f628  pop     rdi
0x18003f629  pop     rsi
0x18003f62a  pop     rbp
0x18003f62b  pop     rbx
0x18003f62c  retn
0x18003f62d  mov     rcx, rbx
0x18003f630  call    btreeEnterAll
0x18003f635  jmp     loc_18003F584
0x18003f63a  mov     rcx, rbx
0x18003f63d  call    btreeLeaveAll
0x18003f642  jmp     short loc_18003F5F0
0x18003f644  test    ebp, ebp
0x18003f646  jz      short loc_18003F682
0x18003f648  mov     rcx, [rbx+128h]
0x18003f64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f654  jmp     short loc_18003F620
0x18003f656  cmp     [rbx+0C5h], bpl
0x18003f65d  jnz     loc_18003F594
0x18003f663  mov     esi, r12d
0x18003f666  jmp     loc_18003F596
0x18003f66b  xor     edx, edx
0x18003f66d  mov     rcx, rbx
0x18003f670  call    sqlite3ExpirePreparedStatements
0x18003f675  mov     rcx, rbx
0x18003f678  call    sqlite3ResetAllSchemasOfConnection
0x18003f67d  jmp     loc_18003F5EA
0x18003f682  cmp     byte ptr [rbx+65h], 0
0x18003f686  jnz     short loc_18003F620
0x18003f688  jmp     short loc_18003F648
```
