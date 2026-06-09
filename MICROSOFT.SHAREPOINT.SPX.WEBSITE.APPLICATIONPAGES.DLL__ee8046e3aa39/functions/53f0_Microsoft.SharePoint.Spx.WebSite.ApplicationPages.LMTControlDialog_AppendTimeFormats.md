# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendTimeFormats

- ea: `0x53f0`
- end: `0x56c5`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendTimeFormats`
- size: `725`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x53a0`

## callees

- `0x53f0`
- `0x59b0`

## string_xrefs

- `0x5401`: `cultureName`

## pseudocode

```c

```

## disassembly

```asm
0x53f0  ldarg.0
0x53f1  brtrue.s loc_53FE
0x53f3  ldstr    aBuf// "buf"
0x53f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x53fd  throw
0x53fe  ldarg.1
0x53ff  brtrue.s loc_540C
0x5401  ldstr    aCulturename_0// "cultureName"
0x5406  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x540b  throw
0x540c  ldloca.s 0
0x540e  ldc.i4   0x7D7
0x5413  ldc.i4.4
0x5414  ldc.i4.s 0x15
0x5416  ldc.i4.s 0x12
0x5418  ldc.i4.7
0x5419  ldc.i4.0
0x541a  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32, int32, int32, int32)
0x541f  ldarg.0
0x5420  ldstr    aVarAsztimeform// "var aszTimeFormats ="
0x5425  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x542a  pop
0x542b  ldarg.0
0x542c  ldstr    asc_22F1A// "["
0x5431  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x5436  pop
0x5437  ldarg.1
0x5438  ldstr    aJaJp// "ja-JP"
0x543d  ldc.i4.5
0x543e  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5443  brfalse  loc_5532
0x5448  ldarg.0
0x5449  ldloc.0
0x544a  ldsfld   string [mscorlib]System.String::Empty
0x544f  ldarg.1
0x5450  ldnull
0x5451  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5456  ldarg.0
0x5457  ldstr    asc_2030E// ","
0x545c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5461  pop
0x5462  ldarg.0
0x5463  ldloc.0
0x5464  ldstr    aTtHhMmSs// "tt hh:mm:ss"
0x5469  ldarg.1
0x546a  ldnull
0x546b  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5470  ldarg.0
0x5471  ldstr    asc_2030E// ","
0x5476  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x547b  pop
0x547c  ldarg.0
0x547d  ldloc.0
0x547e  ldstr    aTtHhMm// "tt hh:mm"
0x5483  ldarg.1
0x5484  ldnull
0x5485  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x548a  ldarg.0
0x548b  ldstr    asc_2030E// ","
0x5490  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5495  pop
0x5496  ldarg.0
0x5497  ldloc.0
0x5498  ldstr    aHhMmSs// "HH:mm:ss"
0x549d  ldarg.1
0x549e  ldnull
0x549f  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x54a4  ldarg.0
0x54a5  ldstr    asc_2030E// ","
0x54aa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x54af  pop
0x54b0  ldarg.0
0x54b1  ldloc.0
0x54b2  ldstr    aHhMm// "HH:mm"
0x54b7  ldarg.1
0x54b8  ldnull
0x54b9  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x54be  ldarg.0
0x54bf  ldstr    asc_2030E// ","
0x54c4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x54c9  pop
0x54ca  ldarg.0
0x54cb  ldloc.0
0x54cc  ldstr    aTtHhMmSsTz// "tt hh:mm:ss TZ"
0x54d1  ldarg.1
0x54d2  ldnull
0x54d3  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x54d8  ldarg.0
0x54d9  ldstr    asc_2030E// ","
0x54de  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x54e3  pop
0x54e4  ldarg.0
0x54e5  ldloc.0
0x54e6  ldstr    aTtHhMmTz// "tt hh:mm TZ"
0x54eb  ldarg.1
0x54ec  ldnull
0x54ed  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x54f2  ldarg.0
0x54f3  ldstr    asc_2030E// ","
0x54f8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x54fd  pop
0x54fe  ldarg.0
0x54ff  ldloc.0
0x5500  ldstr    aHhMmSsTz// "HH:mm:ss TZ"
0x5505  ldarg.1
0x5506  ldnull
0x5507  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x550c  ldarg.0
0x550d  ldstr    asc_2030E// ","
0x5512  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5517  pop
0x5518  ldarg.0
0x5519  ldloc.0
0x551a  ldstr    aHhMmTz// "HH:mm TZ"
0x551f  ldarg.1
0x5520  ldnull
0x5521  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5526  ldarg.0
0x5527  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x552c  pop
0x552d  br       loc_56B8
0x5532  ldarg.1
0x5533  ldstr    aFrFr// "fr-FR"
0x5538  ldc.i4.5
0x5539  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x553e  brtrue.s loc_5551
0x5540  ldarg.1
0x5541  ldstr    aDeDe// "de-DE"
0x5546  ldc.i4.5
0x5547  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x554c  brfalse  loc_55D3
0x5551  ldarg.0
0x5552  ldloc.0
0x5553  ldsfld   string [mscorlib]System.String::Empty
0x5558  ldarg.1
0x5559  ldnull
0x555a  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x555f  ldarg.0
0x5560  ldstr    asc_2030E// ","
0x5565  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x556a  pop
0x556b  ldarg.0
0x556c  ldloc.0
0x556d  ldstr    aHhMmSs// "HH:mm:ss"
0x5572  ldarg.1
0x5573  ldnull
0x5574  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5579  ldarg.0
0x557a  ldstr    asc_2030E// ","
0x557f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5584  pop
0x5585  ldarg.0
0x5586  ldloc.0
0x5587  ldstr    aHhMm// "HH:mm"
0x558c  ldarg.1
0x558d  ldnull
0x558e  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5593  ldarg.0
0x5594  ldstr    asc_2030E// ","
0x5599  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x559e  pop
0x559f  ldarg.0
0x55a0  ldloc.0
0x55a1  ldstr    aHhMmSsTz// "HH:mm:ss TZ"
0x55a6  ldarg.1
0x55a7  ldnull
0x55a8  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x55ad  ldarg.0
0x55ae  ldstr    asc_2030E// ","
0x55b3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x55b8  pop
0x55b9  ldarg.0
0x55ba  ldloc.0
0x55bb  ldstr    aHhMmTz// "HH:mm TZ"
0x55c0  ldarg.1
0x55c1  ldnull
0x55c2  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x55c7  ldarg.0
0x55c8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x55cd  pop
0x55ce  br       loc_56B8
0x55d3  ldarg.0
0x55d4  ldloc.0
0x55d5  ldsfld   string [mscorlib]System.String::Empty
0x55da  ldarg.1
0x55db  ldnull
0x55dc  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x55e1  ldarg.0
0x55e2  ldstr    asc_2030E// ","
0x55e7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x55ec  pop
0x55ed  ldarg.0
0x55ee  ldloc.0
0x55ef  ldstr    aHhMmSsTt// "hh:mm:ss tt"
0x55f4  ldarg.1
0x55f5  ldnull
0x55f6  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x55fb  ldarg.0
0x55fc  ldstr    asc_2030E// ","
0x5601  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5606  pop
0x5607  ldarg.0
0x5608  ldloc.0
0x5609  ldstr    aHhMmTt// "hh:mm tt"
0x560e  ldarg.1
0x560f  ldnull
0x5610  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5615  ldarg.0
0x5616  ldstr    asc_2030E// ","
0x561b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5620  pop
0x5621  ldarg.0
0x5622  ldloc.0
0x5623  ldstr    aHhMmSs// "HH:mm:ss"
0x5628  ldarg.1
0x5629  ldnull
0x562a  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x562f  ldarg.0
0x5630  ldstr    asc_2030E// ","
0x5635  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x563a  pop
0x563b  ldarg.0
0x563c  ldloc.0
0x563d  ldstr    aHhMm// "HH:mm"
0x5642  ldarg.1
0x5643  ldnull
0x5644  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5649  ldarg.0
0x564a  ldstr    asc_2030E// ","
0x564f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5654  pop
0x5655  ldarg.0
0x5656  ldloc.0
0x5657  ldstr    aHhMmSsTtTz// "hh:mm:ss tt TZ"
0x565c  ldarg.1
0x565d  ldnull
0x565e  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5663  ldarg.0
0x5664  ldstr    asc_2030E// ","
0x5669  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x566e  pop
0x566f  ldarg.0
0x5670  ldloc.0
0x5671  ldstr    aHhMmTtTz// "hh:mm tt TZ"
0x5676  ldarg.1
0x5677  ldnull
0x5678  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x567d  ldarg.0
0x567e  ldstr    asc_2030E// ","
0x5683  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5688  pop
0x5689  ldarg.0
0x568a  ldloc.0
0x568b  ldstr    aHhMmSsTz// "HH:mm:ss TZ"
0x5690  ldarg.1
0x5691  ldnull
0x5692  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x5697  ldarg.0
0x5698  ldstr    asc_2030E// ","
0x569d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x56a2  pop
0x56a3  ldarg.0
0x56a4  ldloc.0
0x56a5  ldstr    aHhMmTz// "HH:mm TZ"
0x56aa  ldarg.1
0x56ab  ldnull
0x56ac  call     void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LMTControlDialog::AppendFormat(class [mscorlib]System.Text.StringBuilder buf, valuetype [mscorlib]System.DateTime dt, string format, string cultureName, string calendarName)
0x56b1  ldarg.0
0x56b2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x56b7  pop
0x56b8  ldarg.0
0x56b9  ldstr    asc_2304A// "];"
0x56be  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x56c3  pop
0x56c4  ret
```
