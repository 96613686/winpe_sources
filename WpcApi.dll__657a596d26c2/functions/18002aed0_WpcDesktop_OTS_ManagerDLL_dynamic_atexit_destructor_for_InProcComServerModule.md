# WpcDesktop::OTS::ManagerDLL::_dynamic_atexit_destructor_for__InProcComServerModule__

- ea: `0x18002aed0`
- end: `0x18002af1c`
- name: `WpcDesktop::OTS::ManagerDLL::_dynamic_atexit_destructor_for__InProcComServerModule__`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009eb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002aee9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002aee9`

## pseudocode

```c
bool WpcDesktop::OTS::ManagerDLL::_dynamic_atexit_destructor_for__InProcComServerModule__()
{
  const unsigned __int16 *v0; // r8
  struct Microsoft::WRL::Details::ModuleBase *v1; // rdx
  bool v2; // r9
  bool result; // al

  WpcDesktop::OTS::ManagerDLL::InProcComServerModule = &WpcBase::WrlModule::`vftable';
  DeleteCriticalSection(&CriticalSection);
  LOBYTE(v0) = 1;
  WpcDesktop::OTS::ManagerDLL::InProcComServerModule = &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::`vftable';
  result = Microsoft::WRL::Details::TerminateMap(
             (Microsoft::WRL::Details *)&WpcDesktop::OTS::ManagerDLL::InProcComServerModule,
             v1,
             v0,
             v2);
  Microsoft::WRL::Details::ModuleBase::module_ = 0;
  return result;
}

```

## disassembly

```asm
0x18002aed0  sub     rsp, 28h
0x18002aed4  lea     rax, ??_7WrlModule@WpcBase@@6B@; const WpcBase::WrlModule::`vftable'
0x18002aedb  lea     rcx, CriticalSection; lpCriticalSection
0x18002aee2  mov     cs:?InProcComServerModule@ManagerDLL@OTS@WpcDesktop@@3VWrlModule@WpcBase@@A, rax; WpcBase::WrlModule WpcDesktop::OTS::ManagerDLL::InProcComServerModule
0x18002aee9  call    cs:__imp_DeleteCriticalSection
0x18002aeef  lea     rax, ??_7?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@6B@; const Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::`vftable'
0x18002aef6  mov     r8b, 1; unsigned __int16 *
0x18002aef9  lea     rcx, ?InProcComServerModule@ManagerDLL@OTS@WpcDesktop@@3VWrlModule@WpcBase@@A; this
0x18002af00  mov     cs:?InProcComServerModule@ManagerDLL@OTS@WpcDesktop@@3VWrlModule@WpcBase@@A, rax; WpcBase::WrlModule WpcDesktop::OTS::ManagerDLL::InProcComServerModule
0x18002af07  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18002af0c  mov     cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA, 0; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18002af17  add     rsp, 28h
0x18002af1b  retn
```
