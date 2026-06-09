# Microsoft.SharePoint.UserCode.SPDefaultSolutionValidator::.cctor

- ea: `0x7845e0`
- end: `0x784f99`
- name: `Microsoft.SharePoint.UserCode.SPDefaultSolutionValidator::.cctor`
- size: `2489`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x7845fd`: `system.array.createinstance`
- `0x784655`: `system.runtime.interopservices`
- `0x78466b`: `system.threading`
- `0x784705`: `microsoft.office.securestoreservice.powershellcmdlet`
- `0x784710`: `microsoft.office.securestoreservice.server`
- `0x78471b`: `microsoft.office.securestoreservice.server.keymanagement`
- `0x78473c`: `microsoft.office.securestoreservice.server.upgrade`
- `0x784747`: `microsoft.office.securestoreservice.server.security`
- `0x784768`: `microsoft.office.server.diagnostics.ulseventtemplates`
- `0x784789`: `microsoft.office.server.security`
- `0x7847cb`: `microsoft.office.server.objectcache`
- `0x7847d6`: `microsoft.office.server.commandline`
- `0x78480d`: `microsoft.office.server.utilities.security`
- `0x784844`: `microsoft.office.server.activitycache`
- `0x784865`: `microsoft.office.server.userprofiles.cache`
- `0x7848e9`: `microsoft.office.server.search.administration.commandline`
- `0x78490a`: `microsoft.office.server.search.administration.noteswebservicewrapper`
- `0x784915`: `microsoft.office.server.search.administration.security`
- `0x784936`: `microsoft.office.server.search.extended.administration.common`
- `0x784962`: `microsoft.office.server.search.internal.protocols`
- `0x78496d`: `microsoft.office.server.search.internal.protocols.peoplesoapproxy`
- `0x784978`: `microsoft.office.server.search.internal.protocols.sharepoint2001`
- `0x784983`: `microsoft.office.server.search.internal.protocols.sharepoint2003`
- `0x78498e`: `microsoft.office.server.search.internal.protocols.sharepoint2006`
- `0x784999`: `microsoft.office.server.search.internal.protocols.sharepointportal2003`
- `0x7849a4`: `microsoft.office.server.search.internal.protocols.sitedata`
- `0x7849af`: `microsoft.office.server.search.internal.protocols.spscrawl`
- `0x7849e6`: `microsoft.office.server.search.query.common`
- `0x784a28`: `microsoft.search.administration.commandline`
- `0x784a33`: `microsoft.search.administration.security`
- `0x784a49`: `microsoft.search.server.comadmin`
- `0x784a75`: `microsoft.office.server.applicationregistry.administration`
- `0x784a80`: `microsoft.office.server.applicationregistry.infrastructure`
- `0x784a8b`: `microsoft.office.server.applicationregistry.metadatamodel`
- `0x784a96`: `microsoft.office.server.applicationregistry.runtime`
- `0x784aa1`: `microsoft.office.server.applicationregistry.search`
- `0x784aac`: `microsoft.office.server.applicationregistry.sharedservice`
- `0x784ab7`: `microsoft.office.server.applicationregistry.systemspecific.db`
- `0x784ac2`: `microsoft.office.server.applicationregistry.systemspecific.webservice`
- `0x784acd`: `microsoft.office.server.applicationregistry.upgrade`
- `0x784b7d`: `microsoft.sharepoint.portal.security`
- `0x784bb4`: `microsoft.sharepoint.portal.sitedirectory`
- `0x784c01`: `microsoft.sharepoint.portal.webcontrols.wsrpwebservice`
- `0x784c4e`: `microsoft.office.workflow.templates`
- `0x784cdd`: `microsoft.sharepoint.publishing.webservices`
- `0x784ce8`: `microsoft.sharepoint.publishing.administration.webservices`
- `0x784cf3`: `microsoft.sharepoint.publishing.internal.xml`
- `0x784d35`: `microsoft.sharepoint.search.internal.protocols`
- `0x784d40`: `microsoft.sharepoint.search.internal.protocols.peoplesoapproxy`
- `0x784d4b`: `microsoft.sharepoint.search.internal.protocols.sharepoint2001`
- `0x784d56`: `microsoft.sharepoint.search.internal.protocols.sharepoint2003`
- `0x784d61`: `microsoft.sharepoint.search.internal.protocols.sharepoint2006`
- `0x784d6c`: `microsoft.sharepoint.search.internal.protocols.sharepointportal2003`
- `0x784d77`: `microsoft.sharepoint.search.internal.protocols.sitedata`
- `0x784d82`: `microsoft.sharepoint.search.internal.protocols.spscrawl`
- `0x784da3`: `microsoft.sharepoint.search.plugin`
- `0x784dda`: `microsoft.sharepoint.search.extended.administration.common`
- `0x784dfb`: `microsoft.sharepoint.search.extended.administration.service`
- `0x784e06`: `microsoft.sharepoint.search.extended.administration.service.dto`
- `0x784e95`: `microsoft.sharepoint.search.extended.administration.commandlets.properties`
- `0x784ea0`: `microsoft.sharepoint.search.extended.administration.commandlets`
- `0x784eab`: `microsoft.sharepoint.search.extended.administration.commandlets.schema`
- `0x784f25`: `system.runtime.interopservices.layoutkind`
- `0x784f30`: `system.threading.monitor.enter`
- `0x784f3b`: `system.threading.monitor.exit`
- `0x784f46`: `system.threading.thread.get_currentthread`
- `0x784f51`: `system.threading.thread.get_managedthreadid`
- `0x784f5c`: `system.threading.interlocked.compareexchange`

## pseudocode

```c

```

## disassembly

```asm
0x7845e0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x7845e5  stloc.0
0x7845e6  ldloc.0
0x7845e7  ldstr    aMicrosoftSqlse_5// "microsoft.sqlserver"
0x7845ec  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7845f1  ldloc.0
0x7845f2  ldstr    aMicrosoftWin32// "microsoft.win32"
0x7845f7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7845fc  ldloc.0
0x7845fd  ldstr    aSystemArrayCre// "system.array.createinstance"
0x784602  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784607  ldloc.0
0x784608  ldstr    aSystemDataSql// "system.data.sql"
0x78460d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784612  ldloc.0
0x784613  ldstr    aSystemDataSqlc// "system.data.sqlclient"
0x784618  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78461d  ldloc.0
0x78461e  ldstr    aSystemDataSqlt// "system.data.sqltypes"
0x784623  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784628  ldloc.0
0x784629  ldstr    aSystemDelegate// "system.delegates"
0x78462e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784633  ldloc.0
0x784634  ldstr    aSystemIoPipes// "system.io.pipes"
0x784639  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78463e  ldloc.0
0x78463f  ldstr    aSystemIoPorts// "system.io.ports"
0x784644  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784649  ldloc.0
0x78464a  ldstr    aSystemReflecti// "system.reflection"
0x78464f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784654  ldloc.0
0x784655  ldstr    aSystemRuntimeI// "system.runtime.interopservices"
0x78465a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78465f  ldloc.0
0x784660  ldstr    aSystemRuntimeR// "system.runtime.remoting"
0x784665  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78466a  ldloc.0
0x78466b  ldstr    aSystemThreadin// "system.threading"
0x784670  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784675  ldloc.0
0x784676  ldstr    aSystemTypeGett// "system.type.gettype"
0x78467b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784680  ldloc.0
0x784681  ldstr    aSystemTypeInvo// "system.type.invokemember"
0x784686  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78468b  ldloc.0
0x78468c  ldstr    aMicrosoftBusin_0// "microsoft.businessdata.infrastructure"
0x784691  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784696  ldloc.0
0x784697  ldstr    aMicrosoftBusin_1// "microsoft.businessdata.infrastructure.c"...
0x78469c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7846a1  ldloc.0
0x7846a2  ldstr    aMicrosoftBusin_2// "microsoft.businessdata.infrastructure.s"...
0x7846a7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7846ac  ldloc.0
0x7846ad  ldstr    aMicrosoftBusin_3// "microsoft.businessdata.infrastructure.t"...
0x7846b2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7846b7  ldloc.0
0x7846b8  ldstr    aMicrosoftBusin_4// "microsoft.businessdata.metadatamodel.co"...
0x7846bd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7846c2  ldloc.0
0x7846c3  ldstr    aMicrosoftBusin_5// "microsoft.businessdata.metadatamodel"
0x7846c8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7846cd  ldloc.0
0x7846ce  ldstr    aMicrosoftBusin_6// "microsoft.businessdata.offlining"
0x7846d3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7846d8  ldloc.0
0x7846d9  ldstr    aMicrosoftBusin_7// "microsoft.businessdata.runtime"
0x7846de  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7846e3  ldloc.0
0x7846e4  ldstr    aMicrosoftBusin_8// "microsoft.businessdata.systemspecific.w"...
0x7846e9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7846ee  ldloc.0
0x7846ef  ldstr    aMicrosoftBusin_9// "microsoft.businessdata.systemspecific"
0x7846f4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7846f9  ldloc.0
0x7846fa  ldstr    aMicrosoftOffic_51// "microsoft.office.excel.server.udf"
0x7846ff  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784704  ldloc.0
0x784705  ldstr    aMicrosoftOffic_52// "microsoft.office.securestoreservice.pow"...
0x78470a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78470f  ldloc.0
0x784710  ldstr    aMicrosoftOffic_53// "microsoft.office.securestoreservice.ser"...
0x784715  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78471a  ldloc.0
0x78471b  ldstr    aMicrosoftOffic_54// "microsoft.office.securestoreservice.ser"...
0x784720  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784725  ldloc.0
0x784726  ldstr    aMicrosoftOffic_55// "microsoft.office.server.data"
0x78472b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784730  ldloc.0
0x784731  ldstr    aMicrosoftOffic_56// "microsoft.office.server.data.sql"
0x784736  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78473b  ldloc.0
0x78473c  ldstr    aMicrosoftOffic_57// "microsoft.office.securestoreservice.ser"...
0x784741  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784746  ldloc.0
0x784747  ldstr    aMicrosoftOffic_58// "microsoft.office.securestoreservice.ser"...
0x78474c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784751  ldloc.0
0x784752  ldstr    aMicrosoftOffic_59// "microsoft.office.server.internal.resour"...
0x784757  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78475c  ldloc.0
0x78475d  ldstr    aMicrosoftOffic_60// "microsoft.office.server.diagnostics"
0x784762  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784767  ldloc.0
0x784768  ldstr    aMicrosoftOffic_61// "microsoft.office.server.diagnostics.uls"...
0x78476d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784772  ldloc.0
0x784773  ldstr    aMicrosoftOffic_62// "microsoft.office.server.administration"
0x784778  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78477d  ldloc.0
0x78477e  ldstr    aMicrosoftOffic_63// "microsoft.office.server.metabase"
0x784783  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784788  ldloc.0
0x784789  ldstr    aMicrosoftOffic_64// "microsoft.office.server.security"
0x78478e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784793  ldloc.0
0x784794  ldstr    aMicrosoftOffic_65// "microsoft.office.server.utilities"
0x784799  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78479e  ldloc.0
0x78479f  ldstr    aMicrosoftOffic_66// "microsoft.office.server.utilities.win32"
0x7847a4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7847a9  ldloc.0
0x7847aa  ldstr    aMicrosoftOffic_67// "microsoft.office.server"
0x7847af  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7847b4  ldloc.0
0x7847b5  ldstr    aMicrosoftOffic_68// "microsoft.office.server.auditing"
0x7847ba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7847bf  ldloc.0
0x7847c0  ldstr    aMicrosoftOffic_69// "microsoft.office.server.cabinet"
0x7847c5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7847ca  ldloc.0
0x7847cb  ldstr    aMicrosoftOffic_70// "microsoft.office.server.objectcache"
0x7847d0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7847d5  ldloc.0
0x7847d6  ldstr    aMicrosoftOffic_71// "microsoft.office.server.commandline"
0x7847db  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7847e0  ldloc.0
0x7847e1  ldstr    aMicrosoftOffic_72// "microsoft.office.server.evaluatormodepr"...
0x7847e6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7847eb  ldloc.0
0x7847ec  ldstr    aMicrosoftOffic_73// "microsoft.office.server.infrastructure"
0x7847f1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7847f6  ldloc.0
0x7847f7  ldstr    aMicrosoftOffic_74// "microsoft.office.server.monitoring"
0x7847fc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784801  ldloc.0
0x784802  ldstr    aMicrosoftOffic_75// "microsoft.office.server.internal"
0x784807  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78480c  ldloc.0
0x78480d  ldstr    aMicrosoftOffic_76// "microsoft.office.server.utilities.secur"...
0x784812  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784817  ldloc.0
0x784818  ldstr    aMicrosoftOffic_77// "microsoft.office.server.upgrade"
0x78481d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784822  ldloc.0
0x784823  ldstr    aMicrosoftOffic_78// "microsoft.office.server.webcontrols"
0x784828  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78482d  ldloc.0
0x78482e  ldstr    aMicrosoftOffic_79// "microsoft.office.server.search.portalcr"...
0x784833  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784838  ldloc.0
0x784839  ldstr    aMicrosoftOffic_80// "microsoft.office.server.userprofiles"
0x78483e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784843  ldloc.0
0x784844  ldstr    aMicrosoftOffic_81// "microsoft.office.server.activitycache"
0x784849  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78484e  ldloc.0
0x78484f  ldstr    aMicrosoftOffic_82// "microsoft.office.server.microblog"
0x784854  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784859  ldloc.0
0x78485a  ldstr    aMicrosoftOffic_83// "microsoft.office.server.activityfeed"
0x78485f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784864  ldloc.0
0x784865  ldstr    aMicrosoftOffic_84// "microsoft.office.server.userprofiles.ca"...
0x78486a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78486f  ldloc.0
0x784870  ldstr    aMicrosoftOffic_85// "microsoft.office.server.audience"
0x784875  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78487a  ldloc.0
0x78487b  ldstr    aMicrosoftOffic_86// "microsoft.office.server.socialdata"
0x784880  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784885  ldloc.0
0x784886  ldstr    aMicrosoftOffic_87// "microsoft.office.server.userprofiles.cl"...
0x78488b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784890  ldloc.0
0x784891  ldstr    aMicrosoftOffic_88// "microsoft.office.server.webcontrols.use"...
0x784896  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78489b  ldloc.0
0x78489c  ldstr    aMicrosoftOffic_89// "microsoft.office.server.webcontrols.fie"...
0x7848a1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7848a6  ldloc.0
0x7848a7  ldstr    aMicrosoftOffic_90// "microsoft.office.server.userprofiles.po"...
0x7848ac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7848b1  ldloc.0
0x7848b2  ldstr    aMicrosoftOffic_91// "microsoft.office.server.userprofiles.sy"...
0x7848b7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7848bc  ldloc.0
0x7848bd  ldstr    aBihconsumerint// "bihconsumerinterop"
0x7848c2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7848c7  ldloc.0
0x7848c8  ldstr    aFastserializat// "fastserialization"
0x7848cd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7848d2  ldloc.0
0x7848d3  ldstr    aMicrosoftOffic_92// "microsoft.office.server.search"
0x7848d8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7848dd  ldloc.0
0x7848de  ldstr    aMicrosoftOffic_93// "microsoft.office.server.search.administ"...
0x7848e3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7848e8  ldloc.0
0x7848e9  ldstr    aMicrosoftOffic_94// "microsoft.office.server.search.administ"...
0x7848ee  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7848f3  ldloc.0
0x7848f4  ldstr    aMicrosoftOffic_95// "microsoft.office.server.search.administ"...
0x7848f9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7848fe  ldloc.0
0x7848ff  ldstr    aMicrosoftOffic_96// "microsoft.office.server.search.administ"...
0x784904  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784909  ldloc.0
0x78490a  ldstr    aMicrosoftOffic_97// "microsoft.office.server.search.administ"...
0x78490f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784914  ldloc.0
0x784915  ldstr    aMicrosoftOffic_98// "microsoft.office.server.search.administ"...
0x78491a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78491f  ldloc.0
0x784920  ldstr    aMicrosoftOffic_99// "microsoft.office.server.search.administ"...
0x784925  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78492a  ldloc.0
0x78492b  ldstr    aMicrosoftOffic_100// "microsoft.office.server.search.cmdlet"
0x784930  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784935  ldloc.0
0x784936  ldstr    aMicrosoftOffic_101// "microsoft.office.server.search.extended"...
0x78493b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784940  ldloc.0
0x784941  ldstr    aMicrosoftOffic_102// "microsoft.office.server.search.extended"...
0x784946  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78494b  ldloc.0
0x78494c  ldstr    aMicrosoftOffic_103// "microsoft.office.server.search.extended"...
0x784951  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784956  ldloc.0
0x784957  ldstr    aMicrosoftOffic_104// "microsoft.office.server.search.internal"
0x78495c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784961  ldloc.0
0x784962  ldstr    aMicrosoftOffic_105// "microsoft.office.server.search.internal"...
0x784967  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78496c  ldloc.0
0x78496d  ldstr    aMicrosoftOffic_106// "microsoft.office.server.search.internal"...
0x784972  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784977  ldloc.0
0x784978  ldstr    aMicrosoftOffic_107// "microsoft.office.server.search.internal"...
0x78497d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784982  ldloc.0
0x784983  ldstr    aMicrosoftOffic_108// "microsoft.office.server.search.internal"...
0x784988  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x78498d  ldloc.0
0x78498e  ldstr    aMicrosoftOffic_109// "microsoft.office.server.search.internal"...
0x784993  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784998  ldloc.0
0x784999  ldstr    aMicrosoftOffic_110// "microsoft.office.server.search.internal"...
0x78499e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7849a3  ldloc.0
0x7849a4  ldstr    aMicrosoftOffic_111// "microsoft.office.server.search.internal"...
0x7849a9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7849ae  ldloc.0
0x7849af  ldstr    aMicrosoftOffic_112// "microsoft.office.server.search.internal"...
0x7849b4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7849b9  ldloc.0
0x7849ba  ldstr    aMicrosoftOffic_113// "microsoft.office.server.search.internal"...
0x7849bf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7849c4  ldloc.0
0x7849c5  ldstr    aMicrosoftOffic_114// "microsoft.office.server.search.mobileco"...
0x7849ca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7849cf  ldloc.0
0x7849d0  ldstr    aMicrosoftOffic_115// "microsoft.office.server.search.monitori"...
0x7849d5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7849da  ldloc.0
0x7849db  ldstr    aMicrosoftOffic_116// "microsoft.office.server.search.query"
0x7849e0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7849e5  ldloc.0
0x7849e6  ldstr    aMicrosoftOffic_117// "microsoft.office.server.search.query.co"...
0x7849eb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7849f0  ldloc.0
0x7849f1  ldstr    aMicrosoftOffic_118// "microsoft.office.server.search.query.ga"...
0x7849f6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7849fb  ldloc.0
0x7849fc  ldstr    aMicrosoftOffic_119// "microsoft.office.server.search.query.la"...
0x784a01  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784a06  ldloc.0
0x784a07  ldstr    aMicrosoftOffic_120// "microsoft.office.server.search.upgrade"
0x784a0c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784a11  ldloc.0
0x784a12  ldstr    aMicrosoftOffic_121// "microsoft.office.server.search.webcontr"...
0x784a17  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784a1c  ldloc.0
0x784a1d  ldstr    aMicrosoftSearc// "microsoft.search"
0x784a22  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x784a27  ldloc.0
  ... truncated ...
```
