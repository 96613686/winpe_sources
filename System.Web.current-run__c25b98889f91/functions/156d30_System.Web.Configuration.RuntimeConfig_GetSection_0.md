# System.Web.Configuration.RuntimeConfig::GetSection_0

- ea: `0x156d30`
- end: `0x156dc8`
- name: `System.Web.Configuration.RuntimeConfig::GetSection_0`
- size: `152`
- prototype: ``
- caller_count: `23`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x156640`
- `0x1566c0`
- `0x1566e0`
- `0x156720`
- `0x156740`
- `0x156780`
- `0x156820`
- `0x156840`
- `0x156860`
- `0x156880`
- `0x1568a0`
- `0x1568c0`
- `0x1568e0`
- `0x156900`
- `0x156960`
- `0x1569c0`
- `0x156a60`
- `0x156a80`
- `0x156aa0`
- `0x156ac0`
- `0x156b00`
- `0x156b20`
- `0x156d20`

## callees

- `0x34f20`
- `0x156b60`
- `0x156cb0`
- `0x156d30`

## string_xrefs

- `0x156d76`: `Config_unable_to_get_section`
- `0x156d9e`: `Config_unable_to_get_section`

## pseudocode

```c

```

## disassembly

```asm
0x156d30  ldarg.0
0x156d31  ldfld    object[] System.Web.Configuration.RuntimeConfig::_results
0x156d36  ldarg.3
0x156d37  ldelem.ref
0x156d38  stloc.0
0x156d39  ldloc.0
0x156d3a  ldsfld   object System.Web.Configuration.RuntimeConfig::s_unevaluatedResult
0x156d3f  beq.s    loc_156D43
0x156d41  ldloc.0
0x156d42  ret
0x156d43  nop
0x156d44  ldarg.0
0x156d45  ldarg.1
0x156d46  callvirt instance object System.Web.Configuration.RuntimeConfig::GetSectionObject(string sectionName)
0x156d4b  stloc.0
0x156d4c  leave.s  loc_156D6B
0x156d4e  isinst   [System.Configuration]System.Configuration.ConfigurationErrorsException
0x156d53  dup
0x156d54  brtrue.s loc_156D5A
0x156d56  pop
0x156d57  ldc.i4.0
0x156d58  br.s     loc_156D64
0x156d5a  pop
0x156d5b  ldarg.0
0x156d5c  call     instance bool System.Web.Configuration.RuntimeConfig::get_IgnoreConfigErrors()
0x156d61  ldc.i4.0
0x156d62  cgt.un
0x156d64  endfilter
0x156d66  pop
0x156d67  ldnull
0x156d68  stloc.1
0x156d69  leave.s  loc_156DC6
0x156d6b  ldloc.0
0x156d6c  brtrue.s loc_156D90
0x156d6e  ldarg.0
0x156d6f  ldfld    bool System.Web.Configuration.RuntimeConfig::_permitNull
0x156d74  brtrue.s loc_156DB8
0x156d76  ldstr    aConfigUnableTo// "Config_unable_to_get_section"
0x156d7b  ldc.i4.1
0x156d7c  newarr   [mscorlib]System.Object
0x156d81  dup
0x156d82  ldc.i4.0
0x156d83  ldarg.1
0x156d84  stelem.ref
0x156d85  call     string System.Web.SR::GetString(string name, object[] args)
0x156d8a  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string)
0x156d8f  throw
0x156d90  ldloc.0
0x156d91  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x156d96  ldarg.2
0x156d97  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x156d9c  brfalse.s loc_156DB8
0x156d9e  ldstr    aConfigUnableTo// "Config_unable_to_get_section"
0x156da3  ldc.i4.1
0x156da4  newarr   [mscorlib]System.Object
0x156da9  dup
0x156daa  ldc.i4.0
0x156dab  ldarg.1
0x156dac  stelem.ref
0x156dad  call     string System.Web.SR::GetString(string name, object[] args)
0x156db2  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string)
0x156db7  throw
0x156db8  ldarg.3
0x156db9  brfalse.s loc_156DC4
0x156dbb  ldarg.0
0x156dbc  ldfld    object[] System.Web.Configuration.RuntimeConfig::_results
0x156dc1  ldarg.3
0x156dc2  ldloc.0
0x156dc3  stelem.ref
0x156dc4  ldloc.0
0x156dc5  ret
0x156dc6  ldloc.1
0x156dc7  ret
```
