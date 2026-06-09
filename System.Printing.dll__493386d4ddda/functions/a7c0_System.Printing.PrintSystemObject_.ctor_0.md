# System.Printing.PrintSystemObject::.ctor_0

- ea: `0xa7c0`
- end: `0xa7fe`
- name: `System.Printing.PrintSystemObject::.ctor_0`
- size: `62`
- prototype: ``
- caller_count: `26`
- callee_count: `3`
- tags: ``

## callers

- `0xac70`
- `0xae40`
- `0xd960`
- `0xd9f0`
- `0xda80`
- `0xdaf0`
- `0xdb60`
- `0xdbd0`
- `0xdc40`
- `0xdcb0`
- `0xdd10`
- `0xdd70`
- `0x11d80`
- `0x11dd0`
- `0x11e10`
- `0x11e60`
- `0x11ea0`
- `0x11ee0`
- `0x11f20`
- `0x11f60`
- `0x11fa0`
- `0x17380`
- `0x173e0`
- `0x17460`
- `0x175e0`
- `0x17690`

## callees

- `0xa7c0`
- `0xa890`
- `0x170c0`

## pseudocode

```c

```

## disassembly

```asm
0xa7c0  ldarg.0
0xa7c1  ldnull
0xa7c2  stfld    class System.Printing.PrintSystemObject System.Printing.PrintSystemObject::parent
0xa7c7  ldarg.0
0xa7c8  ldnull
0xa7c9  stfld    string System.Printing.PrintSystemObject::name
0xa7ce  ldarg.0
0xa7cf  call     instance void [mscorlib]System.Object::.ctor()
0xa7d4  ldarg.0
0xa7d5  newobj   instance void System.Printing.IndexedProperties.PrintPropertyDictionary::.ctor()
0xa7da  stfld    class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemObject::propertiesCollection
0xa7df  newobj   instance void [mscorlib]System.Object::.ctor()
0xa7e4  stloc.0
0xa7e5  ldarg.0
0xa7e6  ldloc.0
0xa7e7  stfld    object System.Printing.PrintSystemObject::syncRoot
0xa7ec  ldarg.0
0xa7ed  ldfld    class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemObject::propertiesCollection
0xa7f2  brfalse.s loc_A7FD
0xa7f4  ldloc.0
0xa7f5  brfalse.s loc_A7FD
0xa7f7  ldarg.0
0xa7f8  call     instance void System.Printing.PrintSystemObject::Initialize()
0xa7fd  ret
```
