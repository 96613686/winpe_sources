# System.Xaml.XamlLanguage::LookupXamlType

- ea: `0x9040`
- end: `0x948a`
- name: `System.Xaml.XamlLanguage::LookupXamlType`
- size: `1098`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `loader_planting`

## callers

- `0xb980`

## callees

- `0x8920`
- `0x8940`
- `0x8950`
- `0x8960`
- `0x8970`
- `0x8980`
- `0x8990`
- `0x89a0`
- `0x89b0`
- `0x89c0`
- `0x89d0`
- `0x89e0`
- `0x89f0`
- `0x8a00`
- `0x8a10`
- `0x8a20`
- `0x8a30`
- `0x8a40`
- `0x8a50`
- `0x8a60`
- `0x8a70`
- `0x8a80`
- `0x9040`
- `0x27820`

## string_xrefs

- `0x9202`: `ArrayExtension`
- `0x9241`: `NullExtension`
- `0x9280`: `ReferenceExtension`
- `0x92aa`: `StaticExtension`
- `0x92d4`: `TypeExtension`

## pseudocode

```c

```

## disassembly

```asm
0x9040  call     class [mscorlib]System.Collections.Generic.IList`1<string> System.Xaml.XamlLanguage::get_XamlNamespaces()
0x9045  ldarg.0
0x9046  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x904b  brfalse  loc_9488
0x9050  ldarg.1
0x9051  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x9056  stloc.0
0x9057  ldloc.0
0x9058  ldc.i4   0x9018E81C
0x905d  bgt.un   loc_912A
0x9062  ldloc.0
0x9063  ldc.i4   0x298E5E84
0x9068  bgt.un.s loc_90BE
0x906a  ldloc.0
0x906b  ldc.i4   0x18A43C5B
0x9070  bgt.un.s loc_9098
0x9072  ldloc.0
0x9073  ldc.i4   0x16C8FCC6
0x9078  beq      loc_91EC
0x907d  ldloc.0
0x907e  ldc.i4   0x17000129
0x9083  beq      loc_9240
0x9088  ldloc.0
0x9089  ldc.i4   0x18A43C5B
0x908e  beq      loc_9294
0x9093  br       loc_9486
0x9098  ldloc.0
0x9099  ldc.i4   0x23F6BD6F
0x909e  beq      loc_9201
0x90a3  ldloc.0
0x90a4  ldc.i4   0x2879E23D
0x90a9  beq      loc_9390
0x90ae  ldloc.0
0x90af  ldc.i4   0x298E5E84
0x90b4  beq      loc_933C
0x90b9  br       loc_9486
0x90be  ldloc.0
0x90bf  ldc.i4   0x5221F9E8
0x90c4  bgt.un.s loc_90EC
0x90c6  ldloc.0
0x90c7  ldc.i4   0x2D9FADF1
0x90cc  beq      loc_9312
0x90d1  ldloc.0
0x90d2  ldc.i4   0x500FF16F
0x90d7  beq      loc_9366
0x90dc  ldloc.0
0x90dd  ldc.i4   0x5221F9E8
0x90e2  beq      loc_9255
0x90e7  br       loc_9486
0x90ec  ldloc.0
0x90ed  ldc.i4   0x7D04316B
0x90f2  bgt.un.s loc_910F
0x90f4  ldloc.0
0x90f5  ldc.i4   0x604F4858
0x90fa  beq      loc_92E8
0x90ff  ldloc.0
0x9100  ldc.i4   0x7D04316B
0x9105  beq      loc_927F
0x910a  br       loc_9486
0x910f  ldloc.0
0x9110  ldc.i4   0x8E464C28
0x9115  beq      loc_92FD
0x911a  ldloc.0
0x911b  ldc.i4   0x9018E81C
0x9120  beq      loc_93F9
0x9125  br       loc_9486
0x912a  ldloc.0
0x912b  ldc.i4   0xB24F5642
0x9130  bgt.un.s loc_9186
0x9132  ldloc.0
0x9133  ldc.i4   0xA19A545F
0x9138  bgt.un.s loc_9160
0x913a  ldloc.0
0x913b  ldc.i4   0x92D4BBDC
0x9140  beq      loc_92A9
0x9145  ldloc.0
0x9146  ldc.i4   0x9A19EB9D
0x914b  beq      loc_93E4
0x9150  ldloc.0
0x9151  ldc.i4   0xA19A545F
0x9156  beq      loc_9327
0x915b  br       loc_9486
0x9160  ldloc.0
0x9161  ldc.i4   0xA5AAF4EC
0x9166  beq      loc_93CF
0x916b  ldloc.0
0x916c  ldc.i4   0xADC8C33A
0x9171  beq      loc_926A
0x9176  ldloc.0
0x9177  ldc.i4   0xB24F5642
0x917c  beq      loc_92D3
0x9181  br       loc_9486
0x9186  ldloc.0
0x9187  ldc.i4   0xE58E64DA
0x918c  bgt.un.s loc_91B4
0x918e  ldloc.0
0x918f  ldc.i4   0xCB39993F
0x9194  beq      loc_93BA
0x9199  ldloc.0
0x919a  ldc.i4   0xD155D06D
0x919f  beq      loc_92BE
0x91a4  ldloc.0
0x91a5  ldc.i4   0xE58E64DA
0x91aa  beq      loc_937B
0x91af  br       loc_9486
0x91b4  ldloc.0
0x91b5  ldc.i4   0xF1776509
0x91ba  bgt.un.s loc_91D7
0x91bc  ldloc.0
0x91bd  ldc.i4   0xEC95435F
0x91c2  beq      loc_9351
0x91c7  ldloc.0
0x91c8  ldc.i4   0xF1776509
0x91cd  beq      loc_93A5
0x91d2  br       loc_9486
0x91d7  ldloc.0
0x91d8  ldc.i4   0xF73397C4
0x91dd  beq.s    loc_922B
0x91df  ldloc.0
0x91e0  ldc.i4   0xFEF5FCE3
0x91e5  beq.s    loc_9216
0x91e7  br       loc_9486
0x91ec  ldarg.1
0x91ed  ldstr    aArray// "Array"
0x91f2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x91f7  brtrue   loc_9408
0x91fc  br       loc_9486
0x9201  ldarg.1
0x9202  ldstr    aArrayextension// "ArrayExtension"
0x9207  call     bool [mscorlib]System.String::op_Equality(string, string)
0x920c  brtrue   loc_9408
0x9211  br       loc_9486
0x9216  ldarg.1
0x9217  ldstr    aMember// "Member"
0x921c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9221  brtrue   loc_940E
0x9226  br       loc_9486
0x922b  ldarg.1
0x922c  ldstr    aNull// "Null"
0x9231  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9236  brtrue   loc_9414
0x923b  br       loc_9486
0x9240  ldarg.1
0x9241  ldstr    aNullextension// "NullExtension"
0x9246  call     bool [mscorlib]System.String::op_Equality(string, string)
0x924b  brtrue   loc_9414
0x9250  br       loc_9486
0x9255  ldarg.1
0x9256  ldstr    aProperty_0// "Property"
0x925b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9260  brtrue   loc_941A
0x9265  br       loc_9486
0x926a  ldarg.1
0x926b  ldstr    aReference// "Reference"
0x9270  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9275  brtrue   loc_9420
0x927a  br       loc_9486
0x927f  ldarg.1
0x9280  ldstr    aReferenceexten// "ReferenceExtension"
0x9285  call     bool [mscorlib]System.String::op_Equality(string, string)
0x928a  brtrue   loc_9420
0x928f  br       loc_9486
0x9294  ldarg.1
0x9295  ldstr    aStatic// "Static"
0x929a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x929f  brtrue   loc_9426
0x92a4  br       loc_9486
0x92a9  ldarg.1
0x92aa  ldstr    aStaticextensio// "StaticExtension"
0x92af  call     bool [mscorlib]System.String::op_Equality(string, string)
0x92b4  brtrue   loc_9426
0x92b9  br       loc_9486
0x92be  ldarg.1
0x92bf  ldstr    aType_0// "Type"
0x92c4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x92c9  brtrue   loc_942C
0x92ce  br       loc_9486
0x92d3  ldarg.1
0x92d4  ldstr    aTypeextension// "TypeExtension"
0x92d9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x92de  brtrue   loc_942C
0x92e3  br       loc_9486
0x92e8  ldarg.1
0x92e9  ldstr    aString// "String"
0x92ee  call     bool [mscorlib]System.String::op_Equality(string, string)
0x92f3  brtrue   loc_9432
0x92f8  br       loc_9486
0x92fd  ldarg.1
0x92fe  ldstr    aDouble// "Double"
0x9303  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9308  brtrue   loc_9438
0x930d  br       loc_9486
0x9312  ldarg.1
0x9313  ldstr    aInt16// "Int16"
0x9318  call     bool [mscorlib]System.String::op_Equality(string, string)
0x931d  brtrue   loc_943E
0x9322  br       loc_9486
0x9327  ldarg.1
0x9328  ldstr    aInt32// "Int32"
0x932d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9332  brtrue   loc_9444
0x9337  br       loc_9486
0x933c  ldarg.1
0x933d  ldstr    aInt64// "Int64"
0x9342  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9347  brtrue   loc_944A
0x934c  br       loc_9486
0x9351  ldarg.1
0x9352  ldstr    aBoolean// "Boolean"
0x9357  call     bool [mscorlib]System.String::op_Equality(string, string)
0x935c  brtrue   loc_9450
0x9361  br       loc_9486
0x9366  ldarg.1
0x9367  ldstr    aXdata// "XData"
0x936c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9371  brtrue   loc_9456
0x9376  br       loc_9486
0x937b  ldarg.1
0x937c  ldstr    aObject// "Object"
0x9381  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9386  brtrue   loc_945C
0x938b  br       loc_9486
0x9390  ldarg.1
0x9391  ldstr    aChar// "Char"
0x9396  call     bool [mscorlib]System.String::op_Equality(string, string)
0x939b  brtrue   loc_9462
0x93a0  br       loc_9486
0x93a5  ldarg.1
0x93a6  ldstr    aSingle// "Single"
0x93ab  call     bool [mscorlib]System.String::op_Equality(string, string)
0x93b0  brtrue   loc_9468
0x93b5  br       loc_9486
0x93ba  ldarg.1
0x93bb  ldstr    aByte// "Byte"
0x93c0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x93c5  brtrue   loc_946E
0x93ca  br       loc_9486
0x93cf  ldarg.1
0x93d0  ldstr    aDecimal// "Decimal"
0x93d5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x93da  brtrue   loc_9474
0x93df  br       loc_9486
0x93e4  ldarg.1
0x93e5  ldstr    aUri// "Uri"
0x93ea  call     bool [mscorlib]System.String::op_Equality(string, string)
0x93ef  brtrue   loc_947A
0x93f4  br       loc_9486
0x93f9  ldarg.1
0x93fa  ldstr    aTimespan// "TimeSpan"
0x93ff  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9404  brtrue.s loc_9480
0x9406  br.s     loc_9486
0x9408  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Array()
0x940d  ret
0x940e  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Member()
0x9413  ret
0x9414  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Null()
0x9419  ret
0x941a  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Property()
0x941f  ret
0x9420  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Reference()
0x9425  ret
0x9426  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Static()
0x942b  ret
0x942c  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Type()
0x9431  ret
0x9432  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_String()
0x9437  ret
0x9438  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Double()
0x943d  ret
0x943e  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Int16()
0x9443  ret
0x9444  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Int32()
0x9449  ret
0x944a  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Int64()
0x944f  ret
0x9450  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Boolean()
0x9455  ret
0x9456  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_XData()
0x945b  ret
0x945c  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Object()
0x9461  ret
0x9462  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Char()
0x9467  ret
0x9468  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Single()
0x946d  ret
0x946e  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Byte()
0x9473  ret
0x9474  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Decimal()
0x9479  ret
0x947a  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Uri()
0x947f  ret
0x9480  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_TimeSpan()
0x9485  ret
0x9486  ldnull
0x9487  ret
0x9488  ldnull
0x9489  ret
```
