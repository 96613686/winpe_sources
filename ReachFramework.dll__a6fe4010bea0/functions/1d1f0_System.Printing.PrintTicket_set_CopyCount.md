# System.Printing.PrintTicket::set_CopyCount

- ea: `0x1d1f0`
- end: `0x1d25e`
- name: `System.Printing.PrintTicket::set_CopyCount`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0xf0a0`
- `0x173e0`
- `0x180b0`
- `0x18a20`
- `0x1d1f0`
- `0x1e280`

## string_xrefs

- `0x1d253`: `CopyCount`

## pseudocode

```c

```

## disassembly

```asm
0x1d1f0  ldarga.s 1
0x1d1f2  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x1d1f7  brtrue.s loc_1D20B
0x1d1f9  ldarg.0
0x1d1fa  ldfld    class MS.Internal.Printing.Configuration.InternalPrintTicket System.Printing.PrintTicket::_printTicket
0x1d1ff  callvirt instance class MS.Internal.Printing.Configuration.JobCopyCountSetting MS.Internal.Printing.Configuration.InternalPrintTicket::get_JobCopyCount()
0x1d204  callvirt instance void MS.Internal.Printing.Configuration.PrintTicketParameter::ClearSetting()
0x1d209  br.s     loc_1D252
0x1d20b  ldarg.1
0x1d20c  stloc.0
0x1d20d  ldc.i4.0
0x1d20e  stloc.1
0x1d20f  ldloca.s 0
0x1d211  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x1d216  ldloc.1
0x1d217  cgt
0x1d219  ldc.i4.0
0x1d21a  ceq
0x1d21c  ldloca.s 0
0x1d21e  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x1d223  and
0x1d224  brfalse.s loc_1D23B
0x1d226  ldstr    aValue// "value"
0x1d22b  ldstr    aArgumentexcept// "ArgumentException.PositiveValue"
0x1d230  call     string MS.Internal.Printing.Configuration.PTUtility::GetTextFromResource(string key)
0x1d235  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x1d23a  throw
0x1d23b  ldarg.0
0x1d23c  ldfld    class MS.Internal.Printing.Configuration.InternalPrintTicket System.Printing.PrintTicket::_printTicket
0x1d241  callvirt instance class MS.Internal.Printing.Configuration.JobCopyCountSetting MS.Internal.Printing.Configuration.InternalPrintTicket::get_JobCopyCount()
0x1d246  ldarga.s 1
0x1d248  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x1d24d  callvirt instance void MS.Internal.Printing.Configuration.JobCopyCountSetting::set_Value(int32 value)
0x1d252  ldarg.0
0x1d253  ldstr    aCopycount// "CopyCount"
0x1d258  call     instance void System.Printing.PrintTicket::NotifyPropertyChanged(string name)
0x1d25d  ret
```
