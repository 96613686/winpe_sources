# operator new(unsigned __int64)

- ea: `0x1800150c4`
- end: `0x1800150fd`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `22`
- callee_count: `3`
- tags: ``

## callers

- `0x180007030`
- `0x180008804`
- `0x180008bdc`
- `0x18000a4f0`
- `0x18000b874`
- `0x18000bbb8`
- `0x18000c8f4`
- `0x18000cb14`
- `0x18000e510`
- `0x18000e570`
- `0x18000e5d0`
- `0x18000e6d0`
- `0x18000e900`
- `0x18000fb40`
- `0x18000fbf0`
- `0x18000fdb4`
- `0x180010200`
- `0x180010680`
- `0x180016114`
- `0x180016a10`
- `0x18001f910`
- `0x18007a7f0`

## callees

- `0x1800150c4`
- `0x180015d72`
- `0x180015e3c`

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
0x1800150c4  mov     [rsp+arg_0], rbx
0x1800150c9  push    rdi
0x1800150ca  sub     rsp, 20h
0x1800150ce  mov     rdi, rcx
0x1800150d1  jmp     short loc_1800150E2
0x1800150d3  mov     rcx, rdi
0x1800150d6  call    _o__callnewh_0
0x1800150db  test    eax, eax
0x1800150dd  jz      short loc_1800150EF
0x1800150df  mov     rcx, rdi; Size
0x1800150e2  call    _o_malloc_0
0x1800150e7  mov     rbx, rax
0x1800150ea  test    rax, rax
0x1800150ed  jz      short loc_1800150D3
0x1800150ef  mov     rax, rbx
0x1800150f2  mov     rbx, [rsp+28h+arg_0]
0x1800150f7  add     rsp, 20h
0x1800150fb  pop     rdi
0x1800150fc  retn
```
