# System.Windows.Xps.Packaging.XpsDocument::AddFixedDocumentSequence

- ea: `0x25e90`
- end: `0x25f22`
- name: `System.Windows.Xps.Packaging.XpsDocument::AddFixedDocumentSequence`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x2eb10`

## callees

- `0x1ee90`
- `0x1ef70`
- `0x20000`
- `0x20a20`
- `0x24570`
- `0x247e0`
- `0x24800`
- `0x248c0`
- `0x249a0`
- `0x25aa0`
- `0x25e90`
- `0x26330`

## string_xrefs

- `0x25eb6`: `ReachPackaging_AlreadyHasRootSequenceOrDocument`
- `0x25ee0`: `ReachPackaging_AlreadyHasRootSequenceOrDocument`

## pseudocode

```c

```

## disassembly

```asm
0x25e90  ldarg.0
0x25e91  call     instance void System.Windows.Xps.Packaging.XpsDocument::CheckDisposed()
0x25e96  ldarg.0
0x25e97  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x25e9c  brtrue.s loc_25EAE
0x25e9e  ldstr    aReachpackaging_29// "ReachPackaging_DocumentWasClosed"
0x25ea3  call     string System.Windows.Xps.SR::Get(string id)
0x25ea8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x25ead  throw
0x25eae  ldarg.0
0x25eaf  ldfld    bool System.Windows.Xps.Packaging.XpsDocument::_isInDocumentStage
0x25eb4  brfalse.s loc_25EC6
0x25eb6  ldstr    aReachpackaging_30// "ReachPackaging_AlreadyHasRootSequenceOr"...
0x25ebb  call     string System.Windows.Xps.SR::Get(string id)
0x25ec0  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x25ec5  throw
0x25ec6  ldarg.0
0x25ec7  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x25ecc  callvirt instance bool System.Windows.Xps.Packaging.XpsManager::get_Streaming()
0x25ed1  brtrue.s loc_25EF0
0x25ed3  ldarg.0
0x25ed4  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x25ed9  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::get_StartingPart()
0x25ede  brfalse.s loc_25EF0
0x25ee0  ldstr    aReachpackaging_30// "ReachPackaging_AlreadyHasRootSequenceOr"...
0x25ee5  call     string System.Windows.Xps.SR::Get(string id)
0x25eea  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x25eef  throw
0x25ef0  ldarg.0
0x25ef1  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x25ef6  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_DocumentSequenceContentType()
0x25efb  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GenerateUniquePart(class [WindowsBase]MS.Internal.ContentType contentType)
0x25f00  stloc.0
0x25f01  ldarg.0
0x25f02  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x25f07  ldarg.0
0x25f08  ldloc.0
0x25f09  newobj   instance void System.Windows.Xps.Packaging.XpsFixedDocumentSequenceReaderWriter::.ctor(class System.Windows.Xps.Packaging.XpsManager xpsManager, class System.Windows.Xps.Packaging.INode parent, class [WindowsBase]System.IO.Packaging.PackagePart part)
0x25f0e  stloc.1
0x25f0f  ldarg.0
0x25f10  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x25f15  ldloc.1
0x25f16  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.INode::GetPart()
0x25f1b  callvirt instance void System.Windows.Xps.Packaging.XpsManager::set_StartingPart(class [WindowsBase]System.IO.Packaging.PackagePart value)
0x25f20  ldloc.1
0x25f21  ret
```
