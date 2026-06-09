# CAvEndpointBuilder::ProcessPnpInterface(IPnpInterface *)

- ea: `0x18002d094`
- end: `0x18002e13c`
- name: `?ProcessPnpInterface@CAvEndpointBuilder@@AEAAJPEAUIPnpInterface@@@Z`
- size: `4264`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, __int64 (__fastcall ***)(struct IPnpInterface *, GUID *, __int64 *))`
- caller_count: `3`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000802c`
- `0x18002e43c`
- `0x180050858`

## callees

- `0x1800035d0`
- `0x180006b0c`
- `0x18000796c`
- `0x180008428`
- `0x18000899c`
- `0x18000fb60`
- `0x180010da8`
- `0x18001ef04`
- `0x18001f374`
- `0x180020c30`
- `0x180021030`
- `0x180024ca0`
- `0x180024d54`
- `0x180029024`
- `0x18002d094`
- `0x180033444`
- `0x180034c5c`
- `0x18003767c`
- `0x18003b078`
- `0x18003e920`
- `0x18003f7a4`
- `0x180054ecc`
- `0x180054f90`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d270`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d7fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d965`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002db19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002df21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e004`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d270`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d7fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d965`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002db19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002df21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e004`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d1c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d1c9`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002d1dd`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18002d1dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d28c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d297`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d2a2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d2ae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d2bc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d2c7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d2d2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d2dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d2e9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d2f5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d300`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d30b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d316`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d321`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d32f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d819`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d824`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d82f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d83b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d849`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d854`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d85f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d86a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d876`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d882`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d88d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d898`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d8a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d8ae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d8bc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d981`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d98c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d997`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d9a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d9b1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d9bc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d9c7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d9d2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d9de`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d9ea`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d9f5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002da00`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002da0b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002da16`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002da24`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db2f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db3a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db45`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db51`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db5f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db6a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db75`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db80`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db8c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db98`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dba3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dbae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dbb9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dbc4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dbd2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df37`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df42`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df4d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df59`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df67`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df72`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df7d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df88`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df94`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dfa0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dfab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dfb6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dfc1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dfcc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dfda`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e01a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e025`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e030`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e03c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e04a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e055`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e060`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e06b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e077`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e083`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e08e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e099`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e0a4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e0af`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e0bd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d28c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d297`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d2a2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d2ae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d2bc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d2c7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d2d2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d2dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d2e9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d2f5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d300`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d30b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d316`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d321`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d32f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d819`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d824`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d82f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d83b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d849`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d854`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d85f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d86a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d876`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d882`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d88d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d898`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d8a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d8ae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d8bc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d981`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d98c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d997`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d9a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d9b1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d9bc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d9c7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d9d2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d9de`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d9ea`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d9f5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002da00`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002da0b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002da16`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002da24`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db2f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db3a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db45`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db51`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db5f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db6a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db75`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db80`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db8c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002db98`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dba3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dbae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dbb9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dbc4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dbd2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df37`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df42`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df4d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df59`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df67`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df72`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df7d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df88`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002df94`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dfa0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dfab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dfb6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dfc1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dfcc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dfda`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e01a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e025`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e030`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e03c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e04a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e055`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e060`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e06b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e077`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e083`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e08e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e099`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e0a4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e0af`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e0bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d281`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d344`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d80e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d8cd`

## string_xrefs

- `0x18002d1ee`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002d25b`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002d7e1`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002d94b`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002dafa`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CAvEndpointBuilder::ProcessPnpInterface(
        LPCRITICAL_SECTION lpCriticalSection,
        __int64 (__fastcall ***a2)(struct IPnpInterface *, GUID *, __int64 *))
{
  const char *v4; // r9
  unsigned int LastError; // ebx
  __int64 (__fastcall *v6)(struct IPnpInterface *, GUID *, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rdx
  __int64 (__fastcall *v9)(__int64, __int64, struct IPropertyStore **); // rdi
  __int64 v10; // rdx
  __int64 (__fastcall *v11)(struct IPnpInterface *, __int64 *); // rbx
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, unsigned __int16 **); // rbx
  const struct _tlgProvider_t *v15; // rax
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, __int64, struct IPropertyStore **); // rdi
  struct IPropertyStore *v20; // rcx
  __int64 v21; // r8
  int AudioControllerProperties; // eax
  __int64 v23; // rdx
  const struct _tlgProvider_t *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  bool v27; // di
  unsigned int v28; // ebx
  CAvEndpointBuilder *v29; // rcx
  int v31; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v32; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  struct IPropertyStore *v34; // [rsp+40h] [rbp-C0h] BYREF
  PROPVARIANT v35[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+58h] [rbp-A8h]
  PROPVARIANT v37[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h]
  PROPVARIANT v39[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+88h] [rbp-78h]
  PROPVARIANT v41[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-60h]
  PROPVARIANT pvar[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-48h]
  PROPVARIANT v45[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v46; // [rsp+D0h] [rbp-30h]
  PROPVARIANT v47[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v48; // [rsp+E8h] [rbp-18h]
  PROPVARIANT v49[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v50; // [rsp+100h] [rbp+0h]
  PROPVARIANT v51[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v52; // [rsp+118h] [rbp+18h]
  PROPVARIANT v53[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v54; // [rsp+130h] [rbp+30h]
  PROPVARIANT v55[2]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v56; // [rsp+148h] [rbp+48h]
  PROPVARIANT v57[2]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v58; // [rsp+160h] [rbp+60h]
  PROPVARIANT v59[2]; // [rsp+168h] [rbp+68h] BYREF
  __int64 v60; // [rsp+178h] [rbp+78h]
  PROPVARIANT v61[2]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v62; // [rsp+190h] [rbp+90h]
  PROPVARIANT v63[2]; // [rsp+198h] [rbp+98h] BYREF
  __int64 v64; // [rsp+1A8h] [rbp+A8h]
  unsigned int v65; // [rsp+1B0h] [rbp+B0h] BYREF
  int v66; // [rsp+1B4h] [rbp+B4h] BYREF
  int v67; // [rsp+1B8h] [rbp+B8h] BYREF
  struct IPropertyStore *v68; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v69; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned int v70; // [rsp+1D0h] [rbp+D0h] BYREF
  int v71; // [rsp+1D4h] [rbp+D4h] BYREF
  __int64 v72; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v73; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+1E8h] [rbp+E8h] BYREF
  int v75[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  LPCRITICAL_SECTION v76; // [rsp+1F8h] [rbp+F8h]
  _BYTE v77[40]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 *v78; // [rsp+228h] [rbp+128h]
  PROPVARIANT v79; // [rsp+240h] [rbp+140h]
  PROPVARIANT v80; // [rsp+248h] [rbp+148h]
  PROPVARIANT v81; // [rsp+250h] [rbp+150h]
  PROPVARIANT v82; // [rsp+258h] [rbp+158h]
  PROPVARIANT v83; // [rsp+260h] [rbp+160h]
  PROPVARIANT v84; // [rsp+268h] [rbp+168h]
  CAvEndpointBuilder *v85; // [rsp+278h] [rbp+178h]
  __int64 v86; // [rsp+288h] [rbp+188h]
  PROPVARIANT v87; // [rsp+290h] [rbp+190h]
  __int128 v88; // [rsp+298h] [rbp+198h]
  int v89; // [rsp+2E8h] [rbp+1E8h]
  unsigned int v90; // [rsp+2ECh] [rbp+1ECh]
  int v91; // [rsp+2F0h] [rbp+1F0h]
  int v92; // [rsp+2F4h] [rbp+1F4h]
  int v93; // [rsp+2FCh] [rbp+1FCh]
  bool v94; // [rsp+320h] [rbp+220h]
  char v95; // [rsp+321h] [rbp+221h]
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  v68 = 0;
  v73 = 0;
  v72 = 0;
  v34 = 0;
  v69 = 0;
  v32 = 0;
  *(_OWORD *)v61 = 0;
  v62 = 0;
  *(_OWORD *)v59 = 0;
  v60 = 0;
  *(_OWORD *)v41 = 0;
  v42 = 0;
  *(_OWORD *)v55 = 0;
  v56 = 0;
  *(_OWORD *)v53 = 0;
  v54 = 0;
  *(_OWORD *)v39 = 0;
  v40 = 0;
  *(_OWORD *)v37 = 0;
  v38 = 0;
  *(_OWORD *)v51 = 0;
  v52 = 0;
  *(_OWORD *)v49 = 0;
  v50 = 0;
  *(_OWORD *)v47 = 0;
  v48 = 0;
  *(_OWORD *)v63 = 0;
  v64 = 0;
  *(_OWORD *)v35 = 0;
  v36 = 0;
  *(_OWORD *)v57 = 0;
  v58 = 0;
  *(_OWORD *)v45 = 0;
  v46 = 0;
  *(_OWORD *)pvar = 0;
  v44 = 0;
  v70 = 0;
  v65 = 0;
  v66 = 0;
  v71 = 0;
  v67 = 0;
  pv = 0;
  UnbiasedTime = 0;
  memset_0(v77, 0, 0x128u);
  EnterCriticalSection(lpCriticalSection);
  v76 = lpCriticalSection;
  if ( !QueryUnbiasedInterruptTime(&UnbiasedTime) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x9E6,
                  (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
                  v4);
LABEL_6:
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    if ( pv )
      CoTaskMemFree(pv);
    PropVariantClear(pvar);
    PropVariantClear(v45);
    PropVariantClear(v57);
    PropVariantClear(v35);
    PropVariantClear(v63);
    PropVariantClear(v47);
    PropVariantClear(v49);
    PropVariantClear(v51);
    PropVariantClear(v37);
    PropVariantClear(v39);
    PropVariantClear(v53);
    PropVariantClear(v55);
    PropVariantClear(v41);
    PropVariantClear(v59);
    PropVariantClear(v61);
    if ( v32 )
      CoTaskMemFree(v32);
    goto LABEL_165;
  }
  v6 = **a2;
  v73 = 0;
  v7 = v6((struct IPnpInterface *)a2, &GUID_d666063f_1587_4e43_81f1_b948e807363f, &v73);
  LastError = v7;
  if ( v7 < 0 )
  {
    v8 = 2536;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v7,
      v31);
    goto LABEL_6;
  }
  v9 = *(__int64 (__fastcall **)(__int64, __int64, struct IPropertyStore **))(*(_QWORD *)v73 + 32LL);
  v68 = 0;
  v7 = v9(v73, 2, &v68);
  LastError = v7;
  if ( v7 < 0 )
  {
    v8 = 2538;
    goto LABEL_5;
  }
  LOWORD(v61[0]) = 21;
  v61[1] = (PROPVARIANT)UnbiasedTime;
  v7 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v68->lpVtbl->SetValue)(
         v68,
         PKEY_MMDEVAPI_ActiveTime,
         v61);
  LastError = v7;
  if ( v7 < 0 )
  {
    v8 = 2542;
    goto LABEL_5;
  }
  v7 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v68->lpVtbl->GetValue)(
         v68,
         &PKEY_NAME,
         v59);
  LastError = v7;
  if ( v7 < 0 )
  {
    v8 = 2545;
    goto LABEL_5;
  }
  if ( LOWORD(v59[0]) && LOWORD(v59[0]) != 31 )
  {
    v10 = 2546;
LABEL_79:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)0x80070057LL,
      v31);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    if ( pv )
      CoTaskMemFree(pv);
    PropVariantClear(pvar);
    PropVariantClear(v45);
    PropVariantClear(v57);
    PropVariantClear(v35);
    PropVariantClear(v63);
    PropVariantClear(v47);
    PropVariantClear(v49);
    PropVariantClear(v51);
    PropVariantClear(v37);
    PropVariantClear(v39);
    PropVariantClear(v53);
    PropVariantClear(v55);
    PropVariantClear(v41);
    PropVariantClear(v59);
    PropVariantClear(v61);
    if ( v32 )
      CoTaskMemFree(v32);
LABEL_85:
    LastError = -2147024809;
    goto LABEL_165;
  }
  v11 = (__int64 (__fastcall *)(struct IPnpInterface *, __int64 *))(*a2)[3];
  wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v72);
  v7 = v11((struct IPnpInterface *)a2, &v72);
  LastError = v7;
  if ( v7 < 0 )
  {
    v8 = 2549;
    goto LABEL_5;
  }
  v12 = v69;
  v69 = 0;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v7 = wil::com_query_to_nothrow<IMMDevice,IPnpDevnode * &>(&v72, &v69);
  LastError = v7;
  if ( v7 < 0 )
  {
    v8 = 2551;
    goto LABEL_5;
  }
  v13 = v69;
  v14 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v69 + 40LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v32,
    0);
  v7 = v14(v13, &v32);
  LastError = v7;
  if ( v7 < 0 )
  {
    v8 = 2554;
    goto LABEL_5;
  }
  v15 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v15 > 4u )
  {
    *(_QWORD *)v75 = v32;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v15,
      (unsigned int)&word_180076AEE,
      v16,
      v17,
      (__int64)v75);
  }
  v18 = v69;
  v19 = *(__int64 (__fastcall **)(__int64, __int64, struct IPropertyStore **))(*(_QWORD *)v69 + 32LL);
  v20 = v34;
  v34 = 0;
  if ( v20 )
    ((void (__fastcall *)(struct IPropertyStore *))v20->lpVtbl->Release)(v20);
  v7 = v19(v18, 2, &v34);
  LastError = v7;
  if ( v7 < 0 )
  {
    v8 = 2563;
    goto LABEL_5;
  }
  v7 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v34->lpVtbl->GetValue)(
         v34,
         &PKEY_NAME,
         v41);
  LastError = v7;
  if ( v7 < 0 )
  {
    v8 = 2565;
    goto LABEL_5;
  }
  if ( LOWORD(v41[0]) != 31 )
  {
    v10 = 2566;
    goto LABEL_79;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids, v41[1]);
  }
  v7 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v34->lpVtbl->GetValue)(
         v34,
         &DEVPKEY_Device_DriverNodeStrongName,
         v55);
  LastError = v7;
  if ( v7 < 0 )
  {
    v8 = 2569;
    goto LABEL_5;
  }
  if ( LOWORD(v55[0]) != 31 )
  {
    v10 = 2570;
    goto LABEL_79;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids, v55[1]);
  }
  v7 = ((__int64 (__fastcall *)(struct IPropertyStore *, const DEVPROPKEY *, PROPVARIANT *))v34->lpVtbl->GetValue)(
         v34,
         &DEVPKEY_Device_MatchingDeviceId,
         v53);
  LastError = v7;
  if ( v7 < 0 )
  {
    v8 = 2574;
    goto LABEL_5;
  }
  if ( LOWORD(v53[0]) == 31 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids, v53[1]);
    }
    v82 = v53[1];
  }
  v7 = ((__int64 (__fastcall *)(struct IPropertyStore *, const DEVPROPKEY *, PROPVARIANT *))v34->lpVtbl->GetValue)(
         v34,
         &DEVPKEY_Device_DriverInfPath,
         v39);
  LastError = v7;
  if ( v7 < 0 )
  {
    v8 = 2581;
    goto LABEL_5;
  }
  if ( LOWORD(v39[0]) != 31 )
  {
    v10 = 2582;
    goto LABEL_79;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids, v39[1]);
  }
  v7 = ((__int64 (__fastcall *)(struct IPropertyStore *, const DEVPROPKEY *, PROPVARIANT *))v34->lpVtbl->GetValue)(
         v34,
         &DEVPKEY_Device_DriverInfSection,
         v51);
  LastError = v7;
  if ( v7 < 0 )
  {
    v8 = 2585;
    goto LABEL_5;
  }
  if ( LOWORD(v51[0]) != 31 )
  {
    v10 = 2586;
    goto LABEL_79;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids, v51[1]);
  }
  v7 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v34->lpVtbl->GetValue)(
         v34,
         &PKEY_Device_ContainerId,
         v49);
  LastError = v7;
  if ( v7 < 0 )
  {
    v8 = 2589;
    goto LABEL_5;
  }
  if ( LOWORD(v49[0]) != 72 )
  {
    v10 = 2590;
    goto LABEL_79;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v21, v49[1]);
  }
  v7 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v34->lpVtbl->GetValue)(
         v34,
         &PKEY_Device_EnumeratorName,
         v47);
  LastError = v7;
  if ( v7 < 0 )
  {
    v8 = 2593;
    goto LABEL_5;
  }
  if ( LOWORD(v47[0]) != 31 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA22,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)0x80070057LL,
      v31);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    if ( pv )
      CoTaskMemFree(pv);
    PropVariantClear(pvar);
    PropVariantClear(v45);
    PropVariantClear(v57);
    PropVariantClear(v35);
    PropVariantClear(v63);
    PropVariantClear(v47);
    PropVariantClear(v49);
    PropVariantClear(v51);
    PropVariantClear(v37);
    PropVariantClear(v39);
    PropVariantClear(v53);
    PropVariantClear(v55);
    PropVariantClear(v41);
    PropVariantClear(v59);
    PropVariantClear(v61);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v32);
    goto LABEL_85;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids, v47[1]);
  }
  if ( ((int (__fastcall *)(struct IPropertyStore *, const DEVPROPKEY *, PROPVARIANT *))v34->lpVtbl->GetValue)(
         v34,
         &DEVPKEY_Device_SessionId,
         pvar) >= 0
    && LOWORD(pvar[0]) == 19 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
    }
    v89 = (int)pvar[1];
  }
  AudioControllerProperties = ((__int64 (__fastcall *)(struct IPropertyStore *, const DEVPROPKEY *, PROPVARIANT *))v34->lpVtbl->GetValue)(
                                v34,
                                &DEVPKEY_Device_InstallDate,
                                v35);
  LastError = AudioControllerProperties;
  if ( AudioControllerProperties < 0 )
  {
    v23 = 2604;
LABEL_111:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)AudioControllerProperties,
      v31);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
    PropVariantClear(pvar);
    PropVariantClear(v45);
    PropVariantClear(v57);
    PropVariantClear(v35);
    PropVariantClear(v63);
    PropVariantClear(v47);
    PropVariantClear(v49);
    PropVariantClear(v51);
    PropVariantClear(v37);
    PropVariantClear(v39);
    PropVariantClear(v53);
    PropVariantClear(v55);
    PropVariantClear(v41);
    PropVariantClear(v59);
    PropVariantClear(v61);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v32);
    goto LABEL_165;
  }
  if ( LOWORD(v35[0]) != 64 )
    v35[1] = 0;
  AudioControllerProperties = ((__int64 (__fastcall *)(struct IPropertyStore *, const DEVPROPKEY *, PROPVARIANT *))v34->lpVtbl->GetValue)(
                                v34,
                                &DEVPKEY_Device_IsRebootRequired,
                                v57);
  LastError = AudioControllerProperties;
  if ( AudioControllerProperties < 0 )
  {
    v23 = 2614;
    goto LABEL_111;
  }
  if ( LOWORD(v57[0]) == 11 && LOWORD(v57[1]) )
  {
    v95 = 1;
    v24 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v24 > 4u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v24,
        &byte_180076A7F);
  }
  else
  {
    v95 = 0;
  }
  AudioControllerProperties = CheckBus(
                                v72,
                                (unsigned int)&v65,
                                (unsigned int)&v71,
                                (unsigned int)&v66,
                                (__int64)&v67,
                                (__int64)&pv);
  LastError = AudioControllerProperties;
  if ( AudioControllerProperties < 0 )
  {
    v23 = 2627;
    goto LABEL_111;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v31 = v66;
    WPP_SF_lll(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, v26, v65);
  }
  AudioControllerProperties = GenerateNameDiscriminator(v32, v34, (const unsigned __int16 *)v41[1], &v70);
  LastError = AudioControllerProperties;
  if ( AudioControllerProperties < 0 )
  {
    v23 = 2634;
    goto LABEL_111;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
  }
  AudioControllerProperties = ((__int64 (__fastcall *)(struct IPropertyStore *, const DEVPROPKEY *, PROPVARIANT *))v34->lpVtbl->GetValue)(
                                v34,
                                &DEVPKEY_Device_HardwareIds,
                                v45);
  LastError = AudioControllerProperties;
  if ( AudioControllerProperties < 0 )
  {
    v23 = 2640;
    goto LABEL_111;
  }
  if ( LOWORD(v45[0]) == 4127 && LODWORD(v45[1]) )
    v86 = *v46;
  v27 = IsNonInboxInf((const unsigned __int16 *)v39[1]);
  if ( !v27
    && ((int (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v34->lpVtbl->GetValue)(
         v34,
         DEVPKEY_Device_DriverExtendedInfs,
         v37) >= 0
    && LOWORD(v37[0]) == 4127 )
  {
    v28 = 0;
    if ( LODWORD(v37[1]) )
    {
      while ( !IsNonInboxInf(*(const unsigned __int16 **)(v38 + 8LL * v28)) )
      {
        if ( ++v28 >= LODWORD(v37[1]) )
          goto LABEL_148;
      }
      v27 = 1;
    }
  }
LABEL_148:
  v78 = v32;
  v79 = v59[1];
  v80 = v41[1];
  v81 = v55[1];
  v83 = v39[1];
  v84 = v51[1];
  v88 = *(_OWORD *)v49[1];
  v29 = (CAvEndpointBuilder *)v47[1];
  if ( pv )
    v29 = (CAvEndpointBuilder *)pv;
  v85 = v29;
  v90 = v65;
  v91 = v71;
  v92 = v66;
  v93 = v67;
  v87 = v35[1];
  v94 = v27;
  AudioControllerProperties = CAvEndpointBuilder::ReadAudioControllerProperties(
                                v29,
                                v68,
                                (struct ENDPOINT_DESCRIPTOR *)v77);
  LastError = AudioControllerProperties;
  if ( AudioControllerProperties < 0 )
  {
    v23 = 2686;
    goto LABEL_111;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
  }
  AudioControllerProperties = CAvEndpointBuilder::CreateAvEndpointsForPnpInterface(
                                (CAvEndpointBuilder *)lpCriticalSection,
                                (struct IPnpInterface *)a2,
                                (const struct ENDPOINT_DESCRIPTOR *)v77);
  LastError = AudioControllerProperties;
  if ( AudioControllerProperties >= 0 )
  {
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
    PropVariantClear(pvar);
    PropVariantClear(v45);
    PropVariantClear(v57);
    PropVariantClear(v35);
    PropVariantClear(v63);
    PropVariantClear(v47);
    PropVariantClear(v49);
    PropVariantClear(v51);
    PropVariantClear(v37);
    PropVariantClear(v39);
    PropVariantClear(v53);
    PropVariantClear(v55);
    PropVariantClear(v41);
    PropVariantClear(v59);
    PropVariantClear(v61);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v32);
    LastError = 0;
  }
  else
  {
    if ( AudioControllerProperties != -2147024893 )
    {
      v23 = 2693;
      goto LABEL_111;
    }
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
    PropVariantClear(pvar);
    PropVariantClear(v45);
    PropVariantClear(v57);
    PropVariantClear(v35);
    PropVariantClear(v63);
    PropVariantClear(v47);
    PropVariantClear(v49);
    PropVariantClear(v51);
    PropVariantClear(v37);
    PropVariantClear(v39);
    PropVariantClear(v53);
    PropVariantClear(v55);
    PropVariantClear(v41);
    PropVariantClear(v59);
    PropVariantClear(v61);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v32);
    LastError = -2147024893;
  }
LABEL_165:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v72);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v73);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v68);
  return LastError;
}

```

## disassembly

```asm
0x18002d094  mov     [rsp-8+arg_10], rbx
0x18002d099  mov     [rsp-8+arg_18], rsi
0x18002d09e  push    rbp
0x18002d09f  push    rdi
0x18002d0a0  push    r13
0x18002d0a2  push    r14
0x18002d0a4  push    r15
0x18002d0a6  lea     rbp, [rsp-240h]
0x18002d0ae  sub     rsp, 340h
0x18002d0b5  mov     rax, cs:__security_cookie
0x18002d0bc  xor     rax, rsp
0x18002d0bf  mov     [rbp+260h+var_30], rax
0x18002d0c6  mov     r14, rdx
0x18002d0c9  mov     rsi, rcx
0x18002d0cc  xor     r15d, r15d
0x18002d0cf  mov     [rbp+260h+var_1A0], r15
0x18002d0d6  mov     [rbp+260h+var_180], r15
0x18002d0dd  mov     [rbp+260h+var_188], r15
0x18002d0e4  mov     [rsp+360h+var_320], r15
0x18002d0e9  mov     [rbp+260h+var_198], r15
0x18002d0f0  mov     [rsp+360h+var_330], r15
0x18002d0f5  xorps   xmm0, xmm0
0x18002d0f8  xor     eax, eax
0x18002d0fa  movups  xmmword ptr [rbp+260h+var_1E0], xmm0
0x18002d101  mov     [rbp+260h+var_1D0], rax
0x18002d108  movups  xmmword ptr [rbp+260h+var_1F8], xmm0
0x18002d10c  mov     [rbp+260h+var_1E8], rax
0x18002d110  movups  xmmword ptr [rbp+260h+var_2D0], xmm0
0x18002d114  mov     [rbp+260h+var_2C0], rax
0x18002d118  movups  xmmword ptr [rbp+260h+var_228], xmm0
0x18002d11c  mov     [rbp+260h+var_218], rax
0x18002d120  movups  xmmword ptr [rbp+260h+var_240], xmm0
0x18002d124  mov     [rbp+260h+var_230], rax
0x18002d128  movups  xmmword ptr [rsp+360h+var_2E8], xmm0
0x18002d12d  mov     [rbp+260h+var_2D8], rax
0x18002d131  movups  xmmword ptr [rsp+360h+var_300], xmm0
0x18002d136  mov     [rsp+360h+var_2F0], rax
0x18002d13b  movups  xmmword ptr [rbp+260h+var_258], xmm0
0x18002d13f  mov     [rbp+260h+var_248], rax
0x18002d143  movups  xmmword ptr [rbp+260h+var_270], xmm0
0x18002d147  mov     [rbp+260h+var_260], rax
0x18002d14b  movups  xmmword ptr [rbp+260h+var_288], xmm0
0x18002d14f  mov     [rbp+260h+var_278], rax
0x18002d153  movups  xmmword ptr [rbp+260h+var_1C8], xmm0
0x18002d15a  mov     [rbp+260h+var_1B8], rax
0x18002d161  movups  xmmword ptr [rsp+360h+var_318], xmm0
0x18002d166  mov     [rsp+360h+var_308], rax
0x18002d16b  movups  xmmword ptr [rbp+260h+var_210], xmm0
0x18002d16f  mov     [rbp+260h+var_200], rax
0x18002d173  movups  xmmword ptr [rbp+260h+var_2A0], xmm0
0x18002d177  mov     [rbp+260h+var_290], rax
0x18002d17b  movups  xmmword ptr [rbp+260h+pvar], xmm0
0x18002d17f  mov     [rbp+260h+var_2A8], rax
0x18002d183  mov     [rbp+260h+var_190], r15d
0x18002d18a  mov     [rbp+260h+var_1B0], r15d
0x18002d191  mov     [rbp+260h+var_1AC], r15d
0x18002d198  mov     [rbp+260h+var_18C], r15d
0x18002d19f  mov     [rbp+260h+var_1A8], r15d
0x18002d1a6  mov     [rsp+360h+pv], r15
0x18002d1ab  mov     [rbp+260h+UnbiasedTime], r15
0x18002d1b2  xor     edx, edx; Val
0x18002d1b4  mov     r8d, 128h; Size
0x18002d1ba  lea     rcx, [rbp+260h+var_160]; void *
0x18002d1c1  call    memset_0
0x18002d1c6  mov     rcx, rsi; lpCriticalSection
0x18002d1c9  call    cs:__imp_EnterCriticalSection
0x18002d1cf  mov     [rbp+260h+var_168], rsi
0x18002d1d6  lea     rcx, [rbp+260h+UnbiasedTime]; UnbiasedTime
0x18002d1dd  call    cs:__imp_QueryUnbiasedInterruptTime
0x18002d1e3  test    eax, eax
0x18002d1e5  jnz     short loc_18002D203
0x18002d1e7  mov     rcx, [rbp+268h]; this
0x18002d1ee  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18002d1f5  mov     edx, 9E6h; void *
0x18002d1fa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d1ff  mov     ebx, eax
0x18002d201  jmp     short loc_18002D268
0x18002d203  mov     rax, [r14]
0x18002d206  mov     rbx, [rax]
0x18002d209  mov     rcx, [rbp+260h+var_180]
0x18002d210  mov     [rbp+260h+var_180], r15
0x18002d217  test    rcx, rcx
0x18002d21a  jz      short loc_18002D229
0x18002d21c  mov     rdx, [rcx]
0x18002d21f  mov     rax, [rdx+10h]
0x18002d223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d228  nop
0x18002d229  lea     r8, [rbp+260h+var_180]
0x18002d230  lea     rdx, _GUID_d666063f_1587_4e43_81f1_b948e807363f
0x18002d237  mov     rcx, r14
0x18002d23a  mov     rax, rbx
0x18002d23d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d242  mov     ebx, eax
0x18002d244  test    eax, eax
0x18002d246  jns     loc_18002D34F
0x18002d24c  mov     edx, 9E8h; void *
0x18002d251  mov     rcx, [rbp+268h]; this
0x18002d258  mov     r9d, eax; char *
0x18002d25b  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18002d262  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d267  nop
0x18002d268  test    rsi, rsi
0x18002d26b  jz      short loc_18002D277
0x18002d26d  mov     rcx, rsi; lpCriticalSection
0x18002d270  call    cs:__imp_LeaveCriticalSection
0x18002d276  nop
0x18002d277  mov     rcx, [rsp+360h+pv]; pv
0x18002d27c  test    rcx, rcx
0x18002d27f  jz      short loc_18002D288
0x18002d281  call    cs:__imp_CoTaskMemFree
0x18002d287  nop
0x18002d288  lea     rcx, [rbp+260h+pvar]; pvar
0x18002d28c  call    cs:__imp_PropVariantClear
0x18002d292  nop
0x18002d293  lea     rcx, [rbp+260h+var_2A0]; pvar
0x18002d297  call    cs:__imp_PropVariantClear
0x18002d29d  nop
0x18002d29e  lea     rcx, [rbp+260h+var_210]; pvar
0x18002d2a2  call    cs:__imp_PropVariantClear
0x18002d2a8  nop
0x18002d2a9  lea     rcx, [rsp+360h+var_318]; pvar
0x18002d2ae  call    cs:__imp_PropVariantClear
0x18002d2b4  nop
0x18002d2b5  lea     rcx, [rbp+260h+var_1C8]; pvar
0x18002d2bc  call    cs:__imp_PropVariantClear
0x18002d2c2  nop
0x18002d2c3  lea     rcx, [rbp+260h+var_288]; pvar
0x18002d2c7  call    cs:__imp_PropVariantClear
0x18002d2cd  nop
0x18002d2ce  lea     rcx, [rbp+260h+var_270]; pvar
0x18002d2d2  call    cs:__imp_PropVariantClear
0x18002d2d8  nop
0x18002d2d9  lea     rcx, [rbp+260h+var_258]; pvar
0x18002d2dd  call    cs:__imp_PropVariantClear
0x18002d2e3  nop
0x18002d2e4  lea     rcx, [rsp+360h+var_300]; pvar
0x18002d2e9  call    cs:__imp_PropVariantClear
0x18002d2ef  nop
0x18002d2f0  lea     rcx, [rsp+360h+var_2E8]; pvar
0x18002d2f5  call    cs:__imp_PropVariantClear
0x18002d2fb  nop
0x18002d2fc  lea     rcx, [rbp+260h+var_240]; pvar
0x18002d300  call    cs:__imp_PropVariantClear
0x18002d306  nop
0x18002d307  lea     rcx, [rbp+260h+var_228]; pvar
0x18002d30b  call    cs:__imp_PropVariantClear
0x18002d311  nop
0x18002d312  lea     rcx, [rbp+260h+var_2D0]; pvar
0x18002d316  call    cs:__imp_PropVariantClear
0x18002d31c  nop
0x18002d31d  lea     rcx, [rbp+260h+var_1F8]; pvar
0x18002d321  call    cs:__imp_PropVariantClear
0x18002d327  nop
0x18002d328  lea     rcx, [rbp+260h+var_1E0]; pvar
0x18002d32f  call    cs:__imp_PropVariantClear
0x18002d335  nop
0x18002d336  mov     rcx, [rsp+360h+var_330]; pv
0x18002d33b  test    rcx, rcx
0x18002d33e  jz      loc_18002E0D1
0x18002d344  call    cs:__imp_CoTaskMemFree
0x18002d34a  jmp     loc_18002E0D1
0x18002d34f  mov     rbx, [rbp+260h+var_180]
0x18002d356  mov     rax, [rbx]
0x18002d359  mov     rdi, [rax+20h]
0x18002d35d  mov     rcx, [rbp+260h+var_1A0]
0x18002d364  mov     [rbp+260h+var_1A0], r15
0x18002d36b  test    rcx, rcx
0x18002d36e  jz      short loc_18002D37D
0x18002d370  mov     rdx, [rcx]
0x18002d373  mov     rax, [rdx+10h]
0x18002d377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d37c  nop
0x18002d37d  lea     r8, [rbp+260h+var_1A0]
0x18002d384  mov     r13d, 2
0x18002d38a  mov     edx, r13d
0x18002d38d  mov     rcx, rbx
0x18002d390  mov     rax, rdi
0x18002d393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d398  mov     ebx, eax
0x18002d39a  test    eax, eax
0x18002d39c  jns     short loc_18002D3A8
0x18002d39e  mov     edx, 9EAh
0x18002d3a3  jmp     loc_18002D251
0x18002d3a8  mov     eax, 15h
0x18002d3ad  mov     word ptr [rbp+260h+var_1E0], ax
0x18002d3b4  mov     rax, [rbp+260h+UnbiasedTime]
0x18002d3bb  mov     [rbp+260h+var_1E0+8], rax
0x18002d3c2  mov     rcx, [rbp+260h+var_1A0]
0x18002d3c9  mov     rax, [rcx]
0x18002d3cc  lea     r8, [rbp+260h+var_1E0]
0x18002d3d3  lea     rdx, PKEY_MMDEVAPI_ActiveTime
0x18002d3da  mov     rax, [rax+30h]
0x18002d3de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3e3  mov     ebx, eax
0x18002d3e5  test    eax, eax
0x18002d3e7  jns     short loc_18002D3F3
0x18002d3e9  mov     edx, 9EEh
0x18002d3ee  jmp     loc_18002D251
0x18002d3f3  mov     rcx, [rbp+260h+var_1A0]
0x18002d3fa  mov     rax, [rcx]
0x18002d3fd  lea     r8, [rbp+260h+var_1F8]
0x18002d401  lea     rdx, PKEY_NAME
0x18002d408  mov     rax, [rax+28h]
0x18002d40c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d411  mov     ebx, eax
0x18002d413  test    eax, eax
0x18002d415  jns     short loc_18002D421
0x18002d417  mov     edx, 9F1h
0x18002d41c  jmp     loc_18002D251
0x18002d421  movzx   eax, word ptr [rbp+260h+var_1F8]
0x18002d425  test    ax, ax
0x18002d428  jz      short loc_18002D43A
0x18002d42a  cmp     ax, 1Fh
0x18002d42e  jz      short loc_18002D43A
0x18002d430  mov     edx, 9F2h
0x18002d435  jmp     loc_18002D7DB
0x18002d43a  mov     rax, [r14]
0x18002d43d  mov     rbx, [rax+18h]
0x18002d441  lea     rcx, [rbp+260h+var_188]
0x18002d448  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x18002d44d  lea     rdx, [rbp+260h+var_188]
0x18002d454  mov     rcx, r14
0x18002d457  mov     rax, rbx
0x18002d45a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d45f  mov     ebx, eax
0x18002d461  test    eax, eax
0x18002d463  jns     short loc_18002D46F
0x18002d465  mov     edx, 9F5h
0x18002d46a  jmp     loc_18002D251
0x18002d46f  mov     rcx, [rbp+260h+var_198]
0x18002d476  mov     [rbp+260h+var_198], r15
0x18002d47d  test    rcx, rcx
0x18002d480  jz      short loc_18002D48F
0x18002d482  mov     rax, [rcx]
0x18002d485  mov     rax, [rax+10h]
0x18002d489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d48e  nop
0x18002d48f  lea     rdx, [rbp+260h+var_198]
0x18002d496  lea     rcx, [rbp+260h+var_188]
0x18002d49d  call    ??$com_query_to_nothrow@UIMMDevice@@AEAPEAUIPnpDevnode@@@wil@@YAJAEAPEAUIPnpDevnode@@PEAPEAUIMMDevice@@@Z; wil::com_query_to_nothrow<IMMDevice,IPnpDevnode * &>(IPnpDevnode * &,IMMDevice * *)
0x18002d4a2  mov     ebx, eax
0x18002d4a4  test    eax, eax
0x18002d4a6  jns     short loc_18002D4B2
0x18002d4a8  mov     edx, 9F7h
0x18002d4ad  jmp     loc_18002D251
0x18002d4b2  mov     rdi, [rbp+260h+var_198]
0x18002d4b9  mov     rax, [rdi]
0x18002d4bc  mov     rbx, [rax+28h]
0x18002d4c0  xor     edx, edx
0x18002d4c2  lea     rcx, [rsp+360h+var_330]
0x18002d4c7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002d4cc  lea     rdx, [rsp+360h+var_330]
0x18002d4d1  mov     rcx, rdi
0x18002d4d4  mov     rax, rbx
0x18002d4d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4dc  mov     ebx, eax
0x18002d4de  test    eax, eax
0x18002d4e0  jns     short loc_18002D4EC
0x18002d4e2  mov     edx, 9FAh
0x18002d4e7  jmp     loc_18002D251
0x18002d4ec  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18002d4f1  mov     ecx, [rax]
0x18002d4f3  cmp     ecx, 4
0x18002d4f6  jbe     short loc_18002D51F
0x18002d4f8  mov     rcx, [rsp+360h+var_330]
0x18002d4fd  mov     qword ptr [rbp+260h+var_170], rcx
0x18002d504  lea     rcx, [rbp+260h+var_170]
0x18002d50b  mov     qword ptr [rsp+360h+var_340], rcx; int
0x18002d510  lea     rdx, word_180076AEE
0x18002d517  mov     rcx, rax
0x18002d51a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002d51f  mov     rbx, [rbp+260h+var_198]
0x18002d526  mov     rax, [rbx]
0x18002d529  mov     rdi, [rax+20h]
0x18002d52d  mov     rcx, [rsp+360h+var_320]
0x18002d532  mov     [rsp+360h+var_320], r15
0x18002d537  test    rcx, rcx
0x18002d53a  jz      short loc_18002D549
0x18002d53c  mov     rdx, [rcx]
0x18002d53f  mov     rax, [rdx+10h]
0x18002d543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d548  nop
0x18002d549  lea     r8, [rsp+360h+var_320]
0x18002d54e  mov     edx, r13d
0x18002d551  mov     rcx, rbx
0x18002d554  mov     rax, rdi
0x18002d557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d55c  mov     ebx, eax
0x18002d55e  test    eax, eax
0x18002d560  jns     short loc_18002D56C
0x18002d562  mov     edx, 0A03h
0x18002d567  jmp     loc_18002D251
0x18002d56c  mov     rcx, [rsp+360h+var_320]
0x18002d571  mov     rax, [rcx]
0x18002d574  lea     r8, [rbp+260h+var_2D0]
0x18002d578  lea     rdx, PKEY_NAME
0x18002d57f  mov     rax, [rax+28h]
0x18002d583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d588  mov     ebx, eax
0x18002d58a  test    eax, eax
  ... truncated ...
```
