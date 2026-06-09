# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateSubscription

- ea: `0x146b0`
- end: `0x14707`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateSubscription`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x21040`

## callees

- `0x22d90`

## string_xrefs

- `0x146eb`: `CreateSubscription`

## pseudocode

```c

```

## disassembly

```asm
0x146b0  newobj   instance void <>c__DisplayClass59_0::.ctor()
0x146b5  stloc.0
0x146b6  ldloc.0
0x146b7  ldarg.0
0x146b8  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass59_0::<>4__this
0x146bd  ldloc.0
0x146be  ldarg.1
0x146bf  stfld    string <>c__DisplayClass59_0::itemPath
0x146c4  ldloc.0
0x146c5  ldarg.2
0x146c6  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings <>c__DisplayClass59_0::extensionSettings
0x146cb  ldloc.0
0x146cc  ldarg.3
0x146cd  stfld    string <>c__DisplayClass59_0::description
0x146d2  ldloc.0
0x146d3  ldarg.s  4
0x146d5  stfld    string <>c__DisplayClass59_0::eventType
0x146da  ldloc.0
0x146db  ldarg.s  5
0x146dd  stfld    string <>c__DisplayClass59_0::matchData
0x146e2  ldloc.0
0x146e3  ldarg.s  6
0x146e5  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValue[] <>c__DisplayClass59_0::parameters
0x146ea  ldarg.0
0x146eb  ldstr    aCreatesubscrip// "CreateSubscription"
0x146f0  ldloc.0
0x146f1  ldftn    instance string <>c__DisplayClass59_0::<CreateSubscription>b__0()
0x146f7  newobj   instance void class SoapMethod<string>::.ctor(object, native int)
0x146fc  newobj   instance void class SoapMethodWrapper`1<string>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x14701  callvirt instance var<u1> class SoapMethodWrapper`1<string>::ExecuteMethod()
0x14706  ret
```
