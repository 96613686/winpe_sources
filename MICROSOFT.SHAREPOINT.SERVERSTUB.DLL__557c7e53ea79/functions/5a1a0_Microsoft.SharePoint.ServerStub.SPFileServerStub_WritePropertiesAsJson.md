# Microsoft.SharePoint.ServerStub.SPFileServerStub::WritePropertiesAsJson

- ea: `0x5a1a0`
- end: `0x5a677`
- name: `Microsoft.SharePoint.ServerStub.SPFileServerStub::WritePropertiesAsJson`
- size: `1239`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5a1a0`

## string_xrefs

- `0x5a1b5`: `CheckInComment`
- `0x5a1c1`: `CheckInComment`
- `0x5a1cc`: `CheckInComment`
- `0x5a1e4`: `CheckInComment`
- `0x5a3bf`: `LinkingUri`
- `0x5a3cb`: `LinkingUri`
- `0x5a3d6`: `LinkingUri`
- `0x5a3ee`: `LinkingUri`
- `0x5a3f9`: `LinkingUrl`
- `0x5a405`: `LinkingUrl`
- `0x5a410`: `LinkingUrl`
- `0x5a428`: `LinkingUrl`
- `0x5a51b`: `TimeCreated`
- `0x5a527`: `TimeCreated`
- `0x5a532`: `TimeCreated`
- `0x5a54a`: `TimeCreated`

## pseudocode

```c

```

## disassembly

```asm
0x5a1a0  ldarg.2
0x5a1a1  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFile
0x5a1a6  stloc.0
0x5a1a7  ldloc.0
0x5a1a8  brtrue.s loc_5A1AB
0x5a1aa  ret
0x5a1ab  ldarg.0
0x5a1ac  ldarg.1
0x5a1ad  ldarg.2
0x5a1ae  ldarg.3
0x5a1af  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a1b4  ldarg.0
0x5a1b5  ldstr    aCheckincomment_0// "CheckInComment"
0x5a1ba  ldarg.3
0x5a1bb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a1c0  ldarg.1
0x5a1c1  ldstr    aCheckincomment_0// "CheckInComment"
0x5a1c6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5a1cb  ldarg.3
0x5a1cc  ldstr    aCheckincomment_0// "CheckInComment"
0x5a1d1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5a1d6  ldarg.1
0x5a1d7  ldloc.0
0x5a1d8  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_CheckInComment()
0x5a1dd  ldarg.3
0x5a1de  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a1e3  ldarg.3
0x5a1e4  ldstr    aCheckincomment_0// "CheckInComment"
0x5a1e9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5a1ee  ldarg.0
0x5a1ef  ldstr    aCheckouttype// "CheckOutType"
0x5a1f4  ldarg.3
0x5a1f5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a1fa  ldarg.1
0x5a1fb  ldstr    aCheckouttype// "CheckOutType"
0x5a200  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5a205  ldarg.3
0x5a206  ldstr    aCheckouttype// "CheckOutType"
0x5a20b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5a210  ldarg.1
0x5a211  ldloc.0
0x5a212  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFile/SPCheckOutType [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_CheckOutType()
0x5a217  ldarg.3
0x5a218  call     T0x2B0001B6
0x5a21d  ldarg.3
0x5a21e  ldstr    aCheckouttype// "CheckOutType"
0x5a223  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5a228  ldarg.0
0x5a229  ldstr    aContenttag// "ContentTag"
0x5a22e  ldarg.3
0x5a22f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a234  ldarg.1
0x5a235  ldstr    aContenttag// "ContentTag"
0x5a23a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5a23f  ldarg.3
0x5a240  ldstr    aContenttag// "ContentTag"
0x5a245  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5a24a  ldarg.1
0x5a24b  ldloc.0
0x5a24c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_ContentTag()
0x5a251  ldarg.3
0x5a252  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a257  ldarg.3
0x5a258  ldstr    aContenttag// "ContentTag"
0x5a25d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5a262  ldarg.0
0x5a263  ldstr    aCustomizedpage// "CustomizedPageStatus"
0x5a268  ldarg.3
0x5a269  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a26e  ldarg.1
0x5a26f  ldstr    aCustomizedpage// "CustomizedPageStatus"
0x5a274  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5a279  ldarg.3
0x5a27a  ldstr    aCustomizedpage// "CustomizedPageStatus"
0x5a27f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5a284  ldarg.1
0x5a285  ldloc.0
0x5a286  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPCustomizedPageStatus [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_CustomizedPageStatus()
0x5a28b  ldarg.3
0x5a28c  call     T0x2B0001B7
0x5a291  ldarg.3
0x5a292  ldstr    aCustomizedpage// "CustomizedPageStatus"
0x5a297  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5a29c  ldarg.0
0x5a29d  ldstr    aEtag_0// "ETag"
0x5a2a2  ldarg.3
0x5a2a3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a2a8  ldarg.1
0x5a2a9  ldstr    aEtag_0// "ETag"
0x5a2ae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5a2b3  ldarg.3
0x5a2b4  ldstr    aEtag_0// "ETag"
0x5a2b9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5a2be  ldarg.1
0x5a2bf  ldloc.0
0x5a2c0  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_ETag()
0x5a2c5  ldarg.3
0x5a2c6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a2cb  ldarg.3
0x5a2cc  ldstr    aEtag_0// "ETag"
0x5a2d1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5a2d6  ldarg.0
0x5a2d7  ldstr    aExists// "Exists"
0x5a2dc  ldarg.3
0x5a2dd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a2e2  ldarg.1
0x5a2e3  ldstr    aExists// "Exists"
0x5a2e8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5a2ed  ldarg.3
0x5a2ee  ldstr    aExists// "Exists"
0x5a2f3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5a2f8  ldarg.1
0x5a2f9  ldloc.0
0x5a2fa  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Exists()
0x5a2ff  ldarg.3
0x5a300  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a305  ldarg.3
0x5a306  ldstr    aExists// "Exists"
0x5a30b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5a310  ldarg.0
0x5a311  ldstr    aIrmenabled// "IrmEnabled"
0x5a316  ldarg.3
0x5a317  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a31c  ldarg.1
0x5a31d  ldstr    aIrmenabled// "IrmEnabled"
0x5a322  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5a327  ldarg.3
0x5a328  ldstr    aIrmenabled// "IrmEnabled"
0x5a32d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5a332  ldarg.1
0x5a333  ldloc.0
0x5a334  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_IrmEnabled()
0x5a339  ldarg.3
0x5a33a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a33f  ldarg.3
0x5a340  ldstr    aIrmenabled// "IrmEnabled"
0x5a345  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5a34a  ldarg.0
0x5a34b  ldstr    aLength// "Length"
0x5a350  ldarg.3
0x5a351  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a356  ldarg.1
0x5a357  ldstr    aLength// "Length"
0x5a35c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5a361  ldarg.3
0x5a362  ldstr    aLength// "Length"
0x5a367  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5a36c  ldarg.1
0x5a36d  ldloc.0
0x5a36e  callvirt instance int64 [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Length()
0x5a373  ldarg.3
0x5a374  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt64(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int64, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a379  ldarg.3
0x5a37a  ldstr    aLength// "Length"
0x5a37f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5a384  ldarg.0
0x5a385  ldstr    aLevel// "Level"
0x5a38a  ldarg.3
0x5a38b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a390  ldarg.1
0x5a391  ldstr    aLevel// "Level"
0x5a396  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5a39b  ldarg.3
0x5a39c  ldstr    aLevel// "Level"
0x5a3a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5a3a6  ldarg.1
0x5a3a7  ldloc.0
0x5a3a8  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFileLevel [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Level()
0x5a3ad  ldarg.3
0x5a3ae  call     T0x2B0001B8
0x5a3b3  ldarg.3
0x5a3b4  ldstr    aLevel// "Level"
0x5a3b9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5a3be  ldarg.0
0x5a3bf  ldstr    aLinkinguri// "LinkingUri"
0x5a3c4  ldarg.3
0x5a3c5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a3ca  ldarg.1
0x5a3cb  ldstr    aLinkinguri// "LinkingUri"
0x5a3d0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5a3d5  ldarg.3
0x5a3d6  ldstr    aLinkinguri// "LinkingUri"
0x5a3db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5a3e0  ldarg.1
0x5a3e1  ldloc.0
0x5a3e2  callvirt instance class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_LinkingUri()
0x5a3e7  ldarg.3
0x5a3e8  call     T0x2B000052
0x5a3ed  ldarg.3
0x5a3ee  ldstr    aLinkinguri// "LinkingUri"
0x5a3f3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5a3f8  ldarg.0
0x5a3f9  ldstr    aLinkingurl// "LinkingUrl"
0x5a3fe  ldarg.3
0x5a3ff  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a404  ldarg.1
0x5a405  ldstr    aLinkingurl// "LinkingUrl"
0x5a40a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5a40f  ldarg.3
0x5a410  ldstr    aLinkingurl// "LinkingUrl"
0x5a415  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5a41a  ldarg.1
0x5a41b  ldloc.0
0x5a41c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_LinkingUrl()
0x5a421  ldarg.3
0x5a422  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a427  ldarg.3
0x5a428  ldstr    aLinkingurl// "LinkingUrl"
0x5a42d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5a432  ldarg.0
0x5a433  ldstr    aMajorversion// "MajorVersion"
0x5a438  ldarg.3
0x5a439  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a43e  ldarg.1
0x5a43f  ldstr    aMajorversion// "MajorVersion"
0x5a444  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5a449  ldarg.3
0x5a44a  ldstr    aMajorversion// "MajorVersion"
0x5a44f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5a454  ldarg.1
0x5a455  ldloc.0
0x5a456  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_MajorVersion()
0x5a45b  ldarg.3
0x5a45c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a461  ldarg.3
0x5a462  ldstr    aMajorversion// "MajorVersion"
0x5a467  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5a46c  ldarg.0
0x5a46d  ldstr    aMinorversion// "MinorVersion"
0x5a472  ldarg.3
0x5a473  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a478  ldarg.1
0x5a479  ldstr    aMinorversion// "MinorVersion"
0x5a47e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5a483  ldarg.3
0x5a484  ldstr    aMinorversion// "MinorVersion"
0x5a489  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5a48e  ldarg.1
0x5a48f  ldloc.0
0x5a490  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_MinorVersion()
0x5a495  ldarg.3
0x5a496  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a49b  ldarg.3
0x5a49c  ldstr    aMinorversion// "MinorVersion"
0x5a4a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5a4a6  ldarg.0
0x5a4a7  ldstr    aName// "Name"
0x5a4ac  ldarg.3
0x5a4ad  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a4b2  ldarg.1
0x5a4b3  ldstr    aName// "Name"
0x5a4b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5a4bd  ldarg.3
0x5a4be  ldstr    aName// "Name"
0x5a4c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5a4c8  ldarg.1
0x5a4c9  ldloc.0
0x5a4ca  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Name()
0x5a4cf  ldarg.3
0x5a4d0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a4d5  ldarg.3
0x5a4d6  ldstr    aName// "Name"
0x5a4db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5a4e0  ldarg.0
0x5a4e1  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x5a4e6  ldarg.3
0x5a4e7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a4ec  ldarg.1
0x5a4ed  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x5a4f2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5a4f7  ldarg.3
0x5a4f8  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x5a4fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5a502  ldarg.1
0x5a503  ldloc.0
0x5a504  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_ServerRelativeUrl()
0x5a509  ldarg.3
0x5a50a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a50f  ldarg.3
0x5a510  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x5a515  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5a51a  ldarg.0
0x5a51b  ldstr    aTimecreated// "TimeCreated"
0x5a520  ldarg.3
0x5a521  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a526  ldarg.1
0x5a527  ldstr    aTimecreated// "TimeCreated"
0x5a52c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5a531  ldarg.3
0x5a532  ldstr    aTimecreated// "TimeCreated"
0x5a537  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5a53c  ldarg.1
0x5a53d  ldloc.0
0x5a53e  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_TimeCreated()
0x5a543  ldarg.3
0x5a544  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5a549  ldarg.3
0x5a54a  ldstr    aTimecreated// "TimeCreated"
0x5a54f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5a554  ldarg.0
  ... truncated ...
```
