# WpW32TimeEnableServiceLogging$dtor$0

- ea: `0x18001167c`
- end: `0x180011688`
- name: `WpW32TimeEnableServiceLogging$dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000fbe8`

## pseudocode

```c
void __fastcall WpW32TimeEnableServiceLogging_dtor_0(__int64 a1, __int64 a2)
{
  wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>((void **)(a2 + 32));
}

```

## disassembly

```asm
0x18001167c  lea     rcx, [rdx+20h]
0x180011683  jmp     ??1?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)
```
