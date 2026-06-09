# Microsoft.SharePoint.Utilities.Mime.MailBnfHelper::ReadQuotedString

- ea: `0x2bfd0`
- end: `0x2c0dc`
- name: `Microsoft.SharePoint.Utilities.Mime.MailBnfHelper::ReadQuotedString`
- size: `268`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2b140`
- `0x2c100`

## callees

- `0x29cd0`
- `0x2bfd0`
- `0x2ca50`

## string_xrefs

- `0x2c0c1`: `MimeReaderMalformedHeader`

## pseudocode

```c

```

## disassembly

```asm
0x2bfd0  ldarg.1
0x2bfd1  dup
0x2bfd2  ldind.i4
0x2bfd3  ldc.i4.1
0x2bfd4  add
0x2bfd5  dup
0x2bfd6  stloc.2
0x2bfd7  stind.i4
0x2bfd8  ldloc.2
0x2bfd9  stloc.0
0x2bfda  ldarg.2
0x2bfdb  brtrue.s loc_2BFE4
0x2bfdd  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2bfe2  br.s     loc_2BFE5
0x2bfe4  ldarg.2
0x2bfe5  stloc.1
0x2bfe6  br       loc_2C0B4
0x2bfeb  ldarg.0
0x2bfec  ldarg.1
0x2bfed  ldind.i4
0x2bfee  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2bff3  ldc.i4.s 0x5C
0x2bff5  bne.un.s loc_2C013
0x2bff7  ldloc.1
0x2bff8  ldarg.0
0x2bff9  ldloc.0
0x2bffa  ldarg.1
0x2bffb  ldind.i4
0x2bffc  ldloc.0
0x2bffd  sub
0x2bffe  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string, int32, int32)
0x2c003  pop
0x2c004  ldarg.1
0x2c005  dup
0x2c006  ldind.i4
0x2c007  ldc.i4.1
0x2c008  add
0x2c009  dup
0x2c00a  stloc.3
0x2c00b  stind.i4
0x2c00c  ldloc.3
0x2c00d  stloc.0
0x2c00e  br       loc_2C0AE
0x2c013  ldarg.0
0x2c014  ldarg.1
0x2c015  ldind.i4
0x2c016  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2c01b  ldc.i4.s 0x22
0x2c01d  bne.un.s loc_2C03E
0x2c01f  ldloc.1
0x2c020  ldarg.0
0x2c021  ldloc.0
0x2c022  ldarg.1
0x2c023  ldind.i4
0x2c024  ldloc.0
0x2c025  sub
0x2c026  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string, int32, int32)
0x2c02b  pop
0x2c02c  ldarg.1
0x2c02d  dup
0x2c02e  ldind.i4
0x2c02f  ldc.i4.1
0x2c030  add
0x2c031  stind.i4
0x2c032  ldarg.2
0x2c033  brtrue.s loc_2C03C
0x2c035  ldloc.1
0x2c036  callvirt instance string [mscorlib]System.Object::ToString()
0x2c03b  ret
0x2c03c  ldnull
0x2c03d  ret
0x2c03e  ldarg.0
0x2c03f  ldarg.1
0x2c040  ldind.i4
0x2c041  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2c046  ldsfld   bool[] Microsoft.SharePoint.Utilities.Mime.MailBnfHelper::s_fqtext
0x2c04b  ldlen
0x2c04c  conv.i4
0x2c04d  bge.s    loc_2C05F
0x2c04f  ldsfld   bool[] Microsoft.SharePoint.Utilities.Mime.MailBnfHelper::s_fqtext
0x2c054  ldarg.0
0x2c055  ldarg.1
0x2c056  ldind.i4
0x2c057  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2c05c  ldelem.i1
0x2c05d  brtrue.s loc_2C0AE
0x2c05f  ldstr    aMimeheaderinva// "MimeHeaderInvalidCharacter"
0x2c064  ldc.i4.2
0x2c065  newarr   [mscorlib]System.Object
0x2c06a  stloc.s  4
0x2c06c  ldloc.s  4
0x2c06e  ldc.i4.0
0x2c06f  ldarg.0
0x2c070  ldarg.1
0x2c071  ldind.i4
0x2c072  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2c077  box      [mscorlib]System.Char
0x2c07c  stelem.ref
0x2c07d  ldloc.s  4
0x2c07f  ldc.i4.1
0x2c080  ldarg.0
0x2c081  ldarg.1
0x2c082  ldind.i4
0x2c083  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2c088  stloc.s  5
0x2c08a  ldloca.s 5
0x2c08c  ldstr    aX_0// "X"
0x2c091  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2c096  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x2c09b  stelem.ref
0x2c09c  ldloc.s  4
0x2c09e  call     string Microsoft.SharePoint.Utilities.Mime.SR::GetString(string resourceId, object[] args)
0x2c0a3  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2c0a8  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperError(class [mscorlib]System.Exception ex)
0x2c0ad  throw
0x2c0ae  ldarg.1
0x2c0af  dup
0x2c0b0  ldind.i4
0x2c0b1  ldc.i4.1
0x2c0b2  add
0x2c0b3  stind.i4
0x2c0b4  ldarg.1
0x2c0b5  ldind.i4
0x2c0b6  ldarg.0
0x2c0b7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2c0bc  blt      loc_2BFEB
0x2c0c1  ldstr    aMimereadermalf// "MimeReaderMalformedHeader"
0x2c0c6  ldc.i4.0
0x2c0c7  newarr   [mscorlib]System.Object
0x2c0cc  call     string Microsoft.SharePoint.Utilities.Mime.SR::GetString(string resourceId, object[] args)
0x2c0d1  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2c0d6  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperError(class [mscorlib]System.Exception ex)
0x2c0db  throw
```
