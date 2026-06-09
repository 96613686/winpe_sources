# System.Printing.IndexedProperties.PrintProperty::Dispose

- ea: `0x146a0`
- end: `0x146bc`
- name: `System.Printing.IndexedProperties.PrintProperty::Dispose`
- size: `28`
- prototype: ``
- caller_count: `62`
- callee_count: `3`
- tags: ``

## callers

- `0x146c0`
- `0x146d0`
- `0x14830`
- `0x14860`
- `0x14890`
- `0x14a40`
- `0x14a70`
- `0x14aa0`
- `0x14c80`
- `0x14cb0`
- `0x14ce0`
- `0x14e60`
- `0x14e90`
- `0x14ec0`
- `0x15060`
- `0x15090`
- `0x150c0`
- `0x15260`
- `0x15290`
- `0x152c0`
- `0x15450`
- `0x15480`
- `0x154b0`
- `0x15640`
- `0x15670`
- `0x156a0`
- `0x15830`
- `0x15860`
- `0x15890`
- `0x15a30`
- `0x15a60`
- `0x15a90`
- `0x15c30`
- `0x15c80`
- `0x15cb0`
- `0x15e60`
- `0x15eb0`
- `0x15ee0`
- `0x16090`
- `0x160c0`
- `0x160f0`
- `0x162a0`
- `0x162d0`
- `0x16300`
- `0x164a0`
- `0x164d0`
- `0x16500`
- `0x166a0`
- `0x166d0`
- `0x16700`

## callees

- `0x14530`
- `0x14640`
- `0x146a0`

## pseudocode

```c

```

## disassembly

```asm
0x146a0  ldarg.1
0x146a1  brfalse.s loc_146AB
0x146a3  ldarg.0
0x146a4  call     instance void System.Printing.IndexedProperties.PrintProperty::~PrintProperty()
0x146a9  br.s     loc_146BB
0x146ab  nop
0x146ac  ldarg.0
0x146ad  call     instance void System.Printing.IndexedProperties.PrintProperty::!PrintProperty()
0x146b2  leave.s  loc_146BB
0x146b4  ldarg.0
0x146b5  call     instance void [mscorlib]System.Object::Finalize()
0x146ba  endfinally
0x146bb  ret
```
