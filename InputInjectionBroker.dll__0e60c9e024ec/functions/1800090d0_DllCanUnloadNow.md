# DllCanUnloadNow

- ea: `0x1800090d0`
- end: `0x180009125`
- name: `DllCanUnloadNow`
- size: `85`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008fb8`
- `0x1800090d0`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180009115`
- `RPCRT4!NdrDllCanUnloadNow` at `0x180009115`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800090ea`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800090ea`

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
  byte_180022C18 = 1;
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
0x1800090d0  push    rbx
0x1800090d2  sub     rsp, 20h
0x1800090d6  xor     r9d, r9d; Context
0x1800090d9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800090e0  xor     r8d, r8d; Parameter
0x1800090e3  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800090ea  call    cs:__imp_InitOnceExecuteOnce
0x1800090f0  mov     ebx, 1
0x1800090f5  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x1800090fc  xor     r8d, r8d; unsigned __int16 *
0x1800090ff  mov     cs:byte_180022C18, bl
0x180009105  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18000910a  test    al, al
0x18000910c  jz      short loc_18000911D
0x18000910e  lea     rcx, gPFactory; pPSFactoryBuffer
0x180009115  call    cs:__imp_NdrDllCanUnloadNow
0x18000911b  mov     ebx, eax
0x18000911d  mov     eax, ebx
0x18000911f  add     rsp, 20h
0x180009123  pop     rbx
0x180009124  retn
```
