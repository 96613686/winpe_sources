# CDdeObject::PostSysCommand(DDE_CHANNEL *,char const *,int,int)

- ea: `0x180076c28`
- end: `0x180076dde`
- name: `?PostSysCommand@CDdeObject@@AEAAJPEAVDDE_CHANNEL@@PEBDHH@Z`
- size: `438`
- prototype: `HRESULT __fastcall(CDdeObject *this, DDE_CHANNEL *szCmd, const char *fStdNew, int fWait, int pChannel)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004c74c`
- `0x1800748e0`
- `0x180078a80`
- `0x180078b70`

## callees

- `0x180075e64`
- `0x180076c28`
- `0x180077280`
- `0x180077300`
- `0x180077870`
- `0x1800c4609`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x180076c89`
- `KERNELBASE!GlobalAlloc` at `0x180076c89`
- `KERNELBASE!GlobalFree` at `0x180076cb5`
- `KERNELBASE!GlobalFree` at `0x180076cb5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180076d97`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180076dd1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180076d97`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180076dd1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180076ca4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180076ca4`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameA` at `0x180076d2a`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameA` at `0x180076d6a`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameA` at `0x180076d2a`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameA` at `0x180076d6a`

## pseudocode

```c

```
