# ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)

- ea: `0x180004c88`
- end: `0x180004cb0`
- name: `??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001216f`
- `0x180012201`
- `0x180012213`

## callees

- `0x180004c88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004c9c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004c9c`

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
0x180004c88  push    rbx
0x180004c8a  sub     rsp, 20h
0x180004c8e  mov     rbx, rcx
0x180004c91  mov     rcx, [rcx]
0x180004c94  jmp     short loc_180004CA5
0x180004c96  mov     rax, [rcx]
0x180004c99  mov     [rbx], rax
0x180004c9c  call    cs:__imp_free
0x180004ca2  mov     rcx, [rbx]; Block
0x180004ca5  test    rcx, rcx
0x180004ca8  jnz     short loc_180004C96
0x180004caa  add     rsp, 20h
0x180004cae  pop     rbx
0x180004caf  retn
```
