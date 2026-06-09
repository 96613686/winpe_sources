# operator new(unsigned __int64)

- ea: `0x140001918`
- end: `0x140001951`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400013c8`

## callees

- `0x140001918`
- `0x140001957`
- `0x140001963`

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
0x140001918  mov     [rsp+arg_0], rbx
0x14000191d  push    rdi
0x14000191e  sub     rsp, 20h
0x140001922  mov     rdi, rcx
0x140001925  jmp     short loc_140001936
0x140001927  mov     rcx, rdi; Size
0x14000192a  call    _callnewh_0
0x14000192f  test    eax, eax
0x140001931  jz      short loc_140001943
0x140001933  mov     rcx, rdi; Size
0x140001936  call    malloc_0
0x14000193b  mov     rbx, rax
0x14000193e  test    rax, rax
0x140001941  jz      short loc_140001927
0x140001943  mov     rax, rbx
0x140001946  mov     rbx, [rsp+28h+arg_0]
0x14000194b  add     rsp, 20h
0x14000194f  pop     rdi
0x140001950  retn
```
