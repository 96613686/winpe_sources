# System.Xml.Xsl.XslTransformException::ToString

- ea: `0x3810`
- end: `0x38a9`
- name: `System.Xml.Xsl.XslTransformException::ToString`
- size: `153`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x3790`
- `0x3800`
- `0x3810`

## string_xrefs

- `0x3876`: `Xml_EndOfInnerExceptionStack`

## pseudocode

```c

```

## disassembly

```asm
0x3810  ldarg.0
0x3811  call     instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x3816  callvirt instance string [mscorlib]System.Type::get_FullName()
0x381b  stloc.0
0x381c  ldarg.0
0x381d  callvirt instance string System.Xml.Xsl.XslTransformException::FormatDetailedMessage()
0x3822  stloc.1
0x3823  ldloc.1
0x3824  brfalse.s loc_383C
0x3826  ldloc.1
0x3827  callvirt instance int32 [mscorlib]System.String::get_Length()
0x382c  ldc.i4.0
0x382d  ble.s    loc_383C
0x382f  ldloc.0
0x3830  ldstr    asc_58810// ": "
0x3835  ldloc.1
0x3836  call     string [mscorlib]System.String::Concat(string, string, string)
0x383b  stloc.0
0x383c  ldarg.0
0x383d  call     instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x3842  brfalse.s loc_388D
0x3844  ldc.i4.6
0x3845  newarr   [mscorlib]System.String
0x384a  dup
0x384b  ldc.i4.0
0x384c  ldloc.0
0x384d  stelem.ref
0x384e  dup
0x384f  ldc.i4.1
0x3850  ldstr    asc_58816// " ---> "
0x3855  stelem.ref
0x3856  dup
0x3857  ldc.i4.2
0x3858  ldarg.0
0x3859  call     instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x385e  callvirt instance string [mscorlib]System.Object::ToString()
0x3863  stelem.ref
0x3864  dup
0x3865  ldc.i4.3
0x3866  call     string [mscorlib]System.Environment::get_NewLine()
0x386b  stelem.ref
0x386c  dup
0x386d  ldc.i4.4
0x386e  ldstr    asc_58824// "   "
0x3873  stelem.ref
0x3874  dup
0x3875  ldc.i4.5
0x3876  ldstr    aXmlEndofinnere// "Xml_EndOfInnerExceptionStack"
0x387b  ldc.i4.0
0x387c  newarr   [mscorlib]System.String
0x3881  call     string System.Xml.Xsl.XslTransformException::CreateMessage(string res, string[] args)
0x3886  stelem.ref
0x3887  call     string [mscorlib]System.String::Concat(string[])
0x388c  stloc.0
0x388d  ldarg.0
0x388e  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x3893  brfalse.s loc_38A7
0x3895  ldloc.0
0x3896  call     string [mscorlib]System.Environment::get_NewLine()
0x389b  ldarg.0
0x389c  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x38a1  call     string [mscorlib]System.String::Concat(string, string, string)
0x38a6  stloc.0
0x38a7  ldloc.0
0x38a8  ret
```
