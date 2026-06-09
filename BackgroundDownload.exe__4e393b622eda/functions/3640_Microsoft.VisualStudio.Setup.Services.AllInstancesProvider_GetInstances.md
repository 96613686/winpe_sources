# Microsoft.VisualStudio.Setup.Services.AllInstancesProvider::GetInstances

- ea: `0x3640`
- end: `0x366b`
- name: `Microsoft.VisualStudio.Setup.Services.AllInstancesProvider::GetInstances`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x3640`

## pseudocode

```c

```

## disassembly

```asm
0x3640  ldarg.1
0x3641  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IQuery::GetInstances()
0x3646  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance, string> <>c::<>9__0_0
0x364b  dup
0x364c  brtrue.s loc_3665
0x364e  pop
0x364f  ldsfld   class <>c <>c::<>9
0x3654  ldftn    instance string <>c::<GetInstances>b__0_0(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance v)
0x365a  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance, string>::.ctor(object, native int)
0x365f  dup
0x3660  stsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance, string> <>c::<>9__0_0
0x3665  call     T0x2B000045
0x366a  ret
```
