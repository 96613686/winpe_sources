# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180003c78`
- end: `0x180003ca3`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000369c`
- `0x1800056b8`

## callees

- `0x180003c78`
- `0x180004740`

## import_xrefs

- `msvcrt!malloc` at `0x180003c84`
- `msvcrt!malloc` at `0x180003c84`

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
0x180003c78  push    rbx
0x180003c7a  sub     rsp, 20h
0x180003c7e  mov     rbx, rcx
0x180003c81  mov     rcx, rdx; Size
0x180003c84  call    cs:__imp_malloc
0x180003c8a  test    rax, rax
0x180003c8d  jz      short loc_180003C98
0x180003c8f  mov     [rbx], rax
0x180003c92  add     rsp, 20h
0x180003c96  pop     rbx
0x180003c97  retn
0x180003c98  mov     ecx, 8007000Eh; int
0x180003c9d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
