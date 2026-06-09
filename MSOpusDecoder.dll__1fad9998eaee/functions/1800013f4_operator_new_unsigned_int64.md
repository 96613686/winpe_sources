# operator new(unsigned __int64)

- ea: `0x1800013f4`
- end: `0x18000142d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180001440`
- `0x18001b048`
- `0x1800202b4`
- `0x1800203ec`
- `0x180020500`

## callees

- `0x1800013f4`
- `0x1800021ae`
- `0x180002264`

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
0x1800013f4  mov     [rsp+arg_0], rbx
0x1800013f9  push    rdi
0x1800013fa  sub     rsp, 20h
0x1800013fe  mov     rdi, rcx
0x180001401  jmp     short loc_180001412
0x180001403  mov     rcx, rdi
0x180001406  call    _o__callnewh_0
0x18000140b  test    eax, eax
0x18000140d  jz      short loc_18000141F
0x18000140f  mov     rcx, rdi; Size
0x180001412  call    _o_malloc_0
0x180001417  mov     rbx, rax
0x18000141a  test    rax, rax
0x18000141d  jz      short loc_180001403
0x18000141f  mov     rax, rbx
0x180001422  mov     rbx, [rsp+28h+arg_0]
0x180001427  add     rsp, 20h
0x18000142b  pop     rdi
0x18000142c  retn
```
