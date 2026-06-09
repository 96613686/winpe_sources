# NGenTask.ContainerDirectoryInfo::Equals

- ea: `0x3e20`
- end: `0x3e91`
- name: `NGenTask.ContainerDirectoryInfo::Equals`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x3de0`
- `0x3e00`
- `0x3e20`

## pseudocode

```c

```

## disassembly

```asm
0x3e20  ldarg.1
0x3e21  isinst   NGenTask.ContainerDirectoryInfo
0x3e26  stloc.0
0x3e27  ldloc.0
0x3e28  ldarg.0
0x3e29  bne.un.s loc_3E2D
0x3e2b  ldc.i4.1
0x3e2c  ret
0x3e2d  ldarg.0
0x3e2e  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e33  ldarg.1
0x3e34  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e39  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3e3e  brfalse.s loc_3E42
0x3e40  ldc.i4.0
0x3e41  ret
0x3e42  ldloc.0
0x3e43  brfalse.s loc_3E8F
0x3e45  ldloc.0
0x3e46  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x3e4b  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x3e50  ldarg.0
0x3e51  call     instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x3e56  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x3e5b  callvirt instance bool [mscorlib]System.String::Equals(string)
0x3e60  brfalse.s loc_3E8D
0x3e62  ldarg.0
0x3e63  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e68  ldtoken  NGenTask.ContainerRootDirectoryInfo
0x3e6d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3e72  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3e77  brtrue.s loc_3E8B
0x3e79  ldloc.0
0x3e7a  callvirt instance class NGenTask.ContainerRootDirectoryInfo NGenTask.ContainerDirectoryInfo::get_Root()
0x3e7f  ldarg.0
0x3e80  call     instance class NGenTask.ContainerRootDirectoryInfo NGenTask.ContainerDirectoryInfo::get_Root()
0x3e85  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x3e8a  ret
0x3e8b  ldc.i4.1
0x3e8c  ret
0x3e8d  ldc.i4.0
0x3e8e  ret
0x3e8f  ldc.i4.0
0x3e90  ret
```
