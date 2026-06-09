# sqlite3SelectDelete

- ea: `0x18000c850`
- end: `0x18000c923`
- name: `sqlite3SelectDelete`
- size: `211`
- prototype: ``
- caller_count: `26`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000c454`
- `0x18000c960`
- `0x18000ca30`
- `0x18000d480`
- `0x18000e944`
- `0x18000eb78`
- `0x180018754`
- `0x1800189c8`
- `0x18001a810`
- `0x180031b38`
- `0x180034adc`
- `0x180038fb8`
- `0x18004a834`
- `0x18004d710`
- `0x1800569e0`
- `0x180056b54`
- `0x180058e44`
- `0x18005dae0`
- `0x180060c3c`
- `0x1800644e4`
- `0x1800647cc`
- `0x1800653a4`
- `0x18006f250`
- `0x18007e240`
- `0x18008513c`
- `0x180092f78`

## callees

- `0x18000c850`
- `0x18000c930`
- `0x18000c950`
- `0x18000ca30`
- `0x18005dd34`
- `0x18005fbb8`
- `0x18005fc14`
- `0x18008b8bc`

## pseudocode

```c
__int64 __fastcall sqlite3SelectDelete(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v4; // rsi
  __int64 v5; // rdx
  __int64 result; // rax

  if ( a2 )
  {
    v2 = a2;
    do
    {
      v4 = *(_QWORD *)(v2 + 80);
      sqlite3ExprListDeleteGeneric(a1, *(_QWORD *)(v2 + 32));
      sqlite3SrcListDelete(a1, *(_DWORD **)(v2 + 40));
      sqlite3ExprDelete(a1, *(_QWORD *)(v2 + 48));
      sqlite3ExprListDeleteGeneric(a1, *(_QWORD *)(v2 + 56));
      sqlite3ExprDelete(a1, *(_QWORD *)(v2 + 64));
      sqlite3ExprListDeleteGeneric(a1, *(_QWORD *)(v2 + 72));
      sqlite3ExprDelete(a1, *(_QWORD *)(v2 + 96));
      if ( *(_QWORD *)(v2 + 104) )
        sqlite3WithDelete(a1);
      v5 = *(_QWORD *)(v2 + 120);
      if ( v5 )
        sqlite3WindowListDelete(a1, v5);
      while ( *(_QWORD *)(v2 + 112) )
        sqlite3WindowUnlinkFromSelect();
      result = sqlite3DbNNFreeNN(a1, v2);
      v2 = v4;
    }
    while ( v4 );
  }
  return result;
}

```

## disassembly

```asm
0x18000c850  test    rdx, rdx
0x18000c853  jz      locret_18000C907
0x18000c859  mov     [rsp+arg_0], rbx
0x18000c85e  mov     [rsp+arg_8], rsi
0x18000c863  push    rdi
0x18000c864  sub     rsp, 20h
0x18000c868  mov     rbx, rdx
0x18000c86b  mov     rdi, rcx
0x18000c86e  mov     rdx, [rbx+20h]
0x18000c872  mov     rcx, rdi
0x18000c875  mov     rsi, [rbx+50h]
0x18000c879  call    sqlite3ExprListDeleteGeneric
0x18000c87e  mov     rdx, [rbx+28h]
0x18000c882  mov     rcx, rdi
0x18000c885  call    sqlite3SrcListDelete
0x18000c88a  mov     rdx, [rbx+30h]
0x18000c88e  mov     rcx, rdi
0x18000c891  call    sqlite3ExprDelete
0x18000c896  mov     rdx, [rbx+38h]
0x18000c89a  mov     rcx, rdi
0x18000c89d  call    sqlite3ExprListDeleteGeneric
0x18000c8a2  mov     rdx, [rbx+40h]
0x18000c8a6  mov     rcx, rdi
0x18000c8a9  call    sqlite3ExprDelete
0x18000c8ae  mov     rdx, [rbx+48h]
0x18000c8b2  mov     rcx, rdi
0x18000c8b5  call    sqlite3ExprListDeleteGeneric
0x18000c8ba  mov     rdx, [rbx+60h]
0x18000c8be  mov     rcx, rdi
0x18000c8c1  call    sqlite3ExprDelete
0x18000c8c6  mov     rdx, [rbx+68h]
0x18000c8ca  test    rdx, rdx
0x18000c8cd  jnz     short loc_18000C90F
0x18000c8cf  mov     rdx, [rbx+78h]
0x18000c8d3  test    rdx, rdx
0x18000c8d6  jnz     short loc_18000C919
0x18000c8d8  mov     rcx, [rbx+70h]
0x18000c8dc  test    rcx, rcx
0x18000c8df  jnz     short loc_18000C908
0x18000c8e1  mov     rdx, rbx
0x18000c8e4  mov     rcx, rdi
0x18000c8e7  call    sqlite3DbNNFreeNN
0x18000c8ec  mov     rbx, rsi
0x18000c8ef  test    rsi, rsi
0x18000c8f2  jnz     loc_18000C86E
0x18000c8f8  mov     rbx, [rsp+28h+arg_0]
0x18000c8fd  mov     rsi, [rsp+28h+arg_8]
0x18000c902  add     rsp, 20h
0x18000c906  pop     rdi
0x18000c907  retn
0x18000c908  call    sqlite3WindowUnlinkFromSelect
0x18000c90d  jmp     short loc_18000C8D8
0x18000c90f  mov     rcx, rdi
0x18000c912  call    sqlite3WithDelete
0x18000c917  jmp     short loc_18000C8CF
0x18000c919  mov     rcx, rdi
0x18000c91c  call    sqlite3WindowListDelete
0x18000c921  jmp     short loc_18000C8D8
```
