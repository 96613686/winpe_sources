# Microsoft.ReportingServices.Diagnostics.RSConfiguration::.cctor

- ea: `0x6da0`
- end: `0x6e82`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::.cctor`
- size: `226`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x6e13`: `Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException`
- `0x6e1f`: `Microsoft.ReportingServices.Modeling.InternalModelingException`
- `0x6e2b`: `Microsoft.ReportingServices.Diagnostics.Utilities.InternalRepublishingException`
- `0x6e41`: `System.Threading.ThreadAbortException`

## pseudocode

```c

```

## disassembly

```asm
0x6da0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0x6da5  dup
0x6da6  ldstr    aInfonav// "InfoNav"
0x6dab  ldc.i4   0x7D000
0x6db0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6db5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.ReportingServices.Diagnostics.RSConfiguration::_DefaultPvApplicationQueryMemoryLimits
0x6dba  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0x6dbf  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.ReportingServices.Diagnostics.RSConfiguration::_DefaultPVApplicationQueryTimeoutInternal
0x6dc4  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0x6dc9  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.ReportingServices.Diagnostics.RSConfiguration::_DefaultPVApplicationQueryTimeoutExternal
0x6dce  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.Uri>::.ctor()
0x6dd3  dup
0x6dd4  ldstr    aHttpSampleimag// "http://sampleimages.blob.core.windows.n"...
0x6dd9  newobj   instance void [System]System.Uri::.ctor(string)
0x6dde  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.Uri>::Add(var<u1>)
0x6de3  stsfld   class [mscorlib]System.Collections.Generic.List`1<class [System]System.Uri> Microsoft.ReportingServices.Diagnostics.RSConfiguration::_DefaultAllowedExternalImageDomains
0x6de8  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::.ctor()
0x6ded  dup
0x6dee  ldstr    aSspa// "SSPA"
0x6df3  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0x6df8  dup
0x6df9  ldstr    aFfffffffFfffFf// "ffffffff-ffff-ffff-ffff-ffffffffffff"
0x6dfe  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0x6e03  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::Add(var<u1>, !!T0)
0x6e08  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.ReportingServices.Diagnostics.RSConfiguration::_DefaultAllowedTenantsPerApplication
0x6e0d  newobj   instance void [System]System.Collections.Specialized.StringCollection::.ctor()
0x6e12  dup
0x6e13  ldstr    aMicrosoftRepor// "Microsoft.ReportingServices.Diagnostics"...
0x6e18  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x6e1d  pop
0x6e1e  dup
0x6e1f  ldstr    aMicrosoftRepor_0// "Microsoft.ReportingServices.Modeling.In"...
0x6e24  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x6e29  pop
0x6e2a  dup
0x6e2b  ldstr    aMicrosoftRepor_1// "Microsoft.ReportingServices.Diagnostics"...
0x6e30  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x6e35  pop
0x6e36  stsfld   class [System]System.Collections.Specialized.StringCollection Microsoft.ReportingServices.Diagnostics.RSConfiguration::_DefaultWatsonDumpOnExceptions
0x6e3b  newobj   instance void [System]System.Collections.Specialized.StringCollection::.ctor()
0x6e40  dup
0x6e41  ldstr    aSystemThreadin// "System.Threading.ThreadAbortException"
0x6e46  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x6e4b  pop
0x6e4c  dup
0x6e4d  ldstr    aSystemWebUiVie// "System.Web.UI.ViewStateException"
0x6e52  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x6e57  pop
0x6e58  dup
0x6e59  ldstr    aSystemOutofmem// "System.OutOfMemoryException"
0x6e5e  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x6e63  pop
0x6e64  dup
0x6e65  ldstr    aSystemWebHttpe// "System.Web.HttpException"
0x6e6a  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x6e6f  pop
0x6e70  stsfld   class [System]System.Collections.Specialized.StringCollection Microsoft.ReportingServices.Diagnostics.RSConfiguration::_DefaultWatsonDumpExcludeIfContainsExceptions
0x6e75  ldnull
0x6e76  stsfld   string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_ProductVersion
0x6e7b  ldnull
0x6e7c  stsfld   string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_NativeProductVersion
0x6e81  ret
```
