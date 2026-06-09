# ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x1800034f8`
- end: `0x180003523`
- name: `?AllocateHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002e4c`
- `0x1800050c0`

## callees

- `0x1800034f8`
- `0x1800037f4`

## import_xrefs

- `msvcrt!malloc` at `0x180003504`
- `msvcrt!malloc` at `0x180003504`

## pseudocode

```c
void *__fastcall ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::AllocateHeap(_QWORD *a1, size_t a2)
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
0x1800034f8  push    rbx
0x1800034fa  sub     rsp, 20h
0x1800034fe  mov     rbx, rcx
0x180003501  mov     rcx, rdx; Size
0x180003504  call    cs:__imp_malloc
0x18000350a  test    rax, rax
0x18000350d  jz      short loc_180003518
0x18000350f  mov     [rbx], rax
0x180003512  add     rsp, 20h
0x180003516  pop     rbx
0x180003517  retn
0x180003518  mov     ecx, 8007000Eh; int
0x18000351d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
