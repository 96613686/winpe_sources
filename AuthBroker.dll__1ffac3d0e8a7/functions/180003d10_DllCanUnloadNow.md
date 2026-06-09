# DllCanUnloadNow

- ea: `0x180003d10`
- end: `0x180003d69`
- name: `DllCanUnloadNow`
- size: `89`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003d10`
- `0x180021010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180003d61`
- `RPCRT4!NdrDllCanUnloadNow` at `0x180003d61`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180003d28`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180003d28`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_.initialized_ = 1;
  if ( (*(unsigned int (__fastcall **)(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> *))(*(_QWORD *)Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_.data_ + 24LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_) )
    return 1;
  else
    return NdrDllCanUnloadNow(&gPFactory);
}

```

## disassembly

```asm
0x180003d10  sub     rsp, 28h
0x180003d14  xor     r9d, r9d; Context
0x180003d17  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180003d1e  xor     r8d, r8d; Parameter
0x180003d21  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180003d28  call    cs:__imp_InitOnceExecuteOnce
0x180003d2e  mov     rax, qword ptr cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A.data_; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_ ...
0x180003d35  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180003d3c  mov     cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A.initialized_, 1; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_ ...
0x180003d43  mov     rax, [rax+18h]
0x180003d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d4c  test    eax, eax
0x180003d4e  jz      short loc_180003D5A
0x180003d50  mov     eax, 1
0x180003d55  add     rsp, 28h
0x180003d59  retn
0x180003d5a  lea     rcx, gPFactory; pPSFactoryBuffer
0x180003d61  call    cs:__imp_NdrDllCanUnloadNow
0x180003d67  jmp     short loc_180003D55
```
