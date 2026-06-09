# System.Windows.Controls.ItemsPanelTemplate::ValidateTemplatedParent

- ea: `0x17b8f0`
- end: `0x17b933`
- name: `System.Windows.Controls.ItemsPanelTemplate::ValidateTemplatedParent`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x38c70`
- `0x17b8f0`

## string_xrefs

- `0x17b8f3`: `templatedParent`
- `0x17b906`: `TemplateTargetTypeMismatch`

## pseudocode

```c

```

## disassembly

```asm
0x17b8f0  ldarg.1
0x17b8f1  brtrue.s loc_17B8FE
0x17b8f3  ldstr    aTemplatedparen// "templatedParent"
0x17b8f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x17b8fd  throw
0x17b8fe  ldarg.1
0x17b8ff  isinst   System.Windows.Controls.ItemsPresenter
0x17b904  brtrue.s loc_17B932
0x17b906  ldstr    aTemplatetarget// "TemplateTargetTypeMismatch"
0x17b90b  ldc.i4.2
0x17b90c  newarr   [mscorlib]System.Object
0x17b911  dup
0x17b912  ldc.i4.0
0x17b913  ldstr    aItemspresenter// "ItemsPresenter"
0x17b918  stelem.ref
0x17b919  dup
0x17b91a  ldc.i4.1
0x17b91b  ldarg.1
0x17b91c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x17b921  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x17b926  stelem.ref
0x17b927  call     string System.Windows.SR::Get(string id, object[] args)
0x17b92c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x17b931  throw
0x17b932  ret
```
