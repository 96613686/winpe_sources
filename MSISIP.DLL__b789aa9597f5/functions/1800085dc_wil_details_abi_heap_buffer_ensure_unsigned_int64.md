# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x1800085dc`
- end: `0x180008605`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `41`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004b60`
- `0x1800064b0`
- `0x180008578`
- `0x1800095a8`

## callees

- `0x1800085dc`
- `0x18000cc9c`

## pseudocode

```c
bool __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v2; // r8

  v2 = *((_QWORD *)this + 2) - *(_QWORD *)this;
  if ( a2 + *((_QWORD *)this + 1) - *(_QWORD *)this < v2 )
    return 1;
  if ( a2 < 2 * v2 )
    a2 = 2 * v2;
  return wil::details_abi::heap_buffer::reserve(this, a2);
}

```

## disassembly

```asm
0x1800085dc  mov     rax, [rcx+8]
0x1800085e0  sub     rax, [rcx]
0x1800085e3  mov     r8, [rcx+10h]
0x1800085e7  add     rax, rdx
0x1800085ea  sub     r8, [rcx]
0x1800085ed  cmp     rax, r8
0x1800085f0  jnb     short loc_1800085F5
0x1800085f2  mov     al, 1
0x1800085f4  retn
0x1800085f5  lea     rax, [r8+r8]
0x1800085f9  cmp     rdx, rax
0x1800085fc  cmovb   rdx, rax; unsigned __int64
0x180008600  jmp     ?reserve@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::reserve(unsigned __int64)
```
