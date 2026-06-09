# Microsoft.ReportingServices.Diagnostics.Task::EnsureValidScheduleXml

- ea: `0xd6d0`
- end: `0xd82a`
- name: `Microsoft.ReportingServices.Diagnostics.Task::EnsureValidScheduleXml`
- size: `346`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xd530`
- `0xd6d0`

## pseudocode

```c

```

## disassembly

```asm
0xd6d0  ldarg.0
0xd6d1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd6d6  brtrue.s loc_D6E0
0xd6d8  ldarg.0
0xd6d9  call     bool Microsoft.ReportingServices.Diagnostics.Task::IsSharedSchedule(string xml)
0xd6de  brfalse.s loc_D6E2
0xd6e0  ldarg.0
0xd6e1  ret
0xd6e2  ldarg.0
0xd6e3  stloc.0
0xd6e4  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xd6e9  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentCulture()
0xd6ee  stloc.1
0xd6ef  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xd6f4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd6f9  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0xd6fe  ldloc.0
0xd6ff  ldstr    aFirstWeek// "FIRST_WEEK"
0xd704  callvirt instance bool [mscorlib]System.String::Contains(string)
0xd709  brfalse.s loc_D71C
0xd70b  ldloc.0
0xd70c  ldstr    aFirstWeek// "FIRST_WEEK"
0xd711  ldstr    aFirstweek// "FirstWeek"
0xd716  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xd71b  stloc.0
0xd71c  ldloc.0
0xd71d  ldstr    aSecondWeek// "SECOND_WEEK"
0xd722  callvirt instance bool [mscorlib]System.String::Contains(string)
0xd727  brfalse.s loc_D73A
0xd729  ldloc.0
0xd72a  ldstr    aSecondWeek// "SECOND_WEEK"
0xd72f  ldstr    aSecondweek// "SecondWeek"
0xd734  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xd739  stloc.0
0xd73a  ldloc.0
0xd73b  ldstr    aThirdWeek// "THIRD_WEEK"
0xd740  callvirt instance bool [mscorlib]System.String::Contains(string)
0xd745  brfalse.s loc_D758
0xd747  ldloc.0
0xd748  ldstr    aThirdWeek// "THIRD_WEEK"
0xd74d  ldstr    aThirdweek// "ThirdWeek"
0xd752  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xd757  stloc.0
0xd758  ldloc.0
0xd759  ldstr    aFourthWeek// "FOURTH_WEEK"
0xd75e  callvirt instance bool [mscorlib]System.String::Contains(string)
0xd763  brfalse.s loc_D776
0xd765  ldloc.0
0xd766  ldstr    aFourthWeek// "FOURTH_WEEK"
0xd76b  ldstr    aFourthweek// "FourthWeek"
0xd770  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xd775  stloc.0
0xd776  ldloc.0
0xd777  ldstr    aLastWeek// "LAST_WEEK"
0xd77c  callvirt instance bool [mscorlib]System.String::Contains(string)
0xd781  brfalse.s loc_D794
0xd783  ldloc.0
0xd784  ldstr    aLastWeek// "LAST_WEEK"
0xd789  ldstr    aLastweek// "LastWeek"
0xd78e  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xd793  stloc.0
0xd794  ldloc.0
0xd795  ldstr    aTrue// "True"
0xd79a  ldstr    aTrue_0// "true"
0xd79f  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xd7a4  stloc.0
0xd7a5  ldloc.0
0xd7a6  ldstr    aFalse// "False"
0xd7ab  ldstr    aFalse_0// "false"
0xd7b0  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xd7b5  stloc.0
0xd7b6  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0xd7bb  dup
0xd7bc  ldloc.0
0xd7bd  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0xd7c2  dup
0xd7c3  ldstr    aEnddate// "EndDate"
0xd7c8  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlDocument::GetElementsByTagName(string)
0xd7cd  stloc.2
0xd7ce  ldloc.2
0xd7cf  brfalse.s loc_D80E
0xd7d1  ldloc.2
0xd7d2  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0xd7d7  ldc.i4.0
0xd7d8  ble.s    loc_D80E
0xd7da  ldloc.2
0xd7db  ldc.i4.0
0xd7dc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xd7e1  ldloc.2
0xd7e2  ldc.i4.0
0xd7e3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xd7e8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xd7ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd7f2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0xd7f7  stloc.3
0xd7f8  ldloca.s 3
0xd7fa  ldstr    aYyyyMmDd// "yyyy-MM-dd"
0xd7ff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd804  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0xd809  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0xd80e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0xd813  stloc.0
0xd814  leave.s  loc_D828
0xd816  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MalformedXmlException::.ctor(class [System.Xml]System.Xml.XmlException)
0xd81b  throw
0xd81c  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xd821  ldloc.1
0xd822  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0xd827  endfinally
0xd828  ldloc.0
0xd829  ret
```
