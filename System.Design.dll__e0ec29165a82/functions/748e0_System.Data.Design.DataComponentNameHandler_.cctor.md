# System.Data.Design.DataComponentNameHandler::.cctor

- ea: `0x748e0`
- end: `0x74995`
- name: `System.Data.Design.DataComponentNameHandler::.cctor`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0x74908`: `Update`
- `0x748f4`: `Delete`
- `0x74930`: `_commandCollection`
- `0x7493a`: `CommandCollection`
- `0x74944`: `InitCommandCollection`

## pseudocode

```c

```

## disassembly

```asm
0x748e0  ldstr    aPage// "Page"
0x748e5  stsfld   string System.Data.Design.DataComponentNameHandler::pagingMethodSuffix
0x748ea  ldstr    aInitclass// "InitClass"
0x748ef  stsfld   string System.Data.Design.DataComponentNameHandler::initMethodName
0x748f4  ldstr    aDelete// "Delete"
0x748f9  stsfld   string System.Data.Design.DataComponentNameHandler::deleteMethodName
0x748fe  ldstr    aInsert// "Insert"
0x74903  stsfld   string System.Data.Design.DataComponentNameHandler::insertMethodName
0x74908  ldstr    aUpdate// "Update"
0x7490d  stsfld   string System.Data.Design.DataComponentNameHandler::updateMethodName
0x74912  ldstr    aAdapter// "_adapter"
0x74917  stsfld   string System.Data.Design.DataComponentNameHandler::adapterVariableName
0x7491c  ldstr    aAdapter_0// "Adapter"
0x74921  stsfld   string System.Data.Design.DataComponentNameHandler::adapterPropertyName
0x74926  ldstr    aInitadapter// "InitAdapter"
0x7492b  stsfld   string System.Data.Design.DataComponentNameHandler::initAdapter
0x74930  ldstr    aCommandcollect// "_commandCollection"
0x74935  stsfld   string System.Data.Design.DataComponentNameHandler::selectCmdCollectionVariableName
0x7493a  ldstr    aCommandcollect_0// "CommandCollection"
0x7493f  stsfld   string System.Data.Design.DataComponentNameHandler::selectCmdCollectionPropertyName
0x74944  ldstr    aInitcommandcol// "InitCommandCollection"
0x74949  stsfld   string System.Data.Design.DataComponentNameHandler::initCmdCollection
0x7494e  ldstr    aConnection_0// "_connection"
0x74953  stsfld   string System.Data.Design.DataComponentNameHandler::defaultConnectionVariableName
0x74958  ldstr    aConnection// "Connection"
0x7495d  stsfld   string System.Data.Design.DataComponentNameHandler::defaultConnectionPropertyName
0x74962  ldstr    aTransaction_0// "_transaction"
0x74967  stsfld   string System.Data.Design.DataComponentNameHandler::transactionVariableName
0x7496c  ldstr    aTransaction// "Transaction"
0x74971  stsfld   string System.Data.Design.DataComponentNameHandler::transactionPropertyName
0x74976  ldstr    aInitconnection// "InitConnection"
0x7497b  stsfld   string System.Data.Design.DataComponentNameHandler::initConnection
0x74980  ldstr    aClearbeforefil// "_clearBeforeFill"
0x74985  stsfld   string System.Data.Design.DataComponentNameHandler::clearBeforeFillVariableName
0x7498a  ldstr    aClearbeforefil_0// "ClearBeforeFill"
0x7498f  stsfld   string System.Data.Design.DataComponentNameHandler::clearBeforeFillPropertyName
0x74994  ret
```
