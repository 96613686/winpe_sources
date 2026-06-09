# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendDateFormats

- ea: `0x56d0`
- end: `0x59a1`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendDateFormats`
- size: `721`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x53a0`

## callees

- `0x56d0`
- `0x59b0`

## string_xrefs

- `0x56e1`: `cultureName`

## pseudocode

```c

```

## disassembly

```asm
0x56d0  ldarg.0
0x56d1  brtrue.s loc_56DE
0x56d3  ldstr    aBuf// "buf"
0x56d8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x56dd  throw
0x56de  ldarg.1
0x56df  brtrue.s loc_56EC
0x56e1  ldstr    aCulturename_0// "cultureName"
0x56e6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x56eb  throw
0x56ec  ldloca.s 0
0x56ee  ldc.i4   0x7D7
0x56f3  ldc.i4.4
0x56f4  ldc.i4.s 0x15
0x56f6  ldc.i4.s 0x12
0x56f8  ldc.i4.7
0x56f9  ldc.i4.0
0x56fa  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32, int32, int32, int32)
0x56ff  ldarg.0
0x5700  ldstr    aVarAszdateform// "var aszDateFormats ="
0x5705  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x570a  pop
0x570b  ldarg.0
0x570c  ldstr    asc_22F1A// "["
0x5711  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x5716  pop
0x5717  ldarg.1
0x5718  ldstr    aJaJp// "ja-JP"
0x571d  ldc.i4.5
0x571e  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5723  brfalse.s loc_5791
0x5725  ldarg.0
0x5726  ldloc.0
0x5727  ldsfld   string [mscorlib]System.String::Empty
0x572c  ldarg.1
0x572d  ldnull
0x572e  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5733  ldarg.0
0x5734  ldstr    asc_2030E// ","
0x5739  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x573e  pop
0x573f  ldarg.0
0x5740  ldloc.0
0x5741  ldstr    aYyyyMD// "yyyy'年'M'月'd'日'"
0x5746  ldarg.1
0x5747  ldnull
0x5748  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x574d  ldarg.0
0x574e  ldstr    asc_2030E// ","
0x5753  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5758  pop
0x5759  ldarg.0
0x575a  ldloc.0
0x575b  ldstr    aYyyyMmDd// "yyyy/MM/dd"
0x5760  ldarg.1
0x5761  ldnull
0x5762  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5767  ldarg.0
0x5768  ldstr    asc_2030E// ","
0x576d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5772  pop
0x5773  ldarg.0
0x5774  ldloc.0
0x5775  ldstr    aGgYMD// "gg y'年'M'月'd'日'"
0x577a  ldarg.1
0x577b  ldstr    aJapanese// "Japanese"
0x5780  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5785  ldarg.0
0x5786  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x578b  pop
0x578c  br       loc_5994
0x5791  ldarg.0
0x5792  ldloc.0
0x5793  ldsfld   string [mscorlib]System.String::Empty
0x5798  ldarg.1
0x5799  ldnull
0x579a  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x579f  ldarg.0
0x57a0  ldstr    asc_2030E// ","
0x57a5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x57aa  pop
0x57ab  ldarg.0
0x57ac  ldloc.0
0x57ad  ldstr    aDdddMmmmDdYyyy// "dddd, MMMM dd, yyyy"
0x57b2  ldarg.1
0x57b3  ldnull
0x57b4  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x57b9  ldarg.0
0x57ba  ldstr    asc_2030E// ","
0x57bf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x57c4  pop
0x57c5  ldarg.0
0x57c6  ldloc.0
0x57c7  ldstr    aMmmmDdYyyy// "MMMM dd, yyyy"
0x57cc  ldarg.1
0x57cd  ldnull
0x57ce  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x57d3  ldarg.0
0x57d4  ldstr    asc_2030E// ","
0x57d9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x57de  pop
0x57df  ldarg.0
0x57e0  ldloc.0
0x57e1  ldstr    aDdMmmmYyyy// "dd MMMM, yyyy"
0x57e6  ldarg.1
0x57e7  ldnull
0x57e8  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x57ed  ldarg.0
0x57ee  ldstr    asc_2030E// ","
0x57f3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x57f8  pop
0x57f9  ldarg.0
0x57fa  ldloc.0
0x57fb  ldstr    aDdMmmYyyy// "dd MMM yyyy"
0x5800  ldarg.1
0x5801  ldnull
0x5802  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5807  ldarg.0
0x5808  ldstr    asc_2030E// ","
0x580d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5812  pop
0x5813  ldarg.0
0x5814  ldloc.0
0x5815  ldstr    aDdMmmmYyyy_0// "dd MMMM yyyy"
0x581a  ldarg.1
0x581b  ldnull
0x581c  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5821  ldarg.0
0x5822  ldstr    asc_2030E// ","
0x5827  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x582c  pop
0x582d  ldarg.0
0x582e  ldloc.0
0x582f  ldstr    aDdMmYy// "dd/MM/yy"
0x5834  ldarg.1
0x5835  ldnull
0x5836  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x583b  ldarg.0
0x583c  ldstr    asc_2030E// ","
0x5841  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5846  pop
0x5847  ldarg.0
0x5848  ldloc.0
0x5849  ldstr    aMmDdYy// "MM/dd/yy"
0x584e  ldarg.1
0x584f  ldnull
0x5850  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5855  ldarg.0
0x5856  ldstr    asc_2030E// ","
0x585b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5860  pop
0x5861  ldarg.0
0x5862  ldloc.0
0x5863  ldstr    aMmDdYy_0// "MM.dd.yy"
0x5868  ldarg.1
0x5869  ldnull
0x586a  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x586f  ldarg.0
0x5870  ldstr    asc_2030E// ","
0x5875  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x587a  pop
0x587b  ldarg.0
0x587c  ldloc.0
0x587d  ldstr    aMmDdYyyy// "MM.dd.yyyy"
0x5882  ldarg.1
0x5883  ldnull
0x5884  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5889  ldarg.0
0x588a  ldstr    asc_2030E// ","
0x588f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5894  pop
0x5895  ldarg.0
0x5896  ldloc.0
0x5897  ldstr    aDdMmmYyyy_0// "dd-MMM-yyyy"
0x589c  ldarg.1
0x589d  ldnull
0x589e  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x58a3  ldarg.0
0x58a4  ldstr    asc_2030E// ","
0x58a9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58ae  pop
0x58af  ldarg.0
0x58b0  ldloc.0
0x58b1  ldstr    aYyyyMmDd_0// "yyyy-MM-dd"
0x58b6  ldarg.1
0x58b7  ldnull
0x58b8  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x58bd  ldarg.0
0x58be  ldstr    asc_2030E// ","
0x58c3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58c8  pop
0x58c9  ldarg.0
0x58ca  ldloc.0
0x58cb  ldstr    aYyMmDd// "yy-MM-dd"
0x58d0  ldarg.1
0x58d1  ldnull
0x58d2  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x58d7  ldarg.0
0x58d8  ldstr    asc_2030E// ","
0x58dd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58e2  pop
0x58e3  ldarg.0
0x58e4  ldloc.0
0x58e5  ldstr    aDdMmYy_0// "dd-MM-yy"
0x58ea  ldarg.1
0x58eb  ldnull
0x58ec  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x58f1  ldarg.0
0x58f2  ldstr    asc_2030E// ","
0x58f7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58fc  pop
0x58fd  ldarg.0
0x58fe  ldloc.0
0x58ff  ldstr    aDdMmYyyy// "dd-MM-yyyy"
0x5904  ldarg.1
0x5905  ldnull
0x5906  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x590b  ldarg.0
0x590c  ldstr    asc_2030E// ","
0x5911  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5916  pop
0x5917  ldarg.0
0x5918  ldloc.0
0x5919  ldstr    aMmmmYyyy// "MMMM, yyyy"
0x591e  ldarg.1
0x591f  ldnull
0x5920  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5925  ldarg.0
0x5926  ldstr    asc_2030E// ","
0x592b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5930  pop
0x5931  ldarg.0
0x5932  ldloc.0
0x5933  ldstr    aMmmYy// "MMM-yy"
0x5938  ldarg.1
0x5939  ldnull
0x593a  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x593f  ldarg.0
0x5940  ldstr    asc_2030E// ","
0x5945  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x594a  pop
0x594b  ldarg.0
0x594c  ldloc.0
0x594d  ldstr    aDdddMmmmDdYyyy_0// "dddd MMMM dd,yyyy"
0x5952  ldarg.1
0x5953  ldnull
0x5954  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5959  ldarg.0
0x595a  ldstr    asc_2030E// ","
0x595f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5964  pop
0x5965  ldarg.0
0x5966  ldloc.0
0x5967  ldstr    aDdddDdMmmmYyyy// "dddd, dd MMMM yyyy"
0x596c  ldarg.1
0x596d  ldnull
0x596e  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5973  ldarg.0
0x5974  ldstr    asc_2030E// ","
0x5979  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x597e  pop
0x597f  ldarg.0
0x5980  ldloc.0
0x5981  ldstr    aDdddDdMmmmYyyy_0// "dddd, dd. MMMM yyyy"
0x5986  ldarg.1
0x5987  ldnull
0x5988  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x598d  ldarg.0
0x598e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x5993  pop
0x5994  ldarg.0
0x5995  ldstr    asc_2304A// "];"
0x599a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x599f  pop
0x59a0  ret
```
