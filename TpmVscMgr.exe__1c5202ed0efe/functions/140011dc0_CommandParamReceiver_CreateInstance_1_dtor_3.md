# _CommandParamReceiver::CreateInstance_::_1_::dtor$3

- ea: `0x140011dc0`
- end: `0x140011dcc`
- name: `_CommandParamReceiver::CreateInstance_::_1_::dtor$3`
- size: `12`
- prototype: `HLOCAL __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400083fc`

## pseudocode

```c
HLOCAL __fastcall CommandParamReceiver::CreateInstance_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(a2 + 168);
}

```

## disassembly

```asm
0x140011dc0  lea     rcx, [rdx+0A8h]
0x140011dc7  jmp     ??1?$out_param_t@V?$unique_ptr@XU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
```
