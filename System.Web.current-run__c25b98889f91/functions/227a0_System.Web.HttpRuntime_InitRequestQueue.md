# System.Web.HttpRuntime::InitRequestQueue

- ea: `0x227a0`
- end: `0x22a3e`
- name: `System.Web.HttpRuntime::InitRequestQueue`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x22290`

## callees

- `0x227a0`
- `0x2b860`
- `0x34f20`
- `0x34fa0`
- `0x149fe0`
- `0x14a020`
- `0x14a060`
- `0x151ef0`
- `0x152030`
- `0x152260`
- `0x152290`
- `0x1522a0`
- `0x156580`
- `0x156880`
- `0x156940`

## string_xrefs

- `0x2281a`: `minFreeThreads`
- `0x22936`: `minFreeThreads`
- `0x22950`: `minFreeThreads`
- `0x229a7`: `minFreeThreads`
- `0x229c1`: `minFreeThreads`
- `0x22839`: `maxWorkerThreads`
- `0x2287c`: `maxWorkerThreads`
- `0x22896`: `maxWorkerThreads`
- `0x2284a`: `Thread_pool_limit_must_be_greater_than_minFreeThreads`
- `0x228ab`: `Thread_pool_limit_must_be_greater_than_minFreeThreads`
- `0x228dd`: `maxIoThreads`
- `0x228f7`: `maxIoThreads`
- `0x2290c`: `Min_free_threads_must_be_under_thread_pool_limits`
- `0x22981`: `minLocalRequestFreeThreads`
- `0x229eb`: `minLocalRequestFreeThreads`
- `0x22a05`: `minLocalRequestFreeThreads`
- `0x22992`: `Local_free_threads_cannot_exceed_free_threads`
- `0x229d6`: `Local_free_threads_cannot_exceed_free_threads`

## pseudocode

```c

```

## disassembly

```asm
0x227a0  call     class System.Web.Configuration.RuntimeConfig System.Web.Configuration.RuntimeConfig::GetAppConfig()
0x227a5  stloc.0
0x227a6  ldloc.0
0x227a7  callvirt instance class System.Web.Configuration.HttpRuntimeSection System.Web.Configuration.RuntimeConfig::get_HttpRuntime()
0x227ac  stloc.1
0x227ad  ldloc.0
0x227ae  callvirt instance class System.Web.Configuration.ProcessModelSection System.Web.Configuration.RuntimeConfig::get_ProcessModel()
0x227b3  stloc.2
0x227b4  ldloc.2
0x227b5  callvirt instance bool System.Web.Configuration.ProcessModelSection::get_AutoConfig()
0x227ba  brfalse.s loc_227E6
0x227bc  ldarg.0
0x227bd  ldc.i4.s 0x58
0x227bf  ldloc.2
0x227c0  callvirt instance int32 System.Web.Configuration.ProcessModelSection::get_CpuCount()
0x227c5  mul
0x227c6  ldc.i4.s 0x4C
0x227c8  ldloc.2
0x227c9  callvirt instance int32 System.Web.Configuration.ProcessModelSection::get_CpuCount()
0x227ce  mul
0x227cf  ldloc.1
0x227d0  callvirt instance int32 System.Web.Configuration.HttpRuntimeSection::get_AppRequestQueueLimit()
0x227d5  ldloc.2
0x227d6  callvirt instance valuetype [mscorlib]System.TimeSpan System.Web.Configuration.ProcessModelSection::get_ClientConnectedCheck()
0x227db  newobj   instance void System.Web.RequestQueue::.ctor(int32 minExternFreeThreads, int32 minLocalFreeThreads, int32 queueLimit, valuetype [mscorlib]System.TimeSpan clientConnectedTime)
0x227e0  stfld    class System.Web.RequestQueue System.Web.HttpRuntime::_requestQueue
0x227e5  ret
0x227e6  ldloc.2
0x227e7  callvirt instance int32 System.Web.Configuration.ProcessModelSection::get_MaxWorkerThreadsTimesCpuCount()
0x227ec  ldloc.2
0x227ed  callvirt instance int32 System.Web.Configuration.ProcessModelSection::get_MaxIoThreadsTimesCpuCount()
0x227f2  blt.s    loc_227FC
0x227f4  ldloc.2
0x227f5  callvirt instance int32 System.Web.Configuration.ProcessModelSection::get_MaxIoThreadsTimesCpuCount()
0x227fa  br.s     loc_22802
0x227fc  ldloc.2
0x227fd  callvirt instance int32 System.Web.Configuration.ProcessModelSection::get_MaxWorkerThreadsTimesCpuCount()
0x22802  stloc.3
0x22803  ldloc.1
0x22804  callvirt instance int32 System.Web.Configuration.HttpRuntimeSection::get_MinFreeThreads()
0x22809  ldloc.3
0x2280a  blt      loc_22965
0x2280f  ldloc.1
0x22810  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x22815  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x2281a  ldstr    aMinfreethreads// "minFreeThreads"
0x2281f  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x22824  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x22829  brtrue   loc_2290C
0x2282e  ldloc.2
0x2282f  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x22834  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x22839  ldstr    aMaxworkerthrea// "maxWorkerThreads"
0x2283e  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x22843  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x22848  brfalse.s loc_228AB
0x2284a  ldstr    aThreadPoolLimi// "Thread_pool_limit_must_be_greater_than_"...
0x2284f  ldc.i4.1
0x22850  newarr   [mscorlib]System.Object
0x22855  dup
0x22856  ldc.i4.0
0x22857  ldloc.1
0x22858  callvirt instance int32 System.Web.Configuration.HttpRuntimeSection::get_MinFreeThreads()
0x2285d  stloc.s  4
0x2285f  ldloca.s 4
0x22861  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22866  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2286b  stelem.ref
0x2286c  call     string System.Web.SR::GetString(string name, object[] args)
0x22871  ldloc.2
0x22872  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x22877  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x2287c  ldstr    aMaxworkerthrea// "maxWorkerThreads"
0x22881  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x22886  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x2288b  ldloc.2
0x2288c  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x22891  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x22896  ldstr    aMaxworkerthrea// "maxWorkerThreads"
0x2289b  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x228a0  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x228a5  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x228aa  throw
0x228ab  ldstr    aThreadPoolLimi// "Thread_pool_limit_must_be_greater_than_"...
0x228b0  ldc.i4.1
0x228b1  newarr   [mscorlib]System.Object
0x228b6  dup
0x228b7  ldc.i4.0
0x228b8  ldloc.1
0x228b9  callvirt instance int32 System.Web.Configuration.HttpRuntimeSection::get_MinFreeThreads()
0x228be  stloc.s  4
0x228c0  ldloca.s 4
0x228c2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x228c7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x228cc  stelem.ref
0x228cd  call     string System.Web.SR::GetString(string name, object[] args)
0x228d2  ldloc.2
0x228d3  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x228d8  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x228dd  ldstr    aMaxiothreads// "maxIoThreads"
0x228e2  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x228e7  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x228ec  ldloc.2
0x228ed  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x228f2  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x228f7  ldstr    aMaxiothreads// "maxIoThreads"
0x228fc  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x22901  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x22906  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x2290b  throw
0x2290c  ldstr    aMinFreeThreads// "Min_free_threads_must_be_under_thread_p"...
0x22911  ldc.i4.1
0x22912  newarr   [mscorlib]System.Object
0x22917  dup
0x22918  ldc.i4.0
0x22919  ldloca.s 3
0x2291b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22920  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x22925  stelem.ref
0x22926  call     string System.Web.SR::GetString(string name, object[] args)
0x2292b  ldloc.1
0x2292c  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x22931  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x22936  ldstr    aMinfreethreads// "minFreeThreads"
0x2293b  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x22940  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x22945  ldloc.1
0x22946  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x2294b  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x22950  ldstr    aMinfreethreads// "minFreeThreads"
0x22955  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x2295a  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x2295f  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x22964  throw
0x22965  ldloc.1
0x22966  callvirt instance int32 System.Web.Configuration.HttpRuntimeSection::get_MinLocalRequestFreeThreads()
0x2296b  ldloc.1
0x2296c  callvirt instance int32 System.Web.Configuration.HttpRuntimeSection::get_MinFreeThreads()
0x22971  ble      loc_22A1A
0x22976  ldloc.1
0x22977  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x2297c  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x22981  ldstr    aMinlocalreques// "minLocalRequestFreeThreads"
0x22986  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x2298b  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x22990  brtrue.s loc_229D6
0x22992  ldstr    aLocalFreeThrea// "Local_free_threads_cannot_exceed_free_t"...
0x22997  call     string System.Web.SR::GetString(string name)
0x2299c  ldloc.2
0x2299d  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x229a2  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x229a7  ldstr    aMinfreethreads// "minFreeThreads"
0x229ac  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x229b1  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x229b6  ldloc.2
0x229b7  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x229bc  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x229c1  ldstr    aMinfreethreads// "minFreeThreads"
0x229c6  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x229cb  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x229d0  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x229d5  throw
0x229d6  ldstr    aLocalFreeThrea// "Local_free_threads_cannot_exceed_free_t"...
0x229db  call     string System.Web.SR::GetString(string name)
0x229e0  ldloc.1
0x229e1  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x229e6  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x229eb  ldstr    aMinlocalreques// "minLocalRequestFreeThreads"
0x229f0  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x229f5  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x229fa  ldloc.1
0x229fb  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x22a00  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x22a05  ldstr    aMinlocalreques// "minLocalRequestFreeThreads"
0x22a0a  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x22a0f  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x22a14  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x22a19  throw
0x22a1a  ldarg.0
0x22a1b  ldloc.1
0x22a1c  callvirt instance int32 System.Web.Configuration.HttpRuntimeSection::get_MinFreeThreads()
0x22a21  ldloc.1
0x22a22  callvirt instance int32 System.Web.Configuration.HttpRuntimeSection::get_MinLocalRequestFreeThreads()
0x22a27  ldloc.1
0x22a28  callvirt instance int32 System.Web.Configuration.HttpRuntimeSection::get_AppRequestQueueLimit()
0x22a2d  ldloc.2
0x22a2e  callvirt instance valuetype [mscorlib]System.TimeSpan System.Web.Configuration.ProcessModelSection::get_ClientConnectedCheck()
0x22a33  newobj   instance void System.Web.RequestQueue::.ctor(int32 minExternFreeThreads, int32 minLocalFreeThreads, int32 queueLimit, valuetype [mscorlib]System.TimeSpan clientConnectedTime)
0x22a38  stfld    class System.Web.RequestQueue System.Web.HttpRuntime::_requestQueue
0x22a3d  ret
```
