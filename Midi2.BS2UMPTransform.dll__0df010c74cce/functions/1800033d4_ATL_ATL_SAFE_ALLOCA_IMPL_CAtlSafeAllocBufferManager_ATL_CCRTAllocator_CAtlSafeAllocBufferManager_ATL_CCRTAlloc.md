# ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)

- ea: `0x1800033d4`
- end: `0x1800033fc`
- name: `??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b58f`
- `0x18000b621`
- `0x18000b633`

## callees

- `0x1800033d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800033e8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800033e8`

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
0x1800033d4  push    rbx
0x1800033d6  sub     rsp, 20h
0x1800033da  mov     rbx, rcx
0x1800033dd  mov     rcx, [rcx]
0x1800033e0  jmp     short loc_1800033F1
0x1800033e2  mov     rax, [rcx]
0x1800033e5  mov     [rbx], rax
0x1800033e8  call    cs:__imp_free
0x1800033ee  mov     rcx, [rbx]; Block
0x1800033f1  test    rcx, rcx
0x1800033f4  jnz     short loc_1800033E2
0x1800033f6  add     rsp, 20h
0x1800033fa  pop     rbx
0x1800033fb  retn
```
