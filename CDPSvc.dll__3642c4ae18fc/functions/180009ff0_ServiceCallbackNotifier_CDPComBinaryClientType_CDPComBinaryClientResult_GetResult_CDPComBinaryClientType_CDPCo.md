# ServiceCallbackNotifier<CDPComBinaryClientType,CDPComBinaryClientResult>::GetResult(CDPComBinaryClientType *,CDPComBinaryClientResult *,std::function<void (CDPComBinaryClientResult *,CDPComBinaryClientResult const &)>)

- ea: `0x180009ff0`
- end: `0x18000a19b`
- name: `?GetResult@?$ServiceCallbackNotifier@W4CDPComBinaryClientType@@UCDPComBinaryClientResult@@@@QEAAJPEAW4CDPComBinaryClientType@@PEAUCDPComBinaryClientResult@@V?$function@$$A6AXPEAUCDPComBinaryClientResult@@AEBU1@@Z@std@@@Z`
- size: `427`
- prototype: `__int64 __fastcall(_Mtx_t, _DWORD *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019520`

## callees

- `0x180009ff0`
- `0x18000cb8c`
- `0x18000cc2c`
- `0x18006a010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18000a101`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18000a101`
- `msvcp_win!_Mtx_unlock` at `0x18000a0a6`
- `msvcp_win!_Mtx_unlock` at `0x18000a161`
- `msvcp_win!_Mtx_unlock` at `0x18000a0a6`
- `msvcp_win!_Mtx_unlock` at `0x18000a161`

## string_xrefs

- `0x18000a034`: `onecoreuap\windows\cdp\service\shared\ServiceCallbackNotifier.h`

## pseudocode

```c

```
