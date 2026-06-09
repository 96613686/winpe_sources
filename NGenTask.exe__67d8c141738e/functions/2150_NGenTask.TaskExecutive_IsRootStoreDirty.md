# NGenTask.TaskExecutive::IsRootStoreDirty

- ea: `0x2150`
- end: `0x2170`
- name: `NGenTask.TaskExecutive::IsRootStoreDirty`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1ad0`

## callees

- `0x20a0`
- `0x22e0`

## pseudocode

```c

```

## disassembly

```asm
0x2150  ldarg.0
0x2151  ldarg.0
0x2152  call     instance string NGenTask.TaskExecutive::NGenServiceRegistryRoot()
0x2157  ldstr    aListenedstate// "ListenedState"
0x215c  call     string [mscorlib]System.String::Concat(string, string)
0x2161  ldstr    aRootstoredirty// "RootstoreDirty"
0x2166  ldc.i4.0
0x2167  call     instance int32 NGenTask.TaskExecutive::GetRegistryFlagValue(string keyName, string valueName, [opt] int32 defaultValue)
0x216c  ldc.i4.0
0x216d  cgt.un
0x216f  ret
```
