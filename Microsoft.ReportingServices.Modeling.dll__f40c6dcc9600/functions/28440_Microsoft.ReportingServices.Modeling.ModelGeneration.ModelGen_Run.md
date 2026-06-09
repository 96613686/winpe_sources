# Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::Run

- ea: `0x28440`
- end: `0x2861c`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::Run`
- size: `476`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `service_task, broker_com_uri`

## callers

- `0x28750`

## callees

- `0x97d0`
- `0x14300`
- `0x16b60`
- `0x25e10`
- `0x25e20`
- `0x25e30`
- `0x25e40`
- `0x27220`
- `0x27740`
- `0x27a50`
- `0x28180`
- `0x28190`
- `0x281a0`
- `0x281b0`
- `0x281c0`
- `0x28440`
- `0x28730`
- `0x287d0`
- `0x28920`
- `0x289b0`
- `0x2aad0`
- `0x2aae0`
- `0x39590`
- `0x39610`
- `0x396f0`

## pseudocode

```c

```

## disassembly

```asm
0x28440  ldarg.0
0x28441  ldfld    class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_ruleSet
0x28446  brfalse.s loc_2845D
0x28448  ldarg.0
0x28449  ldfld    class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_model
0x2844e  brfalse.s loc_2845D
0x28450  ldarg.0
0x28451  ldfld    class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_model
0x28456  callvirt instance class Microsoft.ReportingServices.Modeling.DataSourceView Microsoft.ReportingServices.Modeling.SemanticModel::get_DataSourceView()
0x2845b  brtrue.s loc_28463
0x2845d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x28462  throw
0x28463  ldarg.0
0x28464  call     instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::CheckNotRunning()
0x28469  ldnull
0x2846a  stloc.0
0x2846b  ldarg.0
0x2846c  ldc.i4.1
0x2846d  volatile.
0x2846f  stfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_running
0x28474  ldarg.0
0x28475  ldfld    object Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_scopeItems
0x2847a  isinst   class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.Modeling.ModelEntity>
0x2847f  stloc.1
0x28480  ldarg.0
0x28481  ldfld    object Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_scopeItems
0x28486  isinst   class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.Modeling.ModelAttribute>
0x2848b  stloc.2
0x2848c  newobj   instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingBindingContext::.ctor()
0x28491  stloc.3
0x28492  ldarg.0
0x28493  ldfld    class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_model
0x28498  ldloc.1
0x28499  ldloc.2
0x2849a  ldloc.3
0x2849b  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.DsvItemMapper::FillExistingBindingInfo(class Microsoft.ReportingServices.Modeling.SemanticModel model, class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.Modeling.ModelEntity> scopeEntities, class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.Modeling.ModelAttribute> scopeAttrs, class Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingBindingContext bindingContext)
0x284a0  ldarg.0
0x284a1  ldfld    class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_ruleSet
0x284a6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.EvaluateDsvItemRule> Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::GetEnabledDsvItemRules()
0x284ab  stloc.s  4
0x284ad  ldloc.1
0x284ae  brfalse.s loc_284BD
0x284b0  ldloc.s  4
0x284b2  ldloc.1
0x284b3  ldloc.3
0x284b4  newobj   instance void DsvItemFilterWithEntityScope::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.EvaluateDsvItemRule> rules, class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.Modeling.ModelEntity> scopeEntities, class Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingBindingContext bindingContext)
0x284b9  stloc.s  5
0x284bb  br.s     loc_28502
0x284bd  ldloc.2
0x284be  brfalse.s loc_284CD
0x284c0  ldloc.s  4
0x284c2  ldloc.2
0x284c3  ldloc.3
0x284c4  newobj   instance void DsvItemFilterWithAttributeScope::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.EvaluateDsvItemRule> rules, class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.Modeling.ModelAttribute> scopeAttrs, class Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingBindingContext bindingContext)
0x284c9  stloc.s  5
0x284cb  br.s     loc_28502
0x284cd  ldarg.0
0x284ce  ldfld    object Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_scopeItems
0x284d3  brtrue.s loc_284E0
0x284d5  ldloc.s  4
0x284d7  newobj   instance void DsvItemFilter::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.EvaluateDsvItemRule> rules)
0x284dc  stloc.s  5
0x284de  br.s     loc_28502
0x284e0  ldstr    aUnknownMScopei// "Unknown m_scopeItems: "
0x284e5  ldarg.0
0x284e6  ldfld    object Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_scopeItems
0x284eb  dup
0x284ec  brtrue.s loc_284F2
0x284ee  pop
0x284ef  ldnull
0x284f0  br.s     loc_284F7
0x284f2  callvirt instance string [mscorlib]System.Object::ToString()
0x284f7  call     string [mscorlib]System.String::Concat(string, string)
0x284fc  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x28501  throw
0x28502  ldarg.0
0x28503  ldfld    class Microsoft.ReportingServices.Modeling.ModelGeneration.IDsvStatisticsProvider Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_dsvStatisticsProvider
0x28508  brfalse.s loc_28588
0x2850a  ldarg.0
0x2850b  ldfld    class Microsoft.ReportingServices.Modeling.ModelGeneration.IDsvStatisticsProvider Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_dsvStatisticsProvider
0x28510  ldarg.0
0x28511  ldftn    instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::inner_Progress(object sender, class Microsoft.ReportingServices.Modeling.ModelGeneration.ProgressEventArgs e)
0x28517  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.ProgressEventArgs>::.ctor(object, native int)
0x2851c  callvirt instance void Microsoft.ReportingServices.Modeling.ModelGeneration.IDsvStatisticsProvider::add_Progress(class [mscorlib]System.EventHandler`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.ProgressEventArgs> value)
0x28521  ldarg.0
0x28522  ldfld    class Microsoft.ReportingServices.Modeling.ModelGeneration.IDsvStatisticsProvider Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_dsvStatisticsProvider
0x28527  ldarg.0
0x28528  ldftn    instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::inner_Log(object sender, class Microsoft.ReportingServices.Modeling.ModelGeneration.LogEventArgs e)
0x2852e  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.LogEventArgs>::.ctor(object, native int)
0x28533  callvirt instance void Microsoft.ReportingServices.Modeling.ModelGeneration.IDsvStatisticsProvider::add_Log(class [mscorlib]System.EventHandler`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.LogEventArgs> value)
0x28538  ldarg.0
0x28539  ldfld    class Microsoft.ReportingServices.Modeling.ModelGeneration.IDsvStatisticsProvider Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_dsvStatisticsProvider
0x2853e  ldarg.0
0x2853f  ldfld    class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_model
0x28544  callvirt instance class Microsoft.ReportingServices.Modeling.DataSourceView Microsoft.ReportingServices.Modeling.SemanticModel::get_DataSourceView()
0x28549  ldloc.s  5
0x2854b  ldarg.0
0x2854c  ldfld    bool Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_overwriteDsvStatistics
0x28551  ldarg.0
0x28552  callvirt instance void Microsoft.ReportingServices.Modeling.ModelGeneration.IDsvStatisticsProvider::Fill(class Microsoft.ReportingServices.Modeling.DataSourceView dataSourceView, class Microsoft.ReportingServices.Modeling.ModelGeneration.IDsvItemFilter filter, bool overwrite, class Microsoft.ReportingServices.Modeling.ModelGeneration.ICancelEvent cancel)
0x28557  leave.s  loc_28588
0x28559  ldarg.0
0x2855a  ldfld    class Microsoft.ReportingServices.Modeling.ModelGeneration.IDsvStatisticsProvider Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_dsvStatisticsProvider
0x2855f  ldarg.0
0x28560  ldftn    instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::inner_Progress(object sender, class Microsoft.ReportingServices.Modeling.ModelGeneration.ProgressEventArgs e)
0x28566  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.ProgressEventArgs>::.ctor(object, native int)
0x2856b  callvirt instance void Microsoft.ReportingServices.Modeling.ModelGeneration.IDsvStatisticsProvider::remove_Progress(class [mscorlib]System.EventHandler`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.ProgressEventArgs> value)
0x28570  ldarg.0
0x28571  ldfld    class Microsoft.ReportingServices.Modeling.ModelGeneration.IDsvStatisticsProvider Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_dsvStatisticsProvider
0x28576  ldarg.0
0x28577  ldftn    instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::inner_Log(object sender, class Microsoft.ReportingServices.Modeling.ModelGeneration.LogEventArgs e)
0x2857d  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.LogEventArgs>::.ctor(object, native int)
0x28582  callvirt instance void Microsoft.ReportingServices.Modeling.ModelGeneration.IDsvStatisticsProvider::remove_Log(class [mscorlib]System.EventHandler`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.LogEventArgs> value)
0x28587  endfinally
0x28588  ldarg.0
0x28589  ldarg.0
0x2858a  ldfld    class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_ruleSet
0x2858f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule> Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::GetEnabledProcessingRules()
0x28594  ldarg.0
0x28595  ldfld    class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_model
0x2859a  ldloc.s  5
0x2859c  ldloc.3
0x2859d  ldarg.0
0x2859e  ldfld    bool Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_traceVerbose
0x285a3  newobj   instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ModelRuleProcessor::.ctor(class Microsoft.ReportingServices.Modeling.ModelGeneration.IModelGenEvents events, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule> rules, class Microsoft.ReportingServices.Modeling.SemanticModel model, class Microsoft.ReportingServices.Modeling.ModelGeneration.IDsvItemFilter filter, class Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingBindingContext bindingContext, bool traceVerbose)
0x285a8  callvirt instance class Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGenResult Microsoft.ReportingServices.Modeling.ModelGeneration.ModelRuleProcessor::ProcessRules()
0x285ad  pop
0x285ae  ldarg.0
0x285af  ldfld    class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_model
0x285b4  ldc.i4.0
0x285b5  callvirt instance class Microsoft.ReportingServices.Modeling.ValidationMessageCollection Microsoft.ReportingServices.Modeling.ModelItem::Validate(bool throwOnError)
0x285ba  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.ReportingServices.Modeling.ValidationMessage>::GetEnumerator()
0x285bf  stloc.s  6
0x285c1  br.s     loc_285F9
0x285c3  ldloc.s  6
0x285c5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.ReportingServices.Modeling.ValidationMessage>::get_Current()
0x285ca  stloc.s  7
0x285cc  ldarg.0
0x285cd  ldloc.s  7
0x285cf  callvirt instance valuetype Microsoft.ReportingServices.Modeling.Severity Microsoft.ReportingServices.Modeling.ValidationMessage::get_Severity()
0x285d4  brfalse.s loc_285D9
0x285d6  ldc.i4.2
0x285d7  br.s     loc_285DA
0x285d9  ldc.i4.1
0x285da  ldloc.s  7
0x285dc  callvirt instance string Microsoft.ReportingServices.Modeling.ValidationMessage::get_ObjectType()
0x285e1  ldloc.s  7
0x285e3  callvirt instance string Microsoft.ReportingServices.Modeling.ValidationMessage::get_ObjectID()
0x285e8  ldloc.s  7
0x285ea  callvirt instance string Microsoft.ReportingServices.Modeling.ValidationMessage::get_Message()
0x285ef  newobj   instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGenLogEventArgs::.ctor(valuetype Microsoft.ReportingServices.Modeling.ModelGeneration.LogEntryType entryType, string source, string dsvItemName, string message)
0x285f4  call     instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::OnLog(class Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGenLogEventArgs e)
0x285f9  ldloc.s  6
0x285fb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x28600  brtrue.s loc_285C3
0x28602  leave.s  loc_2861A
0x28604  ldloc.s  6
0x28606  brfalse.s loc_2860F
0x28608  ldloc.s  6
0x2860a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2860f  endfinally
0x28610  ldarg.0
0x28611  ldc.i4.0
0x28612  volatile.
0x28614  stfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool Microsoft.ReportingServices.Modeling.ModelGeneration.ModelGen::m_running
0x28619  endfinally
0x2861a  ldloc.0
0x2861b  ret
```
