# _CThread::CThread_::_1_::dtor$0

- ea: `0x18000a42d`
- end: `0x18000a43d`
- name: `_CThread::CThread_::_1_::dtor$0`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800069b0`

## pseudocode

```c
__int64 __fastcall CThread::CThread_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::function<long (thread_inside_functions &)>::~function<long (thread_inside_functions &)>(
           *(_QWORD *)(a2 + 112) + 24LL,
           a2);
}

```

## disassembly

```asm
0x18000a42d  mov     rcx, [rdx+70h]
0x18000a434  add     rcx, 18h
0x18000a438  jmp     ??1?$function@$$A6AJAEAVthread_inside_functions@@@Z@std@@QEAA@XZ; std::function<long (thread_inside_functions &)>::~function<long (thread_inside_functions &)>(void)
```
