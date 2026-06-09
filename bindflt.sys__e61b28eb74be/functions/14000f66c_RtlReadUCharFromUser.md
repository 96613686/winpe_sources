# RtlReadUCharFromUser

- ea: `0x14000f66c`
- end: `0x14000f69e`
- name: `RtlReadUCharFromUser`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140007030`
- `0x140011d18`

## callees

- `0x1400034af`
- `0x14000f66c`

## pseudocode

```c
char __fastcall RtlReadUCharFromUser(volatile void *a1)
{
  ProbeForRead_0(a1, 1u, 1u);
  return *(_BYTE *)a1;
}

```

## disassembly

```asm
0x14000f66c  push    rbx
0x14000f66e  sub     rsp, 20h
0x14000f672  mov     rax, cs:qword_14000D568
0x14000f679  mov     rbx, rcx
0x14000f67c  test    rax, rax
0x14000f67f  jz      short loc_14000F688
0x14000f681  call    rax ; qword_14000D568
0x14000f683  nop     dword ptr [rax]
0x14000f686  jmp     short loc_14000F697
0x14000f688  mov     edx, 1; Length
0x14000f68d  mov     r8d, edx; Alignment
0x14000f690  call    ProbeForRead_0
0x14000f695  mov     al, [rbx]
0x14000f697  add     rsp, 20h
0x14000f69b  pop     rbx
0x14000f69c  retn
```
