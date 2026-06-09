# CTemplateCacheManager::FlushFiles(ushort const *)

- ea: `0x18003456c`
- end: `0x1800346e2`
- name: `?FlushFiles@CTemplateCacheManager@@QEAAXPEBG@Z`
- size: `374`
- prototype: `void(CTemplateCacheManager *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180063788`

## callees

- `0x1800134f0`
- `0x180019f44`
- `0x18001a600`
- `0x18001a768`
- `0x180023daa`
- `0x18003456c`
- `0x180064010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800346c0`
- `KERNEL32!LeaveCriticalSection` at `0x1800346c0`
- `KERNEL32!LeaveCriticalSection` at `0x1800346db`
- `KERNEL32!EnterCriticalSection` at `0x180034585`
- `KERNEL32!EnterCriticalSection` at `0x180034592`
- `KERNEL32!EnterCriticalSection` at `0x180034585`
- `KERNEL32!EnterCriticalSection` at `0x180034592`
- `iisutil!PuDbgPrint` at `0x180034629`
- `iisutil!PuDbgPrint` at `0x180034629`

## string_xrefs

- `0x180034622`: `inetsrv\iis\svcs\cmp\asp\cachemgr.cpp`
- `0x180034610`: `CTemplateCacheManager::FlushFiles`

## pseudocode

```c

```
