# RSManagedCrypto.StoreHelper::GetKeyPath

- ea: `0x2070`
- end: `0x208b`
- name: `RSManagedCrypto.StoreHelper::GetKeyPath`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2540`

## string_xrefs

- `0x2070`: `Software\Microsoft\Microsoft SQL Server\Reporting Services\Service Applications\`

## pseudocode

```c

```

## disassembly

```asm
0x2070  ldstr    aSoftwareMicros// "Software\\Microsoft\\Microsoft SQL Serv"...
0x2075  ldarg.0
0x2076  box      [mscorlib]System.Guid
0x207b  call     string [mscorlib]System.String::Concat(object, object)
0x2080  ldstr    aKeytransform// "\\KeyTransform"
0x2085  call     string [mscorlib]System.String::Concat(string, string)
0x208a  ret
```
