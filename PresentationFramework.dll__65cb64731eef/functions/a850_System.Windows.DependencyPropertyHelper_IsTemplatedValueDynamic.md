# System.Windows.DependencyPropertyHelper::IsTemplatedValueDynamic

- ea: `0xa850`
- end: `0xa8a5`
- name: `System.Windows.DependencyPropertyHelper::IsTemplatedValueDynamic`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0xa850`
- `0x209f0`
- `0x38c40`
- `0x1d8e20`
- `0x1d9000`
- `0x1d9030`

## string_xrefs

- `0xa853`: `elementInTemplate`
- `0xa889`: `elementInTemplate`
- `0xa87f`: `ElementMustBelongToTemplate`

## pseudocode

```c

```

## disassembly

```asm
0xa850  ldarg.0
0xa851  brtrue.s loc_A85E
0xa853  ldstr    aElementintempl// "elementInTemplate"
0xa858  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa85d  throw
0xa85e  ldarg.1
0xa85f  brtrue.s loc_A86C
0xa861  ldstr    aDependencyprop// "dependencyProperty"
0xa866  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa86b  throw
0xa86c  ldloca.s 0
0xa86e  ldarg.0
0xa86f  call     instance void MS.Internal.FrameworkObject::.ctor(class [WindowsBase]System.Windows.DependencyObject d)
0xa874  ldloca.s 0
0xa876  call     instance class [WindowsBase]System.Windows.DependencyObject MS.Internal.FrameworkObject::get_TemplatedParent()
0xa87b  stloc.1
0xa87c  ldloc.1
0xa87d  brtrue.s loc_A894
0xa87f  ldstr    aElementmustbel// "ElementMustBelongToTemplate"
0xa884  call     string System.Windows.SR::Get(string id)
0xa889  ldstr    aElementintempl// "elementInTemplate"
0xa88e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xa893  throw
0xa894  ldloca.s 0
0xa896  call     instance int32 MS.Internal.FrameworkObject::get_TemplateChildIndex()
0xa89b  stloc.2
0xa89c  ldloc.1
0xa89d  ldloc.2
0xa89e  ldarg.1
0xa89f  call     bool System.Windows.StyleHelper::IsValueDynamic(class [WindowsBase]System.Windows.DependencyObject container, int32 childIndex, class [WindowsBase]System.Windows.DependencyProperty dp)
0xa8a4  ret
```
