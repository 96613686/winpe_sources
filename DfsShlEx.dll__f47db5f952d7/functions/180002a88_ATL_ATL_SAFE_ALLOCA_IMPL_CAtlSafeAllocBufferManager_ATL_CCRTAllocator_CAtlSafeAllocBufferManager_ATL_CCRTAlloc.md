# ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)

- ea: `0x180002a88`
- end: `0x180002ab0`
- name: `??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ae9e`
- `0x18000af30`
- `0x18000af42`

## callees

- `0x180002a88`

## import_xrefs

- `msvcrt!free` at `0x180002a9c`
- `msvcrt!free` at `0x180002a9c`

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
0x180002a88  push    rbx
0x180002a8a  sub     rsp, 20h
0x180002a8e  mov     rbx, rcx
0x180002a91  mov     rcx, [rcx]
0x180002a94  jmp     short loc_180002AA5
0x180002a96  mov     rax, [rcx]
0x180002a99  mov     [rbx], rax
0x180002a9c  call    cs:__imp_free
0x180002aa2  mov     rcx, [rbx]; Block
0x180002aa5  test    rcx, rcx
0x180002aa8  jnz     short loc_180002A96
0x180002aaa  add     rsp, 20h
0x180002aae  pop     rbx
0x180002aaf  retn
```
