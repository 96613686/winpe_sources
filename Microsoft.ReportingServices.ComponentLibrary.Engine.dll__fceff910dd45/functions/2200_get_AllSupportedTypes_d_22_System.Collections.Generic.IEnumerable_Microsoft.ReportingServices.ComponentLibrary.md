# <get_AllSupportedTypes>d__22::System.Collections.Generic.IEnumerable<Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType>.GetEnumerator

- ea: `0x2200`
- end: `0x222b`
- name: `<get_AllSupportedTypes>d__22::System.Collections.Generic.IEnumerable<Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType>.GetEnumerator`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2230`

## callees

- `0x20a0`
- `0x2200`

## pseudocode

```c

```

## disassembly

```asm
0x2200  ldarg.0
0x2201  ldfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x2206  ldc.i4.s 0xFE
0x2208  bne.un.s loc_2222
0x220a  ldarg.0
0x220b  ldfld    int32 <get_AllSupportedTypes>d__22::<>l__initialThreadId
0x2210  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0x2215  bne.un.s loc_2222
0x2217  ldarg.0
0x2218  ldc.i4.0
0x2219  stfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x221e  ldarg.0
0x221f  stloc.0
0x2220  br.s     loc_2229
0x2222  ldc.i4.0
0x2223  newobj   instance void <get_AllSupportedTypes>d__22::.ctor(int32 <>1__state)
0x2228  stloc.0
0x2229  ldloc.0
0x222a  ret
```
