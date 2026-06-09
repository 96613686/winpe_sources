# RtlReadULongFromUser

- ea: `0x14002106c`
- end: `0x14002109f`
- name: `RtlReadULongFromUser`
- size: `51`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140014030`
- `0x1400260a4`
- `0x1400266ec`
- `0x140026d94`
- `0x140027144`
- `0x1400277f4`
- `0x140027ca0`

## callees

- `0x1400014ff`
- `0x14002106c`

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
0x14002106c  push    rbx
0x14002106e  sub     rsp, 20h
0x140021072  mov     rax, cs:qword_14001D898
0x140021079  mov     rbx, rcx
0x14002107c  test    rax, rax
0x14002107f  jz      short loc_140021088
0x140021081  call    rax ; qword_14001D898
0x140021083  nop     dword ptr [rax]
0x140021086  jmp     short loc_140021098
0x140021088  mov     edx, 4; Length
0x14002108d  lea     r8d, [rdx-3]; Alignment
0x140021091  call    ProbeForRead_0
0x140021096  mov     eax, [rbx]
0x140021098  add     rsp, 20h
0x14002109c  pop     rbx
0x14002109d  retn
```
