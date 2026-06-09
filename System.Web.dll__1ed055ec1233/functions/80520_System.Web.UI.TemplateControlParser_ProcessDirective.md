# System.Web.UI.TemplateControlParser::ProcessDirective

- ea: `0x80520`
- end: `0x806c2`
- name: `System.Web.UI.TemplateControlParser::ProcessDirective`
- size: `418`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x6eda0`
- `0x782d0`

## callees

- `0x18990`
- `0x31460`
- `0x31470`
- `0x34f20`
- `0x34fa0`
- `0x58d50`
- `0x5b610`
- `0x5b740`
- `0x71020`
- `0x80520`
- `0x80960`
- `0x80d90`
- `0x80e90`
- `0x85580`
- `0x85790`

## string_xrefs

- `0x80595`: `virtualpath`
- `0x80521`: `outputcache`

## pseudocode

```c

```

## disassembly

```asm
0x80520  ldarg.1
0x80521  ldstr    aOutputcache// "outputcache"
0x80526  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x8052b  brfalse.s loc_8057B
0x8052d  ldarg.0
0x8052e  callvirt instance bool System.Web.UI.TemplateParser::get_FInDesigner()
0x80533  brfalse.s loc_80536
0x80535  ret
0x80536  ldarg.0
0x80537  ldfld    class System.Web.UI.OutputCacheParameters System.Web.UI.TemplateControlParser::_outputCacheSettings
0x8053c  brtrue.s loc_80549
0x8053e  ldarg.0
0x8053f  newobj   instance void System.Web.UI.OutputCacheParameters::.ctor()
0x80544  stfld    class System.Web.UI.OutputCacheParameters System.Web.UI.TemplateControlParser::_outputCacheSettings
0x80549  ldarg.0
0x8054a  ldfld    class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControlParser::_outputCacheDirective
0x8054f  brfalse.s loc_8056B
0x80551  ldstr    aOnlyOneDirecti// "Only_one_directive_allowed"
0x80556  ldc.i4.1
0x80557  newarr   [mscorlib]System.Object
0x8055c  dup
0x8055d  ldc.i4.0
0x8055e  ldarg.1
0x8055f  stelem.ref
0x80560  call     string System.Web.SR::GetString(string name, object[] args)
0x80565  newobj   instance void System.Web.HttpException::.ctor(string message)
0x8056a  throw
0x8056b  ldarg.0
0x8056c  ldarg.1
0x8056d  ldarg.2
0x8056e  callvirt instance void System.Web.UI.TemplateControlParser::ProcessOutputCacheDirective(string directiveName, class [mscorlib]System.Collections.IDictionary directive)
0x80573  ldarg.0
0x80574  ldarg.2
0x80575  stfld    class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControlParser::_outputCacheDirective
0x8057a  ret
0x8057b  ldarg.1
0x8057c  ldstr    aReference// "reference"
0x80581  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x80586  brfalse  loc_806B9
0x8058b  ldarg.0
0x8058c  callvirt instance bool System.Web.UI.TemplateParser::get_FInDesigner()
0x80591  brfalse.s loc_80594
0x80593  ret
0x80594  ldarg.2
0x80595  ldstr    aVirtualpath_1// "virtualpath"
0x8059a  call     class System.Web.VirtualPath System.Web.UI.Util::GetAndRemoveVirtualPathAttribute(class [mscorlib]System.Collections.IDictionary directives, string key)
0x8059f  stloc.0
0x805a0  ldc.i4.0
0x805a1  stloc.1
0x805a2  ldc.i4.0
0x805a3  stloc.2
0x805a4  ldarg.2
0x805a5  ldstr    aPage_0// "page"
0x805aa  call     class System.Web.VirtualPath System.Web.UI.Util::GetAndRemoveVirtualPathAttribute(class [mscorlib]System.Collections.IDictionary directives, string key)
0x805af  stloc.3
0x805b0  ldloc.3
0x805b1  ldnull
0x805b2  call     bool System.Web.VirtualPath::op_Inequality(class System.Web.VirtualPath v1, class System.Web.VirtualPath v2)
0x805b7  brfalse.s loc_805D7
0x805b9  ldloc.0
0x805ba  ldnull
0x805bb  call     bool System.Web.VirtualPath::op_Inequality(class System.Web.VirtualPath v1, class System.Web.VirtualPath v2)
0x805c0  brfalse.s loc_805D3
0x805c2  ldarg.0
0x805c3  ldstr    aInvalidReferen// "Invalid_reference_directive"
0x805c8  call     string System.Web.SR::GetString(string name)
0x805cd  call     instance void System.Web.UI.TemplateParser::ProcessError(string message)
0x805d2  ret
0x805d3  ldloc.3
0x805d4  stloc.0
0x805d5  ldc.i4.1
0x805d6  stloc.1
0x805d7  ldarg.2
0x805d8  ldstr    aControl// "control"
0x805dd  call     class System.Web.VirtualPath System.Web.UI.Util::GetAndRemoveVirtualPathAttribute(class [mscorlib]System.Collections.IDictionary directives, string key)
0x805e2  stloc.3
0x805e3  ldloc.3
0x805e4  ldnull
0x805e5  call     bool System.Web.VirtualPath::op_Inequality(class System.Web.VirtualPath v1, class System.Web.VirtualPath v2)
0x805ea  brfalse.s loc_8060A
0x805ec  ldloc.0
0x805ed  ldnull
0x805ee  call     bool System.Web.VirtualPath::op_Inequality(class System.Web.VirtualPath v1, class System.Web.VirtualPath v2)
0x805f3  brfalse.s loc_80606
0x805f5  ldarg.0
0x805f6  ldstr    aInvalidReferen// "Invalid_reference_directive"
0x805fb  call     string System.Web.SR::GetString(string name)
0x80600  call     instance void System.Web.UI.TemplateParser::ProcessError(string message)
0x80605  ret
0x80606  ldloc.3
0x80607  stloc.0
0x80608  ldc.i4.1
0x80609  stloc.2
0x8060a  ldloc.0
0x8060b  ldnull
0x8060c  call     bool System.Web.VirtualPath::op_Equality(class System.Web.VirtualPath v1, class System.Web.VirtualPath v2)
0x80611  brfalse.s loc_80624
0x80613  ldarg.0
0x80614  ldstr    aInvalidReferen// "Invalid_reference_directive"
0x80619  call     string System.Web.SR::GetString(string name)
0x8061e  call     instance void System.Web.UI.TemplateParser::ProcessError(string message)
0x80623  ret
0x80624  ldarg.0
0x80625  ldloc.0
0x80626  call     instance class [mscorlib]System.Type System.Web.UI.BaseTemplateParser::GetReferencedType(class System.Web.VirtualPath virtualPath)
0x8062b  stloc.s  4
0x8062d  ldloc.s  4
0x8062f  ldnull
0x80630  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x80635  brfalse.s loc_80651
0x80637  ldarg.0
0x80638  ldstr    aInvalidReferen_0// "Invalid_reference_directive_attrib"
0x8063d  ldc.i4.1
0x8063e  newarr   [mscorlib]System.Object
0x80643  dup
0x80644  ldc.i4.0
0x80645  ldloc.0
0x80646  stelem.ref
0x80647  call     string System.Web.SR::GetString(string name, object[] args)
0x8064c  call     instance void System.Web.UI.TemplateParser::ProcessError(string message)
0x80651  ldloc.1
0x80652  brfalse.s loc_80681
0x80654  ldtoken  System.Web.UI.Page
0x80659  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8065e  ldloc.s  4
0x80660  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x80665  brtrue.s loc_80681
0x80667  ldarg.0
0x80668  ldstr    aInvalidReferen_0// "Invalid_reference_directive_attrib"
0x8066d  ldc.i4.1
0x8066e  newarr   [mscorlib]System.Object
0x80673  dup
0x80674  ldc.i4.0
0x80675  ldloc.0
0x80676  stelem.ref
0x80677  call     string System.Web.SR::GetString(string name, object[] args)
0x8067c  call     instance void System.Web.UI.TemplateParser::ProcessError(string message)
0x80681  ldloc.2
0x80682  brfalse.s loc_806B1
0x80684  ldtoken  System.Web.UI.UserControl
0x80689  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8068e  ldloc.s  4
0x80690  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x80695  brtrue.s loc_806B1
0x80697  ldarg.0
0x80698  ldstr    aInvalidReferen_0// "Invalid_reference_directive_attrib"
0x8069d  ldc.i4.1
0x8069e  newarr   [mscorlib]System.Object
0x806a3  dup
0x806a4  ldc.i4.0
0x806a5  ldloc.0
0x806a6  stelem.ref
0x806a7  call     string System.Web.SR::GetString(string name, object[] args)
0x806ac  call     instance void System.Web.UI.TemplateParser::ProcessError(string message)
0x806b1  ldarg.1
0x806b2  ldarg.2
0x806b3  call     void System.Web.UI.Util::CheckUnknownDirectiveAttributes(string directiveName, class [mscorlib]System.Collections.IDictionary directive)
0x806b8  ret
0x806b9  ldarg.0
0x806ba  ldarg.1
0x806bb  ldarg.2
0x806bc  call     instance void System.Web.UI.BaseTemplateParser::ProcessDirective(string directiveName, class [mscorlib]System.Collections.IDictionary directive)
0x806c1  ret
```
