# System.Windows.Forms.Design.MaskDescriptor::IsValidMaskDescriptor_0

- ea: `0xbcc90`
- end: `0xbcd9c`
- name: `System.Windows.Forms.Design.MaskDescriptor::IsValidMaskDescriptor_0`
- size: `268`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0xbcc80`
- `0xbd020`
- `0xbed80`

## callees

- `0x8ef40`
- `0xbcc30`
- `0xbcc40`
- `0xbcc50`
- `0xbcc60`
- `0xbcc70`
- `0xbcc90`

## string_xrefs

- `0xbcc9b`: `MaskDescriptorNull`
- `0xbccd0`: `MaskDescriptorNullOrEmptyRequiredProperty`

## pseudocode

```c

```

## disassembly

```asm
0xbcc90  ldarg.1
0xbcc91  ldsfld   string [mscorlib]System.String::Empty
0xbcc96  stind.ref
0xbcc97  ldarg.0
0xbcc98  brtrue.s loc_BCCA8
0xbcc9a  ldarg.1
0xbcc9b  ldstr    aMaskdescriptor// "MaskDescriptorNull"
0xbcca0  call     string System.Design.SR::GetString(string name)
0xbcca5  stind.ref
0xbcca6  ldc.i4.0
0xbcca7  ret
0xbcca8  ldarg.0
0xbcca9  callvirt instance string System.Windows.Forms.Design.MaskDescriptor::get_Mask()
0xbccae  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbccb3  brtrue.s loc_BCCCF
0xbccb5  ldarg.0
0xbccb6  callvirt instance string System.Windows.Forms.Design.MaskDescriptor::get_Name()
0xbccbb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbccc0  brtrue.s loc_BCCCF
0xbccc2  ldarg.0
0xbccc3  callvirt instance string System.Windows.Forms.Design.MaskDescriptor::get_Sample()
0xbccc8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbcccd  brfalse.s loc_BCCDD
0xbcccf  ldarg.1
0xbccd0  ldstr    aMaskdescriptor_0// "MaskDescriptorNullOrEmptyRequiredProper"...
0xbccd5  call     string System.Design.SR::GetString(string name)
0xbccda  stind.ref
0xbccdb  ldc.i4.0
0xbccdc  ret
0xbccdd  ldarg.0
0xbccde  callvirt instance string System.Windows.Forms.Design.MaskDescriptor::get_Mask()
0xbcce3  ldarg.0
0xbcce4  callvirt instance class [mscorlib]System.Globalization.CultureInfo System.Windows.Forms.Design.MaskDescriptor::get_Culture()
0xbcce9  newobj   instance void [System]System.ComponentModel.MaskedTextProvider::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0xbccee  stloc.0
0xbccef  ldloc.0
0xbccf0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MaskedTextBox::.ctor(class [System]System.ComponentModel.MaskedTextProvider)
0xbccf5  stloc.1
0xbccf6  ldloc.1
0xbccf7  ldc.i4.1
0xbccf8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MaskedTextBox::set_SkipLiterals(bool)
0xbccfd  ldloc.1
0xbccfe  ldc.i4.1
0xbccff  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MaskedTextBox::set_ResetOnPrompt(bool)
0xbcd04  ldloc.1
0xbcd05  ldc.i4.1
0xbcd06  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MaskedTextBox::set_ResetOnSpace(bool)
0xbcd0b  ldloc.1
0xbcd0c  ldarg.0
0xbcd0d  callvirt instance class [mscorlib]System.Type System.Windows.Forms.Design.MaskDescriptor::get_ValidatingType()
0xbcd12  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MaskedTextBox::set_ValidatingType(class [mscorlib]System.Type)
0xbcd17  ldloc.1
0xbcd18  ldarg.0
0xbcd19  callvirt instance class [mscorlib]System.Globalization.CultureInfo System.Windows.Forms.Design.MaskDescriptor::get_Culture()
0xbcd1e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MaskedTextBox::set_FormatProvider(class [mscorlib]System.IFormatProvider)
0xbcd23  ldloc.1
0xbcd24  ldarg.0
0xbcd25  callvirt instance class [mscorlib]System.Globalization.CultureInfo System.Windows.Forms.Design.MaskDescriptor::get_Culture()
0xbcd2a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MaskedTextBox::set_Culture(class [mscorlib]System.Globalization.CultureInfo)
0xbcd2f  ldloc.1
0xbcd30  ldnull
0xbcd31  ldftn    void System.Windows.Forms.Design.MaskDescriptor::maskedTextBox1_TypeValidationCompleted(object sender, class [System.Windows.Forms]System.Windows.Forms.TypeValidationEventArgs e)
0xbcd37  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TypeValidationEventHandler::.ctor(object, native int)
0xbcd3c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MaskedTextBox::add_TypeValidationCompleted(class [System.Windows.Forms]System.Windows.Forms.TypeValidationEventHandler)
0xbcd41  ldloc.1
0xbcd42  ldnull
0xbcd43  ldftn    void System.Windows.Forms.Design.MaskDescriptor::maskedTextBox1_MaskInputRejected(object sender, class [System.Windows.Forms]System.Windows.Forms.MaskInputRejectedEventArgs e)
0xbcd49  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MaskInputRejectedEventHandler::.ctor(object, native int)
0xbcd4e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.MaskedTextBox::add_MaskInputRejected(class [System.Windows.Forms]System.Windows.Forms.MaskInputRejectedEventHandler)
0xbcd53  ldloc.1
0xbcd54  ldarg.0
0xbcd55  callvirt instance string System.Windows.Forms.Design.MaskDescriptor::get_Sample()
0xbcd5a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xbcd5f  ldloc.1
0xbcd60  callvirt instance object [System.Windows.Forms]System.Windows.Forms.Control::get_Tag()
0xbcd65  brtrue.s loc_BCD7C
0xbcd67  ldarg.0
0xbcd68  callvirt instance class [mscorlib]System.Type System.Windows.Forms.Design.MaskDescriptor::get_ValidatingType()
0xbcd6d  ldnull
0xbcd6e  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xbcd73  brfalse.s loc_BCD7C
0xbcd75  ldloc.1
0xbcd76  callvirt instance object [System.Windows.Forms]System.Windows.Forms.MaskedTextBox::ValidateText()
0xbcd7b  pop
0xbcd7c  ldloc.1
0xbcd7d  callvirt instance object [System.Windows.Forms]System.Windows.Forms.Control::get_Tag()
0xbcd82  brfalse.s loc_BCD91
0xbcd84  ldarg.1
0xbcd85  ldloc.1
0xbcd86  callvirt instance object [System.Windows.Forms]System.Windows.Forms.Control::get_Tag()
0xbcd8b  callvirt instance string [mscorlib]System.Object::ToString()
0xbcd90  stind.ref
0xbcd91  ldarg.1
0xbcd92  ldind.ref
0xbcd93  callvirt instance int32 [mscorlib]System.String::get_Length()
0xbcd98  ldc.i4.0
0xbcd99  ceq
0xbcd9b  ret
```
