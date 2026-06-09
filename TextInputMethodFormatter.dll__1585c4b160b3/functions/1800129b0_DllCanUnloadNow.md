# DllCanUnloadNow

- ea: `0x1800129b0`
- end: `0x180012a04`
- name: `DllCanUnloadNow`
- size: `84`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001172c`
- `0x1800129b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800129c8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800129c8`
- `RPCRT4!NdrDllCanUnloadNow` at `0x1800129ef`
- `RPCRT4!NdrDllCanUnloadNow` at `0x1800129ef`

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
  byte_180082A48 = 1;
  if ( Microsoft::WRL::Details::TerminateMap(
         (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
         v0,
         0,
         v1) )
  {
    return (unsigned int)NdrDllCanUnloadNow(&gPFactory) >> 31;
  }
  else
  {
    return 1;
  }
}

```

## disassembly

```asm
0x1800129b0  sub     rsp, 28h
0x1800129b4  xor     r9d, r9d; Context
0x1800129b7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800129be  xor     r8d, r8d; Parameter
0x1800129c1  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800129c8  call    cs:__imp_InitOnceExecuteOnce
0x1800129ce  xor     r8d, r8d; unsigned __int16 *
0x1800129d1  mov     cs:byte_180082A48, 1
0x1800129d8  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x1800129df  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x1800129e4  test    al, al
0x1800129e6  jz      short loc_1800129FA
0x1800129e8  lea     rcx, gPFactory; pPSFactoryBuffer
0x1800129ef  call    cs:__imp_NdrDllCanUnloadNow
0x1800129f5  shr     eax, 1Fh
0x1800129f8  jmp     short loc_1800129FF
0x1800129fa  mov     eax, 1
0x1800129ff  add     rsp, 28h
0x180012a03  retn
```
