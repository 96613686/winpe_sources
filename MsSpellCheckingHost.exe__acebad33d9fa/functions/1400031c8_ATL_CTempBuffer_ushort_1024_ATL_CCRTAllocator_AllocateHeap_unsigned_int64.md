# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x1400031c8`
- end: `0x1400031f3`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002bec`
- `0x140004eb8`

## callees

- `0x1400031c8`
- `0x140003b88`

## import_xrefs

- `msvcrt!malloc` at `0x1400031d4`
- `msvcrt!malloc` at `0x1400031d4`

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
0x1400031c8  push    rbx
0x1400031ca  sub     rsp, 20h
0x1400031ce  mov     rbx, rcx
0x1400031d1  mov     rcx, rdx; Size
0x1400031d4  call    cs:__imp_malloc
0x1400031da  test    rax, rax
0x1400031dd  jz      short loc_1400031E8
0x1400031df  mov     [rbx], rax
0x1400031e2  add     rsp, 20h
0x1400031e6  pop     rbx
0x1400031e7  retn
0x1400031e8  mov     ecx, 8007000Eh; int
0x1400031ed  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
