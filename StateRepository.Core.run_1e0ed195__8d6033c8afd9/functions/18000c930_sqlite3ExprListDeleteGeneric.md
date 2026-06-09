# sqlite3ExprListDeleteGeneric

- ea: `0x18000c930`
- end: `0x18000c943`
- name: `sqlite3ExprListDeleteGeneric`
- size: `19`
- prototype: ``
- caller_count: `45`
- callee_count: `2`
- tags: ``

## callers

- `0x180003128`
- `0x18000c454`
- `0x18000c850`
- `0x18000c960`
- `0x18000ca30`
- `0x18000d770`
- `0x1800167c0`
- `0x1800189c8`
- `0x180031b38`
- `0x180037194`
- `0x180038fb8`
- `0x180044538`
- `0x18004a734`
- `0x18004bb50`
- `0x18004f6d8`
- `0x180050420`
- `0x1800569e0`
- `0x180056b54`
- `0x180056bc0`
- `0x180059ff8`
- `0x18005aea0`
- `0x18005dae0`
- `0x18005dd88`
- `0x18005e35c`
- `0x18005eea8`
- `0x18005f714`
- `0x18005fa24`
- `0x18005fae0`
- `0x180063468`
- `0x1800644e4`
- `0x1800653a4`
- `0x18006ba34`
- `0x18006f250`
- `0x180070c50`
- `0x18007d398`
- `0x18007fe4c`
- `0x180083060`
- `0x1800838a0`
- `0x180083d6c`
- `0x180085340`
- `0x1800877e4`
- `0x18008a79c`
- `0x18008b810`
- `0x18008dfb0`
- `0x18009325c`

## callees

- `0x18000c930`
- `0x18000cb64`

## pseudocode

```c
__int64 __fastcall sqlite3ExprListDeleteGeneric(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  if ( a2 )
    return exprListDeleteNN(a1, a2);
  return result;
}

```

## disassembly

```asm
0x18000c930  sub     rsp, 28h
0x18000c934  test    rdx, rdx
0x18000c937  jz      short loc_18000C93E
0x18000c939  call    exprListDeleteNN
0x18000c93e  add     rsp, 28h
0x18000c942  retn
```
