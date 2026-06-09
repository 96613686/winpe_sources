# Windows::System::Threading::WorkItemHandler::__abi_Release(void)

- ea: `0x14000fba0`
- end: `0x14000fc25`
- name: `?__abi_Release@WorkItemHandler@Threading@System@Windows@@UE$AAAKXZ`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000fc30`
- `0x14000fc40`

## callees

- `0x14000614c`
- `0x14000fba0`
- `0x140035010`

## import_xrefs

- `wincorlib!?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ` at `0x14000fbef`
- `wincorlib!?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ` at `0x14000fbef`
- `wincorlib!?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z` at `0x14000fc0b`
- `wincorlib!?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z` at `0x14000fc0b`
- `wincorlib!?Free@Heap@Details@Platform@@SAXPEAX@Z` at `0x14000fbe2`
- `wincorlib!?Free@Heap@Details@Platform@@SAXPEAX@Z` at `0x14000fc13`
- `wincorlib!?Free@Heap@Details@Platform@@SAXPEAX@Z` at `0x14000fbe2`
- `wincorlib!?Free@Heap@Details@Platform@@SAXPEAX@Z` at `0x14000fc13`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::System::Threading::WorkItemHandler::__abi_Release(__int64 a1)
{
  Platform::Details::ControlBlock **v2; // r14
  unsigned int v3; // edi
  _QWORD *v4; // rbx
  void (__fastcall ***v5)(void *, _QWORD); // rsi
  Platform::Details::ControlBlock *v6; // rbx

  v2 = (Platform::Details::ControlBlock **)(a1 + 24);
  v3 = __abi_FTMWeakRefData::Decrement(a1 + 24);
  if ( !v3 )
  {
    v4 = (_QWORD *)(a1 + 40);
    v5 = (void (__fastcall ***)(void *, _QWORD))v4[32];
    (**v5)(v5, 0);
    if ( v5 != v4 )
      Platform::Details::Heap::Free(v5);
    v6 = *v2;
    Platform::Details::ControlBlock::ReleaseTarget(*v2);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 2, 0xFFFFFFFF) == 1 )
    {
      if ( *((_BYTE *)v6 + 25) )
        Platform::Details::Heap::AlignedFree(v6);
      else
        Platform::Details::Heap::Free(v6);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14000fba0  push    rbx
0x14000fba2  push    rsi
0x14000fba3  push    rdi
0x14000fba4  push    r14
0x14000fba6  sub     rsp, 28h
0x14000fbaa  mov     rbx, rcx
0x14000fbad  lea     r14, [rcx+18h]
0x14000fbb1  mov     rcx, r14
0x14000fbb4  call    ?Decrement@__abi_FTMWeakRefData@@QECAKXZ; __abi_FTMWeakRefData::Decrement(void)
0x14000fbb9  mov     edi, eax
0x14000fbbb  test    eax, eax
0x14000fbbd  jnz     short loc_14000FC19
0x14000fbbf  add     rbx, 28h ; '('
0x14000fbc3  mov     rsi, [rbx+100h]
0x14000fbca  mov     rdx, [rsi]
0x14000fbcd  mov     rax, [rdx]
0x14000fbd0  xor     edx, edx
0x14000fbd2  mov     rcx, rsi
0x14000fbd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fbda  cmp     rsi, rbx
0x14000fbdd  jz      short loc_14000FBE9
0x14000fbdf  mov     rcx, rsi
0x14000fbe2  call    cs:__imp_?Free@Heap@Details@Platform@@SAXPEAX@Z; Platform::Details::Heap::Free(void *)
0x14000fbe8  nop
0x14000fbe9  mov     rbx, [r14]
0x14000fbec  mov     rcx, rbx
0x14000fbef  call    cs:__imp_?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ; Platform::Details::ControlBlock::ReleaseTarget(void)
0x14000fbf5  or      eax, 0FFFFFFFFh
0x14000fbf8  lock xadd [rbx+8], eax
0x14000fbfd  cmp     eax, 1
0x14000fc00  jnz     short loc_14000FC19
0x14000fc02  mov     rcx, rbx
0x14000fc05  cmp     byte ptr [rbx+19h], 0
0x14000fc09  jz      short loc_14000FC13
0x14000fc0b  call    cs:__imp_?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z; Platform::Details::Heap::AlignedFree(void *)
0x14000fc11  jmp     short loc_14000FC19
0x14000fc13  call    cs:__imp_?Free@Heap@Details@Platform@@SAXPEAX@Z; Platform::Details::Heap::Free(void *)
0x14000fc19  mov     eax, edi
0x14000fc1b  add     rsp, 28h
0x14000fc1f  pop     r14
0x14000fc21  pop     rdi
0x14000fc22  pop     rsi
0x14000fc23  pop     rbx
0x14000fc24  retn
```
