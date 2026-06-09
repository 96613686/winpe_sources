# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x1800059dc`
- end: `0x180005a07`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004710`
- `0x180007f20`

## callees

- `0x1800059dc`
- `0x180005a10`

## import_xrefs

- `msvcrt!malloc` at `0x1800059e8`
- `msvcrt!malloc` at `0x1800059e8`

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
0x1800059dc  push    rbx
0x1800059de  sub     rsp, 20h
0x1800059e2  mov     rbx, rcx
0x1800059e5  mov     rcx, rdx; Size
0x1800059e8  call    cs:__imp_malloc
0x1800059ee  test    rax, rax
0x1800059f1  jnz     short loc_1800059FE
0x1800059f3  mov     ecx, 8007000Eh; int
0x1800059f8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800059fe  mov     [rbx], rax
0x180005a01  add     rsp, 20h
0x180005a05  pop     rbx
0x180005a06  retn
```
