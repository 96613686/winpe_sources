# operator new(unsigned __int64)

- ea: `0x18000152c`
- end: `0x180001565`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180001c48`
- `0x180011540`
- `0x18001162c`
- `0x180011730`

## callees

- `0x18000152c`
- `0x180001c79`
- `0x180001d55`

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
0x18000152c  mov     [rsp+arg_0], rbx
0x180001531  push    rdi
0x180001532  sub     rsp, 20h
0x180001536  mov     rdi, rcx
0x180001539  jmp     short loc_18000154A
0x18000153b  mov     rcx, rdi; Size
0x18000153e  call    _callnewh_0
0x180001543  test    eax, eax
0x180001545  jz      short loc_180001557
0x180001547  mov     rcx, rdi; Size
0x18000154a  call    malloc_0
0x18000154f  mov     rbx, rax
0x180001552  test    rax, rax
0x180001555  jz      short loc_18000153B
0x180001557  mov     rax, rbx
0x18000155a  mov     rbx, [rsp+28h+arg_0]
0x18000155f  add     rsp, 20h
0x180001563  pop     rdi
0x180001564  retn
```
