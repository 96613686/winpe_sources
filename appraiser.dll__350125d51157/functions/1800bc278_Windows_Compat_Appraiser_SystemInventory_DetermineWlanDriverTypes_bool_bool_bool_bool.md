# Windows::Compat::Appraiser::SystemInventory::DetermineWlanDriverTypes(bool &,bool &,bool &,bool &)

- ea: `0x1800bc278`
- end: `0x1800bc5a1`
- name: `?DetermineWlanDriverTypes@SystemInventory@Appraiser@Compat@Windows@@CAJAEA_N000@Z`
- size: `809`
- prototype: `__int64 __fastcall(bool *, bool *, bool *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800bbf1c`

## callees

- `0x1800301d0`
- `0x1800bc278`
- `0x18021f010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800bc2c6`
- `KERNEL32!LoadLibraryExW` at `0x1800bc2c6`
- `KERNEL32!FreeLibrary` at `0x1800bc588`
- `KERNEL32!FreeLibrary` at `0x1800bc588`
- `KERNEL32!GetProcAddress` at `0x1800bc2ee`
- `KERNEL32!GetProcAddress` at `0x1800bc302`
- `KERNEL32!GetProcAddress` at `0x1800bc315`
- `KERNEL32!GetProcAddress` at `0x1800bc329`
- `KERNEL32!GetProcAddress` at `0x1800bc33c`
- `KERNEL32!GetProcAddress` at `0x1800bc2ee`
- `KERNEL32!GetProcAddress` at `0x1800bc302`
- `KERNEL32!GetProcAddress` at `0x1800bc315`
- `KERNEL32!GetProcAddress` at `0x1800bc329`
- `KERNEL32!GetProcAddress` at `0x1800bc33c`

## string_xrefs

- `0x1800bc3fa`: `onecore\base\appcompat\appraiser\inventory\systeminventory.cpp`
- `0x1800bc50b`: `onecore\base\appcompat\appraiser\inventory\systeminventory.cpp`
- `0x1800bc542`: `onecore\base\appcompat\appraiser\inventory\systeminventory.cpp`
- `0x1800bc2ac`: `wlanapi.dll`
- `0x1800bc2e1`: `WlanOpenHandle`
- `0x1800bc401`: `Windows::Compat::Appraiser::SystemInventory::DetermineWlanDriverTypes`
- `0x1800bc4e5`: `Windows::Compat::Appraiser::SystemInventory::DetermineWlanDriverTypes`
- `0x1800bc53b`: `Windows::Compat::Appraiser::SystemInventory::DetermineWlanDriverTypes`
- `0x1800bc52a`: `Corrupt wlanapi dll.`

## pseudocode

```c

```
