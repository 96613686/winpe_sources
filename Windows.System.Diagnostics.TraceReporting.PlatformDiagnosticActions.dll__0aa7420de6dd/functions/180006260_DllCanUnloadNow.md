# DllCanUnloadNow

- ea: `0x180006260`
- end: `0x1800062b5`
- name: `DllCanUnloadNow`
- size: `85`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006144`
- `0x180006260`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x1800062a5`
- `RPCRT4!NdrDllCanUnloadNow` at `0x1800062a5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000627a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000627a`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT v0; // ebx
  struct Microsoft::WRL::Details::ModuleBase *v1; // rdx

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  v0 = 1;
  byte_180015488 = 1;
  if ( Microsoft::WRL::Details::TerminateMap(
         (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
         v1,
         0) )
  {
    return NdrDllCanUnloadNow(&gPFactory);
  }
  return v0;
}

```

## disassembly

```asm
0x180006260  push    rbx
0x180006262  sub     rsp, 20h
0x180006266  xor     r9d, r9d; Context
0x180006269  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180006270  xor     r8d, r8d; Parameter
0x180006273  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000627a  call    cs:__imp_InitOnceExecuteOnce
0x180006280  mov     ebx, 1
0x180006285  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000628c  xor     r8d, r8d; unsigned __int16 *
0x18000628f  mov     cs:byte_180015488, bl
0x180006295  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18000629a  test    al, al
0x18000629c  jz      short loc_1800062AD
0x18000629e  lea     rcx, gPFactory; pPSFactoryBuffer
0x1800062a5  call    cs:__imp_NdrDllCanUnloadNow
0x1800062ab  mov     ebx, eax
0x1800062ad  mov     eax, ebx
0x1800062af  add     rsp, 20h
0x1800062b3  pop     rbx
0x1800062b4  retn
```
