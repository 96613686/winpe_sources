# _GetSecurityDescriptor_::_1_::dtor$1

- ea: `0x18000fb4e`
- end: `0x18000fb5a`
- name: `_GetSecurityDescriptor_::_1_::dtor$1`
- size: `12`
- prototype: `HLOCAL __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000cf80`

## pseudocode

```c
HLOCAL __fastcall GetSecurityDescriptor_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(a2 + 40);
}

```

## disassembly

```asm
0x18000fb4e  lea     rcx, [rdx+28h]
0x18000fb55  jmp     ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
```
