# Wdi_NdisMRegisterWdiMiniportDriver

- ea: `0x14009afb0`
- end: `0x14009b09d`
- name: `Wdi_NdisMRegisterWdiMiniportDriver`
- size: `237`
- prototype: `NDIS_STATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath, NDIS_HANDLE MiniportDriverContext, PNDIS_MINIPORT_DRIVER_CHARACTERISTICS MiniportDriverCharacteristics, PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS MiniportWdiCharacteristics, PNDIS_HANDLE NdisMiniportDriverHandle)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140034ec4`
- `0x140087804`
- `0x14009afb0`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14009aff3`
- `ntoskrnl!DbgPrintEx` at `0x14009aff3`
- `NDIS!NdisGetVersion` at `0x14009afc5`
- `NDIS!NdisGetVersion` at `0x14009afc5`

## pseudocode

```c

```
