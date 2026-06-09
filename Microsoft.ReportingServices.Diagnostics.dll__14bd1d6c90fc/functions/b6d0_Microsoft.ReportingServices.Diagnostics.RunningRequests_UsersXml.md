# Microsoft.ReportingServices.Diagnostics.RunningRequests::UsersXml

- ea: `0xb6d0`
- end: `0xb7a1`
- name: `Microsoft.ReportingServices.Diagnostics.RunningRequests::UsersXml`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xb6d0`
- `0xb8c0`
- `0xbc80`

## pseudocode

```c

```

## disassembly

```asm
0xb6d0  ldarg.0
0xb6d1  stloc.0
0xb6d2  ldc.i4.0
0xb6d3  stloc.1
0xb6d4  ldloc.0
0xb6d5  ldloca.s 1
0xb6d7  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xb6dc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb6e1  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0xb6e6  stloc.2
0xb6e7  ldloc.2
0xb6e8  newobj   instance void [System.Xml]System.Xml.XmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0xb6ed  stloc.3
0xb6ee  ldloc.3
0xb6ef  ldstr    aUsers// "Users"
0xb6f4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xb6f9  ldarg.0
0xb6fa  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningRequests::get_UserInfoProp()
0xb6ff  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0xb704  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0xb709  ldc.i4.0
0xb70a  ble.s    loc_B784
0xb70c  ldarg.0
0xb70d  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningRequests::get_UserInfoProp()
0xb712  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0xb717  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xb71c  stloc.s  4
0xb71e  br.s     loc_B764
0xb720  ldloc.s  4
0xb722  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xb727  castclass [mscorlib]System.String
0xb72c  stloc.s  5
0xb72e  ldloc.3
0xb72f  ldstr    aUser// "User"
0xb734  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xb739  ldloc.3
0xb73a  ldstr    aName_0// "Name"
0xb73f  ldloc.s  5
0xb741  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xb746  ldarg.0
0xb747  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningRequests::get_UserInfoProp()
0xb74c  ldloc.s  5
0xb74e  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xb753  castclass Microsoft.ReportingServices.Diagnostics.UserInfo
0xb758  ldloc.3
0xb759  callvirt instance void Microsoft.ReportingServices.Diagnostics.UserInfo::ToXml(class [System.Xml]System.Xml.XmlTextWriter writer)
0xb75e  ldloc.3
0xb75f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb764  ldloc.s  4
0xb766  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb76b  brtrue.s loc_B720
0xb76d  leave.s  loc_B784
0xb76f  ldloc.s  4
0xb771  isinst   [mscorlib]System.IDisposable
0xb776  stloc.s  6
0xb778  ldloc.s  6
0xb77a  brfalse.s loc_B783
0xb77c  ldloc.s  6
0xb77e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb783  endfinally
0xb784  ldloc.3
0xb785  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb78a  ldloc.2
0xb78b  callvirt instance string [mscorlib]System.Object::ToString()
0xb790  stloc.s  7
0xb792  leave.s  loc_B79E
0xb794  ldloc.1
0xb795  brfalse.s loc_B79D
0xb797  ldloc.0
0xb798  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xb79d  endfinally
0xb79e  ldloc.s  7
0xb7a0  ret
```
