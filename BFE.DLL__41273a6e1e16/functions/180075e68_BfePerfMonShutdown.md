# BfePerfMonShutdown

- ea: `0x180075e68`
- end: `0x180075fb6`
- name: `BfePerfMonShutdown`
- size: `334`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180040ae0`
- `0x180075b5c`

## callees

- `0x18005b4fc`
- `0x180075e68`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075e7a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075e94`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075eae`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075ec8`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075ee2`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075efc`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075f16`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075f30`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075f4a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075f64`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075e7a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075e94`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075eae`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075ec8`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075ee2`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075efc`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075f16`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075f30`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075f4a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180075f64`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180075f7c`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180075f94`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180075f7c`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180075f94`

## pseudocode

```c
void *BfePerfMonShutdown()
{
  PerfDeleteInstance(gBfePerfMon, InstanceBlock);
  PerfDeleteInstance(gBfePerfMon, Instance);
  PerfDeleteInstance(gBfePerfMon, qword_1800F5798);
  PerfDeleteInstance(gBfePerfMon, qword_1800F57A0);
  PerfDeleteInstance(gBfePerfMon, qword_1800F57A8);
  PerfDeleteInstance(gBfePerfMon, qword_1800F57B0);
  PerfDeleteInstance(gBfePerfMon, qword_1800F57B8);
  PerfDeleteInstance(ProviderHandle, qword_1800F57C8);
  PerfDeleteInstance(gBfePerfMon, qword_1800F57D0);
  PerfDeleteInstance(gBfePerfMon, qword_1800F57D8);
  if ( gBfePerfMon )
    PerfStopProvider(gBfePerfMon);
  if ( ProviderHandle )
    PerfStopProvider(ProviderHandle);
  return memset_0(&gBfePerfMon, 0, 0x60u);
}

```

## disassembly

```asm
0x180075e68  sub     rsp, 28h
0x180075e6c  mov     rdx, cs:InstanceBlock; InstanceBlock
0x180075e73  mov     rcx, cs:gBfePerfMon; Provider
0x180075e7a  call    cs:__imp_PerfDeleteInstance
0x180075e81  nop     dword ptr [rax+rax+00h]
0x180075e86  mov     rdx, cs:Instance; InstanceBlock
0x180075e8d  mov     rcx, cs:gBfePerfMon; Provider
0x180075e94  call    cs:__imp_PerfDeleteInstance
0x180075e9b  nop     dword ptr [rax+rax+00h]
0x180075ea0  mov     rdx, cs:qword_1800F5798; InstanceBlock
0x180075ea7  mov     rcx, cs:gBfePerfMon; Provider
0x180075eae  call    cs:__imp_PerfDeleteInstance
0x180075eb5  nop     dword ptr [rax+rax+00h]
0x180075eba  mov     rdx, cs:qword_1800F57A0; InstanceBlock
0x180075ec1  mov     rcx, cs:gBfePerfMon; Provider
0x180075ec8  call    cs:__imp_PerfDeleteInstance
0x180075ecf  nop     dword ptr [rax+rax+00h]
0x180075ed4  mov     rdx, cs:qword_1800F57A8; InstanceBlock
0x180075edb  mov     rcx, cs:gBfePerfMon; Provider
0x180075ee2  call    cs:__imp_PerfDeleteInstance
0x180075ee9  nop     dword ptr [rax+rax+00h]
0x180075eee  mov     rdx, cs:qword_1800F57B0; InstanceBlock
0x180075ef5  mov     rcx, cs:gBfePerfMon; Provider
0x180075efc  call    cs:__imp_PerfDeleteInstance
0x180075f03  nop     dword ptr [rax+rax+00h]
0x180075f08  mov     rdx, cs:qword_1800F57B8; InstanceBlock
0x180075f0f  mov     rcx, cs:gBfePerfMon; Provider
0x180075f16  call    cs:__imp_PerfDeleteInstance
0x180075f1d  nop     dword ptr [rax+rax+00h]
0x180075f22  mov     rdx, cs:qword_1800F57C8; InstanceBlock
0x180075f29  mov     rcx, cs:ProviderHandle; Provider
0x180075f30  call    cs:__imp_PerfDeleteInstance
0x180075f37  nop     dword ptr [rax+rax+00h]
0x180075f3c  mov     rdx, cs:qword_1800F57D0; InstanceBlock
0x180075f43  mov     rcx, cs:gBfePerfMon; Provider
0x180075f4a  call    cs:__imp_PerfDeleteInstance
0x180075f51  nop     dword ptr [rax+rax+00h]
0x180075f56  mov     rdx, cs:qword_1800F57D8; InstanceBlock
0x180075f5d  mov     rcx, cs:gBfePerfMon; Provider
0x180075f64  call    cs:__imp_PerfDeleteInstance
0x180075f6b  nop     dword ptr [rax+rax+00h]
0x180075f70  mov     rcx, cs:gBfePerfMon; ProviderHandle
0x180075f77  test    rcx, rcx
0x180075f7a  jz      short loc_180075F88
0x180075f7c  call    cs:__imp_PerfStopProvider
0x180075f83  nop     dword ptr [rax+rax+00h]
0x180075f88  mov     rcx, cs:ProviderHandle; ProviderHandle
0x180075f8f  test    rcx, rcx
0x180075f92  jz      short loc_180075FA0
0x180075f94  call    cs:__imp_PerfStopProvider
0x180075f9b  nop     dword ptr [rax+rax+00h]
0x180075fa0  xor     edx, edx; Val
0x180075fa2  lea     rcx, gBfePerfMon; void *
0x180075fa9  lea     r8d, [rdx+60h]; Size
0x180075fad  add     rsp, 28h
0x180075fb1  jmp     memset_0
```
