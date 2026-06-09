# CReportStore::DeleteReportFromStore(wchar_t const *,REPORT_DELETE_REASON,CReport *)

- ea: `0x18001a60c`
- end: `0x18001aa82`
- name: `?DeleteReportFromStore@CReportStore@@QEAAJPEB_WW4REPORT_DELETE_REASON@@PEAVCReport@@@Z`
- size: `1142`
- prototype: `int __high(const wchar_t *, enum REPORT_DELETE_REASON, struct CReport *)`
- caller_count: `4`
- callee_count: `25`
- tags: `loader_planting`

## callers

- `0x180019e10`
- `0x1800674f0`
- `0x180067af0`
- `0x18006ad60`

## callees

- `0x180006c34`
- `0x1800077a4`
- `0x180007f7c`
- `0x18000bc10`
- `0x18000bc48`
- `0x18000c390`
- `0x18000dad0`
- `0x18001a60c`
- `0x18001aa88`
- `0x18001abd8`
- `0x18001fe24`
- `0x180021634`
- `0x180026498`
- `0x18002c16c`
- `0x18002ffc4`
- `0x18003db78`
- `0x180040128`
- `0x18004057c`
- `0x180045bdc`
- `0x18004afac`
- `0x180051f50`
- `0x180070f3c`
- `0x1800722f0`
- `0x1800739c0`
- `0x1800a4990`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a9ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aa0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aa29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a9ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aa0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aa29`
- `ext-ms-win-wer-xbox-l1-2-1!XerCleanupInternalFile` at `0x18001a7da`
- `ext-ms-win-wer-xbox-l1-2-1!XerCleanupInternalFile` at `0x18001a7da`

## string_xrefs

- `0x18001a674`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18001a69e`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`

## pseudocode

```c

```
