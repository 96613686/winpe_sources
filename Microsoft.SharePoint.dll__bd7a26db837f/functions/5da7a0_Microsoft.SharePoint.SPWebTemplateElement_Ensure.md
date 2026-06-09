# Microsoft.SharePoint.SPWebTemplateElement::Ensure

- ea: `0x5da7a0`
- end: `0x5daf8d`
- name: `Microsoft.SharePoint.SPWebTemplateElement::Ensure`
- size: `2029`
- prototype: ``
- caller_count: `44`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x5d9ec0`
- `0x5d9ed0`
- `0x5d9ee0`
- `0x5d9ef0`
- `0x5d9f00`
- `0x5d9f10`
- `0x5d9f20`
- `0x5d9f30`
- `0x5d9f40`
- `0x5d9f50`
- `0x5d9f60`
- `0x5d9f70`
- `0x5d9f80`
- `0x5d9f90`
- `0x5d9fa0`
- `0x5d9fb0`
- `0x5d9fc0`
- `0x5d9fd0`
- `0x5d9fe0`
- `0x5d9ff0`
- `0x5da000`
- `0x5da010`
- `0x5da020`
- `0x5da030`
- `0x5da040`
- `0x5da050`
- `0x5da060`
- `0x5da070`
- `0x5da080`
- `0x5da090`
- `0x5da0a0`
- `0x5da0b0`
- `0x5da0c0`
- `0x5da0d0`
- `0x5da0e0`
- `0x5da0f0`
- `0x5da100`
- `0x5da110`
- `0x5da120`
- `0x5da130`
- `0x5da140`
- `0x5da150`
- `0x5da170`
- `0x5daf90`

## callees

- `0x197ad0`
- `0x19c6f0`
- `0x2960c0`
- `0x296120`
- `0x2ab770`
- `0x5da7a0`
- `0x5db300`
- `0x5db340`
- `0x5db3e0`
- `0x6c9890`
- `0x957430`

## string_xrefs

- `0x5da83d`: `WebTemplate`
- `0x5da8aa`: `WebTemplate`
- `0x5da917`: `WebTemplate`
- `0x5da973`: `WebTemplate`
- `0x5da9e2`: `WebTemplate`
- `0x5daa3e`: `WebTemplate`
- `0x5dad7e`: `HasPendingWebTemplateExtension`
- `0x5dad90`: `HasPendingWebTemplateExtension`
- `0x5da8e1`: `BaseTemplateID`
- `0x5da90e`: `BaseTemplateID`
- `0x5da96a`: `BaseTemplateID`
- `0x5da874`: `BaseTemplateName`
- `0x5da8a1`: `BaseTemplateName`
- `0x5da9ac`: `BaseConfigurationID`
- `0x5da9d9`: `BaseConfigurationID`
- `0x5daa35`: `BaseConfigurationID`
- `0x5daf6b`: `CommentsOnSitePagesDisabled`
- `0x5dade6`: `HideSiteContentsLink`
- `0x5dae46`: `UIVersionConfigurationEnabled`
- `0x5da95a`: `CannotConvertFeatureXmlAttributeToPositiveInt`
- `0x5daa25`: `CannotConvertFeatureXmlAttributeToPositiveInt`

## pseudocode

```c

```

## disassembly

```asm
0x5da7a0  ldnull
0x5da7a1  stloc.0
0x5da7a2  ldnull
0x5da7a3  stloc.1
0x5da7a4  ldnull
0x5da7a5  stloc.2
0x5da7a6  ldnull
0x5da7a7  stloc.3
0x5da7a8  ldnull
0x5da7a9  stloc.s  4
0x5da7ab  ldnull
0x5da7ac  stloc.s  5
0x5da7ae  ldnull
0x5da7af  stloc.s  6
0x5da7b1  ldnull
0x5da7b2  stloc.s  7
0x5da7b4  ldnull
0x5da7b5  stloc.s  8
0x5da7b7  ldnull
0x5da7b8  stloc.s  9
0x5da7ba  ldnull
0x5da7bb  stloc.s  0xA
0x5da7bd  ldnull
0x5da7be  stloc.s  0xB
0x5da7c0  ldnull
0x5da7c1  stloc.s  0xC
0x5da7c3  ldnull
0x5da7c4  stloc.s  0xD
0x5da7c6  ldnull
0x5da7c7  stloc.s  0xE
0x5da7c9  ldnull
0x5da7ca  stloc.s  0xF
0x5da7cc  ldnull
0x5da7cd  stloc.s  0x10
0x5da7cf  ldnull
0x5da7d0  stloc.s  0x11
0x5da7d2  ldnull
0x5da7d3  stloc.s  0x12
0x5da7d5  ldnull
0x5da7d6  stloc.s  0x13
0x5da7d8  ldnull
0x5da7d9  stloc.s  0x14
0x5da7db  ldnull
0x5da7dc  stloc.s  0x15
0x5da7de  ldnull
0x5da7df  stloc.s  0x16
0x5da7e1  ldnull
0x5da7e2  stloc.s  0x17
0x5da7e4  ldnull
0x5da7e5  stloc.s  0x18
0x5da7e7  ldnull
0x5da7e8  stloc.s  0x19
0x5da7ea  ldnull
0x5da7eb  stloc.s  0x1A
0x5da7ed  ldnull
0x5da7ee  stloc.s  0x1B
0x5da7f0  ldnull
0x5da7f1  stloc.s  0x1C
0x5da7f3  ldnull
0x5da7f4  stloc.s  0x1D
0x5da7f6  ldarg.0
0x5da7f7  ldfld    bool Microsoft.SharePoint.SPWebTemplateElement::m_isInitialized
0x5da7fc  brtrue   loc_5DAF8C
0x5da801  ldarg.0
0x5da802  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.SharePoint.Administration.SPElementDefinition::get_XmlDefinition()
0x5da807  ldstr    aName_0// "Name"
0x5da80c  call     string Microsoft.SharePoint.Utilities.SPUtility::XmlGetAttrVal(class [System.Xml]System.Xml.XmlNode xn, string attr)
0x5da811  stloc.0
0x5da812  ldloc.0
0x5da813  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5da818  brfalse.s loc_5DA867
0x5da81a  ldc.i4   0x38356D65
0x5da81f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_FeaturesInfrastructure()
0x5da824  ldstr    aCannotfindfeat_2// "CannotFindFeatureAttribute"
0x5da829  ldc.i4.3
0x5da82a  newarr   [mscorlib]System.Object
0x5da82f  stloc.s  0x21
0x5da831  ldloc.s  0x21
0x5da833  ldc.i4.0
0x5da834  ldstr    aName_0// "Name"
0x5da839  stelem.ref
0x5da83a  ldloc.s  0x21
0x5da83c  ldc.i4.1
0x5da83d  ldstr    aWebtemplate// "WebTemplate"
0x5da842  stelem.ref
0x5da843  ldloc.s  0x21
0x5da845  ldc.i4.2
0x5da846  ldarg.0
0x5da847  call     instance class Microsoft.SharePoint.Administration.SPFeatureDefinition Microsoft.SharePoint.Administration.SPElementDefinition::get_FeatureDefinition()
0x5da84c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPFeatureDefinition::get_Id()
0x5da851  stloc.s  0x22
0x5da853  ldloca.s 0x22
0x5da855  ldstr    aB// "B"
0x5da85a  call     instance string [mscorlib]System.Guid::ToString(string)
0x5da85f  stelem.ref
0x5da860  ldloc.s  0x21
0x5da862  call     void Microsoft.SharePoint.Utilities.SPUtility::ThrowSPExceptionWithTraceTag(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCat traceCategory, string resourceId, object[] resourceArgs)
0x5da867  ldarg.0
0x5da868  ldloc.0
0x5da869  stfld    string Microsoft.SharePoint.SPWebTemplateElement::m_name
0x5da86e  ldarg.0
0x5da86f  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.SharePoint.Administration.SPElementDefinition::get_XmlDefinition()
0x5da874  ldstr    aBasetemplatena// "BaseTemplateName"
0x5da879  call     string Microsoft.SharePoint.Utilities.SPUtility::XmlGetAttrVal(class [System.Xml]System.Xml.XmlNode xn, string attr)
0x5da87e  stloc.1
0x5da87f  ldloc.1
0x5da880  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5da885  brfalse.s loc_5DA8D4
0x5da887  ldc.i4   0x38356D66
0x5da88c  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_FeaturesInfrastructure()
0x5da891  ldstr    aCannotfindfeat_2// "CannotFindFeatureAttribute"
0x5da896  ldc.i4.3
0x5da897  newarr   [mscorlib]System.Object
0x5da89c  stloc.s  0x23
0x5da89e  ldloc.s  0x23
0x5da8a0  ldc.i4.0
0x5da8a1  ldstr    aBasetemplatena// "BaseTemplateName"
0x5da8a6  stelem.ref
0x5da8a7  ldloc.s  0x23
0x5da8a9  ldc.i4.1
0x5da8aa  ldstr    aWebtemplate// "WebTemplate"
0x5da8af  stelem.ref
0x5da8b0  ldloc.s  0x23
0x5da8b2  ldc.i4.2
0x5da8b3  ldarg.0
0x5da8b4  call     instance class Microsoft.SharePoint.Administration.SPFeatureDefinition Microsoft.SharePoint.Administration.SPElementDefinition::get_FeatureDefinition()
0x5da8b9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPFeatureDefinition::get_Id()
0x5da8be  stloc.s  0x24
0x5da8c0  ldloca.s 0x24
0x5da8c2  ldstr    aB// "B"
0x5da8c7  call     instance string [mscorlib]System.Guid::ToString(string)
0x5da8cc  stelem.ref
0x5da8cd  ldloc.s  0x23
0x5da8cf  call     void Microsoft.SharePoint.Utilities.SPUtility::ThrowSPExceptionWithTraceTag(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCat traceCategory, string resourceId, object[] resourceArgs)
0x5da8d4  ldarg.0
0x5da8d5  ldloc.1
0x5da8d6  stfld    string Microsoft.SharePoint.SPWebTemplateElement::m_webTemplateName
0x5da8db  ldarg.0
0x5da8dc  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.SharePoint.Administration.SPElementDefinition::get_XmlDefinition()
0x5da8e1  ldstr    aBasetemplateid_0// "BaseTemplateID"
0x5da8e6  call     string Microsoft.SharePoint.Utilities.SPUtility::XmlGetAttrVal(class [System.Xml]System.Xml.XmlNode xn, string attr)
0x5da8eb  stloc.2
0x5da8ec  ldloc.2
0x5da8ed  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5da8f2  brfalse.s loc_5DA941
0x5da8f4  ldc.i4   0x38356D67
0x5da8f9  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_FeaturesInfrastructure()
0x5da8fe  ldstr    aCannotfindfeat_2// "CannotFindFeatureAttribute"
0x5da903  ldc.i4.3
0x5da904  newarr   [mscorlib]System.Object
0x5da909  stloc.s  0x25
0x5da90b  ldloc.s  0x25
0x5da90d  ldc.i4.0
0x5da90e  ldstr    aBasetemplateid_0// "BaseTemplateID"
0x5da913  stelem.ref
0x5da914  ldloc.s  0x25
0x5da916  ldc.i4.1
0x5da917  ldstr    aWebtemplate// "WebTemplate"
0x5da91c  stelem.ref
0x5da91d  ldloc.s  0x25
0x5da91f  ldc.i4.2
0x5da920  ldarg.0
0x5da921  call     instance class Microsoft.SharePoint.Administration.SPFeatureDefinition Microsoft.SharePoint.Administration.SPElementDefinition::get_FeatureDefinition()
0x5da926  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPFeatureDefinition::get_Id()
0x5da92b  stloc.s  0x26
0x5da92d  ldloca.s 0x26
0x5da92f  ldstr    aB// "B"
0x5da934  call     instance string [mscorlib]System.Guid::ToString(string)
0x5da939  stelem.ref
0x5da93a  ldloc.s  0x25
0x5da93c  call     void Microsoft.SharePoint.Utilities.SPUtility::ThrowSPExceptionWithTraceTag(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCat traceCategory, string resourceId, object[] resourceArgs)
0x5da941  ldloc.2
0x5da942  call     class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.NumberFormatInfo::get_InvariantInfo()
0x5da947  call     unsigned int32 [mscorlib]System.UInt32::Parse(string, class [mscorlib]System.IFormatProvider)
0x5da94c  pop
0x5da94d  leave.s  loc_5DA99F
0x5da94f  pop
0x5da950  ldc.i4   0x38356D6B
0x5da955  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_FeaturesInfrastructure()
0x5da95a  ldstr    aCannotconvertf// "CannotConvertFeatureXmlAttributeToPosit"...
0x5da95f  ldc.i4.3
0x5da960  newarr   [mscorlib]System.Object
0x5da965  stloc.s  0x27
0x5da967  ldloc.s  0x27
0x5da969  ldc.i4.0
0x5da96a  ldstr    aBasetemplateid_0// "BaseTemplateID"
0x5da96f  stelem.ref
0x5da970  ldloc.s  0x27
0x5da972  ldc.i4.1
0x5da973  ldstr    aWebtemplate// "WebTemplate"
0x5da978  stelem.ref
0x5da979  ldloc.s  0x27
0x5da97b  ldc.i4.2
0x5da97c  ldarg.0
0x5da97d  call     instance class Microsoft.SharePoint.Administration.SPFeatureDefinition Microsoft.SharePoint.Administration.SPElementDefinition::get_FeatureDefinition()
0x5da982  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPFeatureDefinition::get_Id()
0x5da987  stloc.s  0x28
0x5da989  ldloca.s 0x28
0x5da98b  ldstr    aB// "B"
0x5da990  call     instance string [mscorlib]System.Guid::ToString(string)
0x5da995  stelem.ref
0x5da996  ldloc.s  0x27
0x5da998  call     void Microsoft.SharePoint.Utilities.SPUtility::ThrowSPExceptionWithTraceTag(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCat traceCategory, string resourceId, object[] resourceArgs)
0x5da99d  leave.s  loc_5DA99F
0x5da99f  ldarg.0
0x5da9a0  ldloc.2
0x5da9a1  stfld    string Microsoft.SharePoint.SPWebTemplateElement::m_webTemplateId
0x5da9a6  ldarg.0
0x5da9a7  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.SharePoint.Administration.SPElementDefinition::get_XmlDefinition()
0x5da9ac  ldstr    aBaseconfigurat// "BaseConfigurationID"
0x5da9b1  call     string Microsoft.SharePoint.Utilities.SPUtility::XmlGetAttrVal(class [System.Xml]System.Xml.XmlNode xn, string attr)
0x5da9b6  stloc.3
0x5da9b7  ldloc.3
0x5da9b8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5da9bd  brfalse.s loc_5DAA0C
0x5da9bf  ldc.i4   0x38356D68
0x5da9c4  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_FeaturesInfrastructure()
0x5da9c9  ldstr    aCannotfindfeat_2// "CannotFindFeatureAttribute"
0x5da9ce  ldc.i4.3
0x5da9cf  newarr   [mscorlib]System.Object
0x5da9d4  stloc.s  0x29
0x5da9d6  ldloc.s  0x29
0x5da9d8  ldc.i4.0
0x5da9d9  ldstr    aBaseconfigurat// "BaseConfigurationID"
0x5da9de  stelem.ref
0x5da9df  ldloc.s  0x29
0x5da9e1  ldc.i4.1
0x5da9e2  ldstr    aWebtemplate// "WebTemplate"
0x5da9e7  stelem.ref
0x5da9e8  ldloc.s  0x29
0x5da9ea  ldc.i4.2
0x5da9eb  ldarg.0
0x5da9ec  call     instance class Microsoft.SharePoint.Administration.SPFeatureDefinition Microsoft.SharePoint.Administration.SPElementDefinition::get_FeatureDefinition()
0x5da9f1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPFeatureDefinition::get_Id()
0x5da9f6  stloc.s  0x2A
0x5da9f8  ldloca.s 0x2A
0x5da9fa  ldstr    aB// "B"
0x5da9ff  call     instance string [mscorlib]System.Guid::ToString(string)
0x5daa04  stelem.ref
0x5daa05  ldloc.s  0x29
0x5daa07  call     void Microsoft.SharePoint.Utilities.SPUtility::ThrowSPExceptionWithTraceTag(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCat traceCategory, string resourceId, object[] resourceArgs)
0x5daa0c  ldloc.3
0x5daa0d  call     class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.NumberFormatInfo::get_InvariantInfo()
0x5daa12  call     unsigned int32 [mscorlib]System.UInt32::Parse(string, class [mscorlib]System.IFormatProvider)
0x5daa17  pop
0x5daa18  leave.s  loc_5DAA6A
0x5daa1a  pop
0x5daa1b  ldc.i4   0x38356D6C
0x5daa20  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_FeaturesInfrastructure()
0x5daa25  ldstr    aCannotconvertf// "CannotConvertFeatureXmlAttributeToPosit"...
0x5daa2a  ldc.i4.3
0x5daa2b  newarr   [mscorlib]System.Object
0x5daa30  stloc.s  0x2B
0x5daa32  ldloc.s  0x2B
0x5daa34  ldc.i4.0
0x5daa35  ldstr    aBaseconfigurat// "BaseConfigurationID"
0x5daa3a  stelem.ref
0x5daa3b  ldloc.s  0x2B
0x5daa3d  ldc.i4.1
0x5daa3e  ldstr    aWebtemplate// "WebTemplate"
0x5daa43  stelem.ref
0x5daa44  ldloc.s  0x2B
0x5daa46  ldc.i4.2
0x5daa47  ldarg.0
0x5daa48  call     instance class Microsoft.SharePoint.Administration.SPFeatureDefinition Microsoft.SharePoint.Administration.SPElementDefinition::get_FeatureDefinition()
0x5daa4d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPFeatureDefinition::get_Id()
0x5daa52  stloc.s  0x2C
0x5daa54  ldloca.s 0x2C
0x5daa56  ldstr    aB// "B"
0x5daa5b  call     instance string [mscorlib]System.Guid::ToString(string)
0x5daa60  stelem.ref
0x5daa61  ldloc.s  0x2B
0x5daa63  call     void Microsoft.SharePoint.Utilities.SPUtility::ThrowSPExceptionWithTraceTag(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCat traceCategory, string resourceId, object[] resourceArgs)
0x5daa68  leave.s  loc_5DAA6A
0x5daa6a  ldarg.0
0x5daa6b  ldloc.3
0x5daa6c  stfld    string Microsoft.SharePoint.SPWebTemplateElement::m_webTemplateConfigurationId
0x5daa71  ldarg.0
0x5daa72  ldloc.1
0x5daa73  ldstr    asc_C80842// "#"
0x5daa78  ldloc.3
0x5daa79  call     string [mscorlib]System.String::Concat(string, string, string)
0x5daa7e  stfld    string Microsoft.SharePoint.SPWebTemplateElement::m_webTemplateNameWithConfigurationId
0x5daa83  ldarg.0
0x5daa84  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.SharePoint.Administration.SPElementDefinition::get_XmlDefinition()
0x5daa89  ldstr    aLocale_0// "Locale"
0x5daa8e  call     string Microsoft.SharePoint.Utilities.SPUtility::XmlGetAttrVal(class [System.Xml]System.Xml.XmlNode xn, string attr)
0x5daa93  stloc.s  0x10
0x5daa95  ldarg.0
0x5daa96  ldloc.s  0x10
0x5daa98  ldstr    aLocale_0// "Locale"
0x5daa9d  ldarg.0
0x5daa9e  ldflda   valuetype [mscorlib]System.Nullable`1<int32> Microsoft.SharePoint.SPWebTemplateElement::m_localeId
0x5daaa3  call     instance void Microsoft.SharePoint.SPWebTemplateElement::EvaluateNullableUIntAttribute(string source, string attribute, valuetype [mscorlib]System.Nullable`1<int32>& target)
0x5daaa8  ldarg.0
0x5daaa9  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.SharePoint.Administration.SPElementDefinition::get_XmlDefinition()
0x5daaae  ldstr    aTimezone_1// "TimeZone"
0x5daab3  call     string Microsoft.SharePoint.Utilities.SPUtility::XmlGetAttrVal(class [System.Xml]System.Xml.XmlNode xn, string attr)
0x5daab8  stloc.s  0x11
0x5daaba  ldarg.0
  ... truncated ...
```
