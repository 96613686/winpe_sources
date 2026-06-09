# _CreateLocalRPCConnection2QM_::_1_::dtor$2

- ea: `0x18000fae4`
- end: `0x18000faf0`
- name: `_CreateLocalRPCConnection2QM_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003430`

## pseudocode

```c
__int64 __fastcall CreateLocalRPCConnection2QM_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return AP<char>::~AP<char>(a2 + 120);
}

```

## disassembly

```asm
0x18000fae4  lea     rcx, [rdx+78h]
0x18000faeb  jmp     ??1?$AP@D@@QEAA@XZ; AP<char>::~AP<char>(void)
```
