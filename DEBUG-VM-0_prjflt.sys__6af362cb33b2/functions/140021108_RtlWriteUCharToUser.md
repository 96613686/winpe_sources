# RtlWriteUCharToUser

- ea: `0x140021108`
- end: `0x140021147`
- name: `RtlWriteUCharToUser`
- size: `63`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140014050`
- `0x1400260a4`
- `0x1400266ec`
- `0x140026d94`

## callees

- `0x1400014ff`
- `0x140021108`

## pseudocode

```c
void __fastcall RtlWriteUCharToUser(_BYTE *a1, char a2)
{
  ProbeForRead_0(a1, 1u, 1u);
  *a1 = a2;
}

```

## disassembly

```asm
0x140021108  mov     [rsp+arg_0], rbx
0x14002110d  push    rdi
0x14002110e  sub     rsp, 20h
0x140021112  mov     rax, cs:qword_14001D880
0x140021119  mov     dil, dl
0x14002111c  mov     rbx, rcx
0x14002111f  test    rax, rax
0x140021122  jz      short loc_14002112B
0x140021124  call    rax ; qword_14001D880
0x140021126  nop     dword ptr [rax]
0x140021129  jmp     short loc_14002113B
0x14002112b  mov     edx, 1; Length
0x140021130  mov     r8d, edx; Alignment
0x140021133  call    ProbeForRead_0
0x140021138  mov     [rbx], dil
0x14002113b  mov     rbx, [rsp+28h+arg_0]
0x140021140  add     rsp, 20h
0x140021144  pop     rdi
0x140021145  retn
```
