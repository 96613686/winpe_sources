# System.Printing.PrintQueue::PrepareNameForDownLevelConnectivity

- ea: `0x11410`
- end: `0x11470`
- name: `System.Printing.PrintQueue::PrepareNameForDownLevelConnectivity`
- size: `96`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: ``

## callers

- `0xe650`
- `0xf610`
- `0xf710`
- `0x102b0`
- `0x11240`

## callees

- `0x6d70`
- `0x11410`
- `0x14aa0`
- `0x170c0`
- `0x170e0`
- `0x19500`
- `0x19540`
- `0x19570`
- `0x19580`
- `0x195f0`
- `0x196b0`

## pseudocode

```c

```

## disassembly

```asm
0x11410  ldarg.1
0x11411  call     string MS.Internal.PrintWin32Thunk.PrinterThunkHandler::GetLocalMachineName()
0x11416  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1141b  brfalse.s loc_11420
0x1141d  ldarg.2
0x1141e  br.s     loc_1146F
0x11420  newobj   instance void System.Printing.IndexedProperties.PrintPropertyDictionary::.ctor()
0x11425  stloc.1
0x11426  ldstr    aServername// "ServerName"
0x1142b  ldarg.1
0x1142c  newobj   instance void System.Printing.IndexedProperties.PrintStringProperty::.ctor(string attributeName, object attributeValue)
0x11431  stloc.0
0x11432  ldloc.1
0x11433  ldloc.0
0x11434  call     instance void System.Printing.IndexedProperties.PrintPropertyDictionary::Add(class System.Printing.IndexedProperties.PrintProperty attributeValue)
0x11439  ldstr    aPrintername// "PrinterName"
0x1143e  ldarg.2
0x1143f  newobj   instance void System.Printing.IndexedProperties.PrintStringProperty::.ctor(string attributeName, object attributeValue)
0x11444  stloc.0
0x11445  ldloc.1
0x11446  ldloc.0
0x11447  call     instance void System.Printing.IndexedProperties.PrintPropertyDictionary::Add(class System.Printing.IndexedProperties.PrintProperty attributeValue)
0x1144c  ldloc.1
0x1144d  newobj   instance void System.Printing.PrintSystemDefaultPathResolver::.ctor()
0x11452  newobj   instance void System.Printing.PrintSystemUNCPathResolver::.ctor(class System.Printing.IPrintSystemPathResolver resolver)
0x11457  newobj   instance void System.Printing.PrintSystemPathResolver::.ctor(class System.Printing.IndexedProperties.PrintPropertyDictionary collection, class System.Printing.IPrintSystemPathResolver resolver)
0x1145c  stloc.2
0x1145d  ldloc.2
0x1145e  call     instance bool System.Printing.PrintSystemPathResolver::Resolve()
0x11463  pop
0x11464  ldloc.2
0x11465  call     instance class System.Printing.PrintSystemProtocol System.Printing.PrintSystemPathResolver::get_Protocol()
0x1146a  call     instance string System.Printing.PrintSystemProtocol::get_Path()
0x1146f  ret
```
