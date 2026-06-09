# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifySignatureTimestampNew

- ea: `0x8810`
- end: `0x8d0b`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifySignatureTimestampNew`
- size: `1275`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x7c80`
- `0x7e60`

## callees

- `0x7730`
- `0x8810`
- `0x8d10`
- `0x8f30`

## pseudocode

```c

```

## disassembly

```asm
0x8810  ldarg.3
0x8811  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x8816  stobj    [mscorlib]System.DateTime
0x881b  ldloca.s 0
0x881d  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x8823  ldnull
0x8824  stloc.1
0x8825  ldnull
0x8826  stloc.2
0x8827  ldarg.1
0x8828  ldstr    aDsObjectAsTime// "ds:Object/as:Timestamp"
0x882d  ldarg.2
0x882e  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x8833  stloc.3
0x8834  ldarg.1
0x8835  ldstr    aDsSignatureval// "ds:SignatureValue"
0x883a  ldarg.2
0x883b  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x8840  stloc.s  4
0x8842  ldloc.3
0x8843  brfalse.s loc_885A
0x8845  ldloc.3
0x8846  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x884b  brfalse.s loc_885A
0x884d  ldloc.s  4
0x884f  brfalse.s loc_885A
0x8851  ldloc.s  4
0x8853  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x8858  brtrue.s loc_885C
0x885a  ldc.i4.0
0x885b  ret
0x885c  ldloc.3
0x885d  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x8862  ldc.i4.1
0x8863  bgt.s    loc_8896
0x8865  ldloc.s  4
0x8867  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x886c  ldc.i4.1
0x886d  bgt.s    loc_8896
0x886f  ldloc.3
0x8870  ldc.i4.0
0x8871  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x8876  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x887b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8880  brtrue.s loc_8896
0x8882  ldloc.s  4
0x8884  ldc.i4.0
0x8885  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x888a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x888f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8894  brfalse.s loc_88B1
0x8896  ldarg.0
0x8897  ldfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_authenticodeSignerInfo
0x889c  ldc.i4   0x80096005
0x88a1  callvirt instance void System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::set_ErrorCode(int32 value)
0x88a6  ldc.i4   0x80096005
0x88ab  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x88b0  throw
0x88b1  ldnull
0x88b2  stloc.s  5
0x88b4  ldnull
0x88b5  stloc.s  6
0x88b7  ldloc.3
0x88b8  ldc.i4.0
0x88b9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x88be  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x88c3  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x88c8  stloc.s  5
0x88ca  ldloc.s  4
0x88cc  ldc.i4.0
0x88cd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x88d2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x88d7  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x88dc  stloc.s  6
0x88de  leave.s  loc_88FC
0x88e0  pop
0x88e1  ldarg.0
0x88e2  ldfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_authenticodeSignerInfo
0x88e7  ldc.i4   0x80096005
0x88ec  callvirt instance void System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::set_ErrorCode(int32 value)
0x88f1  ldc.i4   0x80096005
0x88f6  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x88fb  throw
0x88fc  ldloc.s  5
0x88fe  brfalse.s loc_8904
0x8900  ldloc.s  6
0x8902  brtrue.s loc_8906
0x8904  ldc.i4.0
0x8905  ret
0x8906  newobj   instance void [System.Security]System.Security.Cryptography.Pkcs.SignedCms::.ctor()
0x890b  stloc.s  7
0x890d  ldloc.s  7
0x890f  ldloc.s  5
0x8911  callvirt instance void [System.Security]System.Security.Cryptography.Pkcs.SignedCms::Decode(unsigned int8[])
0x8916  ldloc.s  7
0x8918  ldc.i4.1
0x8919  callvirt instance void [System.Security]System.Security.Cryptography.Pkcs.SignedCms::CheckSignature(bool)
0x891e  ldloc.s  7
0x8920  callvirt instance class [System.Security]System.Security.Cryptography.Pkcs.SignerInfoCollection [System.Security]System.Security.Cryptography.Pkcs.SignedCms::get_SignerInfos()
0x8925  callvirt instance int32 [System.Security]System.Security.Cryptography.Pkcs.SignerInfoCollection::get_Count()
0x892a  ldc.i4.1
0x892b  beq.s    loc_8948
0x892d  ldarg.0
0x892e  ldfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_authenticodeSignerInfo
0x8933  ldc.i4   0x80096002
0x8938  callvirt instance void System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::set_ErrorCode(int32 value)
0x893d  ldc.i4   0x80096002
0x8942  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x8947  throw
0x8948  ldloc.s  7
0x894a  callvirt instance class [System.Security]System.Security.Cryptography.Pkcs.SignerInfoCollection [System.Security]System.Security.Cryptography.Pkcs.SignedCms::get_SignerInfos()
0x894f  ldc.i4.0
0x8950  callvirt instance class [System.Security]System.Security.Cryptography.Pkcs.SignerInfo [System.Security]System.Security.Cryptography.Pkcs.SignerInfoCollection::get_Item(int32)
0x8955  callvirt instance class [System]System.Security.Cryptography.Oid [System.Security]System.Security.Cryptography.Pkcs.SignerInfo::get_DigestAlgorithm()
0x895a  callvirt instance string [System]System.Security.Cryptography.Oid::get_Value()
0x895f  stloc.1
0x8960  ldloc.s  7
0x8962  callvirt instance class [System.Security]System.Security.Cryptography.Pkcs.SignerInfoCollection [System.Security]System.Security.Cryptography.Pkcs.SignedCms::get_SignerInfos()
0x8967  ldc.i4.0
0x8968  callvirt instance class [System.Security]System.Security.Cryptography.Pkcs.SignerInfo [System.Security]System.Security.Cryptography.Pkcs.SignerInfoCollection::get_Item(int32)
0x896d  callvirt instance class [System.Security]System.Security.Cryptography.CryptographicAttributeObjectCollection [System.Security]System.Security.Cryptography.Pkcs.SignerInfo::get_SignedAttributes()
0x8972  stloc.s  8
0x8974  ldloc.s  8
0x8976  callvirt instance class [System.Security]System.Security.Cryptography.CryptographicAttributeObjectEnumerator [System.Security]System.Security.Cryptography.CryptographicAttributeObjectCollection::GetEnumerator()
0x897b  stloc.s  0xC
0x897d  br       loc_8A81
0x8982  ldloc.s  0xC
0x8984  callvirt instance class [System.Security]System.Security.Cryptography.CryptographicAttributeObject [System.Security]System.Security.Cryptography.CryptographicAttributeObjectEnumerator::get_Current()
0x8989  stloc.s  0xD
0x898b  ldloca.s 0
0x898d  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x8992  brtrue.s loc_8A07
0x8994  ldloc.s  0xD
0x8996  callvirt instance class [System]System.Security.Cryptography.Oid [System.Security]System.Security.Cryptography.CryptographicAttributeObject::get_Oid()
0x899b  callvirt instance string [System]System.Security.Cryptography.Oid::get_Value()
0x89a0  ldstr    a12840113549195// "1.2.840.113549.1.9.5"
0x89a5  ldc.i4.4
0x89a6  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x89ab  brtrue.s loc_8A07
0x89ad  ldloc.s  0xD
0x89af  callvirt instance class [System]System.Security.Cryptography.AsnEncodedDataCollection [System.Security]System.Security.Cryptography.CryptographicAttributeObject::get_Values()
0x89b4  callvirt instance class [System]System.Security.Cryptography.AsnEncodedDataEnumerator [System]System.Security.Cryptography.AsnEncodedDataCollection::GetEnumerator()
0x89b9  stloc.s  0xE
0x89bb  br.s     loc_89FC
0x89bd  ldloc.s  0xE
0x89bf  callvirt instance class [System]System.Security.Cryptography.AsnEncodedData [System]System.Security.Cryptography.AsnEncodedDataEnumerator::get_Current()
0x89c4  stloc.s  0xF
0x89c6  ldloc.s  0xF
0x89c8  callvirt instance class [System]System.Security.Cryptography.Oid [System]System.Security.Cryptography.AsnEncodedData::get_Oid()
0x89cd  callvirt instance string [System]System.Security.Cryptography.Oid::get_Value()
0x89d2  ldstr    a12840113549195// "1.2.840.113549.1.9.5"
0x89d7  ldc.i4.4
0x89d8  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x89dd  brtrue.s loc_89FC
0x89df  ldloca.s 0
0x89e1  ldloc.s  0xF
0x89e3  callvirt instance unsigned int8[] [System]System.Security.Cryptography.AsnEncodedData::get_RawData()
0x89e8  newobj   instance void [System.Security]System.Security.Cryptography.Pkcs.Pkcs9SigningTime::.ctor(unsigned int8[])
0x89ed  call     instance valuetype [mscorlib]System.DateTime [System.Security]System.Security.Cryptography.Pkcs.Pkcs9SigningTime::get_SigningTime()
0x89f2  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x89f7  br       loc_8A81
0x89fc  ldloc.s  0xE
0x89fe  callvirt instance bool [System]System.Security.Cryptography.AsnEncodedDataEnumerator::MoveNext()
0x8a03  brtrue.s loc_89BD
0x8a05  br.s     loc_8A81
0x8a07  ldloc.2
0x8a08  brtrue.s loc_8A81
0x8a0a  ldloc.s  0xD
0x8a0c  callvirt instance class [System]System.Security.Cryptography.Oid [System.Security]System.Security.Cryptography.CryptographicAttributeObject::get_Oid()
0x8a11  callvirt instance string [System]System.Security.Cryptography.Oid::get_Value()
0x8a16  ldstr    a12840113549194// "1.2.840.113549.1.9.4"
0x8a1b  ldc.i4.4
0x8a1c  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x8a21  brtrue.s loc_8A81
0x8a23  ldloc.s  0xD
0x8a25  callvirt instance class [System]System.Security.Cryptography.AsnEncodedDataCollection [System.Security]System.Security.Cryptography.CryptographicAttributeObject::get_Values()
0x8a2a  callvirt instance class [System]System.Security.Cryptography.AsnEncodedDataEnumerator [System]System.Security.Cryptography.AsnEncodedDataCollection::GetEnumerator()
0x8a2f  stloc.s  0x10
0x8a31  br.s     loc_8A78
0x8a33  ldloc.s  0x10
0x8a35  callvirt instance class [System]System.Security.Cryptography.AsnEncodedData [System]System.Security.Cryptography.AsnEncodedDataEnumerator::get_Current()
0x8a3a  stloc.s  0x11
0x8a3c  ldloc.s  0x11
0x8a3e  callvirt instance class [System]System.Security.Cryptography.Oid [System]System.Security.Cryptography.AsnEncodedData::get_Oid()
0x8a43  callvirt instance string [System]System.Security.Cryptography.Oid::get_Value()
0x8a48  ldstr    a12840113549194// "1.2.840.113549.1.9.4"
0x8a4d  ldc.i4.4
0x8a4e  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x8a53  brtrue.s loc_8A78
0x8a55  ldloc.s  0x11
0x8a57  callvirt instance unsigned int8[] [System]System.Security.Cryptography.AsnEncodedData::get_RawData()
0x8a5c  stloc.s  0x12
0x8a5e  newobj   instance void [System.Security]System.Security.Cryptography.Pkcs.Pkcs9MessageDigest::.ctor()
0x8a63  stloc.s  0x13
0x8a65  ldloc.s  0x13
0x8a67  ldloc.s  0x12
0x8a69  callvirt instance void [System]System.Security.Cryptography.AsnEncodedData::set_RawData(unsigned int8[])
0x8a6e  ldloc.s  0x13
0x8a70  callvirt instance unsigned int8[] [System.Security]System.Security.Cryptography.Pkcs.Pkcs9MessageDigest::get_MessageDigest()
0x8a75  stloc.2
0x8a76  br.s     loc_8A81
0x8a78  ldloc.s  0x10
0x8a7a  callvirt instance bool [System]System.Security.Cryptography.AsnEncodedDataEnumerator::MoveNext()
0x8a7f  brtrue.s loc_8A33
0x8a81  ldloc.s  0xC
0x8a83  callvirt instance bool [System.Security]System.Security.Cryptography.CryptographicAttributeObjectEnumerator::MoveNext()
0x8a88  brtrue   loc_8982
0x8a8d  ldc.i4.0
0x8a8e  stloc.s  9
0x8a90  ldc.i4.0
0x8a91  stloc.s  0xA
0x8a93  ldarg.0
0x8a94  ldloc.s  5
0x8a96  ldloc.s  6
0x8a98  call     instance valuetype [mscorlib]System.DateTime System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyRFC3161Timestamp(unsigned int8[] base64DecodedMessage, unsigned int8[] base64DecodedSignatureValue)
0x8a9d  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x8aa2  stloc.0
0x8aa3  ldc.i4.1
0x8aa4  stloc.s  9
0x8aa6  ldc.i4.1
0x8aa7  stloc.s  0xA
0x8aa9  leave    loc_8B54
0x8aae  stloc.s  0x14
0x8ab0  ldloc.s  0x14
0x8ab2  isinst   [mscorlib]System.Security.Cryptography.CryptographicException
0x8ab7  brfalse.s loc_8ACA
0x8ab9  ldloc.s  0x14
0x8abb  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x8ac0  ldc.i4   0x80090002
0x8ac5  beq      loc_8B52
0x8aca  ldloc.2
0x8acb  brfalse  loc_8B52
0x8ad0  ldnull
0x8ad1  stloc.s  0x15
0x8ad3  ldnull
0x8ad4  stloc.s  0x16
0x8ad6  ldloc.1
0x8ad7  ldstr    a21684011013423// "2.16.840.1.101.3.4.2.3"
0x8adc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8ae1  brfalse.s loc_8AEC
0x8ae3  call     class [mscorlib]System.Security.Cryptography.SHA512 [mscorlib]System.Security.Cryptography.SHA512::Create()
0x8ae8  stloc.s  0x16
0x8aea  br.s     loc_8B2C
0x8aec  ldloc.1
0x8aed  ldstr    a21684011013422// "2.16.840.1.101.3.4.2.2"
0x8af2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8af7  brfalse.s loc_8B02
0x8af9  call     class [mscorlib]System.Security.Cryptography.SHA384 [mscorlib]System.Security.Cryptography.SHA384::Create()
0x8afe  stloc.s  0x16
0x8b00  br.s     loc_8B2C
0x8b02  ldloc.1
0x8b03  ldstr    a21684011013421// "2.16.840.1.101.3.4.2.1"
0x8b08  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8b0d  brfalse.s loc_8B18
0x8b0f  call     class [mscorlib]System.Security.Cryptography.SHA256 [mscorlib]System.Security.Cryptography.SHA256::Create()
0x8b14  stloc.s  0x16
0x8b16  br.s     loc_8B2C
0x8b18  ldloc.1
0x8b19  ldstr    a13143226// "1.3.14.3.2.26"
0x8b1e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8b23  brfalse.s loc_8B2C
0x8b25  call     class [mscorlib]System.Security.Cryptography.SHA1 [mscorlib]System.Security.Cryptography.SHA1::Create()
0x8b2a  stloc.s  0x16
0x8b2c  ldloc.s  0x16
0x8b2e  brfalse.s loc_8B52
0x8b30  ldloc.s  0x16
0x8b32  ldloc.s  6
0x8b34  callvirt instance unsigned int8[] [mscorlib]System.Security.Cryptography.HashAlgorithm::ComputeHash(unsigned int8[])
0x8b39  stloc.s  0x15
0x8b3b  ldloc.s  0x15
0x8b3d  brfalse.s loc_8B52
0x8b3f  ldloc.s  0x15
0x8b41  ldlen
0x8b42  conv.i4
0x8b43  ldloc.2
0x8b44  ldlen
0x8b45  conv.i4
0x8b46  bne.un.s loc_8B52
0x8b48  ldloc.s  0x15
0x8b4a  ldloc.2
0x8b4b  call     T0x2B000002
0x8b50  stloc.s  9
0x8b52  leave.s  loc_8B54
0x8b54  ldloc.s  9
0x8b56  brtrue.s loc_8B73
0x8b58  ldarg.0
0x8b59  ldfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_authenticodeSignerInfo
0x8b5e  ldc.i4   0x80090002
0x8b63  callvirt instance void System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::set_ErrorCode(int32 value)
0x8b68  ldc.i4   0x80090002
0x8b6d  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x8b72  throw
0x8b73  ldloca.s 0
0x8b75  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x8b7a  brtrue.s loc_8B7E
0x8b7c  ldc.i4.0
0x8b7d  ret
0x8b7e  ldloc.s  0xA
0x8b80  brtrue.s loc_8C01
0x8b82  ldloc.s  7
  ... truncated ...
```
