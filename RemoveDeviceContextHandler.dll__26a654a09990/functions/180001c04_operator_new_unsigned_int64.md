# operator new(unsigned __int64)

- ea: `0x180001c04`
- end: `0x180001c3d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180001bf8`
- `0x180007550`
- `0x1800076b0`
- `0x180007800`
- `0x18000b5dc`

## callees

- `0x180001c04`
- `0x1800021ec`
- `0x180002675`

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
0x180001c04  mov     [rsp+arg_0], rbx
0x180001c09  push    rdi
0x180001c0a  sub     rsp, 20h
0x180001c0e  mov     rdi, rcx
0x180001c11  jmp     short loc_180001C22
0x180001c13  mov     rcx, rdi; Size
0x180001c16  call    _callnewh_0
0x180001c1b  test    eax, eax
0x180001c1d  jz      short loc_180001C2F
0x180001c1f  mov     rcx, rdi; Size
0x180001c22  call    malloc_0
0x180001c27  mov     rbx, rax
0x180001c2a  test    rax, rax
0x180001c2d  jz      short loc_180001C13
0x180001c2f  mov     rax, rbx
0x180001c32  mov     rbx, [rsp+28h+arg_0]
0x180001c37  add     rsp, 20h
0x180001c3b  pop     rdi
0x180001c3c  retn
```
