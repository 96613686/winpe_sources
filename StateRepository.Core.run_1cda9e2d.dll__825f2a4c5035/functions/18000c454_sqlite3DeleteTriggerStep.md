# sqlite3DeleteTriggerStep

- ea: `0x18000c454`
- end: `0x18000c4f2`
- name: `sqlite3DeleteTriggerStep`
- size: `158`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x18000ad30`
- `0x180045eb8`
- `0x180046630`
- `0x18005dae0`

## callees

- `0x18000a9e0`
- `0x18000c454`
- `0x18000c850`
- `0x18000c930`
- `0x18000c960`
- `0x18000ca30`
- `0x18000cbb8`
- `0x180019c00`

## pseudocode

```c
__int64 __fastcall sqlite3DeleteTriggerStep(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v4; // rdi
  __int64 v5; // rdx
  __int64 result; // rax

  if ( a2 )
  {
    v2 = a2;
    do
    {
      v4 = v2;
      v2 = *(_QWORD *)(v2 + 80);
      v5 = *(_QWORD *)(v4 + 40);
      if ( v5 )
        sqlite3ExprDeleteNN(a1, v5);
      sqlite3ExprListDeleteGeneric(a1, *(_QWORD *)(v4 + 48));
      sqlite3SelectDelete(a1, *(_QWORD *)(v4 + 16));
      sqlite3IdListDelete(a1, *(_DWORD **)(v4 + 56));
      sqlite3UpsertDelete(a1, *(_QWORD *)(v4 + 64));
      sqlite3SrcListDelete(a1, *(_DWORD **)(v4 + 32));
      sqlite3DbFree(a1, *(_QWORD *)(v4 + 72));
      result = sqlite3DbFree(a1, v4);
    }
    while ( v2 );
  }
  return result;
}

```

## disassembly

```asm
0x18000c454  test    rdx, rdx
0x18000c457  jz      locret_18000C4F1
0x18000c45d  mov     [rsp+arg_0], rbx
0x18000c462  mov     [rsp+arg_8], rsi
0x18000c467  push    rdi
0x18000c468  sub     rsp, 20h
0x18000c46c  mov     rbx, rdx
0x18000c46f  mov     rsi, rcx
0x18000c472  mov     rdi, rbx
0x18000c475  mov     rbx, [rbx+50h]
0x18000c479  mov     rdx, [rdi+28h]
0x18000c47d  test    rdx, rdx
0x18000c480  jz      short loc_18000C48A
0x18000c482  mov     rcx, rsi
0x18000c485  call    sqlite3ExprDeleteNN
0x18000c48a  mov     rdx, [rdi+30h]
0x18000c48e  mov     rcx, rsi
0x18000c491  call    sqlite3ExprListDeleteGeneric
0x18000c496  mov     rdx, [rdi+10h]
0x18000c49a  mov     rcx, rsi
0x18000c49d  call    sqlite3SelectDelete
0x18000c4a2  mov     rdx, [rdi+38h]
0x18000c4a6  mov     rcx, rsi
0x18000c4a9  call    sqlite3IdListDelete
0x18000c4ae  mov     rdx, [rdi+40h]
0x18000c4b2  mov     rcx, rsi
0x18000c4b5  call    sqlite3UpsertDelete
0x18000c4ba  mov     rdx, [rdi+20h]
0x18000c4be  mov     rcx, rsi
0x18000c4c1  call    sqlite3SrcListDelete
0x18000c4c6  mov     rdx, [rdi+48h]
0x18000c4ca  mov     rcx, rsi
0x18000c4cd  call    sqlite3DbFree
0x18000c4d2  mov     rdx, rdi
0x18000c4d5  mov     rcx, rsi
0x18000c4d8  call    sqlite3DbFree
0x18000c4dd  test    rbx, rbx
0x18000c4e0  jnz     short loc_18000C472
0x18000c4e2  mov     rbx, [rsp+28h+arg_0]
0x18000c4e7  mov     rsi, [rsp+28h+arg_8]
0x18000c4ec  add     rsp, 20h
0x18000c4f0  pop     rdi
0x18000c4f1  retn
```
