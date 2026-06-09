# DllCanUnloadNow

- ea: `0x180006020`
- end: `0x18000605f`
- name: `DllCanUnloadNow`
- size: `63`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005f00`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006038`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006038`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  struct Microsoft::WRL::Details::ModuleBase *v0; // rdx

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_18000B3D8 = 1;
  return !Microsoft::WRL::Details::TerminateMap(
            (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
            v0,
            0);
}

```

## disassembly

```asm
0x180006020  sub     rsp, 28h
0x180006024  xor     r9d, r9d; Context
0x180006027  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000602e  xor     r8d, r8d; Parameter
0x180006031  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180006038  call    cs:__imp_InitOnceExecuteOnce
0x18000603e  xor     r8d, r8d; unsigned __int16 *
0x180006041  mov     cs:byte_18000B3D8, 1
0x180006048  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000604f  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x180006054  movzx   eax, al
0x180006057  xor     eax, 1
0x18000605a  add     rsp, 28h
0x18000605e  retn
```
