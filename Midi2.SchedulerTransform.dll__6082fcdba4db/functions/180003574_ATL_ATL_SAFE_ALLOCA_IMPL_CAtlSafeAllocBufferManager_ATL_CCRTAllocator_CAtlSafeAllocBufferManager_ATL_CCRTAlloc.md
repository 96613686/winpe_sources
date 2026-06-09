# ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)

- ea: `0x180003574`
- end: `0x18000359c`
- name: `??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cdff`
- `0x18000ce91`
- `0x18000cea3`

## callees

- `0x180003574`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003588`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003588`

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
0x180003574  push    rbx
0x180003576  sub     rsp, 20h
0x18000357a  mov     rbx, rcx
0x18000357d  mov     rcx, [rcx]
0x180003580  jmp     short loc_180003591
0x180003582  mov     rax, [rcx]
0x180003585  mov     [rbx], rax
0x180003588  call    cs:__imp_free
0x18000358e  mov     rcx, [rbx]; Block
0x180003591  test    rcx, rcx
0x180003594  jnz     short loc_180003582
0x180003596  add     rsp, 20h
0x18000359a  pop     rbx
0x18000359b  retn
```
