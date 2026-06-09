# Microsoft.BIServer.HostingEnvironment.ManagementObjectEnumeratorExtensions::SelectFirstBy

- ea: `0x1930`
- end: `0x199f`
- name: `Microsoft.BIServer.HostingEnvironment.ManagementObjectEnumeratorExtensions::SelectFirstBy`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1a40`

## callees

- `0x1930`

## pseudocode

```c

```

## disassembly

```asm
0x1930  ldarg.0
0x1931  brtrue.s loc_1935
0x1933  ldnull
0x1934  ret
0x1935  ldarg.0
0x1936  callvirt instance class [System.Management]System.Management.ManagementBaseObject [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::get_Current()
0x193b  stloc.0
0x193c  ldc.i4.1
0x193d  stloc.1
0x193e  br.s     loc_1953
0x1940  ldarg.0
0x1941  callvirt instance bool [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::MoveNext()
0x1946  stloc.1
0x1947  ldarg.0
0x1948  callvirt instance class [System.Management]System.Management.ManagementBaseObject [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::get_Current()
0x194d  castclass [System.Management]System.Management.ManagementObject
0x1952  stloc.0
0x1953  ldloc.1
0x1954  brfalse.s loc_1998
0x1956  ldarg.2
0x1957  ldloc.0
0x1958  brtrue.s loc_195D
0x195a  ldnull
0x195b  br.s     loc_1988
0x195d  ldloc.0
0x195e  callvirt instance class [System.Management]System.Management.PropertyDataCollection [System.Management]System.Management.ManagementBaseObject::get_Properties()
0x1963  dup
0x1964  brtrue.s loc_196A
0x1966  pop
0x1967  ldnull
0x1968  br.s     loc_1988
0x196a  ldarg.1
0x196b  callvirt instance class [System.Management]System.Management.PropertyData [System.Management]System.Management.PropertyDataCollection::get_Item(string)
0x1970  dup
0x1971  brtrue.s loc_1977
0x1973  pop
0x1974  ldnull
0x1975  br.s     loc_1988
0x1977  call     instance object [System.Management]System.Management.PropertyData::get_Value()
0x197c  dup
0x197d  brtrue.s loc_1983
0x197f  pop
0x1980  ldnull
0x1981  br.s     loc_1988
0x1983  callvirt instance string [mscorlib]System.Object::ToString()
0x1988  dup
0x1989  brtrue.s loc_1991
0x198b  pop
0x198c  ldstr    asc_7C08// ""
0x1991  callvirt instance bool class [mscorlib]System.Predicate`1<string>::Invoke(var<u1>)
0x1996  brfalse.s loc_1940
0x1998  ldloc.0
0x1999  castclass [System.Management]System.Management.ManagementObject
0x199e  ret
```
