# operator new(unsigned __int64)

- ea: `0x18000137c`
- end: `0x1800013b5`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x1800013bc`
- `0x180009498`
- `0x1800095f0`
- `0x180009ff0`
- `0x18000a134`
- `0x18000a220`
- `0x18000bc04`
- `0x18000bd94`
- `0x18000cf58`
- `0x18000d9d0`
- `0x18000e090`

## callees

- `0x18000137c`
- `0x1800024a2`
- `0x180002540`

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
0x18000137c  mov     [rsp+arg_0], rbx
0x180001381  push    rdi
0x180001382  sub     rsp, 20h
0x180001386  mov     rdi, rcx
0x180001389  jmp     short loc_18000139A
0x18000138b  mov     rcx, rdi
0x18000138e  call    _o__callnewh_0
0x180001393  test    eax, eax
0x180001395  jz      short loc_1800013A7
0x180001397  mov     rcx, rdi; Size
0x18000139a  call    _o_malloc_0
0x18000139f  mov     rbx, rax
0x1800013a2  test    rax, rax
0x1800013a5  jz      short loc_18000138B
0x1800013a7  mov     rax, rbx
0x1800013aa  mov     rbx, [rsp+28h+arg_0]
0x1800013af  add     rsp, 20h
0x1800013b3  pop     rdi
0x1800013b4  retn
```
