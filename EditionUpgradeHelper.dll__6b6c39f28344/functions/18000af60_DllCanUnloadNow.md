# DllCanUnloadNow

- ea: `0x18000af60`
- end: `0x18000afab`
- name: `DllCanUnloadNow`
- size: `75`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009978`
- `0x18000ad34`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000af7a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000af7a`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  struct Microsoft::WRL::Details::ModuleBase *v0; // rdx
  bool v1; // r9
  BOOL v2; // ebx

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_18002F938 = 1;
  v2 = !Microsoft::WRL::Details::TerminateMap(
          (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
          v0,
          0,
          v1);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v2);
  return v2;
}

```

## disassembly

```asm
0x18000af60  push    rbx
0x18000af62  sub     rsp, 20h
0x18000af66  xor     r9d, r9d; Context
0x18000af69  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000af70  xor     r8d, r8d; Parameter
0x18000af73  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000af7a  call    cs:__imp_InitOnceExecuteOnce
0x18000af80  mov     cs:byte_18002F938, 1
0x18000af87  xor     r8d, r8d; unsigned __int16 *
0x18000af8a  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000af91  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18000af96  movzx   ebx, al
0x18000af99  xor     ebx, 1
0x18000af9c  mov     ecx, ebx
0x18000af9e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000afa3  mov     eax, ebx
0x18000afa5  add     rsp, 20h
0x18000afa9  pop     rbx
0x18000afaa  retn
```
