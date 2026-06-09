# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180002ba8`
- end: `0x180002bd3`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800026a4`
- `0x180004038`

## callees

- `0x180002ba8`
- `0x180003558`

## import_xrefs

- `msvcrt!malloc` at `0x180002bb4`
- `msvcrt!malloc` at `0x180002bb4`

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
0x180002ba8  push    rbx
0x180002baa  sub     rsp, 20h
0x180002bae  mov     rbx, rcx
0x180002bb1  mov     rcx, rdx; Size
0x180002bb4  call    cs:__imp_malloc
0x180002bba  test    rax, rax
0x180002bbd  jz      short loc_180002BC8
0x180002bbf  mov     [rbx], rax
0x180002bc2  add     rsp, 20h
0x180002bc6  pop     rbx
0x180002bc7  retn
0x180002bc8  mov     ecx, 8007000Eh; int
0x180002bcd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
