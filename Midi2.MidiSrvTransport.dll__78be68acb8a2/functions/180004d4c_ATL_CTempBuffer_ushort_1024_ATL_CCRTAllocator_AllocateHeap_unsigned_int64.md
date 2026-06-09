# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x180004d4c`
- end: `0x180004d77`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004770`
- `0x1800070fc`

## callees

- `0x180004d4c`
- `0x180004eb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180004d58`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180004d58`

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
0x180004d4c  push    rbx
0x180004d4e  sub     rsp, 20h
0x180004d52  mov     rbx, rcx
0x180004d55  mov     rcx, rdx; Size
0x180004d58  call    cs:__imp_malloc
0x180004d5e  test    rax, rax
0x180004d61  jz      short loc_180004D6C
0x180004d63  mov     [rbx], rax
0x180004d66  add     rsp, 20h
0x180004d6a  pop     rbx
0x180004d6b  retn
0x180004d6c  mov     ecx, 8007000Eh; int
0x180004d71  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
