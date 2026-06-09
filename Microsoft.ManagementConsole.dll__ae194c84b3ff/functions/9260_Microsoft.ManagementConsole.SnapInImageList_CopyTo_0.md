# Microsoft.ManagementConsole.SnapInImageList::CopyTo_0

- ea: `0x9260`
- end: `0x92e0`
- name: `Microsoft.ManagementConsole.SnapInImageList::CopyTo_0`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0xf0`
- `0x8530`
- `0x9010`
- `0x9020`
- `0x90c0`
- `0x9260`

## pseudocode

```c

```

## disassembly

```asm
0x9260  ldarg.1
0x9261  brtrue.s loc_926E
0x9263  ldstr    aImagelist// "imageList"
0x9268  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x926d  throw
0x926e  ldarg.2
0x926f  ldarg.1
0x9270  callvirt instance int32 Microsoft.ManagementConsole.SnapInImageList::get_Count()
0x9275  bge.s    loc_9291
0x9277  ldarg.0
0x9278  call     instance class [System.Windows.Forms]System.Windows.Forms.ImageList Microsoft.ManagementConsole.SnapInImageList::get_ImageList()
0x927d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection [System.Windows.Forms]System.Windows.Forms.ImageList::get_Images()
0x9282  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection::get_Count()
0x9287  ldarg.1
0x9288  callvirt instance int32 Microsoft.ManagementConsole.SnapInImageList::get_Count()
0x928d  ldarg.2
0x928e  sub
0x928f  ble.s    loc_92A7
0x9291  ldstr    aIndex// "index"
0x9296  call     string Microsoft.ManagementConsole.Internal.Strings::get_ArgumentExceptionCopyTo()
0x929b  ldc.i4.0
0x929c  newarr   [mscorlib]System.Object
0x92a1  call     class [mscorlib]System.ArgumentException Microsoft.ManagementConsole.Internal.Utility::CreateArgumentException(string name, string resourceName, object[] parms)
0x92a6  throw
0x92a7  ldc.i4.0
0x92a8  stloc.0
0x92a9  br.s     loc_92CC
0x92ab  ldarg.1
0x92ac  ldarg.2
0x92ad  dup
0x92ae  ldc.i4.1
0x92af  add
0x92b0  starg.s  2
0x92b2  ldarg.0
0x92b3  call     instance class [System.Windows.Forms]System.Windows.Forms.ImageList Microsoft.ManagementConsole.SnapInImageList::get_ImageList()
0x92b8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection [System.Windows.Forms]System.Windows.Forms.ImageList::get_Images()
0x92bd  ldloc.0
0x92be  callvirt instance class [System.Drawing]System.Drawing.Image [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection::get_Item(int32)
0x92c3  callvirt instance void Microsoft.ManagementConsole.SnapInImageList::set_Item(int32 index, class [System.Drawing]System.Drawing.Image value)
0x92c8  ldloc.0
0x92c9  ldc.i4.1
0x92ca  add
0x92cb  stloc.0
0x92cc  ldloc.0
0x92cd  ldarg.0
0x92ce  call     instance class [System.Windows.Forms]System.Windows.Forms.ImageList Microsoft.ManagementConsole.SnapInImageList::get_ImageList()
0x92d3  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection [System.Windows.Forms]System.Windows.Forms.ImageList::get_Images()
0x92d8  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection::get_Count()
0x92dd  blt.s    loc_92AB
0x92df  ret
```
