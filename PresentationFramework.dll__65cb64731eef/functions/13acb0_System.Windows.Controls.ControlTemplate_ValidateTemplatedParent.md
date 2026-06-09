# System.Windows.Controls.ControlTemplate::ValidateTemplatedParent

- ea: `0x13acb0`
- end: `0x13ad26`
- name: `System.Windows.Controls.ControlTemplate::ValidateTemplatedParent`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xe6f0`
- `0x38c40`
- `0x38c70`
- `0x13acb0`

## string_xrefs

- `0x13acb3`: `templatedParent`
- `0x13acda`: `TemplateTargetTypeMismatch`
- `0x13ad15`: `MustNotTemplateUnassociatedControl`

## pseudocode

```c

```

## disassembly

```asm
0x13acb0  ldarg.1
0x13acb1  brtrue.s loc_13ACBE
0x13acb3  ldstr    aTemplatedparen// "templatedParent"
0x13acb8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13acbd  throw
0x13acbe  ldarg.0
0x13acbf  ldfld    class [mscorlib]System.Type System.Windows.Controls.ControlTemplate::_targetType
0x13acc4  ldnull
0x13acc5  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13acca  brfalse.s loc_13AD0C
0x13accc  ldarg.0
0x13accd  ldfld    class [mscorlib]System.Type System.Windows.Controls.ControlTemplate::_targetType
0x13acd2  ldarg.1
0x13acd3  callvirt instance bool [mscorlib]System.Type::IsInstanceOfType(object)
0x13acd8  brtrue.s loc_13AD0C
0x13acda  ldstr    aTemplatetarget// "TemplateTargetTypeMismatch"
0x13acdf  ldc.i4.2
0x13ace0  newarr   [mscorlib]System.Object
0x13ace5  dup
0x13ace6  ldc.i4.0
0x13ace7  ldarg.0
0x13ace8  ldfld    class [mscorlib]System.Type System.Windows.Controls.ControlTemplate::_targetType
0x13aced  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x13acf2  stelem.ref
0x13acf3  dup
0x13acf4  ldc.i4.1
0x13acf5  ldarg.1
0x13acf6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x13acfb  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x13ad00  stelem.ref
0x13ad01  call     string System.Windows.SR::Get(string id, object[] args)
0x13ad06  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x13ad0b  throw
0x13ad0c  ldarg.1
0x13ad0d  callvirt instance class System.Windows.FrameworkTemplate System.Windows.FrameworkElement::get_TemplateInternal()
0x13ad12  ldarg.0
0x13ad13  beq.s    loc_13AD25
0x13ad15  ldstr    aMustnottemplat// "MustNotTemplateUnassociatedControl"
0x13ad1a  call     string System.Windows.SR::Get(string id)
0x13ad1f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x13ad24  throw
0x13ad25  ret
```
