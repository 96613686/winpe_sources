# SystemEffectDescriptor::GetSupportedProcessingModes(CAudioSignalProcessingModeArray &,SED_ENHANCEMENTSENABLESTATE)

- ea: `0x1800281f8`
- end: `0x1800284b7`
- name: `?GetSupportedProcessingModes@SystemEffectDescriptor@@QEAAJAEAVCAudioSignalProcessingModeArray@@W4SED_ENHANCEMENTSENABLESTATE@@@Z`
- size: `703`
- prototype: `int __high(struct CAudioSignalProcessingModeArray *, enum SED_ENHANCEMENTSENABLESTATE)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180020bdc`
- `0x18002818c`
- `0x18003f6cc`
- `0x180142e98`

## callees

- `0x1800126bc`
- `0x180021f90`
- `0x1800281f8`
- `0x180028eb8`
- `0x1800b6fb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x1800282a9`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180028389`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x1800282a9`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180028389`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180028243`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180028243`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002822d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002822d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800284a9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800284a9`

## string_xrefs

- `0x180028451`: `avcore\audiocore\server\lib\audioserviceutil\systemeffect.cpp`

## pseudocode

```c

```
