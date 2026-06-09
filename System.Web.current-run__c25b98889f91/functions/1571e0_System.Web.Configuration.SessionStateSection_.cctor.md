# System.Web.Configuration.SessionStateSection::.cctor

- ea: `0x1571e0`
- end: `0x1575c9`
- name: `System.Web.Configuration.SessionStateSection::.cctor`
- size: `1001`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180c0`
- `0x158490`
- `0x1584d0`
- `0x158550`

## string_xrefs

- `0x15728a`: `data source=localhost;Integrated Security=SSPI`
- `0x15729a`: `sqlCommandTimeout`
- `0x1573d1`: `compressionEnabled`

## pseudocode

```c

```

## disassembly

```asm
0x1571e0  ldtoken  System.Web.Configuration.SessionStateSection
0x1571e5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1571ea  ldnull
0x1571eb  ldftn    void System.Web.Configuration.SessionStateSection::Validate(object value)
0x1571f1  newobj   instance void [System.Configuration]System.Configuration.ValidatorCallback::.ctor(object, native int)
0x1571f6  newobj   instance void [System.Configuration]System.Configuration.CallbackValidator::.ctor(class [mscorlib]System.Type, class [System.Configuration]System.Configuration.ValidatorCallback)
0x1571fb  newobj   instance void [System.Configuration]System.Configuration.ConfigurationElementProperty::.ctor(class [System.Configuration]System.Configuration.ConfigurationValidatorBase)
0x157200  stsfld   class [System.Configuration]System.Configuration.ConfigurationElementProperty System.Web.Configuration.SessionStateSection::s_elemProperty
0x157205  ldstr    aMode// "mode"
0x15720a  ldtoken  System.Web.SessionState.SessionStateMode
0x15720f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x157214  ldc.i4.1
0x157215  box      System.Web.SessionState.SessionStateMode
0x15721a  ldc.i4.0
0x15721b  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x157220  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propMode
0x157225  ldstr    aStateconnectio// "stateConnectionString"
0x15722a  ldtoken  [mscorlib]System.String
0x15722f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x157234  ldstr    aTcpipLoopback4// "tcpip=loopback:42424"
0x157239  ldc.i4.0
0x15723a  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x15723f  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propStateConnectionString
0x157244  ldstr    aStatenetworkti// "stateNetworkTimeout"
0x157249  ldtoken  [mscorlib]System.TimeSpan
0x15724e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x157253  ldc.r8   10.0
0x15725c  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x157261  box      [mscorlib]System.TimeSpan
0x157266  call     class [System]System.ComponentModel.TypeConverter System.Web.Configuration.StdValidatorsAndConverters::get_TimeSpanSecondsOrInfiniteConverter()
0x15726b  call     class [System.Configuration]System.Configuration.ConfigurationValidatorBase System.Web.Configuration.StdValidatorsAndConverters::get_PositiveTimeSpanValidator()
0x157270  ldc.i4.0
0x157271  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, class [System]System.ComponentModel.TypeConverter, class [System.Configuration]System.Configuration.ConfigurationValidatorBase, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x157276  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propStateNetworkTimeout
0x15727b  ldstr    aSqlconnections// "sqlConnectionString"
0x157280  ldtoken  [mscorlib]System.String
0x157285  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15728a  ldstr    aDataSourceLoca// "data source=localhost;Integrated Securi"...
0x15728f  ldc.i4.0
0x157290  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x157295  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propSqlConnectionString
0x15729a  ldstr    aSqlcommandtime// "sqlCommandTimeout"
0x15729f  ldtoken  [mscorlib]System.TimeSpan
0x1572a4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1572a9  ldc.r8   30.0
0x1572b2  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x1572b7  box      [mscorlib]System.TimeSpan
0x1572bc  call     class [System]System.ComponentModel.TypeConverter System.Web.Configuration.StdValidatorsAndConverters::get_TimeSpanSecondsOrInfiniteConverter()
0x1572c1  ldnull
0x1572c2  ldc.i4.0
0x1572c3  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, class [System]System.ComponentModel.TypeConverter, class [System.Configuration]System.Configuration.ConfigurationValidatorBase, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x1572c8  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propSqlCommandTimeout
0x1572cd  ldstr    aSqlconnectionr// "sqlConnectionRetryInterval"
0x1572d2  ldtoken  [mscorlib]System.TimeSpan
0x1572d7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1572dc  ldc.r8   0.0
0x1572e5  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x1572ea  box      [mscorlib]System.TimeSpan
0x1572ef  call     class [System]System.ComponentModel.TypeConverter System.Web.Configuration.StdValidatorsAndConverters::get_TimeSpanSecondsOrInfiniteConverter()
0x1572f4  ldnull
0x1572f5  ldc.i4.0
0x1572f6  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, class [System]System.ComponentModel.TypeConverter, class [System.Configuration]System.Configuration.ConfigurationValidatorBase, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x1572fb  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propSqlConnectionRetryInterval
0x157300  ldstr    aCustomprovider// "customProvider"
0x157305  ldtoken  [mscorlib]System.String
0x15730a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15730f  ldsfld   string [mscorlib]System.String::Empty
0x157314  ldc.i4.0
0x157315  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x15731a  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propCustomProvider
0x15731f  ldstr    aCookieless// "cookieless"
0x157324  ldtoken  [mscorlib]System.String
0x157329  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15732e  ldc.i4.1
0x15732f  stloc.0
0x157330  ldloca.s 0
0x157332  constrained. System.Web.HttpCookieMode
0x157338  callvirt instance string [mscorlib]System.Object::ToString()
0x15733d  ldc.i4.0
0x15733e  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x157343  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propCookieless
0x157348  ldstr    aCookiename_0// "cookieName"
0x15734d  ldtoken  [mscorlib]System.String
0x157352  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x157357  ldstr    aAspNetSessioni// "ASP.NET_SessionId"
0x15735c  ldc.i4.0
0x15735d  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x157362  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propCookieName
0x157367  ldstr    aTimeout_0// "timeout"
0x15736c  ldtoken  [mscorlib]System.TimeSpan
0x157371  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x157376  ldc.r8   20.0
0x15737f  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x157384  box      [mscorlib]System.TimeSpan
0x157389  call     class [System]System.ComponentModel.TypeConverter System.Web.Configuration.StdValidatorsAndConverters::get_TimeSpanMinutesOrInfiniteConverter()
0x15738e  ldc.r8   1.0
0x157397  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x15739c  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::MaxValue
0x1573a1  newobj   instance void [System.Configuration]System.Configuration.TimeSpanValidator::.ctor(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x1573a6  ldc.i4.0
0x1573a7  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, class [System]System.ComponentModel.TypeConverter, class [System.Configuration]System.Configuration.ConfigurationValidatorBase, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x1573ac  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propTimeout
0x1573b1  ldstr    aAllowcustomsql// "allowCustomSqlDatabase"
0x1573b6  ldtoken  [mscorlib]System.Boolean
0x1573bb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1573c0  ldc.i4.0
0x1573c1  box      [mscorlib]System.Boolean
0x1573c6  ldc.i4.0
0x1573c7  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x1573cc  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propAllowCustomSqlDatabase
0x1573d1  ldstr    aCompressionena// "compressionEnabled"
0x1573d6  ldtoken  [mscorlib]System.Boolean
0x1573db  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1573e0  ldc.i4.0
0x1573e1  box      [mscorlib]System.Boolean
0x1573e6  ldc.i4.0
0x1573e7  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x1573ec  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propCompressionEnabled
0x1573f1  ldstr    aProviders// "providers"
0x1573f6  ldtoken  [System.Configuration]System.Configuration.ProviderSettingsCollection
0x1573fb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x157400  ldnull
0x157401  ldc.i4.0
0x157402  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x157407  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propProviders
0x15740c  ldstr    aRegenerateexpi// "regenerateExpiredSessionId"
0x157411  ldtoken  [mscorlib]System.Boolean
0x157416  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15741b  ldc.i4.1
0x15741c  box      [mscorlib]System.Boolean
0x157421  ldc.i4.0
0x157422  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x157427  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propRegenerateExpiredSessionId
0x15742c  ldstr    aPartitionresol// "partitionResolverType"
0x157431  ldtoken  [mscorlib]System.String
0x157436  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15743b  ldsfld   string [mscorlib]System.String::Empty
0x157440  ldc.i4.0
0x157441  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x157446  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propPartitionResolverType
0x15744b  ldstr    aUsehostingiden// "useHostingIdentity"
0x157450  ldtoken  [mscorlib]System.Boolean
0x157455  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15745a  ldc.i4.1
0x15745b  box      [mscorlib]System.Boolean
0x157460  ldc.i4.0
0x157461  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x157466  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propUseHostingIdentity
0x15746b  ldstr    aSessionidmanag_1// "sessionIDManagerType"
0x157470  ldtoken  [mscorlib]System.String
0x157475  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15747a  ldsfld   string [mscorlib]System.String::Empty
0x15747f  ldc.i4.0
0x157480  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x157485  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propSessionIDManagerType
0x15748a  ldstr    aCookiesamesite// "cookieSameSite"
0x15748f  ldtoken  System.Web.SameSiteMode
0x157494  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x157499  ldc.i4.1
0x15749a  box      System.Web.SameSiteMode
0x15749f  newobj   instance void System.Web.SameSiteConverter::.ctor()
0x1574a4  ldnull
0x1574a5  ldc.i4.0
0x1574a6  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, class [System]System.ComponentModel.TypeConverter, class [System.Configuration]System.Configuration.ConfigurationValidatorBase, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x1574ab  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propCookieSameSite
0x1574b0  newobj   instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::.ctor()
0x1574b5  stsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x1574ba  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x1574bf  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propMode
0x1574c4  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x1574c9  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x1574ce  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propStateConnectionString
0x1574d3  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x1574d8  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x1574dd  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propStateNetworkTimeout
0x1574e2  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x1574e7  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x1574ec  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propSqlConnectionString
0x1574f1  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x1574f6  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x1574fb  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propSqlCommandTimeout
0x157500  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x157505  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x15750a  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propSqlConnectionRetryInterval
0x15750f  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x157514  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x157519  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propCustomProvider
0x15751e  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x157523  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x157528  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propCookieless
0x15752d  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x157532  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x157537  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propCookieName
0x15753c  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x157541  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x157546  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propTimeout
0x15754b  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x157550  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x157555  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propAllowCustomSqlDatabase
0x15755a  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x15755f  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x157564  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propCompressionEnabled
0x157569  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x15756e  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x157573  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propProviders
0x157578  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x15757d  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x157582  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propRegenerateExpiredSessionId
0x157587  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x15758c  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x157591  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propPartitionResolverType
0x157596  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x15759b  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x1575a0  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propUseHostingIdentity
0x1575a5  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x1575aa  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x1575af  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propSessionIDManagerType
0x1575b4  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x1575b9  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.SessionStateSection::_properties
0x1575be  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.SessionStateSection::_propCookieSameSite
0x1575c3  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x1575c8  ret
```
