# RtlCopyToUser

- ea: `0x14000f608`
- end: `0x14000f665`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140007020`
- `0x140024a58`
- `0x140025c60`

## callees

- `0x1400034af`
- `0x140004bc0`
- `0x14000f608`

## pseudocode

```c
void *__fastcall RtlCopyToUser(void *a1, void *Src, size_t Size)
{
  void *result; // rax

  result = 0;
  if ( Size )
  {
    ProbeForRead_0(a1, Size, 1u);
    return RtlCopyVolatileMemory(a1, Src, Size);
  }
  return result;
}

```

## disassembly

```asm
0x14000f608  mov     [rsp+arg_0], rbx
0x14000f60d  mov     [rsp+arg_8], rsi
0x14000f612  push    rdi
0x14000f613  sub     rsp, 20h
0x14000f617  mov     rax, cs:qword_14000D540
0x14000f61e  mov     rbx, r8
0x14000f621  mov     rsi, rdx
0x14000f624  mov     rdi, rcx
0x14000f627  test    rax, rax
0x14000f62a  jz      short loc_14000F633
0x14000f62c  call    rax ; qword_14000D540
0x14000f62e  nop     dword ptr [rax]
0x14000f631  jmp     short loc_14000F654
0x14000f633  test    rbx, rbx
0x14000f636  jz      short loc_14000F654
0x14000f638  mov     r8d, 1; Alignment
0x14000f63e  mov     rdx, rbx; Length
0x14000f641  call    ProbeForRead_0
0x14000f646  mov     r8, rbx; Size
0x14000f649  mov     rdx, rsi; Src
0x14000f64c  mov     rcx, rdi; void *
0x14000f64f  call    RtlCopyVolatileMemory
0x14000f654  mov     rbx, [rsp+28h+arg_0]
0x14000f659  mov     rsi, [rsp+28h+arg_8]
0x14000f65e  add     rsp, 20h
0x14000f662  pop     rdi
0x14000f663  retn
```
