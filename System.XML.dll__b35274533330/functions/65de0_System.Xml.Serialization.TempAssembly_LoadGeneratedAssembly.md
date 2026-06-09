# System.Xml.Serialization.TempAssembly::LoadGeneratedAssembly

- ea: `0x65de0`
- end: `0x66003`
- name: `System.Xml.Serialization.TempAssembly::LoadGeneratedAssembly`
- size: `547`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0xa9e70`
- `0xaa460`
- `0xaaf10`

## callees

- `0xdb20`
- `0x622f0`
- `0x65de0`
- `0x66010`
- `0x66030`
- `0x66060`
- `0x66a30`
- `0x67330`
- `0xa9c10`
- `0xa9c30`
- `0xa9d40`

## string_xrefs

- `0x65fb2`: `XmlSerializerContract`
- `0x65eb5`: `XmlPregenCannotLoad`
- `0x65ee2`: `XmlSerializerExpiredDetails`
- `0x65fdb`: `XmlSerializerExpiredDetails`
- `0x65f23`: `XmlPregenInvalidXmlSerializerAssemblyAttribute`

## pseudocode

```c

```

## disassembly

```asm
0x65de0  ldnull
0x65de1  stloc.0
0x65de2  ldarg.2
0x65de3  ldnull
0x65de4  stind.ref
0x65de5  ldnull
0x65de6  stloc.1
0x65de7  ldsfld   class [mscorlib]System.Lazy`1<bool> Microsoft.Win32.UnsafeNativeMethods::IsPackagedProcess
0x65dec  callvirt instance var<u1> class [mscorlib]System.Lazy`1<bool>::get_Value()
0x65df1  brfalse.s loc_65DF5
0x65df3  ldnull
0x65df4  ret
0x65df5  call     class [System]System.Diagnostics.BooleanSwitch System.Xml.DiagnosticsSwitches::get_PregenEventLog()
0x65dfa  callvirt instance bool [System]System.Diagnostics.BooleanSwitch::get_Enabled()
0x65dff  stloc.2
0x65e00  ldarg.0
0x65e01  ldtoken  System.Xml.Serialization.XmlSerializerAssemblyAttribute
0x65e06  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x65e0b  ldc.i4.0
0x65e0c  callvirt instance object[] [mscorlib]System.Reflection.MemberInfo::GetCustomAttributes(class [mscorlib]System.Type, bool)
0x65e11  stloc.3
0x65e12  ldloc.3
0x65e13  ldlen
0x65e14  brtrue   loc_65F07
0x65e19  ldarg.0
0x65e1a  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x65e1f  ldc.i4.1
0x65e20  call     class [mscorlib]System.Reflection.AssemblyName System.Xml.Serialization.TempAssembly::GetName(class [mscorlib]System.Reflection.Assembly assembly, bool copyName)
0x65e25  stloc.s  5
0x65e27  ldloc.s  5
0x65e29  ldarg.1
0x65e2a  call     string System.Xml.Serialization.Compiler::GetTempAssemblyName(class [mscorlib]System.Reflection.AssemblyName parent, string ns)
0x65e2f  stloc.1
0x65e30  ldloc.s  5
0x65e32  ldloc.1
0x65e33  callvirt instance void [mscorlib]System.Reflection.AssemblyName::set_Name(string)
0x65e38  ldloc.s  5
0x65e3a  ldnull
0x65e3b  callvirt instance void [mscorlib]System.Reflection.AssemblyName::set_CodeBase(string)
0x65e40  ldloc.s  5
0x65e42  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x65e47  callvirt instance void [mscorlib]System.Reflection.AssemblyName::set_CultureInfo(class [mscorlib]System.Globalization.CultureInfo)
0x65e4c  ldloc.s  5
0x65e4e  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(class [mscorlib]System.Reflection.AssemblyName)
0x65e53  stloc.0
0x65e54  leave.s  loc_65EA9
0x65e56  stloc.s  6
0x65e58  ldloc.s  6
0x65e5a  isinst   [mscorlib]System.Threading.ThreadAbortException
0x65e5f  brtrue.s loc_65E73
0x65e61  ldloc.s  6
0x65e63  isinst   [mscorlib]System.StackOverflowException
0x65e68  brtrue.s loc_65E73
0x65e6a  ldloc.s  6
0x65e6c  isinst   [mscorlib]System.OutOfMemoryException
0x65e71  brfalse.s loc_65E75
0x65e73  rethrow
0x65e75  ldloc.2
0x65e76  brfalse.s loc_65E85
0x65e78  ldloc.s  6
0x65e7a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x65e7f  ldc.i4.4
0x65e80  call     void System.Xml.Serialization.TempAssembly::Log(string message, valuetype [System]System.Diagnostics.EventLogEntryType type)
0x65e85  ldloc.s  5
0x65e87  callvirt instance unsigned int8[] [mscorlib]System.Reflection.AssemblyName::GetPublicKeyToken()
0x65e8c  stloc.s  7
0x65e8e  ldloc.s  7
0x65e90  brfalse.s loc_65E9F
0x65e92  ldloc.s  7
0x65e94  ldlen
0x65e95  brfalse.s loc_65E9F
0x65e97  ldnull
0x65e98  stloc.s  8
0x65e9a  leave    loc_66000
0x65e9f  ldloc.1
0x65ea0  ldnull
0x65ea1  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::LoadWithPartialName(string, class [mscorlib]System.Security.Policy.Evidence)
0x65ea6  stloc.0
0x65ea7  leave.s  loc_65EA9
0x65ea9  ldloc.0
0x65eaa  ldnull
0x65eab  call     bool [mscorlib]System.Reflection.Assembly::op_Equality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x65eb0  brfalse.s loc_65ED1
0x65eb2  ldloc.2
0x65eb3  brfalse.s loc_65ECF
0x65eb5  ldstr    aXmlpregencanno// "XmlPregenCannotLoad"
0x65eba  ldc.i4.1
0x65ebb  newarr   [mscorlib]System.Object
0x65ec0  dup
0x65ec1  ldc.i4.0
0x65ec2  ldloc.1
0x65ec3  stelem.ref
0x65ec4  call     string System.Xml.Res::GetString(string name, object[] args)
0x65ec9  ldc.i4.4
0x65eca  call     void System.Xml.Serialization.TempAssembly::Log(string message, valuetype [System]System.Diagnostics.EventLogEntryType type)
0x65ecf  ldnull
0x65ed0  ret
0x65ed1  ldloc.0
0x65ed2  ldarg.0
0x65ed3  ldarg.1
0x65ed4  ldnull
0x65ed5  call     bool System.Xml.Serialization.TempAssembly::IsSerializerVersionMatch(class [mscorlib]System.Reflection.Assembly serializer, class [mscorlib]System.Type type, string defaultNamespace, string location)
0x65eda  brtrue   loc_65FB1
0x65edf  ldloc.2
0x65ee0  brfalse.s loc_65F05
0x65ee2  ldstr    aXmlserializere// "XmlSerializerExpiredDetails"
0x65ee7  ldc.i4.2
0x65ee8  newarr   [mscorlib]System.Object
0x65eed  dup
0x65eee  ldc.i4.0
0x65eef  ldloc.1
0x65ef0  stelem.ref
0x65ef1  dup
0x65ef2  ldc.i4.1
0x65ef3  ldarg.0
0x65ef4  callvirt instance string [mscorlib]System.Type::get_FullName()
0x65ef9  stelem.ref
0x65efa  call     string System.Xml.Res::GetString(string name, object[] args)
0x65eff  ldc.i4.1
0x65f00  call     void System.Xml.Serialization.TempAssembly::Log(string message, valuetype [System]System.Diagnostics.EventLogEntryType type)
0x65f05  ldnull
0x65f06  ret
0x65f07  ldloc.3
0x65f08  ldc.i4.0
0x65f09  ldelem.ref
0x65f0a  castclass System.Xml.Serialization.XmlSerializerAssemblyAttribute
0x65f0f  stloc.s  9
0x65f11  ldloc.s  9
0x65f13  callvirt instance string System.Xml.Serialization.XmlSerializerAssemblyAttribute::get_AssemblyName()
0x65f18  brfalse.s loc_65F49
0x65f1a  ldloc.s  9
0x65f1c  callvirt instance string System.Xml.Serialization.XmlSerializerAssemblyAttribute::get_CodeBase()
0x65f21  brfalse.s loc_65F49
0x65f23  ldstr    aXmlpregeninval// "XmlPregenInvalidXmlSerializerAssemblyAt"...
0x65f28  ldc.i4.2
0x65f29  newarr   [mscorlib]System.Object
0x65f2e  dup
0x65f2f  ldc.i4.0
0x65f30  ldstr    aAssemblyname// "AssemblyName"
0x65f35  stelem.ref
0x65f36  dup
0x65f37  ldc.i4.1
0x65f38  ldstr    aCodebase// "CodeBase"
0x65f3d  stelem.ref
0x65f3e  call     string System.Xml.Res::GetString(string name, object[] args)
0x65f43  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x65f48  throw
0x65f49  ldloc.s  9
0x65f4b  callvirt instance string System.Xml.Serialization.XmlSerializerAssemblyAttribute::get_AssemblyName()
0x65f50  brfalse.s loc_65F64
0x65f52  ldloc.s  9
0x65f54  callvirt instance string System.Xml.Serialization.XmlSerializerAssemblyAttribute::get_AssemblyName()
0x65f59  stloc.1
0x65f5a  ldloc.1
0x65f5b  ldnull
0x65f5c  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::LoadWithPartialName(string, class [mscorlib]System.Security.Policy.Evidence)
0x65f61  stloc.0
0x65f62  br.s     loc_65FA0
0x65f64  ldloc.s  9
0x65f66  callvirt instance string System.Xml.Serialization.XmlSerializerAssemblyAttribute::get_CodeBase()
0x65f6b  brfalse.s loc_65F8D
0x65f6d  ldloc.s  9
0x65f6f  callvirt instance string System.Xml.Serialization.XmlSerializerAssemblyAttribute::get_CodeBase()
0x65f74  callvirt instance int32 [mscorlib]System.String::get_Length()
0x65f79  ldc.i4.0
0x65f7a  ble.s    loc_65F8D
0x65f7c  ldloc.s  9
0x65f7e  callvirt instance string System.Xml.Serialization.XmlSerializerAssemblyAttribute::get_CodeBase()
0x65f83  stloc.1
0x65f84  ldloc.1
0x65f85  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::LoadFrom(string)
0x65f8a  stloc.0
0x65f8b  br.s     loc_65FA0
0x65f8d  ldarg.0
0x65f8e  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x65f93  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x65f98  stloc.1
0x65f99  ldarg.0
0x65f9a  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x65f9f  stloc.0
0x65fa0  ldloc.0
0x65fa1  ldnull
0x65fa2  call     bool [mscorlib]System.Reflection.Assembly::op_Equality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x65fa7  brfalse.s loc_65FB1
0x65fa9  ldnull
0x65faa  ldloc.1
0x65fab  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor(string, string)
0x65fb0  throw
0x65fb1  ldloc.0
0x65fb2  ldstr    aXmlserializerc// "XmlSerializerContract"
0x65fb7  call     class [mscorlib]System.Type System.Xml.Serialization.TempAssembly::GetTypeFromAssembly(class [mscorlib]System.Reflection.Assembly assembly, string typeName)
0x65fbc  stloc.s  4
0x65fbe  ldarg.2
0x65fbf  ldloc.s  4
0x65fc1  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x65fc6  castclass System.Xml.Serialization.XmlSerializerImplementation
0x65fcb  stind.ref
0x65fcc  ldarg.2
0x65fcd  ldind.ref
0x65fce  ldarg.0
0x65fcf  callvirt instance bool System.Xml.Serialization.XmlSerializerImplementation::CanSerialize(class [mscorlib]System.Type type)
0x65fd4  brfalse.s loc_65FD8
0x65fd6  ldloc.0
0x65fd7  ret
0x65fd8  ldloc.2
0x65fd9  brfalse.s loc_65FFE
0x65fdb  ldstr    aXmlserializere// "XmlSerializerExpiredDetails"
0x65fe0  ldc.i4.2
0x65fe1  newarr   [mscorlib]System.Object
0x65fe6  dup
0x65fe7  ldc.i4.0
0x65fe8  ldloc.1
0x65fe9  stelem.ref
0x65fea  dup
0x65feb  ldc.i4.1
0x65fec  ldarg.0
0x65fed  callvirt instance string [mscorlib]System.Type::get_FullName()
0x65ff2  stelem.ref
0x65ff3  call     string System.Xml.Res::GetString(string name, object[] args)
0x65ff8  ldc.i4.1
0x65ff9  call     void System.Xml.Serialization.TempAssembly::Log(string message, valuetype [System]System.Diagnostics.EventLogEntryType type)
0x65ffe  ldnull
0x65fff  ret
0x66000  ldloc.s  8
0x66002  ret
```
