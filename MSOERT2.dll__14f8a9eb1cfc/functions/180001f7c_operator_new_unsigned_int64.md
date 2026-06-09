# operator new(unsigned __int64)

- ea: `0x180001f7c`
- end: `0x180001fb5`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x180001820`
- `0x180001980`
- `0x180001b60`
- `0x180001fc8`
- `0x180004ba0`
- `0x180004f50`
- `0x180005d20`
- `0x180005f30`
- `0x180006330`
- `0x1800091c0`
- `0x180009834`
- `0x18000a420`
- `0x180010820`
- `0x1800109a0`
- `0x180011040`

## callees

- `0x180001f7c`
- `0x1800027c4`
- `0x1800027d0`

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
0x180001f7c  mov     [rsp+arg_0], rbx
0x180001f81  push    rdi
0x180001f82  sub     rsp, 20h
0x180001f86  mov     rdi, rcx
0x180001f89  jmp     short loc_180001F9A
0x180001f8b  mov     rcx, rdi; Size
0x180001f8e  call    _callnewh_0
0x180001f93  test    eax, eax
0x180001f95  jz      short loc_180001FA7
0x180001f97  mov     rcx, rdi; Size
0x180001f9a  call    malloc_0
0x180001f9f  mov     rbx, rax
0x180001fa2  test    rax, rax
0x180001fa5  jz      short loc_180001F8B
0x180001fa7  mov     rax, rbx
0x180001faa  mov     rbx, [rsp+28h+arg_0]
0x180001faf  add     rsp, 20h
0x180001fb3  pop     rdi
0x180001fb4  retn
```
