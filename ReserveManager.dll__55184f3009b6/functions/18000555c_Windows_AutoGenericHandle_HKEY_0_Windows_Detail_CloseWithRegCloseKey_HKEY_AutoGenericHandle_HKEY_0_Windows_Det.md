# Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(void)

- ea: `0x18000555c`
- end: `0x1800055a3`
- name: `??1?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@QEAA@XZ`
- size: `71`
- prototype: `void __fastcall(HKEY *)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800177f8`
- `0x180032385`
- `0x1800324ff`
- `0x180032732`
- `0x180032744`
- `0x180032aad`
- `0x180032ba6`

## callees

- `0x18000555c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005589`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000557f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000557f`

## pseudocode

```c

```
