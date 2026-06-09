# operator new(unsigned __int64)

- ea: `0x180001a64`
- end: `0x180001a9d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003c90`
- `0x180007930`

## callees

- `0x180001a64`
- `0x18000203d`
- `0x180002049`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = malloc_0(Size);
    if ( v2 || !callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x180001a64  mov     [rsp+arg_0], rbx
0x180001a69  push    rdi
0x180001a6a  sub     rsp, 20h
0x180001a6e  mov     rdi, rcx
0x180001a71  jmp     short loc_180001A82
0x180001a73  mov     rcx, rdi; Size
0x180001a76  call    _callnewh_0
0x180001a7b  test    eax, eax
0x180001a7d  jz      short loc_180001A8F
0x180001a7f  mov     rcx, rdi; Size
0x180001a82  call    malloc_0
0x180001a87  mov     rbx, rax
0x180001a8a  test    rax, rax
0x180001a8d  jz      short loc_180001A73
0x180001a8f  mov     rax, rbx
0x180001a92  mov     rbx, [rsp+28h+arg_0]
0x180001a97  add     rsp, 20h
0x180001a9b  pop     rdi
0x180001a9c  retn
```
