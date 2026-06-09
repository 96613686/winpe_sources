# MS.Internal.Printing.Configuration.ImageableSizeCapability::BuildProperty

- ea: `0xeea0`
- end: `0xf031`
- name: `MS.Internal.Printing.Configuration.ImageableSizeCapability::BuildProperty`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0xecd0`
- `0xee20`
- `0xeea0`
- `0x16680`
- `0x16880`
- `0x169e0`
- `0x16a00`

## pseudocode

```c

```

## disassembly

```asm
0xeea0  ldarg.1
0xeea1  callvirt instance int32 MS.Internal.Printing.Configuration.XmlPrintCapReader::get_CurrentElementDepth()
0xeea6  ldc.i4.1
0xeea7  add
0xeea8  stloc.0
0xeea9  br       loc_EFE0
0xeeae  ldarg.1
0xeeaf  callvirt instance string MS.Internal.Printing.Configuration.XmlPrintCapReader::get_CurrentElementNameAttrValue()
0xeeb4  ldstr    aImageablesizew_0// "ImageableSizeWidth"
0xeeb9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xeebe  brfalse.s loc_EED7
0xeec0  ldarg.0
0xeec1  ldarg.1
0xeec2  callvirt instance int32 MS.Internal.Printing.Configuration.XmlPrintCapReader::GetCurrentPropertyIntValueWithException()
0xeec7  stfld    int32 MS.Internal.Printing.Configuration.ImageableSizeCapability::_imageableSizeWidth
0xeecc  leave    loc_EFE0
0xeed1  pop
0xeed2  leave    loc_EFE0
0xeed7  ldarg.1
0xeed8  callvirt instance string MS.Internal.Printing.Configuration.XmlPrintCapReader::get_CurrentElementNameAttrValue()
0xeedd  ldstr    aImageablesizeh_0// "ImageableSizeHeight"
0xeee2  call     bool [mscorlib]System.String::op_Equality(string, string)
0xeee7  brfalse.s loc_EF00
0xeee9  ldarg.0
0xeeea  ldarg.1
0xeeeb  callvirt instance int32 MS.Internal.Printing.Configuration.XmlPrintCapReader::GetCurrentPropertyIntValueWithException()
0xeef0  stfld    int32 MS.Internal.Printing.Configuration.ImageableSizeCapability::_imageableSizeHeight
0xeef5  leave    loc_EFE0
0xeefa  pop
0xeefb  leave    loc_EFE0
0xef00  ldarg.1
0xef01  callvirt instance string MS.Internal.Printing.Configuration.XmlPrintCapReader::get_CurrentElementNameAttrValue()
0xef06  ldstr    aImageablearea// "ImageableArea"
0xef0b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xef10  brfalse  loc_EFE0
0xef15  ldarg.0
0xef16  ldarg.0
0xef17  newobj   instance void MS.Internal.Printing.Configuration.CanvasImageableArea::.ctor(class MS.Internal.Printing.Configuration.ImageableSizeCapability ownerProperty)
0xef1c  stfld    class MS.Internal.Printing.Configuration.CanvasImageableArea MS.Internal.Printing.Configuration.ImageableSizeCapability::_imageableArea
0xef21  ldarg.1
0xef22  callvirt instance int32 MS.Internal.Printing.Configuration.XmlPrintCapReader::get_CurrentElementDepth()
0xef27  ldc.i4.1
0xef28  add
0xef29  stloc.2
0xef2a  br       loc_EFCF
0xef2f  ldarg.1
0xef30  callvirt instance string MS.Internal.Printing.Configuration.XmlPrintCapReader::get_CurrentElementNameAttrValue()
0xef35  ldstr    aOriginwidth// "OriginWidth"
0xef3a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xef3f  brfalse.s loc_EF57
0xef41  ldarg.0
0xef42  ldfld    class MS.Internal.Printing.Configuration.CanvasImageableArea MS.Internal.Printing.Configuration.ImageableSizeCapability::_imageableArea
0xef47  ldarg.1
0xef48  callvirt instance int32 MS.Internal.Printing.Configuration.XmlPrintCapReader::GetCurrentPropertyIntValueWithException()
0xef4d  stfld    int32 MS.Internal.Printing.Configuration.CanvasImageableArea::_originWidth
0xef52  leave.s  loc_EFCF
0xef54  pop
0xef55  leave.s  loc_EFCF
0xef57  ldarg.1
0xef58  callvirt instance string MS.Internal.Printing.Configuration.XmlPrintCapReader::get_CurrentElementNameAttrValue()
0xef5d  ldstr    aOriginheight// "OriginHeight"
0xef62  call     bool [mscorlib]System.String::op_Equality(string, string)
0xef67  brfalse.s loc_EF7F
0xef69  ldarg.0
0xef6a  ldfld    class MS.Internal.Printing.Configuration.CanvasImageableArea MS.Internal.Printing.Configuration.ImageableSizeCapability::_imageableArea
0xef6f  ldarg.1
0xef70  callvirt instance int32 MS.Internal.Printing.Configuration.XmlPrintCapReader::GetCurrentPropertyIntValueWithException()
0xef75  stfld    int32 MS.Internal.Printing.Configuration.CanvasImageableArea::_originHeight
0xef7a  leave.s  loc_EFCF
0xef7c  pop
0xef7d  leave.s  loc_EFCF
0xef7f  ldarg.1
0xef80  callvirt instance string MS.Internal.Printing.Configuration.XmlPrintCapReader::get_CurrentElementNameAttrValue()
0xef85  ldstr    aExtentwidth// "ExtentWidth"
0xef8a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xef8f  brfalse.s loc_EFA7
0xef91  ldarg.0
0xef92  ldfld    class MS.Internal.Printing.Configuration.CanvasImageableArea MS.Internal.Printing.Configuration.ImageableSizeCapability::_imageableArea
0xef97  ldarg.1
0xef98  callvirt instance int32 MS.Internal.Printing.Configuration.XmlPrintCapReader::GetCurrentPropertyIntValueWithException()
0xef9d  stfld    int32 MS.Internal.Printing.Configuration.CanvasImageableArea::_extentWidth
0xefa2  leave.s  loc_EFCF
0xefa4  pop
0xefa5  leave.s  loc_EFCF
0xefa7  ldarg.1
0xefa8  callvirt instance string MS.Internal.Printing.Configuration.XmlPrintCapReader::get_CurrentElementNameAttrValue()
0xefad  ldstr    aExtentheight// "ExtentHeight"
0xefb2  call     bool [mscorlib]System.String::op_Equality(string, string)
0xefb7  brfalse.s loc_EFCF
0xefb9  ldarg.0
0xefba  ldfld    class MS.Internal.Printing.Configuration.CanvasImageableArea MS.Internal.Printing.Configuration.ImageableSizeCapability::_imageableArea
0xefbf  ldarg.1
0xefc0  callvirt instance int32 MS.Internal.Printing.Configuration.XmlPrintCapReader::GetCurrentPropertyIntValueWithException()
0xefc5  stfld    int32 MS.Internal.Printing.Configuration.CanvasImageableArea::_extentHeight
0xefca  leave.s  loc_EFCF
0xefcc  pop
0xefcd  leave.s  loc_EFCF
0xefcf  ldarg.1
0xefd0  ldloc.2
0xefd1  ldc.i4   0x100
0xefd6  callvirt instance bool MS.Internal.Printing.Configuration.XmlPrintCapReader::MoveToNextSchemaElement(int32 depth, valuetype MS.Internal.Printing.Configuration.PrintSchemaNodeTypes typeFilterFlags)
0xefdb  brtrue   loc_EF2F
0xefe0  ldarg.1
0xefe1  ldloc.0
0xefe2  ldc.i4   0x100
0xefe7  callvirt instance bool MS.Internal.Printing.Configuration.XmlPrintCapReader::MoveToNextSchemaElement(int32 depth, valuetype MS.Internal.Printing.Configuration.PrintSchemaNodeTypes typeFilterFlags)
0xefec  brtrue   loc_EEAE
0xeff1  ldc.i4.0
0xeff2  stloc.1
0xeff3  ldarg.0
0xeff4  ldfld    int32 MS.Internal.Printing.Configuration.ImageableSizeCapability::_imageableSizeWidth
0xeff9  ldc.i4.0
0xeffa  blt.s    loc_F02F
0xeffc  ldarg.0
0xeffd  ldfld    int32 MS.Internal.Printing.Configuration.ImageableSizeCapability::_imageableSizeHeight
0xf002  ldc.i4.0
0xf003  blt.s    loc_F02F
0xf005  ldc.i4.1
0xf006  stloc.1
0xf007  ldarg.0
0xf008  call     instance class MS.Internal.Printing.Configuration.CanvasImageableArea MS.Internal.Printing.Configuration.ImageableSizeCapability::get_ImageableArea()
0xf00d  brfalse.s loc_F02F
0xf00f  ldc.i4.0
0xf010  stloc.1
0xf011  ldarg.0
0xf012  call     instance class MS.Internal.Printing.Configuration.CanvasImageableArea MS.Internal.Printing.Configuration.ImageableSizeCapability::get_ImageableArea()
0xf017  ldfld    int32 MS.Internal.Printing.Configuration.CanvasImageableArea::_extentWidth
0xf01c  ldc.i4.0
0xf01d  blt.s    loc_F02F
0xf01f  ldarg.0
0xf020  call     instance class MS.Internal.Printing.Configuration.CanvasImageableArea MS.Internal.Printing.Configuration.ImageableSizeCapability::get_ImageableArea()
0xf025  ldfld    int32 MS.Internal.Printing.Configuration.CanvasImageableArea::_extentHeight
0xf02a  ldc.i4.0
0xf02b  blt.s    loc_F02F
0xf02d  ldc.i4.1
0xf02e  stloc.1
0xf02f  ldloc.1
0xf030  ret
```
