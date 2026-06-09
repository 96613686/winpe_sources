# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x18001fa78`
- end: `0x18001faa3`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f49c`
- `0x180021228`

## callees

- `0x18001fa78`
- `0x180020178`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001fa84`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001fa84`

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
0x18001fa78  push    rbx
0x18001fa7a  sub     rsp, 20h
0x18001fa7e  mov     rbx, rcx
0x18001fa81  mov     rcx, rdx; Size
0x18001fa84  call    cs:__imp_malloc
0x18001fa8a  test    rax, rax
0x18001fa8d  jz      short loc_18001FA98
0x18001fa8f  mov     [rbx], rax
0x18001fa92  add     rsp, 20h
0x18001fa96  pop     rbx
0x18001fa97  retn
0x18001fa98  mov     ecx, 8007000Eh; int
0x18001fa9d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
