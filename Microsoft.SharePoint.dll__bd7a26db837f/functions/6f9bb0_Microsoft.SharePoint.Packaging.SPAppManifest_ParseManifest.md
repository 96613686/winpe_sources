# Microsoft.SharePoint.Packaging.SPAppManifest::ParseManifest

- ea: `0x6f9bb0`
- end: `0x6f9dc3`
- name: `Microsoft.SharePoint.Packaging.SPAppManifest::ParseManifest`
- size: `531`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config, broker_com_uri`

## callers

- `0x702b20`
- `0x7072e0`

## callees

- `0x3192a0`
- `0x432d70`
- `0x577070`
- `0x6c9890`
- `0x6f95f0`
- `0x6f9600`
- `0x6f9610`
- `0x6f9630`
- `0x6f9670`
- `0x6f96a0`
- `0x6f96e0`
- `0x6f9710`
- `0x6f9730`
- `0x6f9780`
- `0x6f9880`
- `0x6f98b0`
- `0x6f9900`
- `0x6f9bb0`
- `0x6f9dd0`
- `0x6f9eb0`
- `0x6fa020`
- `0x6fa6a0`
- `0x6faa30`
- `0x6fc100`
- `0x93dae0`
- `0x957770`

## string_xrefs

- `0x6f9c7c`: `{http://schemas.microsoft.com/sharepoint/2012/app/manifest}AppPermissionRequests`
- `0x6f9cbe`: `{http://schemas.microsoft.com/sharepoint/2012/app/manifest}AppPrincipal`
- `0x6f9d06`: `{http://schemas.microsoft.com/sharepoint/2012/app/manifest}AppPrerequisites`
- `0x6f9ca8`: `{http://schemas.microsoft.com/sharepoint/2012/app/manifest}WebApiPermissionRequests`
- `0x6f9bd4`: `Created:`
- `0x6f9be2`: `Created:`
- `0x6f9c50`: `{http://schemas.microsoft.com/sharepoint/2012/app/manifest}Properties`
- `0x6f9c66`: `{http://schemas.microsoft.com/sharepoint/2012/app/manifest}RemoteEndpoints`
- `0x6f9cef`: `AppManifestMissingPropertiesSection`
- `0x6f9d29`: `AppLifecycleError_AppManifest`
- `0x6f9d38`: `AppManifestValidationErrors`
- `0x6f9d55`: `AppLifeCycleManifestParsed`
- `0x6f9d8b`: `SPAppManifest: Parsed manifest has productId {0} version {1} name '{2}'`

## pseudocode

```c

```

## disassembly

```asm
0x6f9bb0  ldarg.0
0x6f9bb1  ldfld    class [System.Xml.Linq]System.Xml.Linq.XDocument Microsoft.SharePoint.Packaging.SPAppManifest::appManifestXDoc
0x6f9bb6  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XNode [System.Xml.Linq]System.Xml.Linq.XContainer::get_FirstNode()
0x6f9bbb  stloc.0
0x6f9bbc  br.s     loc_6F9C38
0x6f9bbe  ldloc.0
0x6f9bbf  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml.Linq]System.Xml.Linq.XObject::get_NodeType()
0x6f9bc4  ldc.i4.8
0x6f9bc5  bne.un.s loc_6F9C31
0x6f9bc7  ldloc.0
0x6f9bc8  castclass [System.Xml.Linq]System.Xml.Linq.XComment
0x6f9bcd  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XComment::get_Value()
0x6f9bd2  stloc.1
0x6f9bd3  ldloc.1
0x6f9bd4  ldstr    aCreated_1// "Created:"
0x6f9bd9  ldc.i4.5
0x6f9bda  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x6f9bdf  brfalse.s loc_6F9C03
0x6f9be1  ldloc.1
0x6f9be2  ldstr    aCreated_1// "Created:"
0x6f9be7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6f9bec  callvirt instance string [mscorlib]System.String::Substring(int32)
0x6f9bf1  ldloca.s 2
0x6f9bf3  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x6f9bf8  brfalse.s loc_6F9C03
0x6f9bfa  ldarg.0
0x6f9bfb  ldloc.2
0x6f9bfc  call     instance void Microsoft.SharePoint.Packaging.SPAppManifest::set_CreatedID(valuetype [mscorlib]System.Guid value)
0x6f9c01  br.s     loc_6F9C31
0x6f9c03  ldloc.1
0x6f9c04  ldstr    aPublished_1// "Published:"
0x6f9c09  ldc.i4.5
0x6f9c0a  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x6f9c0f  brfalse.s loc_6F9C31
0x6f9c11  ldloc.1
0x6f9c12  ldstr    aPublished_1// "Published:"
0x6f9c17  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6f9c1c  callvirt instance string [mscorlib]System.String::Substring(int32)
0x6f9c21  ldloca.s 2
0x6f9c23  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x6f9c28  brfalse.s loc_6F9C31
0x6f9c2a  ldarg.0
0x6f9c2b  ldloc.2
0x6f9c2c  call     instance void Microsoft.SharePoint.Packaging.SPAppManifest::set_PublishedID(valuetype [mscorlib]System.Guid value)
0x6f9c31  ldloc.0
0x6f9c32  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XNode [System.Xml.Linq]System.Xml.Linq.XNode::get_NextNode()
0x6f9c37  stloc.0
0x6f9c38  ldloc.0
0x6f9c39  brtrue.s loc_6F9BBE
0x6f9c3b  ldarg.0
0x6f9c3c  ldfld    class [System.Xml.Linq]System.Xml.Linq.XDocument Microsoft.SharePoint.Packaging.SPAppManifest::appManifestXDoc
0x6f9c41  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XDocument::get_Root()
0x6f9c46  stloc.3
0x6f9c47  ldarg.0
0x6f9c48  ldloc.3
0x6f9c49  call     instance void Microsoft.SharePoint.Packaging.SPAppManifest::ParseAppElementAttributes(class [System.Xml.Linq]System.Xml.Linq.XElement root)
0x6f9c4e  ldarg.0
0x6f9c4f  ldloc.3
0x6f9c50  ldstr    aHttpSchemasMic_112// "{http://schemas.microsoft.com/sharepoin"...
0x6f9c55  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6f9c5a  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6f9c5f  call     instance void Microsoft.SharePoint.Packaging.SPAppManifest::ParseProperties(class [System.Xml.Linq]System.Xml.Linq.XElement propertiesElement)
0x6f9c64  ldarg.0
0x6f9c65  ldloc.3
0x6f9c66  ldstr    aHttpSchemasMic_113// "{http://schemas.microsoft.com/sharepoin"...
0x6f9c6b  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6f9c70  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6f9c75  call     instance void Microsoft.SharePoint.Packaging.SPAppManifest::ParseRemoteEndpoints(class [System.Xml.Linq]System.Xml.Linq.XElement remoteEndpointsElement)
0x6f9c7a  ldarg.0
0x6f9c7b  ldloc.3
0x6f9c7c  ldstr    aHttpSchemasMic_9// "{http://schemas.microsoft.com/sharepoin"...
0x6f9c81  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6f9c86  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6f9c8b  call     instance void Microsoft.SharePoint.Packaging.SPAppManifest::set_AppPermissionRequests(class [System.Xml.Linq]System.Xml.Linq.XElement value)
0x6f9c90  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Packaging.SPAppManifest::WebApiPermissionRequestsValidationKillSwitch
0x6f9c95  ldstr    a102417// "10/24/17"
0x6f9c9a  ldstr    aEnableWebapipe// "Enable WebApiPermissionRequests Package"...
0x6f9c9f  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x6f9ca4  brtrue.s loc_6F9CBC
0x6f9ca6  ldarg.0
0x6f9ca7  ldloc.3
0x6f9ca8  ldstr    aHttpSchemasMic_111// "{http://schemas.microsoft.com/sharepoin"...
0x6f9cad  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6f9cb2  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6f9cb7  call     instance void Microsoft.SharePoint.Packaging.SPAppManifest::set_WebApiPermissionRequests(class [System.Xml.Linq]System.Xml.Linq.XElement value)
0x6f9cbc  ldarg.0
0x6f9cbd  ldloc.3
0x6f9cbe  ldstr    aHttpSchemasMic_11// "{http://schemas.microsoft.com/sharepoin"...
0x6f9cc3  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6f9cc8  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6f9ccd  call     instance void Microsoft.SharePoint.Packaging.SPAppManifest::set_AppPrincipal(class [System.Xml.Linq]System.Xml.Linq.XElement value)
0x6f9cd2  call     bool Microsoft.SharePoint.ClientSideComponent.SPClientSideFrameworkFlights::IsClientSideThirdPartyPackageDeploymentEnabled()
0x6f9cd7  brfalse.s loc_6F9D04
0x6f9cd9  ldarg.0
0x6f9cda  call     instance bool Microsoft.SharePoint.Packaging.SPAppManifest::get_IsClientSideSolution()
0x6f9cdf  brtrue.s loc_6F9D04
0x6f9ce1  ldarg.0
0x6f9ce2  call     instance class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.SharePoint.Packaging.SPAppManifest::get_AppPrincipal()
0x6f9ce7  brtrue.s loc_6F9D04
0x6f9ce9  ldarg.0
0x6f9cea  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x6f9cef  ldstr    aAppmanifestmis// "AppManifestMissingPropertiesSection"
0x6f9cf4  ldc.i4.0
0x6f9cf5  newarr   [mscorlib]System.Object
0x6f9cfa  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x6f9cff  call     instance void Microsoft.SharePoint.Packaging.SPAppManifest::AddMessageToErrorContext(string message)
0x6f9d04  ldarg.0
0x6f9d05  ldloc.3
0x6f9d06  ldstr    aHttpSchemasMic_12// "{http://schemas.microsoft.com/sharepoin"...
0x6f9d0b  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x6f9d10  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x6f9d15  call     instance void Microsoft.SharePoint.Packaging.SPAppManifest::set_AppPrerequisites(class [System.Xml.Linq]System.Xml.Linq.XElement value)
0x6f9d1a  ldarg.0
0x6f9d1b  call     instance bool Microsoft.SharePoint.Packaging.SPAppManifest::get_HasValidationErrors()
0x6f9d20  brfalse.s loc_6F9D55
0x6f9d22  ldc.i4.2
0x6f9d23  ldarg.0
0x6f9d24  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6f9d29  ldstr    aApplifecycleer_11// "AppLifecycleError_AppManifest"
0x6f9d2e  call     void Microsoft.SharePoint.Administration.SPAppInstanceErrorTracker::PushErrorContext(valuetype Microsoft.SharePoint.Administration.SPAppInstanceErrorType type, class [mscorlib]System.Type source, string detailToken)
0x6f9d33  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x6f9d38  ldstr    aAppmanifestval// "AppManifestValidationErrors"
0x6f9d3d  ldc.i4.0
0x6f9d3e  newarr   [mscorlib]System.Object
0x6f9d43  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x6f9d48  ldnull
0x6f9d49  ldarg.0
0x6f9d4a  call     instance class Microsoft.SharePoint.ValidationErrorContext Microsoft.SharePoint.Packaging.SPAppManifest::get_ErrorContext()
0x6f9d4f  newobj   instance void Microsoft.SharePoint.AppPackageValidationException::.ctor(string message, class [mscorlib]System.Exception innerException, class Microsoft.SharePoint.ValidationErrorContext errorContext)
0x6f9d54  throw
0x6f9d55  ldstr    aApplifecyclema// "AppLifeCycleManifestParsed"
0x6f9d5a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x6f9d5f  stloc.s  4
0x6f9d61  ldloc.s  4
0x6f9d63  ldstr    aProductid_0// "ProductId"
0x6f9d68  ldarg.0
0x6f9d69  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Packaging.SPAppManifest::get_ProductID()
0x6f9d6e  box      [mscorlib]System.Guid
0x6f9d73  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6f9d78  ldloc.s  4
0x6f9d7a  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x6f9d7f  ldc.i4   0x2C034B
0x6f9d84  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x6f9d89  ldc.i4.s 0x32
0x6f9d8b  ldstr    aSpappmanifestP// "SPAppManifest: Parsed manifest has prod"...
0x6f9d90  ldc.i4.3
0x6f9d91  newarr   [mscorlib]System.Object
0x6f9d96  stloc.s  5
0x6f9d98  ldloc.s  5
0x6f9d9a  ldc.i4.0
0x6f9d9b  ldarg.0
0x6f9d9c  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Packaging.SPAppManifest::get_ProductID()
0x6f9da1  box      [mscorlib]System.Guid
0x6f9da6  stelem.ref
0x6f9da7  ldloc.s  5
0x6f9da9  ldc.i4.1
0x6f9daa  ldarg.0
0x6f9dab  call     instance class [mscorlib]System.Version Microsoft.SharePoint.Packaging.SPAppManifest::get_Version()
0x6f9db0  stelem.ref
0x6f9db1  ldloc.s  5
0x6f9db3  ldc.i4.2
0x6f9db4  ldarg.0
0x6f9db5  call     instance string Microsoft.SharePoint.Packaging.SPAppManifest::get_Name()
0x6f9dba  stelem.ref
0x6f9dbb  ldloc.s  5
0x6f9dbd  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x6f9dc2  ret
```
