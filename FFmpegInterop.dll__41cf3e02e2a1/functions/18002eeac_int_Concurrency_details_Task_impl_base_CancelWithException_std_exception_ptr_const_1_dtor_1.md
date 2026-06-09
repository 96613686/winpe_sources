# int `Concurrency::details::_Task_impl_base::_CancelWithException(std::exception_ptr const &)'::`1'::dtor$1

- ea: `0x18002eeac`
- end: `0x18002eeb8`
- name: `?dtor$1@?0??_CancelWithException@_Task_impl_base@details@Concurrency@@QEAA_NAEBVexception_ptr@std@@@Z@4HA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180002da4`

## pseudocode

```c
__int64 __fastcall `Concurrency::details::_Task_impl_base::_CancelWithException'::`1'::dtor$1(__int64 a1, __int64 a2)
{
  return sub_180002DA4(a2 + 56);
}

```

## disassembly

```asm
0x18002eeac  lea     rcx, [rdx+38h]
0x18002eeb3  jmp     sub_180002DA4
```
