# System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::Initialize

- ea: `0x1a060`
- end: `0x1a3b1`
- name: `System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::Initialize`
- size: `849`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## string_xrefs

- `0x1a21e`: `SideBarButtonStyleFontUnderline`
- `0x1a22f`: `SideBarButtonStyleFontName`
- `0x1a240`: `SideBarButtonStyleForeColor`
- `0x1a256`: `SideBarButtonStyleBorderWidth`
- `0x1a271`: `SideBarButtonStyleBackColor`
- `0x1a332`: `SideBarStyleBackColor`
- `0x1a348`: `SideBarStyleVerticalAlign`
- `0x1a359`: `SideBarStyleFontSize`
- `0x1a374`: `SideBarStyleFontUnderline`
- `0x1a385`: `SideBarStyleFontStrikeout`
- `0x1a396`: `SideBarStyleBorderWidth`

## pseudocode

```c

```

## disassembly

```asm
0x1a060  ldarg.0
0x1a061  ldstr    aBackcolor// "BackColor"
0x1a066  ldarg.1
0x1a067  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a06c  stfld    string System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::backColor
0x1a071  ldarg.0
0x1a072  ldstr    aBordercolor// "BorderColor"
0x1a077  ldarg.1
0x1a078  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a07d  stfld    string System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::borderColor
0x1a082  ldarg.0
0x1a083  ldstr    aBorderwidth// "BorderWidth"
0x1a088  ldarg.1
0x1a089  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a08e  stfld    string System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::borderWidth
0x1a093  ldarg.0
0x1a094  ldstr    aBorderstyle// "BorderStyle"
0x1a099  ldc.i4.m1
0x1a09a  ldarg.1
0x1a09b  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetIntProperty(string, int32, class [System.Data]System.Data.DataRow)
0x1a0a0  stfld    int32 System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::borderStyle
0x1a0a5  ldarg.0
0x1a0a6  ldstr    aFontsize_0// "FontSize"
0x1a0ab  ldarg.1
0x1a0ac  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a0b1  stfld    string System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::fontSize
0x1a0b6  ldarg.0
0x1a0b7  ldstr    aFontname// "FontName"
0x1a0bc  ldarg.1
0x1a0bd  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a0c2  stfld    string System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::fontName
0x1a0c7  ldarg.0
0x1a0c8  ldstr    aTitletextbackc// "TitleTextBackColor"
0x1a0cd  ldarg.1
0x1a0ce  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a0d3  stfld    string System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::titleTextBackColor
0x1a0d8  ldarg.0
0x1a0d9  ldstr    aTitletextforec// "TitleTextForeColor"
0x1a0de  ldarg.1
0x1a0df  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a0e4  stfld    string System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::titleTextForeColor
0x1a0e9  ldarg.0
0x1a0ea  ldstr    aTitletextfont// "TitleTextFont"
0x1a0ef  ldarg.1
0x1a0f0  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x1a0f5  stfld    int32 System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::titleTextFont
0x1a0fa  ldarg.0
0x1a0fb  ldstr    aNavigationbutt// "NavigationButtonStyleBorderWidth"
0x1a100  ldarg.1
0x1a101  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a106  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a10b  newobj   instance void [System.Web]System.Web.UI.WebControls.Unit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x1a110  stfld    valuetype [System.Web]System.Web.UI.WebControls.Unit System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::NavigationButtonStyleBorderWidth
0x1a115  ldarg.0
0x1a116  ldstr    aNavigationbutt_0// "NavigationButtonStyleFontName"
0x1a11b  ldarg.1
0x1a11c  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a121  stfld    string System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::NavigationButtonStyleFontName
0x1a126  ldarg.0
0x1a127  ldstr    aNavigationbutt_1// "NavigationButtonStyleFontSize"
0x1a12c  ldarg.1
0x1a12d  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a132  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a137  newobj   instance void [System.Web]System.Web.UI.WebControls.FontUnit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x1a13c  stfld    valuetype [System.Web]System.Web.UI.WebControls.FontUnit System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::NavigationButtonStyleFontSize
0x1a141  ldarg.0
0x1a142  ldstr    aNavigationbutt_2// "NavigationButtonStyleBorderStyle"
0x1a147  ldarg.1
0x1a148  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x1a14d  stfld    valuetype [System.Web]System.Web.UI.WebControls.BorderStyle System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::NavigationButtonStyleBorderStyle
0x1a152  ldarg.0
0x1a153  ldstr    aNavigationbutt_3// "NavigationButtonStyleBorderColor"
0x1a158  ldarg.1
0x1a159  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a15e  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x1a163  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::NavigationButtonStyleBorderColor
0x1a168  ldarg.0
0x1a169  ldstr    aNavigationbutt_4// "NavigationButtonStyleForeColor"
0x1a16e  ldarg.1
0x1a16f  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a174  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x1a179  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::NavigationButtonStyleForeColor
0x1a17e  ldarg.0
0x1a17f  ldstr    aNavigationbutt_5// "NavigationButtonStyleBackColor"
0x1a184  ldarg.1
0x1a185  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a18a  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x1a18f  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::NavigationButtonStyleBackColor
0x1a194  ldarg.0
0x1a195  ldstr    aStepstyleborde// "StepStyleBorderWidth"
0x1a19a  ldarg.1
0x1a19b  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a1a0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a1a5  newobj   instance void [System.Web]System.Web.UI.WebControls.Unit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x1a1aa  stfld    valuetype [System.Web]System.Web.UI.WebControls.Unit System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::StepStyleBorderWidth
0x1a1af  ldarg.0
0x1a1b0  ldstr    aStepstyleborde_0// "StepStyleBorderStyle"
0x1a1b5  ldarg.1
0x1a1b6  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x1a1bb  stfld    valuetype [System.Web]System.Web.UI.WebControls.BorderStyle System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::StepStyleBorderStyle
0x1a1c0  ldarg.0
0x1a1c1  ldstr    aStepstyleborde_1// "StepStyleBorderColor"
0x1a1c6  ldarg.1
0x1a1c7  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a1cc  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x1a1d1  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::StepStyleBorderColor
0x1a1d6  ldarg.0
0x1a1d7  ldstr    aStepstyleforec// "StepStyleForeColor"
0x1a1dc  ldarg.1
0x1a1dd  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a1e2  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x1a1e7  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::StepStyleForeColor
0x1a1ec  ldarg.0
0x1a1ed  ldstr    aStepstylebackc// "StepStyleBackColor"
0x1a1f2  ldarg.1
0x1a1f3  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a1f8  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x1a1fd  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::StepStyleBackColor
0x1a202  ldarg.0
0x1a203  ldstr    aStepstylefonts// "StepStyleFontSize"
0x1a208  ldarg.1
0x1a209  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a20e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a213  newobj   instance void [System.Web]System.Web.UI.WebControls.FontUnit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x1a218  stfld    valuetype [System.Web]System.Web.UI.WebControls.FontUnit System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::StepStyleFontSize
0x1a21d  ldarg.0
0x1a21e  ldstr    aSidebarbuttons// "SideBarButtonStyleFontUnderline"
0x1a223  ldarg.1
0x1a224  call     bool class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetBooleanProperty(string, class [System.Data]System.Data.DataRow)
0x1a229  stfld    bool System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::SideBarButtonStyleFontUnderline
0x1a22e  ldarg.0
0x1a22f  ldstr    aSidebarbuttons_0// "SideBarButtonStyleFontName"
0x1a234  ldarg.1
0x1a235  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a23a  stfld    string System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::SideBarButtonStyleFontName
0x1a23f  ldarg.0
0x1a240  ldstr    aSidebarbuttons_1// "SideBarButtonStyleForeColor"
0x1a245  ldarg.1
0x1a246  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a24b  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x1a250  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::SideBarButtonStyleForeColor
0x1a255  ldarg.0
0x1a256  ldstr    aSidebarbuttons_2// "SideBarButtonStyleBorderWidth"
0x1a25b  ldarg.1
0x1a25c  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a261  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a266  newobj   instance void [System.Web]System.Web.UI.WebControls.Unit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x1a26b  stfld    valuetype [System.Web]System.Web.UI.WebControls.Unit System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::SideBarButtonStyleBorderWidth
0x1a270  ldarg.0
0x1a271  ldstr    aSidebarbuttons_3// "SideBarButtonStyleBackColor"
0x1a276  ldarg.1
0x1a277  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a27c  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x1a281  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::SideBarButtonStyleBackColor
0x1a286  ldarg.0
0x1a287  ldstr    aHeaderstylefor// "HeaderStyleForeColor"
0x1a28c  ldarg.1
0x1a28d  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a292  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x1a297  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::HeaderStyleForeColor
0x1a29c  ldarg.0
0x1a29d  ldstr    aHeaderstylebor// "HeaderStyleBorderColor"
0x1a2a2  ldarg.1
0x1a2a3  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a2a8  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x1a2ad  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::HeaderStyleBorderColor
0x1a2b2  ldarg.0
0x1a2b3  ldstr    aHeaderstylebac// "HeaderStyleBackColor"
0x1a2b8  ldarg.1
0x1a2b9  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a2be  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x1a2c3  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::HeaderStyleBackColor
0x1a2c8  ldarg.0
0x1a2c9  ldstr    aHeaderstylefon// "HeaderStyleFontSize"
0x1a2ce  ldarg.1
0x1a2cf  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a2d4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a2d9  newobj   instance void [System.Web]System.Web.UI.WebControls.FontUnit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x1a2de  stfld    valuetype [System.Web]System.Web.UI.WebControls.FontUnit System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::HeaderStyleFontSize
0x1a2e3  ldarg.0
0x1a2e4  ldstr    aHeaderstylefon_0// "HeaderStyleFontBold"
0x1a2e9  ldarg.1
0x1a2ea  call     bool class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetBooleanProperty(string, class [System.Data]System.Data.DataRow)
0x1a2ef  stfld    bool System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::HeaderStyleFontBold
0x1a2f4  ldarg.0
0x1a2f5  ldstr    aHeaderstylebor_0// "HeaderStyleBorderWidth"
0x1a2fa  ldarg.1
0x1a2fb  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a300  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a305  newobj   instance void [System.Web]System.Web.UI.WebControls.Unit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x1a30a  stfld    valuetype [System.Web]System.Web.UI.WebControls.Unit System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::HeaderStyleBorderWidth
0x1a30f  ldarg.0
0x1a310  ldstr    aHeaderstylehor// "HeaderStyleHorizontalAlign"
0x1a315  ldarg.1
0x1a316  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x1a31b  stfld    valuetype [System.Web]System.Web.UI.WebControls.HorizontalAlign System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::HeaderStyleHorizontalAlign
0x1a320  ldarg.0
0x1a321  ldstr    aHeaderstylebor_1// "HeaderStyleBorderStyle"
0x1a326  ldarg.1
0x1a327  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x1a32c  stfld    valuetype [System.Web]System.Web.UI.WebControls.BorderStyle System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::HeaderStyleBorderStyle
0x1a331  ldarg.0
0x1a332  ldstr    aSidebarstyleba// "SideBarStyleBackColor"
0x1a337  ldarg.1
0x1a338  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a33d  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x1a342  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::SideBarStyleBackColor
0x1a347  ldarg.0
0x1a348  ldstr    aSidebarstyleve// "SideBarStyleVerticalAlign"
0x1a34d  ldarg.1
0x1a34e  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x1a353  stfld    valuetype [System.Web]System.Web.UI.WebControls.VerticalAlign System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::SideBarStyleVerticalAlign
0x1a358  ldarg.0
0x1a359  ldstr    aSidebarstylefo// "SideBarStyleFontSize"
0x1a35e  ldarg.1
0x1a35f  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a364  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a369  newobj   instance void [System.Web]System.Web.UI.WebControls.FontUnit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x1a36e  stfld    valuetype [System.Web]System.Web.UI.WebControls.FontUnit System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::SideBarStyleFontSize
0x1a373  ldarg.0
0x1a374  ldstr    aSidebarstylefo_0// "SideBarStyleFontUnderline"
0x1a379  ldarg.1
0x1a37a  call     bool class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetBooleanProperty(string, class [System.Data]System.Data.DataRow)
0x1a37f  stfld    bool System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::SideBarStyleFontUnderline
0x1a384  ldarg.0
0x1a385  ldstr    aSidebarstylefo_1// "SideBarStyleFontStrikeout"
0x1a38a  ldarg.1
0x1a38b  call     bool class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetBooleanProperty(string, class [System.Data]System.Data.DataRow)
0x1a390  stfld    bool System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::SideBarStyleFontStrikeout
0x1a395  ldarg.0
0x1a396  ldstr    aSidebarstylebo// "SideBarStyleBorderWidth"
0x1a39b  ldarg.1
0x1a39c  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.CreateUserWizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x1a3a1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a3a6  newobj   instance void [System.Web]System.Web.UI.WebControls.Unit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x1a3ab  stfld    valuetype [System.Web]System.Web.UI.WebControls.Unit System.Web.UI.Design.WebControls.CreateUserWizardAutoFormat::SideBarStyleBorderWidth
0x1a3b0  ret
```
