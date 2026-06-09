# AddDriverToFilters(ushort const *,ushort const *,_GUID const *,EFilterLocation)

- ea: `0x14006dcf0`
- end: `0x14006dfab`
- name: `?AddDriverToFilters@@YAJPEBG0PEBU_GUID@@W4EFilterLocation@@@Z`
- size: `699`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY, const GUID *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14006e19c`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140061134`
- `0x140061ce4`
- `0x14006dcf0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14006df94`
- `ADVAPI32!RegCloseKey` at `0x14006df94`
- `KERNEL32!GetLastError` at `0x14006de03`
- `KERNEL32!GetLastError` at `0x14006de03`
- `KERNEL32!IsDebuggerPresent` at `0x14006dd57`
- `KERNEL32!IsDebuggerPresent` at `0x14006de5e`
- `KERNEL32!IsDebuggerPresent` at `0x14006df11`
- `KERNEL32!IsDebuggerPresent` at `0x14006dd57`
- `KERNEL32!IsDebuggerPresent` at `0x14006de5e`
- `KERNEL32!IsDebuggerPresent` at `0x14006df11`
- `SETUPAPI!SetupDiOpenClassRegKey` at `0x14006ddf0`
- `SETUPAPI!SetupDiOpenClassRegKey` at `0x14006ddf0`

## string_xrefs

- `0x14006dd37`: `termsrv\wms\src\common\srcutils\srcdriverinstaller.cpp`
- `0x14006de33`: `termsrv\wms\src\common\srcutils\srcdriverinstaller.cpp`
- `0x14006deed`: `termsrv\wms\src\common\srcutils\srcdriverinstaller.cpp`

## pseudocode

```c

```
