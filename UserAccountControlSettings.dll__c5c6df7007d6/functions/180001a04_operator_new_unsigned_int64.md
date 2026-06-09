# operator new(unsigned __int64)

- ea: `0x180001a04`
- end: `0x180001a3d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800031b4`
- `0x180003224`
- `0x180003380`
- `0x180003650`
- `0x180005d88`
- `0x180008a04`

## callees

- `0x180001a04`
- `0x1800021cd`
- `0x1800021d9`

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
0x180001a04  mov     [rsp+arg_0], rbx
0x180001a09  push    rdi
0x180001a0a  sub     rsp, 20h
0x180001a0e  mov     rdi, rcx
0x180001a11  jmp     short loc_180001A22
0x180001a13  mov     rcx, rdi; Size
0x180001a16  call    _callnewh_0
0x180001a1b  test    eax, eax
0x180001a1d  jz      short loc_180001A2F
0x180001a1f  mov     rcx, rdi; Size
0x180001a22  call    malloc_0
0x180001a27  mov     rbx, rax
0x180001a2a  test    rax, rax
0x180001a2d  jz      short loc_180001A13
0x180001a2f  mov     rax, rbx
0x180001a32  mov     rbx, [rsp+28h+arg_0]
0x180001a37  add     rsp, 20h
0x180001a3b  pop     rdi
0x180001a3c  retn
```
