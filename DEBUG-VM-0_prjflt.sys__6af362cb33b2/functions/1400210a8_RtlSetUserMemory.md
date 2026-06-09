# RtlSetUserMemory

- ea: `0x1400210a8`
- end: `0x140021102`
- name: `RtlSetUserMemory`
- size: `90`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140014040`
- `0x1400260a4`
- `0x1400266ec`
- `0x140026d94`
- `0x140027144`
- `0x140027ca0`

## callees

- `0x1400014ff`
- `0x14000ba70`
- `0x1400210a8`

## pseudocode

```c
void *__fastcall RtlSetUserMemory(void *a1, unsigned __int8 a2, SIZE_T a3)
{
  int v4; // esi

  v4 = a2;
  ProbeForRead_0(a1, a3, 1u);
  return RtlSetVolatileMemory(a1, v4, a3);
}

```

## disassembly

```asm
0x1400210a8  mov     [rsp+arg_0], rbx
0x1400210ad  mov     [rsp+arg_8], rsi
0x1400210b2  push    rdi
0x1400210b3  sub     rsp, 20h
0x1400210b7  mov     rax, cs:qword_14001D870
0x1400210be  mov     rbx, r8
0x1400210c1  movzx   esi, dl
0x1400210c4  mov     rdi, rcx
0x1400210c7  test    rax, rax
0x1400210ca  jz      short loc_1400210D6
0x1400210cc  mov     dl, sil
0x1400210cf  call    rax ; qword_14001D870
0x1400210d1  nop     dword ptr [rax]
0x1400210d4  jmp     short loc_1400210F1
0x1400210d6  mov     r8d, 1; Alignment
0x1400210dc  mov     rdx, rbx; Length
0x1400210df  call    ProbeForRead_0
0x1400210e4  mov     edx, esi; Val
0x1400210e6  mov     r8, rbx; Size
0x1400210e9  mov     rcx, rdi; void *
0x1400210ec  call    RtlSetVolatileMemory
0x1400210f1  mov     rbx, [rsp+28h+arg_0]
0x1400210f6  mov     rsi, [rsp+28h+arg_8]
0x1400210fb  add     rsp, 20h
0x1400210ff  pop     rdi
0x140021100  retn
```
