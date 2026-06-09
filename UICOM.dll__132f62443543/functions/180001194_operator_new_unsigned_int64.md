# operator new(unsigned __int64)

- ea: `0x180001194`
- end: `0x1800011cd`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180001188`
- `0x1800052f0`
- `0x180005440`
- `0x180005bc0`

## callees

- `0x180001194`
- `0x180001af1`
- `0x180001b0c`

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
0x180001194  mov     [rsp+arg_0], rbx
0x180001199  push    rdi
0x18000119a  sub     rsp, 20h
0x18000119e  mov     rdi, rcx
0x1800011a1  jmp     short loc_1800011B2
0x1800011a3  mov     rcx, rdi; Size
0x1800011a6  call    _callnewh_0
0x1800011ab  test    eax, eax
0x1800011ad  jz      short loc_1800011BF
0x1800011af  mov     rcx, rdi; Size
0x1800011b2  call    malloc_0
0x1800011b7  mov     rbx, rax
0x1800011ba  test    rax, rax
0x1800011bd  jz      short loc_1800011A3
0x1800011bf  mov     rax, rbx
0x1800011c2  mov     rbx, [rsp+28h+arg_0]
0x1800011c7  add     rsp, 20h
0x1800011cb  pop     rdi
0x1800011cc  retn
```
