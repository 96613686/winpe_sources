# Microsoft.SharePoint.Publishing.DesignPackageInfoValueTypeConverter::WritePropertiesAsJson

- ea: `0x2cd0`
- end: `0x2d45`
- name: `Microsoft.SharePoint.Publishing.DesignPackageInfoValueTypeConverter::WritePropertiesAsJson`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2cd0`

## pseudocode

```c

```

## disassembly

```asm
0x2cd0  ldarg.2
0x2cd1  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.DesignPackageInfo
0x2cd6  stloc.0
0x2cd7  ldloc.0
0x2cd8  brtrue.s loc_2CDB
0x2cda  ret
0x2cdb  ldarg.0
0x2cdc  ldarg.1
0x2cdd  ldarg.2
0x2cde  ldarg.3
0x2cdf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2ce4  ldarg.1
0x2ce5  ldstr    aMajorversion// "MajorVersion"
0x2cea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2cef  ldarg.1
0x2cf0  ldloc.0
0x2cf1  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.DesignPackageInfo::get_MajorVersion()
0x2cf6  ldarg.3
0x2cf7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2cfc  ldarg.1
0x2cfd  ldstr    aMinorversion// "MinorVersion"
0x2d02  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2d07  ldarg.1
0x2d08  ldloc.0
0x2d09  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.DesignPackageInfo::get_MinorVersion()
0x2d0e  ldarg.3
0x2d0f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2d14  ldarg.1
0x2d15  ldstr    aPackageguid// "PackageGuid"
0x2d1a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2d1f  ldarg.1
0x2d20  ldloc.0
0x2d21  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.DesignPackageInfo::get_PackageGuid()
0x2d26  ldarg.3
0x2d27  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2d2c  ldarg.1
0x2d2d  ldstr    aPackagename// "PackageName"
0x2d32  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2d37  ldarg.1
0x2d38  ldloc.0
0x2d39  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.DesignPackageInfo::get_PackageName()
0x2d3e  ldarg.3
0x2d3f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2d44  ret
```
