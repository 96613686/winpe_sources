# ThreadedMapiTable::GetConvRowFromObject(TableId,ulong,IOlkObjectData *)

- ea: `0x1408164d8`
- end: `0x1408177ca`
- name: `?GetConvRowFromObject@ThreadedMapiTable@@IEAA?AV?$shared_ptr@VConvRow@@@std@@W4TableId@@KPEAUIOlkObjectData@@@Z`
- size: `4850`
- prototype: `__int64 __usercall@<rax>(ThreadedMapiTable *this@<rcx>, struct IOlkObjectData *)`
- caller_count: `5`
- callee_count: `38`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14081528c`
- `0x140b704cc`
- `0x1419f06bc`
- `0x1419f1014`
- `0x1419f146c`

## callees

- `0x14002ba90`
- `0x140031848`
- `0x140031890`
- `0x14003a974`
- `0x14003f988`
- `0x14005cd9c`
- `0x14005d09c`
- `0x1400dd630`
- `0x140105998`
- `0x1401723a8`
- `0x1401bf5e8`
- `0x1404479f0`
- `0x140572640`
- `0x1405ed270`
- `0x1405edcf4`
- `0x1405f33a0`
- `0x1405f6ee0`
- `0x140602300`
- `0x14060d058`
- `0x14060e5b8`
- `0x1406225c8`
- `0x1407e99f0`
- `0x1407eb010`
- `0x1408164b4`
- `0x1408164d8`
- `0x140818a48`
- `0x140877cc0`
- `0x1409954d0`
- `0x140995a5c`
- `0x1409bac2c`
- `0x140a3db7c`
- `0x140a3dccc`
- `0x140c40ee8`
- `0x140cabe48`
- `0x140cad47c`
- `0x140cbb5b0`
- `0x140d0e328`
- `0x140d0e778`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14081778f`
- `KERNEL32!LeaveCriticalSection` at `0x14081778f`
- `OLMAPI32!FIsFeatureEnabled` at `0x140817688`
- `OLMAPI32!FIsFeatureEnabled` at `0x140817688`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816524`
- `OLMAPI32!EtwTraceErrorTag` at `0x14081655e`
- `OLMAPI32!EtwTraceErrorTag` at `0x1408165e9`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816685`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816739`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816966`
- `OLMAPI32!EtwTraceErrorTag` at `0x1408169f6`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816a41`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816ab5`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816b1d`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816b67`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816bcd`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816d1a`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816d5f`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816db2`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816e04`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816eb2`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816f1c`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816f64`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816fb4`
- `OLMAPI32!EtwTraceErrorTag` at `0x140817002`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816524`
- `OLMAPI32!EtwTraceErrorTag` at `0x14081655e`
- `OLMAPI32!EtwTraceErrorTag` at `0x1408165e9`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816685`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816739`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816966`
- `OLMAPI32!EtwTraceErrorTag` at `0x1408169f6`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816a41`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816ab5`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816b1d`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816b67`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816bcd`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816d1a`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816d5f`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816db2`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816e04`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816eb2`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816f1c`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816f64`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816fb4`
- `OLMAPI32!EtwTraceErrorTag` at `0x140817002`
- `OLEAUT32!__imp_SysFreeString` at `0x14081771d`
- `OLEAUT32!__imp_SysFreeString` at `0x14081772c`
- `OLEAUT32!__imp_SysFreeString` at `0x14081771d`
- `OLEAUT32!__imp_SysFreeString` at `0x14081772c`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x14081719f`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408171b5`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408171db`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408171ff`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x140817215`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x14081723f`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408172f8`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x14081730e`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x14081719f`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408171b5`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408171db`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408171ff`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x140817215`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x14081723f`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408172f8`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x14081730e`
- `Mso30Win32Client!__imp_MsoFRgwchEqual` at `0x14081728d`
- `Mso30Win32Client!__imp_MsoFRgwchEqual` at `0x1408172d2`
- `Mso30Win32Client!__imp_MsoFRgwchEqual` at `0x14081728d`
- `Mso30Win32Client!__imp_MsoFRgwchEqual` at `0x1408172d2`

## string_xrefs

- `0x1408171d4`: `IPM.TaskRequest`
- `0x1408171f8`: `IPM.Note.Rules.OofTemplate.Microsoft`
- `0x140816fba`: `timeValue->SetFILETIME(ftZero)`
- `0x140816f22`: `sortField->GetEmptyValue(&sortValue)`
- `0x140816a47`: `container->GetRegistry(&unwrappedRegistry)`

## pseudocode

```c

```
