# System.Xml.Xsl.Runtime.XmlExtensionFunction::Invoke

- ea: `0x2e730`
- end: `0x2e795`
- name: `System.Xml.Xsl.Runtime.XmlExtensionFunction::Invoke`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x2f390`

## callees

- `0x3760`
- `0x2e730`

## string_xrefs

- `0x2e753`: `XmlIl_ExtensionError`
- `0x2e779`: `XmlIl_ExtensionError`

## pseudocode

```c

```

## disassembly

```asm
0x2e730  ldarg.0
0x2e731  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XmlExtensionFunction::meth
0x2e736  ldarg.1
0x2e737  ldarg.0
0x2e738  ldfld    valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Xsl.Runtime.XmlExtensionFunction::flags
0x2e73d  ldnull
0x2e73e  ldarg.2
0x2e73f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e744  callvirt instance object [mscorlib]System.Reflection.MethodBase::Invoke(object, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, object[], class [mscorlib]System.Globalization.CultureInfo)
0x2e749  stloc.0
0x2e74a  leave.s  loc_2E793
0x2e74c  stloc.1
0x2e74d  ldloc.1
0x2e74e  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x2e753  ldstr    aXmlilExtension// "XmlIl_ExtensionError"
0x2e758  ldc.i4.1
0x2e759  newarr   [mscorlib]System.String
0x2e75e  dup
0x2e75f  ldc.i4.0
0x2e760  ldarg.0
0x2e761  ldfld    string System.Xml.Xsl.Runtime.XmlExtensionFunction::name
0x2e766  stelem.ref
0x2e767  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(class [mscorlib]System.Exception inner, string res, string[] args)
0x2e76c  throw
0x2e76d  stloc.2
0x2e76e  ldloc.2
0x2e76f  call     bool [System.Xml]System.Xml.XmlException::IsCatchableException(class [mscorlib]System.Exception)
0x2e774  brtrue.s loc_2E778
0x2e776  rethrow
0x2e778  ldloc.2
0x2e779  ldstr    aXmlilExtension// "XmlIl_ExtensionError"
0x2e77e  ldc.i4.1
0x2e77f  newarr   [mscorlib]System.String
0x2e784  dup
0x2e785  ldc.i4.0
0x2e786  ldarg.0
0x2e787  ldfld    string System.Xml.Xsl.Runtime.XmlExtensionFunction::name
0x2e78c  stelem.ref
0x2e78d  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(class [mscorlib]System.Exception inner, string res, string[] args)
0x2e792  throw
0x2e793  ldloc.0
0x2e794  ret
```
