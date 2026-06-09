# NGenTask.LogsParser::AddNewILAssembly

- ea: `0x3c10`
- end: `0x3ca9`
- name: `NGenTask.LogsParser::AddNewILAssembly`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x3930`

## callees

- `0x100`
- `0x2c30`
- `0x2d30`
- `0x2d50`
- `0x2dd0`
- `0x34a0`
- `0x35d0`
- `0x3c10`

## pseudocode

```c

```

## disassembly

```asm
0x3c10  ldarg.2
0x3c11  ldarg.3
0x3c12  bne.un.s loc_3C2F
0x3c14  ldarg.s  5
0x3c16  brtrue.s loc_3C23
0x3c18  ldarg.1
0x3c19  call     bool NGenTask.TaskHelper::IsAssemblyInGac(string assemblyPath)
0x3c1e  ldc.i4.0
0x3c1f  ceq
0x3c21  br.s     loc_3C2C
0x3c23  ldarg.1
0x3c24  call     bool NGenTask.TaskHelper::IsFrameworkAssemblyInGac(string assemblyPath)
0x3c29  ldc.i4.0
0x3c2a  ceq
0x3c2c  brfalse.s loc_3C2F
0x3c2e  ret
0x3c2f  ldarg.3
0x3c30  ldc.i4.m1
0x3c31  beq.s    loc_3C41
0x3c33  ldarg.2
0x3c34  ldarg.s  4
0x3c36  bne.un.s loc_3C41
0x3c38  ldarg.1
0x3c39  call     bool NGenTask.TaskHelper::IsFirstPartyWinMD(string assemblyPath)
0x3c3e  brtrue.s loc_3C41
0x3c40  ret
0x3c41  ldarg.3
0x3c42  ldc.i4.m1
0x3c43  bne.un.s loc_3C53
0x3c45  ldarg.2
0x3c46  ldarg.s  4
0x3c48  bne.un.s loc_3C53
0x3c4a  ldarg.1
0x3c4b  call     bool NGenTask.TaskHelper::IsFirstPartyWinMD(string assemblyPath)
0x3c50  brfalse.s loc_3C53
0x3c52  ret
0x3c53  ldarg.s  8
0x3c55  ldarg.1
0x3c56  callvirt instance bool NGenTask.ExcludeList::Contains(string assembly)
0x3c5b  brfalse.s loc_3C73
0x3c5d  ldc.i4.3
0x3c5e  ldstr    aSkippingAssemb// "Skipping assembly \"{0}\" because it is"...
0x3c63  ldc.i4.1
0x3c64  newarr   [mscorlib]System.Object
0x3c69  dup
0x3c6a  ldc.i4.0
0x3c6b  ldarg.1
0x3c6c  stelem.ref
0x3c6d  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x3c72  ret
0x3c73  ldarg.s  6
0x3c75  ldarg.2
0x3c76  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class NGenTask.BindingContext>::ContainsKey(var<u1>)
0x3c7b  brfalse.s loc_3CA8
0x3c7d  ldarg.s  6
0x3c7f  ldarg.2
0x3c80  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class NGenTask.BindingContext>::get_Item(void)
0x3c85  stloc.0
0x3c86  ldarg.2
0x3c87  ldarg.s  4
0x3c89  bne.un.s loc_3C98
0x3c8b  ldarg.3
0x3c8c  ldc.i4.m1
0x3c8d  beq.s    loc_3C98
0x3c8f  ldarg.s  6
0x3c91  ldarg.3
0x3c92  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class NGenTask.BindingContext>::get_Item(void)
0x3c97  stloc.0
0x3c98  ldloc.0
0x3c99  ldarg.1
0x3c9a  newobj   instance void NGenTask.ILAssembly::.ctor(class NGenTask.BindingContext context, string assembly)
0x3c9f  stloc.1
0x3ca0  ldarg.s  7
0x3ca2  ldloc.1
0x3ca3  callvirt instance void NGenTask.ParsedLogsInfo::AddNewILAssembly(class NGenTask.ILAssembly newILAssembly)
0x3ca8  ret
```
