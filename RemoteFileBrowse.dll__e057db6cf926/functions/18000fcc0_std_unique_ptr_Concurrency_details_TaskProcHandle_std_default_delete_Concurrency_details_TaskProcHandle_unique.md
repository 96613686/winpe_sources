# std::unique_ptr<Concurrency::details::_TaskProcHandle,std::default_delete<Concurrency::details::_TaskProcHandle>>::~unique_ptr<Concurrency::details::_TaskProcHandle,std::default_delete<Concurrency::details::_TaskProcHandle>>(void)

- ea: `0x18000fcc0`
- end: `0x18000fce1`
- name: `??1?$unique_ptr@U_TaskProcHandle@details@Concurrency@@U?$default_delete@U_TaskProcHandle@details@Concurrency@@@std@@@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180018446`
- `0x1800184b1`

## callees

- `0x18000fcc0`
- `0x180019010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::unique_ptr<Concurrency::details::_TaskProcHandle>::~unique_ptr<Concurrency::details::_TaskProcHandle>(
        __int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (**v1)(v1, 1);
  return result;
}

```

## disassembly

```asm
0x18000fcc0  sub     rsp, 28h
0x18000fcc4  mov     rcx, [rcx]
0x18000fcc7  test    rcx, rcx
0x18000fcca  jz      short loc_18000FCDC
0x18000fccc  mov     rax, [rcx]
0x18000fccf  mov     edx, 1
0x18000fcd4  mov     rax, [rax]
0x18000fcd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcdc  add     rsp, 28h
0x18000fce0  retn
```
