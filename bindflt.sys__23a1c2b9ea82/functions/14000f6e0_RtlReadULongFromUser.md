# RtlReadULongFromUser

- ea: `0x14000f6e0`
- end: `0x14000f713`
- name: `RtlReadULongFromUser`
- size: `51`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140007050`
- `0x140011c9c`
- `0x140011d18`

## callees

- `0x1400034af`
- `0x14000f6e0`

## pseudocode

```c
__int64 __fastcall RtlReadULongFromUser(unsigned int *a1)
{
  ProbeForRead_0(a1, 4u, 1u);
  return *a1;
}

```

## disassembly

```asm
0x14000f6e0  push    rbx
0x14000f6e2  sub     rsp, 20h
0x14000f6e6  mov     rax, cs:qword_14000D588
0x14000f6ed  mov     rbx, rcx
0x14000f6f0  test    rax, rax
0x14000f6f3  jz      short loc_14000F6FC
0x14000f6f5  call    rax ; qword_14000D588
0x14000f6f7  nop     dword ptr [rax]
0x14000f6fa  jmp     short loc_14000F70C
0x14000f6fc  mov     edx, 4; Length
0x14000f701  lea     r8d, [rdx-3]; Alignment
0x14000f705  call    ProbeForRead_0
0x14000f70a  mov     eax, [rbx]
0x14000f70c  add     rsp, 20h
0x14000f710  pop     rbx
0x14000f711  retn
```
