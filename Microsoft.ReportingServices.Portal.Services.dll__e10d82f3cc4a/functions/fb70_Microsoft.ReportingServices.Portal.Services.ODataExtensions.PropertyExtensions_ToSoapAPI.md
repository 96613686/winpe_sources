# Microsoft.ReportingServices.Portal.Services.ODataExtensions.PropertyExtensions::ToSoapAPI

- ea: `0xfb70`
- end: `0xfb9c`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.PropertyExtensions::ToSoapAPI`
- size: `44`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1d1c0`
- `0x1d1e0`
- `0x1d1f0`
- `0x1d270`
- `0x1d2a0`
- `0x1d330`
- `0x1d340`
- `0x1d350`

## callees

- `0xfb70`

## pseudocode

```c

```

## disassembly

```asm
0xfb70  ldarg.0
0xfb71  brtrue.s loc_FB7E
0xfb73  ldstr    aWebapiproperty// "webApiProperty"
0xfb78  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfb7d  throw
0xfb7e  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0xfb83  dup
0xfb84  ldarg.0
0xfb85  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::get_Name()
0xfb8a  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0xfb8f  dup
0xfb90  ldarg.0
0xfb91  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::get_Value()
0xfb96  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0xfb9b  ret
```
