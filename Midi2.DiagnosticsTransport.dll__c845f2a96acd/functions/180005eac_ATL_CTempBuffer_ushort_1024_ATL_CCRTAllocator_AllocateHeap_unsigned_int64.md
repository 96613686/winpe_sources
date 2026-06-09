# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180005eac`
- end: `0x180005ed7`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800058d0`
- `0x18000824c`

## callees

- `0x180005eac`
- `0x180006018`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180005eb8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180005eb8`

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
0x180005eac  push    rbx
0x180005eae  sub     rsp, 20h
0x180005eb2  mov     rbx, rcx
0x180005eb5  mov     rcx, rdx; Size
0x180005eb8  call    cs:__imp_malloc
0x180005ebe  test    rax, rax
0x180005ec1  jz      short loc_180005ECC
0x180005ec3  mov     [rbx], rax
0x180005ec6  add     rsp, 20h
0x180005eca  pop     rbx
0x180005ecb  retn
0x180005ecc  mov     ecx, 8007000Eh; int
0x180005ed1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
