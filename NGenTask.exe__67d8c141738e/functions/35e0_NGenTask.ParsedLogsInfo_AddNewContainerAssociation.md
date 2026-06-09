# NGenTask.ParsedLogsInfo::AddNewContainerAssociation

- ea: `0x35e0`
- end: `0x3613`
- name: `NGenTask.ParsedLogsInfo::AddNewContainerAssociation`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x3620`
- `0x3930`

## callees

- `0x35e0`

## pseudocode

```c

```

## disassembly

```asm
0x35e0  ldarg.0
0x35e1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>> NGenTask.ParsedLogsInfo::m_containerAssociations
0x35e6  ldarg.1
0x35e7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>>::ContainsKey(var<u1>)
0x35ec  brtrue.s loc_35FF
0x35ee  ldarg.0
0x35ef  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>> NGenTask.ParsedLogsInfo::m_containerAssociations
0x35f4  ldarg.1
0x35f5  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x35fa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>>::set_Item(var<u1>, !!T0)
0x35ff  ldarg.0
0x3600  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>> NGenTask.ParsedLogsInfo::m_containerAssociations
0x3605  ldarg.1
0x3606  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>>::get_Item(void)
0x360b  ldarg.2
0x360c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x3611  pop
0x3612  ret
```
