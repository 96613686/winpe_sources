# System.Windows.Annotations.AnnotationHelper::CheckInputs

- ea: `0x1d1b90`
- end: `0x1d1c10`
- name: `System.Windows.Annotations.AnnotationHelper::CheckInputs`
- size: `128`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1d0cf0`
- `0x1d1080`
- `0x1d1170`
- `0x1d15f0`
- `0x1d1820`

## callees

- `0x38c40`
- `0x1ba150`
- `0x1d1b90`
- `0x1d26e0`
- `0x1d2850`

## string_xrefs

- `0x1d1b93`: `service`
- `0x1d1bb0`: `service`
- `0x1d1ba6`: `AnnotationServiceNotEnabled`
- `0x1d1bec`: `Service's Root must be either a FlowDocumentReader, DocumentViewerBase or a FlowDocumentScrollViewer.`

## pseudocode

```c

```

## disassembly

```asm
0x1d1b90  ldarg.0
0x1d1b91  brtrue.s loc_1D1B9E
0x1d1b93  ldstr    aService// "service"
0x1d1b98  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1d1b9d  throw
0x1d1b9e  ldarg.0
0x1d1b9f  callvirt instance bool System.Windows.Annotations.AnnotationService::get_IsEnabled()
0x1d1ba4  brtrue.s loc_1D1BBB
0x1d1ba6  ldstr    aAnnotationserv// "AnnotationServiceNotEnabled"
0x1d1bab  call     string System.Windows.SR::Get(string id)
0x1d1bb0  ldstr    aService// "service"
0x1d1bb5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1d1bba  throw
0x1d1bbb  ldarg.0
0x1d1bbc  callvirt instance class [WindowsBase]System.Windows.DependencyObject System.Windows.Annotations.AnnotationService::get_Root()
0x1d1bc1  isinst   System.Windows.Controls.Primitives.DocumentViewerBase
0x1d1bc6  stloc.0
0x1d1bc7  ldloc.0
0x1d1bc8  brtrue.s loc_1D1BF7
0x1d1bca  ldarg.0
0x1d1bcb  callvirt instance class [WindowsBase]System.Windows.DependencyObject System.Windows.Annotations.AnnotationService::get_Root()
0x1d1bd0  isinst   System.Windows.Controls.FlowDocumentScrollViewer
0x1d1bd5  stloc.1
0x1d1bd6  ldarg.0
0x1d1bd7  callvirt instance class [WindowsBase]System.Windows.DependencyObject System.Windows.Annotations.AnnotationService::get_Root()
0x1d1bdc  isinst   System.Windows.Controls.FlowDocumentReader
0x1d1be1  stloc.2
0x1d1be2  ldloc.1
0x1d1be3  brtrue.s loc_1D1BEB
0x1d1be5  ldloc.2
0x1d1be6  ldnull
0x1d1be7  cgt.un
0x1d1be9  br.s     loc_1D1BEC
0x1d1beb  ldc.i4.1
0x1d1bec  ldstr    aServiceSRootMu// "Service's Root must be either a FlowDoc"...
0x1d1bf1  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x1d1bf6  ret
0x1d1bf7  ldloc.0
0x1d1bf8  callvirt instance class [PresentationCore]System.Windows.Documents.IDocumentPaginatorSource System.Windows.Controls.Primitives.DocumentViewerBase::get_Document()
0x1d1bfd  brtrue.s loc_1D1C0F
0x1d1bff  ldstr    aOnlyflowfixeds// "OnlyFlowFixedSupported"
0x1d1c04  call     string System.Windows.SR::Get(string id)
0x1d1c09  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1d1c0e  throw
0x1d1c0f  ret
```
