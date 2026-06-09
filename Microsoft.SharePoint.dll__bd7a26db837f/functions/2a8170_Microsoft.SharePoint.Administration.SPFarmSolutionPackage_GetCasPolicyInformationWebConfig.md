# Microsoft.SharePoint.Administration.SPFarmSolutionPackage::GetCasPolicyInformationWebConfig

- ea: `0x2a8170`
- end: `0x2a842d`
- name: `Microsoft.SharePoint.Administration.SPFarmSolutionPackage::GetCasPolicyInformationWebConfig`
- size: `701`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2a7920`
- `0x2a7ad0`

## callees

- `0x197ad0`
- `0x1b7de0`
- `0x2a4890`
- `0x2a8170`
- `0x2a8430`
- `0x2a9060`
- `0x2a90e0`
- `0x577060`
- `0x93dae0`
- `0x957530`

## string_xrefs

- `0x2a81a6`: `Solution Deployment : Web.config MISSING at {0} `
- `0x2a81c2`: `//configuration/system.web/trust`
- `0x2a81f1`: `//configuration/system.web/trust`
- `0x2a8262`: `//configuration/system.web/trust`
- `0x2a82a0`: `//configuration/system.web/trust`
- `0x2a83af`: `//configuration/system.web/trust`
- `0x2a81dc`: `CAS Deployment : No trust node in Web.config at {0}. Xpath : {1} `
- `0x2a824d`: `CAS Deployment : Missing level attr in trust node in Web.config at {0}. Xpath : {1} `
- `0x2a828b`: `CAS Deployment : Full trust in trust node in Web.config at {0}. Xpath : {1} `
- `0x2a82ce`: `//configuration/system.web/securityPolicy/trustLevel[@name="`
- `0x2a8313`: `CAS Deployment : No policy file attribute for policy {0} in web.config at {1}. Xpath : {2} `
- `0x2a834e`: `CAS Deployment : MISSING Policy File {0} for policy {1} in web.config at {2}.`
- `0x2a839a`: `CAS Deployment : Current trust policy is wss_custom in trust node in Web.config at {0}. Xpath : {1} `
- `0x2a8405`: `CAS Deployment : No policy file for policy {0} in web.config at {1}. Xpath : {2} `

## pseudocode

```c

```

## disassembly

```asm
0x2a8170  ldarg.3
0x2a8171  ldsfld   string [mscorlib]System.String::Empty
0x2a8176  stind.ref
0x2a8177  ldarg.s  4
0x2a8179  ldsfld   string [mscorlib]System.String::Empty
0x2a817e  stind.ref
0x2a817f  ldarg.s  5
0x2a8181  ldsfld   string [mscorlib]System.String::Empty
0x2a8186  stind.ref
0x2a8187  ldarg.s  6
0x2a8189  ldsfld   string [mscorlib]System.String::Empty
0x2a818e  stind.ref
0x2a818f  ldarg.0
0x2a8190  ldarg.1
0x2a8191  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Administration.SPFarmSolutionPackage::LoadWebConfig(string vrPath)
0x2a8196  stloc.0
0x2a8197  ldloc.0
0x2a8198  brtrue.s loc_2A81C1
0x2a819a  ldc.i4   0x356D666A
0x2a819f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a81a4  ldc.i4.s 0x14
0x2a81a6  ldstr    aSolutionDeploy_18// "Solution Deployment : Web.config MISSIN"...
0x2a81ab  ldc.i4.1
0x2a81ac  newarr   [mscorlib]System.Object
0x2a81b1  stloc.s  6
0x2a81b3  ldloc.s  6
0x2a81b5  ldc.i4.0
0x2a81b6  ldarg.1
0x2a81b7  stelem.ref
0x2a81b8  ldloc.s  6
0x2a81ba  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2a81bf  ldc.i4.0
0x2a81c0  ret
0x2a81c1  ldloc.0
0x2a81c2  ldstr    aConfigurationS_11// "//configuration/system.web/trust"
0x2a81c7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2a81cc  stloc.1
0x2a81cd  ldloc.1
0x2a81ce  brtrue.s loc_2A822D
0x2a81d0  ldc.i4   0x356D666B
0x2a81d5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a81da  ldc.i4.s 0x32
0x2a81dc  ldstr    aCasDeploymentN_1// "CAS Deployment : No trust node in Web.c"...
0x2a81e1  ldc.i4.2
0x2a81e2  newarr   [mscorlib]System.Object
0x2a81e7  stloc.s  7
0x2a81e9  ldloc.s  7
0x2a81eb  ldc.i4.0
0x2a81ec  ldarg.1
0x2a81ed  stelem.ref
0x2a81ee  ldloc.s  7
0x2a81f0  ldc.i4.1
0x2a81f1  ldstr    aConfigurationS_11// "//configuration/system.web/trust"
0x2a81f6  stelem.ref
0x2a81f7  ldloc.s  7
0x2a81f9  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2a81fe  ldstr    aCasdeploynotru// "CasDeployNoTrustNode"
0x2a8203  ldc.i4.2
0x2a8204  newarr   [mscorlib]System.Object
0x2a8209  stloc.s  8
0x2a820b  ldloc.s  8
0x2a820d  ldc.i4.0
0x2a820e  ldarg.0
0x2a820f  call     instance string Microsoft.SharePoint.Administration.SPSolutionPackage::get_Name()
0x2a8214  stelem.ref
0x2a8215  ldloc.s  8
0x2a8217  ldc.i4.1
0x2a8218  ldarg.0
0x2a8219  ldarg.1
0x2a821a  call     instance string Microsoft.SharePoint.Administration.SPFarmSolutionPackage::GetWebConfigPath(string vrPath)
0x2a821f  stelem.ref
0x2a8220  ldloc.s  8
0x2a8222  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x2a8227  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x2a822c  throw
0x2a822d  ldloc.1
0x2a822e  ldstr    aLevel// "level"
0x2a8233  call     string Microsoft.SharePoint.Utilities.SPUtility::XmlGetAttrVal(class [System.Xml]System.Xml.XmlNode xn, string attr)
0x2a8238  stloc.2
0x2a8239  ldloc.2
0x2a823a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a823f  brfalse.s loc_2A8271
0x2a8241  ldc.i4   0x356D666C
0x2a8246  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a824b  ldc.i4.s 0x14
0x2a824d  ldstr    aCasDeploymentM// "CAS Deployment : Missing level attr in "...
0x2a8252  ldc.i4.2
0x2a8253  newarr   [mscorlib]System.Object
0x2a8258  stloc.s  9
0x2a825a  ldloc.s  9
0x2a825c  ldc.i4.0
0x2a825d  ldarg.1
0x2a825e  stelem.ref
0x2a825f  ldloc.s  9
0x2a8261  ldc.i4.1
0x2a8262  ldstr    aConfigurationS_11// "//configuration/system.web/trust"
0x2a8267  stelem.ref
0x2a8268  ldloc.s  9
0x2a826a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2a826f  ldc.i4.0
0x2a8270  ret
0x2a8271  ldloc.2
0x2a8272  ldstr    aFull// "full"
0x2a8277  ldc.i4.3
0x2a8278  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2a827d  brtrue.s loc_2A82AF
0x2a827f  ldc.i4   0x356D666D
0x2a8284  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a8289  ldc.i4.s 0x32
0x2a828b  ldstr    aCasDeploymentF// "CAS Deployment : Full trust in trust no"...
0x2a8290  ldc.i4.2
0x2a8291  newarr   [mscorlib]System.Object
0x2a8296  stloc.s  0xA
0x2a8298  ldloc.s  0xA
0x2a829a  ldc.i4.0
0x2a829b  ldarg.1
0x2a829c  stelem.ref
0x2a829d  ldloc.s  0xA
0x2a829f  ldc.i4.1
0x2a82a0  ldstr    aConfigurationS_11// "//configuration/system.web/trust"
0x2a82a5  stelem.ref
0x2a82a6  ldloc.s  0xA
0x2a82a8  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2a82ad  ldc.i4.1
0x2a82ae  ret
0x2a82af  ldarg.3
0x2a82b0  ldloc.2
0x2a82b1  stind.ref
0x2a82b2  ldloc.2
0x2a82b3  ldstr    aWssCustom// "WSS_Custom"
0x2a82b8  ldc.i4.5
0x2a82b9  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2a82be  brtrue.s loc_2A82C6
0x2a82c0  ldarg.s  4
0x2a82c2  ldloc.2
0x2a82c3  stind.ref
0x2a82c4  br.s     loc_2A82CE
0x2a82c6  ldarg.s  4
0x2a82c8  ldstr    aWssCustom// "WSS_Custom"
0x2a82cd  stind.ref
0x2a82ce  ldstr    aConfigurationS_12// "//configuration/system.web/securityPoli"...
0x2a82d3  ldarg.3
0x2a82d4  ldind.ref
0x2a82d5  ldstr    asc_D696FE// "\"]"
0x2a82da  call     string [mscorlib]System.String::Concat(string, string, string)
0x2a82df  stloc.3
0x2a82e0  ldloc.0
0x2a82e1  ldloc.3
0x2a82e2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2a82e7  stloc.s  4
0x2a82e9  ldloc.s  4
0x2a82eb  brfalse  loc_2A83F9
0x2a82f0  ldloc.s  4
0x2a82f2  ldstr    aPolicyfile// "policyFile"
0x2a82f7  call     string Microsoft.SharePoint.Utilities.SPUtility::XmlGetAttrVal(class [System.Xml]System.Xml.XmlNode xn, string attr)
0x2a82fc  stloc.s  5
0x2a82fe  ldloc.s  5
0x2a8300  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a8305  brfalse.s loc_2A8339
0x2a8307  ldc.i4   0x356D666E
0x2a830c  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a8311  ldc.i4.s 0x14
0x2a8313  ldstr    aCasDeploymentN_2// "CAS Deployment : No policy file attribu"...
0x2a8318  ldc.i4.3
0x2a8319  newarr   [mscorlib]System.Object
0x2a831e  stloc.s  0xB
0x2a8320  ldloc.s  0xB
0x2a8322  ldc.i4.0
0x2a8323  ldarg.3
0x2a8324  ldind.ref
0x2a8325  stelem.ref
0x2a8326  ldloc.s  0xB
0x2a8328  ldc.i4.1
0x2a8329  ldarg.1
0x2a832a  stelem.ref
0x2a832b  ldloc.s  0xB
0x2a832d  ldc.i4.2
0x2a832e  ldloc.3
0x2a832f  stelem.ref
0x2a8330  ldloc.s  0xB
0x2a8332  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2a8337  ldc.i4.0
0x2a8338  ret
0x2a8339  ldloc.s  5
0x2a833b  call     bool [mscorlib]System.IO.File::Exists(string)
0x2a8340  brtrue.s loc_2A8375
0x2a8342  ldc.i4   0x356D666F
0x2a8347  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a834c  ldc.i4.s 0x14
0x2a834e  ldstr    aCasDeploymentM_0// "CAS Deployment : MISSING Policy File {0"...
0x2a8353  ldc.i4.3
0x2a8354  newarr   [mscorlib]System.Object
0x2a8359  stloc.s  0xC
0x2a835b  ldloc.s  0xC
0x2a835d  ldc.i4.0
0x2a835e  ldloc.s  5
0x2a8360  stelem.ref
0x2a8361  ldloc.s  0xC
0x2a8363  ldc.i4.1
0x2a8364  ldarg.3
0x2a8365  ldind.ref
0x2a8366  stelem.ref
0x2a8367  ldloc.s  0xC
0x2a8369  ldc.i4.2
0x2a836a  ldarg.1
0x2a836b  stelem.ref
0x2a836c  ldloc.s  0xC
0x2a836e  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2a8373  ldc.i4.0
0x2a8374  ret
0x2a8375  ldarg.s  5
0x2a8377  ldloc.s  5
0x2a8379  stind.ref
0x2a837a  ldarg.2
0x2a837b  brfalse  loc_2A842B
0x2a8380  ldloc.2
0x2a8381  ldstr    aWssCustom// "WSS_Custom"
0x2a8386  ldc.i4.3
0x2a8387  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2a838c  brtrue.s loc_2A83C4
0x2a838e  ldc.i4   0x356D6670
0x2a8393  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a8398  ldc.i4.s 0x64
0x2a839a  ldstr    aCasDeploymentC_1// "CAS Deployment : Current trust policy i"...
0x2a839f  ldc.i4.2
0x2a83a0  newarr   [mscorlib]System.Object
0x2a83a5  stloc.s  0xD
0x2a83a7  ldloc.s  0xD
0x2a83a9  ldc.i4.0
0x2a83aa  ldarg.1
0x2a83ab  stelem.ref
0x2a83ac  ldloc.s  0xD
0x2a83ae  ldc.i4.1
0x2a83af  ldstr    aConfigurationS_11// "//configuration/system.web/trust"
0x2a83b4  stelem.ref
0x2a83b5  ldloc.s  0xD
0x2a83b7  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2a83bc  ldarg.s  6
0x2a83be  ldarg.s  5
0x2a83c0  ldind.ref
0x2a83c1  stind.ref
0x2a83c2  br.s     loc_2A83D0
0x2a83c4  ldarg.s  6
0x2a83c6  ldarg.0
0x2a83c7  ldarg.s  5
0x2a83c9  ldind.ref
0x2a83ca  call     instance string Microsoft.SharePoint.Administration.SPFarmSolutionPackage::CreateCustomPolicyFileName(string file)
0x2a83cf  stind.ref
0x2a83d0  ldc.i4   0x356D6671
0x2a83d5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a83da  ldc.i4.s 0x32
0x2a83dc  ldstr    aCasDeploymentN_3// "CAS Deployment : New policy file is  {0"...
0x2a83e1  ldc.i4.1
0x2a83e2  newarr   [mscorlib]System.Object
0x2a83e7  stloc.s  0xE
0x2a83e9  ldloc.s  0xE
0x2a83eb  ldc.i4.0
0x2a83ec  ldarg.s  6
0x2a83ee  ldind.ref
0x2a83ef  stelem.ref
0x2a83f0  ldloc.s  0xE
0x2a83f2  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2a83f7  br.s     loc_2A842B
0x2a83f9  ldc.i4   0x356D6672
0x2a83fe  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a8403  ldc.i4.s 0x14
0x2a8405  ldstr    aCasDeploymentN_4// "CAS Deployment : No policy file for pol"...
0x2a840a  ldc.i4.3
0x2a840b  newarr   [mscorlib]System.Object
0x2a8410  stloc.s  0xF
0x2a8412  ldloc.s  0xF
0x2a8414  ldc.i4.0
0x2a8415  ldarg.3
0x2a8416  ldind.ref
0x2a8417  stelem.ref
0x2a8418  ldloc.s  0xF
0x2a841a  ldc.i4.1
0x2a841b  ldarg.1
0x2a841c  stelem.ref
0x2a841d  ldloc.s  0xF
0x2a841f  ldc.i4.2
0x2a8420  ldloc.3
0x2a8421  stelem.ref
0x2a8422  ldloc.s  0xF
0x2a8424  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2a8429  ldc.i4.0
0x2a842a  ret
0x2a842b  ldc.i4.1
0x2a842c  ret
```
