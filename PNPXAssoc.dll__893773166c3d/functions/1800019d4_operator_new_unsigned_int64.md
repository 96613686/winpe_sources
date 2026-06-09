# operator new(unsigned __int64)

- ea: `0x1800019d4`
- end: `0x180001a0d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x1800019c8`
- `0x180006890`
- `0x180006990`
- `0x180006a8c`
- `0x180006b90`
- `0x180006ca0`
- `0x18000bfcc`
- `0x18000ccec`
- `0x18000f6cc`
- `0x18000f95c`
- `0x18000fce0`
- `0x18000ff38`

## callees

- `0x1800019d4`
- `0x180001fad`
- `0x18000235c`

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
0x1800019d4  mov     [rsp+arg_0], rbx
0x1800019d9  push    rdi
0x1800019da  sub     rsp, 20h
0x1800019de  mov     rdi, rcx
0x1800019e1  jmp     short loc_1800019F2
0x1800019e3  mov     rcx, rdi; Size
0x1800019e6  call    _callnewh_0
0x1800019eb  test    eax, eax
0x1800019ed  jz      short loc_1800019FF
0x1800019ef  mov     rcx, rdi; Size
0x1800019f2  call    malloc_0
0x1800019f7  mov     rbx, rax
0x1800019fa  test    rax, rax
0x1800019fd  jz      short loc_1800019E3
0x1800019ff  mov     rax, rbx
0x180001a02  mov     rbx, [rsp+28h+arg_0]
0x180001a07  add     rsp, 20h
0x180001a0b  pop     rdi
0x180001a0c  retn
```
