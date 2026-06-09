# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::UpdateItemExecutionSnapshot

- ea: `0x14e40`
- end: `0x14e72`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::UpdateItemExecutionSnapshot`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x21550`

## callees

- `0x23430`

## string_xrefs

- `0x14e55`: `UpdateItemExecutionSnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x14e40  newobj   instance void <>c__DisplayClass83_0::.ctor()
0x14e45  stloc.0
0x14e46  ldloc.0
0x14e47  ldarg.0
0x14e48  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass83_0::<>4__this
0x14e4d  ldloc.0
0x14e4e  ldarg.1
0x14e4f  stfld    string <>c__DisplayClass83_0::itemPath
0x14e54  ldarg.0
0x14e55  ldstr    aUpdateitemexec// "UpdateItemExecutionSnapshot"
0x14e5a  ldloc.0
0x14e5b  ldftn    instance int32 <>c__DisplayClass83_0::<UpdateItemExecutionSnapshot>b__0()
0x14e61  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x14e66  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x14e6b  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x14e70  pop
0x14e71  ret
```
