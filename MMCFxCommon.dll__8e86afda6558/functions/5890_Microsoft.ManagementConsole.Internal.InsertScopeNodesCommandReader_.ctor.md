# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::.ctor

- ea: `0x5890`
- end: `0x58c7`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::.ctor`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x5890`
- `0x7ac0`

## pseudocode

```c

```

## disassembly

```asm
0x5890  ldarg.0
0x5891  call     instance void [mscorlib]System.Object::.ctor()
0x5896  ldarg.1
0x5897  brtrue.s loc_58A4
0x5899  ldstr    aSource// "source"
0x589e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x58a3  throw
0x58a4  ldarg.0
0x58a5  ldarg.1
0x58a6  stfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x58ab  ldarg.0
0x58ac  ldarg.0
0x58ad  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x58b2  callvirt instance unsigned int8[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_strings()
0x58b7  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x58bc  newobj   instance void [mscorlib]System.IO.BinaryReader::.ctor(class [mscorlib]System.IO.Stream)
0x58c1  stfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x58c6  ret
```
