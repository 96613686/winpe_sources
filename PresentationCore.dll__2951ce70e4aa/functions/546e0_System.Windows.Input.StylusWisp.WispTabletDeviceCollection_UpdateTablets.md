# System.Windows.Input.StylusWisp.WispTabletDeviceCollection::UpdateTablets

- ea: `0x546e0`
- end: `0x5473c`
- name: `System.Windows.Input.StylusWisp.WispTabletDeviceCollection::UpdateTablets`
- size: `92`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x52310`
- `0x52550`
- `0x52580`
- `0x52740`
- `0x544c0`

## callees

- `0x546e0`
- `0x54740`
- `0x5be40`

## string_xrefs

- `0x546fb`: `UpdateTablets`

## pseudocode

```c

```

## disassembly

```asm
0x546e0  ldarg.0
0x546e1  ldfld    class System.Windows.Input.TabletDevice[] System.Windows.Input.StylusWisp.WispTabletDeviceCollection::_tablets
0x546e6  brtrue.s loc_546F3
0x546e8  ldstr    aTabletdeviceco// "TabletDeviceCollection"
0x546ed  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x546f2  throw
0x546f3  ldarg.0
0x546f4  ldfld    bool System.Windows.Input.StylusWisp.WispTabletDeviceCollection::_inUpdateTablets
0x546f9  brfalse.s loc_5470D
0x546fb  ldstr    aUpdatetablets// "UpdateTablets"
0x54700  call     void System.Windows.Input.Tracing.StylusTraceLogger::LogReentrancy([opt] string functionName)
0x54705  ldarg.0
0x54706  ldc.i4.1
0x54707  stfld    bool System.Windows.Input.StylusWisp.WispTabletDeviceCollection::_hasUpdateTabletsBeenCalledReentrantly
0x5470c  ret
0x5470d  nop
0x5470e  ldarg.0
0x5470f  ldc.i4.1
0x54710  stfld    bool System.Windows.Input.StylusWisp.WispTabletDeviceCollection::_inUpdateTablets
0x54715  ldarg.0
0x54716  ldc.i4.0
0x54717  stfld    bool System.Windows.Input.StylusWisp.WispTabletDeviceCollection::_hasUpdateTabletsBeenCalledReentrantly
0x5471c  ldarg.0
0x5471d  call     instance void System.Windows.Input.StylusWisp.WispTabletDeviceCollection::UpdateTabletsImpl()
0x54722  ldarg.0
0x54723  ldfld    bool System.Windows.Input.StylusWisp.WispTabletDeviceCollection::_hasUpdateTabletsBeenCalledReentrantly
0x54728  brtrue.s loc_54715
0x5472a  leave.s  loc_5473B
0x5472c  ldarg.0
0x5472d  ldc.i4.0
0x5472e  stfld    bool System.Windows.Input.StylusWisp.WispTabletDeviceCollection::_inUpdateTablets
0x54733  ldarg.0
0x54734  ldc.i4.0
0x54735  stfld    bool System.Windows.Input.StylusWisp.WispTabletDeviceCollection::_hasUpdateTabletsBeenCalledReentrantly
0x5473a  endfinally
0x5473b  ret
```
