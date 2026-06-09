# DllCanUnloadNow

- ea: `0x18000bb80`
- end: `0x18000bbe4`
- name: `DllCanUnloadNow`
- size: `100`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ba44`
- `0x18000bb80`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000bb9a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000bb9a`

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
  byte_18002DCB8 = 1;
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
0x18000bb80  push    rbx
0x18000bb82  sub     rsp, 20h
0x18000bb86  xor     r9d, r9d; Context
0x18000bb89  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@45@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000bb90  xor     r8d, r8d; Parameter
0x18000bb93  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000bb9a  call    cs:__imp_InitOnceExecuteOnce
0x18000bba0  mov     ebx, 1
0x18000bba5  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000bbac  xor     r8d, r8d; unsigned __int16 *
0x18000bbaf  mov     cs:byte_18002DCB8, bl
0x18000bbb5  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18000bbba  test    al, al
0x18000bbbc  jz      short loc_18000BBDC
0x18000bbbe  mov     rax, cs:?_AtlModule@@3VCMidi2VirtualMidiTransportModule@@A; CMidi2VirtualMidiTransportModule _AtlModule
0x18000bbc5  lea     rcx, ?_AtlModule@@3VCMidi2VirtualMidiTransportModule@@A; CMidi2VirtualMidiTransportModule _AtlModule
0x18000bbcc  mov     rax, [rax+18h]
0x18000bbd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbd5  xor     ebx, ebx
0x18000bbd7  test    eax, eax
0x18000bbd9  setnz   bl
0x18000bbdc  mov     eax, ebx
0x18000bbde  add     rsp, 20h
0x18000bbe2  pop     rbx
0x18000bbe3  retn
```
