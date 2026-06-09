# StsAttach::UploadAttachments(wchar_t const *,wchar_t const *,wchar_t const *,IMessage *,wchar_t const *,ICancelled *,_SPropValue *)

- ea: `0x1419d2540`
- end: `0x1419d3b5d`
- name: `?UploadAttachments@StsAttach@@QEAAJPEB_W00PEAUIMessage@@0PEAUICancelled@@PEAU_SPropValue@@@Z`
- size: `5661`
- prototype: `__int64 __fastcall(StsAttach *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, struct IMessage *, const wchar_t *, struct ICancelled *, struct _SPropValue *)`
- caller_count: `2`
- callee_count: `34`
- tags: `registry_config`

## callers

- `0x14199f2a0`
- `0x1419cb5bc`

## callees

- `0x14001fadc`
- `0x140046fec`
- `0x140047cfc`
- `0x14009db40`
- `0x1400dd630`
- `0x1400dd680`
- `0x1400dd710`
- `0x140103f1c`
- `0x14010a050`
- `0x14010ab1c`
- `0x14010af24`
- `0x1401ca3a0`
- `0x1401fb050`
- `0x14024b8a0`
- `0x14029f8d0`
- `0x140503f00`
- `0x140509800`
- `0x140718e20`
- `0x1407e99f0`
- `0x140c818cc`
- `0x140cac3f4`
- `0x14198a580`
- `0x14198a750`
- `0x14199ba44`
- `0x14199baf0`
- `0x14199c758`
- `0x14199d130`
- `0x1419d0ac0`
- `0x1419d1244`
- `0x1419d2540`
- `0x1419d47c4`
- `0x1419d4b3c`
- `0x1419d5060`
- `0x141d3d448`

## import_xrefs

- `KERNEL32!GetACP` at `0x1419d28a9`
- `KERNEL32!GetACP` at `0x1419d28a9`
- `OLMAPI32!HrCreateAttachConverter` at `0x1419d28bf`
- `OLMAPI32!HrCreateAttachConverter` at `0x1419d28bf`
- `OLMAPI32!CreateVirtualStream` at `0x1419d2d0c`
- `OLMAPI32!CreateVirtualStream` at `0x1419d2d0c`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d267a`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d2710`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d2c58`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d32b5`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d33e8`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d3460`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d3825`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d386c`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d267a`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d2710`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d2c58`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d32b5`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d33e8`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d3460`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d3825`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d386c`
- `OLMAPI32!__imp_HrQueryAllRows` at `0x1419d2795`
- `OLMAPI32!__imp_HrQueryAllRows` at `0x1419d2795`
- `OLMAPI32!__imp_FreeProws` at `0x1419d26cd`
- `OLMAPI32!__imp_FreeProws` at `0x1419d26cd`
- `ole32!WriteClassStg` at `0x1419d2dde`
- `ole32!WriteClassStg` at `0x1419d2dde`
- `MSO!__imp_?MsoFImportXML@@YAHPEAUIStream@@P6AHPEAXPEAU_MSOHISD@@PEAU_MSOXPS@@H@Z1PEB_W3H@Z` at `0x1419d2f6c`
- `MSO!__imp_?MsoFImportXML@@YAHPEAUIStream@@P6AHPEAXPEAU_MSOHISD@@PEAU_MSOXPS@@H@Z1PEB_W3H@Z` at `0x1419d39d5`
- `MSO!__imp_?MsoFImportXML@@YAHPEAUIStream@@P6AHPEAXPEAU_MSOHISD@@PEAU_MSOXPS@@H@Z1PEB_W3H@Z` at `0x1419d2f6c`
- `MSO!__imp_?MsoFImportXML@@YAHPEAUIStream@@P6AHPEAXPEAU_MSOHISD@@PEAU_MSOXPS@@H@Z1PEB_W3H@Z` at `0x1419d39d5`
- `Mso98Win32Client!__imp_?MsoFreeParserInstance@@YAXXZ` at `0x1419d2f8c`
- `Mso98Win32Client!__imp_?MsoFreeParserInstance@@YAXXZ` at `0x1419d39ea`
- `Mso98Win32Client!__imp_?MsoFreeParserInstance@@YAXXZ` at `0x1419d3b0b`
- `Mso98Win32Client!__imp_?MsoFreeParserInstance@@YAXXZ` at `0x1419d2f8c`
- `Mso98Win32Client!__imp_?MsoFreeParserInstance@@YAXXZ` at `0x1419d39ea`
- `Mso98Win32Client!__imp_?MsoFreeParserInstance@@YAXXZ` at `0x1419d3b0b`
- `Mso98Win32Client!__imp_?MsoFNewParserInstance@@YAHXZ` at `0x1419d2f16`
- `Mso98Win32Client!__imp_?MsoFNewParserInstance@@YAHXZ` at `0x1419d3974`
- `Mso98Win32Client!__imp_?MsoFNewParserInstance@@YAHXZ` at `0x1419d2f16`
- `Mso98Win32Client!__imp_?MsoFNewParserInstance@@YAHXZ` at `0x1419d3974`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1419d2c05`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1419d2c05`
- `Mso20Win32Client!__imp_?MsoEmptyPx@@YAXPEAX@Z` at `0x1419d2687`
- `Mso20Win32Client!__imp_?MsoEmptyPx@@YAXPEAX@Z` at `0x1419d3b01`
- `Mso20Win32Client!__imp_?MsoEmptyPx@@YAXPEAX@Z` at `0x1419d2687`
- `Mso20Win32Client!__imp_?MsoEmptyPx@@YAXPEAX@Z` at `0x1419d3b01`
- `Mso20Win32Client!__imp_?MsoFRemovePx@@YAHPEAXII@Z` at `0x1419d2c3c`
- `Mso20Win32Client!__imp_?MsoFRemovePx@@YAHPEAXII@Z` at `0x1419d2c3c`
- `Mso20Win32Client!__imp_MsoFInitPxCore` at `0x1419d265d`
- `Mso20Win32Client!__imp_MsoFInitPxCore` at `0x1419d265d`
- `Mso20Win32Client!__imp_?MsoIAppendPx@@YAHPEAXPEBX@Z` at `0x1419d2bac`
- `Mso20Win32Client!__imp_?MsoIAppendPx@@YAHPEAXPEBX@Z` at `0x1419d2bac`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1419d2c73`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1419d355d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1419d2c73`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1419d355d`

## string_xrefs

- `0x1419d39a0`: `DeleteAttachmentResponse`
- `0x1419d39c0`: `n q;o Envelope;o Body;(|(o Fault;n ;e0 faultcode;e1 faultstring;p1;o detail;n sps;e?0 errorstring;e?1 errorcode;p2;n c;c;)(n sps;e DeleteAttachmentResponse;p0;))c;c;f;`

## pseudocode

```c

```
