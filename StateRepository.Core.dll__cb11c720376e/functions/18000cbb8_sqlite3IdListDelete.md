# sqlite3IdListDelete

- ea: `0x18000cbb8`
- end: `0x18000cc0c`
- name: `sqlite3IdListDelete`
- size: `84`
- prototype: ``
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ad30`
- `0x18000c454`
- `0x18000ca30`
- `0x180017fac`
- `0x1800189c8`
- `0x18001a810`
- `0x180046630`
- `0x18004d710`
- `0x180058e44`
- `0x18005c8b0`
- `0x18005dae0`
- `0x180083c4c`

## callees

- `0x18000a9e0`
- `0x18000cbb8`
- `0x18005fbb8`

## pseudocode

```c
__int64 __fastcall sqlite3IdListDelete(__int64 a1, _DWORD *a2)
{
  int i; // edi
  __int64 result; // rax

  if ( a2 )
  {
    for ( i = 0; i < *a2; ++i )
      sqlite3DbFree(a1, *(_QWORD *)&a2[4 * i + 2]);
    return sqlite3DbNNFreeNN(a1);
  }
  return result;
}

```

## disassembly

```asm
0x18000cbb8  test    rdx, rdx
0x18000cbbb  jz      short locret_18000CC0B
0x18000cbbd  mov     [rsp+arg_0], rbx
0x18000cbc2  mov     [rsp+arg_8], rsi
0x18000cbc7  push    rdi
0x18000cbc8  sub     rsp, 20h
0x18000cbcc  xor     edi, edi
0x18000cbce  mov     rbx, rdx
0x18000cbd1  mov     rsi, rcx
0x18000cbd4  cmp     [rdx], edi
0x18000cbd6  jle     short loc_18000CBF1
0x18000cbd8  movsxd  rdx, edi
0x18000cbdb  mov     rcx, rsi
0x18000cbde  add     rdx, rdx
0x18000cbe1  mov     rdx, [rbx+rdx*8+8]
0x18000cbe6  call    sqlite3DbFree
0x18000cbeb  inc     edi
0x18000cbed  cmp     edi, [rbx]
0x18000cbef  jl      short loc_18000CBD8
0x18000cbf1  mov     rdx, rbx
0x18000cbf4  mov     rcx, rsi
0x18000cbf7  call    sqlite3DbNNFreeNN
0x18000cbfc  mov     rbx, [rsp+28h+arg_0]
0x18000cc01  mov     rsi, [rsp+28h+arg_8]
0x18000cc06  add     rsp, 20h
0x18000cc0a  pop     rdi
0x18000cc0b  retn
```
