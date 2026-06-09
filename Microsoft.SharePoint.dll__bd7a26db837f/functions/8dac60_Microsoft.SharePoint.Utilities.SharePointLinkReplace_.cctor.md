# Microsoft.SharePoint.Utilities.SharePointLinkReplace::.cctor

- ea: `0x8dac60`
- end: `0x8dae74`
- name: `Microsoft.SharePoint.Utilities.SharePointLinkReplace::.cctor`
- size: `532`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x8daee0`
- `0x957470`

## string_xrefs

- `0x8dac9f`: `/xsf:xDocumentClass/xsf:query/xsf:webServiceAdapter/xsf:operation/@serviceUrl`
- `0x8dacad`: `/xsf:xDocumentClass/xsf:query/xsf:webServiceAdapter/@wsdlUrl`
- `0x8dacc9`: `/xsf:xDocumentClass/xsf:submit/xsf:webServiceAdapter/xsf:operation/@serviceUrl`
- `0x8dacd7`: `/xsf:xDocumentClass/xsf:submit/xsf:webServiceAdapter/@wsdlUrl`
- `0x8dacf4`: `/xsf:xDocumentClass/xsf:dataAdapters/xsf:webServiceAdapter/xsf:operation/@serviceUrl`
- `0x8dad03`: `/xsf:xDocumentClass/xsf:dataAdapters/xsf:webServiceAdapter/@wsdlUrl`
- `0x8dad12`: `/xsf:xDocumentClass/xsf:dataObjects/xsf:dataObject/xsf:query/xsf:webServiceAdapter/xsf:operation/@serviceUrl`
- `0x8dad21`: `/xsf:xDocumentClass/xsf:dataObjects/xsf:dataObject/xsf:query/xsf:webServiceAdapter/@wsdlUrl`
- `0x8dad30`: `/xsf:xDocumentClass/xsf:extensions/xsf:extension[@name='SolutionDefinitionExtensions']/xsf2:solutionDefinition/xsf2:dataConnections/xsf2:webServiceAdapterExtension/xsf2:connectoid/@siteCollection`
- `0x8dad3f`: `/xsf:xDocumentClass/xsf:extensions/xsf:extension[@name='SolutionDefinitionExtensions']/xsf2:solutionDefinition/xsf2:dataConnections/xsf2:useHttpHandlerExtension/xsf2:connectoid/@siteCollection`
- `0x8dad4e`: `/xsf:xDocumentClass/xsf:extensions/xsf:extension[@name='SolutionDefinitionExtensions']/xsf2:solutionDefinition/xsf2:dataConnections/xsf2:sharepointListAdapterExtension/xsf2:connectoid/@siteCollection`
- `0x8dad5d`: `/xsf:xDocumentClass/xsf:extensions/xsf:extension[@name='SolutionDefinitionExtensions']/xsf2:solutionDefinition/xsf2:dataConnections/xsf2:davAdapterExtension/xsf2:connectoid/@siteCollection`
- `0x8dad6c`: `/xsf:xDocumentClass/xsf:extensions/xsf:extension[@name='SolutionDefinitionExtensions']/xsf2:solutionDefinition/xsf2:dataConnections/xsf2:xmlFileAdapterExtension/xsf2:connectoid/@siteCollection`
- `0x8dad7b`: `/xsf:xDocumentClass/xsf:extensions/xsf:extension[@name='SolutionDefinitionExtensions']/xsf2:solutionDefinition/xsf2:dataConnections/xsf2:adoAdapterExtension/xsf2:connectoid/@siteCollection`
- `0x8dad99`: `/xsf:xDocumentClass/xsf:dataObjects/xsf:dataObject/xsf:query/xsf:xmlFileAdapter/@fileUrl`
- `0x8dada8`: `/xsf:xDocumentClass/xsf:taskpane/@href`
- `0x8dadb7`: `/xsf:xDocumentClass/xsf:ruleSets/xsf:ruleSet/xsf:rule/xsf:openNewDocumentAction/@solutionURI`
- `0x8dadc6`: `/xsf:xDocumentClass/xsf:extensions/xsf:extension[@name='SolutionDefinitionExtensions']/xsf2:solutionDefinition/xsf2:dataConnections/xsf2:webServiceAdapterExtension/@queryKey`
- `0x8dadd5`: `/xsf:xDocumentClass/xsf:extensions/xsf:extension[@name='SolutionDefinitionExtensions']/xsf2:solutionDefinition/xsf2:dataConnections/xsf2:sharepointListAdapterExtension/@queryKey`
- `0x8dade4`: `/xsf:xDocumentClass/xsf:extensions/xsf:extension[@name='SolutionDefinitionExtensions']/xsf2:solutionDefinition/xsf2:dataConnections/xsf2:xmlFileAdapterExtension/@queryKey`
- `0x8dadf3`: `/xsf:xDocumentClass/xsf:extensions/xsf:extention[@name='SolutionMode']/xsf3:solutionMode/@originalPublishUrl`
- `0x8dae1c`: `/udc:DataSource/udc:ConnectionInfo/udc:SelectCommand/udc:ServiceUrl`
- `0x8dae2a`: `/udc:DataSource/udc:ConnectionInfo/udc:UpdateCommand/udc:ServiceUrl`
- `0x8dae38`: `/udc:DataSource/udc:ConnectionInfo/udc:SelectCommand/udc:Query`
- `0x8dae46`: `/udc:DataSource/udc:ConnectionInfo/udc:UpdateCommand/udc:Submit`
- `0x8dae54`: `/udc:DataSource/udc:ConnectionInfo/udc:UpdateCommand/udc:FolderName`
- `0x8dae62`: `/udc:DataSource/udc:ConnectionInfo/udc:SelectCommand/udc:WebUrl`

## pseudocode

```c

```

## disassembly

```asm
0x8dac60  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x8dac65  stsfld   class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Utilities.SharePointLinkReplace::UlsCategory
0x8dac6a  ldc.i4.s 0x1B
0x8dac6c  newarr   Entry
0x8dac71  stloc.0
0x8dac72  ldloc.0
0x8dac73  ldc.i4.0
0x8dac74  ldc.i4.1
0x8dac75  ldstr    aXsfXdocumentcl_2// "/xsf:xDocumentClass/xsf:dataAdapters/xs"...
0x8dac7a  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dac7f  stelem.ref
0x8dac80  ldloc.0
0x8dac81  ldc.i4.1
0x8dac82  ldc.i4.1
0x8dac83  ldstr    aXsfXdocumentcl_3// "/xsf:xDocumentClass/xsf:dataObjects/xsf"...
0x8dac88  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dac8d  stelem.ref
0x8dac8e  ldloc.0
0x8dac8f  ldc.i4.2
0x8dac90  ldc.i4.1
0x8dac91  ldstr    aXsfXdocumentcl_4// "/xsf:xDocumentClass/xsf:dataObjects/xsf"...
0x8dac96  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dac9b  stelem.ref
0x8dac9c  ldloc.0
0x8dac9d  ldc.i4.3
0x8dac9e  ldc.i4.1
0x8dac9f  ldstr    aXsfXdocumentcl_5// "/xsf:xDocumentClass/xsf:query/xsf:webSe"...
0x8daca4  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8daca9  stelem.ref
0x8dacaa  ldloc.0
0x8dacab  ldc.i4.4
0x8dacac  ldc.i4.1
0x8dacad  ldstr    aXsfXdocumentcl_6// "/xsf:xDocumentClass/xsf:query/xsf:webSe"...
0x8dacb2  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dacb7  stelem.ref
0x8dacb8  ldloc.0
0x8dacb9  ldc.i4.5
0x8dacba  ldc.i4.1
0x8dacbb  ldstr    aXsfXdocumentcl_7// "/xsf:xDocumentClass/xsf:query/xsf:share"...
0x8dacc0  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dacc5  stelem.ref
0x8dacc6  ldloc.0
0x8dacc7  ldc.i4.6
0x8dacc8  ldc.i4.1
0x8dacc9  ldstr    aXsfXdocumentcl_8// "/xsf:xDocumentClass/xsf:submit/xsf:webS"...
0x8dacce  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dacd3  stelem.ref
0x8dacd4  ldloc.0
0x8dacd5  ldc.i4.7
0x8dacd6  ldc.i4.1
0x8dacd7  ldstr    aXsfXdocumentcl_9// "/xsf:xDocumentClass/xsf:submit/xsf:webS"...
0x8dacdc  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dace1  stelem.ref
0x8dace2  ldloc.0
0x8dace3  ldc.i4.8
0x8dace4  ldc.i4.1
0x8dace5  ldstr    aXsfXdocumentcl_10// "/xsf:xDocumentClass/xsf:submit/xsf:davA"...
0x8dacea  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dacef  stelem.ref
0x8dacf0  ldloc.0
0x8dacf1  ldc.i4.s 9
0x8dacf3  ldc.i4.1
0x8dacf4  ldstr    aXsfXdocumentcl_11// "/xsf:xDocumentClass/xsf:dataAdapters/xs"...
0x8dacf9  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dacfe  stelem.ref
0x8dacff  ldloc.0
0x8dad00  ldc.i4.s 0xA
0x8dad02  ldc.i4.1
0x8dad03  ldstr    aXsfXdocumentcl_12// "/xsf:xDocumentClass/xsf:dataAdapters/xs"...
0x8dad08  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dad0d  stelem.ref
0x8dad0e  ldloc.0
0x8dad0f  ldc.i4.s 0xB
0x8dad11  ldc.i4.1
0x8dad12  ldstr    aXsfXdocumentcl_13// "/xsf:xDocumentClass/xsf:dataObjects/xsf"...
0x8dad17  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dad1c  stelem.ref
0x8dad1d  ldloc.0
0x8dad1e  ldc.i4.s 0xC
0x8dad20  ldc.i4.1
0x8dad21  ldstr    aXsfXdocumentcl_14// "/xsf:xDocumentClass/xsf:dataObjects/xsf"...
0x8dad26  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dad2b  stelem.ref
0x8dad2c  ldloc.0
0x8dad2d  ldc.i4.s 0xD
0x8dad2f  ldc.i4.1
0x8dad30  ldstr    aXsfXdocumentcl_15// "/xsf:xDocumentClass/xsf:extensions/xsf:"...
0x8dad35  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dad3a  stelem.ref
0x8dad3b  ldloc.0
0x8dad3c  ldc.i4.s 0xE
0x8dad3e  ldc.i4.1
0x8dad3f  ldstr    aXsfXdocumentcl_16// "/xsf:xDocumentClass/xsf:extensions/xsf:"...
0x8dad44  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dad49  stelem.ref
0x8dad4a  ldloc.0
0x8dad4b  ldc.i4.s 0xF
0x8dad4d  ldc.i4.1
0x8dad4e  ldstr    aXsfXdocumentcl_17// "/xsf:xDocumentClass/xsf:extensions/xsf:"...
0x8dad53  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dad58  stelem.ref
0x8dad59  ldloc.0
0x8dad5a  ldc.i4.s 0x10
0x8dad5c  ldc.i4.1
0x8dad5d  ldstr    aXsfXdocumentcl_18// "/xsf:xDocumentClass/xsf:extensions/xsf:"...
0x8dad62  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dad67  stelem.ref
0x8dad68  ldloc.0
0x8dad69  ldc.i4.s 0x11
0x8dad6b  ldc.i4.1
0x8dad6c  ldstr    aXsfXdocumentcl_19// "/xsf:xDocumentClass/xsf:extensions/xsf:"...
0x8dad71  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dad76  stelem.ref
0x8dad77  ldloc.0
0x8dad78  ldc.i4.s 0x12
0x8dad7a  ldc.i4.1
0x8dad7b  ldstr    aXsfXdocumentcl_20// "/xsf:xDocumentClass/xsf:extensions/xsf:"...
0x8dad80  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dad85  stelem.ref
0x8dad86  ldloc.0
0x8dad87  ldc.i4.s 0x13
0x8dad89  ldc.i4.1
0x8dad8a  ldstr    aXsfXdocumentcl_21// "/xsf:xDocumentClass/xsf:submit/xsf:useH"...
0x8dad8f  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dad94  stelem.ref
0x8dad95  ldloc.0
0x8dad96  ldc.i4.s 0x14
0x8dad98  ldc.i4.1
0x8dad99  ldstr    aXsfXdocumentcl_22// "/xsf:xDocumentClass/xsf:dataObjects/xsf"...
0x8dad9e  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dada3  stelem.ref
0x8dada4  ldloc.0
0x8dada5  ldc.i4.s 0x15
0x8dada7  ldc.i4.1
0x8dada8  ldstr    aXsfXdocumentcl_23// "/xsf:xDocumentClass/xsf:taskpane/@href"
0x8dadad  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dadb2  stelem.ref
0x8dadb3  ldloc.0
0x8dadb4  ldc.i4.s 0x16
0x8dadb6  ldc.i4.1
0x8dadb7  ldstr    aXsfXdocumentcl_24// "/xsf:xDocumentClass/xsf:ruleSets/xsf:ru"...
0x8dadbc  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dadc1  stelem.ref
0x8dadc2  ldloc.0
0x8dadc3  ldc.i4.s 0x17
0x8dadc5  ldc.i4.0
0x8dadc6  ldstr    aXsfXdocumentcl_25// "/xsf:xDocumentClass/xsf:extensions/xsf:"...
0x8dadcb  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dadd0  stelem.ref
0x8dadd1  ldloc.0
0x8dadd2  ldc.i4.s 0x18
0x8dadd4  ldc.i4.0
0x8dadd5  ldstr    aXsfXdocumentcl_26// "/xsf:xDocumentClass/xsf:extensions/xsf:"...
0x8dadda  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8daddf  stelem.ref
0x8dade0  ldloc.0
0x8dade1  ldc.i4.s 0x19
0x8dade3  ldc.i4.0
0x8dade4  ldstr    aXsfXdocumentcl_27// "/xsf:xDocumentClass/xsf:extensions/xsf:"...
0x8dade9  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dadee  stelem.ref
0x8dadef  ldloc.0
0x8dadf0  ldc.i4.s 0x1A
0x8dadf2  ldc.i4.1
0x8dadf3  ldstr    aXsfXdocumentcl_28// "/xsf:xDocumentClass/xsf:extensions/xsf:"...
0x8dadf8  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dadfd  stelem.ref
0x8dadfe  ldloc.0
0x8dadff  stsfld   class Entry[] Microsoft.SharePoint.Utilities.SharePointLinkReplace::XSFEntryNeedtoFix
0x8dae04  ldc.i4.7
0x8dae05  newarr   Entry
0x8dae0a  stloc.1
0x8dae0b  ldloc.1
0x8dae0c  ldc.i4.0
0x8dae0d  ldc.i4.1
0x8dae0e  ldstr    aUdcDatasourceU// "/udc:DataSource/udc:ConnectionInfo/udc:"...
0x8dae13  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dae18  stelem.ref
0x8dae19  ldloc.1
0x8dae1a  ldc.i4.1
0x8dae1b  ldc.i4.1
0x8dae1c  ldstr    aUdcDatasourceU_0// "/udc:DataSource/udc:ConnectionInfo/udc:"...
0x8dae21  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dae26  stelem.ref
0x8dae27  ldloc.1
0x8dae28  ldc.i4.2
0x8dae29  ldc.i4.1
0x8dae2a  ldstr    aUdcDatasourceU_1// "/udc:DataSource/udc:ConnectionInfo/udc:"...
0x8dae2f  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dae34  stelem.ref
0x8dae35  ldloc.1
0x8dae36  ldc.i4.3
0x8dae37  ldc.i4.1
0x8dae38  ldstr    aUdcDatasourceU_2// "/udc:DataSource/udc:ConnectionInfo/udc:"...
0x8dae3d  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dae42  stelem.ref
0x8dae43  ldloc.1
0x8dae44  ldc.i4.4
0x8dae45  ldc.i4.1
0x8dae46  ldstr    aUdcDatasourceU_3// "/udc:DataSource/udc:ConnectionInfo/udc:"...
0x8dae4b  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dae50  stelem.ref
0x8dae51  ldloc.1
0x8dae52  ldc.i4.5
0x8dae53  ldc.i4.1
0x8dae54  ldstr    aUdcDatasourceU_4// "/udc:DataSource/udc:ConnectionInfo/udc:"...
0x8dae59  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dae5e  stelem.ref
0x8dae5f  ldloc.1
0x8dae60  ldc.i4.6
0x8dae61  ldc.i4.1
0x8dae62  ldstr    aUdcDatasourceU_5// "/udc:DataSource/udc:ConnectionInfo/udc:"...
0x8dae67  newobj   instance void Entry::.ctor(bool fIsUrl, string entryXPath)
0x8dae6c  stelem.ref
0x8dae6d  ldloc.1
0x8dae6e  stsfld   class Entry[] Microsoft.SharePoint.Utilities.SharePointLinkReplace::UDCEntryNeedtoFix
0x8dae73  ret
```
