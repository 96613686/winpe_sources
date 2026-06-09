# bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::WriteVersion(void)

- ea: `0x180022904`
- end: `0x18002292d`
- name: `?WriteVersion@?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@QEAAXXZ`
- size: `41`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016000`
- `0x180016104`
- `0x180016208`
- `0x18001630c`
- `0x180016410`
- `0x180016514`
- `0x180016618`
- `0x18001671c`

## callees

- `0x180011c04`

## pseudocode

```c
__int64 __fastcall bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::WriteVersion(__int64 a1)
{
  bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned short>(*(_QWORD *)a1, (unsigned __int16 *)"CB");
  return bond::OutputMemoryStream<std::allocator<char>>::Write<unsigned short>(
           *(_QWORD *)a1,
           (unsigned __int16 *)(a1 + 16));
}

```

## disassembly

```asm
0x180022904  push    rbx
0x180022906  sub     rsp, 20h
0x18002290a  mov     rbx, rcx
0x18002290d  lea     rdx, ?magic@?$CompactBinaryReader@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@2GB; "CB"
0x180022914  mov     rcx, [rcx]
0x180022917  call    ??$Write@G@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBG@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<ushort>(ushort const &)
0x18002291c  mov     rcx, [rbx]
0x18002291f  lea     rdx, [rbx+10h]
0x180022923  add     rsp, 20h
0x180022927  pop     rbx
0x180022928  jmp     ??$Write@G@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXAEBG@Z; bond::OutputMemoryStream<std::allocator<char>>::Write<ushort>(ushort const &)
```
