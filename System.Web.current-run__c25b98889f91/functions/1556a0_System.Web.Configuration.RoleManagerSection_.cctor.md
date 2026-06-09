# System.Web.Configuration.RoleManagerSection::.cctor

- ea: `0x1556a0`
- end: `0x155933`
- name: `System.Web.Configuration.RoleManagerSection::.cctor`
- size: `659`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x158490`
- `0x1584f0`
- `0x158550`
- `0x158570`

## string_xrefs

- `0x155844`: `maxCachedResults`
- `0x155740`: `cookiePath`
- `0x1556c0`: `cacheRolesInCookie`
- `0x155809`: `createPersistentCookie`

## pseudocode

```c

```

## disassembly

```asm
0x1556a0  ldstr    aEnabled_0// "enabled"
0x1556a5  ldtoken  [mscorlib]System.Boolean
0x1556aa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1556af  ldc.i4.0
0x1556b0  box      [mscorlib]System.Boolean
0x1556b5  ldc.i4.0
0x1556b6  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x1556bb  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propEnabled
0x1556c0  ldstr    aCacherolesinco// "cacheRolesInCookie"
0x1556c5  ldtoken  [mscorlib]System.Boolean
0x1556ca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1556cf  ldc.i4.0
0x1556d0  box      [mscorlib]System.Boolean
0x1556d5  ldc.i4.0
0x1556d6  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x1556db  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propUseCookies
0x1556e0  ldstr    aCookiename_0// "cookieName"
0x1556e5  ldtoken  [mscorlib]System.String
0x1556ea  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1556ef  ldstr    aAspxroles// ".ASPXROLES"
0x1556f4  call     class [System]System.ComponentModel.TypeConverter System.Web.Configuration.StdValidatorsAndConverters::get_WhiteSpaceTrimStringConverter()
0x1556f9  call     class [System.Configuration]System.Configuration.ConfigurationValidatorBase System.Web.Configuration.StdValidatorsAndConverters::get_NonEmptyStringValidator()
0x1556fe  ldc.i4.0
0x1556ff  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, class [System]System.ComponentModel.TypeConverter, class [System.Configuration]System.Configuration.ConfigurationValidatorBase, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x155704  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propCookieName
0x155709  ldstr    aCookietimeout// "cookieTimeout"
0x15570e  ldtoken  [mscorlib]System.TimeSpan
0x155713  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x155718  ldc.r8   30.0
0x155721  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x155726  box      [mscorlib]System.TimeSpan
0x15572b  call     class [System]System.ComponentModel.TypeConverter System.Web.Configuration.StdValidatorsAndConverters::get_TimeSpanMinutesOrInfiniteConverter()
0x155730  call     class [System.Configuration]System.Configuration.ConfigurationValidatorBase System.Web.Configuration.StdValidatorsAndConverters::get_PositiveTimeSpanValidator()
0x155735  ldc.i4.0
0x155736  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, class [System]System.ComponentModel.TypeConverter, class [System.Configuration]System.Configuration.ConfigurationValidatorBase, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x15573b  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propCookieTimeout
0x155740  ldstr    aCookiepath// "cookiePath"
0x155745  ldtoken  [mscorlib]System.String
0x15574a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15574f  ldstr    asc_1B2C3C// "/"
0x155754  call     class [System]System.ComponentModel.TypeConverter System.Web.Configuration.StdValidatorsAndConverters::get_WhiteSpaceTrimStringConverter()
0x155759  call     class [System.Configuration]System.Configuration.ConfigurationValidatorBase System.Web.Configuration.StdValidatorsAndConverters::get_NonEmptyStringValidator()
0x15575e  ldc.i4.0
0x15575f  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, class [System]System.ComponentModel.TypeConverter, class [System.Configuration]System.Configuration.ConfigurationValidatorBase, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x155764  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propCookiePath
0x155769  ldstr    aCookierequires// "cookieRequireSSL"
0x15576e  ldtoken  [mscorlib]System.Boolean
0x155773  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x155778  ldc.i4.0
0x155779  box      [mscorlib]System.Boolean
0x15577e  ldc.i4.0
0x15577f  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x155784  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propCookieRequireSSL
0x155789  ldstr    aCookieslidinge// "cookieSlidingExpiration"
0x15578e  ldtoken  [mscorlib]System.Boolean
0x155793  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x155798  ldc.i4.1
0x155799  box      [mscorlib]System.Boolean
0x15579e  ldc.i4.0
0x15579f  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x1557a4  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propCookieSlidingExpiration
0x1557a9  ldstr    aCookieprotecti// "cookieProtection"
0x1557ae  ldtoken  System.Web.Security.CookieProtection
0x1557b3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1557b8  ldc.i4.3
0x1557b9  box      System.Web.Security.CookieProtection
0x1557be  ldc.i4.0
0x1557bf  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x1557c4  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propCookieProtection
0x1557c9  ldstr    aDefaultprovide// "defaultProvider"
0x1557ce  ldtoken  [mscorlib]System.String
0x1557d3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1557d8  ldstr    aAspnetsqlrolep// "AspNetSqlRoleProvider"
0x1557dd  ldnull
0x1557de  call     class [System.Configuration]System.Configuration.ConfigurationValidatorBase System.Web.Configuration.StdValidatorsAndConverters::get_NonEmptyStringValidator()
0x1557e3  ldc.i4.0
0x1557e4  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, class [System]System.ComponentModel.TypeConverter, class [System.Configuration]System.Configuration.ConfigurationValidatorBase, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x1557e9  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propDefaultProvider
0x1557ee  ldstr    aProviders// "providers"
0x1557f3  ldtoken  [System.Configuration]System.Configuration.ProviderSettingsCollection
0x1557f8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1557fd  ldnull
0x1557fe  ldc.i4.0
0x1557ff  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x155804  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propProviders
0x155809  ldstr    aCreatepersiste// "createPersistentCookie"
0x15580e  ldtoken  [mscorlib]System.Boolean
0x155813  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x155818  ldc.i4.0
0x155819  box      [mscorlib]System.Boolean
0x15581e  ldc.i4.0
0x15581f  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x155824  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propCreatePersistentCookie
0x155829  ldstr    aDomain_2// "domain"
0x15582e  ldtoken  [mscorlib]System.String
0x155833  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x155838  ldnull
0x155839  ldc.i4.0
0x15583a  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x15583f  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propDomain
0x155844  ldstr    aMaxcachedresul// "maxCachedResults"
0x155849  ldtoken  [mscorlib]System.Int32
0x15584e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x155853  ldc.i4.s 0x19
0x155855  box      [mscorlib]System.Int32
0x15585a  ldc.i4.0
0x15585b  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x155860  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propMaxCachedResults
0x155865  newobj   instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::.ctor()
0x15586a  stsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.RoleManagerSection::_properties
0x15586f  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.RoleManagerSection::_properties
0x155874  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propEnabled
0x155879  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x15587e  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.RoleManagerSection::_properties
0x155883  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propUseCookies
0x155888  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x15588d  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.RoleManagerSection::_properties
0x155892  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propCookieName
0x155897  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x15589c  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.RoleManagerSection::_properties
0x1558a1  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propCookieTimeout
0x1558a6  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x1558ab  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.RoleManagerSection::_properties
0x1558b0  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propCookiePath
0x1558b5  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x1558ba  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.RoleManagerSection::_properties
0x1558bf  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propCookieRequireSSL
0x1558c4  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x1558c9  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.RoleManagerSection::_properties
0x1558ce  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propCookieSlidingExpiration
0x1558d3  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x1558d8  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.RoleManagerSection::_properties
0x1558dd  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propCookieProtection
0x1558e2  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x1558e7  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.RoleManagerSection::_properties
0x1558ec  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propDefaultProvider
0x1558f1  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x1558f6  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.RoleManagerSection::_properties
0x1558fb  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propProviders
0x155900  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x155905  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.RoleManagerSection::_properties
0x15590a  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propCreatePersistentCookie
0x15590f  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x155914  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.RoleManagerSection::_properties
0x155919  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propDomain
0x15591e  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x155923  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.RoleManagerSection::_properties
0x155928  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.RoleManagerSection::_propMaxCachedResults
0x15592d  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x155932  ret
```
