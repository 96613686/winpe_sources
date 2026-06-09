# operator new(unsigned __int64)

- ea: `0x14000196c`
- end: `0x1400019a5`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140005b40`
- `0x140005c30`

## callees

- `0x14000196c`
- `0x14000257a`
- `0x140002660`

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
0x14000196c  mov     [rsp+arg_0], rbx
0x140001971  push    rdi
0x140001972  sub     rsp, 20h
0x140001976  mov     rdi, rcx
0x140001979  jmp     short loc_14000198A
0x14000197b  mov     rcx, rdi
0x14000197e  call    _o__callnewh_0
0x140001983  test    eax, eax
0x140001985  jz      short loc_140001997
0x140001987  mov     rcx, rdi; Size
0x14000198a  call    _o_malloc_0
0x14000198f  mov     rbx, rax
0x140001992  test    rax, rax
0x140001995  jz      short loc_14000197B
0x140001997  mov     rax, rbx
0x14000199a  mov     rbx, [rsp+28h+arg_0]
0x14000199f  add     rsp, 20h
0x1400019a3  pop     rdi
0x1400019a4  retn
```
