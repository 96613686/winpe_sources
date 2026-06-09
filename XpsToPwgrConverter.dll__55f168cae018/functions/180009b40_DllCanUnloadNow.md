# DllCanUnloadNow

- ea: `0x180009b40`
- end: `0x180009b8a`
- name: `DllCanUnloadNow`
- size: `74`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180009b58`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180009b58`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_180017718 = 1;
  return (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                           + 24LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_) != 0;
}

```

## disassembly

```asm
0x180009b40  sub     rsp, 28h
0x180009b44  xor     r9d, r9d; Context
0x180009b47  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180009b4e  xor     r8d, r8d; Parameter
0x180009b51  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180009b58  call    cs:__imp_InitOnceExecuteOnce
0x180009b5e  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180009b65  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180009b6c  mov     cs:byte_180017718, 1
0x180009b73  mov     rax, [rax+18h]
0x180009b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b7c  xor     ecx, ecx
0x180009b7e  test    eax, eax
0x180009b80  setnz   cl
0x180009b83  mov     eax, ecx
0x180009b85  add     rsp, 28h
0x180009b89  retn
```
