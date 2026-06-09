# Microsoft.SharePoint.Client.ClientMethodsProcessor::CreateResult

- ea: `0xb070`
- end: `0xb1c4`
- name: `Microsoft.SharePoint.Client.ClientMethodsProcessor::CreateResult`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa7b0`

## callees

- `0x5c80`
- `0x9840`
- `0xb070`
- `0xdae0`
- `0x29d10`
- `0x29d30`
- `0x29d50`
- `0x29d70`
- `0x29d80`
- `0x2a010`
- `0x2c310`

## string_xrefs

- `0xb070`: `application/json; charset=utf-8`
- `0xb0a3`: `<http://sharepoint.microsoft.com/client/`
- `0xb0f1`: `application/jop+json;charset=utf-8;type="application/json"`
- `0xb196`: `multipart/related;type="application/jop+json";boundary="{0}";start="{1}";start-info="application/json"`

## pseudocode

```c

```

## disassembly

```asm
0xb070  ldstr    aApplicationJso// "application/json; charset=utf-8"
0xb075  stloc.0
0xb076  ldarg.0
0xb077  ldfld    class Microsoft.SharePoint.Utilities.ChunkStringBuilder Microsoft.SharePoint.Client.ClientMethodsProcessor::m_sb
0xb07c  callvirt instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.ChunkStringBuilder::CreateUTF8ReadonlyStream()
0xb081  stloc.1
0xb082  ldarg.0
0xb083  call     instance class [mscorlib]System.Collections.Generic.IList`1<class AttachmentStream> Microsoft.SharePoint.Client.ClientMethodsProcessor::get_OutputStreams()
0xb088  brfalse  loc_B1BC
0xb08d  ldarg.0
0xb08e  call     instance class [mscorlib]System.Collections.Generic.IList`1<class AttachmentStream> Microsoft.SharePoint.Client.ClientMethodsProcessor::get_OutputStreams()
0xb093  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class AttachmentStream>::get_Count()
0xb098  brfalse  loc_B1BC
0xb09d  call     string Microsoft.SharePoint.Utilities.Mime.MimeUtility::CreateBoundary()
0xb0a2  stloc.2
0xb0a3  ldstr    aHttpSharepoint// "<http://sharepoint.microsoft.com/client"...
0xb0a8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xb0ad  stloc.s  8
0xb0af  ldloca.s 8
0xb0b1  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0xb0b6  stloc.s  9
0xb0b8  ldloca.s 9
0xb0ba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb0bf  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0xb0c4  ldstr    asc_40C3E// ">"
0xb0c9  call     string [mscorlib]System.String::Concat(string, string, string)
0xb0ce  stloc.3
0xb0cf  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Mime.MimePart>::.ctor()
0xb0d4  stloc.s  4
0xb0d6  ldloc.s  4
0xb0d8  newobj   instance void Microsoft.SharePoint.Utilities.Mime.MimePart::.ctor()
0xb0dd  stloc.s  7
0xb0df  ldloc.s  7
0xb0e1  ldloc.3
0xb0e2  callvirt instance void Microsoft.SharePoint.Utilities.Mime.MimePart::set_ContentId(string value)
0xb0e7  ldloc.s  7
0xb0e9  ldc.i4.1
0xb0ea  callvirt instance void Microsoft.SharePoint.Utilities.Mime.MimePart::set_ContentTransferEncoding(valuetype Microsoft.SharePoint.Utilities.Mime.ContentTransferEncoding value)
0xb0ef  ldloc.s  7
0xb0f1  ldstr    aApplicationJop// "application/jop+json;charset=utf-8;type"...
0xb0f6  callvirt instance void Microsoft.SharePoint.Utilities.Mime.MimePart::set_ContentType(string value)
0xb0fb  ldloc.s  7
0xb0fd  ldloc.1
0xb0fe  callvirt instance void Microsoft.SharePoint.Utilities.Mime.MimePart::set_Stream(class [mscorlib]System.IO.Stream value)
0xb103  ldloc.s  7
0xb105  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Mime.MimePart>::Add(var<u1>)
0xb10a  ldarg.0
0xb10b  call     instance class [mscorlib]System.Collections.Generic.IList`1<class AttachmentStream> Microsoft.SharePoint.Client.ClientMethodsProcessor::get_OutputStreams()
0xb110  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class AttachmentStream>::GetEnumerator()
0xb115  stloc.s  0xA
0xb117  br.s     loc_B171
0xb119  ldloc.s  0xA
0xb11b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class AttachmentStream>::get_Current()
0xb120  stloc.s  5
0xb122  ldloc.s  4
0xb124  newobj   instance void Microsoft.SharePoint.Utilities.Mime.MimePart::.ctor()
0xb129  stloc.s  6
0xb12b  ldloc.s  6
0xb12d  ldstr    asc_40CB8// "<"
0xb132  ldloc.s  5
0xb134  ldfld    string AttachmentStream::Id
0xb139  ldstr    asc_40C3E// ">"
0xb13e  call     string [mscorlib]System.String::Concat(string, string, string)
0xb143  callvirt instance void Microsoft.SharePoint.Utilities.Mime.MimePart::set_ContentId(string value)
0xb148  ldloc.s  6
0xb14a  ldc.i4.2
0xb14b  callvirt instance void Microsoft.SharePoint.Utilities.Mime.MimePart::set_ContentTransferEncoding(valuetype Microsoft.SharePoint.Utilities.Mime.ContentTransferEncoding value)
0xb150  ldloc.s  6
0xb152  ldstr    aApplicationOct// "application/octet-stream"
0xb157  callvirt instance void Microsoft.SharePoint.Utilities.Mime.MimePart::set_ContentType(string value)
0xb15c  ldloc.s  6
0xb15e  ldloc.s  5
0xb160  ldfld    class [mscorlib]System.IO.Stream AttachmentStream::Stream
0xb165  callvirt instance void Microsoft.SharePoint.Utilities.Mime.MimePart::set_Stream(class [mscorlib]System.IO.Stream value)
0xb16a  ldloc.s  6
0xb16c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Mime.MimePart>::Add(var<u1>)
0xb171  ldloc.s  0xA
0xb173  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb178  brtrue.s loc_B119
0xb17a  leave.s  loc_B188
0xb17c  ldloc.s  0xA
0xb17e  brfalse.s loc_B187
0xb180  ldloc.s  0xA
0xb182  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb187  endfinally
0xb188  ldloc.2
0xb189  ldloc.s  4
0xb18b  newobj   instance void Microsoft.SharePoint.Utilities.Mime.MimeMergedStream::.ctor(string boundary, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Utilities.Mime.MimePart> parts)
0xb190  stloc.1
0xb191  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb196  ldstr    aMultipartRelat// "multipart/related;type=\"application/jo"...
0xb19b  ldc.i4.2
0xb19c  newarr   [mscorlib]System.Object
0xb1a1  stloc.s  0xB
0xb1a3  ldloc.s  0xB
0xb1a5  ldc.i4.0
0xb1a6  ldloc.2
0xb1a7  stelem.ref
0xb1a8  ldloc.s  0xB
0xb1aa  ldc.i4.1
0xb1ab  ldloc.3
0xb1ac  stelem.ref
0xb1ad  ldloc.s  0xB
0xb1af  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb1b4  stloc.0
0xb1b5  ldarg.0
0xb1b6  ldnull
0xb1b7  stfld    class [mscorlib]System.Collections.Generic.List`1<class AttachmentStream> Microsoft.SharePoint.Client.ClientMethodsProcessor::m_ouputStreams
0xb1bc  ldloc.0
0xb1bd  ldloc.1
0xb1be  newobj   instance void Microsoft.SharePoint.Client.ClientMethodsProcessorResult::.ctor(string contentType, class [mscorlib]System.IO.Stream outputStream)
0xb1c3  ret
```
