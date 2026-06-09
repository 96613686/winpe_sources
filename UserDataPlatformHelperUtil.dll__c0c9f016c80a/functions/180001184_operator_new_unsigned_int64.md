# operator new(unsigned __int64)

- ea: `0x180001184`
- end: `0x1800011bd`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x18000116c`
- `0x1800016e8`
- `0x180003ef0`
- `0x180004060`
- `0x180004180`
- `0x180008420`
- `0x180009574`
- `0x180009ca0`

## callees

- `0x180001184`
- `0x1800016a2`
- `0x1800018d5`

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
0x180001184  mov     [rsp+arg_0], rbx
0x180001189  push    rdi
0x18000118a  sub     rsp, 20h
0x18000118e  mov     rdi, rcx
0x180001191  jmp     short loc_1800011A2
0x180001193  mov     rcx, rdi; Size
0x180001196  call    _callnewh_0
0x18000119b  test    eax, eax
0x18000119d  jz      short loc_1800011AF
0x18000119f  mov     rcx, rdi; Size
0x1800011a2  call    malloc_0
0x1800011a7  mov     rbx, rax
0x1800011aa  test    rax, rax
0x1800011ad  jz      short loc_180001193
0x1800011af  mov     rax, rbx
0x1800011b2  mov     rbx, [rsp+28h+arg_0]
0x1800011b7  add     rsp, 20h
0x1800011bb  pop     rdi
0x1800011bc  retn
```
