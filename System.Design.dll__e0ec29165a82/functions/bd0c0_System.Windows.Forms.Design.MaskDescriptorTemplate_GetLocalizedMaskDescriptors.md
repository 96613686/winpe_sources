# System.Windows.Forms.Design.MaskDescriptorTemplate::GetLocalizedMaskDescriptors

- ea: `0xbd0c0`
- end: `0xbdeb4`
- name: `System.Windows.Forms.Design.MaskDescriptorTemplate::GetLocalizedMaskDescriptors`
- size: `3572`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xbe910`

## callees

- `0xbd010`
- `0xbd0c0`
- `0xef340`
- `0x11c7f0`
- `0x11c810`
- `0x11c820`

## string_xrefs

- `0xbd30d`: `Social security number`
- `0xbd416`: `Social Security Number`
- `0xbd5bd`: `Numéro de Sécurité Sociale (France)`

## pseudocode

```c

```

## disassembly

```asm
0xbd0c0  newobj   instance void ValidMaskDescriptorList::.ctor()
0xbd0c5  stloc.0
0xbd0c6  ldarg.0
0xbd0c7  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_Parent()
0xbd0cc  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0xbd0d1  stloc.2
0xbd0d2  ldloc.2
0xbd0d3  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0xbd0d8  stloc.3
0xbd0d9  ldloc.3
0xbd0da  ldc.i4   0x44BC8642
0xbd0df  bgt.un.s loc_BD132
0xbd0e1  ldloc.3
0xbd0e2  ldc.i4   0x3FBC7E63
0xbd0e7  bgt.un.s loc_BD10F
0xbd0e9  ldloc.3
0xbd0ea  ldc.i4   0x5B29CB
0xbd0ef  beq      loc_BD237
0xbd0f4  ldloc.3
0xbd0f5  ldc.i4   0x55B31AA
0xbd0fa  beq      loc_BD213
0xbd0ff  ldloc.3
0xbd100  ldc.i4   0x3FBC7E63
0xbd105  beq      loc_BD225
0xbd10a  br       loc_BD259
0xbd10f  ldloc.3
0xbd110  ldc.i4   0x411A658A
0xbd115  beq.s    loc_BD177
0xbd117  ldloc.3
0xbd118  ldc.i4   0x423CF95F
0xbd11d  beq      loc_BD249
0xbd122  ldloc.3
0xbd123  ldc.i4   0x44BC8642
0xbd128  beq      loc_BD201
0xbd12d  br       loc_BD259
0xbd132  ldloc.3
0xbd133  ldc.i4   0x5722D6F1
0xbd138  bgt.un.s loc_BD15A
0xbd13a  ldloc.3
0xbd13b  ldc.i4   0x461A6D69
0xbd140  beq      loc_BD1DD
0xbd145  ldloc.3
0xbd146  ldc.i4   0x47388410
0xbd14b  beq.s    loc_BD1CB
0xbd14d  ldloc.3
0xbd14e  ldc.i4   0x5722D6F1
0xbd153  beq.s    loc_BD1B6
0xbd155  br       loc_BD259
0xbd15a  ldloc.3
0xbd15b  ldc.i4   0x5C1CCEA2
0xbd160  beq.s    loc_BD1A1
0xbd162  ldloc.3
0xbd163  ldc.i4   0x5D251EFA
0xbd168  beq.s    loc_BD18C
0xbd16a  ldloc.3
0xbd16b  ldc.i4   0x6C3F7A14
0xbd170  beq.s    loc_BD1EF
0xbd172  br       loc_BD259
0xbd177  ldloc.2
0xbd178  ldstr    aEn// "en"
0xbd17d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbd182  brtrue   loc_BD260
0xbd187  br       loc_BD259
0xbd18c  ldloc.2
0xbd18d  ldstr    aAr// "ar"
0xbd192  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbd197  brtrue   loc_BD38E
0xbd19c  br       loc_BD259
0xbd1a1  ldloc.2
0xbd1a2  ldstr    aDe// "de"
0xbd1a7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbd1ac  brtrue   loc_BD47B
0xbd1b1  br       loc_BD259
0xbd1b6  ldloc.2
0xbd1b7  ldstr    aFr// "fr"
0xbd1bc  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbd1c1  brtrue   loc_BD50B
0xbd1c6  br       loc_BD259
0xbd1cb  ldloc.2
0xbd1cc  ldstr    aIt// "it"
0xbd1d1  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbd1d6  brtrue   loc_BD619
0xbd1db  br.s     loc_BD259
0xbd1dd  ldloc.2
0xbd1de  ldstr    aEs// "es"
0xbd1e3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbd1e8  brtrue   loc_BD706
0xbd1ed  br.s     loc_BD259
0xbd1ef  ldloc.2
0xbd1f0  ldstr    aJa// "ja"
0xbd1f5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbd1fa  brtrue   loc_BD82B
0xbd1ff  br.s     loc_BD259
0xbd201  ldloc.2
0xbd202  ldstr    aZhChs// "zh-CHS"
0xbd207  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbd20c  brtrue   loc_BDA1B
0xbd211  br.s     loc_BD259
0xbd213  ldloc.2
0xbd214  ldstr    aZhHans// "zh-Hans"
0xbd219  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbd21e  brtrue   loc_BDA1B
0xbd223  br.s     loc_BD259
0xbd225  ldloc.2
0xbd226  ldstr    aZhCht// "zh-CHT"
0xbd22b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbd230  brtrue   loc_BDBCB
0xbd235  br.s     loc_BD259
0xbd237  ldloc.2
0xbd238  ldstr    aZhHant// "zh-Hant"
0xbd23d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbd242  brtrue   loc_BDBCB
0xbd247  br.s     loc_BD259
0xbd249  ldloc.2
0xbd24a  ldstr    aKo// "ko"
0xbd24f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbd254  brtrue   loc_BDD1E
0xbd259  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbd25e  starg.s  0
0xbd260  ldloc.0
0xbd261  ldstr    a00000// "00000"
0xbd266  ldstr    aNumeric5Digits// "Numeric (5-digits)"
0xbd26b  ldstr    a12345// "12345"
0xbd270  ldtoken  [mscorlib]System.Int32
0xbd275  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbd27a  ldarg.0
0xbd27b  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd280  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd285  ldloc.0
0xbd286  ldstr    a9990000000// "(999) 000-0000"
0xbd28b  ldstr    aPhoneNumber// "Phone number"
0xbd290  ldstr    a5745550123// "5745550123"
0xbd295  ldnull
0xbd296  ldarg.0
0xbd297  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd29c  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd2a1  ldloc.0
0xbd2a2  ldstr    a0000000// "000-0000"
0xbd2a7  ldstr    aPhoneNumberNoA// "Phone number no area code"
0xbd2ac  ldstr    a5550123// "5550123"
0xbd2b1  ldnull
0xbd2b2  ldarg.0
0xbd2b3  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd2b8  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd2bd  ldloc.0
0xbd2be  ldstr    a00000000// "00/00/0000"
0xbd2c3  ldstr    aShortDate// "Short date"
0xbd2c8  ldstr    a12112003// "12112003"
0xbd2cd  ldtoken  [mscorlib]System.DateTime
0xbd2d2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbd2d7  ldarg.0
0xbd2d8  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd2dd  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd2e2  ldloc.0
0xbd2e3  ldstr    a000000009000// "00/00/0000 90:00"
0xbd2e8  ldstr    aShortDateAndTi// "Short date and time (US)"
0xbd2ed  ldstr    a121120031120// "121120031120"
0xbd2f2  ldtoken  [mscorlib]System.DateTime
0xbd2f7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbd2fc  ldarg.0
0xbd2fd  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd302  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd307  ldloc.0
0xbd308  ldstr    a000000000// "000-00-0000"
0xbd30d  ldstr    aSocialSecurity// "Social security number"
0xbd312  ldstr    a000001234// "000001234"
0xbd317  ldnull
0xbd318  ldarg.0
0xbd319  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd31e  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd323  ldloc.0
0xbd324  ldstr    a9000// "90:00"
0xbd329  ldstr    aTimeUs// "Time (US)"
0xbd32e  ldstr    a1120// "1120"
0xbd333  ldtoken  [mscorlib]System.DateTime
0xbd338  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbd33d  ldarg.0
0xbd33e  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd343  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd348  ldloc.0
0xbd349  ldstr    a0000// "00:00"
0xbd34e  ldstr    aTimeEuropeanMi// "Time (European/Military)"
0xbd353  ldstr    a2320// "2320"
0xbd358  ldtoken  [mscorlib]System.DateTime
0xbd35d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbd362  ldarg.0
0xbd363  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd368  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd36d  ldloc.0
0xbd36e  ldstr    a000009999// "00000-9999"
0xbd373  ldstr    aZipCode// "Zip Code"
0xbd378  ldstr    a980526399// "980526399"
0xbd37d  ldnull
0xbd37e  ldarg.0
0xbd37f  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd384  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd389  br       loc_BDEAD
0xbd38e  ldloc.0
0xbd38f  ldstr    a9990000000_0// "(999)000-0000"
0xbd394  ldstr    aPhoneNumber_0// "Phone Number"
0xbd399  ldstr    a0123456789// "0123456789"
0xbd39e  ldnull
0xbd39f  ldarg.0
0xbd3a0  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd3a5  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd3aa  ldloc.0
0xbd3ab  ldstr    a0000000// "000-0000"
0xbd3b0  ldstr    aPhoneNumberNoA_0// "Phone Number no Area Code"
0xbd3b5  ldstr    a1234567// "1234567"
0xbd3ba  ldnull
0xbd3bb  ldarg.0
0xbd3bc  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd3c1  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd3c6  ldloc.0
0xbd3c7  ldstr    a00000000_0// "00 /00 /0000"
0xbd3cc  ldstr    aShortDate_0// "Short Date"
0xbd3d1  ldstr    a26102005// "26102005"
0xbd3d6  ldtoken  [mscorlib]System.DateTime
0xbd3db  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbd3e0  ldarg.0
0xbd3e1  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd3e6  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd3eb  ldloc.0
0xbd3ec  ldstr    a000000000000// "00 /00 /0000 00:00"
0xbd3f1  ldstr    aShortDateTime// "Short Date/Time"
0xbd3f6  ldstr    a261020051430// "261020051430"
0xbd3fb  ldtoken  [mscorlib]System.DateTime
0xbd400  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbd405  ldarg.0
0xbd406  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd40b  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd410  ldloc.0
0xbd411  ldstr    a000000000// "000-00-0000"
0xbd416  ldstr    aSocialSecurity_0// "Social Security Number"
0xbd41b  ldstr    a123456789// "123456789"
0xbd420  ldnull
0xbd421  ldarg.0
0xbd422  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd427  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd42c  ldloc.0
0xbd42d  ldstr    a9000// "90:00"
0xbd432  ldstr    aTime// "Time"
0xbd437  ldstr    a230// " 230"
0xbd43c  ldtoken  [mscorlib]System.DateTime
0xbd441  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbd446  ldarg.0
0xbd447  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd44c  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd451  ldloc.0
0xbd452  ldstr    a0000// "00:00"
0xbd457  ldstr    aTime24Hour// "Time (24 Hour)"
0xbd45c  ldstr    a1430// "1430"
0xbd461  ldtoken  [mscorlib]System.DateTime
0xbd466  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbd46b  ldarg.0
0xbd46c  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd471  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd476  br       loc_BDEAD
0xbd47b  ldloc.0
0xbd47c  ldstr    a00000000// "00/00/0000"
0xbd481  ldstr    aDatumKurz// "Datum kurz"
0xbd486  ldstr    a28112005// "28112005"
0xbd48b  ldtoken  [mscorlib]System.DateTime
0xbd490  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbd495  ldarg.0
0xbd496  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd49b  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd4a0  ldloc.0
0xbd4a1  ldstr    a000000000000_0// "00/00/0000 00:00"
0xbd4a6  ldstr    aDatumLang// "Datum lang"
0xbd4ab  ldstr    a281120051430// "281120051430"
0xbd4b0  ldtoken  [mscorlib]System.DateTime
0xbd4b5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbd4ba  ldarg.0
0xbd4bb  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd4c0  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd4c5  ldloc.0
0xbd4c6  ldstr    a9000// "90:00"
0xbd4cb  ldstr    aZeit// "Zeit"
0xbd4d0  ldstr    a1430// "1430"
0xbd4d5  ldtoken  [mscorlib]System.DateTime
0xbd4da  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbd4df  ldarg.0
0xbd4e0  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd4e5  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd4ea  ldloc.0
0xbd4eb  ldstr    a00000// "00000"
0xbd4f0  ldstr    aPostleitzahl// "Postleitzahl"
0xbd4f5  ldstr    a91450// "91450"
0xbd4fa  ldnull
0xbd4fb  ldarg.0
0xbd4fc  newobj   instance void System.Windows.Forms.Design.MaskDescriptorTemplate::.ctor(string mask, string name, string sample, class [mscorlib]System.Type validatingType, class [mscorlib]System.Globalization.CultureInfo culture)
0xbd501  callvirt instance void ValidMaskDescriptorList::Add(class System.Windows.Forms.Design.MaskDescriptorTemplate mdt)
0xbd506  br       loc_BDEAD
0xbd50b  ldarg.0
0xbd50c  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0xbd511  ldstr    aFrCa// "fr-CA"
0xbd516  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbd51b  brtrue.s loc_BD524
0xbd51d  ldstr    a28112005// "28112005"
  ... truncated ...
```
