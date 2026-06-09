# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)

- ea: `0x18000832c`
- end: `0x18000835d`
- name: `?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800031d0`
- `0x18000aff0`
- `0x18000b040`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008344`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008344`

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
  byte_180025800 = 1;
  return result;
}

```

## disassembly

```asm
0x18000832c  sub     rsp, 28h
0x180008330  xor     r9d, r9d; Context
0x180008333  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000833a  xor     r8d, r8d; Parameter
0x18000833d  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180008344  call    cs:__imp_InitOnceExecuteOnce
0x18000834a  lea     rax, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008351  mov     cs:byte_180025800, 1
0x180008358  add     rsp, 28h
0x18000835c  retn
```
