# <GenerateSyndicationFeedItems>d__33::System.Collections.Generic.IEnumerable<System.ServiceModel.Syndication.SyndicationItem>.GetEnumerator

- ea: `0xb960`
- end: `0xb997`
- name: `<GenerateSyndicationFeedItems>d__33::System.Collections.Generic.IEnumerable<System.ServiceModel.Syndication.SyndicationItem>.GetEnumerator`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0xb9a0`

## callees

- `0xb7c0`
- `0xb960`

## pseudocode

```c

```

## disassembly

```asm
0xb960  ldarg.0
0xb961  ldfld    int32 <GenerateSyndicationFeedItems>d__33::<>1__state
0xb966  ldc.i4.s 0xFE
0xb968  bne.un.s loc_B982
0xb96a  ldarg.0
0xb96b  ldfld    int32 <GenerateSyndicationFeedItems>d__33::<>l__initialThreadId
0xb970  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0xb975  bne.un.s loc_B982
0xb977  ldarg.0
0xb978  ldc.i4.0
0xb979  stfld    int32 <GenerateSyndicationFeedItems>d__33::<>1__state
0xb97e  ldarg.0
0xb97f  stloc.0
0xb980  br.s     loc_B995
0xb982  ldc.i4.0
0xb983  newobj   instance void <GenerateSyndicationFeedItems>d__33::.ctor(int32 <>1__state)
0xb988  stloc.0
0xb989  ldloc.0
0xb98a  ldarg.0
0xb98b  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor <GenerateSyndicationFeedItems>d__33::<>4__this
0xb990  stfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor <GenerateSyndicationFeedItems>d__33::<>4__this
0xb995  ldloc.0
0xb996  ret
```
