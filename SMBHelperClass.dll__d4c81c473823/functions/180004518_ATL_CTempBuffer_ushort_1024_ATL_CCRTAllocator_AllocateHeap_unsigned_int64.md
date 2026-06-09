# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180004518`
- end: `0x180004543`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003f3c`
- `0x18000766c`

## callees

- `0x180004518`
- `0x180004684`

## import_xrefs

- `msvcrt!malloc` at `0x180004524`
- `msvcrt!malloc` at `0x180004524`

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
0x180004518  push    rbx
0x18000451a  sub     rsp, 20h
0x18000451e  mov     rbx, rcx
0x180004521  mov     rcx, rdx; Size
0x180004524  call    cs:__imp_malloc
0x18000452a  test    rax, rax
0x18000452d  jz      short loc_180004538
0x18000452f  mov     [rbx], rax
0x180004532  add     rsp, 20h
0x180004536  pop     rbx
0x180004537  retn
0x180004538  mov     ecx, 8007000Eh; int
0x18000453d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
