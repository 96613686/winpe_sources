# PcapTokenProcessOneCallback(int *,unsigned __int64,void *)

- ea: `0x180012040`
- end: `0x180012917`
- name: `?PcapTokenProcessOneCallback@@YAKPEAH_KPEAX@Z`
- size: `2263`
- prototype: `__int64 __fastcall(int *, unsigned __int64, struct _PCA_SERVICE *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callees

- `0x180011bf4`
- `0x180012040`
- `0x180012920`
- `0x180012960`
- `0x180012b78`
- `0x180056256`
- `0x18007a9cf`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `msvcrt!_itoa_s` at `0x180012414`
- `msvcrt!_itoa_s` at `0x180012414`
- `ntdll!RtlFreeHeap` at `0x18001261f`
- `ntdll!RtlFreeHeap` at `0x18001261f`
- `ntdll!RtlAllocateHeap` at `0x18001253c`
- `ntdll!RtlAllocateHeap` at `0x18001253c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800125c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012706`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800125c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012706`

## string_xrefs

- `0x1800125aa`: `PcaServiceSendDMEvent`
- `0x180012884`: `PcaServiceSendDMEvent`
- `0x1800128da`: `PcaServiceSendDMEvent`
- `0x18001259d`: `Failed to create stream [%d]`
- `0x18001282b`: `PcapTokenProcessOneCallback`
- `0x180012855`: `PcapTokenProcessOneCallback`
- `0x180012901`: `PcapTokenProcessOneCallback`
- `0x1800123b8`: `,Descriptor,`

## pseudocode

```c

```
