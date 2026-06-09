# _dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Windows::Internal::ServiceModule_1_int_::instance___

- ea: `0x18000cfa0`
- end: `0x18000cfd1`
- name: `_dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Windows::Internal::ServiceModule_1_int_::instance___`
- size: `49`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000cfa0`
- `0x18000e010`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Windows::Internal::ServiceModule_1_int_::instance___()
{
  __int64 result; // rax

  if ( byte_180014568 )
  {
    result = (*(__int64 (__fastcall **)(__int64 *, _QWORD))qword_180014558)(&qword_180014558, 0);
    byte_180014568 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000cfa0  sub     rsp, 28h
0x18000cfa4  cmp     cs:byte_180014568, 0
0x18000cfab  jz      short loc_18000CFCC
0x18000cfad  mov     rax, cs:qword_180014558
0x18000cfb4  lea     rcx, qword_180014558
0x18000cfbb  xor     edx, edx
0x18000cfbd  mov     rax, [rax]
0x18000cfc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfc5  mov     cs:byte_180014568, 0
0x18000cfcc  add     rsp, 28h
0x18000cfd0  retn
```
