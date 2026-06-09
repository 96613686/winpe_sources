# _CommandParamReceiver::CreateInstance_::_1_::dtor$2

- ea: `0x140011dae`
- end: `0x140011dba`
- name: `_CommandParamReceiver::CreateInstance_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400084fc`

## pseudocode

```c
HLOCAL __fastcall CommandParamReceiver::CreateInstance_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>((HLOCAL *)(a2 + 128));
}

```

## disassembly

```asm
0x140011dae  lea     rcx, [rdx+80h]
0x140011db5  jmp     ??1?$unique_ptr@XU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
```
