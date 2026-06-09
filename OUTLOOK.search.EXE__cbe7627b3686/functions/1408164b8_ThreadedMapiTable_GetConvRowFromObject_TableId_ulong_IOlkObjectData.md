# ThreadedMapiTable::GetConvRowFromObject(TableId,ulong,IOlkObjectData *)

- ea: `0x1408164b8`
- end: `0x1408177aa`
- name: `?GetConvRowFromObject@ThreadedMapiTable@@IEAA?AV?$shared_ptr@VConvRow@@@std@@W4TableId@@KPEAUIOlkObjectData@@@Z`
- size: `4850`
- prototype: `__int64 __usercall@<rax>(ThreadedMapiTable *this@<rcx>, struct IOlkObjectData *)`
- caller_count: `5`
- callee_count: `38`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14081526c`
- `0x140b7058c`
- `0x1419f077c`
- `0x1419f10d4`
- `0x1419f152c`

## callees

- `0x14002ba90`
- `0x140031848`
- `0x140031890`
- `0x14003a974`
- `0x14003f988`
- `0x14005cd5c`
- `0x14005d05c`
- `0x1400dd620`
- `0x140105a28`
- `0x1401723e8`
- `0x1401bf608`
- `0x140448410`
- `0x140573750`
- `0x1405ec5d0`
- `0x1405f7d90`
- `0x1405f8814`
- `0x1405fdaf0`
- `0x140600550`
- `0x14060b2a8`
- `0x14060c808`
- `0x1406765b8`
- `0x1407e9990`
- `0x1407eafb0`
- `0x140816494`
- `0x1408164b8`
- `0x140818a28`
- `0x140877cb0`
- `0x140995620`
- `0x140995bac`
- `0x1409bad7c`
- `0x140a3dcac`
- `0x140a3ddfc`
- `0x140c40f98`
- `0x140cabef8`
- `0x140cad52c`
- `0x140cbb660`
- `0x140d0e3d8`
- `0x140d0e828`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14081776f`
- `KERNEL32!LeaveCriticalSection` at `0x14081776f`
- `OLMAPI32!FIsFeatureEnabled` at `0x140817668`
- `OLMAPI32!FIsFeatureEnabled` at `0x140817668`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816504`
- `OLMAPI32!EtwTraceErrorTag` at `0x14081653e`
- `OLMAPI32!EtwTraceErrorTag` at `0x1408165c9`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816665`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816719`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816946`
- `OLMAPI32!EtwTraceErrorTag` at `0x1408169d6`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816a21`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816a95`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816afd`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816b47`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816bad`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816cfa`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816d3f`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816d92`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816de4`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816e92`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816efc`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816f44`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816f94`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816fe2`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816504`
- `OLMAPI32!EtwTraceErrorTag` at `0x14081653e`
- `OLMAPI32!EtwTraceErrorTag` at `0x1408165c9`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816665`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816719`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816946`
- `OLMAPI32!EtwTraceErrorTag` at `0x1408169d6`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816a21`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816a95`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816afd`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816b47`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816bad`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816cfa`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816d3f`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816d92`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816de4`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816e92`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816efc`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816f44`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816f94`
- `OLMAPI32!EtwTraceErrorTag` at `0x140816fe2`
- `OLEAUT32!__imp_SysFreeString` at `0x1408176fd`
- `OLEAUT32!__imp_SysFreeString` at `0x14081770c`
- `OLEAUT32!__imp_SysFreeString` at `0x1408176fd`
- `OLEAUT32!__imp_SysFreeString` at `0x14081770c`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x14081717f`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x140817195`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408171bb`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408171df`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408171f5`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x14081721f`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408172d8`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408172ee`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x14081717f`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x140817195`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408171bb`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408171df`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408171f5`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x14081721f`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408172d8`
- `Mso98Win32Client!__imp_?FIsMsgClsPrefixW@@YA_NPEB_W0@Z` at `0x1408172ee`
- `Mso30Win32Client!__imp_MsoFRgwchEqual` at `0x14081726d`
- `Mso30Win32Client!__imp_MsoFRgwchEqual` at `0x1408172b2`
- `Mso30Win32Client!__imp_MsoFRgwchEqual` at `0x14081726d`
- `Mso30Win32Client!__imp_MsoFRgwchEqual` at `0x1408172b2`

## string_xrefs

- `0x1408171b4`: `IPM.TaskRequest`
- `0x1408171d8`: `IPM.Note.Rules.OofTemplate.Microsoft`
- `0x140816f9a`: `timeValue->SetFILETIME(ftZero)`
- `0x140816f02`: `sortField->GetEmptyValue(&sortValue)`
- `0x140816a27`: `container->GetRegistry(&unwrappedRegistry)`

## pseudocode

```c

```
