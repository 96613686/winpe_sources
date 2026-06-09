# DllCanUnloadNow

- ea: `0x180002810`
- end: `0x180002862`
- name: `DllCanUnloadNow`
- size: `82`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026b4`
- `0x180002810`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180002839`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180002839`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000281b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000281b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
  {
    InitOnceExecuteOnce(
      &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
      _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_18001A518 = 1;
    return !Microsoft::WRL::Details::TerminateMap(
              (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
              0,
              0);
  }
  return result;
}

```

## disassembly

```asm
0x180002810  sub     rsp, 28h
0x180002814  lea     rcx, gPFactory; pPSFactoryBuffer
0x18000281b  call    cs:__imp_NdrDllCanUnloadNow
0x180002821  test    eax, eax
0x180002823  jnz     short loc_18000285D
0x180002825  xor     r9d, r9d; Context
0x180002828  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000282f  xor     r8d, r8d; Parameter
0x180002832  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180002839  call    cs:__imp_InitOnceExecuteOnce
0x18000283f  xor     r8d, r8d; unsigned __int16 *
0x180002842  mov     cs:byte_18001A518, 1
0x180002849  xor     edx, edx; struct Microsoft::WRL::Details::ModuleBase *
0x18000284b  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180002852  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x180002857  movzx   eax, al
0x18000285a  xor     eax, 1
0x18000285d  add     rsp, 28h
0x180002861  retn
```
