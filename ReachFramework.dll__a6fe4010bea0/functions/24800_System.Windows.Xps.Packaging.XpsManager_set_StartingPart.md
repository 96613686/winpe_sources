# System.Windows.Xps.Packaging.XpsManager::set_StartingPart

- ea: `0x24800`
- end: `0x24845`
- name: `System.Windows.Xps.Packaging.XpsManager::set_StartingPart`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x25e90`

## callees

- `0x1ee90`
- `0x1ef70`
- `0x24800`
- `0x248c0`
- `0x25870`
- `0x258f0`

## string_xrefs

- `0x24828`: `ReachPackaging_AlreadyHasStartingPart`

## pseudocode

```c

```

## disassembly

```asm
0x24800  ldarg.0
0x24801  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Packaging.XpsManager::_metroPackage
0x24806  brtrue.s loc_24813
0x24808  ldstr    aXpsmanager// "XpsManager"
0x2480d  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x24812  throw
0x24813  ldarg.0
0x24814  call     instance bool System.Windows.Xps.Packaging.XpsManager::get_Streaming()
0x24819  brtrue.s loc_24838
0x2481b  ldarg.0
0x2481c  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Packaging.XpsManager::_metroPackage
0x24821  call     class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GetXpsDocumentStartingPart(class [WindowsBase]System.IO.Packaging.Package package)
0x24826  brfalse.s loc_24838
0x24828  ldstr    aReachpackaging_17// "ReachPackaging_AlreadyHasStartingPart"
0x2482d  call     string System.Windows.Xps.SR::Get(string id)
0x24832  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x24837  throw
0x24838  ldarg.0
0x24839  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Packaging.XpsManager::_metroPackage
0x2483e  ldarg.1
0x2483f  call     void System.Windows.Xps.Packaging.XpsManager::SetXpsDocumentStartingPart(class [WindowsBase]System.IO.Packaging.Package package, class [WindowsBase]System.IO.Packaging.PackagePart startingPart)
0x24844  ret
```
