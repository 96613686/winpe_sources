# Pal::Lockable<std::vector<Pal::PerformanceTracerImplWindows *,std::allocator<Pal::PerformanceTracerImplWindows *>>>::~Lockable<std::vector<Pal::PerformanceTracerImplWindows *,std::allocator<Pal::PerformanceTracerImplWindows *>>>(void)

- ea: `0x180010ebc`
- end: `0x180010f05`
- name: `??1?$Lockable@V?$vector@PEAVPerformanceTracerImplWindows@Pal@@V?$allocator@PEAVPerformanceTracerImplWindows@Pal@@@std@@@std@@@Pal@@QEAA@XZ`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011658`

## callees

- `0x18000b938`
- `0x180010ebc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010efe`

## pseudocode

```c
void __fastcall Pal::Lockable<std::vector<Pal::PerformanceTracerImplWindows *>>::~Lockable<std::vector<Pal::PerformanceTracerImplWindows *>>(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)(a1 + 40);
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (*(_QWORD *)(a1 + 56) - (_QWORD)v2) & 0xFFFFFFFFFFFFFFF8uLL);
    *(_QWORD *)(a1 + 40) = 0;
    *(_QWORD *)(a1 + 48) = 0;
    *(_QWORD *)(a1 + 56) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)a1);
}

```

## disassembly

```asm
0x180010ebc  push    rbx
0x180010ebe  sub     rsp, 20h
0x180010ec2  mov     rbx, rcx
0x180010ec5  mov     rcx, [rcx+28h]
0x180010ec9  test    rcx, rcx
0x180010ecc  jz      short loc_180010EF6
0x180010ece  mov     rdx, [rbx+38h]
0x180010ed2  sub     rdx, rcx
0x180010ed5  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180010ed9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180010ede  mov     qword ptr [rbx+28h], 0
0x180010ee6  mov     qword ptr [rbx+30h], 0
0x180010eee  mov     qword ptr [rbx+38h], 0
0x180010ef6  mov     rcx, rbx
0x180010ef9  add     rsp, 20h
0x180010efd  pop     rbx
0x180010efe  jmp     cs:__imp_DeleteCriticalSection
```
