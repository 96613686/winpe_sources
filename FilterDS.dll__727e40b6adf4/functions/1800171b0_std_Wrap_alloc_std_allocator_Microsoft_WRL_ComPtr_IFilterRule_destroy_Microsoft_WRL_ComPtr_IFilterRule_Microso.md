# std::_Wrap_alloc<std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>>::destroy<Microsoft::WRL::ComPtr<IFilterRule>>(Microsoft::WRL::ComPtr<IFilterRule> *)

- ea: `0x1800171b0`
- end: `0x1800171d5`
- name: `??$destroy@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@?$_Wrap_alloc@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@std@@QEAAXPEAV?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@Z`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180023145`

## callees

- `0x1800171b0`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall std::_Wrap_alloc<std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>>::destroy<Microsoft::WRL::ComPtr<IFilterRule>>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x1800171b0  sub     rsp, 28h
0x1800171b4  mov     rcx, [rdx]
0x1800171b7  test    rcx, rcx
0x1800171ba  jz      short loc_1800171D0
0x1800171bc  mov     qword ptr [rdx], 0
0x1800171c3  mov     rax, [rcx]
0x1800171c6  mov     rax, [rax+10h]
0x1800171ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171cf  nop
0x1800171d0  add     rsp, 28h
0x1800171d4  retn
```
