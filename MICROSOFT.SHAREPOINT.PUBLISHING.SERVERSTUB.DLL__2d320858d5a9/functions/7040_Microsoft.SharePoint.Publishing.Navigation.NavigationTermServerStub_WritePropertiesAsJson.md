# Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::WritePropertiesAsJson

- ea: `0x7040`
- end: `0x725f`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::WritePropertiesAsJson`
- size: `543`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5d80`
- `0x7040`

## string_xrefs

- `0x7225`: `SimpleLinkUrl`
- `0x7231`: `SimpleLinkUrl`
- `0x723c`: `SimpleLinkUrl`
- `0x7254`: `SimpleLinkUrl`

## pseudocode

```c

```

## disassembly

```asm
0x7040  ldarg.2
0x7041  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm
0x7046  stloc.0
0x7047  ldloc.0
0x7048  brtrue.s loc_704B
0x704a  ret
0x704b  ldarg.0
0x704c  ldarg.1
0x704d  ldarg.2
0x704e  ldarg.3
0x704f  call     instance void Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter writer, object target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7054  ldarg.0
0x7055  ldstr    aAssociatedfold// "AssociatedFolderUrl"
0x705a  ldarg.3
0x705b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7060  ldarg.1
0x7061  ldstr    aAssociatedfold// "AssociatedFolderUrl"
0x7066  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x706b  ldarg.3
0x706c  ldstr    aAssociatedfold// "AssociatedFolderUrl"
0x7071  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x7076  ldarg.1
0x7077  ldloc.0
0x7078  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_AssociatedFolderUrl()
0x707d  ldarg.3
0x707e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7083  ldarg.3
0x7084  ldstr    aAssociatedfold// "AssociatedFolderUrl"
0x7089  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x708e  ldarg.0
0x708f  ldstr    aCategoryimageu// "CategoryImageUrl"
0x7094  ldarg.3
0x7095  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x709a  ldarg.1
0x709b  ldstr    aCategoryimageu// "CategoryImageUrl"
0x70a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x70a5  ldarg.3
0x70a6  ldstr    aCategoryimageu// "CategoryImageUrl"
0x70ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x70b0  ldarg.1
0x70b1  ldloc.0
0x70b2  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_CategoryImageUrl()
0x70b7  ldarg.3
0x70b8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x70bd  ldarg.3
0x70be  ldstr    aCategoryimageu// "CategoryImageUrl"
0x70c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x70c8  ldarg.0
0x70c9  ldstr    aExcludefromcur// "ExcludeFromCurrentNavigation"
0x70ce  ldarg.3
0x70cf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x70d4  ldarg.1
0x70d5  ldstr    aExcludefromcur// "ExcludeFromCurrentNavigation"
0x70da  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x70df  ldarg.3
0x70e0  ldstr    aExcludefromcur// "ExcludeFromCurrentNavigation"
0x70e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x70ea  ldarg.1
0x70eb  ldloc.0
0x70ec  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_ExcludeFromCurrentNavigation()
0x70f1  ldarg.3
0x70f2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x70f7  ldarg.3
0x70f8  ldstr    aExcludefromcur// "ExcludeFromCurrentNavigation"
0x70fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x7102  ldarg.0
0x7103  ldstr    aExcludefromglo// "ExcludeFromGlobalNavigation"
0x7108  ldarg.3
0x7109  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x710e  ldarg.1
0x710f  ldstr    aExcludefromglo// "ExcludeFromGlobalNavigation"
0x7114  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x7119  ldarg.3
0x711a  ldstr    aExcludefromglo// "ExcludeFromGlobalNavigation"
0x711f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x7124  ldarg.1
0x7125  ldloc.0
0x7126  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_ExcludeFromGlobalNavigation()
0x712b  ldarg.3
0x712c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7131  ldarg.3
0x7132  ldstr    aExcludefromglo// "ExcludeFromGlobalNavigation"
0x7137  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x713c  ldarg.0
0x713d  ldstr    aHovertext// "HoverText"
0x7142  ldarg.3
0x7143  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7148  ldarg.1
0x7149  ldstr    aHovertext// "HoverText"
0x714e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x7153  ldarg.3
0x7154  ldstr    aHovertext// "HoverText"
0x7159  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x715e  ldarg.1
0x715f  ldloc.0
0x7160  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_HoverText()
0x7165  ldarg.3
0x7166  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x716b  ldarg.3
0x716c  ldstr    aHovertext// "HoverText"
0x7171  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x7176  ldarg.0
0x7177  ldstr    aIsdeprecated// "IsDeprecated"
0x717c  ldarg.3
0x717d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7182  ldarg.1
0x7183  ldstr    aIsdeprecated// "IsDeprecated"
0x7188  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x718d  ldarg.3
0x718e  ldstr    aIsdeprecated// "IsDeprecated"
0x7193  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x7198  ldarg.1
0x7199  ldloc.0
0x719a  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_IsDeprecated()
0x719f  ldarg.3
0x71a0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71a5  ldarg.3
0x71a6  ldstr    aIsdeprecated// "IsDeprecated"
0x71ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x71b0  ldarg.0
0x71b1  ldstr    aIspinned// "IsPinned"
0x71b6  ldarg.3
0x71b7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71bc  ldarg.1
0x71bd  ldstr    aIspinned// "IsPinned"
0x71c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x71c7  ldarg.3
0x71c8  ldstr    aIspinned// "IsPinned"
0x71cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x71d2  ldarg.1
0x71d3  ldloc.0
0x71d4  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_IsPinned()
0x71d9  ldarg.3
0x71da  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71df  ldarg.3
0x71e0  ldstr    aIspinned// "IsPinned"
0x71e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x71ea  ldarg.0
0x71eb  ldstr    aIspinnedroot// "IsPinnedRoot"
0x71f0  ldarg.3
0x71f1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71f6  ldarg.1
0x71f7  ldstr    aIspinnedroot// "IsPinnedRoot"
0x71fc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x7201  ldarg.3
0x7202  ldstr    aIspinnedroot// "IsPinnedRoot"
0x7207  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x720c  ldarg.1
0x720d  ldloc.0
0x720e  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_IsPinnedRoot()
0x7213  ldarg.3
0x7214  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7219  ldarg.3
0x721a  ldstr    aIspinnedroot// "IsPinnedRoot"
0x721f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x7224  ldarg.0
0x7225  ldstr    aSimplelinkurl// "SimpleLinkUrl"
0x722a  ldarg.3
0x722b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7230  ldarg.1
0x7231  ldstr    aSimplelinkurl// "SimpleLinkUrl"
0x7236  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x723b  ldarg.3
0x723c  ldstr    aSimplelinkurl// "SimpleLinkUrl"
0x7241  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x7246  ldarg.1
0x7247  ldloc.0
0x7248  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_SimpleLinkUrl()
0x724d  ldarg.3
0x724e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7253  ldarg.3
0x7254  ldstr    aSimplelinkurl// "SimpleLinkUrl"
0x7259  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x725e  ret
```
