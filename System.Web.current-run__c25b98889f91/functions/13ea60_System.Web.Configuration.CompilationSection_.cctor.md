# System.Web.Configuration.CompilationSection::.cctor

- ea: `0x13ea60`
- end: `0x13ef05`
- name: `System.Web.Configuration.CompilationSection::.cctor`
- size: `1189`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1584d0`
- `0x158550`

## string_xrefs

- `0x13ea60`: `tempDirectory`
- `0x13eaff`: `optimizeCompilations`
- `0x13eb9e`: `numRecompilesBeforeAppRestart`
- `0x13ebf9`: `compilers`
- `0x13ed59`: `maxConcurrentCompilations`

## pseudocode

```c

```

## disassembly

```asm
0x13ea60  ldstr    aTempdirectory// "tempDirectory"
0x13ea65  ldtoken  [mscorlib]System.String
0x13ea6a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ea6f  ldsfld   string [mscorlib]System.String::Empty
0x13ea74  ldc.i4.0
0x13ea75  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ea7a  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propTempDirectory
0x13ea7f  ldstr    aDebug_0// "debug"
0x13ea84  ldtoken  [mscorlib]System.Boolean
0x13ea89  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ea8e  ldc.i4.0
0x13ea8f  box      [mscorlib]System.Boolean
0x13ea94  ldc.i4.0
0x13ea95  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ea9a  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propDebug
0x13ea9f  ldstr    aStrict// "strict"
0x13eaa4  ldtoken  [mscorlib]System.Boolean
0x13eaa9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13eaae  ldc.i4.0
0x13eaaf  box      [mscorlib]System.Boolean
0x13eab4  ldc.i4.0
0x13eab5  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13eaba  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propStrict
0x13eabf  ldstr    aExplicit// "explicit"
0x13eac4  ldtoken  [mscorlib]System.Boolean
0x13eac9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13eace  ldc.i4.1
0x13eacf  box      [mscorlib]System.Boolean
0x13ead4  ldc.i4.0
0x13ead5  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13eada  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propExplicit
0x13eadf  ldstr    aBatch// "batch"
0x13eae4  ldtoken  [mscorlib]System.Boolean
0x13eae9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13eaee  ldc.i4.1
0x13eaef  box      [mscorlib]System.Boolean
0x13eaf4  ldc.i4.0
0x13eaf5  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13eafa  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propBatch
0x13eaff  ldstr    aOptimizecompil// "optimizeCompilations"
0x13eb04  ldtoken  [mscorlib]System.Boolean
0x13eb09  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13eb0e  ldc.i4.0
0x13eb0f  box      [mscorlib]System.Boolean
0x13eb14  ldc.i4.0
0x13eb15  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13eb1a  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propOptimizeCompilations
0x13eb1f  ldstr    aBatchtimeout// "batchTimeout"
0x13eb24  ldtoken  [mscorlib]System.TimeSpan
0x13eb29  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13eb2e  ldc.r8   15.0
0x13eb37  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x13eb3c  box      [mscorlib]System.TimeSpan
0x13eb41  call     class [System]System.ComponentModel.TypeConverter System.Web.Configuration.StdValidatorsAndConverters::get_TimeSpanSecondsOrInfiniteConverter()
0x13eb46  call     class [System.Configuration]System.Configuration.ConfigurationValidatorBase System.Web.Configuration.StdValidatorsAndConverters::get_PositiveTimeSpanValidator()
0x13eb4b  ldc.i4.0
0x13eb4c  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, class [System]System.ComponentModel.TypeConverter, class [System.Configuration]System.Configuration.ConfigurationValidatorBase, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13eb51  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propBatchTimeout
0x13eb56  ldstr    aMaxbatchsize// "maxBatchSize"
0x13eb5b  ldtoken  [mscorlib]System.Int32
0x13eb60  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13eb65  ldc.i4   0x3E8
0x13eb6a  box      [mscorlib]System.Int32
0x13eb6f  ldc.i4.0
0x13eb70  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13eb75  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propMaxBatchSize
0x13eb7a  ldstr    aMaxbatchgenera// "maxBatchGeneratedFileSize"
0x13eb7f  ldtoken  [mscorlib]System.Int32
0x13eb84  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13eb89  ldc.i4   0x3E8
0x13eb8e  box      [mscorlib]System.Int32
0x13eb93  ldc.i4.0
0x13eb94  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13eb99  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propMaxBatchGeneratedFileSize
0x13eb9e  ldstr    aNumrecompilesb// "numRecompilesBeforeAppRestart"
0x13eba3  ldtoken  [mscorlib]System.Int32
0x13eba8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ebad  ldc.i4.s 0xF
0x13ebaf  box      [mscorlib]System.Int32
0x13ebb4  ldc.i4.0
0x13ebb5  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ebba  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propNumRecompilesBeforeAppRestart
0x13ebbf  ldstr    aDefaultlanguag// "defaultLanguage"
0x13ebc4  ldtoken  [mscorlib]System.String
0x13ebc9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ebce  ldstr    aVb// "vb"
0x13ebd3  ldc.i4.0
0x13ebd4  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ebd9  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propDefaultLanguage
0x13ebde  ldstr    aTargetframewor_0// "targetFramework"
0x13ebe3  ldtoken  [mscorlib]System.String
0x13ebe8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ebed  ldnull
0x13ebee  ldc.i4.0
0x13ebef  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ebf4  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propTargetFramework
0x13ebf9  ldstr    aCompilers// "compilers"
0x13ebfe  ldtoken  System.Web.Configuration.CompilerCollection
0x13ec03  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ec08  ldnull
0x13ec09  ldc.i4.1
0x13ec0a  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ec0f  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propCompilers
0x13ec14  ldstr    aAssemblies// "assemblies"
0x13ec19  ldtoken  System.Web.Configuration.AssemblyCollection
0x13ec1e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ec23  ldnull
0x13ec24  ldc.i4.1
0x13ec25  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ec2a  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propAssemblies
0x13ec2f  ldstr    aBuildproviders// "buildProviders"
0x13ec34  ldtoken  System.Web.Configuration.BuildProviderCollection
0x13ec39  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ec3e  ldnull
0x13ec3f  ldc.i4.1
0x13ec40  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ec45  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propBuildProviders
0x13ec4a  ldstr    aFolderlevelbui// "folderLevelBuildProviders"
0x13ec4f  ldtoken  System.Web.Configuration.FolderLevelBuildProviderCollection
0x13ec54  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ec59  ldnull
0x13ec5a  ldc.i4.1
0x13ec5b  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ec60  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propFolderLevelBuildProviders
0x13ec65  ldstr    aExpressionbuil_0// "expressionBuilders"
0x13ec6a  ldtoken  System.Web.Configuration.ExpressionBuilderCollection
0x13ec6f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ec74  ldnull
0x13ec75  ldc.i4.1
0x13ec76  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ec7b  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propExpressionBuilders
0x13ec80  ldstr    aUrllinepragmas// "urlLinePragmas"
0x13ec85  ldtoken  [mscorlib]System.Boolean
0x13ec8a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ec8f  ldc.i4.0
0x13ec90  box      [mscorlib]System.Boolean
0x13ec95  ldc.i4.0
0x13ec96  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ec9b  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propUrlLinePragmas
0x13eca0  ldstr    aCodesubdirecto// "codeSubDirectories"
0x13eca5  ldtoken  System.Web.Configuration.CodeSubDirectoriesCollection
0x13ecaa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ecaf  ldnull
0x13ecb0  ldc.i4.1
0x13ecb1  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ecb6  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propCodeSubDirs
0x13ecbb  ldstr    aAssemblypostpr// "assemblyPostProcessorType"
0x13ecc0  ldtoken  [mscorlib]System.String
0x13ecc5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ecca  ldsfld   string [mscorlib]System.String::Empty
0x13eccf  ldc.i4.0
0x13ecd0  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ecd5  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propAssemblyPreprocessorType
0x13ecda  ldstr    aEnableprefetch// "enablePrefetchOptimization"
0x13ecdf  ldtoken  [mscorlib]System.Boolean
0x13ece4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ece9  ldc.i4.0
0x13ecea  box      [mscorlib]System.Boolean
0x13ecef  ldc.i4.0
0x13ecf0  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ecf5  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propEnablePrefetchOptimization
0x13ecfa  ldstr    aProfileguidedo// "profileGuidedOptimizations"
0x13ecff  ldtoken  System.Web.Configuration.ProfileGuidedOptimizationsFlags
0x13ed04  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ed09  ldc.i4.1
0x13ed0a  box      System.Web.Configuration.ProfileGuidedOptimizationsFlags
0x13ed0f  ldc.i4.0
0x13ed10  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ed15  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propProfileGuidedOptimizations
0x13ed1a  ldstr    aControlbuilder_8// "controlBuilderInterceptorType"
0x13ed1f  ldtoken  [mscorlib]System.String
0x13ed24  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ed29  ldsfld   string [mscorlib]System.String::Empty
0x13ed2e  ldc.i4.0
0x13ed2f  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ed34  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propControlBuilderInterceptorType
0x13ed39  ldstr    aDisableobsolet// "disableObsoleteWarnings"
0x13ed3e  ldtoken  [mscorlib]System.Boolean
0x13ed43  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ed48  ldc.i4.1
0x13ed49  box      [mscorlib]System.Boolean
0x13ed4e  ldc.i4.0
0x13ed4f  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ed54  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propDisableObsoleteWarnings
0x13ed59  ldstr    aMaxconcurrentc// "maxConcurrentCompilations"
0x13ed5e  ldtoken  [mscorlib]System.Int32
0x13ed63  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ed68  ldc.i4.1
0x13ed69  box      [mscorlib]System.Int32
0x13ed6e  ldc.i4.0
0x13ed6f  newobj   instance void [System.Configuration]System.Configuration.ConfigurationProperty::.ctor(string, class [mscorlib]System.Type, object, valuetype [System.Configuration]System.Configuration.ConfigurationPropertyOptions)
0x13ed74  stsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propMaxConcurrentCompilations
0x13ed79  newobj   instance void class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Reflection.Assembly, string>>::.ctor()
0x13ed7e  stsfld   class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Reflection.Assembly, string>> System.Web.Configuration.CompilationSection::_assemblyNames
0x13ed83  newobj   instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::.ctor()
0x13ed88  stsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13ed8d  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13ed92  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propTempDirectory
0x13ed97  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13ed9c  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13eda1  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propDebug
0x13eda6  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13edab  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13edb0  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propStrict
0x13edb5  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13edba  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13edbf  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propExplicit
0x13edc4  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13edc9  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13edce  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propBatch
0x13edd3  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13edd8  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13eddd  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propOptimizeCompilations
0x13ede2  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13ede7  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13edec  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propBatchTimeout
0x13edf1  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13edf6  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13edfb  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propMaxBatchSize
0x13ee00  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13ee05  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13ee0a  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propMaxBatchGeneratedFileSize
0x13ee0f  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13ee14  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13ee19  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propNumRecompilesBeforeAppRestart
0x13ee1e  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13ee23  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13ee28  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propDefaultLanguage
0x13ee2d  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13ee32  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13ee37  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propTargetFramework
0x13ee3c  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13ee41  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13ee46  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propCompilers
0x13ee4b  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13ee50  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13ee55  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propAssemblies
0x13ee5a  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13ee5f  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13ee64  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propBuildProviders
0x13ee69  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13ee6e  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13ee73  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propFolderLevelBuildProviders
0x13ee78  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13ee7d  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13ee82  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propExpressionBuilders
0x13ee87  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13ee8c  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13ee91  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propUrlLinePragmas
0x13ee96  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13ee9b  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13eea0  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propCodeSubDirs
0x13eea5  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13eeaa  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13eeaf  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propAssemblyPreprocessorType
0x13eeb4  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13eeb9  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13eebe  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propEnablePrefetchOptimization
0x13eec3  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13eec8  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13eecd  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propProfileGuidedOptimizations
0x13eed2  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13eed7  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13eedc  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propControlBuilderInterceptorType
0x13eee1  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13eee6  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13eeeb  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propDisableObsoleteWarnings
0x13eef0  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13eef5  ldsfld   class [System.Configuration]System.Configuration.ConfigurationPropertyCollection System.Web.Configuration.CompilationSection::_properties
0x13eefa  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propMaxConcurrentCompilations
0x13eeff  callvirt instance void [System.Configuration]System.Configuration.ConfigurationPropertyCollection::Add(class [System.Configuration]System.Configuration.ConfigurationProperty)
0x13ef04  ret
```
