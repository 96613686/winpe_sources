# _CThread::CThread_::_1_::dtor$4

- ea: `0x18000a481`
- end: `0x18000a48d`
- name: `_CThread::CThread_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800069b0`

## pseudocode

```c
__int64 __fastcall CThread::CThread_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::function<long (thread_inside_functions &)>::~function<long (thread_inside_functions &)>(
           *(_QWORD *)(a2 + 120),
           a2);
}

```

## disassembly

```asm
0x18000a481  mov     rcx, [rdx+78h]
0x18000a488  jmp     ??1?$function@$$A6AJAEAVthread_inside_functions@@@Z@std@@QEAA@XZ; std::function<long (thread_inside_functions &)>::~function<long (thread_inside_functions &)>(void)
```
