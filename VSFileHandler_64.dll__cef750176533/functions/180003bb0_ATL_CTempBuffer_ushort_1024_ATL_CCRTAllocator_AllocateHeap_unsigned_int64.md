# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180003bb0`
- end: `0x180003bda`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `42`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000421c`
- `0x180005538`

## callees

- `0x180002238`
- `0x180003bb0`
- `0x18000bc80`

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
0x180003bb0  push    rbx
0x180003bb2  sub     rsp, 20h
0x180003bb6  mov     rbx, rcx
0x180003bb9  mov     rcx, rdx; Size
0x180003bbc  call    malloc
0x180003bc1  test    rax, rax
0x180003bc4  jz      short loc_180003BCF
0x180003bc6  mov     [rbx], rax
0x180003bc9  add     rsp, 20h
0x180003bcd  pop     rbx
0x180003bce  retn
0x180003bcf  mov     ecx, 8007000Eh; int
0x180003bd4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
