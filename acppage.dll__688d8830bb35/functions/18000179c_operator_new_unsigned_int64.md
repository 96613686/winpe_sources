# operator new(unsigned __int64)

- ea: `0x18000179c`
- end: `0x1800017d5`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180008ec8`
- `0x180008fe0`
- `0x18000b170`

## callees

- `0x18000179c`
- `0x180001f96`
- `0x180001fa2`

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
0x18000179c  mov     [rsp+arg_0], rbx
0x1800017a1  push    rdi
0x1800017a2  sub     rsp, 20h
0x1800017a6  mov     rdi, rcx
0x1800017a9  jmp     short loc_1800017BA
0x1800017ab  mov     rcx, rdi; Size
0x1800017ae  call    _callnewh_0
0x1800017b3  test    eax, eax
0x1800017b5  jz      short loc_1800017C7
0x1800017b7  mov     rcx, rdi; Size
0x1800017ba  call    malloc_0
0x1800017bf  mov     rbx, rax
0x1800017c2  test    rax, rax
0x1800017c5  jz      short loc_1800017AB
0x1800017c7  mov     rax, rbx
0x1800017ca  mov     rbx, [rsp+28h+arg_0]
0x1800017cf  add     rsp, 20h
0x1800017d3  pop     rdi
0x1800017d4  retn
```
