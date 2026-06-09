# operator new(unsigned __int64)

- ea: `0x180001028`
- end: `0x180001061`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800022e0`
- `0x180002d60`

## callees

- `0x180001028`
- `0x180001cb2`
- `0x180001d12`

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
0x180001028  mov     [rsp+arg_0], rbx
0x18000102d  push    rdi
0x18000102e  sub     rsp, 20h
0x180001032  mov     rdi, rcx
0x180001035  jmp     short loc_180001046
0x180001037  mov     rcx, rdi
0x18000103a  call    _o__callnewh_0
0x18000103f  test    eax, eax
0x180001041  jz      short loc_180001053
0x180001043  mov     rcx, rdi; Size
0x180001046  call    _o_malloc_0
0x18000104b  mov     rbx, rax
0x18000104e  test    rax, rax
0x180001051  jz      short loc_180001037
0x180001053  mov     rax, rbx
0x180001056  mov     rbx, [rsp+28h+arg_0]
0x18000105b  add     rsp, 20h
0x18000105f  pop     rdi
0x180001060  retn
```
