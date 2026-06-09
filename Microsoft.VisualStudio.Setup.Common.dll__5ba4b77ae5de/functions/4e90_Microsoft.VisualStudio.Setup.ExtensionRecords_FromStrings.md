# Microsoft.VisualStudio.Setup.ExtensionRecords::FromStrings

- ea: `0x4e90`
- end: `0x4fe1`
- name: `Microsoft.VisualStudio.Setup.ExtensionRecords::FromStrings`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0xee20`

## callees

- `0x4e20`
- `0x4e90`
- `0x4ff0`
- `0x50e0`
- `0x5110`
- `0x11b00`
- `0x11b20`

## string_xrefs

- `0x4f13`: ` as a file path.`
- `0x4f7b`: `Adding ${0} as a URI.`
- `0x4f9c`: `Failed to convert '{0}' to an extension type, its type is unknown.`

## pseudocode

```c

```

## disassembly

```asm
0x4e90  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>::.ctor()
0x4e95  stloc.0
0x4e96  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>::.ctor()
0x4e9b  stloc.1
0x4e9c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>::.ctor()
0x4ea1  stloc.2
0x4ea2  ldarg.1
0x4ea3  brfalse.s loc_4EAD
0x4ea5  ldarg.1
0x4ea6  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>>::get_Count()
0x4eab  brtrue.s loc_4EB5
0x4ead  ldloc.0
0x4eae  ldloc.1
0x4eaf  newobj   instance void Microsoft.VisualStudio.Setup.ExtensionRecords::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> Uris, class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> MarketPlaceItemNames)
0x4eb4  ret
0x4eb5  ldarg.1
0x4eb6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>>::GetEnumerator()
0x4ebb  stloc.3
0x4ebc  br       loc_4FBB
0x4ec1  ldloc.3
0x4ec2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>>::get_Current()
0x4ec7  stloc.s  4
0x4ec9  ldloca.s 4
0x4ecb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>::get_Key()
0x4ed0  stloc.s  5
0x4ed2  ldloca.s 4
0x4ed4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>::get_Value()
0x4ed9  stloc.s  6
0x4edb  ldloc.s  5
0x4edd  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x4ee2  stloc.s  7
0x4ee4  ldloca.s 7
0x4ee6  call     instance string [mscorlib]System.Char::ToString()
0x4eeb  callvirt instance bool [mscorlib]System.String::Contains(string)
0x4ef0  brfalse.s loc_4F2C
0x4ef2  ldloc.s  5
0x4ef4  call     bool Microsoft.VisualStudio.Setup.ExtensionRecords::IsExtensionFilePath(string extension)
0x4ef9  brfalse.s loc_4F2C
0x4efb  ldloc.0
0x4efc  ldloc.s  5
0x4efe  ldloc.s  6
0x4f00  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>::Add(var<u1>, !!T0)
0x4f05  ldarg.0
0x4f06  brfalse  loc_4FBB
0x4f0b  ldarg.0
0x4f0c  ldstr    aAdding// "Adding $"
0x4f11  ldloc.s  5
0x4f13  ldstr    aAsAFilePath// " as a file path."
0x4f18  call     string [mscorlib]System.String::Concat(string, string, string)
0x4f1d  call     T0x2B000016
0x4f22  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string format, object[] args)
0x4f27  br       loc_4FBB
0x4f2c  ldloc.s  5
0x4f2e  ldc.i4.1
0x4f2f  ldloca.s 8
0x4f31  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x4f36  brfalse.s loc_4F98
0x4f38  ldloc.s  8
0x4f3a  ldloca.s 9
0x4f3c  call     bool Microsoft.VisualStudio.Setup.ExtensionRecords::TryGetItemName(class [System]System.Uri uri, [out] string& itemName)
0x4f41  brfalse.s loc_4F6D
0x4f43  ldarg.0
0x4f44  brfalse.s loc_4F61
0x4f46  ldarg.0
0x4f47  ldstr    aParsedMarketpl// "Parsed marketplace item name '{0}' from"...
0x4f4c  ldc.i4.2
0x4f4d  newarr   [mscorlib]System.Object
0x4f52  dup
0x4f53  ldc.i4.0
0x4f54  ldloc.s  9
0x4f56  stelem.ref
0x4f57  dup
0x4f58  ldc.i4.1
0x4f59  ldloc.s  5
0x4f5b  stelem.ref
0x4f5c  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string format, object[] args)
0x4f61  ldloc.1
0x4f62  ldloc.s  9
0x4f64  ldloc.s  6
0x4f66  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>::set_Item(var<u1>, !!T0)
0x4f6b  br.s     loc_4FBB
0x4f6d  ldloc.0
0x4f6e  ldloc.s  5
0x4f70  ldloc.s  6
0x4f72  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>::Add(var<u1>, !!T0)
0x4f77  ldarg.0
0x4f78  brfalse.s loc_4FBB
0x4f7a  ldarg.0
0x4f7b  ldstr    aAdding0AsAUri// "Adding ${0} as a URI."
0x4f80  ldloc.s  4
0x4f82  box      valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>
0x4f87  call     string [mscorlib]System.String::Format(string, object)
0x4f8c  call     T0x2B000016
0x4f91  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string format, object[] args)
0x4f96  br.s     loc_4FBB
0x4f98  ldarg.0
0x4f99  brfalse.s loc_4FB1
0x4f9b  ldarg.0
0x4f9c  ldstr    aFailedToConver// "Failed to convert '{0}' to an extension"...
0x4fa1  ldc.i4.1
0x4fa2  newarr   [mscorlib]System.Object
0x4fa7  dup
0x4fa8  ldc.i4.0
0x4fa9  ldloc.s  5
0x4fab  stelem.ref
0x4fac  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string format, object[] args)
0x4fb1  ldloc.2
0x4fb2  ldloc.s  5
0x4fb4  ldloc.s  6
0x4fb6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>::set_Item(var<u1>, !!T0)
0x4fbb  ldloc.3
0x4fbc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4fc1  brtrue   loc_4EC1
0x4fc6  leave.s  loc_4FD2
0x4fc8  ldloc.3
0x4fc9  brfalse.s loc_4FD1
0x4fcb  ldloc.3
0x4fcc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4fd1  endfinally
0x4fd2  ldloc.0
0x4fd3  ldloc.1
0x4fd4  newobj   instance void Microsoft.VisualStudio.Setup.ExtensionRecords::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> Uris, class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> MarketPlaceItemNames)
0x4fd9  dup
0x4fda  ldloc.2
0x4fdb  callvirt instance modreq(System.Runtime.CompilerServices.IsExternalInit) void Microsoft.VisualStudio.Setup.ExtensionRecords::set_UnknownExtensions(class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> value)
0x4fe0  ret
```
