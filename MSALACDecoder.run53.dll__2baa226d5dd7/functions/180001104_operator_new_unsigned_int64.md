# operator new(unsigned __int64)

- ea: `0x180001104`
- end: `0x18000113d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180001150`
- `0x1800023b0`
- `0x180002ec4`
- `0x180004f84`
- `0x1800050a8`
- `0x1800051b0`

## callees

- `0x180001104`
- `0x180001e0e`
- `0x180001ea0`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = o_malloc_0(Size);
    if ( v2 || !(unsigned int)o__callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x180001104  mov     [rsp+arg_0], rbx
0x180001109  push    rdi
0x18000110a  sub     rsp, 20h
0x18000110e  mov     rdi, rcx
0x180001111  jmp     short loc_180001122
0x180001113  mov     rcx, rdi
0x180001116  call    _o__callnewh_0
0x18000111b  test    eax, eax
0x18000111d  jz      short loc_18000112F
0x18000111f  mov     rcx, rdi; Size
0x180001122  call    _o_malloc_0
0x180001127  mov     rbx, rax
0x18000112a  test    rax, rax
0x18000112d  jz      short loc_180001113
0x18000112f  mov     rax, rbx
0x180001132  mov     rbx, [rsp+28h+arg_0]
0x180001137  add     rsp, 20h
0x18000113b  pop     rdi
0x18000113c  retn
```
