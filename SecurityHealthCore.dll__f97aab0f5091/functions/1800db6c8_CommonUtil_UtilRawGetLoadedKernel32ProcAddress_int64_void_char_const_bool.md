# CommonUtil::UtilRawGetLoadedKernel32ProcAddress(__int64 (**)(void),char const *,bool)

- ea: `0x1800db6c8`
- end: `0x1800db7ac`
- name: `?UtilRawGetLoadedKernel32ProcAddress@CommonUtil@@YAJPEAP6A_JXZPEBD_N@Z`
- size: `228`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, __int64 (**)(void), const char *, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800e0598`

## callees

- `0x1800db304`
- `0x1800db6c8`
- `0x1800db864`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800db761`
- `KERNEL32!FreeLibrary` at `0x1800db77a`
- `KERNEL32!FreeLibrary` at `0x1800db794`
- `KERNEL32!FreeLibrary` at `0x1800db761`
- `KERNEL32!FreeLibrary` at `0x1800db77a`
- `KERNEL32!FreeLibrary` at `0x1800db794`

## string_xrefs

- `0x1800db6ea`: `kernelbase.dll`
- `0x1800db6dc`: `kernel32.dll`

## pseudocode

```c

```
