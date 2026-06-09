# System.Web.UI.WebControls.WebParts.WebPartManager::LoadDynamicWebPart

- ea: `0x108cf0`
- end: `0x108f96`
- name: `System.Web.UI.WebControls.WebParts.WebPartManager::LoadDynamicWebPart`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x108fa0`

## callees

- `0x169c0`
- `0x34f20`
- `0x34fa0`
- `0x5ef80`
- `0x5f1e0`
- `0x5f680`
- `0x80010`
- `0x100630`
- `0x104e50`
- `0x104f20`
- `0x106e20`
- `0x106e50`
- `0x108970`
- `0x108cf0`
- `0x10a720`
- `0x10a770`
- `0x10a830`
- `0x10a860`
- `0x10bfb0`
- `0x10c9f0`

## string_xrefs

- `0x108daf`: `WebPartManager_CantCreateInstance`
- `0x108e99`: `WebPartManager_CantCreateInstance`
- `0x108dbd`: `WebPartManager_CantCreateInstanceWithType`
- `0x108ea7`: `WebPartManager_CantCreateInstanceWithType`
- `0x108ed8`: `WebPartManager_InvalidPath`
- `0x108ee6`: `WebPartManager_InvalidPathWithPath`
- `0x108efe`: `WebPartManager_CantCreateGeneric`

## pseudocode

```c

```

## disassembly

```asm
0x108cf0  ldnull
0x108cf1  stloc.0
0x108cf2  ldarg.2
0x108cf3  ldc.i4.0
0x108cf4  call     class [mscorlib]System.Type System.Web.UI.WebControls.WebParts.WebPartUtil::DeserializeType(string typeName, bool throwOnError)
0x108cf9  stloc.1
0x108cfa  ldloc.1
0x108cfb  ldnull
0x108cfc  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x108d01  brfalse.s loc_108D4C
0x108d03  ldarg.0
0x108d04  callvirt instance class System.Web.HttpContext System.Web.UI.Control::get_Context()
0x108d09  brfalse.s loc_108D25
0x108d0b  ldarg.0
0x108d0c  callvirt instance class System.Web.HttpContext System.Web.UI.Control::get_Context()
0x108d11  callvirt instance bool System.Web.HttpContext::get_IsCustomErrorEnabled()
0x108d16  brfalse.s loc_108D25
0x108d18  ldstr    aWebpartmanager_38// "WebPartManager_ErrorLoadingWebPartType"
0x108d1d  call     string System.Web.SR::GetString(string name)
0x108d22  stloc.2
0x108d23  br.s     loc_108D3A
0x108d25  ldstr    aInvalidType// "Invalid_type"
0x108d2a  ldc.i4.1
0x108d2b  newarr   [mscorlib]System.Object
0x108d30  dup
0x108d31  ldc.i4.0
0x108d32  ldarg.2
0x108d33  stelem.ref
0x108d34  call     string System.Web.SR::GetString(string name, object[] args)
0x108d39  stloc.2
0x108d3a  ldarg.0
0x108d3b  ldarg.1
0x108d3c  ldarg.2
0x108d3d  ldarg.3
0x108d3e  ldarg.s  4
0x108d40  ldloc.2
0x108d41  callvirt instance class System.Web.UI.WebControls.WebParts.ErrorWebPart System.Web.UI.WebControls.WebParts.WebPartManager::CreateErrorWebPart(string originalID, string originalTypeName, string originalPath, string genericWebPartID, string errorMessage)
0x108d46  stloc.0
0x108d47  br       loc_108F6E
0x108d4c  ldloc.1
0x108d4d  ldtoken  System.Web.UI.WebControls.WebParts.WebPart
0x108d52  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x108d57  callvirt instance bool [mscorlib]System.Type::IsSubclassOf(class [mscorlib]System.Type)
0x108d5c  brfalse  loc_108DF6
0x108d61  ldarg.0
0x108d62  call     instance class System.Web.UI.WebControls.WebParts.WebPartPersonalization System.Web.UI.WebControls.WebParts.WebPartManager::get_Personalization()
0x108d67  ldarg.1
0x108d68  callvirt instance string System.Web.UI.WebControls.WebParts.WebPartPersonalization::GetAuthorizationFilter(string webPartID)
0x108d6d  stloc.3
0x108d6e  ldarg.0
0x108d6f  ldloc.1
0x108d70  ldnull
0x108d71  ldloc.3
0x108d72  ldarg.s  5
0x108d74  callvirt instance bool System.Web.UI.WebControls.WebParts.WebPartManager::IsAuthorized(class [mscorlib]System.Type type, string path, string authorizationFilter, bool isShared)
0x108d79  brfalse.s loc_108DE6
0x108d7b  ldarg.0
0x108d7c  call     instance class System.Web.UI.WebControls.WebParts.WebPartManagerInternals System.Web.UI.WebControls.WebParts.WebPartManager::get_Internals()
0x108d81  ldloc.1
0x108d82  callvirt instance object System.Web.UI.WebControls.WebParts.WebPartManagerInternals::CreateObjectFromType(class [mscorlib]System.Type type)
0x108d87  castclass System.Web.UI.WebControls.WebParts.WebPart
0x108d8c  stloc.0
0x108d8d  ldloc.0
0x108d8e  ldarg.1
0x108d8f  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x108d94  leave    loc_108F6E
0x108d99  pop
0x108d9a  ldarg.0
0x108d9b  callvirt instance class System.Web.HttpContext System.Web.UI.Control::get_Context()
0x108da0  brfalse.s loc_108DBD
0x108da2  ldarg.0
0x108da3  callvirt instance class System.Web.HttpContext System.Web.UI.Control::get_Context()
0x108da8  callvirt instance bool System.Web.HttpContext::get_IsCustomErrorEnabled()
0x108dad  brfalse.s loc_108DBD
0x108daf  ldstr    aWebpartmanager_42// "WebPartManager_CantCreateInstance"
0x108db4  call     string System.Web.SR::GetString(string name)
0x108db9  stloc.s  4
0x108dbb  br.s     loc_108DD3
0x108dbd  ldstr    aWebpartmanager_43// "WebPartManager_CantCreateInstanceWithTy"...
0x108dc2  ldc.i4.1
0x108dc3  newarr   [mscorlib]System.Object
0x108dc8  dup
0x108dc9  ldc.i4.0
0x108dca  ldarg.2
0x108dcb  stelem.ref
0x108dcc  call     string System.Web.SR::GetString(string name, object[] args)
0x108dd1  stloc.s  4
0x108dd3  ldarg.0
0x108dd4  ldarg.1
0x108dd5  ldarg.2
0x108dd6  ldarg.3
0x108dd7  ldarg.s  4
0x108dd9  ldloc.s  4
0x108ddb  callvirt instance class System.Web.UI.WebControls.WebParts.ErrorWebPart System.Web.UI.WebControls.WebParts.WebPartManager::CreateErrorWebPart(string originalID, string originalTypeName, string originalPath, string genericWebPartID, string errorMessage)
0x108de0  stloc.0
0x108de1  leave    loc_108F6E
0x108de6  ldarg.1
0x108de7  ldarg.2
0x108de8  ldarg.3
0x108de9  ldarg.s  4
0x108deb  newobj   instance void System.Web.UI.WebControls.WebParts.UnauthorizedWebPart::.ctor(string originalID, string originalTypeName, string originalPath, string genericWebPartID)
0x108df0  stloc.0
0x108df1  br       loc_108F6E
0x108df6  ldloc.1
0x108df7  ldtoken  System.Web.UI.Control
0x108dfc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x108e01  callvirt instance bool [mscorlib]System.Type::IsSubclassOf(class [mscorlib]System.Type)
0x108e06  brfalse  loc_108F27
0x108e0b  ldarg.0
0x108e0c  call     instance class System.Web.UI.WebControls.WebParts.WebPartPersonalization System.Web.UI.WebControls.WebParts.WebPartManager::get_Personalization()
0x108e11  ldarg.s  4
0x108e13  callvirt instance string System.Web.UI.WebControls.WebParts.WebPartPersonalization::GetAuthorizationFilter(string webPartID)
0x108e18  stloc.s  5
0x108e1a  ldarg.0
0x108e1b  ldloc.1
0x108e1c  ldarg.3
0x108e1d  ldloc.s  5
0x108e1f  ldarg.s  5
0x108e21  callvirt instance bool System.Web.UI.WebControls.WebParts.WebPartManager::IsAuthorized(class [mscorlib]System.Type type, string path, string authorizationFilter, bool isShared)
0x108e26  brfalse  loc_108F1A
0x108e2b  ldnull
0x108e2c  stloc.s  6
0x108e2e  ldarg.3
0x108e2f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x108e34  brtrue.s loc_108E46
0x108e36  ldarg.0
0x108e37  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0x108e3c  ldarg.3
0x108e3d  callvirt instance class System.Web.UI.Control System.Web.UI.TemplateControl::LoadControl(string virtualPath)
0x108e42  stloc.s  6
0x108e44  br.s     loc_108E59
0x108e46  ldarg.0
0x108e47  call     instance class System.Web.UI.WebControls.WebParts.WebPartManagerInternals System.Web.UI.WebControls.WebParts.WebPartManager::get_Internals()
0x108e4c  ldloc.1
0x108e4d  callvirt instance object System.Web.UI.WebControls.WebParts.WebPartManagerInternals::CreateObjectFromType(class [mscorlib]System.Type type)
0x108e52  castclass System.Web.UI.Control
0x108e57  stloc.s  6
0x108e59  ldloc.s  6
0x108e5b  ldarg.1
0x108e5c  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x108e61  ldarg.0
0x108e62  ldloc.s  6
0x108e64  callvirt instance class System.Web.UI.WebControls.WebParts.GenericWebPart System.Web.UI.WebControls.WebParts.WebPartManager::CreateWebPart(class System.Web.UI.Control control)
0x108e69  stloc.0
0x108e6a  ldloc.0
0x108e6b  ldarg.s  4
0x108e6d  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x108e72  leave    loc_108F6E
0x108e77  pop
0x108e78  ldloc.s  6
0x108e7a  brtrue.s loc_108EBF
0x108e7c  ldarg.3
0x108e7d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x108e82  brfalse.s loc_108EBF
0x108e84  ldarg.0
0x108e85  callvirt instance class System.Web.HttpContext System.Web.UI.Control::get_Context()
0x108e8a  brfalse.s loc_108EA7
0x108e8c  ldarg.0
0x108e8d  callvirt instance class System.Web.HttpContext System.Web.UI.Control::get_Context()
0x108e92  callvirt instance bool System.Web.HttpContext::get_IsCustomErrorEnabled()
0x108e97  brfalse.s loc_108EA7
0x108e99  ldstr    aWebpartmanager_42// "WebPartManager_CantCreateInstance"
0x108e9e  call     string System.Web.SR::GetString(string name)
0x108ea3  stloc.s  7
0x108ea5  br.s     loc_108F0A
0x108ea7  ldstr    aWebpartmanager_43// "WebPartManager_CantCreateInstanceWithTy"...
0x108eac  ldc.i4.1
0x108ead  newarr   [mscorlib]System.Object
0x108eb2  dup
0x108eb3  ldc.i4.0
0x108eb4  ldarg.2
0x108eb5  stelem.ref
0x108eb6  call     string System.Web.SR::GetString(string name, object[] args)
0x108ebb  stloc.s  7
0x108ebd  br.s     loc_108F0A
0x108ebf  ldloc.s  6
0x108ec1  brtrue.s loc_108EFE
0x108ec3  ldarg.0
0x108ec4  callvirt instance class System.Web.HttpContext System.Web.UI.Control::get_Context()
0x108ec9  brfalse.s loc_108EE6
0x108ecb  ldarg.0
0x108ecc  callvirt instance class System.Web.HttpContext System.Web.UI.Control::get_Context()
0x108ed1  callvirt instance bool System.Web.HttpContext::get_IsCustomErrorEnabled()
0x108ed6  brfalse.s loc_108EE6
0x108ed8  ldstr    aWebpartmanager_44// "WebPartManager_InvalidPath"
0x108edd  call     string System.Web.SR::GetString(string name)
0x108ee2  stloc.s  7
0x108ee4  br.s     loc_108F0A
0x108ee6  ldstr    aWebpartmanager_45// "WebPartManager_InvalidPathWithPath"
0x108eeb  ldc.i4.1
0x108eec  newarr   [mscorlib]System.Object
0x108ef1  dup
0x108ef2  ldc.i4.0
0x108ef3  ldarg.3
0x108ef4  stelem.ref
0x108ef5  call     string System.Web.SR::GetString(string name, object[] args)
0x108efa  stloc.s  7
0x108efc  br.s     loc_108F0A
0x108efe  ldstr    aWebpartmanager_46// "WebPartManager_CantCreateGeneric"
0x108f03  call     string System.Web.SR::GetString(string name)
0x108f08  stloc.s  7
0x108f0a  ldarg.0
0x108f0b  ldarg.1
0x108f0c  ldarg.2
0x108f0d  ldarg.3
0x108f0e  ldarg.s  4
0x108f10  ldloc.s  7
0x108f12  callvirt instance class System.Web.UI.WebControls.WebParts.ErrorWebPart System.Web.UI.WebControls.WebParts.WebPartManager::CreateErrorWebPart(string originalID, string originalTypeName, string originalPath, string genericWebPartID, string errorMessage)
0x108f17  stloc.0
0x108f18  leave.s  loc_108F6E
0x108f1a  ldarg.1
0x108f1b  ldarg.2
0x108f1c  ldarg.3
0x108f1d  ldarg.s  4
0x108f1f  newobj   instance void System.Web.UI.WebControls.WebParts.UnauthorizedWebPart::.ctor(string originalID, string originalTypeName, string originalPath, string genericWebPartID)
0x108f24  stloc.0
0x108f25  br.s     loc_108F6E
0x108f27  ldarg.0
0x108f28  callvirt instance class System.Web.HttpContext System.Web.UI.Control::get_Context()
0x108f2d  brfalse.s loc_108F4A
0x108f2f  ldarg.0
0x108f30  callvirt instance class System.Web.HttpContext System.Web.UI.Control::get_Context()
0x108f35  callvirt instance bool System.Web.HttpContext::get_IsCustomErrorEnabled()
0x108f3a  brfalse.s loc_108F4A
0x108f3c  ldstr    aWebpartmanager_0// "WebPartManager_TypeMustDeriveFromContro"...
0x108f41  call     string System.Web.SR::GetString(string name)
0x108f46  stloc.s  8
0x108f48  br.s     loc_108F60
0x108f4a  ldstr    aWebpartmanager_47// "WebPartManager_TypeMustDeriveFromContro"...
0x108f4f  ldc.i4.1
0x108f50  newarr   [mscorlib]System.Object
0x108f55  dup
0x108f56  ldc.i4.0
0x108f57  ldarg.2
0x108f58  stelem.ref
0x108f59  call     string System.Web.SR::GetString(string name, object[] args)
0x108f5e  stloc.s  8
0x108f60  ldarg.0
0x108f61  ldarg.1
0x108f62  ldarg.2
0x108f63  ldarg.3
0x108f64  ldarg.s  4
0x108f66  ldloc.s  8
0x108f68  callvirt instance class System.Web.UI.WebControls.WebParts.ErrorWebPart System.Web.UI.WebControls.WebParts.WebPartManager::CreateErrorWebPart(string originalID, string originalTypeName, string originalPath, string genericWebPartID, string errorMessage)
0x108f6d  stloc.0
0x108f6e  ldarg.0
0x108f6f  call     instance class System.Web.UI.WebControls.WebParts.WebPartManagerInternals System.Web.UI.WebControls.WebParts.WebPartManager::get_Internals()
0x108f74  ldloc.0
0x108f75  ldc.i4.0
0x108f76  callvirt instance void System.Web.UI.WebControls.WebParts.WebPartManagerInternals::SetIsStatic(class System.Web.UI.WebControls.WebParts.WebPart webPart, bool isStatic)
0x108f7b  ldarg.0
0x108f7c  call     instance class System.Web.UI.WebControls.WebParts.WebPartManagerInternals System.Web.UI.WebControls.WebParts.WebPartManager::get_Internals()
0x108f81  ldloc.0
0x108f82  ldarg.s  5
0x108f84  callvirt instance void System.Web.UI.WebControls.WebParts.WebPartManagerInternals::SetIsShared(class System.Web.UI.WebControls.WebParts.WebPart webPart, bool isShared)
0x108f89  ldarg.0
0x108f8a  call     instance class System.Web.UI.WebControls.WebParts.WebPartManagerInternals System.Web.UI.WebControls.WebParts.WebPartManager::get_Internals()
0x108f8f  ldloc.0
0x108f90  callvirt instance void System.Web.UI.WebControls.WebParts.WebPartManagerInternals::AddWebPart(class System.Web.UI.WebControls.WebParts.WebPart webPart)
0x108f95  ret
```
