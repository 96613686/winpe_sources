# DllCanUnloadNow

- ea: `0x180009ab0`
- end: `0x180009b14`
- name: `DllCanUnloadNow`
- size: `100`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009974`
- `0x180009ab0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180009aca`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180009aca`

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
  byte_180012628 = 1;
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
0x180009ab0  push    rbx
0x180009ab2  sub     rsp, 20h
0x180009ab6  xor     r9d, r9d; Context
0x180009ab9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@45@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180009ac0  xor     r8d, r8d; Parameter
0x180009ac3  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180009aca  call    cs:__imp_InitOnceExecuteOnce
0x180009ad0  mov     ebx, 1
0x180009ad5  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180009adc  xor     r8d, r8d; unsigned __int16 *
0x180009adf  mov     cs:byte_180012628, bl
0x180009ae5  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x180009aea  test    al, al
0x180009aec  jz      short loc_180009B0C
0x180009aee  mov     rax, cs:?_AtlModule@@3VCMidi2BS2UMPTransformModule@@A; CMidi2BS2UMPTransformModule _AtlModule
0x180009af5  lea     rcx, ?_AtlModule@@3VCMidi2BS2UMPTransformModule@@A; CMidi2BS2UMPTransformModule _AtlModule
0x180009afc  mov     rax, [rax+18h]
0x180009b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b05  xor     ebx, ebx
0x180009b07  test    eax, eax
0x180009b09  setnz   bl
0x180009b0c  mov     eax, ebx
0x180009b0e  add     rsp, 20h
0x180009b12  pop     rbx
0x180009b13  retn
```
