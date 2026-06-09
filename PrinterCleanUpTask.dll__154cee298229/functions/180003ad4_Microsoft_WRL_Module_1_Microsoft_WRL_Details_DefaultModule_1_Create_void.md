# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)

- ea: `0x180003ad4`
- end: `0x180003b05`
- name: `?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ`
- size: `49`
- prototype: `__int64 *()`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001a40`
- `0x180005820`
- `0x180005860`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180003aec`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180003aec`

## pseudocode

```c
__int64 *Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create()
{
  __int64 *result; // rax

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  result = &Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_;
  byte_180022920 = 1;
  return result;
}

```

## disassembly

```asm
0x180003ad4  sub     rsp, 28h
0x180003ad8  xor     r9d, r9d; Context
0x180003adb  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180003ae2  xor     r8d, r8d; Parameter
0x180003ae5  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180003aec  call    cs:__imp_InitOnceExecuteOnce
0x180003af2  lea     rax, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180003af9  mov     cs:byte_180022920, 1
0x180003b00  add     rsp, 28h
0x180003b04  retn
```
