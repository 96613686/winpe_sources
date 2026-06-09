# Microsoft.VisualStudio.Setup.Utility.ShortcutUtility::DeleteShortcuts

- ea: `0x28db0`
- end: `0x28f98`
- name: `Microsoft.VisualStudio.Setup.Utility.ShortcutUtility::DeleteShortcuts`
- size: `488`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x33e80`
- `0x450b0`

## callees

- `0xf0d0`
- `0xfe50`
- `0x28b60`
- `0x28db0`
- `0x28fa0`
- `0x290e0`
- `0x292b0`

## string_xrefs

- `0x28f23`: `Deleted shortcut: {0}`
- `0x28f59`: `Failed to delete shortcut: {0}, exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x28db0  ldarg.0
0x28db1  ldstr    aShortcuts// "shortcuts"
0x28db6  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x28dbb  ldc.i4.1
0x28dbc  stloc.0
0x28dbd  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x28dc2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x28dc7  stloc.1
0x28dc8  ldarg.1
0x28dc9  brfalse.s loc_28DD2
0x28dcb  ldloc.1
0x28dcc  ldarg.1
0x28dcd  call     T0x2B000161
0x28dd2  ldarg.2
0x28dd3  brtrue.s loc_28DD8
0x28dd5  ldnull
0x28dd6  br.s     loc_28DDF
0x28dd8  ldarg.2
0x28dd9  ldc.i4.0
0x28dda  call     T0x2B000001
0x28ddf  stloc.2
0x28de0  ldarg.2
0x28de1  brtrue.s loc_28DE6
0x28de3  ldnull
0x28de4  br.s     loc_28DED
0x28de6  ldarg.2
0x28de7  ldc.i4.0
0x28de8  call     T0x2B00000C
0x28ded  dup
0x28dee  brtrue.s loc_28DF6
0x28df0  pop
0x28df1  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Services.FileSystem::Default
0x28df6  stloc.3
0x28df7  ldloc.1
0x28df8  ldloc.3
0x28df9  call     class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Utility.ShortcutUtility::GetVariableMapping(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem)
0x28dfe  call     T0x2B000161
0x28e03  ldarg.0
0x28e04  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ShortcutInformation>::GetEnumerator()
0x28e09  stloc.s  4
0x28e0b  br       loc_28F7C
0x28e10  ldloc.s  4
0x28e12  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ShortcutInformation>::get_Current()
0x28e17  stloc.s  5
0x28e19  ldloc.s  5
0x28e1b  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ShortcutInformation::get_DisplayName()
0x28e20  ldloc.1
0x28e21  call     string Microsoft.VisualStudio.Setup.Utility.StringUtility::FormatDisplayName(string displayName, class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> propertyBag)
0x28e26  stloc.s  6
0x28e28  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x28e2d  ldloc.s  5
0x28e2f  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ShortcutInformation::get_Folder()
0x28e34  ldloc.1
0x28e35  ldnull
0x28e36  ldc.i4.0
0x28e37  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x28e3c  stloc.s  7
0x28e3e  ldloc.s  5
0x28e40  call     string Microsoft.VisualStudio.Setup.Utility.ShortcutUtility::GetExtension(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ShortcutInformation shortcut)
0x28e45  stloc.s  8
0x28e47  ldloc.s  7
0x28e49  ldloc.s  6
0x28e4b  ldloc.s  8
0x28e4d  call     string [mscorlib]System.String::Concat(string, string)
0x28e52  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x28e57  stloc.s  9
0x28e59  dup
0x28e5a  ldloc.s  9
0x28e5c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x28e61  ldloc.s  5
0x28e63  call     class [System]System.Collections.Generic.ISet`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetLocalPaths(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ShortcutInformation)
0x28e68  ldsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__7_0
0x28e6d  dup
0x28e6e  brtrue.s loc_28E87
0x28e70  pop
0x28e71  ldsfld   class <>c <>c::<>9
0x28e76  ldftn    instance bool <>c::<DeleteShortcuts>b__7_0(string x)
0x28e7c  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x28e81  dup
0x28e82  stsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__7_0
0x28e87  call     T0x2B0000E4
0x28e8c  stloc.s  0xA
0x28e8e  dup
0x28e8f  ldloc.s  0xA
0x28e91  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x28e96  ldloc.3
0x28e97  ldloc.s  7
0x28e99  ldloc.s  5
0x28e9b  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ShortcutInformation::get_DisplayName()
0x28ea0  ldstr    asc_81126// "*"
0x28ea5  ldloc.s  8
0x28ea7  call     string [mscorlib]System.String::Concat(string, string, string)
0x28eac  ldc.i4.0
0x28ead  callvirt instance string[] [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::GetFiles(string, string, bool)
0x28eb2  stloc.s  0xB
0x28eb4  dup
0x28eb5  ldloc.s  0xB
0x28eb7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x28ebc  dup
0x28ebd  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x28ec2  call     T0x2B000162
0x28ec7  pop
0x28ec8  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x28ecd  stloc.s  0xC
0x28ecf  br.s     loc_28F38
0x28ed1  ldloca.s 0xC
0x28ed3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x28ed8  stloc.s  0xD
0x28eda  ldloc.3
0x28edb  ldloc.s  0xD
0x28edd  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x28ee2  brfalse.s loc_28F38
0x28ee4  ldloc.2
0x28ee5  brfalse.s loc_28F02
0x28ee7  ldloc.2
0x28ee8  ldstr    aCheckingIfShor// "Checking if shortcut '{0}' has the same"...
0x28eed  ldc.i4.2
0x28eee  newarr   [mscorlib]System.Object
0x28ef3  dup
0x28ef4  ldc.i4.0
0x28ef5  ldloc.s  0xD
0x28ef7  stelem.ref
0x28ef8  dup
0x28ef9  ldc.i4.1
0x28efa  ldloc.s  6
0x28efc  stelem.ref
0x28efd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x28f02  ldloc.s  5
0x28f04  ldloc.s  0xD
0x28f06  ldloc.1
0x28f07  ldarg.3
0x28f08  call     bool Microsoft.VisualStudio.Setup.Utility.ShortcutUtility::ShortcutEquals(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ShortcutInformation shortcut, string shortcutPath, class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> variables, class Microsoft.VisualStudio.Setup.Shortcuts.IShortcutFactory shortcutFactory)
0x28f0d  brfalse.s loc_28F38
0x28f0f  ldloc.3
0x28f10  ldloc.s  0xD
0x28f12  ldc.i4.2
0x28f13  ldc.i4   0x1F4
0x28f18  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteFileIfExists(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [opt] int32 retryCount, [opt] int32 retryDelay)
0x28f1d  brfalse.s loc_28F38
0x28f1f  ldloc.2
0x28f20  brfalse.s loc_28F38
0x28f22  ldloc.2
0x28f23  ldstr    aDeletedShortcu// "Deleted shortcut: {0}"
0x28f28  ldc.i4.1
0x28f29  newarr   [mscorlib]System.Object
0x28f2e  dup
0x28f2f  ldc.i4.0
0x28f30  ldloc.s  0xD
0x28f32  stelem.ref
0x28f33  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x28f38  ldloca.s 0xC
0x28f3a  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x28f3f  brtrue.s loc_28ED1
0x28f41  leave.s  loc_28F51
0x28f43  ldloca.s 0xC
0x28f45  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x28f4b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x28f50  endfinally
0x28f51  leave.s  loc_28F7C
0x28f53  stloc.s  0xE
0x28f55  ldloc.2
0x28f56  brfalse.s loc_28F78
0x28f58  ldloc.2
0x28f59  ldstr    aFailedToDelete_5// "Failed to delete shortcut: {0}, excepti"...
0x28f5e  ldc.i4.2
0x28f5f  newarr   [mscorlib]System.Object
0x28f64  dup
0x28f65  ldc.i4.0
0x28f66  ldloc.s  6
0x28f68  stelem.ref
0x28f69  dup
0x28f6a  ldc.i4.1
0x28f6b  ldloc.s  0xE
0x28f6d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x28f72  stelem.ref
0x28f73  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x28f78  ldc.i4.0
0x28f79  stloc.0
0x28f7a  leave.s  loc_28F7C
0x28f7c  ldloc.s  4
0x28f7e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x28f83  brtrue   loc_28E10
0x28f88  leave.s  loc_28F96
0x28f8a  ldloc.s  4
0x28f8c  brfalse.s loc_28F95
0x28f8e  ldloc.s  4
0x28f90  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x28f95  endfinally
0x28f96  ldloc.0
0x28f97  ret
```
