# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x1800037c8`
- end: `0x1800037f3`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ea0`
- `0x1800055ec`

## callees

- `0x1800037c8`
- `0x180004484`

## import_xrefs

- `ucrtbase_clr0400!malloc` at `0x1800037d4`
- `ucrtbase_clr0400!malloc` at `0x1800037d4`

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
0x1800037c8  push    rbx
0x1800037ca  sub     rsp, 20h
0x1800037ce  mov     rbx, rcx
0x1800037d1  mov     rcx, rdx; Size
0x1800037d4  call    cs:__imp_malloc
0x1800037da  test    rax, rax
0x1800037dd  jz      short loc_1800037E8
0x1800037df  mov     [rbx], rax
0x1800037e2  add     rsp, 20h
0x1800037e6  pop     rbx
0x1800037e7  retn
0x1800037e8  mov     ecx, 8007000Eh; int
0x1800037ed  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
