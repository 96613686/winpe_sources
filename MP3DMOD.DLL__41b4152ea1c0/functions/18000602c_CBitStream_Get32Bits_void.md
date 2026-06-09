# CBitStream::Get32Bits(void)

- ea: `0x18000602c`
- end: `0x180006062`
- name: `?Get32Bits@CBitStream@@QEAAKXZ`
- size: `54`
- prototype: `unsigned int __fastcall(CBitStream *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006628`
- `0x18000de5c`

## callees

- `0x180005f80`

## pseudocode

```c
__int64 __fastcall CBitStream::Get32Bits(CBitStream *this)
{
  unsigned int v2; // ebx

  v2 = (unsigned int)CBitStream::GetBits(this, 0x10u) << 16;
  return v2 | (unsigned int)CBitStream::GetBits(this, 0x10u);
}

```

## disassembly

```asm
0x18000602c  mov     [rsp+arg_0], rbx
0x180006031  push    rdi
0x180006032  sub     rsp, 20h
0x180006036  mov     edx, 10h; unsigned int
0x18000603b  mov     rdi, rcx
0x18000603e  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x180006043  mov     ebx, eax
0x180006045  mov     edx, 10h; unsigned int
0x18000604a  mov     rcx, rdi; this
0x18000604d  shl     ebx, 10h
0x180006050  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x180006055  or      eax, ebx
0x180006057  mov     rbx, [rsp+28h+arg_0]
0x18000605c  add     rsp, 20h
0x180006060  pop     rdi
0x180006061  retn
```
