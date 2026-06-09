# NGenTask.TaskHelper::IsAssemblyInGac

- ea: `0x2d30`
- end: `0x2d41`
- name: `NGenTask.TaskHelper::IsAssemblyInGac`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x3c10`

## pseudocode

```c

```

## disassembly

```asm
0x2d30  ldsfld   class [System]System.Text.RegularExpressions.Regex NGenTask.TaskHelper::s_assemblyNameRegex
0x2d35  ldarg.0
0x2d36  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string)
0x2d3b  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x2d40  ret
```
