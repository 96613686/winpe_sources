# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x18000653c`
- end: `0x180006567`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005f60`
- `0x18000891c`

## callees

- `0x18000653c`
- `0x1800066a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006548`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006548`

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
0x18000653c  push    rbx
0x18000653e  sub     rsp, 20h
0x180006542  mov     rbx, rcx
0x180006545  mov     rcx, rdx; Size
0x180006548  call    cs:__imp_malloc
0x18000654e  test    rax, rax
0x180006551  jz      short loc_18000655C
0x180006553  mov     [rbx], rax
0x180006556  add     rsp, 20h
0x18000655a  pop     rbx
0x18000655b  retn
0x18000655c  mov     ecx, 8007000Eh; int
0x180006561  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
