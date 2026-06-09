# Microsoft.SharePoint.SPAppLicense::.ctor_1

- ea: `0xba1bf0`
- end: `0xba1ffb`
- name: `Microsoft.SharePoint.SPAppLicense::.ctor_1`
- size: `1035`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0xba2790`

## callees

- `0x577070`
- `0x93dab0`
- `0x957990`
- `0xba1bf0`
- `0xba2050`
- `0xba2070`
- `0xba2090`
- `0xba2100`
- `0xba2110`
- `0xba2150`
- `0xba2180`
- `0xba21a0`
- `0xba21d0`
- `0xba2270`
- `0xba2290`
- `0xba2310`
- `0xba2370`
- `0xba2380`
- `0xba2420`
- `0xba2450`
- `0xba2640`
- `0xba27a0`
- `0xba2850`
- `0xba2950`
- `0xbfdb50`

## string_xrefs

- `0xba1ca2`: `AppManagementAttributesMissingFromToken`
- `0xba1cb2`: `rawXMLEntitlementToken`
- `0xba1f0c`: `rawXMLEntitlementToken`
- `0xba1ceb`: `EntitlementTokenFieldProductId`
- `0xba1d3e`: `EntitlementTokenFieldDeploymentId`
- `0xba1d8b`: `EntitlementTokenFieldSiteLicense`
- `0xba1dd1`: `EntitlementTokenFieldTestLicense`
- `0xba1e0b`: `EntitlementTokenFieldTotalSeats`
- `0xba1e5f`: `EntitlementTokenEntitlementType`
- `0xba1f26`: `EntitlementTokenEntitlementType`
- `0xba1f02`: `License type field in the license token is invalid`
- `0xba1f46`: `EntitlementTokenFieldEntitlementAcquisitionDate`
- `0xba1f9d`: `EntitlementTokenFieldEntitlementExpiryDate`
- `0xba1fca`: `Token expiry date`
- `0xba1fcf`: `EntitlementTokenFieldTokenExpiryDate`

## pseudocode

```c

```

## disassembly

```asm
0xba1bf0  ldarg.0
0xba1bf1  call     instance void [mscorlib]System.Object::.ctor()
0xba1bf6  newobj   instance void <>c__DisplayClass2::.ctor()
0xba1bfb  stloc.s  5
0xba1bfd  ldarg.0
0xba1bfe  ldarg.2
0xba1bff  ldarg.3
0xba1c00  call     instance void Microsoft.SharePoint.SPAppLicense::SetMarkets(string newContentMarket, string newBillingMarket)
0xba1c05  ldarg.0
0xba1c06  ldarg.1
0xba1c07  call     instance void Microsoft.SharePoint.SPAppLicense::set_RawXMLLicenseToken(string value)
0xba1c0c  ldarg.s  4
0xba1c0e  brtrue.s loc_BA1C24
0xba1c10  ldloc.s  5
0xba1c12  ldarg.1
0xba1c13  call     class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.SharePoint.SPAppLicense::ParseAppLicenseToken(string rawXMLEntitlementToken)
0xba1c18  call     class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.SharePoint.SPAppLicense::ExtractTokenElementFromXML(class [System.Xml.Linq]System.Xml.Linq.XElement fullToken)
0xba1c1d  stfld    class [System.Xml.Linq]System.Xml.Linq.XElement <>c__DisplayClass2::token
0xba1c22  br.s     loc_BA1C2D
0xba1c24  ldloc.s  5
0xba1c26  ldarg.s  4
0xba1c28  stfld    class [System.Xml.Linq]System.Xml.Linq.XElement <>c__DisplayClass2::token
0xba1c2d  ldc.i4.8
0xba1c2e  newarr   [mscorlib]System.String
0xba1c33  stloc.s  6
0xba1c35  ldloc.s  6
0xba1c37  ldc.i4.0
0xba1c38  ldstr    aAid// "aid"
0xba1c3d  stelem.ref
0xba1c3e  ldloc.s  6
0xba1c40  ldc.i4.1
0xba1c41  ldstr    aPid// "pid"
0xba1c46  stelem.ref
0xba1c47  ldloc.s  6
0xba1c49  ldc.i4.2
0xba1c4a  ldstr    aCid_0// "cid"
0xba1c4f  stelem.ref
0xba1c50  ldloc.s  6
0xba1c52  ldc.i4.3
0xba1c53  ldstr    aDid_0// "did"
0xba1c58  stelem.ref
0xba1c59  ldloc.s  6
0xba1c5b  ldc.i4.4
0xba1c5c  ldstr    aTs// "ts"
0xba1c61  stelem.ref
0xba1c62  ldloc.s  6
0xba1c64  ldc.i4.5
0xba1c65  ldstr    aEt// "et"
0xba1c6a  stelem.ref
0xba1c6b  ldloc.s  6
0xba1c6d  ldc.i4.6
0xba1c6e  ldstr    aAd_1// "ad"
0xba1c73  stelem.ref
0xba1c74  ldloc.s  6
0xba1c76  ldc.i4.7
0xba1c77  ldstr    aTe_0// "te"
0xba1c7c  stelem.ref
0xba1c7d  ldloc.s  6
0xba1c7f  stloc.0
0xba1c80  ldloc.0
0xba1c81  ldloc.s  5
0xba1c83  ldftn    instance bool <>c__DisplayClass2::<.ctor>b__0(string attribute)
0xba1c89  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0xba1c8e  call     T0x2B00003A
0xba1c93  stloc.1
0xba1c94  ldloc.1
0xba1c95  call     T0x2B00005E
0xba1c9a  ldc.i4.0
0xba1c9b  ble.s    loc_BA1CBD
0xba1c9d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xba1ca2  ldstr    aAppmanagementa// "AppManagementAttributesMissingFromToken"
0xba1ca7  ldc.i4.0
0xba1ca8  newarr   [mscorlib]System.Object
0xba1cad  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0xba1cb2  ldstr    aRawxmlentitlem_1// "rawXMLEntitlementToken"
0xba1cb7  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xba1cbc  throw
0xba1cbd  ldarg.0
0xba1cbe  ldloc.s  5
0xba1cc0  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement <>c__DisplayClass2::token
0xba1cc5  ldstr    aAid// "aid"
0xba1cca  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0xba1ccf  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0xba1cd4  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0xba1cd9  call     instance void Microsoft.SharePoint.SPAppLicense::set_AssetId(string value)
0xba1cde  ldarg.0
0xba1cdf  ldloc.s  5
0xba1ce1  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement <>c__DisplayClass2::token
0xba1ce6  ldstr    aProductId// "Product ID"
0xba1ceb  ldstr    aEntitlementtok// "EntitlementTokenFieldProductId"
0xba1cf0  ldstr    aPid// "pid"
0xba1cf5  ldnull
0xba1cf6  ldftn    object Microsoft.SharePoint.SPAppLicense::ConvertToGuid(string attributeValue, string fieldName, string localizedFieldName)
0xba1cfc  newobj   instance void EntitlementFieldConversionDelegate::.ctor(object object, native int method)
0xba1d01  call     object Microsoft.SharePoint.SPAppLicense::ExtractEntitlementField(class [System.Xml.Linq]System.Xml.Linq.XElement token, string fieldName, string localizedFieldName, string attributeName, class EntitlementFieldConversionDelegate convert)
0xba1d06  unbox.any [mscorlib]System.Guid
0xba1d0b  call     instance void Microsoft.SharePoint.SPAppLicense::set_ProductId(valuetype [mscorlib]System.Guid value)
0xba1d10  ldarg.0
0xba1d11  ldloc.s  5
0xba1d13  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement <>c__DisplayClass2::token
0xba1d18  ldstr    aCid_0// "cid"
0xba1d1d  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0xba1d22  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0xba1d27  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0xba1d2c  call     instance void Microsoft.SharePoint.SPAppLicense::set_PurchaserIdentity(string value)
0xba1d31  ldarg.0
0xba1d32  ldloc.s  5
0xba1d34  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement <>c__DisplayClass2::token
0xba1d39  ldstr    aDeploymentId// "Deployment ID"
0xba1d3e  ldstr    aEntitlementtok_0// "EntitlementTokenFieldDeploymentId"
0xba1d43  ldstr    aDid_0// "did"
0xba1d48  ldnull
0xba1d49  ldftn    object Microsoft.SharePoint.SPAppLicense::ConvertToGuid(string attributeValue, string fieldName, string localizedFieldName)
0xba1d4f  newobj   instance void EntitlementFieldConversionDelegate::.ctor(object object, native int method)
0xba1d54  call     object Microsoft.SharePoint.SPAppLicense::ExtractEntitlementField(class [System.Xml.Linq]System.Xml.Linq.XElement token, string fieldName, string localizedFieldName, string attributeName, class EntitlementFieldConversionDelegate convert)
0xba1d59  unbox.any [mscorlib]System.Guid
0xba1d5e  call     instance void Microsoft.SharePoint.SPAppLicense::set_DeploymentId(valuetype [mscorlib]System.Guid value)
0xba1d63  ldloc.s  5
0xba1d65  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement <>c__DisplayClass2::token
0xba1d6a  ldstr    aSl// "sl"
0xba1d6f  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0xba1d74  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0xba1d79  brtrue.s loc_BA1D7F
0xba1d7b  ldc.i4.0
0xba1d7c  stloc.2
0xba1d7d  br.s     loc_BA1DAC
0xba1d7f  ldloc.s  5
0xba1d81  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement <>c__DisplayClass2::token
0xba1d86  ldstr    aSiteLicense// "Site license"
0xba1d8b  ldstr    aEntitlementtok_1// "EntitlementTokenFieldSiteLicense"
0xba1d90  ldstr    aSl// "sl"
0xba1d95  ldnull
0xba1d96  ldftn    object Microsoft.SharePoint.SPAppLicense::ConvertToBoolean(string attributeValue, string fieldName, string localizedFieldName)
0xba1d9c  newobj   instance void EntitlementFieldConversionDelegate::.ctor(object object, native int method)
0xba1da1  call     object Microsoft.SharePoint.SPAppLicense::ExtractEntitlementField(class [System.Xml.Linq]System.Xml.Linq.XElement token, string fieldName, string localizedFieldName, string attributeName, class EntitlementFieldConversionDelegate convert)
0xba1da6  unbox.any [mscorlib]System.Boolean
0xba1dab  stloc.2
0xba1dac  ldloc.s  5
0xba1dae  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement <>c__DisplayClass2::token
0xba1db3  ldstr    aTest_0// "test"
0xba1db8  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0xba1dbd  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0xba1dc2  brfalse.s loc_BA1DF8
0xba1dc4  ldarg.0
0xba1dc5  ldloc.s  5
0xba1dc7  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement <>c__DisplayClass2::token
0xba1dcc  ldstr    aTestLicense// "Test license"
0xba1dd1  ldstr    aEntitlementtok_2// "EntitlementTokenFieldTestLicense"
0xba1dd6  ldstr    aTest_0// "test"
0xba1ddb  ldnull
0xba1ddc  ldftn    object Microsoft.SharePoint.SPAppLicense::ConvertToBoolean(string attributeValue, string fieldName, string localizedFieldName)
0xba1de2  newobj   instance void EntitlementFieldConversionDelegate::.ctor(object object, native int method)
0xba1de7  call     object Microsoft.SharePoint.SPAppLicense::ExtractEntitlementField(class [System.Xml.Linq]System.Xml.Linq.XElement token, string fieldName, string localizedFieldName, string attributeName, class EntitlementFieldConversionDelegate convert)
0xba1dec  unbox.any [mscorlib]System.Boolean
0xba1df1  call     instance void Microsoft.SharePoint.SPAppLicense::set_IsTestLicense(bool value)
0xba1df6  br.s     loc_BA1DFF
0xba1df8  ldarg.0
0xba1df9  ldc.i4.0
0xba1dfa  call     instance void Microsoft.SharePoint.SPAppLicense::set_IsTestLicense(bool value)
0xba1dff  ldloc.s  5
0xba1e01  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement <>c__DisplayClass2::token
0xba1e06  ldstr    aTotalSeats// "Total seats"
0xba1e0b  ldstr    aEntitlementtok_3// "EntitlementTokenFieldTotalSeats"
0xba1e10  ldstr    aTs// "ts"
0xba1e15  ldnull
0xba1e16  ldftn    object Microsoft.SharePoint.SPAppLicense::ConvertToUInt(string attributeValue, string fieldName, string localizedFieldName)
0xba1e1c  newobj   instance void EntitlementFieldConversionDelegate::.ctor(object object, native int method)
0xba1e21  call     object Microsoft.SharePoint.SPAppLicense::ExtractEntitlementField(class [System.Xml.Linq]System.Xml.Linq.XElement token, string fieldName, string localizedFieldName, string attributeName, class EntitlementFieldConversionDelegate convert)
0xba1e26  unbox.any [mscorlib]System.UInt32
0xba1e2b  stloc.3
0xba1e2c  ldarg.0
0xba1e2d  ldloc.2
0xba1e2e  brtrue.s loc_BA1E33
0xba1e30  ldloc.3
0xba1e31  br.s     loc_BA1E34
0xba1e33  ldc.i4.m1
0xba1e34  call     instance void Microsoft.SharePoint.SPAppLicense::set_MaxUserCount(int32 value)
0xba1e39  ldloc.s  5
0xba1e3b  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement <>c__DisplayClass2::token
0xba1e40  ldstr    aEt// "et"
0xba1e45  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0xba1e4a  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0xba1e4f  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0xba1e54  stloc.s  4
0xba1e56  ldloc.s  4
0xba1e58  brtrue.s loc_BA1E69
0xba1e5a  ldstr    aLicenseType// "License type"
0xba1e5f  ldstr    aEntitlementtok_4// "EntitlementTokenEntitlementType"
0xba1e64  call     void Microsoft.SharePoint.SPAppLicense::NullAttributeValueAction(string fieldName, string localizedFieldName)
0xba1e69  ldloc.s  4
0xba1e6b  dup
0xba1e6c  stloc.s  7
0xba1e6e  brfalse  loc_BA1EF6
0xba1e73  ldloc.s  7
0xba1e75  ldstr    aFree_0// "Free"
0xba1e7a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xba1e7f  brtrue.s loc_BA1E9F
0xba1e81  ldloc.s  7
0xba1e83  ldstr    aPaid// "Paid"
0xba1e88  call     bool [mscorlib]System.String::op_Equality(string, string)
0xba1e8d  brtrue.s loc_BA1EB2
0xba1e8f  ldloc.s  7
0xba1e91  ldstr    aTrial// "Trial"
0xba1e96  call     bool [mscorlib]System.String::op_Equality(string, string)
0xba1e9b  brtrue.s loc_BA1ED4
0xba1e9d  br.s     loc_BA1EF6
0xba1e9f  ldarg.0
0xba1ea0  ldc.i4.0
0xba1ea1  call     instance void Microsoft.SharePoint.SPAppLicense::set_OmexLicenseType(valuetype Microsoft.SharePoint.OfficeMarketplaceLicenseType value)
0xba1ea6  ldarg.0
0xba1ea7  ldc.i4.1
0xba1ea8  call     instance void Microsoft.SharePoint.SPAppLicense::set_LicenseType(valuetype Microsoft.SharePoint.SPAppLicenseType value)
0xba1ead  br       loc_BA1F39
0xba1eb2  ldarg.0
0xba1eb3  ldc.i4.1
0xba1eb4  call     instance void Microsoft.SharePoint.SPAppLicense::set_OmexLicenseType(valuetype Microsoft.SharePoint.OfficeMarketplaceLicenseType value)
0xba1eb9  ldarg.0
0xba1eba  call     instance int32 Microsoft.SharePoint.SPAppLicense::get_MaxUserCount()
0xba1ebf  ldc.i4.m1
0xba1ec0  bne.un.s loc_BA1ECB
0xba1ec2  ldarg.0
0xba1ec3  ldc.i4.1
0xba1ec4  call     instance void Microsoft.SharePoint.SPAppLicense::set_LicenseType(valuetype Microsoft.SharePoint.SPAppLicenseType value)
0xba1ec9  br.s     loc_BA1F39
0xba1ecb  ldarg.0
0xba1ecc  ldc.i4.0
0xba1ecd  call     instance void Microsoft.SharePoint.SPAppLicense::set_LicenseType(valuetype Microsoft.SharePoint.SPAppLicenseType value)
0xba1ed2  br.s     loc_BA1F39
0xba1ed4  ldarg.0
0xba1ed5  ldc.i4.2
0xba1ed6  call     instance void Microsoft.SharePoint.SPAppLicense::set_OmexLicenseType(valuetype Microsoft.SharePoint.OfficeMarketplaceLicenseType value)
0xba1edb  ldarg.0
0xba1edc  call     instance int32 Microsoft.SharePoint.SPAppLicense::get_MaxUserCount()
0xba1ee1  ldc.i4.m1
0xba1ee2  bne.un.s loc_BA1EED
0xba1ee4  ldarg.0
0xba1ee5  ldc.i4.3
0xba1ee6  call     instance void Microsoft.SharePoint.SPAppLicense::set_LicenseType(valuetype Microsoft.SharePoint.SPAppLicenseType value)
0xba1eeb  br.s     loc_BA1F39
0xba1eed  ldarg.0
0xba1eee  ldc.i4.2
0xba1eef  call     instance void Microsoft.SharePoint.SPAppLicense::set_LicenseType(valuetype Microsoft.SharePoint.SPAppLicenseType value)
0xba1ef4  br.s     loc_BA1F39
0xba1ef6  ldc.i4   0x1480D3
0xba1efb  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppMarketplace()
0xba1f00  ldc.i4.s 0x32
0xba1f02  ldstr    aLicenseTypeFie// "License type field in the license token"...
0xba1f07  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0xba1f0c  ldstr    aRawxmlentitlem_1// "rawXMLEntitlementToken"
0xba1f11  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xba1f16  ldstr    aAppmanagemente_0// "AppManagementEntitlementFieldOutOfBound"...
0xba1f1b  ldc.i4.1
0xba1f1c  newarr   [mscorlib]System.Object
0xba1f21  stloc.s  8
0xba1f23  ldloc.s  8
0xba1f25  ldc.i4.0
0xba1f26  ldstr    aEntitlementtok_4// "EntitlementTokenEntitlementType"
0xba1f2b  stelem.ref
0xba1f2c  ldloc.s  8
0xba1f2e  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0xba1f33  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xba1f38  throw
0xba1f39  ldarg.0
0xba1f3a  ldloc.s  5
0xba1f3c  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement <>c__DisplayClass2::token
0xba1f41  ldstr    aLicenseAcquisi// "License acquisition date"
0xba1f46  ldstr    aEntitlementtok_5// "EntitlementTokenFieldEntitlementAcquisi"...
0xba1f4b  ldstr    aAd_1// "ad"
0xba1f50  ldnull
0xba1f51  ldftn    object Microsoft.SharePoint.SPAppLicense::ConvertToDateTime(string attributeValue, string fieldName, string localizedFieldName)
0xba1f57  newobj   instance void EntitlementFieldConversionDelegate::.ctor(object object, native int method)
0xba1f5c  call     object Microsoft.SharePoint.SPAppLicense::ExtractEntitlementField(class [System.Xml.Linq]System.Xml.Linq.XElement token, string fieldName, string localizedFieldName, string attributeName, class EntitlementFieldConversionDelegate convert)
0xba1f61  unbox.any [mscorlib]System.DateTime
0xba1f66  call     instance void Microsoft.SharePoint.SPAppLicense::set_LicenseAcquisitionDate(valuetype [mscorlib]System.DateTime value)
0xba1f6b  ldloc.s  5
0xba1f6d  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement <>c__DisplayClass2::token
0xba1f72  ldstr    aEd_0// "ed"
0xba1f77  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0xba1f7c  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0xba1f81  brtrue.s loc_BA1F90
0xba1f83  ldarg.0
0xba1f84  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0xba1f89  call     instance void Microsoft.SharePoint.SPAppLicense::set_ExpirationDate(valuetype [mscorlib]System.DateTime value)
0xba1f8e  br.s     loc_BA1FC2
0xba1f90  ldarg.0
0xba1f91  ldloc.s  5
0xba1f93  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement <>c__DisplayClass2::token
0xba1f98  ldstr    aLicenseExpiryD// "License expiry date"
0xba1f9d  ldstr    aEntitlementtok_6// "EntitlementTokenFieldEntitlementExpiryD"...
0xba1fa2  ldstr    aEd_0// "ed"
0xba1fa7  ldnull
0xba1fa8  ldftn    object Microsoft.SharePoint.SPAppLicense::ConvertToDateTime(string attributeValue, string fieldName, string localizedFieldName)
0xba1fae  newobj   instance void EntitlementFieldConversionDelegate::.ctor(object object, native int method)
0xba1fb3  call     object Microsoft.SharePoint.SPAppLicense::ExtractEntitlementField(class [System.Xml.Linq]System.Xml.Linq.XElement token, string fieldName, string localizedFieldName, string attributeName, class EntitlementFieldConversionDelegate convert)
0xba1fb8  unbox.any [mscorlib]System.DateTime
0xba1fbd  call     instance void Microsoft.SharePoint.SPAppLicense::set_ExpirationDate(valuetype [mscorlib]System.DateTime value)
0xba1fc2  ldarg.0
0xba1fc3  ldloc.s  5
0xba1fc5  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement <>c__DisplayClass2::token
0xba1fca  ldstr    aTokenExpiryDat// "Token expiry date"
  ... truncated ...
```
