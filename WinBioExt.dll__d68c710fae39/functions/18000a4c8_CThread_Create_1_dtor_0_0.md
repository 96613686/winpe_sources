# _CThread::Create_::_1_::dtor$0_0

- ea: `0x18000a4c8`
- end: `0x18000a4d4`
- name: `_CThread::Create_::_1_::dtor$0_0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800069b0`

## pseudocode

```c
__int64 __fastcall CThread::Create_::_1_::dtor_0_0(__int64 a1, __int64 a2)
{
  return std::function<long (thread_inside_functions &)>::~function<long (thread_inside_functions &)>(a2 + 48, a2);
}

```

## disassembly

```asm
0x18000a4c8  lea     rcx, [rdx+30h]
0x18000a4cf  jmp     ??1?$function@$$A6AJAEAVthread_inside_functions@@@Z@std@@QEAA@XZ; std::function<long (thread_inside_functions &)>::~function<long (thread_inside_functions &)>(void)
```
