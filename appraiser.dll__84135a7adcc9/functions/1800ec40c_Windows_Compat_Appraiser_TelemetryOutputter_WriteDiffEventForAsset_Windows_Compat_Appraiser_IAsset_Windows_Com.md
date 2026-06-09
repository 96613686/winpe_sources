# Windows::Compat::Appraiser::TelemetryOutputter::WriteDiffEventForAsset(Windows::Compat::Appraiser::IAsset *,Windows::Compat::Appraiser::IAsset *,Windows::Compat::Appraiser::TelemetryEventInformation *,unsigned __int64)

- ea: `0x1800ec40c`
- end: `0x1800ecc59`
- name: `?WriteDiffEventForAsset@TelemetryOutputter@Appraiser@Compat@Windows@@AEAAXPEAVIAsset@234@0PEAUTelemetryEventInformation@234@_K@Z`
- size: `2125`
- prototype: `void(Windows::Compat::Appraiser::TelemetryOutputter *__hidden this, struct Windows::Compat::Appraiser::IAsset *, struct Windows::Compat::Appraiser::IAsset *, struct Windows::Compat::Appraiser::TelemetryEventInformation *, unsigned __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800ebe6c`

## callees

- `0x18000147c`
- `0x180008570`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800a5d88`
- `0x1800a88a0`
- `0x1800ad88c`
- `0x1800e601c`
- `0x1800e6590`
- `0x1800e90ec`
- `0x1800e975c`
- `0x1800ec40c`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1800ec817`
- `KERNEL32!GetSystemTime` at `0x1800ecae0`
- `KERNEL32!GetSystemTime` at `0x1800ec817`
- `KERNEL32!GetSystemTime` at `0x1800ecae0`
- `KERNEL32!GetProcessHeap` at `0x1800ec468`
- `KERNEL32!GetProcessHeap` at `0x1800ec885`
- `KERNEL32!GetProcessHeap` at `0x1800ecbc5`
- `KERNEL32!GetProcessHeap` at `0x1800ecc0d`
- `KERNEL32!GetProcessHeap` at `0x1800ec468`
- `KERNEL32!GetProcessHeap` at `0x1800ec885`
- `KERNEL32!GetProcessHeap` at `0x1800ecbc5`
- `KERNEL32!GetProcessHeap` at `0x1800ecc0d`
- `KERNEL32!HeapAlloc` at `0x1800ec897`
- `KERNEL32!HeapAlloc` at `0x1800ec897`
- `KERNEL32!HeapFree` at `0x1800ecbd3`
- `KERNEL32!HeapFree` at `0x1800ecc1b`
- `KERNEL32!HeapFree` at `0x1800ecc30`
- `KERNEL32!HeapFree` at `0x1800ecbd3`
- `KERNEL32!HeapFree` at `0x1800ecc1b`
- `KERNEL32!HeapFree` at `0x1800ecc30`

## string_xrefs

- `0x1800ec4c3`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800ec538`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800ec4ca`: `Windows::Compat::Appraiser::TelemetryOutputter::WriteDiffEventForAsset`
- `0x1800ec531`: `Windows::Compat::Appraiser::TelemetryOutputter::WriteDiffEventForAsset`
- `0x1800ec4bc`: `Attempted to write diff against the same asset.`
- `0x1800ec5db`: `Failed to Compare previous and current Assets: [0x%x].`
- `0x1800ec613`: `Failed to Compare previous and current Assets: [0x%x].`

## pseudocode

```c

```
