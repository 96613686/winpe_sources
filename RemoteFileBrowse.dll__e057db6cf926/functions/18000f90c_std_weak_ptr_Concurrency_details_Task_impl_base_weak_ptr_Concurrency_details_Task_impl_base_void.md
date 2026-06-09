# std::weak_ptr<Concurrency::details::_Task_impl_base>::~weak_ptr<Concurrency::details::_Task_impl_base>(void)

- ea: `0x18000f90c`
- end: `0x18000f937`
- name: `??1?$weak_ptr@U_Task_impl_base@details@Concurrency@@@std@@QEAA@XZ`
- size: `43`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180018410`
- `0x180018422`

## callees

- `0x18000f90c`
- `0x180019010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::weak_ptr<Concurrency::details::_Task_impl_base>::~weak_ptr<Concurrency::details::_Task_impl_base>(
        __int64 a1)
{
  volatile signed __int32 *v1; // rcx
  __int64 result; // rax

  v1 = *(volatile signed __int32 **)(a1 + 8);
  if ( v1 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v1 + 3, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
      return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 8LL))(v1);
  }
  return result;
}

```

## disassembly

```asm
0x18000f90c  sub     rsp, 28h
0x18000f910  mov     rcx, [rcx+8]
0x18000f914  test    rcx, rcx
0x18000f917  jz      short loc_18000F932
0x18000f919  or      eax, 0FFFFFFFFh
0x18000f91c  lock xadd [rcx+0Ch], eax
0x18000f921  cmp     eax, 1
0x18000f924  jnz     short loc_18000F932
0x18000f926  mov     rax, [rcx]
0x18000f929  mov     rax, [rax+8]
0x18000f92d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f932  add     rsp, 28h
0x18000f936  retn
```
