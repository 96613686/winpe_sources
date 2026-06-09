# RtlCopyFromUser

- ea: `0x1400034c8`
- end: `0x140003528`
- name: `RtlCopyFromUser`
- size: `96`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140007010`
- `0x140011fb4`
- `0x140025c70`

## callees

- `0x1400034af`
- `0x1400034c8`
- `0x140004bc0`

## pseudocode

```c
__int64 (*__fastcall RtlCopyFromUser(void *a1, void *Src, size_t Size))(void)
{
  __int64 (*result)(void); // rax

  result = _uma_functions;
  if ( _uma_functions )
    return (__int64 (*)(void))_uma_functions();
  if ( Size )
  {
    ProbeForRead_0(Src, Size, 1u);
    return (__int64 (*)(void))RtlCopyVolatileMemory(a1, Src, Size);
  }
  return result;
}

```

## disassembly

```asm
0x1400034c8  mov     [rsp+arg_0], rbx
0x1400034cd  mov     [rsp+arg_8], rsi
0x1400034d2  push    rdi
0x1400034d3  sub     rsp, 20h
0x1400034d7  mov     rax, cs:__uma_functions
0x1400034de  mov     rbx, r8
0x1400034e1  mov     rdi, rdx
0x1400034e4  mov     rsi, rcx
0x1400034e7  test    rax, rax
0x1400034ea  jz      short loc_1400034F3
0x1400034ec  call    rax ; __uma_functions
0x1400034ee  nop     dword ptr [rax]
0x1400034f1  jmp     short loc_140003517
0x1400034f3  test    rbx, rbx
0x1400034f6  jz      short loc_140003517
0x1400034f8  mov     r8d, 1; Alignment
0x1400034fe  mov     rdx, rbx; Length
0x140003501  mov     rcx, rdi; Address
0x140003504  call    ProbeForRead_0
0x140003509  mov     r8, rbx; Size
0x14000350c  mov     rdx, rdi; Src
0x14000350f  mov     rcx, rsi; void *
0x140003512  call    RtlCopyVolatileMemory
0x140003517  mov     rbx, [rsp+28h+arg_0]
0x14000351c  mov     rsi, [rsp+28h+arg_8]
0x140003521  add     rsp, 20h
0x140003525  pop     rdi
0x140003526  retn
```
