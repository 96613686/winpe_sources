# NGenTask.TaskHelper::IsFrameworkAssemblyInGac

- ea: `0x2d50`
- end: `0x2dc1`
- name: `NGenTask.TaskHelper::IsFrameworkAssemblyInGac`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x3c10`

## callees

- `0x2d50`

## pseudocode

```c

```

## disassembly

```asm
0x2d50  ldsfld   class [System]System.Text.RegularExpressions.Regex NGenTask.TaskHelper::s_assemblyNameRegex
0x2d55  ldarg.0
0x2d56  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string)
0x2d5b  stloc.0
0x2d5c  ldloc.0
0x2d5d  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x2d62  brtrue.s loc_2D66
0x2d64  ldc.i4.0
0x2d65  ret
0x2d66  ldsfld   class [mscorlib]System.Reflection.MethodInfo NGenTask.TaskHelper::s_isFrameworkAssembly
0x2d6b  ldnull
0x2d6c  call     bool [mscorlib]System.Reflection.MethodInfo::op_Equality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x2d71  brfalse.s loc_2DA1
0x2d73  ldtoken  [mscorlib]System.Object
0x2d78  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d7d  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetAssembly(class [mscorlib]System.Type)
0x2d82  stloc.1
0x2d83  ldloc.1
0x2d84  ldstr    aSystemReflecti// "System.Reflection.RuntimeAssembly"
0x2d89  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x2d8e  stloc.2
0x2d8f  ldloc.2
0x2d90  ldstr    aIsframeworkass// "IsFrameworkAssembly"
0x2d95  ldc.i4.s 0x28
0x2d97  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x2d9c  stsfld   class [mscorlib]System.Reflection.MethodInfo NGenTask.TaskHelper::s_isFrameworkAssembly
0x2da1  ldsfld   class [mscorlib]System.Reflection.MethodInfo NGenTask.TaskHelper::s_isFrameworkAssembly
0x2da6  ldnull
0x2da7  ldc.i4.1
0x2da8  newarr   [mscorlib]System.Object
0x2dad  dup
0x2dae  ldc.i4.0
0x2daf  ldarg.0
0x2db0  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor(string)
0x2db5  stelem.ref
0x2db6  callvirt instance object [mscorlib]System.Reflection.MethodBase::Invoke(object, object[])
0x2dbb  unbox.any [mscorlib]System.Boolean
0x2dc0  ret
```
