# operator new(unsigned __int64)

- ea: `0x180006b8c`
- end: `0x180006bc5`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x1800019d0`
- `0x180001c80`
- `0x1800021c0`
- `0x180003000`
- `0x180003104`
- `0x180003fb8`
- `0x1800056c0`
- `0x180005c80`
- `0x180005dc0`
- `0x180006bcc`
- `0x180008718`
- `0x18000a474`

## callees

- `0x180006b8c`
- `0x1800074b6`
- `0x180007671`

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
0x180006b8c  mov     [rsp+arg_0], rbx
0x180006b91  push    rdi
0x180006b92  sub     rsp, 20h
0x180006b96  mov     rdi, rcx
0x180006b99  jmp     short loc_180006BAA
0x180006b9b  mov     rcx, rdi; Size
0x180006b9e  call    _callnewh_0
0x180006ba3  test    eax, eax
0x180006ba5  jz      short loc_180006BB7
0x180006ba7  mov     rcx, rdi; Size
0x180006baa  call    malloc_0
0x180006baf  mov     rbx, rax
0x180006bb2  test    rax, rax
0x180006bb5  jz      short loc_180006B9B
0x180006bb7  mov     rax, rbx
0x180006bba  mov     rbx, [rsp+28h+arg_0]
0x180006bbf  add     rsp, 20h
0x180006bc3  pop     rdi
0x180006bc4  retn
```
