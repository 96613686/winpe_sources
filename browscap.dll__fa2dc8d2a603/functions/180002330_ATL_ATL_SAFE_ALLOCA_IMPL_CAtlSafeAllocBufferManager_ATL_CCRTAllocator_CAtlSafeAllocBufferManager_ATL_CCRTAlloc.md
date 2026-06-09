# ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)

- ea: `0x180002330`
- end: `0x180002358`
- name: `??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bb30`
- `0x18000bb54`
- `0x18000bbd3`

## callees

- `0x180002330`

## import_xrefs

- `msvcrt!free` at `0x180002344`
- `msvcrt!free` at `0x180002344`

## pseudocode

```c
void __fastcall ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(
        _QWORD **a1)
{
  _QWORD *i; // rcx

  for ( i = *a1; i; i = *a1 )
  {
    *a1 = (_QWORD *)*i;
    free(i);
  }
}

```

## disassembly

```asm
0x180002330  push    rbx
0x180002332  sub     rsp, 20h
0x180002336  mov     rbx, rcx
0x180002339  mov     rcx, [rcx]
0x18000233c  jmp     short loc_18000234D
0x18000233e  mov     rax, [rcx]
0x180002341  mov     [rbx], rax
0x180002344  call    cs:__imp_free
0x18000234a  mov     rcx, [rbx]; Block
0x18000234d  test    rcx, rcx
0x180002350  jnz     short loc_18000233E
0x180002352  add     rsp, 20h
0x180002356  pop     rbx
0x180002357  retn
```
