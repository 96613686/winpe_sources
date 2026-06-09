# Microsoft.Internal.GDIExporter.TrueTypeFont::ReplaceAll

- ea: `0x23050`
- end: `0x231ff`
- name: `Microsoft.Internal.GDIExporter.TrueTypeFont::ReplaceAll`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x22e70`

## callees

- `0x23050`
- `0x23220`
- `0x23340`
- `0x23410`
- `0x23470`

## pseudocode

```c

```

## disassembly

```asm
0x23050  ldc.i4.0
0x23051  stloc.0
0x23052  ldnull
0x23053  stloc.s  8
0x23055  ldarg.0
0x23056  ldarg.1
0x23057  ldc.i4.2
0x23058  add
0x23059  call     instance unsigned int16 Microsoft.Internal.GDIExporter.TrueTypeFont::read16(unsigned int32 offset)
0x2305e  stloc.s  0xF
0x23060  ldarg.0
0x23061  ldarg.1
0x23062  ldc.i4.4
0x23063  add
0x23064  call     instance unsigned int16 Microsoft.Internal.GDIExporter.TrueTypeFont::read16(unsigned int32 offset)
0x23069  stloc.s  0x10
0x2306b  ldc.i4.0
0x2306c  stloc.s  7
0x2306e  ldc.i4.0
0x2306f  stloc.s  0xB
0x23071  ldc.i4.0
0x23072  stloc.s  6
0x23074  ldc.i4.0
0x23075  ldloc.s  0xF
0x23077  bge.un   loc_231FD
0x2307c  ldloc.s  6
0x2307e  ldc.i4.s 0xC
0x23080  mul
0x23081  ldarg.1
0x23082  add
0x23083  ldc.i4.6
0x23084  add
0x23085  stloc.s  4
0x23087  ldarg.0
0x23088  ldloc.s  4
0x2308a  call     instance unsigned int16 Microsoft.Internal.GDIExporter.TrueTypeFont::read16(unsigned int32 offset)
0x2308f  stloc.s  5
0x23091  ldarg.0
0x23092  ldloc.s  4
0x23094  ldc.i4.2
0x23095  add
0x23096  call     instance unsigned int16 Microsoft.Internal.GDIExporter.TrueTypeFont::read16(unsigned int32 offset)
0x2309b  stloc.3
0x2309c  ldarg.0
0x2309d  ldloc.s  4
0x2309f  ldc.i4.4
0x230a0  add
0x230a1  call     instance unsigned int16 Microsoft.Internal.GDIExporter.TrueTypeFont::read16(unsigned int32 offset)
0x230a6  stloc.s  0xA
0x230a8  ldarg.0
0x230a9  ldloc.s  4
0x230ab  ldc.i4.6
0x230ac  add
0x230ad  call     instance unsigned int16 Microsoft.Internal.GDIExporter.TrueTypeFont::read16(unsigned int32 offset)
0x230b2  stloc.s  0xE
0x230b4  ldarg.0
0x230b5  ldloc.s  4
0x230b7  ldc.i4.8
0x230b8  add
0x230b9  call     instance unsigned int16 Microsoft.Internal.GDIExporter.TrueTypeFont::read16(unsigned int32 offset)
0x230be  stloc.1
0x230bf  ldarg.0
0x230c0  ldloc.s  4
0x230c2  ldc.i4.s 0xA
0x230c4  add
0x230c5  call     instance unsigned int16 Microsoft.Internal.GDIExporter.TrueTypeFont::read16(unsigned int32 offset)
0x230ca  ldloc.s  0x10
0x230cc  add
0x230cd  ldarg.1
0x230ce  add
0x230cf  stloc.2
0x230d0  ldloc.s  0xE
0x230d2  ldc.i4.1
0x230d3  beq      loc_23167
0x230d8  ldloc.s  0xE
0x230da  ldc.i4.4
0x230db  bne.un   loc_231EE
0x230e0  ldloc.s  5
0x230e2  ldc.i4.3
0x230e3  bne.un.s loc_2312C
0x230e5  ldloc.3
0x230e6  ldc.i4.1
0x230e7  beq.s    loc_230EF
0x230e9  ldloc.3
0x230ea  brtrue   loc_231EE
0x230ef  ldloc.s  8
0x230f1  brfalse.s loc_23104
0x230f3  ldloc.s  7
0x230f5  ldc.i4.3
0x230f6  bne.un.s loc_23104
0x230f8  ldloc.s  0xB
0x230fa  ldloc.s  0xA
0x230fc  bne.un.s loc_23104
0x230fe  ldloc.s  8
0x23100  stloc.s  9
0x23102  br.s     loc_23107
0x23104  ldarg.2
0x23105  stloc.s  9
0x23107  ldloc.s  9
0x23109  brfalse  loc_231EE
0x2310e  ldarg.0
0x2310f  ldloc.2
0x23110  ldloc.1
0x23111  ldloc.s  9
0x23113  ldarg.3
0x23114  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_BigEndianUnicode()
0x23119  call     instance bool Microsoft.Internal.GDIExporter.TrueTypeFont::ReplaceFullFamilyName([hasfieldmarshal] unsigned int32 value, unsigned int32 namepos, char[] length, char[] familyName, class [mscorlib]System.Text.Encoding newFamilyName)
0x2311e  brfalse  loc_231EE
0x23123  ldloc.0
0x23124  ldc.i4.1
0x23125  add
0x23126  stloc.0
0x23127  br       loc_231EE
0x2312c  ldloc.s  5
0x2312e  ldc.i4.1
0x2312f  bne.un   loc_231EE
0x23134  ldloc.3
0x23135  brtrue   loc_231EE
0x2313a  ldloc.s  8
0x2313c  brfalse  loc_231EE
0x23141  ldloc.s  7
0x23143  ldc.i4.1
0x23144  bne.un   loc_231EE
0x23149  ldarg.0
0x2314a  ldloc.2
0x2314b  ldloc.1
0x2314c  ldloc.s  8
0x2314e  ldarg.3
0x2314f  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_ASCII()
0x23154  call     instance bool Microsoft.Internal.GDIExporter.TrueTypeFont::ReplaceFullFamilyName([hasfieldmarshal] unsigned int32 value, unsigned int32 namepos, char[] length, char[] familyName, class [mscorlib]System.Text.Encoding newFamilyName)
0x23159  brfalse  loc_231EE
0x2315e  ldloc.0
0x2315f  ldc.i4.1
0x23160  add
0x23161  stloc.0
0x23162  br       loc_231EE
0x23167  ldloc.s  5
0x23169  ldc.i4.3
0x2316a  bne.un.s loc_231AF
0x2316c  ldloc.3
0x2316d  ldc.i4.1
0x2316e  beq.s    loc_23176
0x23170  ldloc.3
0x23171  brtrue   loc_231EE
0x23176  ldarg.0
0x23177  ldloc.2
0x23178  ldloc.1
0x23179  ldloca.s 8
0x2317b  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_BigEndianUnicode()
0x23180  call     instance void Microsoft.Internal.GDIExporter.TrueTypeFont::readString(unsigned int32 offset, unsigned int32 byteLength, char[]& value, class [mscorlib]System.Text.Encoding encoding)
0x23185  ldc.i4.3
0x23186  stloc.s  7
0x23188  ldloc.s  0xA
0x2318a  stloc.s  0xB
0x2318c  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_BigEndianUnicode()
0x23191  stloc.s  0xD
0x23193  ldloc.1
0x23194  ldloc.s  0xD
0x23196  ldarg.3
0x23197  callvirt instance int32 [mscorlib]System.Text.Encoding::GetByteCount(char[])
0x2319c  bne.un.s loc_231EE
0x2319e  ldarg.0
0x2319f  ldloc.2
0x231a0  ldloc.1
0x231a1  ldarg.3
0x231a2  ldloc.s  0xD
0x231a4  call     instance void Microsoft.Internal.GDIExporter.TrueTypeFont::writeString(unsigned int32 offset, unsigned int32 byteLength, char[] value, class [mscorlib]System.Text.Encoding encoding)
0x231a9  ldloc.0
0x231aa  ldc.i4.1
0x231ab  add
0x231ac  stloc.0
0x231ad  br.s     loc_231EE
0x231af  ldloc.s  5
0x231b1  ldc.i4.1
0x231b2  bne.un.s loc_231EE
0x231b4  ldloc.3
0x231b5  brtrue.s loc_231EE
0x231b7  ldarg.0
0x231b8  ldloc.2
0x231b9  ldloc.1
0x231ba  ldloca.s 8
0x231bc  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_ASCII()
0x231c1  call     instance void Microsoft.Internal.GDIExporter.TrueTypeFont::readString(unsigned int32 offset, unsigned int32 byteLength, char[]& value, class [mscorlib]System.Text.Encoding encoding)
0x231c6  ldc.i4.1
0x231c7  stloc.s  7
0x231c9  ldloc.s  0xA
0x231cb  stloc.s  0xB
0x231cd  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_ASCII()
0x231d2  stloc.s  0xC
0x231d4  ldloc.1
0x231d5  ldloc.s  0xC
0x231d7  ldarg.3
0x231d8  callvirt instance int32 [mscorlib]System.Text.Encoding::GetByteCount(char[])
0x231dd  bne.un.s loc_231EE
0x231df  ldarg.0
0x231e0  ldloc.2
0x231e1  ldloc.1
0x231e2  ldarg.3
0x231e3  ldloc.s  0xC
0x231e5  call     instance void Microsoft.Internal.GDIExporter.TrueTypeFont::writeString(unsigned int32 offset, unsigned int32 byteLength, char[] value, class [mscorlib]System.Text.Encoding encoding)
0x231ea  ldloc.0
0x231eb  ldc.i4.1
0x231ec  add
0x231ed  stloc.0
0x231ee  ldloc.s  6
0x231f0  ldc.i4.1
0x231f1  add
0x231f2  stloc.s  6
0x231f4  ldloc.s  6
0x231f6  ldloc.s  0xF
0x231f8  blt.un   loc_2307C
0x231fd  ldloc.0
0x231fe  ret
```
