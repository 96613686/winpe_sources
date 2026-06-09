# NgcUtils::ConvertPrivateBlobToRsaFullKey(std::vector<uchar,wil::secure_allocator<uchar>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_BCryptBufferDesc const *,ulong,std::unique_ptr<NgcUtils::RsaKey,std::default_delete<NgcUtils::RsaKey>> *)

- ea: `0x180044e40`
- end: `0x180045264`
- name: `?ConvertPrivateBlobToRsaFullKey@NgcUtils@@YAJAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@PEBU_BCryptBufferDesc@@KPEAV?$unique_ptr@URsaKey@NgcUtils@@U?$default_delete@URsaKey@NgcUtils@@@std@@@3@@Z`
- size: `1060`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18003f230`
- `0x180067a10`

## callees

- `0x180010a94`
- `0x180011c04`
- `0x180016280`
- `0x180022928`
- `0x180028d18`
- `0x180031090`
- `0x180044e40`
- `0x18005348c`
- `0x18005d2ec`
- `0x180068b78`
- `0x180089cbc`

## import_xrefs

- `ncrypt!NCryptExportKey` at `0x18004505e`
- `ncrypt!NCryptExportKey` at `0x1800450c1`
- `ncrypt!NCryptExportKey` at `0x18004505e`
- `ncrypt!NCryptExportKey` at `0x1800450c1`
- `ncrypt!NCryptSetProperty` at `0x180044fe4`
- `ncrypt!NCryptSetProperty` at `0x180044fe4`
- `ncrypt!NCryptImportKey` at `0x180044f7d`
- `ncrypt!NCryptImportKey` at `0x180044f7d`
- `ncrypt!NCryptOpenStorageProvider` at `0x180044edf`
- `ncrypt!NCryptOpenStorageProvider` at `0x180044edf`
- `ncrypt!NCryptGetProperty` at `0x1800451b7`
- `ncrypt!NCryptGetProperty` at `0x1800451b7`
- `ncrypt!NCryptFinalizeKey` at `0x18004500e`
- `ncrypt!NCryptFinalizeKey` at `0x18004500e`

## pseudocode

```c

```
