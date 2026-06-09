# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x140004c34`
- end: `0x140004c5f`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400046ac`
- `0x1400095a4`

## callees

- `0x140004c34`
- `0x140004f54`

## import_xrefs

- `msvcrt!malloc` at `0x140004c40`
- `msvcrt!malloc` at `0x140004c40`

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
0x140004c34  push    rbx
0x140004c36  sub     rsp, 20h
0x140004c3a  mov     rbx, rcx
0x140004c3d  mov     rcx, rdx; Size
0x140004c40  call    cs:__imp_malloc
0x140004c46  test    rax, rax
0x140004c49  jnz     short loc_140004C56
0x140004c4b  mov     ecx, 8007000Eh; int
0x140004c50  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140004c56  mov     [rbx], rax
0x140004c59  add     rsp, 20h
0x140004c5d  pop     rbx
0x140004c5e  retn
```
