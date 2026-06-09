# DoHangDetection(CIsapiReqInfo *,ulong)

- ea: `0x180007e20`
- end: `0x180007e99`
- name: `?DoHangDetection@@YAXPEAVCIsapiReqInfo@@K@Z`
- size: `121`
- prototype: `void __fastcall(struct CIsapiReqInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000bcb0`

## callees

- `0x18000243c`
- `0x180007e20`
- `0x180019e7c`
- `0x180023dd0`
- `0x18003e364`
- `0x18003ead0`
- `0x180064010`

## import_xrefs

- `msvcrt!sprintf_s` at `0x180026c10`
- `msvcrt!sprintf_s` at `0x180026c10`
- `msvcrt!strcpy_s` at `0x180026bf1`
- `msvcrt!strcpy_s` at `0x180026bf1`
- `iisutil!PuDbgPrint` at `0x180026a73`
- `iisutil!PuDbgPrint` at `0x180026ad1`
- `iisutil!PuDbgPrint` at `0x180026b3b`
- `iisutil!PuDbgPrint` at `0x180026bc1`
- `iisutil!PuDbgPrint` at `0x180026c75`
- `iisutil!PuDbgPrint` at `0x180026a73`
- `iisutil!PuDbgPrint` at `0x180026ad1`
- `iisutil!PuDbgPrint` at `0x180026b3b`
- `iisutil!PuDbgPrint` at `0x180026bc1`
- `iisutil!PuDbgPrint` at `0x180026c75`

## string_xrefs

- `0x180026a67`: `DoHangDetection: Request Thread Hit.  Percent Hung Threads is %d (%d of %d)\n`
- `0x180026b2f`: `DoHangDetection: Exceeded combined threshold.  Incrementing ConsecIllStates (%d)\n`

## pseudocode

```c

```
