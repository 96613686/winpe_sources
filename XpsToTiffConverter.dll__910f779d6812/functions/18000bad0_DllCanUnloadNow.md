# DllCanUnloadNow

- ea: `0x18000bad0`
- end: `0x18000bb1a`
- name: `DllCanUnloadNow`
- size: `74`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000bae8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000bae8`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_180014938 = 1;
  return (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                           + 24LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_) != 0;
}

```

## disassembly

```asm
0x18000bad0  sub     rsp, 28h
0x18000bad4  xor     r9d, r9d; Context
0x18000bad7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000bade  xor     r8d, r8d; Parameter
0x18000bae1  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000bae8  call    cs:__imp_InitOnceExecuteOnce
0x18000baee  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000baf5  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000bafc  mov     cs:byte_180014938, 1
0x18000bb03  mov     rax, [rax+18h]
0x18000bb07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb0c  xor     ecx, ecx
0x18000bb0e  test    eax, eax
0x18000bb10  setnz   cl
0x18000bb13  mov     eax, ecx
0x18000bb15  add     rsp, 28h
0x18000bb19  retn
```
