# DllCanUnloadNow

- ea: `0x1800073a0`
- end: `0x1800073df`
- name: `DllCanUnloadNow`
- size: `63`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006c58`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800073b8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800073b8`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  struct Microsoft::WRL::Details::ModuleBase *v0; // rdx
  bool v1; // r9

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    `Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_1800144E8 = 1;
  return !Microsoft::WRL::Details::TerminateMap(
            (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
            v0,
            0,
            v1);
}

```

## disassembly

```asm
0x1800073a0  sub     rsp, 28h
0x1800073a4  xor     r9d, r9d; Context
0x1800073a7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@45@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800073ae  xor     r8d, r8d; Parameter
0x1800073b1  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800073b8  call    cs:__imp_InitOnceExecuteOnce
0x1800073be  xor     r8d, r8d; unsigned __int16 *
0x1800073c1  mov     cs:byte_1800144E8, 1
0x1800073c8  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x1800073cf  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x1800073d4  movzx   eax, al
0x1800073d7  xor     eax, 1
0x1800073da  add     rsp, 28h
0x1800073de  retn
```
