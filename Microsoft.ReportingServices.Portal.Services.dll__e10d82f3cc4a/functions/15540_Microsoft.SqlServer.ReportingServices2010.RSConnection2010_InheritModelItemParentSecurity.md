# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::InheritModelItemParentSecurity

- ea: `0x15540`
- end: `0x15579`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::InheritModelItemParentSecurity`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x23ad0`

## string_xrefs

- `0x1555c`: `InheritModelItemParentSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x15540  newobj   instance void <>c__DisplayClass111_0::.ctor()
0x15545  stloc.0
0x15546  ldloc.0
0x15547  ldarg.0
0x15548  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass111_0::<>4__this
0x1554d  ldloc.0
0x1554e  ldarg.1
0x1554f  stfld    string <>c__DisplayClass111_0::model
0x15554  ldloc.0
0x15555  ldarg.2
0x15556  stfld    string <>c__DisplayClass111_0::modelItemId
0x1555b  ldarg.0
0x1555c  ldstr    aInheritmodelit// "InheritModelItemParentSecurity"
0x15561  ldloc.0
0x15562  ldftn    instance int32 <>c__DisplayClass111_0::<InheritModelItemParentSecurity>b__0()
0x15568  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x1556d  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x15572  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x15577  pop
0x15578  ret
```
