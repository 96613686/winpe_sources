# DllCanUnloadNow

- ea: `0x18000b340`
- end: `0x18000b37f`
- name: `DllCanUnloadNow`
- size: `63`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b204`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000b358`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000b358`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  struct Microsoft::WRL::Details::ModuleBase *v0; // rdx
  bool v1; // r9

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_18001B3B8 = 1;
  return !Microsoft::WRL::Details::TerminateMap(
            (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
            v0,
            0,
            v1);
}

```

## disassembly

```asm
0x18000b340  sub     rsp, 28h
0x18000b344  xor     r9d, r9d; Context
0x18000b347  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000b34e  xor     r8d, r8d; Parameter
0x18000b351  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000b358  call    cs:__imp_InitOnceExecuteOnce
0x18000b35e  xor     r8d, r8d; unsigned __int16 *
0x18000b361  mov     cs:byte_18001B3B8, 1
0x18000b368  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000b36f  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18000b374  movzx   eax, al
0x18000b377  xor     eax, 1
0x18000b37a  add     rsp, 28h
0x18000b37e  retn
```
