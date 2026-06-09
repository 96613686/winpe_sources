# Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::.cctor

- ea: `0x4e640`
- end: `0x4e941`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::.cctor`
- size: `769`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x4e7bc`: `Computer`
- `0x4e730`: `ViewerConfig`
- `0x4e74e`: `FilePath`
- `0x4e762`: `QueryConfig`
- `0x4e82a`: `ResultsConfig`
- `0x4e85c`: `SortConfig`
- `0x4e866`: `GroupConfig`
- `0x4e8c0`: `Application and Services Logs`

## pseudocode

```c

```

## disassembly

```asm
0x4e640  ldstr    aViews// "Views"
0x4e645  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::VIEWSNODE
0x4e64a  ldstr    aView_0// "View"
0x4e64f  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::VIEWNODE
0x4e654  ldstr    aViewfolder// "ViewFolder"
0x4e659  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::VIEWFOLDERNODE
0x4e65e  ldstr    aName// "Name"
0x4e663  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::NAMEATTR
0x4e668  ldstr    aPath// "Path"
0x4e66d  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::PATHATTR
0x4e672  ldstr    aSelect// "Select"
0x4e677  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::SELECTNODE
0x4e67c  ldstr    aSuppress// "Suppress"
0x4e681  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::SUPPRESSNODE
0x4e686  ldstr    aQuery// "Query"
0x4e68b  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::QUERYNODE
0x4e690  ldstr    aDescription// "Description"
0x4e695  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::DescriptionNode
0x4e69a  ldstr    aLanguageneutra// "LanguageNeutralValue"
0x4e69f  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::LanguageNeutralValue
0x4e6a4  ldstr    aColumns// "Columns"
0x4e6a9  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::COLUMNSNODE
0x4e6ae  ldstr    aColumn// "Column"
0x4e6b3  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::COLUMNNODE
0x4e6b8  ldstr    aType// "Type"
0x4e6bd  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::TYPENODE
0x4e6c2  ldstr    aLength// "Length"
0x4e6c7  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::LENGTHNODE
0x4e6cc  ldstr    aPath// "Path"
0x4e6d1  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::PATHNODE
0x4e6d6  ldstr    aCrimsonviewroo// "CRIMSONVIEWROOTFOLDER"
0x4e6db  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::ROOTFOLDER
0x4e6e0  ldstr    aTarget// "Target"
0x4e6e5  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::TARGETNAME
0x4e6ea  ldstr    aSourcequery// "SourceQuery"
0x4e6ef  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::SOURCEQUERY
0x4e6f4  ldstr    aId// "Id"
0x4e6f9  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::IDATTR
0x4e6fe  ldstr    aQuerylist// "QueryList"
0x4e703  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::QUERYLISTNODE
0x4e708  ldstr    aQuerynode// "QueryNode"
0x4e70d  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::QueryConfigRootNode
0x4e712  ldstr    aName_0// "Name`   "
0x4e717  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::QueryConfigQueryName
0x4e71c  ldstr    aDescription// "Description"
0x4e721  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::QueryConfigQueryDescription
0x4e726  ldstr    aResourceid// "ResourceId"
0x4e72b  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::ResourceIdAttr
0x4e730  ldstr    aViewerconfig// "ViewerConfig"
0x4e735  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::ConfigRootNode
0x4e73a  ldstr    aExternallog// "ExternalLog"
0x4e73f  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::ExternalLog
0x4e744  ldstr    aName// "Name"
0x4e749  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::NameNode
0x4e74e  ldstr    aFilepath// "FilePath"
0x4e753  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::ExternalFilePath
0x4e758  ldstr    aFile// "file://"
0x4e75d  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::ExternalFilePrefix
0x4e762  ldstr    aQueryconfig// "QueryConfig"
0x4e767  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::QueryConfig
0x4e76c  ldstr    aQueryparams// "QueryParams"
0x4e771  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::QueryParams
0x4e776  ldstr    aUserquery// "UserQuery"
0x4e77b  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::UserQuery
0x4e780  ldstr    aSimple// "Simple"
0x4e785  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::Simple
0x4e78a  ldstr    aChannel// "Channel"
0x4e78f  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::Channel
0x4e794  ldstr    aSource// "Source"
0x4e799  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::Source
0x4e79e  ldstr    aLevel// "Level"
0x4e7a3  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::Level
0x4e7a8  ldstr    aTask// "Task"
0x4e7ad  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::Task
0x4e7b2  ldstr    aUser// "User"
0x4e7b7  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::User
0x4e7bc  ldstr    aComputer// "Computer"
0x4e7c1  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::Computer
0x4e7c6  ldstr    aEventid// "EventId"
0x4e7cb  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::EventId
0x4e7d0  ldstr    aKeywords_0// "KeyWords"
0x4e7d5  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::KeyWords
0x4e7da  ldstr    aFromdate// "FromDate"
0x4e7df  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::FromDate
0x4e7e4  ldstr    aTodate// "ToDate"
0x4e7e9  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::ToDate
0x4e7ee  ldstr    aRelativetimein// "RelativeTimeInfo"
0x4e7f3  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::RelativeTimeInfo
0x4e7f8  ldstr    aBysource// "BySource"
0x4e7fd  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::BySource
0x4e802  ldstr    aType// "Type"
0x4e807  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::TypeAttr
0x4e80c  ldstr    aId_0// "ID"
0x4e811  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::IdAttr
0x4e816  ldstr    aPath// "Path"
0x4e81b  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::PathAttr
0x4e820  ldstr    aVisible// "Visible"
0x4e825  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::VisibleAttr
0x4e82a  ldstr    aResultsconfig// "ResultsConfig"
0x4e82f  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::ResultViewConfig
0x4e834  ldstr    aPreview// "Preview"
0x4e839  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::PreviewConfigNode
0x4e83e  ldstr    aDirectchannels// "DirectChannelsVisible"
0x4e843  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::DirectChannelsVisible
0x4e848  ldstr    asc_A8C94// "-"
0x4e84d  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::CrimsonPublisherNamingDelimiter
0x4e852  ldstr    asc_AC608// "/"
0x4e857  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::CrimsonPublisherNamingDelimiterForChannel
0x4e85c  ldstr    aSortconfig// "SortConfig"
0x4e861  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::SortingParam
0x4e866  ldstr    aGroupconfig// "GroupConfig"
0x4e86b  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::GroupingParam
0x4e870  ldstr    aAsc// "Asc"
0x4e875  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::Ascending
0x4e87a  ldstr    a1// "1"
0x4e87f  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::True
0x4e884  ldstr    a0_2// "0"
0x4e889  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::False
0x4e88e  ldstr    aSuppressquerye// "SuppressQueryExecutionErrors"
0x4e893  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::SuppressQueryExecutionErrors
0x4e898  ldstr    aEventViewer// "Event Viewer"
0x4e89d  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::LIN_EventViewer
0x4e8a2  ldstr    aCustomViews// "Custom Views"
0x4e8a7  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::LIN_CustomViews
0x4e8ac  ldstr    aSavedLogs// "Saved Logs"
0x4e8b1  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::LIN_ExternalLogs
0x4e8b6  ldstr    aSubscriptions// "Subscriptions"
0x4e8bb  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::LIN_Subscriptions
0x4e8c0  ldstr    aApplicationAnd// "Application and Services Logs"
0x4e8c5  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::LIN_ApplicationLogs
0x4e8ca  ldstr    aWindowsLogs// "Windows Logs"
0x4e8cf  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::LIN_WindowsLogs
0x4e8d4  ldstr    aMicrosoft// "Microsoft"
0x4e8d9  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::MicrosoftFolderName
0x4e8de  ldc.i4.s 0xA
0x4e8e0  newarr   [mscorlib]System.String
0x4e8e5  dup
0x4e8e6  ldc.i4.0
0x4e8e7  ldstr    aSystemString// "System.String"
0x4e8ec  stelem.ref
0x4e8ed  dup
0x4e8ee  ldc.i4.1
0x4e8ef  ldstr    aSystemDatetime// "System.DateTime"
0x4e8f4  stelem.ref
0x4e8f5  dup
0x4e8f6  ldc.i4.2
0x4e8f7  ldstr    aSystemGuid// "System.Guid"
0x4e8fc  stelem.ref
0x4e8fd  dup
0x4e8fe  ldc.i4.3
0x4e8ff  ldstr    aSystemInt32// "System.Int32"
0x4e904  stelem.ref
0x4e905  dup
0x4e906  ldc.i4.4
0x4e907  ldstr    aSystemInt16// "System.Int16"
0x4e90c  stelem.ref
0x4e90d  dup
0x4e90e  ldc.i4.5
0x4e90f  ldstr    aSystemInt64// "System.Int64"
0x4e914  stelem.ref
0x4e915  dup
0x4e916  ldc.i4.6
0x4e917  ldstr    aSystemUint16// "System.UInt16"
0x4e91c  stelem.ref
0x4e91d  dup
0x4e91e  ldc.i4.7
0x4e91f  ldstr    aSystemUint32// "System.UInt32"
0x4e924  stelem.ref
0x4e925  dup
0x4e926  ldc.i4.8
0x4e927  ldstr    aSystemUint64// "System.UInt64"
0x4e92c  stelem.ref
0x4e92d  dup
0x4e92e  ldc.i4.s 9
0x4e930  ldstr    aSystemObject// "System.Object"
0x4e935  stelem.ref
0x4e936  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x4e93b  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::ColumnTypes
0x4e940  ret
```
