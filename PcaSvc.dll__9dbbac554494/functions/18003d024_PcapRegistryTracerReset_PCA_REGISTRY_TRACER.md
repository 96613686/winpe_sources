# PcapRegistryTracerReset(_PCA_REGISTRY_TRACER *)

- ea: `0x18003d024`
- end: `0x18003d261`
- name: `?PcapRegistryTracerReset@@YAXPEAU_PCA_REGISTRY_TRACER@@@Z`
- size: `573`
- prototype: `void __fastcall(struct _PCA_REGISTRY_TRACER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800b8e1c`

## callees

- `0x180012920`
- `0x18003d024`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d25a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003d1d4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003d1d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d036`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d036`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d1ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d1ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d23a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d23a`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18003d0ba`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18003d0ec`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18003d15a`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18003d0ba`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18003d0ec`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18003d15a`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18003d085`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18003d085`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18003d190`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18003d190`

## string_xrefs

- `0x18003d040`: `PcapRegistryTracerReset`
- `0x18003d117`: `Registry Events Lost: %lu, BufferWritten: %lu, LogBuffersLost: %lu, RealTimeBuffersLost: %lu`
- `0x18003d21f`: `RegistryTracer reset: WAIT_ABANDONED`
- `0x18003d210`: `RegistryTracer reset: WAIT_TIMEOUT`
- `0x18003d1f3`: `RegistryTracer reset: WAIT_FAILED [%d]`

## pseudocode

```c

```
