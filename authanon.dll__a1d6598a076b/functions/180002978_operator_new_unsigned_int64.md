# operator new(unsigned __int64)

- ea: `0x180002978`
- end: `0x1800029b1`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180002080`
- `0x180003f30`
- `0x1800043b8`
- `0x180005354`

## callees

- `0x180002978`
- `0x180002ea2`
- `0x180002eae`

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
0x180002978  mov     [rsp+arg_0], rbx
0x18000297d  push    rdi
0x18000297e  sub     rsp, 20h
0x180002982  mov     rdi, rcx
0x180002985  jmp     short loc_180002996
0x180002987  mov     rcx, rdi; Size
0x18000298a  call    _callnewh_0
0x18000298f  test    eax, eax
0x180002991  jz      short loc_1800029A3
0x180002993  mov     rcx, rdi; Size
0x180002996  call    malloc_0
0x18000299b  mov     rbx, rax
0x18000299e  test    rax, rax
0x1800029a1  jz      short loc_180002987
0x1800029a3  mov     rax, rbx
0x1800029a6  mov     rbx, [rsp+28h+arg_0]
0x1800029ab  add     rsp, 20h
0x1800029af  pop     rdi
0x1800029b0  retn
```
