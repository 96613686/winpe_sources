# operator new(unsigned __int64)

- ea: `0x180001130`
- end: `0x180001169`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x18000333c`
- `0x18000340c`
- `0x180003538`
- `0x1800039d4`
- `0x180003b9c`
- `0x1800050f0`
- `0x180007c70`
- `0x180007f1c`

## callees

- `0x180001130`
- `0x18000164e`
- `0x18000165a`

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
0x180001130  mov     [rsp+arg_0], rbx
0x180001135  push    rdi
0x180001136  sub     rsp, 20h
0x18000113a  mov     rdi, rcx
0x18000113d  jmp     short loc_18000114E
0x18000113f  mov     rcx, rdi; Size
0x180001142  call    _callnewh_0
0x180001147  test    eax, eax
0x180001149  jz      short loc_18000115B
0x18000114b  mov     rcx, rdi; Size
0x18000114e  call    malloc_0
0x180001153  mov     rbx, rax
0x180001156  test    rax, rax
0x180001159  jz      short loc_18000113F
0x18000115b  mov     rax, rbx
0x18000115e  mov     rbx, [rsp+28h+arg_0]
0x180001163  add     rsp, 20h
0x180001167  pop     rdi
0x180001168  retn
```
