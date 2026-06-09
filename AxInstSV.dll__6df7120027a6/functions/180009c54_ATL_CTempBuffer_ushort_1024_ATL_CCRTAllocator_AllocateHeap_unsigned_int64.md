# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180009c54`
- end: `0x180009c7f`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800096cc`
- `0x18000e660`

## callees

- `0x180003208`
- `0x180009c54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180009c60`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180009c60`

## pseudocode

```c
void *__fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(_QWORD *a1, size_t a2)
{
  void *result; // rax

  result = malloc(a2);
  if ( !result )
    ATL::AtlThrowImpl(-2147024882);
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x180009c54  push    rbx
0x180009c56  sub     rsp, 20h
0x180009c5a  mov     rbx, rcx
0x180009c5d  mov     rcx, rdx; Size
0x180009c60  call    cs:__imp_malloc
0x180009c66  test    rax, rax
0x180009c69  jnz     short loc_180009C76
0x180009c6b  mov     ecx, 8007000Eh; int
0x180009c70  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009c76  mov     [rbx], rax
0x180009c79  add     rsp, 20h
0x180009c7d  pop     rbx
0x180009c7e  retn
```
