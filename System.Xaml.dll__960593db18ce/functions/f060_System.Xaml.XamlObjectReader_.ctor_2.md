# System.Xaml.XamlObjectReader::.ctor_2

- ea: `0xf060`
- end: `0xf167`
- name: `System.Xaml.XamlObjectReader::.ctor_2`
- size: `263`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0xf040`
- `0xf050`

## callees

- `0x2120`
- `0xb470`
- `0xf060`
- `0xf320`
- `0x29140`
- `0x29fb0`
- `0x29fc0`
- `0x2a0a0`
- `0x2a0c0`
- `0x2b4a0`
- `0x2bb70`
- `0x2bc70`
- `0x2bcd0`
- `0x2bd90`

## pseudocode

```c

```

## disassembly

```asm
0xf060  ldarg.0
0xf061  call     instance void System.Xaml.XamlReader::.ctor()
0xf066  ldarg.2
0xf067  brtrue.s loc_F074
0xf069  ldstr    aSchemacontext// "schemaContext"
0xf06e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf073  throw
0xf074  ldarg.0
0xf075  ldarg.2
0xf076  stfld    class System.Xaml.XamlSchemaContext System.Xaml.XamlObjectReader::schemaContext
0xf07b  ldarg.0
0xf07c  ldarg.3
0xf07d  dup
0xf07e  brtrue.s loc_F086
0xf080  pop
0xf081  newobj   instance void System.Xaml.XamlObjectReaderSettings::.ctor()
0xf086  stfld    class System.Xaml.XamlObjectReaderSettings System.Xaml.XamlObjectReader::settings
0xf08b  ldarg.0
0xf08c  newobj   instance void class [System]System.Collections.Generic.Stack`1<class MarkupInfo>::.ctor()
0xf091  stfld    class [System]System.Collections.Generic.Stack`1<class MarkupInfo> System.Xaml.XamlObjectReader::nodes
0xf096  ldarg.0
0xf097  ldc.i4.1
0xf098  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype InternalNodeType internalNodeType)
0xf09d  stfld    valuetype System.Xaml.XamlNode System.Xaml.XamlObjectReader::currentXamlNode
0xf0a2  ldarg.2
0xf0a3  ldarg.0
0xf0a4  ldfld    class System.Xaml.XamlObjectReaderSettings System.Xaml.XamlObjectReader::settings
0xf0a9  newobj   instance void SerializerContext::.ctor(class System.Xaml.XamlSchemaContext schemaContext, class System.Xaml.XamlObjectReaderSettings settings)
0xf0ae  stloc.0
0xf0af  ldloc.0
0xf0b0  ldarg.1
0xf0b1  brfalse.s loc_F0BB
0xf0b3  ldarg.1
0xf0b4  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xf0b9  br.s     loc_F0BC
0xf0bb  ldnull
0xf0bc  callvirt instance void SerializerContext::set_RootType(class [mscorlib]System.Type value)
0xf0c1  ldarg.1
0xf0c2  ldloc.0
0xf0c3  ldnull
0xf0c4  ldc.i4.1
0xf0c5  call     class ObjectMarkupInfo ObjectMarkupInfo::ForObject(object value, class SerializerContext context, [opt] class [System]System.ComponentModel.TypeConverter instanceConverter, [opt] bool isRoot)
0xf0ca  stloc.1
0xf0cb  br.s     loc_F0E2
0xf0cd  ldloc.0
0xf0ce  callvirt instance class [System]System.Collections.Generic.Queue`1<class NameScopeMarkupInfo> SerializerContext::get_PendingNameScopes()
0xf0d3  callvirt instance var<u1> class [System]System.Collections.Generic.Queue`1<class NameScopeMarkupInfo>::Dequeue()
0xf0d8  stloc.s  4
0xf0da  ldloc.s  4
0xf0dc  ldloc.0
0xf0dd  callvirt instance void NameScopeMarkupInfo::Resume(class SerializerContext context)
0xf0e2  ldloc.0
0xf0e3  callvirt instance class [System]System.Collections.Generic.Queue`1<class NameScopeMarkupInfo> SerializerContext::get_PendingNameScopes()
0xf0e8  callvirt instance int32 class [System]System.Collections.Generic.Queue`1<class NameScopeMarkupInfo>::get_Count()
0xf0ed  ldc.i4.0
0xf0ee  bgt.s    loc_F0CD
0xf0f0  newobj   instance void class [System]System.Collections.Generic.Stack`1<class HashSet`1<string>>::.ctor()
0xf0f5  stloc.2
0xf0f6  ldloc.2
0xf0f7  newobj   instance void class HashSet`1<string>::.ctor()
0xf0fc  callvirt instance void class [System]System.Collections.Generic.Stack`1<class HashSet`1<string>>::Push(var<u1>)
0xf101  ldloc.1
0xf102  ldloc.2
0xf103  callvirt instance void ObjectOrValueMarkupInfo::EnsureNoDuplicateNames(class [System]System.Collections.Generic.Stack`1<class HashSet`1<string>> namesInCurrentScope)
0xf108  ldloc.1
0xf109  ldloc.0
0xf10a  callvirt instance void MarkupInfo::FindNamespace(class SerializerContext context)
0xf10f  ldarg.0
0xf110  ldfld    class [System]System.Collections.Generic.Stack`1<class MarkupInfo> System.Xaml.XamlObjectReader::nodes
0xf115  ldloc.1
0xf116  callvirt instance void class [System]System.Collections.Generic.Stack`1<class MarkupInfo>::Push(var<u1>)
0xf11b  ldloc.0
0xf11c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode> SerializerContext::GetSortedNamespaceNodes()
0xf121  stloc.3
0xf122  ldloc.3
0xf123  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0xf128  stloc.s  5
0xf12a  br.s     loc_F14D
0xf12c  ldloca.s 5
0xf12e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype System.Xaml.XamlNode>::get_Current()
0xf133  stloc.s  6
0xf135  ldarg.0
0xf136  ldfld    class [System]System.Collections.Generic.Stack`1<class MarkupInfo> System.Xaml.XamlObjectReader::nodes
0xf13b  newobj   instance void NamespaceMarkupInfo::.ctor()
0xf140  dup
0xf141  ldloc.s  6
0xf143  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0xf148  callvirt instance void class [System]System.Collections.Generic.Stack`1<class MarkupInfo>::Push(var<u1>)
0xf14d  ldloca.s 5
0xf14f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype System.Xaml.XamlNode>::MoveNext()
0xf154  brtrue.s loc_F12C
0xf156  leave.s  loc_F166
0xf158  ldloca.s 5
0xf15a  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype System.Xaml.XamlNode>
0xf160  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf165  endfinally
0xf166  ret
```
