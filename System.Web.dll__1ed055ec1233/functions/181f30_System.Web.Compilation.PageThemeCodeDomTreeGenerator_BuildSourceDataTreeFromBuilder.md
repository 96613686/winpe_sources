# System.Web.Compilation.PageThemeCodeDomTreeGenerator::BuildSourceDataTreeFromBuilder

- ea: `0x181f30`
- end: `0x1821b9`
- name: `System.Web.Compilation.PageThemeCodeDomTreeGenerator::BuildSourceDataTreeFromBuilder`
- size: `649`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x18eb0`
- `0x34f20`
- `0x5c6e0`
- `0x62470`
- `0x624b0`
- `0x62560`
- `0x625a0`
- `0x626d0`
- `0x626f0`
- `0x62710`
- `0x62780`
- `0x62950`
- `0x629a0`
- `0x79570`
- `0x81170`
- `0x171340`
- `0x172960`
- `0x172f60`
- `0x1735c0`
- `0x173920`
- `0x181f30`
- `0x1ae2d0`

## string_xrefs

- `0x181fdb`: `Page_theme_default_theme_already_defined`
- `0x18200d`: `Page_theme_skinID_already_defined`

## pseudocode

```c

```

## disassembly

```asm
0x181f30  ldarg.1
0x181f31  isinst   System.Web.UI.CodeBlockBuilder
0x181f36  brfalse.s loc_181F39
0x181f38  ret
0x181f39  ldarg.1
0x181f3a  isinst   System.Web.UI.TemplateBuilder
0x181f3f  ldnull
0x181f40  cgt.un
0x181f42  stloc.0
0x181f43  ldarg.1
0x181f44  ldarg.0
0x181f45  ldfld    class System.Web.UI.PageThemeParser System.Web.Compilation.PageThemeCodeDomTreeGenerator::_themeParser
0x181f4a  callvirt instance class System.Web.UI.RootBuilder System.Web.UI.TemplateParser::get_RootBuilder()
0x181f4f  ceq
0x181f51  stloc.1
0x181f52  ldarg.2
0x181f53  brtrue.s loc_181F5B
0x181f55  ldloc.0
0x181f56  ldc.i4.0
0x181f57  ceq
0x181f59  br.s     loc_181F5C
0x181f5b  ldc.i4.0
0x181f5c  ldarg.3
0x181f5d  and
0x181f5e  stloc.2
0x181f5f  ldarg.0
0x181f60  ldarg.0
0x181f61  ldfld    int32 System.Web.Compilation.PageThemeCodeDomTreeGenerator::_controlCount
0x181f66  ldc.i4.1
0x181f67  add
0x181f68  stfld    int32 System.Web.Compilation.PageThemeCodeDomTreeGenerator::_controlCount
0x181f6d  ldarg.1
0x181f6e  ldstr    aControl_0// "__control"
0x181f73  ldarg.0
0x181f74  ldflda   int32 System.Web.Compilation.PageThemeCodeDomTreeGenerator::_controlCount
0x181f79  call     class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.NumberFormatInfo::get_InvariantInfo()
0x181f7e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x181f83  call     string [mscorlib]System.String::Concat(string, string)
0x181f88  callvirt instance void System.Web.UI.ControlBuilder::set_ID(string value)
0x181f8d  ldarg.1
0x181f8e  ldc.i4.1
0x181f8f  callvirt instance void System.Web.UI.ControlBuilder::set_IsGeneratedID(bool value)
0x181f94  ldloc.2
0x181f95  brfalse  loc_18205D
0x181f9a  ldarg.1
0x181f9b  isinst   System.Web.UI.DataBoundLiteralControlBuilder
0x181fa0  brtrue   loc_18205D
0x181fa5  ldarg.1
0x181fa6  callvirt instance class [mscorlib]System.Type System.Web.UI.ControlBuilder::get_ControlType()
0x181fab  stloc.3
0x181fac  ldarg.1
0x181fad  callvirt instance string System.Web.UI.ControlBuilder::get_SkinID()
0x181fb2  stloc.s  4
0x181fb4  ldarg.1
0x181fb5  callvirt instance class [mscorlib]System.Type System.Web.UI.ControlBuilder::get_ControlType()
0x181fba  ldloc.s  4
0x181fbc  call     object System.Web.UI.PageTheme::CreateSkinKey(class [mscorlib]System.Type controlType, string skinID)
0x181fc1  stloc.s  5
0x181fc3  ldarg.0
0x181fc4  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.PageThemeCodeDomTreeGenerator::_controlSkinTypeNameCollection
0x181fc9  ldloc.s  5
0x181fcb  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x181fd0  brfalse.s loc_182036
0x181fd2  ldloc.s  4
0x181fd4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x181fd9  brfalse.s loc_18200D
0x181fdb  ldstr    aPageThemeDefau// "Page_theme_default_theme_already_define"...
0x181fe0  ldc.i4.1
0x181fe1  newarr   [mscorlib]System.Object
0x181fe6  dup
0x181fe7  ldc.i4.0
0x181fe8  ldarg.1
0x181fe9  callvirt instance class [mscorlib]System.Type System.Web.UI.ControlBuilder::get_ControlType()
0x181fee  callvirt instance string [mscorlib]System.Type::get_FullName()
0x181ff3  stelem.ref
0x181ff4  call     string System.Web.SR::GetString(string name, object[] args)
0x181ff9  ldnull
0x181ffa  ldarg.1
0x181ffb  callvirt instance class System.Web.VirtualPath System.Web.UI.ControlBuilder::get_VirtualPath()
0x182000  ldnull
0x182001  ldarg.1
0x182002  callvirt instance int32 System.Web.UI.ControlBuilder::get_Line()
0x182007  newobj   instance void System.Web.HttpParseException::.ctor(string message, class [mscorlib]System.Exception innerException, class System.Web.VirtualPath virtualPath, string sourceCode, int32 line)
0x18200c  throw
0x18200d  ldstr    aPageThemeSkini// "Page_theme_skinID_already_defined"
0x182012  ldc.i4.1
0x182013  newarr   [mscorlib]System.Object
0x182018  dup
0x182019  ldc.i4.0
0x18201a  ldloc.s  4
0x18201c  stelem.ref
0x18201d  call     string System.Web.SR::GetString(string name, object[] args)
0x182022  ldnull
0x182023  ldarg.1
0x182024  callvirt instance class System.Web.VirtualPath System.Web.UI.ControlBuilder::get_VirtualPath()
0x182029  ldnull
0x18202a  ldarg.1
0x18202b  callvirt instance int32 System.Web.UI.ControlBuilder::get_Line()
0x182030  newobj   instance void System.Web.HttpParseException::.ctor(string message, class [mscorlib]System.Exception innerException, class System.Web.VirtualPath virtualPath, string sourceCode, int32 line)
0x182035  throw
0x182036  ldarg.0
0x182037  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Compilation.PageThemeCodeDomTreeGenerator::_controlSkinTypeNameCollection
0x18203c  ldloc.s  5
0x18203e  ldc.i4.1
0x18203f  box      [mscorlib]System.Boolean
0x182044  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x182049  ldarg.0
0x18204a  ldfld    class [mscorlib]System.Collections.ArrayList System.Web.Compilation.PageThemeCodeDomTreeGenerator::_controlSkinBuilderEntryList
0x18204f  ldarg.1
0x182050  ldloc.s  4
0x182052  newobj   instance void ControlSkinBuilderEntry::.ctor(class System.Web.UI.ControlBuilder builder, string skinID)
0x182057  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x18205c  pop
0x18205d  ldarg.1
0x18205e  callvirt instance class [mscorlib]System.Collections.ArrayList System.Web.UI.ControlBuilder::get_SubBuilders()
0x182063  brfalse.s loc_1820DA
0x182065  ldarg.1
0x182066  callvirt instance class [mscorlib]System.Collections.ArrayList System.Web.UI.ControlBuilder::get_SubBuilders()
0x18206b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x182070  stloc.s  6
0x182072  br.s     loc_1820BA
0x182074  ldloc.s  6
0x182076  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x18207b  stloc.s  7
0x18207d  ldloc.s  7
0x18207f  isinst   System.Web.UI.ControlBuilder
0x182084  brfalse.s loc_1820BA
0x182086  ldloc.0
0x182087  brfalse.s loc_1820A6
0x182089  ldtoken  System.Web.UI.Control
0x18208e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x182093  ldloc.s  7
0x182095  castclass System.Web.UI.ControlBuilder
0x18209a  callvirt instance class [mscorlib]System.Type System.Web.UI.ControlBuilder::get_ControlType()
0x18209f  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x1820a4  br.s     loc_1820A7
0x1820a6  ldc.i4.0
0x1820a7  stloc.s  8
0x1820a9  ldarg.0
0x1820aa  ldloc.s  7
0x1820ac  castclass System.Web.UI.ControlBuilder
0x1820b1  ldarg.2
0x1820b2  ldloc.s  8
0x1820b4  ldnull
0x1820b5  callvirt instance void System.Web.Compilation.BaseTemplateCodeDomTreeGenerator::BuildSourceDataTreeFromBuilder(class System.Web.UI.ControlBuilder builder, bool fInTemplate, bool topLevelControlInTemplate, class System.Web.UI.PropertyEntry pse)
0x1820ba  ldloc.s  6
0x1820bc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1820c1  brtrue.s loc_182074
0x1820c3  leave.s  loc_1820DA
0x1820c5  ldloc.s  6
0x1820c7  isinst   [mscorlib]System.IDisposable
0x1820cc  stloc.s  9
0x1820ce  ldloc.s  9
0x1820d0  brfalse.s loc_1820D9
0x1820d2  ldloc.s  9
0x1820d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1820d9  endfinally
0x1820da  ldarg.1
0x1820db  callvirt instance class [mscorlib]System.Collections.ICollection System.Web.UI.ControlBuilder::get_TemplatePropertyEntries()
0x1820e0  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x1820e5  stloc.s  0xA
0x1820e7  br.s     loc_182108
0x1820e9  ldloc.s  0xA
0x1820eb  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1820f0  castclass System.Web.UI.TemplatePropertyEntry
0x1820f5  stloc.s  0xB
0x1820f7  ldarg.0
0x1820f8  ldloc.s  0xB
0x1820fa  callvirt instance class System.Web.UI.ControlBuilder System.Web.UI.BuilderPropertyEntry::get_Builder()
0x1820ff  ldc.i4.1
0x182100  ldc.i4.0
0x182101  ldloc.s  0xB
0x182103  callvirt instance void System.Web.Compilation.BaseTemplateCodeDomTreeGenerator::BuildSourceDataTreeFromBuilder(class System.Web.UI.ControlBuilder builder, bool fInTemplate, bool topLevelControlInTemplate, class System.Web.UI.PropertyEntry pse)
0x182108  ldloc.s  0xA
0x18210a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x18210f  brtrue.s loc_1820E9
0x182111  leave.s  loc_182128
0x182113  ldloc.s  0xA
0x182115  isinst   [mscorlib]System.IDisposable
0x18211a  stloc.s  9
0x18211c  ldloc.s  9
0x18211e  brfalse.s loc_182127
0x182120  ldloc.s  9
0x182122  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x182127  endfinally
0x182128  ldarg.1
0x182129  callvirt instance class [mscorlib]System.Collections.ICollection System.Web.UI.ControlBuilder::get_ComplexPropertyEntries()
0x18212e  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x182133  stloc.s  0xC
0x182135  br.s     loc_182164
0x182137  ldloc.s  0xC
0x182139  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x18213e  castclass System.Web.UI.ComplexPropertyEntry
0x182143  stloc.s  0xD
0x182145  ldloc.s  0xD
0x182147  callvirt instance class System.Web.UI.ControlBuilder System.Web.UI.BuilderPropertyEntry::get_Builder()
0x18214c  isinst   System.Web.UI.StringPropertyBuilder
0x182151  brtrue.s loc_182164
0x182153  ldarg.0
0x182154  ldloc.s  0xD
0x182156  callvirt instance class System.Web.UI.ControlBuilder System.Web.UI.BuilderPropertyEntry::get_Builder()
0x18215b  ldarg.2
0x18215c  ldc.i4.0
0x18215d  ldloc.s  0xD
0x18215f  callvirt instance void System.Web.Compilation.BaseTemplateCodeDomTreeGenerator::BuildSourceDataTreeFromBuilder(class System.Web.UI.ControlBuilder builder, bool fInTemplate, bool topLevelControlInTemplate, class System.Web.UI.PropertyEntry pse)
0x182164  ldloc.s  0xC
0x182166  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x18216b  brtrue.s loc_182137
0x18216d  leave.s  loc_182184
0x18216f  ldloc.s  0xC
0x182171  isinst   [mscorlib]System.IDisposable
0x182176  stloc.s  9
0x182178  ldloc.s  9
0x18217a  brfalse.s loc_182183
0x18217c  ldloc.s  9
0x18217e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x182183  endfinally
0x182184  ldloc.1
0x182185  brtrue.s loc_182195
0x182187  ldarg.0
0x182188  ldarg.1
0x182189  ldloc.0
0x18218a  ldarg.2
0x18218b  ldarg.3
0x18218c  ldarg.s  4
0x18218e  ldloc.2
0x18218f  call     instance class [System]System.CodeDom.CodeMemberMethod System.Web.Compilation.BaseTemplateCodeDomTreeGenerator::BuildBuildMethod(class System.Web.UI.ControlBuilder builder, bool fTemplate, bool fInTemplate, bool topLevelControlInTemplate, class System.Web.UI.PropertyEntry pse, bool fControlSkin)
0x182194  pop
0x182195  ldloc.2
0x182196  brtrue.s loc_1821A8
0x182198  ldarg.1
0x182199  callvirt instance bool System.Web.UI.ControlBuilder::get_HasAspCode()
0x18219e  brfalse.s loc_1821A8
0x1821a0  ldarg.0
0x1821a1  ldarg.1
0x1821a2  ldloc.0
0x1821a3  call     instance void System.Web.Compilation.BaseTemplateCodeDomTreeGenerator::BuildRenderMethod(class System.Web.UI.ControlBuilder builder, bool fTemplate)
0x1821a8  ldarg.0
0x1821a9  ldarg.1
0x1821aa  call     instance void System.Web.Compilation.BaseTemplateCodeDomTreeGenerator::BuildExtractMethod(class System.Web.UI.ControlBuilder builder)
0x1821af  ldarg.0
0x1821b0  ldarg.1
0x1821b1  ldloc.2
0x1821b2  call     instance class [System]System.CodeDom.CodeMemberMethod System.Web.Compilation.BaseTemplateCodeDomTreeGenerator::BuildPropertyBindingMethod(class System.Web.UI.ControlBuilder builder, bool fControlSkin)
0x1821b7  pop
0x1821b8  ret
```
