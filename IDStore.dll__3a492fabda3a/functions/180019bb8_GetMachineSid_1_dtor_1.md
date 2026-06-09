# _GetMachineSid_::_1_::dtor$1

- ea: `0x180019bb8`
- end: `0x180019bc4`
- name: `_GetMachineSid_::_1_::dtor$1`
- size: `12`
- prototype: `HLOCAL __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18001599c`

## pseudocode

```c
HLOCAL __fastcall GetMachineSid_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>((HLOCAL *)(a2 + 80));
}

```

## disassembly

```asm
0x180019bb8  lea     rcx, [rdx+50h]
0x180019bbf  jmp     ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
```
