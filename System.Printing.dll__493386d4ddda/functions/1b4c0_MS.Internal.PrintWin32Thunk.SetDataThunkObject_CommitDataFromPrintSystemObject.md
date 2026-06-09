# MS.Internal.PrintWin32Thunk.SetDataThunkObject::CommitDataFromPrintSystemObject

- ea: `0x1b4c0`
- end: `0x1b516`
- name: `MS.Internal.PrintWin32Thunk.SetDataThunkObject::CommitDataFromPrintSystemObject`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xf610`

## callees

- `0x9440`
- `0x1b4c0`
- `0x1b520`
- `0x1b560`
- `0x1b5d0`

## pseudocode

```c

```

## disassembly

```asm
0x1b4c0  ldc.i4.0
0x1b4c1  stloc.1
0x1b4c2  ldnull
0x1b4c3  stloc.0
0x1b4c4  ldarg.0
0x1b4c5  ldfld    class [mscorlib]System.Type MS.Internal.PrintWin32Thunk.SetDataThunkObject::printingType
0x1b4ca  ldc.i4.2
0x1b4cb  ldarg.3
0x1b4cc  call     valuetype MS.Internal.PrintWin32Thunk.AttributeNameToInfoLevelMapping.InfoLevelMask MS.Internal.PrintWin32Thunk.AttributeNameToInfoLevelMapping.TypeToLevelMap::GetCoverageMaskForPropertiesFilter(class [mscorlib]System.Type printingType, valuetype OperationType operationType, string[] propertiesFilter)
0x1b4d1  stloc.3
0x1b4d2  ldloc.3
0x1b4d3  brfalse.s loc_1B4FE
0x1b4d5  ldarg.0
0x1b4d6  ldarg.1
0x1b4d7  ldloc.3
0x1b4d8  call     instance class MS.Internal.PrintWin32Thunk.AttributeNameToInfoLevelMapping.InfoLevelCoverageList MS.Internal.PrintWin32Thunk.SetDataThunkObject::BuildCoverageListToSetData(class MS.Internal.PrintWin32Thunk.PrinterThunkHandler printerThunkHandler, valuetype MS.Internal.PrintWin32Thunk.AttributeNameToInfoLevelMapping.InfoLevelMask mask)
0x1b4dd  stloc.0
0x1b4de  ldloc.0
0x1b4df  brfalse.s loc_1B4FE
0x1b4e1  ldarg.0
0x1b4e2  ldarg.2
0x1b4e3  ldarg.3
0x1b4e4  ldloc.0
0x1b4e5  call     instance bool MS.Internal.PrintWin32Thunk.SetDataThunkObject::SetAttributesFromCoverageList([hasfieldmarshal] class System.Printing.PrintSystemObject value, string[] printObject, class MS.Internal.PrintWin32Thunk.AttributeNameToInfoLevelMapping.InfoLevelCoverageList propertiesFilter)
0x1b4ea  stloc.1
0x1b4eb  ldloc.1
0x1b4ec  brfalse.s loc_1B4FE
0x1b4ee  ldarg.0
0x1b4ef  ldarg.1
0x1b4f0  ldarg.3
0x1b4f1  ldloc.0
0x1b4f2  ldarg.2
0x1b4f3  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1b4f8  call     instance bool MS.Internal.PrintWin32Thunk.SetDataThunkObject::SetDataFromCoverageList([hasfieldmarshal] class MS.Internal.PrintWin32Thunk.PrinterThunkHandler value, string[] printingHandler, class MS.Internal.PrintWin32Thunk.AttributeNameToInfoLevelMapping.InfoLevelCoverageList propertiesFilter, class [mscorlib]System.Type coverageList)
0x1b4fd  stloc.1
0x1b4fe  leave.s  loc_1B514
0x1b500  ldloc.0
0x1b501  brfalse.s loc_1B513
0x1b503  ldloc.0
0x1b504  isinst   [mscorlib]System.IDisposable
0x1b509  stloc.2
0x1b50a  ldloc.2
0x1b50b  brfalse.s loc_1B513
0x1b50d  ldloc.2
0x1b50e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b513  endfinally
0x1b514  ldloc.1
0x1b515  ret
```
