# Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::[Platform::Object]::__abi_Release

- ea: `0x140021360`
- end: `0x14002140f`
- name: `Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::[Platform::Object]::__abi_Release`
- size: `175`
- prototype: ``
- caller_count: `12`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140021420`
- `0x140021430`
- `0x140021440`
- `0x140021450`
- `0x140021460`
- `0x140021470`
- `0x140021480`
- `0x140021490`
- `0x1400214a0`
- `0x1400214c0`
- `0x1400214e0`
- `0x140021500`

## callees

- `0x1400039b6`
- `0x14000614c`
- `0x140015354`
- `0x140021360`
- `0x140035010`

## import_xrefs

- `wincorlib!?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ` at `0x1400213d3`
- `wincorlib!?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ` at `0x1400213d3`
- `wincorlib!?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z` at `0x1400213ef`
- `wincorlib!?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z` at `0x1400213ef`
- `wincorlib!?Free@Heap@Details@Platform@@SAXPEAX@Z` at `0x1400213f7`
- `wincorlib!?Free@Heap@Details@Platform@@SAXPEAX@Z` at `0x1400213f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::_Platform::Object_::__abi_Release(
        __int64 a1)
{
  Platform::Details::ControlBlock **v2; // rsi
  unsigned int v3; // edi
  __int64 v4; // rcx
  __int64 v5; // rcx
  Platform::Details::ControlBlock *v6; // rbx

  v2 = (Platform::Details::ControlBlock **)(a1 + 176);
  v3 = __abi_FTMWeakRefData::Decrement(a1 + 176);
  if ( !v3 )
  {
    v4 = *(_QWORD *)(a1 + 232);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    v5 = *(_QWORD *)(a1 + 224);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    WindowsDeleteString_0(*(HSTRING *)(a1 + 216));
    Concurrency::details::_AsyncTaskThunkBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__void_::__AsyncTaskThunkBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__void_(a1 + 16);
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
0x140021360  mov     [rsp+arg_8], rbx
0x140021365  mov     [rsp+arg_10], rsi
0x14002136a  push    rdi
0x14002136b  sub     rsp, 20h
0x14002136f  mov     rbx, rcx
0x140021372  lea     rsi, [rcx+0B0h]
0x140021379  mov     rcx, rsi
0x14002137c  call    ?Decrement@__abi_FTMWeakRefData@@QECAKXZ; __abi_FTMWeakRefData::Decrement(void)
0x140021381  mov     edi, eax
0x140021383  test    eax, eax
0x140021385  jnz     short loc_1400213FD
0x140021387  mov     rcx, [rbx+0E8h]
0x14002138e  test    rcx, rcx
0x140021391  jz      short loc_14002139F
0x140021393  mov     rdx, [rcx]
0x140021396  mov     rax, [rdx+10h]
0x14002139a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002139f  mov     rcx, [rbx+0E0h]
0x1400213a6  test    rcx, rcx
0x1400213a9  jz      short loc_1400213B7
0x1400213ab  mov     rax, [rcx]
0x1400213ae  mov     rax, [rax+10h]
0x1400213b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400213b7  mov     rcx, [rbx+0D8h]; string
0x1400213be  call    WindowsDeleteString_0
0x1400213c3  nop
0x1400213c4  lea     rcx, [rbx+10h]
0x1400213c8  call    Concurrency__details___AsyncTaskThunkBase_Concurrency__details___AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency__details___TaskTypeTraits_void_0__0_0__void_____AsyncTaskThunkBase_Concurrency__details___AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency__details___TaskTypeTraits_void_0__0_0__void_
0x1400213cd  mov     rbx, [rsi]
0x1400213d0  mov     rcx, rbx
0x1400213d3  call    cs:__imp_?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ; Platform::Details::ControlBlock::ReleaseTarget(void)
0x1400213d9  or      eax, 0FFFFFFFFh
0x1400213dc  lock xadd [rbx+8], eax
0x1400213e1  cmp     eax, 1
0x1400213e4  jnz     short loc_1400213FD
0x1400213e6  mov     rcx, rbx
0x1400213e9  cmp     byte ptr [rbx+19h], 0
0x1400213ed  jz      short loc_1400213F7
0x1400213ef  call    cs:__imp_?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z; Platform::Details::Heap::AlignedFree(void *)
0x1400213f5  jmp     short loc_1400213FD
0x1400213f7  call    cs:__imp_?Free@Heap@Details@Platform@@SAXPEAX@Z; Platform::Details::Heap::Free(void *)
0x1400213fd  mov     eax, edi
0x1400213ff  mov     rbx, [rsp+28h+arg_8]
0x140021404  mov     rsi, [rsp+28h+arg_10]
0x140021409  add     rsp, 20h
0x14002140d  pop     rdi
0x14002140e  retn
```
