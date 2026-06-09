# ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)

- ea: `0x18000d75c`
- end: `0x18000d787`
- name: `?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z`
- size: `43`
- prototype: `void *__fastcall(_QWORD *, size_t)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012b04`

## callees

- `0x18000b410`
- `0x18000d75c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d768`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d768`

## pseudocode

```c
void *__fastcall ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(_QWORD *a1, size_t a2)
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
0x18000d75c  push    rbx
0x18000d75e  sub     rsp, 20h
0x18000d762  mov     rbx, rcx
0x18000d765  mov     rcx, rdx; Size
0x18000d768  call    cs:__imp_malloc
0x18000d76e  test    rax, rax
0x18000d771  jz      short loc_18000D77C
0x18000d773  mov     [rbx], rax
0x18000d776  add     rsp, 20h
0x18000d77a  pop     rbx
0x18000d77b  retn
0x18000d77c  mov     ecx, 8007000Eh; int
0x18000d781  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
