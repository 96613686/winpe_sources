# DllCanUnloadNow

- ea: `0x180009c60`
- end: `0x180009cc4`
- name: `DllCanUnloadNow`
- size: `100`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009b24`
- `0x180009c60`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180009c7a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180009c7a`

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
  byte_180015628 = 1;
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
0x180009c60  push    rbx
0x180009c62  sub     rsp, 20h
0x180009c66  xor     r9d, r9d; Context
0x180009c69  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@45@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180009c70  xor     r8d, r8d; Parameter
0x180009c73  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180009c7a  call    cs:__imp_InitOnceExecuteOnce
0x180009c80  mov     ebx, 1
0x180009c85  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180009c8c  xor     r8d, r8d; unsigned __int16 *
0x180009c8f  mov     cs:byte_180015628, bl
0x180009c95  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x180009c9a  test    al, al
0x180009c9c  jz      short loc_180009CBC
0x180009c9e  mov     rax, cs:?_AtlModule@@3VCMidi2SchedulerTransformModule@@A; CMidi2SchedulerTransformModule _AtlModule
0x180009ca5  lea     rcx, ?_AtlModule@@3VCMidi2SchedulerTransformModule@@A; CMidi2SchedulerTransformModule _AtlModule
0x180009cac  mov     rax, [rax+18h]
0x180009cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cb5  xor     ebx, ebx
0x180009cb7  test    eax, eax
0x180009cb9  setnz   bl
0x180009cbc  mov     eax, ebx
0x180009cbe  add     rsp, 20h
0x180009cc2  pop     rbx
0x180009cc3  retn
```
