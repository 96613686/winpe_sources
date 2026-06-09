# Microsoft.VisualStudio.Setup.Serialization.CatalogConverter::ReadJson

- ea: `0xd760`
- end: `0xd9e9`
- name: `Microsoft.VisualStudio.Setup.Serialization.CatalogConverter::ReadJson`
- size: `649`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x2780`
- `0x2790`
- `0x27b0`
- `0x2a40`
- `0xd760`
- `0xda00`
- `0x10370`

## string_xrefs

- `0xd76d`: `ManifestVersion`
- `0xd9ad`: `' is not supported in an installer manifest`
- `0xd9d6`: `Invalid manifest: signers must be read before packages.`

## pseudocode

```c

```

## disassembly

```asm
0xd760  ldarg.1
0xd761  ldloca.s 0
0xd763  call     bool Microsoft.VisualStudio.Setup.Serialization.CatalogConverter::TryReadPropertyName(class [Newtonsoft.Json]Newtonsoft.Json.JsonReader reader, [out] string& propertyName)
0xd768  brfalse  loc_D9E3
0xd76d  ldstr    aManifestversio// "ManifestVersion"
0xd772  ldloc.0
0xd773  ldc.i4.5
0xd774  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xd779  brfalse  loc_D9E3
0xd77e  ldarg.1
0xd77f  callvirt instance string [Newtonsoft.Json]Newtonsoft.Json.JsonReader::ReadAsString()
0xd784  ldloca.s 1
0xd786  call     bool [mscorlib]System.Version::TryParse(string, class [mscorlib]System.Version&)
0xd78b  brfalse  loc_D9E3
0xd790  ldloc.1
0xd791  ldnull
0xd792  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xd797  brfalse  loc_D9E3
0xd79c  ldloc.1
0xd79d  ldsfld   class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Catalog::CurrentVersion
0xd7a2  call     bool [mscorlib]System.Version::op_LessThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xd7a7  brfalse  loc_D9E3
0xd7ac  ldarg.s  4
0xd7ae  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.JsonConverterCollection [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::get_Converters()
0xd7b3  ldarg.0
0xd7b4  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Serialization.CatalogConverter::services
0xd7b9  newobj   instance void Microsoft.VisualStudio.Setup.Serialization.PackageConverter::.ctor(class [mscorlib]System.IServiceProvider services)
0xd7be  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Newtonsoft.Json]Newtonsoft.Json.JsonConverter>::Add(var<u1>)
0xd7c3  newobj   instance void Microsoft.VisualStudio.Setup.Catalog::.ctor()
0xd7c8  dup
0xd7c9  ldloc.1
0xd7ca  callvirt instance void class Microsoft.VisualStudio.Setup.Manifest`1<class Microsoft.VisualStudio.Setup.IPackage>::set_ManifestVersion(class [mscorlib]System.Version)
0xd7cf  stloc.2
0xd7d0  ldc.i4.0
0xd7d1  stloc.3
0xd7d2  ldc.i4.0
0xd7d3  stloc.s  4
0xd7d5  br       loc_D9C3
0xd7da  ldstr    aSigners// "Signers"
0xd7df  ldloc.0
0xd7e0  ldc.i4.5
0xd7e1  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xd7e6  brfalse.s loc_D813
0xd7e8  ldc.i4.1
0xd7e9  stloc.3
0xd7ea  ldarg.1
0xd7eb  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xd7f0  pop
0xd7f1  ldloc.2
0xd7f2  ldarg.s  4
0xd7f4  ldarg.1
0xd7f5  callvirt T0x2B000058
0xd7fa  dup
0xd7fb  brtrue.s loc_D809
0xd7fd  pop
0xd7fe  ldstr    aExpectedNonNul_0// "Expected non-null 'Signers' when deseri"...
0xd803  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xd808  throw
0xd809  callvirt instance void class Microsoft.VisualStudio.Setup.Manifest`1<class Microsoft.VisualStudio.Setup.IPackage>::set_Signers(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Signer>)
0xd80e  br       loc_D9C3
0xd813  ldstr    aPackages// "Packages"
0xd818  ldloc.0
0xd819  ldc.i4.5
0xd81a  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xd81f  brfalse.s loc_D855
0xd821  ldloc.3
0xd822  brtrue.s loc_D827
0xd824  ldc.i4.1
0xd825  stloc.s  4
0xd827  ldarg.1
0xd828  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xd82d  pop
0xd82e  ldloc.2
0xd82f  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.Catalog::get_Packages()
0xd834  ldarg.s  4
0xd836  ldarg.1
0xd837  callvirt T0x2B000059
0xd83c  dup
0xd83d  brtrue.s loc_D84B
0xd83f  pop
0xd840  ldstr    aExpectedNonNul_1// "Expected non-null 'Packages' when deser"...
0xd845  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xd84a  throw
0xd84b  call     T0x2B00005A
0xd850  br       loc_D9C3
0xd855  ldstr    aDeprecate// "Deprecate"
0xd85a  ldloc.0
0xd85b  ldc.i4.5
0xd85c  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xd861  brfalse.s loc_D88C
0xd863  ldarg.1
0xd864  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xd869  pop
0xd86a  ldloc.2
0xd86b  ldarg.s  4
0xd86d  ldarg.1
0xd86e  callvirt T0x2B00005B
0xd873  dup
0xd874  brtrue.s loc_D882
0xd876  pop
0xd877  ldstr    aExpectedNonNul_2// "Expected non-null 'Deprecate' when dese"...
0xd87c  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xd881  throw
0xd882  callvirt instance void Microsoft.VisualStudio.Setup.Catalog::set_Deprecate(class Microsoft.VisualStudio.Setup.DependencyCollection value)
0xd887  br       loc_D9C3
0xd88c  ldstr    aEngineversion// "EngineVersion"
0xd891  ldloc.0
0xd892  ldc.i4.5
0xd893  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xd898  brfalse.s loc_D8C3
0xd89a  ldarg.1
0xd89b  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xd8a0  pop
0xd8a1  ldloc.2
0xd8a2  ldarg.s  4
0xd8a4  ldarg.1
0xd8a5  callvirt T0x2B00005C
0xd8aa  dup
0xd8ab  brtrue.s loc_D8B9
0xd8ad  pop
0xd8ae  ldstr    aExpectedNonNul_3// "Expected non-null 'EngineVersion' when "...
0xd8b3  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xd8b8  throw
0xd8b9  callvirt instance void class Microsoft.VisualStudio.Setup.Manifest`1<class Microsoft.VisualStudio.Setup.IPackage>::set_EngineVersion(class [mscorlib]System.Version)
0xd8be  br       loc_D9C3
0xd8c3  ldstr    aInfo_0// "Info"
0xd8c8  ldloc.0
0xd8c9  ldc.i4.5
0xd8ca  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xd8cf  brfalse.s loc_D8FA
0xd8d1  ldarg.1
0xd8d2  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xd8d7  pop
0xd8d8  ldloc.2
0xd8d9  ldarg.s  4
0xd8db  ldarg.1
0xd8dc  callvirt T0x2B00005D
0xd8e1  dup
0xd8e2  brtrue.s loc_D8F0
0xd8e4  pop
0xd8e5  ldstr    aExpectedNonNul_4// "Expected non-null 'Info' when deseriali"...
0xd8ea  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xd8ef  throw
0xd8f0  callvirt instance void class Microsoft.VisualStudio.Setup.Manifest`1<class Microsoft.VisualStudio.Setup.IPackage>::set_Info(class Microsoft.VisualStudio.Setup.CatalogInfo)
0xd8f5  br       loc_D9C3
0xd8fa  ldstr    aBuildinfo// "_buildInfo"
0xd8ff  ldloc.0
0xd900  ldc.i4.5
0xd901  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xd906  brfalse.s loc_D931
0xd908  ldarg.1
0xd909  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xd90e  pop
0xd90f  ldloc.2
0xd910  ldarg.s  4
0xd912  ldarg.1
0xd913  callvirt T0x2B00005E
0xd918  dup
0xd919  brtrue.s loc_D927
0xd91b  pop
0xd91c  ldstr    aExpectedNonNul_5// "Expected non-null '_buildInfo' when des"...
0xd921  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xd926  throw
0xd927  callvirt instance void class Microsoft.VisualStudio.Setup.Manifest`1<class Microsoft.VisualStudio.Setup.IPackage>::set_BuildInformation(class Microsoft.VisualStudio.Setup.CatalogBuildInformation)
0xd92c  br       loc_D9C3
0xd931  ldstr    aSignature// "Signature"
0xd936  ldloc.0
0xd937  ldc.i4.5
0xd938  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xd93d  brfalse.s loc_D965
0xd93f  ldarg.1
0xd940  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xd945  pop
0xd946  ldloc.2
0xd947  ldarg.s  4
0xd949  ldarg.1
0xd94a  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Deserialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonReader)
0xd94f  dup
0xd950  brtrue.s loc_D95E
0xd952  pop
0xd953  ldstr    aExpectedNonNul_6// "Expected non-null 'Signature' when dese"...
0xd958  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xd95d  throw
0xd95e  callvirt instance void class Microsoft.VisualStudio.Setup.Manifest`1<class Microsoft.VisualStudio.Setup.IPackage>::set_Signature(object)
0xd963  br.s     loc_D9C3
0xd965  ldstr    aAppliesto// "AppliesTo"
0xd96a  ldloc.0
0xd96b  ldc.i4.5
0xd96c  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xd971  brfalse.s loc_D999
0xd973  ldarg.1
0xd974  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xd979  pop
0xd97a  ldloc.2
0xd97b  ldarg.s  4
0xd97d  ldarg.1
0xd97e  callvirt T0x2B00005F
0xd983  dup
0xd984  brtrue.s loc_D992
0xd986  pop
0xd987  ldstr    aExpectedNonNul_7// "Expected non-null 'AppliesTo' when dese"...
0xd98c  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xd991  throw
0xd992  callvirt instance void Microsoft.VisualStudio.Setup.Catalog::set_AppliesTo(class Microsoft.VisualStudio.Setup.AppliesToCollection value)
0xd997  br.s     loc_D9C3
0xd999  ldstr    aChannelitems// "ChannelItems"
0xd99e  ldloc.0
0xd99f  ldc.i4.5
0xd9a0  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xd9a5  brfalse.s loc_D9BD
0xd9a7  ldstr    asc_212B8// "'"
0xd9ac  ldloc.0
0xd9ad  ldstr    aIsNotSupported// "' is not supported in an installer mani"...
0xd9b2  call     string [mscorlib]System.String::Concat(string, string, string)
0xd9b7  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xd9bc  throw
0xd9bd  ldarg.1
0xd9be  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Skip()
0xd9c3  ldarg.1
0xd9c4  ldloca.s 0
0xd9c6  call     bool Microsoft.VisualStudio.Setup.Serialization.CatalogConverter::TryReadPropertyName(class [Newtonsoft.Json]Newtonsoft.Json.JsonReader reader, [out] string& propertyName)
0xd9cb  brtrue   loc_D7DA
0xd9d0  ldloc.3
0xd9d1  ldloc.s  4
0xd9d3  and
0xd9d4  brfalse.s loc_D9E1
0xd9d6  ldstr    aInvalidManifes// "Invalid manifest: signers must be read "...
0xd9db  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xd9e0  throw
0xd9e1  ldloc.2
0xd9e2  ret
0xd9e3  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0xd9e8  throw
```
