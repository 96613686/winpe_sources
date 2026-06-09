# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x18000385c`
- end: `0x180003887`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003280`
- `0x180005588`

## callees

- `0x18000385c`
- `0x180004328`

## import_xrefs

- `msvcrt!malloc` at `0x180003868`
- `msvcrt!malloc` at `0x180003868`

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
0x18000385c  push    rbx
0x18000385e  sub     rsp, 20h
0x180003862  mov     rbx, rcx
0x180003865  mov     rcx, rdx; Size
0x180003868  call    cs:__imp_malloc
0x18000386e  test    rax, rax
0x180003871  jz      short loc_18000387C
0x180003873  mov     [rbx], rax
0x180003876  add     rsp, 20h
0x18000387a  pop     rbx
0x18000387b  retn
0x18000387c  mov     ecx, 8007000Eh; int
0x180003881  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
