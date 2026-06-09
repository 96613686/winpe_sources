# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180004c08`
- end: `0x180004c33`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000462c`
- `0x180005e98`

## callees

- `0x180004c08`
- `0x180004e40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180004c14`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180004c14`

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
0x180004c08  push    rbx
0x180004c0a  sub     rsp, 20h
0x180004c0e  mov     rbx, rcx
0x180004c11  mov     rcx, rdx; Size
0x180004c14  call    cs:__imp_malloc
0x180004c1a  test    rax, rax
0x180004c1d  jz      short loc_180004C28
0x180004c1f  mov     [rbx], rax
0x180004c22  add     rsp, 20h
0x180004c26  pop     rbx
0x180004c27  retn
0x180004c28  mov     ecx, 8007000Eh; int
0x180004c2d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
