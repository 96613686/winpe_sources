# DllCanUnloadNow

- ea: `0x18000b8e0`
- end: `0x18000b935`
- name: `DllCanUnloadNow`
- size: `85`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b7c4`
- `0x18000b8e0`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000b8eb`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000b8eb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000b90b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000b90b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT CanUnloadNow; // ecx
  struct Microsoft::WRL::Details::ModuleBase *v1; // rdx
  bool v2; // r9

  CanUnloadNow = NdrDllCanUnloadNow(&gPFactory);
  if ( !CanUnloadNow )
  {
    InitOnceExecuteOnce(
      &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
      _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_18005A058 = 1;
    return !Microsoft::WRL::Details::TerminateMap(
              (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
              v1,
              0,
              v2);
  }
  return CanUnloadNow;
}

```

## disassembly

```asm
0x18000b8e0  sub     rsp, 28h
0x18000b8e4  lea     rcx, gPFactory; pPSFactoryBuffer
0x18000b8eb  call    cs:__imp_NdrDllCanUnloadNow
0x18000b8f1  mov     ecx, eax
0x18000b8f3  test    eax, eax
0x18000b8f5  jnz     short loc_18000B92E
0x18000b8f7  xor     r9d, r9d; Context
0x18000b8fa  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000b901  xor     r8d, r8d; Parameter
0x18000b904  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000b90b  call    cs:__imp_InitOnceExecuteOnce
0x18000b911  xor     r8d, r8d; unsigned __int16 *
0x18000b914  mov     cs:byte_18005A058, 1
0x18000b91b  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000b922  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18000b927  xor     ecx, ecx
0x18000b929  test    al, al
0x18000b92b  setz    cl
0x18000b92e  mov     eax, ecx
0x18000b930  add     rsp, 28h
0x18000b934  retn
```
