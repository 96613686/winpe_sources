# ResourceDirectory::.ctor

- ea: `0x2b6f0`
- end: `0x2b8c7`
- name: `ResourceDirectory::.ctor`
- size: `471`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x2b6f0`
- `0x2bdd0`

## callees

- `0x2b030`
- `0x2b110`
- `0x2b190`
- `0x2b6d0`
- `0x2b6f0`
- `0x2b9d0`
- `0x2ba30`
- `0x2ba50`
- `0x2ba70`
- `0x2ba90`
- `0x2bab0`
- `0x2bae0`
- `0x2bc40`
- `0x2bc60`
- `0x2be30`

## pseudocode

```c

```

## disassembly

```asm
0x2b6f0  ldarg.0
0x2b6f1  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x2b6f6  stfld    class [mscorlib]System.Collections.Hashtable ResourceDirectory::_resourceDirectoryItems
0x2b6fb  ldarg.0
0x2b6fc  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x2b701  stfld    class [mscorlib]System.Collections.ArrayList ResourceDirectory::_resourceDirectoryEntries
0x2b706  ldarg.0
0x2b707  call     instance void ResourceComponent::.ctor()
0x2b70c  ldarg.0
0x2b70d  ldarg.2
0x2b70e  ldarg.s  4
0x2b710  ldarg.0
0x2b711  ldfld    valuetype IMAGE_RESOURCE_DIRECTORY ResourceDirectory::_imageResourceDirectory
0x2b716  box      IMAGE_RESOURCE_DIRECTORY
0x2b71b  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2b720  call     object PEComponent::ReadData(class [mscorlib]System.IO.FileStream file, int64 position, class [mscorlib]System.Type dataType)
0x2b725  unbox.any IMAGE_RESOURCE_DIRECTORY
0x2b72a  stfld    valuetype IMAGE_RESOURCE_DIRECTORY ResourceDirectory::_imageResourceDirectory
0x2b72f  ldarg.0
0x2b730  ldarg.s  4
0x2b732  stfld    int64 PEComponent::_address
0x2b737  ldarg.0
0x2b738  ldarg.0
0x2b739  ldarg.0
0x2b73a  ldfld    valuetype IMAGE_RESOURCE_DIRECTORY ResourceDirectory::_imageResourceDirectory
0x2b73f  box      IMAGE_RESOURCE_DIRECTORY
0x2b744  call     instance int64 PEComponent::CalculateSize(object data)
0x2b749  stfld    int64 PEComponent::_size
0x2b74e  ldarg.0
0x2b74f  ldarg.0
0x2b750  ldfld    valuetype IMAGE_RESOURCE_DIRECTORY ResourceDirectory::_imageResourceDirectory
0x2b755  box      IMAGE_RESOURCE_DIRECTORY
0x2b75a  stfld    object PEComponent::_data
0x2b75f  ldarg.0
0x2b760  ldfld    int64 PEComponent::_address
0x2b765  ldarg.0
0x2b766  ldfld    int64 PEComponent::_size
0x2b76b  add
0x2b76c  stloc.0
0x2b76d  ldc.i4.0
0x2b76e  stloc.1
0x2b76f  ldc.i4.0
0x2b770  stloc.1
0x2b771  br.s     loc_2B795
0x2b773  ldarg.2
0x2b774  ldloc.0
0x2b775  newobj   instance void ResourceDirectoryEntry::.ctor(class [mscorlib]System.IO.FileStream file, int64 address)
0x2b77a  stloc.2
0x2b77b  ldarg.0
0x2b77c  ldfld    class [mscorlib]System.Collections.ArrayList ResourceDirectory::_resourceDirectoryEntries
0x2b781  ldloc.2
0x2b782  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x2b787  pop
0x2b788  ldloc.0
0x2b789  ldloc.2
0x2b78a  callvirt instance int64 PEComponent::get_Size()
0x2b78f  add
0x2b790  stloc.0
0x2b791  ldloc.1
0x2b792  ldc.i4.1
0x2b793  add
0x2b794  stloc.1
0x2b795  ldloc.1
0x2b796  ldarg.0
0x2b797  ldflda   valuetype IMAGE_RESOURCE_DIRECTORY ResourceDirectory::_imageResourceDirectory
0x2b79c  ldfld    unsigned int16 IMAGE_RESOURCE_DIRECTORY::NumberOfIdEntries
0x2b7a1  blt.s    loc_2B773
0x2b7a3  ldc.i4.0
0x2b7a4  stloc.1
0x2b7a5  br.s     loc_2B7C9
0x2b7a7  ldarg.2
0x2b7a8  ldloc.0
0x2b7a9  newobj   instance void ResourceDirectoryEntry::.ctor(class [mscorlib]System.IO.FileStream file, int64 address)
0x2b7ae  stloc.3
0x2b7af  ldarg.0
0x2b7b0  ldfld    class [mscorlib]System.Collections.ArrayList ResourceDirectory::_resourceDirectoryEntries
0x2b7b5  ldloc.3
0x2b7b6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x2b7bb  pop
0x2b7bc  ldloc.0
0x2b7bd  ldloc.3
0x2b7be  callvirt instance int64 PEComponent::get_Size()
0x2b7c3  add
0x2b7c4  stloc.0
0x2b7c5  ldloc.1
0x2b7c6  ldc.i4.1
0x2b7c7  add
0x2b7c8  stloc.1
0x2b7c9  ldloc.1
0x2b7ca  ldarg.0
0x2b7cb  ldflda   valuetype IMAGE_RESOURCE_DIRECTORY ResourceDirectory::_imageResourceDirectory
0x2b7d0  ldfld    unsigned int16 IMAGE_RESOURCE_DIRECTORY::NumberOfNamedEntries
0x2b7d5  blt.s    loc_2B7A7
0x2b7d7  ldarg.0
0x2b7d8  ldfld    class [mscorlib]System.Collections.ArrayList ResourceDirectory::_resourceDirectoryEntries
0x2b7dd  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x2b7e2  stloc.s  4
0x2b7e4  br       loc_2B8A3
0x2b7e9  ldloc.s  4
0x2b7eb  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2b7f0  castclass ResourceDirectoryEntry
0x2b7f5  stloc.s  5
0x2b7f7  ldc.i4.0
0x2b7f8  stloc.s  6
0x2b7fa  ldnull
0x2b7fb  stloc.s  7
0x2b7fd  ldloc.s  5
0x2b7ff  callvirt instance bool ResourceDirectoryEntry::get_NameIsString()
0x2b804  brfalse.s loc_2B823
0x2b806  ldarg.1
0x2b807  ldarg.2
0x2b808  ldarg.3
0x2b809  ldloc.s  5
0x2b80b  callvirt instance int64 ResourceDirectoryEntry::get_NameOffset()
0x2b810  add
0x2b811  callvirt instance class ResourceDirectoryString ResourceSection::CreateResourceDirectoryString(class [mscorlib]System.IO.FileStream file, int64 offset)
0x2b816  stloc.s  9
0x2b818  ldloc.s  9
0x2b81a  callvirt instance string ResourceDirectoryString::get_NameString()
0x2b81f  stloc.s  7
0x2b821  br.s     loc_2B844
0x2b823  ldloc.s  5
0x2b825  callvirt instance unsigned int16 ResourceDirectoryEntry::get_Id()
0x2b82a  box      [mscorlib]System.UInt16
0x2b82f  stloc.s  7
0x2b831  ldarg.3
0x2b832  ldarg.s  4
0x2b834  bne.un.s loc_2B844
0x2b836  ldloc.s  5
0x2b838  callvirt instance unsigned int16 ResourceDirectoryEntry::get_Id()
0x2b83d  ldc.i4.s 0x18
0x2b83f  bne.un.s loc_2B844
0x2b841  ldc.i4.1
0x2b842  stloc.s  6
0x2b844  ldloc.s  5
0x2b846  ldloc.s  7
0x2b848  callvirt instance void ResourceDirectoryEntry::set_Key(object value)
0x2b84d  ldnull
0x2b84e  stloc.s  8
0x2b850  ldloc.s  5
0x2b852  callvirt instance bool ResourceDirectoryEntry::get_IsDirectory()
0x2b857  brfalse.s loc_2B87C
0x2b859  ldarg.s  6
0x2b85b  brfalse.s loc_2B864
0x2b85d  ldarg.s  6
0x2b85f  ldloc.s  6
0x2b861  and
0x2b862  brfalse.s loc_2B890
0x2b864  ldarg.1
0x2b865  ldarg.2
0x2b866  ldarg.3
0x2b867  ldarg.3
0x2b868  ldloc.s  5
0x2b86a  callvirt instance int64 ResourceDirectoryEntry::get_OffsetToData()
0x2b86f  add
0x2b870  ldarg.s  5
0x2b872  ldc.i4.0
0x2b873  newobj   instance void ResourceDirectory::.ctor(class ResourceSection resourceSection, class [mscorlib]System.IO.FileStream file, int64 rootResourceAddress, int64 resourceAddress, int64 addressDelta, bool partialConstruct)
0x2b878  stloc.s  8
0x2b87a  br.s     loc_2B890
0x2b87c  ldarg.2
0x2b87d  ldarg.3
0x2b87e  ldarg.3
0x2b87f  ldloc.s  5
0x2b881  callvirt instance int64 ResourceDirectoryEntry::get_OffsetToData()
0x2b886  add
0x2b887  ldarg.s  5
0x2b889  newobj   instance void ResourceData::.ctor(class [mscorlib]System.IO.FileStream file, int64 rootResourceAddress, int64 address, int64 addressDelta)
0x2b88e  stloc.s  8
0x2b890  ldloc.s  8
0x2b892  brfalse.s loc_2B8A3
0x2b894  ldarg.0
0x2b895  ldfld    class [mscorlib]System.Collections.Hashtable ResourceDirectory::_resourceDirectoryItems
0x2b89a  ldloc.s  7
0x2b89c  ldloc.s  8
0x2b89e  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x2b8a3  ldloc.s  4
0x2b8a5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2b8aa  brtrue   loc_2B7E9
0x2b8af  leave.s  loc_2B8C6
0x2b8b1  ldloc.s  4
0x2b8b3  isinst   [mscorlib]System.IDisposable
0x2b8b8  stloc.s  0xA
0x2b8ba  ldloc.s  0xA
0x2b8bc  brfalse.s loc_2B8C5
0x2b8be  ldloc.s  0xA
0x2b8c0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b8c5  endfinally
0x2b8c6  ret
```
