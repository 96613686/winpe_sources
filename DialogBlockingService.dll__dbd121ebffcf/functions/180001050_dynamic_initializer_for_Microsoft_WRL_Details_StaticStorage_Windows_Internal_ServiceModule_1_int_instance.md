# _dynamic_initializer_for__Microsoft::WRL::Details::StaticStorage_Windows::Internal::ServiceModule_1_int_::instance___

- ea: `0x180001050`
- end: `0x18000105c`
- name: `_dynamic_initializer_for__Microsoft::WRL::Details::StaticStorage_Windows::Internal::ServiceModule_1_int_::instance___`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001a20`

## pseudocode

```c
int dynamic_initializer_for__Microsoft::WRL::Details::StaticStorage_Windows::Internal::ServiceModule_1_int_::instance___()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Windows::Internal::ServiceModule_1_int_::instance___);
}

```

## disassembly

```asm
0x180001050  lea     rcx, _dynamic_atexit_destructor_for__Microsoft__WRL__Details__StaticStorage_Windows__Internal__ServiceModule_1_int___instance___
0x180001057  jmp     atexit
```
