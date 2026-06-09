# System.Xaml.XamlXmlWriter::InitializeXamlXmlWriter

- ea: `0xf5c0`
- end: `0xf65e`
- name: `System.Xaml.XamlXmlWriter::InitializeXamlXmlWriter`
- size: `158`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0xf4e0`
- `0xf540`
- `0xf5a0`

## callees

- `0x9dc0`
- `0xf5c0`
- `0x10200`
- `0x10220`
- `0x2cb80`
- `0x2cd20`
- `0x2d0e0`
- `0x2eb40`

## string_xrefs

- `0xf62b`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c

```

## disassembly

```asm
0xf5c0  ldarg.2
0xf5c1  brtrue.s loc_F5CE
0xf5c3  ldstr    aSchemacontext// "schemaContext"
0xf5c8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf5cd  throw
0xf5ce  ldarg.0
0xf5cf  ldarg.2
0xf5d0  stfld    class System.Xaml.XamlSchemaContext System.Xaml.XamlXmlWriter::schemaContext
0xf5d5  ldarg.0
0xf5d6  ldarg.1
0xf5d7  stfld    class [System.Xml]System.Xml.XmlWriter System.Xaml.XamlXmlWriter::output
0xf5dc  ldarg.0
0xf5dd  ldarg.3
0xf5de  brfalse.s loc_F5E8
0xf5e0  ldarg.3
0xf5e1  callvirt instance class System.Xaml.XamlXmlWriterSettings System.Xaml.XamlXmlWriterSettings::Copy()
0xf5e6  br.s     loc_F5ED
0xf5e8  newobj   instance void System.Xaml.XamlXmlWriterSettings::.ctor()
0xf5ed  stfld    class System.Xaml.XamlXmlWriterSettings System.Xaml.XamlXmlWriter::settings
0xf5f2  ldarg.0
0xf5f3  call     class WriterState Start::get_State()
0xf5f8  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0xf5fd  ldarg.0
0xf5fe  newobj   instance void class [System]System.Collections.Generic.Stack`1<class Frame>::.ctor()
0xf603  stfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0xf608  ldarg.0
0xf609  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0xf60e  newobj   instance void Frame::.ctor()
0xf613  dup
0xf614  ldc.i4.1
0xf615  callvirt instance void Frame::set_AllocatingNodeType(valuetype System.Xaml.XamlNodeType value)
0xf61a  callvirt instance void class [System]System.Collections.Generic.Stack`1<class Frame>::Push(var<u1>)
0xf61f  ldarg.0
0xf620  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xf625  dup
0xf626  ldstr    aXml// "xml"
0xf62b  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0xf630  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xf635  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Xaml.XamlXmlWriter::prefixAssignmentHistory
0xf63a  ldarg.0
0xf63b  newobj   instance void class [System]System.Collections.Generic.Stack`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>>::.ctor()
0xf640  stfld    class [System]System.Collections.Generic.Stack`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>> System.Xaml.XamlXmlWriter::meNodesStack
0xf645  ldarg.0
0xf646  ldarg.0
0xf647  newobj   instance void System.Xaml.XamlMarkupExtensionWriter::.ctor(class System.Xaml.XamlXmlWriter xamlXmlWriter)
0xf64c  stfld    class System.Xaml.XamlMarkupExtensionWriter System.Xaml.XamlXmlWriter::meWriter
0xf651  ldarg.0
0xf652  ldarg.0
0xf653  newobj   instance void PositionalParameterStateInfo::.ctor(class System.Xaml.XamlXmlWriter xamlXmlWriter)
0xf658  stfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0xf65d  ret
```
