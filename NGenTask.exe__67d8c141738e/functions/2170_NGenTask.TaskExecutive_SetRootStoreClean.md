# NGenTask.TaskExecutive::SetRootStoreClean

- ea: `0x2170`
- end: `0x218d`
- name: `NGenTask.TaskExecutive::SetRootStoreClean`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1ad0`

## callees

- `0x20a0`
- `0x23e0`

## pseudocode

```c

```

## disassembly

```asm
0x2170  ldarg.0
0x2171  ldarg.0
0x2172  call     instance string NGenTask.TaskExecutive::NGenServiceRegistryRoot()
0x2177  ldstr    aListenedstate// "ListenedState"
0x217c  call     string [mscorlib]System.String::Concat(string, string)
0x2181  ldstr    aRootstoredirty// "RootstoreDirty"
0x2186  ldc.i4.0
0x2187  call     instance void NGenTask.TaskExecutive::SetRegistryFlagValue(string keyName, string valueName, int32 value)
0x218c  ret
```
