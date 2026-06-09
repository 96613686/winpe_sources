# System.Xml.Xsl.Xslt.CompilerScopeManager`1::.ctor

- ea: `0x13e70`
- end: `0x13ec3`
- name: `System.Xml.Xsl.Xslt.CompilerScopeManager`1::.ctor`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x13eb8`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c

```

## disassembly

```asm
0x13e70  ldarg.0
0x13e71  ldc.i4.s 0x20
0x13e73  newarr   valuetype ScopeRecord<var<u1>>
0x13e78  stfld    valuetype ScopeRecord<var<u1>>[] class System.Xml.Xsl.Xslt.CompilerScopeManager`1<var<u1>>::records
0x13e7d  ldarg.0
0x13e7e  call     instance void [mscorlib]System.Object::.ctor()
0x13e83  ldarg.0
0x13e84  ldfld    valuetype ScopeRecord<var<u1>>[] class System.Xml.Xsl.Xslt.CompilerScopeManager`1<var<u1>>::records
0x13e89  ldc.i4.0
0x13e8a  ldelema  valuetype ScopeRecord<var<u1>>
0x13e8f  ldc.i4.s 0x10
0x13e91  stfld    valuetype ScopeFlags<var<u1>> valuetype ScopeRecord<var<u1>>::flags
0x13e96  ldarg.0
0x13e97  ldfld    valuetype ScopeRecord<var<u1>>[] class System.Xml.Xsl.Xslt.CompilerScopeManager`1<var<u1>>::records
0x13e9c  ldc.i4.0
0x13e9d  ldelema  valuetype ScopeRecord<var<u1>>
0x13ea2  ldstr    aXml// "xml"
0x13ea7  stfld    string valuetype ScopeRecord<var<u1>>::ncName
0x13eac  ldarg.0
0x13ead  ldfld    valuetype ScopeRecord<var<u1>>[] class System.Xml.Xsl.Xslt.CompilerScopeManager`1<var<u1>>::records
0x13eb2  ldc.i4.0
0x13eb3  ldelema  valuetype ScopeRecord<var<u1>>
0x13eb8  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x13ebd  stfld    string valuetype ScopeRecord<var<u1>>::nsUri
0x13ec2  ret
```
