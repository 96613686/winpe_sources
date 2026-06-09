# Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::Initialize

- ea: `0x75afc0`
- end: `0x75b53b`
- name: `Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::Initialize`
- size: `1403`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `broker_com_uri`

## callers

- `0x75af30`
- `0x75af70`

## callees

- `0x19dc20`
- `0x749060`
- `0x74d6c0`
- `0x75ac80`
- `0x75aca0`
- `0x75acd0`
- `0x75ace0`
- `0x75acf0`
- `0x75ad00`
- `0x75ad20`
- `0x75ad60`
- `0x75ad80`
- `0x75ada0`
- `0x75adc0`
- `0x75ade0`
- `0x75ae10`
- `0x75ae20`
- `0x75ae40`
- `0x75ae50`
- `0x75ae60`
- `0x75aea0`
- `0x75aeb0`
- `0x75aec0`
- `0x75aee0`
- `0x75afc0`
- `0x75b550`
- `0x93dab0`
- `0x93dae0`
- `0x957b70`

## string_xrefs

- `0x75b045`: `guestaccesstoken`
- `0x75b0b3`: `SPSharingLinkParsedParameters.Initialize: Not a ShareByLink request - missing access token, share token, or authkey`
- `0x75b0ee`: `SPSharingLinkParsedParameters.Initialize: Not a ShareByLink request - share token is invalid`
- `0x75b138`: `SPSharingLinkParsedParameters.Initialize: GuestAccessToken is partially decoded, fixing up decoding on GuestAccessToken.`
- `0x75b18f`: `SPSharingLinkParsedParameters.Initialize: Invalid URL format - missing unique id`
- `0x75b20e`: `SPSharingLinkParsedParameters.Initialize: Unable to parse the Expiration parameter. Exception: '{0}'.`
- `0x75b25c`: `SPSharingLinkParsedParameters.Initialize: Unable to parse the TokenSchemaRevision parameter.`
- `0x75b2a0`: `SPSharingLinkParsedParameters.Initialize: Unable to parse the isPreAuthUrl parameter. Exception: '{0}'.`
- `0x75b309`: `SPSharingLinkParsedParameters.Initialize: Link is not valid format.`
- `0x75b340`: `SPSharingLinkParsedParameters.Initialize: Unable to find a valid type in unique id. Exception: '{0}'.`
- `0x75b39c`: `SPSharingLinkParsedParameters.Initialize: Unexpectedly small size of unique id string`
- `0x75b3e4`: `SPSharingLinkParsedParameters.Initialize: Unable to read the read-write bit`
- `0x75b40e`: `SPSharingLinkParsedParameters.Initialize: Unable to find a valid guid in unique id. Exception: '{0}'.`
- `0x75b4c3`: `SPSharingLinkParsedParameters.Initialize: Url has link target, {0} ID: ({0})`
- `0x75b500`: `SPSharingLinkParsedParameters.Initialize: Invalid value in target parameter [{0}={1}].`

## pseudocode

```c

```

## disassembly

```asm
0x75afc0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x75afc5  stloc.0
0x75afc6  ldc.i4.0
0x75afc7  stloc.1
0x75afc8  ldarg.1
0x75afc9  ldstr    aDocid_3// "docid"
0x75afce  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75afd3  stloc.2
0x75afd4  ldarg.1
0x75afd5  ldstr    aFolderid_2// "folderid"
0x75afda  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75afdf  stloc.3
0x75afe0  ldarg.1
0x75afe1  ldstr    aDownload// "download"
0x75afe6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75afeb  stloc.s  4
0x75afed  ldarg.1
0x75afee  ldstr    aExpiration_0// "expiration"
0x75aff3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75aff8  stloc.s  5
0x75affa  ldarg.1
0x75affb  ldstr    aAuthurl// "authurl"
0x75b000  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75b005  stloc.s  6
0x75b007  ldarg.1
0x75b008  ldstr    aRev// "rev"
0x75b00d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75b012  stloc.s  7
0x75b014  ldarg.1
0x75b015  ldstr    aShare_0// "share"
0x75b01a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75b01f  stloc.s  8
0x75b021  ldarg.0
0x75b022  ldarg.1
0x75b023  ldstr    aEmail_1// "email"
0x75b028  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75b02d  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_EmailAddress(string value)
0x75b032  ldarg.0
0x75b033  ldarg.1
0x75b034  ldstr    aAuthkey_0// "authkey"
0x75b039  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75b03e  stfld    string Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::m_authKey
0x75b043  ldarg.0
0x75b044  ldarg.1
0x75b045  ldstr    aGuestaccesstok_1// "guestaccesstoken"
0x75b04a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75b04f  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_GuestAccessToken(string value)
0x75b054  ldarg.0
0x75b055  ldloc.s  4
0x75b057  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x75b05c  brtrue.s loc_75B06D
0x75b05e  ldloc.s  4
0x75b060  ldstr    a1// "1"
0x75b065  ldc.i4.5
0x75b066  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x75b06b  br.s     loc_75B06E
0x75b06d  ldc.i4.0
0x75b06e  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_IsForceDownloadUrl(bool value)
0x75b073  ldarg.0
0x75b074  ldarg.1
0x75b075  ldstr    aUserid_5// "userid"
0x75b07a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75b07f  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_UserId(string value)
0x75b084  ldarg.0
0x75b085  call     instance string Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::get_GuestAccessToken()
0x75b08a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x75b08f  brfalse.s loc_75B0BF
0x75b091  ldarg.0
0x75b092  call     instance string Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::get_AuthKey()
0x75b097  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x75b09c  brfalse.s loc_75B0BF
0x75b09e  ldloc.s  8
0x75b0a0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x75b0a5  brfalse.s loc_75B0BF
0x75b0a7  ldc.i4   0x1699482
0x75b0ac  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x75b0b1  ldc.i4.s 0x32
0x75b0b3  ldstr    aSpsharinglinkp// "SPSharingLinkParsedParameters.Initializ"...
0x75b0b8  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x75b0bd  ldc.i4.2
0x75b0be  ret
0x75b0bf  ldloc.s  8
0x75b0c1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x75b0c6  brtrue.s loc_75B10D
0x75b0c8  ldarg.0
0x75b0c9  ldc.i4.1
0x75b0ca  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_IsShareTokenEnabledLink(bool value)
0x75b0cf  ldloc.s  8
0x75b0d1  ldloca.s 1
0x75b0d3  ldloca.s 0
0x75b0d5  ldarg.0
0x75b0d6  ldflda   string Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::m_authKey
0x75b0db  call     bool Microsoft.SharePoint.Sharing.SPShareTokenConverter::GetValuesFromShareToken(string shareToken, [out] valuetype Microsoft.SharePoint.Sharing.SPSharedObjectType& objectType, [out] valuetype [mscorlib]System.Guid& objectUniqueId, [out] string& authKey)
0x75b0e0  brtrue.s loc_75B0FB
0x75b0e2  ldc.i4   0x1699483
0x75b0e7  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x75b0ec  ldc.i4.s 0x32
0x75b0ee  ldstr    aSpsharinglinkp_0// "SPSharingLinkParsedParameters.Initializ"...
0x75b0f3  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x75b0f8  ldc.i4.s 0x19
0x75b0fa  ret
0x75b0fb  ldarg.0
0x75b0fc  ldloc.1
0x75b0fd  ldloc.0
0x75b0fe  newobj   instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkObjectParam::.ctor(valuetype Microsoft.SharePoint.Sharing.SPSharedObjectType type, valuetype [mscorlib]System.Guid uniqueId)
0x75b103  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_SharedObject(class Microsoft.SharePoint.Sharing.Internal.SPSharingLinkObjectParam value)
0x75b108  br       loc_75B43E
0x75b10d  ldarg.0
0x75b10e  call     instance string Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::get_GuestAccessToken()
0x75b113  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x75b118  brtrue.s loc_75B15D
0x75b11a  ldarg.0
0x75b11b  call     instance string Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::get_GuestAccessToken()
0x75b120  ldstr    asc_C68BFA// " "
0x75b125  callvirt instance bool [mscorlib]System.String::Contains(string)
0x75b12a  brfalse.s loc_75B15D
0x75b12c  ldc.i4   0x1699484
0x75b131  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x75b136  ldc.i4.s 0x14
0x75b138  ldstr    aSpsharinglinkp_1// "SPSharingLinkParsedParameters.Initializ"...
0x75b13d  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x75b142  ldarg.0
0x75b143  ldarg.0
0x75b144  call     instance string Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::get_GuestAccessToken()
0x75b149  ldstr    asc_C68BFA// " "
0x75b14e  ldstr    asc_C95F04// "+"
0x75b153  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x75b158  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_GuestAccessToken(string value)
0x75b15d  ldloc.2
0x75b15e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x75b163  brtrue.s loc_75B170
0x75b165  ldarg.0
0x75b166  ldloc.2
0x75b167  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_UniqueIdString(string value)
0x75b16c  ldc.i4.1
0x75b16d  stloc.1
0x75b16e  br.s     loc_75B19B
0x75b170  ldloc.3
0x75b171  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x75b176  brtrue.s loc_75B183
0x75b178  ldarg.0
0x75b179  ldloc.3
0x75b17a  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_UniqueIdString(string value)
0x75b17f  ldc.i4.2
0x75b180  stloc.1
0x75b181  br.s     loc_75B19B
0x75b183  ldc.i4   0x1699485
0x75b188  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x75b18d  ldc.i4.s 0x14
0x75b18f  ldstr    aSpsharinglinkp_2// "SPSharingLinkParsedParameters.Initializ"...
0x75b194  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x75b199  ldc.i4.3
0x75b19a  ret
0x75b19b  ldstr    a09T09Z// "[0-9\\-]+T[0-9\\.\\:]+Z"
0x75b1a0  ldc.i4.1
0x75b1a1  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x75b1a6  stloc.s  9
0x75b1a8  ldloc.s  5
0x75b1aa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x75b1af  brfalse.s loc_75B1BE
0x75b1b1  ldarg.0
0x75b1b2  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x75b1b7  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_ExpirationTime(valuetype [mscorlib]System.DateTime value)
0x75b1bc  br.s     loc_75B1FE
0x75b1be  ldloc.s  9
0x75b1c0  ldloc.s  5
0x75b1c2  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0x75b1c7  brfalse.s loc_75B1DF
0x75b1c9  ldarg.0
0x75b1ca  ldloc.s  5
0x75b1cc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x75b1d1  ldc.i4.s 0x10
0x75b1d3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider, valuetype [mscorlib]System.Globalization.DateTimeStyles)
0x75b1d8  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_ExpirationTime(valuetype [mscorlib]System.DateTime value)
0x75b1dd  br.s     loc_75B1FE
0x75b1df  ldarg.0
0x75b1e0  ldloc.s  5
0x75b1e2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string)
0x75b1e7  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_ExpirationTime(valuetype [mscorlib]System.DateTime value)
0x75b1ec  ldarg.0
0x75b1ed  ldarg.0
0x75b1ee  call     instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::get_ExpirationTime()
0x75b1f3  ldc.i4.1
0x75b1f4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x75b1f9  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_ExpirationTime(valuetype [mscorlib]System.DateTime value)
0x75b1fe  leave.s  loc_75B230
0x75b200  stloc.s  0xA
0x75b202  ldc.i4   0x1699486
0x75b207  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x75b20c  ldc.i4.s 0x14
0x75b20e  ldstr    aSpsharinglinkp_3// "SPSharingLinkParsedParameters.Initializ"...
0x75b213  ldc.i4.1
0x75b214  newarr   [mscorlib]System.Object
0x75b219  stloc.s  0x18
0x75b21b  ldloc.s  0x18
0x75b21d  ldc.i4.0
0x75b21e  ldloc.s  0xA
0x75b220  stelem.ref
0x75b221  ldloc.s  0x18
0x75b223  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x75b228  ldc.i4.4
0x75b229  stloc.s  0x17
0x75b22b  leave    loc_75B538
0x75b230  ldloc.s  7
0x75b232  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x75b237  brfalse.s loc_75B242
0x75b239  ldarg.0
0x75b23a  ldc.i4.0
0x75b23b  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_TokenSchemaRevision(int32 value)
0x75b240  br.s     loc_75B271
0x75b242  ldc.i4.0
0x75b243  stloc.s  0xB
0x75b245  ldloc.s  7
0x75b247  ldloca.s 0xB
0x75b249  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x75b24e  brtrue.s loc_75B269
0x75b250  ldc.i4   0x1699487
0x75b255  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x75b25a  ldc.i4.s 0x14
0x75b25c  ldstr    aSpsharinglinkp_4// "SPSharingLinkParsedParameters.Initializ"...
0x75b261  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x75b266  ldc.i4.s 0x1C
0x75b268  ret
0x75b269  ldarg.0
0x75b26a  ldloc.s  0xB
0x75b26c  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_TokenSchemaRevision(int32 value)
0x75b271  ldloc.s  6
0x75b273  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x75b278  brfalse.s loc_75B283
0x75b27a  ldarg.0
0x75b27b  ldc.i4.0
0x75b27c  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_IsPreAuthUrl(bool value)
0x75b281  br.s     loc_75B2C2
0x75b283  ldarg.0
0x75b284  ldloc.s  6
0x75b286  call     bool [mscorlib]System.Boolean::Parse(string)
0x75b28b  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_IsPreAuthUrl(bool value)
0x75b290  leave.s  loc_75B2C2
0x75b292  stloc.s  0xC
0x75b294  ldc.i4   0x1699488
0x75b299  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x75b29e  ldc.i4.s 0x14
0x75b2a0  ldstr    aSpsharinglinkp_5// "SPSharingLinkParsedParameters.Initializ"...
0x75b2a5  ldc.i4.1
0x75b2a6  newarr   [mscorlib]System.Object
0x75b2ab  stloc.s  0x19
0x75b2ad  ldloc.s  0x19
0x75b2af  ldc.i4.0
0x75b2b0  ldloc.s  0xC
0x75b2b2  stelem.ref
0x75b2b3  ldloc.s  0x19
0x75b2b5  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x75b2ba  ldc.i4.5
0x75b2bb  stloc.s  0x17
0x75b2bd  leave    loc_75B538
0x75b2c2  ldarg.0
0x75b2c3  call     instance string Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::get_UniqueIdString()
0x75b2c8  stloc.s  0xD
0x75b2ca  ldloc.s  0xD
0x75b2cc  ldc.i4.s 0x5F
0x75b2ce  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x75b2d3  stloc.s  0xE
0x75b2d5  ldloc.s  0xE
0x75b2d7  ldc.i4.m1
0x75b2d8  beq      loc_75B37E
0x75b2dd  ldloc.s  0xD
0x75b2df  ldc.i4.0
0x75b2e0  ldloc.s  0xE
0x75b2e2  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x75b2e7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x75b2ec  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x75b2f1  stloc.s  0xF
0x75b2f3  ldloc.s  0xF
0x75b2f5  ldc.i4.0
0x75b2f6  blt.s    loc_75B2FD
0x75b2f8  ldloc.s  0xF
0x75b2fa  ldc.i4.3
0x75b2fb  blt.s    loc_75B319
0x75b2fd  ldc.i4   0x1699489
0x75b302  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x75b307  ldc.i4.s 0xA
0x75b309  ldstr    aSpsharinglinkp_6// "SPSharingLinkParsedParameters.Initializ"...
0x75b30e  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x75b313  newobj   instance void [mscorlib]System.FormatException::.ctor()
0x75b318  throw
0x75b319  ldarg.0
0x75b31a  ldloc.s  0xF
0x75b31c  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_SharingType(valuetype SharingType value)
0x75b321  ldarg.0
0x75b322  ldarg.0
0x75b323  call     instance valuetype SharingType Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::get_SharingType()
0x75b328  ldc.i4.1
0x75b329  ceq
0x75b32b  call     instance void Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::set_IsFormsEnabledLink(bool value)
0x75b330  leave.s  loc_75B362
0x75b332  stloc.s  0x10
0x75b334  ldc.i4   0x169948A
0x75b339  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x75b33e  ldc.i4.s 0x14
0x75b340  ldstr    aSpsharinglinkp_7// "SPSharingLinkParsedParameters.Initializ"...
  ... truncated ...
```
