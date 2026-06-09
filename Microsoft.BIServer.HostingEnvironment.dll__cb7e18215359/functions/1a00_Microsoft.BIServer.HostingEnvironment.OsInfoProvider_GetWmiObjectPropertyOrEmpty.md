# Microsoft.BIServer.HostingEnvironment.OsInfoProvider::GetWmiObjectPropertyOrEmpty

- ea: `0x1a00`
- end: `0x1a3b`
- name: `Microsoft.BIServer.HostingEnvironment.OsInfoProvider::GetWmiObjectPropertyOrEmpty`
- size: `59`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1aa0`
- `0x1ad0`
- `0x1af0`
- `0x1b10`
- `0x1b40`
- `0x58a0`

## callees

- `0x1a00`

## pseudocode

```c

```

## disassembly

```asm
0x1a00  ldarg.1
0x1a01  brtrue.s loc_1A06
0x1a03  ldnull
0x1a04  br.s     loc_1A31
0x1a06  ldarg.1
0x1a07  callvirt instance class [System.Management]System.Management.PropertyDataCollection [System.Management]System.Management.ManagementBaseObject::get_Properties()
0x1a0c  dup
0x1a0d  brtrue.s loc_1A13
0x1a0f  pop
0x1a10  ldnull
0x1a11  br.s     loc_1A31
0x1a13  ldarg.2
0x1a14  callvirt instance class [System.Management]System.Management.PropertyData [System.Management]System.Management.PropertyDataCollection::get_Item(string)
0x1a19  dup
0x1a1a  brtrue.s loc_1A20
0x1a1c  pop
0x1a1d  ldnull
0x1a1e  br.s     loc_1A31
0x1a20  call     instance object [System.Management]System.Management.PropertyData::get_Value()
0x1a25  dup
0x1a26  brtrue.s loc_1A2C
0x1a28  pop
0x1a29  ldnull
0x1a2a  br.s     loc_1A31
0x1a2c  callvirt instance string [mscorlib]System.Object::ToString()
0x1a31  dup
0x1a32  brtrue.s loc_1A3A
0x1a34  pop
0x1a35  ldstr    asc_7C08// ""
0x1a3a  ret
```
