# System.Windows.FrameworkElementFactory::ApplyAutoAliasRules

- ea: `0x15750`
- end: `0x1591f`
- name: `System.Windows.FrameworkElementFactory::ApplyAutoAliasRules`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14f90`

## callees

- `0x14a80`
- `0x14f10`
- `0x15750`
- `0x15920`
- `0x170d0`
- `0x2c620`
- `0x38c70`

## string_xrefs

- `0x157bc`: `Template`
- `0x157cf`: `TemplateSelector`

## pseudocode

```c

```

## disassembly

```asm
0x15750  ldtoken  System.Windows.Controls.ContentPresenter
0x15755  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1575a  ldarg.0
0x1575b  ldfld    class [mscorlib]System.Type System.Windows.FrameworkElementFactory::_type
0x15760  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x15765  brfalse  loc_158A7
0x1576a  ldarg.0
0x1576b  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ContentPresenter::ContentSourceProperty
0x15770  call     instance object System.Windows.FrameworkElementFactory::GetValue(class [WindowsBase]System.Windows.DependencyProperty dp)
0x15775  stloc.0
0x15776  ldloc.0
0x15777  ldsfld   object [WindowsBase]System.Windows.DependencyProperty::UnsetValue
0x1577c  beq.s    loc_15786
0x1577e  ldloc.0
0x1577f  castclass [mscorlib]System.String
0x15784  br.s     loc_1578B
0x15786  ldstr    aContent// "Content"
0x1578b  stloc.1
0x1578c  ldloc.1
0x1578d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15792  brtrue   loc_1591E
0x15797  ldarg.0
0x15798  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ContentPresenter::ContentProperty
0x1579d  call     instance bool System.Windows.FrameworkElementFactory::IsValueDefined(class [WindowsBase]System.Windows.DependencyProperty dp)
0x157a2  brtrue   loc_1591E
0x157a7  ldarg.0
0x157a8  ldfld    class System.Windows.FrameworkTemplate System.Windows.FrameworkElementFactory::_frameworkTemplate
0x157ad  callvirt instance class [mscorlib]System.Type System.Windows.FrameworkTemplate::get_TargetTypeInternal()
0x157b2  stloc.2
0x157b3  ldloc.1
0x157b4  ldloc.2
0x157b5  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::FromName(string, class [mscorlib]System.Type)
0x157ba  stloc.3
0x157bb  ldloc.1
0x157bc  ldstr    aTemplate// "Template"
0x157c1  call     string [mscorlib]System.String::Concat(string, string)
0x157c6  ldloc.2
0x157c7  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::FromName(string, class [mscorlib]System.Type)
0x157cc  stloc.s  4
0x157ce  ldloc.1
0x157cf  ldstr    aTemplateselect// "TemplateSelector"
0x157d4  call     string [mscorlib]System.String::Concat(string, string)
0x157d9  ldloc.2
0x157da  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::FromName(string, class [mscorlib]System.Type)
0x157df  stloc.s  5
0x157e1  ldloc.1
0x157e2  ldstr    aStringformat// "StringFormat"
0x157e7  call     string [mscorlib]System.String::Concat(string, string)
0x157ec  ldloc.2
0x157ed  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::FromName(string, class [mscorlib]System.Type)
0x157f2  stloc.s  6
0x157f4  ldloc.3
0x157f5  brtrue.s loc_1581D
0x157f7  ldloc.0
0x157f8  ldsfld   object [WindowsBase]System.Windows.DependencyProperty::UnsetValue
0x157fd  beq.s    loc_1581D
0x157ff  ldstr    aMissingcontent// "MissingContentSource"
0x15804  ldc.i4.2
0x15805  newarr   [mscorlib]System.Object
0x1580a  dup
0x1580b  ldc.i4.0
0x1580c  ldloc.1
0x1580d  stelem.ref
0x1580e  dup
0x1580f  ldc.i4.1
0x15810  ldloc.2
0x15811  stelem.ref
0x15812  call     string System.Windows.SR::Get(string id, object[] args)
0x15817  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1581c  throw
0x1581d  ldloc.3
0x1581e  brfalse.s loc_15831
0x15820  ldarg.0
0x15821  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ContentPresenter::ContentProperty
0x15826  ldloc.3
0x15827  newobj   instance void System.Windows.TemplateBindingExtension::.ctor(class [WindowsBase]System.Windows.DependencyProperty property)
0x1582c  call     instance void System.Windows.FrameworkElementFactory::SetValue(class [WindowsBase]System.Windows.DependencyProperty dp, object value)
0x15831  ldarg.0
0x15832  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ContentPresenter::ContentTemplateProperty
0x15837  call     instance bool System.Windows.FrameworkElementFactory::IsValueDefined(class [WindowsBase]System.Windows.DependencyProperty dp)
0x1583c  brtrue   loc_1591E
0x15841  ldarg.0
0x15842  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ContentPresenter::ContentTemplateSelectorProperty
0x15847  call     instance bool System.Windows.FrameworkElementFactory::IsValueDefined(class [WindowsBase]System.Windows.DependencyProperty dp)
0x1584c  brtrue   loc_1591E
0x15851  ldarg.0
0x15852  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ContentPresenter::ContentStringFormatProperty
0x15857  call     instance bool System.Windows.FrameworkElementFactory::IsValueDefined(class [WindowsBase]System.Windows.DependencyProperty dp)
0x1585c  brtrue   loc_1591E
0x15861  ldloc.s  4
0x15863  brfalse.s loc_15877
0x15865  ldarg.0
0x15866  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ContentPresenter::ContentTemplateProperty
0x1586b  ldloc.s  4
0x1586d  newobj   instance void System.Windows.TemplateBindingExtension::.ctor(class [WindowsBase]System.Windows.DependencyProperty property)
0x15872  call     instance void System.Windows.FrameworkElementFactory::SetValue(class [WindowsBase]System.Windows.DependencyProperty dp, object value)
0x15877  ldloc.s  5
0x15879  brfalse.s loc_1588D
0x1587b  ldarg.0
0x1587c  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ContentPresenter::ContentTemplateSelectorProperty
0x15881  ldloc.s  5
0x15883  newobj   instance void System.Windows.TemplateBindingExtension::.ctor(class [WindowsBase]System.Windows.DependencyProperty property)
0x15888  call     instance void System.Windows.FrameworkElementFactory::SetValue(class [WindowsBase]System.Windows.DependencyProperty dp, object value)
0x1588d  ldloc.s  6
0x1588f  brfalse  loc_1591E
0x15894  ldarg.0
0x15895  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ContentPresenter::ContentStringFormatProperty
0x1589a  ldloc.s  6
0x1589c  newobj   instance void System.Windows.TemplateBindingExtension::.ctor(class [WindowsBase]System.Windows.DependencyProperty property)
0x158a1  call     instance void System.Windows.FrameworkElementFactory::SetValue(class [WindowsBase]System.Windows.DependencyProperty dp, object value)
0x158a6  ret
0x158a7  ldtoken  System.Windows.Controls.GridViewRowPresenter
0x158ac  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x158b1  ldarg.0
0x158b2  ldfld    class [mscorlib]System.Type System.Windows.FrameworkElementFactory::_type
0x158b7  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x158bc  brfalse.s loc_1591E
0x158be  ldarg.0
0x158bf  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.GridViewRowPresenter::ContentProperty
0x158c4  call     instance bool System.Windows.FrameworkElementFactory::IsValueDefined(class [WindowsBase]System.Windows.DependencyProperty dp)
0x158c9  brtrue.s loc_158FC
0x158cb  ldarg.0
0x158cc  ldfld    class System.Windows.FrameworkTemplate System.Windows.FrameworkElementFactory::_frameworkTemplate
0x158d1  callvirt instance class [mscorlib]System.Type System.Windows.FrameworkTemplate::get_TargetTypeInternal()
0x158d6  stloc.s  7
0x158d8  ldstr    aContent// "Content"
0x158dd  ldloc.s  7
0x158df  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::FromName(string, class [mscorlib]System.Type)
0x158e4  stloc.s  8
0x158e6  ldloc.s  8
0x158e8  brfalse.s loc_158FC
0x158ea  ldarg.0
0x158eb  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.GridViewRowPresenter::ContentProperty
0x158f0  ldloc.s  8
0x158f2  newobj   instance void System.Windows.TemplateBindingExtension::.ctor(class [WindowsBase]System.Windows.DependencyProperty property)
0x158f7  call     instance void System.Windows.FrameworkElementFactory::SetValue(class [WindowsBase]System.Windows.DependencyProperty dp, object value)
0x158fc  ldarg.0
0x158fd  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.GridViewRowPresenterBase::ColumnsProperty
0x15902  call     instance bool System.Windows.FrameworkElementFactory::IsValueDefined(class [WindowsBase]System.Windows.DependencyProperty dp)
0x15907  brtrue.s loc_1591E
0x15909  ldarg.0
0x1590a  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.GridViewRowPresenterBase::ColumnsProperty
0x1590f  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.GridView::ColumnCollectionProperty
0x15914  newobj   instance void System.Windows.TemplateBindingExtension::.ctor(class [WindowsBase]System.Windows.DependencyProperty property)
0x15919  call     instance void System.Windows.FrameworkElementFactory::SetValue(class [WindowsBase]System.Windows.DependencyProperty dp, object value)
0x1591e  ret
```
