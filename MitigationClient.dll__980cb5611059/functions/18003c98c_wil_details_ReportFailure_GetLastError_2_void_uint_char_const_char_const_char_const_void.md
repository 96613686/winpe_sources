# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18003c98c`
- end: `0x18003ca2f`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `163`
- prototype: `__int64 __fastcall(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x18003d304`

## callees

- `0x18000d35c`
- `0x18000fda0`
- `0x180010398`
- `0x18003c98c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ca17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ca17`

## string_xrefs

- `0x18003c9a3`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\privilegedaction.cpp`
- `0x18003c9de`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\privilegedaction.cpp`

## pseudocode

```c

```
