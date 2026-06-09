# ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)

- ea: `0x1800065fc`
- end: `0x180006624`
- name: `??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180004710`
- `0x180007ed0`
- `0x180007f20`
- `0x180008ad8`
- `0x1800091d4`
- `0x18000b934`
- `0x18000bd56`

## callees

- `0x1800065fc`

## import_xrefs

- `msvcrt!free` at `0x180006610`
- `msvcrt!free` at `0x180006610`

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
0x1800065fc  push    rbx
0x1800065fe  sub     rsp, 20h
0x180006602  mov     rbx, rcx
0x180006605  mov     rcx, [rcx]
0x180006608  jmp     short loc_180006619
0x18000660a  mov     rax, [rcx]
0x18000660d  mov     [rbx], rax
0x180006610  call    cs:__imp_free
0x180006616  mov     rcx, [rbx]; Block
0x180006619  test    rcx, rcx
0x18000661c  jnz     short loc_18000660A
0x18000661e  add     rsp, 20h
0x180006622  pop     rbx
0x180006623  retn
```
