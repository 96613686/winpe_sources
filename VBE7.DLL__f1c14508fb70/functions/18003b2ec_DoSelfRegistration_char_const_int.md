# _DoSelfRegistration(char const *,int)

- ea: `0x18003b2ec`
- end: `0x18003b5ba`
- name: `?_DoSelfRegistration@@YAHPEBDH@Z`
- size: `718`
- prototype: `__int64 __fastcall(const char *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18003b5c0`

## callees

- `0x180019278`
- `0x180028468`
- `0x18003acb4`
- `0x18003b2ec`
- `0x180051e5c`
- `0x18005633c`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!strcpy_s` at `0x18003b3d8`
- `MSVCR100!strcpy_s` at `0x18003b42b`
- `MSVCR100!strcpy_s` at `0x18003b3d8`
- `MSVCR100!strcpy_s` at `0x18003b42b`
- `MSVCR100!free` at `0x18003b3b7`
- `MSVCR100!free` at `0x18003b4a2`
- `MSVCR100!free` at `0x18003b3b7`
- `MSVCR100!free` at `0x18003b4a2`
- `MSVCR100!malloc` at `0x18003b386`
- `MSVCR100!malloc` at `0x18003b386`
- `KERNEL32!lstrcpyA` at `0x18003b552`
- `KERNEL32!lstrcpyA` at `0x18003b552`
- `KERNEL32!lstrcatA` at `0x18003b575`
- `KERNEL32!lstrcatA` at `0x18003b575`
- `KERNEL32!FreeLibrary` at `0x18003b50b`
- `KERNEL32!FreeLibrary` at `0x18003b528`
- `KERNEL32!FreeLibrary` at `0x18003b50b`
- `KERNEL32!FreeLibrary` at `0x18003b528`
- `KERNEL32!GetProcAddress` at `0x18003b4ed`
- `KERNEL32!GetProcAddress` at `0x18003b4ed`
- `USER32!wsprintfA` at `0x18003b474`
- `USER32!wsprintfA` at `0x18003b474`

## string_xrefs

- `0x18003b4d5`: `DllRegisterServer`
- `0x18003b4dc`: `DllUnregisterServer`

## pseudocode

```c

```
