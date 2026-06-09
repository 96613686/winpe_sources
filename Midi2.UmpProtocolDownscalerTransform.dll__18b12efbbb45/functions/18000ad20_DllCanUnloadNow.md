# DllCanUnloadNow

- ea: `0x18000ad20`
- end: `0x18000ad84`
- name: `DllCanUnloadNow`
- size: `100`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000abe4`
- `0x18000ad20`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000ad3a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000ad3a`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rbx
  struct Microsoft::WRL::Details::ModuleBase *v1; // rdx
  bool v2; // r9

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    `Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
    0,
    0);
  LODWORD(v0) = 1;
  byte_18001BA68 = 1;
  if ( Microsoft::WRL::Details::TerminateMap(
         (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
         v1,
         0,
         v2) )
  {
    return (*(__int64 (__fastcall **)(void *))(_AtlModule + 24LL))(&_AtlModule) != 0;
  }
  return v0;
}

```

## disassembly

```asm
0x18000ad20  push    rbx
0x18000ad22  sub     rsp, 20h
0x18000ad26  xor     r9d, r9d; Context
0x18000ad29  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@45@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000ad30  xor     r8d, r8d; Parameter
0x18000ad33  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000ad3a  call    cs:__imp_InitOnceExecuteOnce
0x18000ad40  mov     ebx, 1
0x18000ad45  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000ad4c  xor     r8d, r8d; unsigned __int16 *
0x18000ad4f  mov     cs:byte_18001BA68, bl
0x18000ad55  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18000ad5a  test    al, al
0x18000ad5c  jz      short loc_18000AD7C
0x18000ad5e  mov     rax, cs:?_AtlModule@@3VCMidi2UmpProtocolDownscalerTransformModule@@A; CMidi2UmpProtocolDownscalerTransformModule _AtlModule
0x18000ad65  lea     rcx, ?_AtlModule@@3VCMidi2UmpProtocolDownscalerTransformModule@@A; CMidi2UmpProtocolDownscalerTransformModule _AtlModule
0x18000ad6c  mov     rax, [rax+18h]
0x18000ad70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad75  xor     ebx, ebx
0x18000ad77  test    eax, eax
0x18000ad79  setnz   bl
0x18000ad7c  mov     eax, ebx
0x18000ad7e  add     rsp, 20h
0x18000ad82  pop     rbx
0x18000ad83  retn
```
