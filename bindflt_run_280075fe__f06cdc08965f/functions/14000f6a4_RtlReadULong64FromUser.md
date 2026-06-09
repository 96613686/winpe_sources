# RtlReadULong64FromUser

- ea: `0x14000f6a4`
- end: `0x14000f6d8`
- name: `RtlReadULong64FromUser`
- size: `52`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140007040`
- `0x140011c9c`
- `0x140011d18`
- `0x140011df0`

## callees

- `0x1400034af`
- `0x14000f6a4`

## pseudocode

```c
__int64 __fastcall RtlReadULong64FromUser(volatile void *a1)
{
  ProbeForRead_0(a1, 8u, 1u);
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x14000f6a4  push    rbx
0x14000f6a6  sub     rsp, 20h
0x14000f6aa  mov     rax, cs:qword_14000D598
0x14000f6b1  mov     rbx, rcx
0x14000f6b4  test    rax, rax
0x14000f6b7  jz      short loc_14000F6C0
0x14000f6b9  call    rax ; qword_14000D598
0x14000f6bb  nop     dword ptr [rax]
0x14000f6be  jmp     short loc_14000F6D1
0x14000f6c0  mov     edx, 8; Length
0x14000f6c5  lea     r8d, [rdx-7]; Alignment
0x14000f6c9  call    ProbeForRead_0
0x14000f6ce  mov     rax, [rbx]
0x14000f6d1  add     rsp, 20h
0x14000f6d5  pop     rbx
0x14000f6d6  retn
```
