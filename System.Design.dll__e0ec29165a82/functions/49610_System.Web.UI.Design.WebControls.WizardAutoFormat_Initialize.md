# System.Web.UI.Design.WebControls.WizardAutoFormat::Initialize

- ea: `0x49610`
- end: `0x49976`
- name: `System.Web.UI.Design.WebControls.WizardAutoFormat::Initialize`
- size: `870`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x49610`

## string_xrefs

- `0x497e3`: `SideBarButtonStyleFontUnderline`
- `0x497f4`: `SideBarButtonStyleFontName`
- `0x49805`: `SideBarButtonStyleForeColor`
- `0x4981b`: `SideBarButtonStyleBorderWidth`
- `0x49836`: `SideBarButtonStyleBackColor`
- `0x49688`: `SideBarStyleBackColor`
- `0x498f7`: `SideBarStyleBackColor`
- `0x4969e`: `SideBarStyleVerticalAlign`
- `0x4990d`: `SideBarStyleVerticalAlign`
- `0x4991e`: `SideBarStyleFontSize`
- `0x49939`: `SideBarStyleFontUnderline`
- `0x4994a`: `SideBarStyleFontStrikeout`
- `0x4995b`: `SideBarStyleBorderWidth`

## pseudocode

```c

```

## disassembly

```asm
0x49610  ldarg.1
0x49611  brtrue.s loc_49614
0x49613  ret
0x49614  ldarg.0
0x49615  ldstr    aFontname// "FontName"
0x4961a  ldarg.1
0x4961b  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49620  stfld    string System.Web.UI.Design.WebControls.WizardAutoFormat::FontName
0x49625  ldarg.0
0x49626  ldstr    aFontsize_0// "FontSize"
0x4962b  ldarg.1
0x4962c  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49631  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x49636  newobj   instance void [System.Web]System.Web.UI.WebControls.FontUnit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x4963b  stfld    valuetype [System.Web]System.Web.UI.WebControls.FontUnit System.Web.UI.Design.WebControls.WizardAutoFormat::FontSize
0x49640  ldarg.0
0x49641  ldstr    aBackcolor// "BackColor"
0x49646  ldarg.1
0x49647  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x4964c  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x49651  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.WizardAutoFormat::BackColor
0x49656  ldarg.0
0x49657  ldstr    aBordercolor// "BorderColor"
0x4965c  ldarg.1
0x4965d  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49662  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x49667  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.WizardAutoFormat::BorderColor
0x4966c  ldarg.0
0x4966d  ldstr    aBorderwidth// "BorderWidth"
0x49672  ldarg.1
0x49673  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49678  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4967d  newobj   instance void [System.Web]System.Web.UI.WebControls.Unit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x49682  stfld    valuetype [System.Web]System.Web.UI.WebControls.Unit System.Web.UI.Design.WebControls.WizardAutoFormat::BorderWidth
0x49687  ldarg.0
0x49688  ldstr    aSidebarstyleba// "SideBarStyleBackColor"
0x4968d  ldarg.1
0x4968e  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49693  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x49698  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.WizardAutoFormat::SideBarStyleBackColor
0x4969d  ldarg.0
0x4969e  ldstr    aSidebarstyleve// "SideBarStyleVerticalAlign"
0x496a3  ldarg.1
0x496a4  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x496a9  stfld    valuetype [System.Web]System.Web.UI.WebControls.VerticalAlign System.Web.UI.Design.WebControls.WizardAutoFormat::SideBarStyleVerticalAlign
0x496ae  ldarg.0
0x496af  ldstr    aBorderstyle// "BorderStyle"
0x496b4  ldarg.1
0x496b5  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x496ba  stfld    valuetype [System.Web]System.Web.UI.WebControls.BorderStyle System.Web.UI.Design.WebControls.WizardAutoFormat::BorderStyle
0x496bf  ldarg.0
0x496c0  ldstr    aNavigationbutt// "NavigationButtonStyleBorderWidth"
0x496c5  ldarg.1
0x496c6  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x496cb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x496d0  newobj   instance void [System.Web]System.Web.UI.WebControls.Unit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x496d5  stfld    valuetype [System.Web]System.Web.UI.WebControls.Unit System.Web.UI.Design.WebControls.WizardAutoFormat::NavigationButtonStyleBorderWidth
0x496da  ldarg.0
0x496db  ldstr    aNavigationbutt_0// "NavigationButtonStyleFontName"
0x496e0  ldarg.1
0x496e1  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x496e6  stfld    string System.Web.UI.Design.WebControls.WizardAutoFormat::NavigationButtonStyleFontName
0x496eb  ldarg.0
0x496ec  ldstr    aNavigationbutt_1// "NavigationButtonStyleFontSize"
0x496f1  ldarg.1
0x496f2  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x496f7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x496fc  newobj   instance void [System.Web]System.Web.UI.WebControls.FontUnit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x49701  stfld    valuetype [System.Web]System.Web.UI.WebControls.FontUnit System.Web.UI.Design.WebControls.WizardAutoFormat::NavigationButtonStyleFontSize
0x49706  ldarg.0
0x49707  ldstr    aNavigationbutt_2// "NavigationButtonStyleBorderStyle"
0x4970c  ldarg.1
0x4970d  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x49712  stfld    valuetype [System.Web]System.Web.UI.WebControls.BorderStyle System.Web.UI.Design.WebControls.WizardAutoFormat::NavigationButtonStyleBorderStyle
0x49717  ldarg.0
0x49718  ldstr    aNavigationbutt_3// "NavigationButtonStyleBorderColor"
0x4971d  ldarg.1
0x4971e  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49723  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x49728  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.WizardAutoFormat::NavigationButtonStyleBorderColor
0x4972d  ldarg.0
0x4972e  ldstr    aNavigationbutt_4// "NavigationButtonStyleForeColor"
0x49733  ldarg.1
0x49734  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49739  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x4973e  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.WizardAutoFormat::NavigationButtonStyleForeColor
0x49743  ldarg.0
0x49744  ldstr    aNavigationbutt_5// "NavigationButtonStyleBackColor"
0x49749  ldarg.1
0x4974a  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x4974f  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x49754  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.WizardAutoFormat::NavigationButtonStyleBackColor
0x49759  ldarg.0
0x4975a  ldstr    aStepstyleborde// "StepStyleBorderWidth"
0x4975f  ldarg.1
0x49760  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49765  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4976a  newobj   instance void [System.Web]System.Web.UI.WebControls.Unit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x4976f  stfld    valuetype [System.Web]System.Web.UI.WebControls.Unit System.Web.UI.Design.WebControls.WizardAutoFormat::StepStyleBorderWidth
0x49774  ldarg.0
0x49775  ldstr    aStepstyleborde_0// "StepStyleBorderStyle"
0x4977a  ldarg.1
0x4977b  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x49780  stfld    valuetype [System.Web]System.Web.UI.WebControls.BorderStyle System.Web.UI.Design.WebControls.WizardAutoFormat::StepStyleBorderStyle
0x49785  ldarg.0
0x49786  ldstr    aStepstyleborde_1// "StepStyleBorderColor"
0x4978b  ldarg.1
0x4978c  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49791  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x49796  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.WizardAutoFormat::StepStyleBorderColor
0x4979b  ldarg.0
0x4979c  ldstr    aStepstyleforec// "StepStyleForeColor"
0x497a1  ldarg.1
0x497a2  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x497a7  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x497ac  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.WizardAutoFormat::StepStyleForeColor
0x497b1  ldarg.0
0x497b2  ldstr    aStepstylebackc// "StepStyleBackColor"
0x497b7  ldarg.1
0x497b8  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x497bd  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x497c2  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.WizardAutoFormat::StepStyleBackColor
0x497c7  ldarg.0
0x497c8  ldstr    aStepstylefonts// "StepStyleFontSize"
0x497cd  ldarg.1
0x497ce  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x497d3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x497d8  newobj   instance void [System.Web]System.Web.UI.WebControls.FontUnit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x497dd  stfld    valuetype [System.Web]System.Web.UI.WebControls.FontUnit System.Web.UI.Design.WebControls.WizardAutoFormat::StepStyleFontSize
0x497e2  ldarg.0
0x497e3  ldstr    aSidebarbuttons// "SideBarButtonStyleFontUnderline"
0x497e8  ldarg.1
0x497e9  call     bool class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetBooleanProperty(string, class [System.Data]System.Data.DataRow)
0x497ee  stfld    bool System.Web.UI.Design.WebControls.WizardAutoFormat::SideBarButtonStyleFontUnderline
0x497f3  ldarg.0
0x497f4  ldstr    aSidebarbuttons_0// "SideBarButtonStyleFontName"
0x497f9  ldarg.1
0x497fa  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x497ff  stfld    string System.Web.UI.Design.WebControls.WizardAutoFormat::SideBarButtonStyleFontName
0x49804  ldarg.0
0x49805  ldstr    aSidebarbuttons_1// "SideBarButtonStyleForeColor"
0x4980a  ldarg.1
0x4980b  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49810  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x49815  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.WizardAutoFormat::SideBarButtonStyleForeColor
0x4981a  ldarg.0
0x4981b  ldstr    aSidebarbuttons_2// "SideBarButtonStyleBorderWidth"
0x49820  ldarg.1
0x49821  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49826  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4982b  newobj   instance void [System.Web]System.Web.UI.WebControls.Unit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x49830  stfld    valuetype [System.Web]System.Web.UI.WebControls.Unit System.Web.UI.Design.WebControls.WizardAutoFormat::SideBarButtonStyleBorderWidth
0x49835  ldarg.0
0x49836  ldstr    aSidebarbuttons_3// "SideBarButtonStyleBackColor"
0x4983b  ldarg.1
0x4983c  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49841  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x49846  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.WizardAutoFormat::SideBarButtonStyleBackColor
0x4984b  ldarg.0
0x4984c  ldstr    aHeaderstylefor// "HeaderStyleForeColor"
0x49851  ldarg.1
0x49852  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49857  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x4985c  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.WizardAutoFormat::HeaderStyleForeColor
0x49861  ldarg.0
0x49862  ldstr    aHeaderstylebor// "HeaderStyleBorderColor"
0x49867  ldarg.1
0x49868  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x4986d  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x49872  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.WizardAutoFormat::HeaderStyleBorderColor
0x49877  ldarg.0
0x49878  ldstr    aHeaderstylebac// "HeaderStyleBackColor"
0x4987d  ldarg.1
0x4987e  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49883  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x49888  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.WizardAutoFormat::HeaderStyleBackColor
0x4988d  ldarg.0
0x4988e  ldstr    aHeaderstylefon// "HeaderStyleFontSize"
0x49893  ldarg.1
0x49894  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49899  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4989e  newobj   instance void [System.Web]System.Web.UI.WebControls.FontUnit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x498a3  stfld    valuetype [System.Web]System.Web.UI.WebControls.FontUnit System.Web.UI.Design.WebControls.WizardAutoFormat::HeaderStyleFontSize
0x498a8  ldarg.0
0x498a9  ldstr    aHeaderstylefon_0// "HeaderStyleFontBold"
0x498ae  ldarg.1
0x498af  call     bool class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetBooleanProperty(string, class [System.Data]System.Data.DataRow)
0x498b4  stfld    bool System.Web.UI.Design.WebControls.WizardAutoFormat::HeaderStyleFontBold
0x498b9  ldarg.0
0x498ba  ldstr    aHeaderstylebor_0// "HeaderStyleBorderWidth"
0x498bf  ldarg.1
0x498c0  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x498c5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x498ca  newobj   instance void [System.Web]System.Web.UI.WebControls.Unit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x498cf  stfld    valuetype [System.Web]System.Web.UI.WebControls.Unit System.Web.UI.Design.WebControls.WizardAutoFormat::HeaderStyleBorderWidth
0x498d4  ldarg.0
0x498d5  ldstr    aHeaderstylehor// "HeaderStyleHorizontalAlign"
0x498da  ldarg.1
0x498db  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x498e0  stfld    valuetype [System.Web]System.Web.UI.WebControls.HorizontalAlign System.Web.UI.Design.WebControls.WizardAutoFormat::HeaderStyleHorizontalAlign
0x498e5  ldarg.0
0x498e6  ldstr    aHeaderstylebor_1// "HeaderStyleBorderStyle"
0x498eb  ldarg.1
0x498ec  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x498f1  stfld    valuetype [System.Web]System.Web.UI.WebControls.BorderStyle System.Web.UI.Design.WebControls.WizardAutoFormat::HeaderStyleBorderStyle
0x498f6  ldarg.0
0x498f7  ldstr    aSidebarstyleba// "SideBarStyleBackColor"
0x498fc  ldarg.1
0x498fd  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49902  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x49907  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.WizardAutoFormat::SideBarStyleBackColor
0x4990c  ldarg.0
0x4990d  ldstr    aSidebarstyleve// "SideBarStyleVerticalAlign"
0x49912  ldarg.1
0x49913  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x49918  stfld    valuetype [System.Web]System.Web.UI.WebControls.VerticalAlign System.Web.UI.Design.WebControls.WizardAutoFormat::SideBarStyleVerticalAlign
0x4991d  ldarg.0
0x4991e  ldstr    aSidebarstylefo// "SideBarStyleFontSize"
0x49923  ldarg.1
0x49924  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49929  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4992e  newobj   instance void [System.Web]System.Web.UI.WebControls.FontUnit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x49933  stfld    valuetype [System.Web]System.Web.UI.WebControls.FontUnit System.Web.UI.Design.WebControls.WizardAutoFormat::SideBarStyleFontSize
0x49938  ldarg.0
0x49939  ldstr    aSidebarstylefo_0// "SideBarStyleFontUnderline"
0x4993e  ldarg.1
0x4993f  call     bool class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetBooleanProperty(string, class [System.Data]System.Data.DataRow)
0x49944  stfld    bool System.Web.UI.Design.WebControls.WizardAutoFormat::SideBarStyleFontUnderline
0x49949  ldarg.0
0x4994a  ldstr    aSidebarstylefo_1// "SideBarStyleFontStrikeout"
0x4994f  ldarg.1
0x49950  call     bool class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetBooleanProperty(string, class [System.Data]System.Data.DataRow)
0x49955  stfld    bool System.Web.UI.Design.WebControls.WizardAutoFormat::SideBarStyleFontStrikeout
0x4995a  ldarg.0
0x4995b  ldstr    aSidebarstylebo// "SideBarStyleBorderWidth"
0x49960  ldarg.1
0x49961  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.Wizard>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x49966  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4996b  newobj   instance void [System.Web]System.Web.UI.WebControls.Unit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x49970  stfld    valuetype [System.Web]System.Web.UI.WebControls.Unit System.Web.UI.Design.WebControls.WizardAutoFormat::SideBarStyleBorderWidth
0x49975  ret
```
