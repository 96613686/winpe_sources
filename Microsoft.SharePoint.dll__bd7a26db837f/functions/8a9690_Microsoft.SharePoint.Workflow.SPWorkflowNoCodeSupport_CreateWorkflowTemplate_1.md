# Microsoft.SharePoint.Workflow.SPWorkflowNoCodeSupport::CreateWorkflowTemplate_1

- ea: `0x8a9690`
- end: `0x8aa0f5`
- name: `Microsoft.SharePoint.Workflow.SPWorkflowNoCodeSupport::CreateWorkflowTemplate_1`
- size: `2661`
- prototype: ``
- caller_count: `4`
- callee_count: `25`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x8a4380`
- `0x8a9200`
- `0x8a9600`
- `0x9deab0`

## callees

- `0x1a1f60`
- `0x49b040`
- `0x4cc7c0`
- `0x577060`
- `0x8871d0`
- `0x8876f0`
- `0x8a4710`
- `0x8a9390`
- `0x8a9690`
- `0x8aa100`
- `0x8abcc0`
- `0x8ac400`
- `0x8ac710`
- `0x8ac730`
- `0x8ac740`
- `0x8ac750`
- `0x8ac770`
- `0x8ac7d0`
- `0x8ac7f0`
- `0x8ac810`
- `0x8ac830`
- `0x8ac910`
- `0x8ac950`
- `0x8ac970`
- `0x8ad080`

## string_xrefs

- `0x8a99e2`: `TaskType`
- `0x8a9830`: `LastUpdated`
- `0x8a9bd7`: `CompileVersion`
- `0x8a97fa`: `DeclarativeConfiguration`
- `0x8a9704`: `/WorkflowConfig/Template[@Type="RulesOnly"]`
- `0x8a9db7`: `/WorkflowConfig/ContentTypes/ContentType`
- `0x8a96a5`: `Microsoft.SharePoint.Workflow.SPWinOeHostServices`
- `0x8a96e3`: `/WorkflowConfig/Template/@BaseID`
- `0x8a973b`: `/WorkflowConfig/Template/@Ruleset`
- `0x8a9755`: `/WorkflowConfig/Template/@Visibility`
- `0x8a97cc`: `/WorkflowConfig/MetaData`
- `0x8a97e2`: `/WorkflowConfig/MetaData`
- `0x8a9842`: `/WorkflowConfig/Initiation/Fields`
- `0x8a986a`: `/WorkflowConfig/Initiation/Parameters`
- `0x8a9892`: `/WorkflowConfig/Initiation/@URL`
- `0x8a98ac`: `/WorkflowConfig/Template/@AssociationURL`
- `0x8a98c6`: `/WorkflowConfig/MetaData/Instantiation_FormURI`
- `0x8a98d7`: `/WorkflowConfig/MetaData/Instantiation_FormURN`
- `0x8a98f2`: `Instantiation_FormURI`
- `0x8a98ff`: `/WorkflowConfig/MetaData/Association_FormURN`
- `0x8a9927`: `/WorkflowConfig/MetaData/HasStatusColumn`
- `0x8a996c`: `/WorkflowConfig/Template/@TaskContentType`
- `0x8a998b`: `/WorkflowConfig/MetaData/TaskForms/TaskForm`
- `0x8a99a1`: `Task{0}_FormURN`
- `0x8a9a1d`: `/WorkflowConfig/MetaData/Modifications/Modification`
- `0x8a9b03`: `/WorkflowConfig/MetaData/Modifications/@ModificationUrl`
- `0x8a9b26`: `<my:myFields xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:my="http://schemas.microsoft.com/office/infopath/2003/myXSD" xmlns:pc="http://schemas.microsoft.com/office/infopath/2007/PartnerControls">{0}</my:myFields>`
- `0x8a9b6a`: `/WorkflowConfig/Template/@Category`
- `0x8a9bc5`: `/WorkflowConfig/@Version`
- `0x8a9be9`: `/WorkflowConfig/Extended/Fields/Field`
- `0x8a9c99`: `/WorkflowConfig/Initiation/Fields/Field[@Type='HybridUser']/@Name`
- `0x8a9cbd`: `/WorkflowConfig/Template/@ShowPreview`
- `0x8a9ce1`: `/WorkflowConfig/Template/@PreviewHref`
- `0x8a9d2e`: `/WorkflowConfig/Template/@Description`
- `0x8a9d4d`: `/WorkflowConfig/Initiation/DefaultData`
- `0x8a9e47`: `/WorkflowConfig/ContentTypes`
- `0x8a9e6f`: `/WorkflowConfig/Template/@StartManually`
- `0x8a9e80`: `/WorkflowConfig/Association/@StartManually`
- `0x8a9ecb`: `/WorkflowConfig/Template/@RequireManagePermission`
- `0x8a9ef4`: `/WorkflowConfig/Association/@ListID`
- `0x8a9f2a`: `/WorkflowConfig/Template/@StartOnCreate`
- `0x8a9f3b`: `/WorkflowConfig/Association/@StartOnCreate`
- `0x8a9f92`: `/WorkflowConfig/Template/@StartOnChange`
- `0x8a9fa3`: `/WorkflowConfig/Association/@StartOnChange`
- `0x8a9ff1`: `/WorkflowConfig/Template/@AllowStartOnMajorCheckin`
- `0x8aa03f`: `/WorkflowConfig/MetaData/HasTaskList`
- `0x8aa093`: `/WorkflowConfig/MetaData/HasHistoryList`

## pseudocode

```c

```

## disassembly

```asm
0x8a9690  ldnull
0x8a9691  stloc.0
0x8a9692  ldstr    aMicrosoftShare_225// "Microsoft.SharePoint.Workflow.SPWinOeWo"...
0x8a9697  stloc.2
0x8a9698  call     string Microsoft.SharePoint.SPAssemblyLoader::get_SharePointAssemblyName()
0x8a969d  stloc.3
0x8a969e  ldstr    aMicrosoftShare_222// "Microsoft.SharePoint.Workflow.ROOT"
0x8a96a3  stloc.s  4
0x8a96a5  ldstr    aMicrosoftShare_226// "Microsoft.SharePoint.Workflow.SPWinOeHo"...
0x8a96aa  stloc.s  5
0x8a96ac  call     string Microsoft.SharePoint.SPAssemblyLoader::get_SharePointAssemblyName()
0x8a96b1  stloc.s  6
0x8a96b3  ldstr    aMicrosoftShare_227// "Microsoft.SharePoint.Workflow.SPWinOeEn"...
0x8a96b8  stloc.s  7
0x8a96ba  call     string Microsoft.SharePoint.SPAssemblyLoader::get_SharePointAssemblyName()
0x8a96bf  stloc.s  8
0x8a96c1  ldnull
0x8a96c2  stloc.s  9
0x8a96c4  ldnull
0x8a96c5  stloc.s  0xA
0x8a96c7  ldnull
0x8a96c8  stloc.s  0xB
0x8a96ca  ldarg.0
0x8a96cb  call     string Microsoft.SharePoint.Utilities.SPUtility::GetLayoutsFolder(class Microsoft.SharePoint.SPWeb web)
0x8a96d0  ldstr    aWrkstatAspx// "/WrkStat.aspx"
0x8a96d5  call     string [mscorlib]System.String::Concat(string, string)
0x8a96da  stloc.s  0xC
0x8a96dc  ldc.i4.1
0x8a96dd  stloc.s  0xD
0x8a96df  ldnull
0x8a96e0  stloc.s  0xE
0x8a96e2  ldarg.2
0x8a96e3  ldstr    aWorkflowconfig_13// "/WorkflowConfig/Template/@BaseID"
0x8a96e8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8a96ed  stloc.s  0xF
0x8a96ef  ldloc.s  0xF
0x8a96f1  brtrue.s loc_8A96F5
0x8a96f3  ldnull
0x8a96f4  ret
0x8a96f5  ldloca.s 1
0x8a96f7  ldloc.s  0xF
0x8a96f9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x8a96fe  call     instance void [mscorlib]System.Guid::.ctor(string)
0x8a9703  ldarg.2
0x8a9704  ldstr    aWorkflowconfig_3// "/WorkflowConfig/Template[@Type=\"RulesO"...
0x8a9709  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8a970e  ldnull
0x8a970f  ceq
0x8a9711  ldc.i4.0
0x8a9712  ceq
0x8a9714  stloc.s  0x10
0x8a9716  ldloc.s  0x10
0x8a9718  brfalse.s loc_8A9754
0x8a971a  ldnull
0x8a971b  stloc.2
0x8a971c  ldnull
0x8a971d  stloc.3
0x8a971e  ldnull
0x8a971f  stloc.s  4
0x8a9721  ldnull
0x8a9722  stloc.0
0x8a9723  ldnull
0x8a9724  stloc.s  5
0x8a9726  ldnull
0x8a9727  stloc.s  6
0x8a9729  ldstr    aMicrosoftShare_228// "Microsoft.SharePoint.Workflow.SPWinOeRu"...
0x8a972e  stloc.s  7
0x8a9730  call     string Microsoft.SharePoint.SPAssemblyLoader::get_SharePointAssemblyName()
0x8a9735  stloc.s  8
0x8a9737  ldc.i4.0
0x8a9738  stloc.s  0xD
0x8a973a  ldarg.2
0x8a973b  ldstr    aWorkflowconfig_14// "/WorkflowConfig/Template/@Ruleset"
0x8a9740  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8a9745  stloc.s  0xF
0x8a9747  ldloc.s  0xF
0x8a9749  brfalse.s loc_8A9754
0x8a974b  ldloc.s  0xF
0x8a974d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x8a9752  stloc.s  4
0x8a9754  ldarg.2
0x8a9755  ldstr    aWorkflowconfig_15// "/WorkflowConfig/Template/@Visibility"
0x8a975a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8a975f  stloc.s  0xF
0x8a9761  ldloc.s  0xF
0x8a9763  brfalse.s loc_8A976E
0x8a9765  ldloc.s  0xF
0x8a9767  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x8a976c  stloc.s  0xE
0x8a976e  ldloc.s  0xE
0x8a9770  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8a9775  brtrue.s loc_8A979B
0x8a9777  ldloc.s  0xE
0x8a9779  ldstr    aPublic// "public"
0x8a977e  ldc.i4.5
0x8a977f  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x8a9784  brfalse.s loc_8A9798
0x8a9786  ldloc.s  0xE
0x8a9788  ldstr    aRootpublic_0// "rootpublic"
0x8a978d  ldc.i4.5
0x8a978e  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x8a9793  ldc.i4.0
0x8a9794  ceq
0x8a9796  br.s     loc_8A979C
0x8a9798  ldc.i4.1
0x8a9799  br.s     loc_8A979C
0x8a979b  ldc.i4.0
0x8a979c  stloc.s  0x11
0x8a979e  ldc.i4.m1
0x8a979f  stloc.s  0x12
0x8a97a1  ldarg.0
0x8a97a2  ldarg.2
0x8a97a3  ldloca.s 0x12
0x8a97a5  call     string Microsoft.SharePoint.Workflow.SPWorkflowNoCodeSupport::AssemblyNameFromConfig(class Microsoft.SharePoint.SPWeb web, class [System.Xml]System.Xml.XmlDocument configInfo, [out] valuetype Microsoft.SharePoint.SPListTemplateType& doclibType)
0x8a97aa  stloc.0
0x8a97ab  ldloc.0
0x8a97ac  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8a97b1  brfalse.s loc_8A97B5
0x8a97b3  ldnull
0x8a97b4  ret
0x8a97b5  ldloc.1
0x8a97b6  ldloc.1
0x8a97b7  ldloc.2
0x8a97b8  ldloc.3
0x8a97b9  ldloc.s  4
0x8a97bb  ldloc.0
0x8a97bc  ldloc.s  5
0x8a97be  ldloc.s  6
0x8a97c0  ldloc.s  7
0x8a97c2  ldloc.s  8
0x8a97c4  newobj   instance void Microsoft.SharePoint.Workflow.SPWorkflowTemplateIdSet::.ctor(valuetype [mscorlib]System.Guid templateId, valuetype [mscorlib]System.Guid baseId, string workflowClass, string workflowAssm, string codeBesideClass, string codeBesideAssm, string hostClass, string hostAssm, string engineClass, string engineAssm)
0x8a97c9  stloc.s  0x13
0x8a97cb  ldarg.2
0x8a97cc  ldstr    aWorkflowconfig_16// "/WorkflowConfig/MetaData"
0x8a97d1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8a97d6  brtrue.s loc_8A97E1
0x8a97d8  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x8a97dd  stloc.s  0xB
0x8a97df  br.s     loc_8A97F8
0x8a97e1  ldarg.2
0x8a97e2  ldstr    aWorkflowconfig_16// "/WorkflowConfig/MetaData"
0x8a97e7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8a97ec  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x8a97f1  call     class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.WorkflowUtil.XmlUtil::XmlToHashtable2(string strXml)
0x8a97f6  stloc.s  0xB
0x8a97f8  ldloc.s  0xB
0x8a97fa  ldstr    aDeclarativecon// "DeclarativeConfiguration"
0x8a97ff  ldarg.3
0x8a9800  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x8a9805  ldloc.s  0xB
0x8a9807  ldstr    aScopeid_1// "ScopeID"
0x8a980c  ldarg.0
0x8a980d  ldloc.s  0xE
0x8a980f  ldloc.s  0x12
0x8a9811  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.Workflow.SPWorkflowManager::ScopeIdFromWebAndTemplateType(class Microsoft.SharePoint.SPWeb web, string visibility, valuetype Microsoft.SharePoint.SPListTemplateType doclibType)
0x8a9816  box      [mscorlib]System.Guid
0x8a981b  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x8a9820  ldloc.s  0xB
0x8a9822  ldstr    aVisibility// "Visibility"
0x8a9827  ldloc.s  0xE
0x8a9829  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x8a982e  ldloc.s  0xB
0x8a9830  ldstr    aLastupdated// "LastUpdated"
0x8a9835  ldarg.s  4
0x8a9837  box      [mscorlib]System.DateTime
0x8a983c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x8a9841  ldarg.2
0x8a9842  ldstr    aWorkflowconfig_17// "/WorkflowConfig/Initiation/Fields"
0x8a9847  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8a984c  stloc.s  0xF
0x8a984e  ldloc.s  0xF
0x8a9850  brfalse.s loc_8A9869
0x8a9852  ldloc.s  0xF
0x8a9854  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x8a9859  stloc.s  0x14
0x8a985b  ldloc.s  0xB
0x8a985d  ldstr    aInstantiationF_1// "Instantiation_FieldML"
0x8a9862  ldloc.s  0x14
0x8a9864  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x8a9869  ldarg.2
0x8a986a  ldstr    aWorkflowconfig_18// "/WorkflowConfig/Initiation/Parameters"
0x8a986f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8a9874  stloc.s  0xF
0x8a9876  ldloc.s  0xF
0x8a9878  brfalse.s loc_8A9891
0x8a987a  ldloc.s  0xF
0x8a987c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x8a9881  stloc.s  0x15
0x8a9883  ldloc.s  0xB
0x8a9885  ldstr    aInitiationPara// "Initiation_Parameters"
0x8a988a  ldloc.s  0x15
0x8a988c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x8a9891  ldarg.2
0x8a9892  ldstr    aWorkflowconfig_19// "/WorkflowConfig/Initiation/@URL"
0x8a9897  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8a989c  stloc.s  0xF
0x8a989e  ldloc.s  0xF
0x8a98a0  brfalse.s loc_8A98AB
0x8a98a2  ldloc.s  0xF
0x8a98a4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x8a98a9  stloc.s  9
0x8a98ab  ldarg.2
0x8a98ac  ldstr    aWorkflowconfig_20// "/WorkflowConfig/Template/@AssociationUR"...
0x8a98b1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8a98b6  stloc.s  0xF
0x8a98b8  ldloc.s  0xF
0x8a98ba  brfalse.s loc_8A98C5
0x8a98bc  ldloc.s  0xF
0x8a98be  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x8a98c3  stloc.s  0xA
0x8a98c5  ldarg.2
0x8a98c6  ldstr    aWorkflowconfig_21// "/WorkflowConfig/MetaData/Instantiation_"...
0x8a98cb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8a98d0  stloc.s  0xF
0x8a98d2  ldloc.s  0xF
0x8a98d4  brtrue.s loc_8A98E3
0x8a98d6  ldarg.2
0x8a98d7  ldstr    aWorkflowconfig_22// "/WorkflowConfig/MetaData/Instantiation_"...
0x8a98dc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8a98e1  stloc.s  0xF
0x8a98e3  ldloc.s  0xF
0x8a98e5  brfalse.s loc_8A98FE
0x8a98e7  ldloc.s  0xF
0x8a98e9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8a98ee  stloc.s  0x16
0x8a98f0  ldloc.s  0xB
0x8a98f2  ldstr    aInstantiationF_2// "Instantiation_FormURI"
0x8a98f7  ldloc.s  0x16
0x8a98f9  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x8a98fe  ldarg.2
0x8a98ff  ldstr    aWorkflowconfig_23// "/WorkflowConfig/MetaData/Association_Fo"...
0x8a9904  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8a9909  stloc.s  0xF
0x8a990b  ldloc.s  0xF
0x8a990d  brfalse.s loc_8A9926
0x8a990f  ldloc.s  0xF
0x8a9911  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8a9916  stloc.s  0x17
0x8a9918  ldloc.s  0xB
0x8a991a  ldstr    aAssociationFor_1// "Association_FormURN"
0x8a991f  ldloc.s  0x17
0x8a9921  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x8a9926  ldarg.2
0x8a9927  ldstr    aWorkflowconfig_24// "/WorkflowConfig/MetaData/HasStatusColum"...
0x8a992c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8a9931  stloc.s  0xF
0x8a9933  ldloc.s  0xF
0x8a9935  brfalse.s loc_8A9964
0x8a9937  ldloc.s  0xF
0x8a9939  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8a993e  stloc.s  0x18
0x8a9940  ldloc.s  0x18
0x8a9942  ldstr    aFalse// "false"
0x8a9947  callvirt instance bool [mscorlib]System.String::Equals(string)
0x8a994c  brfalse.s loc_8A9953
0x8a994e  ldc.i4.0
0x8a994f  stloc.s  0xD
0x8a9951  br.s     loc_8A9964
0x8a9953  ldloc.s  0x18
0x8a9955  ldstr    aTrue// "true"
0x8a995a  callvirt instance bool [mscorlib]System.String::Equals(string)
0x8a995f  brfalse.s loc_8A9964
0x8a9961  ldc.i4.1
0x8a9962  stloc.s  0xD
0x8a9964  ldsfld   valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPBuiltInContentTypeId::System
0x8a9969  stloc.s  0x19
0x8a996b  ldarg.2
0x8a996c  ldstr    aWorkflowconfig_25// "/WorkflowConfig/Template/@TaskContentTy"...
0x8a9971  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8a9976  stloc.s  0xF
0x8a9978  ldloc.s  0xF
0x8a997a  brfalse.s loc_8A998A
0x8a997c  ldloca.s 0x19
0x8a997e  ldloc.s  0xF
0x8a9980  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x8a9985  call     instance void Microsoft.SharePoint.SPContentTypeId::.ctor(string id)
0x8a998a  ldarg.2
0x8a998b  ldstr    aWorkflowconfig_26// "/WorkflowConfig/MetaData/TaskForms/Task"...
0x8a9990  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x8a9995  stloc.s  0x1A
0x8a9997  ldloc.s  0x1A
0x8a9999  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x8a999e  ldc.i4.0
0x8a999f  ble.s    loc_8A9A1C
0x8a99a1  ldstr    aTask0Formurn// "Task{0}_FormURN"
0x8a99a6  stloc.s  0x1B
0x8a99a8  ldloc.s  0x1A
0x8a99aa  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x8a99af  stloc.s  0x1C
0x8a99b1  ldloc.s  0x1C
0x8a99b3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8a99b8  stloc.s  0x1D
0x8a99ba  br.s     loc_8A9A18
0x8a99bc  ldloc.s  0x1C
0x8a99be  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8a99c3  isinst   [System.Xml]System.Xml.XmlElement
0x8a99c8  stloc.s  0x1E
0x8a99ca  ldloc.s  0x1E
0x8a99cc  brfalse.s loc_8A9A0F
0x8a99ce  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
  ... truncated ...
```
