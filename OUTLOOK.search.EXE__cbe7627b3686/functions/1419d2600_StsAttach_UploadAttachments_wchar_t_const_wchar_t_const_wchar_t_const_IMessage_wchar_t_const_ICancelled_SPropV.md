# StsAttach::UploadAttachments(wchar_t const *,wchar_t const *,wchar_t const *,IMessage *,wchar_t const *,ICancelled *,_SPropValue *)

- ea: `0x1419d2600`
- end: `0x1419d3c1d`
- name: `?UploadAttachments@StsAttach@@QEAAJPEB_W00PEAUIMessage@@0PEAUICancelled@@PEAU_SPropValue@@@Z`
- size: `5661`
- prototype: `__int64 __fastcall(StsAttach *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, struct IMessage *, const wchar_t *, struct ICancelled *, struct _SPropValue *)`
- caller_count: `2`
- callee_count: `34`
- tags: `registry_config`

## callers

- `0x14199f360`
- `0x1419cb67c`

## callees

- `0x14001fadc`
- `0x140046fec`
- `0x140047cfc`
- `0x14009db40`
- `0x1400dd620`
- `0x1400dd670`
- `0x1400dd700`
- `0x140103fac`
- `0x14010a0e0`
- `0x14010abac`
- `0x14010afb4`
- `0x1401ca3c0`
- `0x1401fb830`
- `0x14024c080`
- `0x1402a0170`
- `0x1405049f0`
- `0x14050a2e0`
- `0x140723160`
- `0x1407e9990`
- `0x140c8197c`
- `0x140cac4a4`
- `0x14198a640`
- `0x14198a810`
- `0x14199bb04`
- `0x14199bbb0`
- `0x14199c818`
- `0x14199d1f0`
- `0x1419d0b80`
- `0x1419d1304`
- `0x1419d2600`
- `0x1419d4884`
- `0x1419d4bfc`
- `0x1419d5120`
- `0x141d3d508`

## import_xrefs

- `KERNEL32!GetACP` at `0x1419d2969`
- `KERNEL32!GetACP` at `0x1419d2969`
- `OLMAPI32!HrCreateAttachConverter` at `0x1419d297f`
- `OLMAPI32!HrCreateAttachConverter` at `0x1419d297f`
- `OLMAPI32!CreateVirtualStream` at `0x1419d2dcc`
- `OLMAPI32!CreateVirtualStream` at `0x1419d2dcc`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d273a`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d27d0`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d2d18`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d3375`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d34a8`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d3520`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d38e5`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d392c`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d273a`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d27d0`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d2d18`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d3375`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d34a8`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d3520`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d38e5`
- `OLMAPI32!EtwTraceErrorTag` at `0x1419d392c`
- `OLMAPI32!__imp_HrQueryAllRows` at `0x1419d2855`
- `OLMAPI32!__imp_HrQueryAllRows` at `0x1419d2855`
- `OLMAPI32!__imp_FreeProws` at `0x1419d278d`
- `OLMAPI32!__imp_FreeProws` at `0x1419d278d`
- `ole32!WriteClassStg` at `0x1419d2e9e`
- `ole32!WriteClassStg` at `0x1419d2e9e`
- `MSO!__imp_?MsoFImportXML@@YAHPEAUIStream@@P6AHPEAXPEAU_MSOHISD@@PEAU_MSOXPS@@H@Z1PEB_W3H@Z` at `0x1419d302c`
- `MSO!__imp_?MsoFImportXML@@YAHPEAUIStream@@P6AHPEAXPEAU_MSOHISD@@PEAU_MSOXPS@@H@Z1PEB_W3H@Z` at `0x1419d3a95`
- `MSO!__imp_?MsoFImportXML@@YAHPEAUIStream@@P6AHPEAXPEAU_MSOHISD@@PEAU_MSOXPS@@H@Z1PEB_W3H@Z` at `0x1419d302c`
- `MSO!__imp_?MsoFImportXML@@YAHPEAUIStream@@P6AHPEAXPEAU_MSOHISD@@PEAU_MSOXPS@@H@Z1PEB_W3H@Z` at `0x1419d3a95`
- `Mso98Win32Client!__imp_?MsoFreeParserInstance@@YAXXZ` at `0x1419d304c`
- `Mso98Win32Client!__imp_?MsoFreeParserInstance@@YAXXZ` at `0x1419d3aaa`
- `Mso98Win32Client!__imp_?MsoFreeParserInstance@@YAXXZ` at `0x1419d3bcb`
- `Mso98Win32Client!__imp_?MsoFreeParserInstance@@YAXXZ` at `0x1419d304c`
- `Mso98Win32Client!__imp_?MsoFreeParserInstance@@YAXXZ` at `0x1419d3aaa`
- `Mso98Win32Client!__imp_?MsoFreeParserInstance@@YAXXZ` at `0x1419d3bcb`
- `Mso98Win32Client!__imp_?MsoFNewParserInstance@@YAHXZ` at `0x1419d2fd6`
- `Mso98Win32Client!__imp_?MsoFNewParserInstance@@YAHXZ` at `0x1419d3a34`
- `Mso98Win32Client!__imp_?MsoFNewParserInstance@@YAHXZ` at `0x1419d2fd6`
- `Mso98Win32Client!__imp_?MsoFNewParserInstance@@YAHXZ` at `0x1419d3a34`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1419d2cc5`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1419d2cc5`
- `Mso20Win32Client!__imp_?MsoEmptyPx@@YAXPEAX@Z` at `0x1419d2747`
- `Mso20Win32Client!__imp_?MsoEmptyPx@@YAXPEAX@Z` at `0x1419d3bc1`
- `Mso20Win32Client!__imp_?MsoEmptyPx@@YAXPEAX@Z` at `0x1419d2747`
- `Mso20Win32Client!__imp_?MsoEmptyPx@@YAXPEAX@Z` at `0x1419d3bc1`
- `Mso20Win32Client!__imp_?MsoFRemovePx@@YAHPEAXII@Z` at `0x1419d2cfc`
- `Mso20Win32Client!__imp_?MsoFRemovePx@@YAHPEAXII@Z` at `0x1419d2cfc`
- `Mso20Win32Client!__imp_MsoFInitPxCore` at `0x1419d271d`
- `Mso20Win32Client!__imp_MsoFInitPxCore` at `0x1419d271d`
- `Mso20Win32Client!__imp_?MsoIAppendPx@@YAHPEAXPEBX@Z` at `0x1419d2c6c`
- `Mso20Win32Client!__imp_?MsoIAppendPx@@YAHPEAXPEBX@Z` at `0x1419d2c6c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1419d2d33`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1419d361d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1419d2d33`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1419d361d`

## string_xrefs

- `0x1419d3a60`: `DeleteAttachmentResponse`
- `0x1419d3a80`: `n q;o Envelope;o Body;(|(o Fault;n ;e0 faultcode;e1 faultstring;p1;o detail;n sps;e?0 errorstring;e?1 errorcode;p2;n c;c;)(n sps;e DeleteAttachmentResponse;p0;))c;c;f;`

## pseudocode

```c

```
