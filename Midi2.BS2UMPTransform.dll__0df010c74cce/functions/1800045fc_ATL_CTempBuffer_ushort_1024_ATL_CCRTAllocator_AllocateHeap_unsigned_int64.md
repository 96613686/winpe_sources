# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x1800045fc`
- end: `0x180004627`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004020`
- `0x18000699c`

## callees

- `0x1800045fc`
- `0x180004768`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180004608`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180004608`

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
0x1800045fc  push    rbx
0x1800045fe  sub     rsp, 20h
0x180004602  mov     rbx, rcx
0x180004605  mov     rcx, rdx; Size
0x180004608  call    cs:__imp_malloc
0x18000460e  test    rax, rax
0x180004611  jz      short loc_18000461C
0x180004613  mov     [rbx], rax
0x180004616  add     rsp, 20h
0x18000461a  pop     rbx
0x18000461b  retn
0x18000461c  mov     ecx, 8007000Eh; int
0x180004621  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
