# bond::CompactBinaryWriter<bond::OutputCounter>::~CompactBinaryWriter<bond::OutputCounter>(void)

- ea: `0x18001af44`
- end: `0x18001af67`
- name: `??1?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@QEAA@XZ`
- size: `35`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `18`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bdd8`
- `0x18000bedc`
- `0x18000bfe0`
- `0x18000c0e4`
- `0x18000c1e8`
- `0x18000c2ec`
- `0x18000c3f0`
- `0x18000c4f4`
- `0x180016000`
- `0x180016104`
- `0x180016208`
- `0x18001630c`
- `0x180016410`
- `0x180016514`
- `0x180016618`
- `0x18001671c`
- `0x18002ebf8`
- `0x18002f045`

## callees

- `0x180024770`

## pseudocode

```c
__int64 __fastcall bond::CompactBinaryWriter<bond::OutputCounter>::~CompactBinaryWriter<bond::OutputCounter>(
        __int64 a1)
{
  bond::detail::SimpleArray<unsigned int,64>::memfree(a1 + 296);
  return bond::detail::SimpleArray<unsigned int,64>::memfree(a1 + 24);
}

```

## disassembly

```asm
0x18001af44  push    rbx
0x18001af46  sub     rsp, 20h
0x18001af4a  mov     rbx, rcx
0x18001af4d  add     rcx, 128h
0x18001af54  call    ?memfree@?$SimpleArray@I$0EA@@detail@bond@@AEAAXXZ; bond::detail::SimpleArray<uint,64>::memfree(void)
0x18001af59  lea     rcx, [rbx+18h]
0x18001af5d  add     rsp, 20h
0x18001af61  pop     rbx
0x18001af62  jmp     ?memfree@?$SimpleArray@I$0EA@@detail@bond@@AEAAXXZ; bond::detail::SimpleArray<uint,64>::memfree(void)
```
