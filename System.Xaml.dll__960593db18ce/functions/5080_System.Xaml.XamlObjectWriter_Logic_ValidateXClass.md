# System.Xaml.XamlObjectWriter::Logic_ValidateXClass

- ea: `0x5080`
- end: `0x5166`
- name: `System.Xaml.XamlObjectWriter::Logic_ValidateXClass`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x33d0`

## callees

- `0x5080`
- `0x8590`
- `0x8ac0`
- `0xc260`
- `0xd0b0`
- `0xf3b0`
- `0x11f50`
- `0x21200`
- `0x215a0`
- `0x215d0`
- `0x216d0`

## pseudocode

```c

```

## disassembly

```asm
0x5080  ldarg.1
0x5081  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_Depth()
0x5086  ldc.i4.1
0x5087  ble.s    loc_50AD
0x5089  ldarg.1
0x508a  ldstr    aDirectivenotat// "DirectiveNotAtRoot"
0x508f  ldc.i4.1
0x5090  newarr   [mscorlib]System.Object
0x5095  dup
0x5096  ldc.i4.0
0x5097  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Class()
0x509c  stelem.ref
0x509d  call     string System.Xaml.SR::Get(string id, object[] args)
0x50a2  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x50a7  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x50ac  throw
0x50ad  ldarg.2
0x50ae  isinst   [mscorlib]System.String
0x50b3  stloc.0
0x50b4  ldloc.0
0x50b5  brtrue.s loc_50DB
0x50b7  ldarg.1
0x50b8  ldstr    aDirectivemustb// "DirectiveMustBeString"
0x50bd  ldc.i4.1
0x50be  newarr   [mscorlib]System.Object
0x50c3  dup
0x50c4  ldc.i4.0
0x50c5  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Class()
0x50ca  stelem.ref
0x50cb  call     string System.Xaml.SR::Get(string id, object[] args)
0x50d0  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x50d5  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x50da  throw
0x50db  ldarg.1
0x50dc  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x50e1  stloc.1
0x50e2  ldloc.1
0x50e3  brtrue.s loc_50F2
0x50e5  ldarg.1
0x50e6  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x50eb  callvirt instance class [mscorlib]System.Type System.Xaml.XamlType::get_UnderlyingType()
0x50f0  br.s     loc_50F8
0x50f2  ldloc.1
0x50f3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x50f8  stloc.2
0x50f9  ldloc.2
0x50fa  callvirt instance string [mscorlib]System.Type::get_FullName()
0x50ff  ldloc.0
0x5100  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5105  brfalse.s loc_5165
0x5107  ldarg.0
0x5108  callvirt instance class System.Xaml.XamlSchemaContext System.Xaml.XamlWriter::get_SchemaContext()
0x510d  ldloc.2
0x510e  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x5113  callvirt instance string System.Xaml.XamlSchemaContext::GetRootNamespace(class [mscorlib]System.Reflection.Assembly asm)
0x5118  stloc.3
0x5119  ldloc.3
0x511a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x511f  brtrue.s loc_512E
0x5121  ldloc.3
0x5122  ldstr    asc_37256// "."
0x5127  ldloc.0
0x5128  call     string [mscorlib]System.String::Concat(string, string, string)
0x512d  stloc.0
0x512e  ldloc.2
0x512f  callvirt instance string [mscorlib]System.Type::get_FullName()
0x5134  ldloc.0
0x5135  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x513a  brfalse.s loc_5165
0x513c  ldarg.1
0x513d  ldstr    aXclassmustmatc// "XClassMustMatchRootInstance"
0x5142  ldc.i4.2
0x5143  newarr   [mscorlib]System.Object
0x5148  dup
0x5149  ldc.i4.0
0x514a  ldloc.0
0x514b  stelem.ref
0x514c  dup
0x514d  ldc.i4.1
0x514e  ldloc.2
0x514f  callvirt instance string [mscorlib]System.Type::get_FullName()
0x5154  stelem.ref
0x5155  call     string System.Xaml.SR::Get(string id, object[] args)
0x515a  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x515f  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x5164  throw
0x5165  ret
```
