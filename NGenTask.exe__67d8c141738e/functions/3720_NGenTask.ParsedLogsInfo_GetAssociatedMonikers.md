# NGenTask.ParsedLogsInfo::GetAssociatedMonikers

- ea: `0x3720`
- end: `0x3741`
- name: `NGenTask.ParsedLogsInfo::GetAssociatedMonikers`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x3720`

## pseudocode

```c

```

## disassembly

```asm
0x3720  ldarg.0
0x3721  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>> NGenTask.ParsedLogsInfo::m_containerAssociations
0x3726  ldarg.1
0x3727  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>>::ContainsKey(var<u1>)
0x372c  brfalse.s loc_373B
0x372e  ldarg.0
0x372f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>> NGenTask.ParsedLogsInfo::m_containerAssociations
0x3734  ldarg.1
0x3735  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class NGenTask.ContainerRootDirectoryInfo, class [System.Core]System.Collections.Generic.HashSet`1<string>>::get_Item(void)
0x373a  ret
0x373b  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x3740  ret
```
