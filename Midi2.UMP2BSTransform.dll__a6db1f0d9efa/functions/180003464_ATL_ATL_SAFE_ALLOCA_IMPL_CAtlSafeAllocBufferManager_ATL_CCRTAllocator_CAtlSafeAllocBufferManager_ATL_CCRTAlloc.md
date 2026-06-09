# ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)

- ea: `0x180003464`
- end: `0x18000348c`
- name: `??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ea8f`
- `0x18000eb21`
- `0x18000eb33`

## callees

- `0x180003464`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003478`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003478`

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
0x180003464  push    rbx
0x180003466  sub     rsp, 20h
0x18000346a  mov     rbx, rcx
0x18000346d  mov     rcx, [rcx]
0x180003470  jmp     short loc_180003481
0x180003472  mov     rax, [rcx]
0x180003475  mov     [rbx], rax
0x180003478  call    cs:__imp_free
0x18000347e  mov     rcx, [rbx]; Block
0x180003481  test    rcx, rcx
0x180003484  jnz     short loc_180003472
0x180003486  add     rsp, 20h
0x18000348a  pop     rbx
0x18000348b  retn
```
