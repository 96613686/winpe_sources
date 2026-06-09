# operator new(unsigned __int64)

- ea: `0x180004388`
- end: `0x1800043c1`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001c20`
- `0x180004d50`

## callees

- `0x180004388`
- `0x1800048a6`
- `0x1800048be`

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
0x180004388  mov     [rsp+arg_0], rbx
0x18000438d  push    rdi
0x18000438e  sub     rsp, 20h
0x180004392  mov     rdi, rcx
0x180004395  jmp     short loc_1800043A6
0x180004397  mov     rcx, rdi; Size
0x18000439a  call    _callnewh_0
0x18000439f  test    eax, eax
0x1800043a1  jz      short loc_1800043B3
0x1800043a3  mov     rcx, rdi; Size
0x1800043a6  call    malloc_0
0x1800043ab  mov     rbx, rax
0x1800043ae  test    rax, rax
0x1800043b1  jz      short loc_180004397
0x1800043b3  mov     rax, rbx
0x1800043b6  mov     rbx, [rsp+28h+arg_0]
0x1800043bb  add     rsp, 20h
0x1800043bf  pop     rdi
0x1800043c0  retn
```
