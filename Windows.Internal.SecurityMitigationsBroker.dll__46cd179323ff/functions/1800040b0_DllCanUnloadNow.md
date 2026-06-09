# DllCanUnloadNow

- ea: `0x1800040b0`
- end: `0x180004105`
- name: `DllCanUnloadNow`
- size: `85`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003f90`
- `0x1800040b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800040ca`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800040ca`
- `RPCRT4!NdrDllCanUnloadNow` at `0x1800040f5`
- `RPCRT4!NdrDllCanUnloadNow` at `0x1800040f5`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT v0; // ebx
  struct Microsoft::WRL::Details::ModuleBase *v1; // rdx
  bool v2; // r9

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  v0 = 1;
  byte_18000C8B8 = 1;
  if ( Microsoft::WRL::Details::TerminateMap(
         (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
         v1,
         0,
         v2) )
  {
    return NdrDllCanUnloadNow(&gPFactory);
  }
  return v0;
}

```

## disassembly

```asm
0x1800040b0  push    rbx
0x1800040b2  sub     rsp, 20h
0x1800040b6  xor     r9d, r9d; Context
0x1800040b9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800040c0  xor     r8d, r8d; Parameter
0x1800040c3  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800040ca  call    cs:__imp_InitOnceExecuteOnce
0x1800040d0  mov     ebx, 1
0x1800040d5  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x1800040dc  xor     r8d, r8d; unsigned __int16 *
0x1800040df  mov     cs:byte_18000C8B8, bl
0x1800040e5  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x1800040ea  test    al, al
0x1800040ec  jz      short loc_1800040FD
0x1800040ee  lea     rcx, gPFactory; pPSFactoryBuffer
0x1800040f5  call    cs:__imp_NdrDllCanUnloadNow
0x1800040fb  mov     ebx, eax
0x1800040fd  mov     eax, ebx
0x1800040ff  add     rsp, 20h
0x180004103  pop     rbx
0x180004104  retn
```
