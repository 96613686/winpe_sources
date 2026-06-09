# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x18000479c`
- end: `0x1800047c7`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800041c0`
- `0x180006b3c`

## callees

- `0x18000479c`
- `0x180004908`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800047a8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800047a8`

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
0x18000479c  push    rbx
0x18000479e  sub     rsp, 20h
0x1800047a2  mov     rbx, rcx
0x1800047a5  mov     rcx, rdx; Size
0x1800047a8  call    cs:__imp_malloc
0x1800047ae  test    rax, rax
0x1800047b1  jz      short loc_1800047BC
0x1800047b3  mov     [rbx], rax
0x1800047b6  add     rsp, 20h
0x1800047ba  pop     rbx
0x1800047bb  retn
0x1800047bc  mov     ecx, 8007000Eh; int
0x1800047c1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
