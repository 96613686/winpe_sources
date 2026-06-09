# DllCanUnloadNow

- ea: `0x180006dc0`
- end: `0x180006e15`
- name: `DllCanUnloadNow`
- size: `85`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006ca4`
- `0x180006dc0`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180006e05`
- `RPCRT4!NdrDllCanUnloadNow` at `0x180006e05`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006dda`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006dda`

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
  byte_18001D5D8 = 1;
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
0x180006dc0  push    rbx
0x180006dc2  sub     rsp, 20h
0x180006dc6  xor     r9d, r9d; Context
0x180006dc9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180006dd0  xor     r8d, r8d; Parameter
0x180006dd3  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180006dda  call    cs:__imp_InitOnceExecuteOnce
0x180006de0  mov     ebx, 1
0x180006de5  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180006dec  xor     r8d, r8d; unsigned __int16 *
0x180006def  mov     cs:byte_18001D5D8, bl
0x180006df5  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x180006dfa  test    al, al
0x180006dfc  jz      short loc_180006E0D
0x180006dfe  lea     rcx, gPFactory; pPSFactoryBuffer
0x180006e05  call    cs:__imp_NdrDllCanUnloadNow
0x180006e0b  mov     ebx, eax
0x180006e0d  mov     eax, ebx
0x180006e0f  add     rsp, 20h
0x180006e13  pop     rbx
0x180006e14  retn
```
