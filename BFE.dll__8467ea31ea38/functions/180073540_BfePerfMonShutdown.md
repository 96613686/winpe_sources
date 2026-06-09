# BfePerfMonShutdown

- ea: `0x180073540`
- end: `0x180073646`
- name: `BfePerfMonShutdown`
- size: `262`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18003f8d0`
- `0x180073250`

## callees

- `0x1800595ac`
- `0x180073540`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180073552`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180073566`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x18007357a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x18007358e`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x1800735a2`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x1800735b6`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x1800735ca`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x1800735de`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x1800735f2`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180073606`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180073552`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180073566`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x18007357a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x18007358e`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x1800735a2`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x1800735b6`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x1800735ca`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x1800735de`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x1800735f2`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180073606`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180073618`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x18007362a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180073618`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x18007362a`

## pseudocode

```c
void *BfePerfMonShutdown()
{
  PerfDeleteInstance(gBfePerfMon, InstanceBlock);
  PerfDeleteInstance(gBfePerfMon, Instance);
  PerfDeleteInstance(gBfePerfMon, qword_1800F2778);
  PerfDeleteInstance(gBfePerfMon, qword_1800F2780);
  PerfDeleteInstance(gBfePerfMon, qword_1800F2788);
  PerfDeleteInstance(gBfePerfMon, qword_1800F2790);
  PerfDeleteInstance(gBfePerfMon, qword_1800F2798);
  PerfDeleteInstance(ProviderHandle, qword_1800F27A8);
  PerfDeleteInstance(gBfePerfMon, qword_1800F27B0);
  PerfDeleteInstance(gBfePerfMon, qword_1800F27B8);
  if ( gBfePerfMon )
    PerfStopProvider(gBfePerfMon);
  if ( ProviderHandle )
    PerfStopProvider(ProviderHandle);
  return memset_0(&gBfePerfMon, 0, 0x60u);
}

```

## disassembly

```asm
0x180073540  sub     rsp, 28h
0x180073544  mov     rdx, cs:InstanceBlock; InstanceBlock
0x18007354b  mov     rcx, cs:gBfePerfMon; Provider
0x180073552  call    cs:__imp_PerfDeleteInstance
0x180073558  mov     rdx, cs:Instance; InstanceBlock
0x18007355f  mov     rcx, cs:gBfePerfMon; Provider
0x180073566  call    cs:__imp_PerfDeleteInstance
0x18007356c  mov     rdx, cs:qword_1800F2778; InstanceBlock
0x180073573  mov     rcx, cs:gBfePerfMon; Provider
0x18007357a  call    cs:__imp_PerfDeleteInstance
0x180073580  mov     rdx, cs:qword_1800F2780; InstanceBlock
0x180073587  mov     rcx, cs:gBfePerfMon; Provider
0x18007358e  call    cs:__imp_PerfDeleteInstance
0x180073594  mov     rdx, cs:qword_1800F2788; InstanceBlock
0x18007359b  mov     rcx, cs:gBfePerfMon; Provider
0x1800735a2  call    cs:__imp_PerfDeleteInstance
0x1800735a8  mov     rdx, cs:qword_1800F2790; InstanceBlock
0x1800735af  mov     rcx, cs:gBfePerfMon; Provider
0x1800735b6  call    cs:__imp_PerfDeleteInstance
0x1800735bc  mov     rdx, cs:qword_1800F2798; InstanceBlock
0x1800735c3  mov     rcx, cs:gBfePerfMon; Provider
0x1800735ca  call    cs:__imp_PerfDeleteInstance
0x1800735d0  mov     rdx, cs:qword_1800F27A8; InstanceBlock
0x1800735d7  mov     rcx, cs:ProviderHandle; Provider
0x1800735de  call    cs:__imp_PerfDeleteInstance
0x1800735e4  mov     rdx, cs:qword_1800F27B0; InstanceBlock
0x1800735eb  mov     rcx, cs:gBfePerfMon; Provider
0x1800735f2  call    cs:__imp_PerfDeleteInstance
0x1800735f8  mov     rdx, cs:qword_1800F27B8; InstanceBlock
0x1800735ff  mov     rcx, cs:gBfePerfMon; Provider
0x180073606  call    cs:__imp_PerfDeleteInstance
0x18007360c  mov     rcx, cs:gBfePerfMon; ProviderHandle
0x180073613  test    rcx, rcx
0x180073616  jz      short loc_18007361E
0x180073618  call    cs:__imp_PerfStopProvider
0x18007361e  mov     rcx, cs:ProviderHandle; ProviderHandle
0x180073625  test    rcx, rcx
0x180073628  jz      short loc_180073630
0x18007362a  call    cs:__imp_PerfStopProvider
0x180073630  xor     edx, edx; Val
0x180073632  lea     rcx, gBfePerfMon; void *
0x180073639  lea     r8d, [rdx+60h]; Size
0x18007363d  add     rsp, 28h
0x180073641  jmp     memset_0
```
