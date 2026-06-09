# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180006c88`
- end: `0x180006cb3`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006784`
- `0x1800096c8`

## callees

- `0x180006c88`
- `0x180006df4`

## import_xrefs

- `msvcrt!malloc` at `0x180006c94`
- `msvcrt!malloc` at `0x180006c94`

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
0x180006c88  push    rbx
0x180006c8a  sub     rsp, 20h
0x180006c8e  mov     rbx, rcx
0x180006c91  mov     rcx, rdx; Size
0x180006c94  call    cs:__imp_malloc
0x180006c9a  test    rax, rax
0x180006c9d  jz      short loc_180006CA8
0x180006c9f  mov     [rbx], rax
0x180006ca2  add     rsp, 20h
0x180006ca6  pop     rbx
0x180006ca7  retn
0x180006ca8  mov     ecx, 8007000Eh; int
0x180006cad  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
