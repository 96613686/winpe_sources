# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x18000468c`
- end: `0x1800046b7`
- name: `?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800040b0`
- `0x180006a2c`

## callees

- `0x18000468c`
- `0x1800047f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180004698`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180004698`

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
0x18000468c  push    rbx
0x18000468e  sub     rsp, 20h
0x180004692  mov     rbx, rcx
0x180004695  mov     rcx, rdx; Size
0x180004698  call    cs:__imp_malloc
0x18000469e  test    rax, rax
0x1800046a1  jz      short loc_1800046AC
0x1800046a3  mov     [rbx], rax
0x1800046a6  add     rsp, 20h
0x1800046aa  pop     rbx
0x1800046ab  retn
0x1800046ac  mov     ecx, 8007000Eh; int
0x1800046b1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
