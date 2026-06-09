# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x18000586c`
- end: `0x180005897`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005290`
- `0x180007c0c`

## callees

- `0x18000586c`
- `0x1800059d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180005878`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180005878`

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
0x18000586c  push    rbx
0x18000586e  sub     rsp, 20h
0x180005872  mov     rbx, rcx
0x180005875  mov     rcx, rdx; Size
0x180005878  call    cs:__imp_malloc
0x18000587e  test    rax, rax
0x180005881  jz      short loc_18000588C
0x180005883  mov     [rbx], rax
0x180005886  add     rsp, 20h
0x18000588a  pop     rbx
0x18000588b  retn
0x18000588c  mov     ecx, 8007000Eh; int
0x180005891  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
