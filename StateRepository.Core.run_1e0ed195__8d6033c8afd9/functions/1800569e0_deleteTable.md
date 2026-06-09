# deleteTable

- ea: `0x1800569e0`
- end: `0x180056aa3`
- name: `deleteTable`
- size: `195`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18000ad30`
- `0x18004660c`

## callees

- `0x18000a9e0`
- `0x18000c500`
- `0x18000c718`
- `0x18000c850`
- `0x18000c930`
- `0x1800569e0`
- `0x180056aac`
- `0x180056bc0`
- `0x180089a24`

## pseudocode

```c
__int64 __fastcall deleteTable(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rsi
  _QWORD *v5; // rbp
  char v6; // al

  v2 = *(_QWORD **)(a2 + 16);
  if ( v2 )
  {
    do
    {
      v5 = (_QWORD *)v2[5];
      if ( !*(_QWORD *)(a1 + 776) && *(_BYTE *)(a2 + 63) != 1 )
        sqlite3HashInsert(v2[6] + 32LL, *v2, 0);
      sqlite3FreeIndex(a1, v2);
      v2 = v5;
    }
    while ( v5 );
  }
  v6 = *(_BYTE *)(a2 + 63);
  if ( v6 )
  {
    if ( v6 == 1 )
      sqlite3VtabClear(a1, a2);
    else
      sqlite3SelectDelete(a1, *(_QWORD *)(a2 + 64));
  }
  else
  {
    sqlite3FkDelete(a1, a2);
  }
  sqlite3DeleteColumnNames(a1);
  sqlite3DbFree(a1, *(_QWORD *)a2);
  sqlite3DbFree(a1, *(_QWORD *)(a2 + 24));
  sqlite3ExprListDeleteGeneric(a1, *(_QWORD *)(a2 + 32));
  return sqlite3DbFree(a1, a2);
}

```

## disassembly

```asm
0x1800569e0  push    rbx
0x1800569e2  push    rbp
0x1800569e3  push    rsi
0x1800569e4  push    rdi
0x1800569e5  sub     rsp, 28h
0x1800569e9  mov     rsi, [rdx+10h]
0x1800569ed  mov     rbx, rdx
0x1800569f0  mov     rdi, rcx
0x1800569f3  test    rsi, rsi
0x1800569f6  jz      short loc_180056A19
0x1800569f8  cmp     qword ptr [rdi+308h], 0
0x180056a00  mov     rbp, [rsi+28h]
0x180056a04  jz      short loc_180056A6C
0x180056a06  mov     rdx, rsi
0x180056a09  mov     rcx, rdi
0x180056a0c  call    sqlite3FreeIndex
0x180056a11  mov     rsi, rbp
0x180056a14  test    rbp, rbp
0x180056a17  jnz     short loc_1800569F8
0x180056a19  mov     al, [rbx+3Fh]
0x180056a1c  mov     rcx, rdi
0x180056a1f  test    al, al
0x180056a21  jnz     short loc_180056A8A
0x180056a23  mov     rdx, rbx
0x180056a26  call    sqlite3FkDelete
0x180056a2b  mov     rdx, rbx
0x180056a2e  mov     rcx, rdi
0x180056a31  call    sqlite3DeleteColumnNames
0x180056a36  mov     rdx, [rbx]
0x180056a39  mov     rcx, rdi
0x180056a3c  call    sqlite3DbFree
0x180056a41  mov     rdx, [rbx+18h]
0x180056a45  mov     rcx, rdi
0x180056a48  call    sqlite3DbFree
0x180056a4d  mov     rdx, [rbx+20h]
0x180056a51  mov     rcx, rdi
0x180056a54  call    sqlite3ExprListDeleteGeneric
0x180056a59  mov     rdx, rbx
0x180056a5c  mov     rcx, rdi
0x180056a5f  add     rsp, 28h
0x180056a63  pop     rdi
0x180056a64  pop     rsi
0x180056a65  pop     rbp
0x180056a66  pop     rbx
0x180056a67  jmp     sqlite3DbFree
0x180056a6c  cmp     byte ptr [rbx+3Fh], 1
0x180056a70  jz      short loc_180056A06
0x180056a72  mov     rcx, [rsi+30h]
0x180056a76  xor     r8d, r8d
0x180056a79  mov     rdx, [rsi]
0x180056a7c  add     rcx, 20h ; ' '
0x180056a80  call    sqlite3HashInsert
0x180056a85  jmp     loc_180056A06
0x180056a8a  cmp     al, 1
0x180056a8c  jnz     short loc_180056A98
0x180056a8e  mov     rdx, rbx
0x180056a91  call    sqlite3VtabClear
0x180056a96  jmp     short loc_180056A2B
0x180056a98  mov     rdx, [rbx+40h]
0x180056a9c  call    sqlite3SelectDelete
0x180056aa1  jmp     short loc_180056A2B
```
