# Concurrency::details::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___::[Platform::Object]::__abi_Release

- ea: `0x140021520`
- end: `0x140021592`
- name: `Concurrency::details::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___::[Platform::Object]::__abi_Release`
- size: `114`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1400215a0`
- `0x1400215b0`
- `0x1400215c0`
- `0x1400215d0`
- `0x1400215e0`
- `0x1400215f0`
- `0x140021600`
- `0x140021610`
- `0x140021630`

## callees

- `0x14000614c`
- `0x140015354`
- `0x140021520`

## import_xrefs

- `wincorlib!?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ` at `0x140021556`
- `wincorlib!?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ` at `0x140021556`
- `wincorlib!?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z` at `0x140021572`
- `wincorlib!?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z` at `0x140021572`
- `wincorlib!?Free@Heap@Details@Platform@@SAXPEAX@Z` at `0x14002157a`
- `wincorlib!?Free@Heap@Details@Platform@@SAXPEAX@Z` at `0x14002157a`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___::_Platform::Object_::__abi_Release(
        __int64 a1)
{
  Platform::Details::ControlBlock **v1; // rsi
  unsigned int v3; // edi
  Platform::Details::ControlBlock *v4; // rbx

  v1 = (Platform::Details::ControlBlock **)(a1 + 168);
  v3 = __abi_FTMWeakRefData::Decrement(a1 + 168);
  if ( !v3 )
  {
    Concurrency::details::_AsyncTaskThunkBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__void_::__AsyncTaskThunkBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__void_(a1 + 8);
    v4 = *v1;
    Platform::Details::ControlBlock::ReleaseTarget(*v1);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 2, 0xFFFFFFFF) == 1 )
    {
      if ( *((_BYTE *)v4 + 25) )
        Platform::Details::Heap::AlignedFree(v4);
      else
        Platform::Details::Heap::Free(v4);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140021520  mov     [rsp+arg_8], rbx
0x140021525  mov     [rsp+arg_10], rsi
0x14002152a  push    rdi
0x14002152b  sub     rsp, 20h
0x14002152f  lea     rsi, [rcx+0A8h]
0x140021536  mov     rbx, rcx
0x140021539  mov     rcx, rsi
0x14002153c  call    ?Decrement@__abi_FTMWeakRefData@@QECAKXZ; __abi_FTMWeakRefData::Decrement(void)
0x140021541  mov     edi, eax
0x140021543  test    eax, eax
0x140021545  jnz     short loc_140021580
0x140021547  lea     rcx, [rbx+8]
0x14002154b  call    Concurrency__details___AsyncTaskThunkBase_Concurrency__details___AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency__details___TaskTypeTraits_void_0__0_0__void_____AsyncTaskThunkBase_Concurrency__details___AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency__details___TaskTypeTraits_void_0__0_0__void_
0x140021550  mov     rbx, [rsi]
0x140021553  mov     rcx, rbx
0x140021556  call    cs:__imp_?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ; Platform::Details::ControlBlock::ReleaseTarget(void)
0x14002155c  or      edx, 0FFFFFFFFh
0x14002155f  lock xadd [rbx+8], edx
0x140021564  cmp     edx, 1
0x140021567  jnz     short loc_140021580
0x140021569  mov     rcx, rbx
0x14002156c  cmp     [rbx+19h], dil
0x140021570  jz      short loc_14002157A
0x140021572  call    cs:__imp_?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z; Platform::Details::Heap::AlignedFree(void *)
0x140021578  jmp     short loc_140021580
0x14002157a  call    cs:__imp_?Free@Heap@Details@Platform@@SAXPEAX@Z; Platform::Details::Heap::Free(void *)
0x140021580  mov     rbx, [rsp+28h+arg_8]
0x140021585  mov     eax, edi
0x140021587  mov     rsi, [rsp+28h+arg_10]
0x14002158c  add     rsp, 20h
0x140021590  pop     rdi
0x140021591  retn
```
