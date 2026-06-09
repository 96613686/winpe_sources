# System.Xml.Xsl.Xslt.Scripts::CompileScripts

- ea: `0x1c290`
- end: `0x1c3c2`
- name: `System.Xml.Xsl.Xslt.Scripts::CompileScripts`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16300`

## callees

- `0x1c290`
- `0x1c3d0`

## string_xrefs

- `0x1c34a`: `System.Xml.Xsl.CompiledQuery`

## pseudocode

```c

```

## disassembly

```asm
0x1c290  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::.ctor()
0x1c295  stloc.0
0x1c296  ldc.i4.0
0x1c297  stloc.1
0x1c298  br       loc_1C3B0
0x1c29d  ldarg.0
0x1c29e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass> System.Xml.Xsl.Xslt.Scripts::scriptClasses
0x1c2a3  ldloc.1
0x1c2a4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::get_Item(!!T0)
0x1c2a9  brfalse  loc_1C3AC
0x1c2ae  ldarg.0
0x1c2af  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass> System.Xml.Xsl.Xslt.Scripts::scriptClasses
0x1c2b4  ldloc.1
0x1c2b5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::get_Item(!!T0)
0x1c2ba  ldfld    class [System]System.CodeDom.Compiler.CompilerInfo System.Xml.Xsl.Xslt.ScriptClass::compilerInfo
0x1c2bf  stloc.2
0x1c2c0  ldloc.0
0x1c2c1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::Clear()
0x1c2c6  ldloc.1
0x1c2c7  stloc.s  4
0x1c2c9  br.s     loc_1C316
0x1c2cb  ldarg.0
0x1c2cc  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass> System.Xml.Xsl.Xslt.Scripts::scriptClasses
0x1c2d1  ldloc.s  4
0x1c2d3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::get_Item(!!T0)
0x1c2d8  brfalse.s loc_1C310
0x1c2da  ldarg.0
0x1c2db  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass> System.Xml.Xsl.Xslt.Scripts::scriptClasses
0x1c2e0  ldloc.s  4
0x1c2e2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::get_Item(!!T0)
0x1c2e7  ldfld    class [System]System.CodeDom.Compiler.CompilerInfo System.Xml.Xsl.Xslt.ScriptClass::compilerInfo
0x1c2ec  ldloc.2
0x1c2ed  bne.un.s loc_1C310
0x1c2ef  ldloc.0
0x1c2f0  ldarg.0
0x1c2f1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass> System.Xml.Xsl.Xslt.Scripts::scriptClasses
0x1c2f6  ldloc.s  4
0x1c2f8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::get_Item(!!T0)
0x1c2fd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::Add(var<u1>)
0x1c302  ldarg.0
0x1c303  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass> System.Xml.Xsl.Xslt.Scripts::scriptClasses
0x1c308  ldloc.s  4
0x1c30a  ldnull
0x1c30b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::set_Item(int32, var<u1>)
0x1c310  ldloc.s  4
0x1c312  ldc.i4.1
0x1c313  add
0x1c314  stloc.s  4
0x1c316  ldloc.s  4
0x1c318  ldarg.0
0x1c319  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass> System.Xml.Xsl.Xslt.Scripts::scriptClasses
0x1c31e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::get_Count()
0x1c323  blt.s    loc_1C2CB
0x1c325  ldarg.0
0x1c326  ldloc.0
0x1c327  call     instance class [mscorlib]System.Reflection.Assembly System.Xml.Xsl.Xslt.Scripts::CompileAssembly(class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass> scriptsForLang)
0x1c32c  stloc.3
0x1c32d  ldloc.3
0x1c32e  ldnull
0x1c32f  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x1c334  brfalse.s loc_1C3AC
0x1c336  ldloc.0
0x1c337  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::GetEnumerator()
0x1c33c  stloc.s  5
0x1c33e  br.s     loc_1C393
0x1c340  ldloca.s 5
0x1c342  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Xslt.ScriptClass>::get_Current()
0x1c347  stloc.s  6
0x1c349  ldloc.3
0x1c34a  ldstr    aSystemXmlXslCo// "System.Xml.Xsl.CompiledQuery"
0x1c34f  ldsfld   char [mscorlib]System.Type::Delimiter
0x1c354  stloc.s  8
0x1c356  ldloca.s 8
0x1c358  call     instance string [mscorlib]System.Char::ToString()
0x1c35d  ldloc.s  6
0x1c35f  ldfld    class [System]System.CodeDom.CodeTypeDeclaration System.Xml.Xsl.Xslt.ScriptClass::typeDecl
0x1c364  callvirt instance string [System]System.CodeDom.CodeTypeMember::get_Name()
0x1c369  call     string [mscorlib]System.String::Concat(string, string, string)
0x1c36e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x1c373  stloc.s  7
0x1c375  ldloc.s  7
0x1c377  ldnull
0x1c378  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c37d  brfalse.s loc_1C393
0x1c37f  ldarg.0
0x1c380  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type> System.Xml.Xsl.Xslt.Scripts::nsToType
0x1c385  ldloc.s  6
0x1c387  ldfld    string System.Xml.Xsl.Xslt.ScriptClass::ns
0x1c38c  ldloc.s  7
0x1c38e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::Add(var<u1>, !!T0)
0x1c393  ldloca.s 5
0x1c395  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Xslt.ScriptClass>::MoveNext()
0x1c39a  brtrue.s loc_1C340
0x1c39c  leave.s  loc_1C3AC
0x1c39e  ldloca.s 5
0x1c3a0  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Xslt.ScriptClass>
0x1c3a6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c3ab  endfinally
0x1c3ac  ldloc.1
0x1c3ad  ldc.i4.1
0x1c3ae  add
0x1c3af  stloc.1
0x1c3b0  ldloc.1
0x1c3b1  ldarg.0
0x1c3b2  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass> System.Xml.Xsl.Xslt.Scripts::scriptClasses
0x1c3b7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.ScriptClass>::get_Count()
0x1c3bc  blt      loc_1C29D
0x1c3c1  ret
```
