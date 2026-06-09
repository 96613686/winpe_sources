# GetRegistryKeyValue(HKEY__ *,CxString const &,CxString &)

- ea: `0x183068fb0`
- end: `0x1830690ef`
- name: `?GetRegistryKeyValue@@YA_NPEAUHKEY__@@AEBVCxString@@AEAV2@@Z`
- size: `319`
- prototype: `bool __fastcall(HKEY hkey, const struct CxString *this, struct CxString *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1830691e0`

## callees

- `0x183052e40`
- `0x183052ed0`
- `0x183053010`
- `0x183053170`
- `0x183055940`
- `0x1830566f0`
- `0x183068fb0`
- `0x1832ce3b0`

## import_xrefs

- `ADVAPI32!RegGetValueA` at `0x18306903e`
- `ADVAPI32!RegGetValueA` at `0x183069092`
- `ADVAPI32!RegGetValueA` at `0x18306903e`
- `ADVAPI32!RegGetValueA` at `0x183069092`

## pseudocode

```c

```
