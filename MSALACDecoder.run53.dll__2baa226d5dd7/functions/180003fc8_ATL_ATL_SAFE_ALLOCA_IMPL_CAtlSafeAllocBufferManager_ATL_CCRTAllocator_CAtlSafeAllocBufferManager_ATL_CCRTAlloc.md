# ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)

- ea: `0x180003fc8`
- end: `0x180003ff0`
- name: `??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a148`
- `0x18000a1da`

## callees

- `0x180003fc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003fdc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003fdc`

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
0x180003fc8  push    rbx
0x180003fca  sub     rsp, 20h
0x180003fce  mov     rbx, rcx
0x180003fd1  mov     rcx, [rcx]
0x180003fd4  jmp     short loc_180003FE5
0x180003fd6  mov     rax, [rcx]
0x180003fd9  mov     [rbx], rax
0x180003fdc  call    cs:__imp_free
0x180003fe2  mov     rcx, [rbx]; Block
0x180003fe5  test    rcx, rcx
0x180003fe8  jnz     short loc_180003FD6
0x180003fea  add     rsp, 20h
0x180003fee  pop     rbx
0x180003fef  retn
```
