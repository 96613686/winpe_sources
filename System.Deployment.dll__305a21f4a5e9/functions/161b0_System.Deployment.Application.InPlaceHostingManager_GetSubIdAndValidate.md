# System.Deployment.Application.InPlaceHostingManager::GetSubIdAndValidate

- ea: `0x161b0`
- end: `0x162e9`
- name: `System.Deployment.Application.InPlaceHostingManager::GetSubIdAndValidate`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x16030`
- `0x16060`

## callees

- `0xd930`
- `0xda60`
- `0xda80`
- `0xdaa0`
- `0xdab0`
- `0x161b0`
- `0x23020`

## string_xrefs

- `0x161b8`: `Ex_ComArgSubIdentityNull`
- `0x161d9`: `Ex_ComArgSubIdentityNotValid`
- `0x161ff`: `Ex_ComArgSubIdentityNotValid`
- `0x16225`: `Ex_ComArgSubIdentityNotValid`
- `0x16252`: `Ex_ComArgSubIdentityNotValid`
- `0x1627e`: `Ex_ComArgSubIdentityNotValid`
- `0x162aa`: `Ex_ComArgSubIdentityNotValid`
- `0x162d7`: `Ex_ComArgSubIdentityWithVersion`

## pseudocode

```c

```

## disassembly

```asm
0x161b0  ldarg.0
0x161b1  brtrue.s loc_161C8
0x161b3  ldstr    aSubscriptionid// "subscriptionId"
0x161b8  ldstr    aExComargsubide// "Ex_ComArgSubIdentityNull"
0x161bd  call     string System.Deployment.Application.Resources::GetString(string s)
0x161c2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x161c7  throw
0x161c8  ldnull
0x161c9  stloc.0
0x161ca  ldarg.0
0x161cb  newobj   instance void System.Deployment.Application.DefinitionIdentity::.ctor(string text)
0x161d0  stloc.0
0x161d1  leave.s  loc_16245
0x161d3  stloc.1
0x161d4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x161d9  ldstr    aExComargsubide_0// "Ex_ComArgSubIdentityNotValid"
0x161de  call     string System.Deployment.Application.Resources::GetString(string s)
0x161e3  ldc.i4.1
0x161e4  newarr   [mscorlib]System.Object
0x161e9  dup
0x161ea  ldc.i4.0
0x161eb  ldarg.0
0x161ec  stelem.ref
0x161ed  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x161f2  ldloc.1
0x161f3  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, class [mscorlib]System.Exception)
0x161f8  throw
0x161f9  stloc.2
0x161fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x161ff  ldstr    aExComargsubide_0// "Ex_ComArgSubIdentityNotValid"
0x16204  call     string System.Deployment.Application.Resources::GetString(string s)
0x16209  ldc.i4.1
0x1620a  newarr   [mscorlib]System.Object
0x1620f  dup
0x16210  ldc.i4.0
0x16211  ldarg.0
0x16212  stelem.ref
0x16213  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16218  ldloc.2
0x16219  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, class [mscorlib]System.Exception)
0x1621e  throw
0x1621f  stloc.3
0x16220  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x16225  ldstr    aExComargsubide_0// "Ex_ComArgSubIdentityNotValid"
0x1622a  call     string System.Deployment.Application.Resources::GetString(string s)
0x1622f  ldc.i4.1
0x16230  newarr   [mscorlib]System.Object
0x16235  dup
0x16236  ldc.i4.0
0x16237  ldarg.0
0x16238  stelem.ref
0x16239  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1623e  ldloc.3
0x1623f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, class [mscorlib]System.Exception)
0x16244  throw
0x16245  ldloc.0
0x16246  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_Name()
0x1624b  brtrue.s loc_16271
0x1624d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x16252  ldstr    aExComargsubide_0// "Ex_ComArgSubIdentityNotValid"
0x16257  call     string System.Deployment.Application.Resources::GetString(string s)
0x1625c  ldc.i4.1
0x1625d  newarr   [mscorlib]System.Object
0x16262  dup
0x16263  ldc.i4.0
0x16264  ldarg.0
0x16265  stelem.ref
0x16266  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1626b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x16270  throw
0x16271  ldloc.0
0x16272  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_PublicKeyToken()
0x16277  brtrue.s loc_1629D
0x16279  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x1627e  ldstr    aExComargsubide_0// "Ex_ComArgSubIdentityNotValid"
0x16283  call     string System.Deployment.Application.Resources::GetString(string s)
0x16288  ldc.i4.1
0x16289  newarr   [mscorlib]System.Object
0x1628e  dup
0x1628f  ldc.i4.0
0x16290  ldarg.0
0x16291  stelem.ref
0x16292  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16297  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1629c  throw
0x1629d  ldloc.0
0x1629e  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_ProcessorArchitecture()
0x162a3  brtrue.s loc_162C9
0x162a5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x162aa  ldstr    aExComargsubide_0// "Ex_ComArgSubIdentityNotValid"
0x162af  call     string System.Deployment.Application.Resources::GetString(string s)
0x162b4  ldc.i4.1
0x162b5  newarr   [mscorlib]System.Object
0x162ba  dup
0x162bb  ldc.i4.0
0x162bc  ldarg.0
0x162bd  stelem.ref
0x162be  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x162c3  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x162c8  throw
0x162c9  ldloc.0
0x162ca  callvirt instance class [mscorlib]System.Version System.Deployment.Application.DefinitionIdentity::get_Version()
0x162cf  ldnull
0x162d0  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x162d5  brfalse.s loc_162E7
0x162d7  ldstr    aExComargsubide_1// "Ex_ComArgSubIdentityWithVersion"
0x162dc  call     string System.Deployment.Application.Resources::GetString(string s)
0x162e1  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x162e6  throw
0x162e7  ldloc.0
0x162e8  ret
```
