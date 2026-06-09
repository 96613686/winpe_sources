# operator new(unsigned __int64)

- ea: `0x140001b34`
- end: `0x140001b6d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140006a88`
- `0x140008090`
- `0x140008710`
- `0x14000aaa4`

## callees

- `0x140001b34`
- `0x140001b8c`
- `0x140001b98`

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
0x140001b34  mov     [rsp+arg_0], rbx
0x140001b39  push    rdi
0x140001b3a  sub     rsp, 20h
0x140001b3e  mov     rdi, rcx
0x140001b41  jmp     short loc_140001B52
0x140001b43  mov     rcx, rdi; Size
0x140001b46  call    _callnewh_0
0x140001b4b  test    eax, eax
0x140001b4d  jz      short loc_140001B5F
0x140001b4f  mov     rcx, rdi; Size
0x140001b52  call    malloc_0
0x140001b57  mov     rbx, rax
0x140001b5a  test    rax, rax
0x140001b5d  jz      short loc_140001B43
0x140001b5f  mov     rax, rbx
0x140001b62  mov     rbx, [rsp+28h+arg_0]
0x140001b67  add     rsp, 20h
0x140001b6b  pop     rdi
0x140001b6c  retn
```
