# RichTextServices::LineServicesGetGlyphs(Ptls6::ols *,Ptls6::lsrun * const *,long const *,long,ushort const *,long,ulong,ushort *,ushort *,int *,ushort * *,ulong * *,long *)

- ea: `0x18044f580`
- end: `0x18044fa83`
- name: `?LineServicesGetGlyphs@RichTextServices@@YAJPEAUols@Ptls6@@PEBQEAUlsrun@3@PEBJJPEBGJKPEAG4PEAHPEAPEAGPEAPEAKPEAJ@Z`
- size: `1283`
- prototype: `int __fastcall(struct Ptls6::ols *pols, Ptls6::lsrun *const *rgplsrun, const int *rgdwchRun, int crun, const wchar_t *rgwch, int cwch, unsigned int lstflow, unsigned __int16 *rggmap, unsigned __int16 *rgchprop, int *rgfCanGlyphAlone, unsigned __int16 **prggindex, unsigned int **prggprop, int *pcgindex)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task`

## callees

- `0x180004bc0`
- `0x18001c368`
- `0x1800ab600`
- `0x1800fe130`
- `0x180131190`
- `0x1803b0858`
- `0x18044f580`
- `0x18044fa8c`
- `0x18044fe08`
- `0x1806877a8`
- `0x180687890`
- `0x18076e134`
- `0x18076f08c`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18044fa71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18044fa71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18044f80f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18044f80f`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x18044f92b`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x18044f92b`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18044f6ef`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18044f6ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18044f6a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18044f6a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18044f9ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18044fa0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18044f9ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18044fa0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18044f705`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18044f705`

## pseudocode

```c

```
