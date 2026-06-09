# DllCanUnloadNow

- ea: `0x18000d6c0`
- end: `0x18000d70a`
- name: `DllCanUnloadNow`
- size: `74`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000d6d8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000d6d8`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_18002ED98 = 1;
  return (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                              + 24))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_) != 0;
}

```

## disassembly

```asm
0x18000d6c0  sub     rsp, 28h
0x18000d6c4  xor     r9d, r9d; Context
0x18000d6c7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000d6ce  xor     r8d, r8d; Parameter
0x18000d6d1  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000d6d8  call    cs:__imp_InitOnceExecuteOnce
0x18000d6de  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000d6e5  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000d6ec  mov     cs:byte_18002ED98, 1
0x18000d6f3  mov     rax, [rax+18h]
0x18000d6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6fc  xor     ecx, ecx
0x18000d6fe  test    eax, eax
0x18000d700  setnz   cl
0x18000d703  mov     eax, ecx
0x18000d705  add     rsp, 28h
0x18000d709  retn
```
