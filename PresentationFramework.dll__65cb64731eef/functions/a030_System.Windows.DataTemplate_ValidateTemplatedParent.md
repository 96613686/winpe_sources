# System.Windows.DataTemplate::ValidateTemplatedParent

- ea: `0xa030`
- end: `0xa073`
- name: `System.Windows.DataTemplate::ValidateTemplatedParent`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0xa030`
- `0x38c70`

## string_xrefs

- `0xa033`: `templatedParent`
- `0xa046`: `TemplateTargetTypeMismatch`

## pseudocode

```c

```

## disassembly

```asm
0xa030  ldarg.1
0xa031  brtrue.s loc_A03E
0xa033  ldstr    aTemplatedparen// "templatedParent"
0xa038  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa03d  throw
0xa03e  ldarg.1
0xa03f  isinst   System.Windows.Controls.ContentPresenter
0xa044  brtrue.s loc_A072
0xa046  ldstr    aTemplatetarget// "TemplateTargetTypeMismatch"
0xa04b  ldc.i4.2
0xa04c  newarr   [mscorlib]System.Object
0xa051  dup
0xa052  ldc.i4.0
0xa053  ldstr    aContentpresent// "ContentPresenter"
0xa058  stelem.ref
0xa059  dup
0xa05a  ldc.i4.1
0xa05b  ldarg.1
0xa05c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xa061  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xa066  stelem.ref
0xa067  call     string System.Windows.SR::Get(string id, object[] args)
0xa06c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xa071  throw
0xa072  ret
```
