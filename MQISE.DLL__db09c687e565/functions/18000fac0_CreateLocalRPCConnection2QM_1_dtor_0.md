# _CreateLocalRPCConnection2QM_::_1_::dtor$0

- ea: `0x18000fac0`
- end: `0x18000facc`
- name: `_CreateLocalRPCConnection2QM_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003430`

## pseudocode

```c
__int64 __fastcall CreateLocalRPCConnection2QM_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return AP<char>::~AP<char>(a2 + 112);
}

```

## disassembly

```asm
0x18000fac0  lea     rcx, [rdx+70h]
0x18000fac7  jmp     ??1?$AP@D@@QEAA@XZ; AP<char>::~AP<char>(void)
```
