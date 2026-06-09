# System.Web.UI.PageParser::ProcessMainDirectiveAttribute

- ea: `0x783b0`
- end: `0x78ae0`
- name: `System.Web.UI.PageParser::ProcessMainDirectiveAttribute`
- size: `1840`
- prototype: ``
- caller_count: `0`
- callee_count: `31`
- tags: `broker_com_uri`

## callees

- `0x18990`
- `0x24200`
- `0x24240`
- `0x25140`
- `0x25230`
- `0x34f20`
- `0x34fa0`
- `0x589f0`
- `0x58a00`
- `0x58d50`
- `0x58f20`
- `0x5b3f0`
- `0x5b600`
- `0x77f10`
- `0x783b0`
- `0x78c10`
- `0x80730`
- `0x80e90`
- `0x80fe0`
- `0x82800`
- `0x82f60`
- `0x85290`
- `0x85510`
- `0x857f0`
- `0x85840`
- `0x85910`
- `0x85a40`
- `0x85a60`
- `0x86210`
- `0x147a20`
- `0x18f2f0`

## string_xrefs

- `0x78967`: `AspCompat`
- `0x78738`: `readonly`
- `0x785fa`: `aspcompat`
- `0x78760`: `Enablesessionstate_must_be_true_false_or_readonly`

## pseudocode

```c

```

## disassembly

```asm
0x783b0  ldarg.2
0x783b1  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x783b6  stloc.s  5
0x783b8  ldloc.s  5
0x783ba  ldc.i4   0x7ACCC325
0x783bf  bgt.un   loc_7846B
0x783c4  ldloc.s  5
0x783c6  ldc.i4   0x596DCA27
0x783cb  bgt.un.s loc_7841C
0x783cd  ldloc.s  5
0x783cf  ldc.i4   0xCB5E9F5
0x783d4  bgt.un.s loc_783F3
0x783d6  ldloc.s  5
0x783d8  ldc.i4   0x6ADD4B6
0x783dd  beq      loc_78551
0x783e2  ldloc.s  5
0x783e4  ldc.i4   0xCB5E9F5
0x783e9  beq      loc_78623
0x783ee  br       loc_78AC6
0x783f3  ldloc.s  5
0x783f5  ldc.i4   0x20D57AF4
0x783fa  beq      loc_78677
0x783ff  ldloc.s  5
0x78401  ldc.i4   0x509F1712
0x78406  beq      loc_78527
0x7840b  ldloc.s  5
0x7840d  ldc.i4   0x596DCA27
0x78412  beq      loc_78566
0x78417  br       loc_78AC6
0x7841c  ldloc.s  5
0x7841e  ldc.i4   0x63D1AEB2
0x78423  bgt.un.s loc_78442
0x78425  ldloc.s  5
0x78427  ldc.i4   0x623ABE31
0x7842c  beq      loc_785F9
0x78431  ldloc.s  5
0x78433  ldc.i4   0x63D1AEB2
0x78438  beq      loc_78512
0x7843d  br       loc_78AC6
0x78442  ldloc.s  5
0x78444  ldc.i4   0x6B5D964F
0x78449  beq      loc_785BA
0x7844e  ldloc.s  5
0x78450  ldc.i4   0x75095723
0x78455  beq      loc_785E4
0x7845a  ldloc.s  5
0x7845c  ldc.i4   0x7ACCC325
0x78461  beq      loc_78590
0x78466  br       loc_78AC6
0x7846b  ldloc.s  5
0x7846d  ldc.i4   0xBB84B518
0x78472  bgt.un.s loc_784C3
0x78474  ldloc.s  5
0x78476  ldc.i4   0x995CF3AF
0x7847b  bgt.un.s loc_7849A
0x7847d  ldloc.s  5
0x7847f  ldc.i4   0x813D75AE
0x78484  beq      loc_78638
0x78489  ldloc.s  5
0x7848b  ldc.i4   0x995CF3AF
0x78490  beq      loc_785CF
0x78495  br       loc_78AC6
0x7849a  ldloc.s  5
0x7849c  ldc.i4   0xA1F7CA0F
0x784a1  beq      loc_7860E
0x784a6  ldloc.s  5
0x784a8  ldc.i4   0xA8F277F2
0x784ad  beq      loc_7853C
0x784b2  ldloc.s  5
0x784b4  ldc.i4   0xBB84B518
0x784b9  beq      loc_7864D
0x784be  br       loc_78AC6
0x784c3  ldloc.s  5
0x784c5  ldc.i4   0xC4EDA0D1
0x784ca  bgt.un.s loc_784E9
0x784cc  ldloc.s  5
0x784ce  ldc.i4   0xBCDA609E
0x784d3  beq      loc_786A1
0x784d8  ldloc.s  5
0x784da  ldc.i4   0xC4EDA0D1
0x784df  beq      loc_7857B
0x784e4  br       loc_78AC6
0x784e9  ldloc.s  5
0x784eb  ldc.i4   0xCF5F6E2A
0x784f0  beq      loc_78662
0x784f5  ldloc.s  5
0x784f7  ldc.i4   0xD790F80F
0x784fc  beq      loc_7868C
0x78501  ldloc.s  5
0x78503  ldc.i4   0xF8D542B3
0x78508  beq      loc_785A5
0x7850d  br       loc_78AC6
0x78512  ldarg.2
0x78513  ldstr    aErrorpage// "errorpage"
0x78518  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7851d  brtrue   loc_786B6
0x78522  br       loc_78AC6
0x78527  ldarg.2
0x78528  ldstr    aContenttype// "contenttype"
0x7852d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78532  brtrue   loc_786C5
0x78537  br       loc_78AC6
0x7853c  ldarg.2
0x7853d  ldstr    aTheme_0// "theme"
0x78542  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78547  brtrue   loc_786CF
0x7854c  br       loc_78AC6
0x78551  ldarg.2
0x78552  ldstr    aStylesheetthem// "stylesheettheme"
0x78557  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7855c  brtrue   loc_786E2
0x78561  br       loc_78AC6
0x78566  ldarg.2
0x78567  ldstr    aEnablesessions// "enablesessionstate"
0x7856c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78571  brtrue   loc_786FA
0x78576  br       loc_78AC6
0x7857b  ldarg.2
0x7857c  ldstr    aCulture// "culture"
0x78581  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78586  brtrue   loc_78790
0x7858b  br       loc_78AC6
0x78590  ldarg.2
0x78591  ldstr    aLcid// "lcid"
0x78596  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7859b  brtrue   loc_7885D
0x785a0  br       loc_78AC6
0x785a5  ldarg.2
0x785a6  ldstr    aUiculture// "uiculture"
0x785ab  call     bool [mscorlib]System.String::op_Equality(string, string)
0x785b0  brtrue   loc_788B9
0x785b5  br       loc_78AC6
0x785ba  ldarg.2
0x785bb  ldstr    aResponseencodi// "responseencoding"
0x785c0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x785c5  brtrue   loc_788C3
0x785ca  br       loc_78AC6
0x785cf  ldarg.2
0x785d0  ldstr    aCodepage// "codepage"
0x785d5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x785da  brtrue   loc_788E9
0x785df  br       loc_78AC6
0x785e4  ldarg.2
0x785e5  ldstr    aTransaction// "transaction"
0x785ea  call     bool [mscorlib]System.String::op_Equality(string, string)
0x785ef  brtrue   loc_7890F
0x785f4  br       loc_78AC6
0x785f9  ldarg.2
0x785fa  ldstr    aAspcompat_0// "aspcompat"
0x785ff  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78604  brtrue   loc_78923
0x78609  br       loc_78AC6
0x7860e  ldarg.2
0x7860f  ldstr    aAsync// "async"
0x78614  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78619  brtrue   loc_78978
0x7861e  br       loc_78AC6
0x78623  ldarg.2
0x78624  ldstr    aTracemode// "tracemode"
0x78629  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7862e  brtrue   loc_789C3
0x78633  br       loc_78AC6
0x78638  ldarg.2
0x78639  ldstr    aTrace_0// "trace"
0x7863e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78643  brtrue   loc_789E6
0x78648  br       loc_78AC6
0x7864d  ldarg.2
0x7864e  ldstr    aSmartnavigatio// "smartnavigation"
0x78653  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78658  brtrue   loc_78A09
0x7865d  br       loc_78AC6
0x78662  ldarg.2
0x78663  ldstr    aMaintainscroll_0// "maintainscrollpositiononpostback"
0x78668  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7866d  brtrue   loc_78A1F
0x78672  br       loc_78AC6
0x78677  ldarg.2
0x78678  ldstr    aValidatereques_0// "validaterequest"
0x7867d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78682  brtrue   loc_78A2E
0x78687  br       loc_78AC6
0x7868c  ldarg.2
0x7868d  ldstr    aClienttarget// "clienttarget"
0x78692  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78697  brtrue   loc_78A4A
0x7869c  br       loc_78AC6
0x786a1  ldarg.2
0x786a2  ldstr    aMasterpagefile// "masterpagefile"
0x786a7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x786ac  brtrue   loc_78A64
0x786b1  br       loc_78AC6
0x786b6  ldarg.0
0x786b7  ldarg.2
0x786b8  ldarg.3
0x786b9  call     string System.Web.UI.Util::GetNonEmptyAttribute(string name, string value)
0x786be  stfld    string System.Web.UI.PageParser::_errorPage
0x786c3  ldc.i4.0
0x786c4  ret
0x786c5  ldarg.2
0x786c6  ldarg.3
0x786c7  call     string System.Web.UI.Util::GetNonEmptyAttribute(string name, string value)
0x786cc  pop
0x786cd  ldc.i4.0
0x786ce  ret
0x786cf  ldarg.0
0x786d0  ldarg.3
0x786d1  call     instance bool System.Web.UI.TemplateParser::IsExpressionBuilderValue(string val)
0x786d6  brfalse.s loc_786DA
0x786d8  ldc.i4.0
0x786d9  ret
0x786da  ldarg.3
0x786db  call     void System.Web.UI.Util::CheckThemeAttribute(string themeName)
0x786e0  ldc.i4.0
0x786e1  ret
0x786e2  ldarg.0
0x786e3  ldarg.1
0x786e4  ldarg.2
0x786e5  ldarg.3
0x786e6  call     instance void System.Web.UI.TemplateParser::ValidateBuiltInAttribute(string deviceName, string name, string value)
0x786eb  ldarg.3
0x786ec  call     void System.Web.UI.Util::CheckThemeAttribute(string themeName)
0x786f1  ldarg.0
0x786f2  ldarg.3
0x786f3  stfld    string System.Web.UI.PageParser::_styleSheetTheme
0x786f8  ldc.i4.1
0x786f9  ret
0x786fa  ldarg.0
0x786fb  ldflda   valuetype System.Web.Util.SimpleBitVector32 System.Web.UI.TemplateParser::flags
0x78700  ldc.i4   (loc_FFFFD+3)
0x78705  ldc.i4.1
0x78706  call     instance void System.Web.Util.SimpleBitVector32::set_Item(int32 bit, bool value)
0x7870b  ldarg.0
0x7870c  ldflda   valuetype System.Web.Util.SimpleBitVector32 System.Web.UI.TemplateParser::flags
0x78711  ldc.i4   0x200000
0x78716  ldc.i4.0
0x78717  call     instance void System.Web.Util.SimpleBitVector32::set_Item(int32 bit, bool value)
0x7871c  ldarg.3
0x7871d  call     bool System.Web.UI.Util::IsFalseString(string s)
0x78722  brfalse.s loc_78737
0x78724  ldarg.0
0x78725  ldflda   valuetype System.Web.Util.SimpleBitVector32 System.Web.UI.TemplateParser::flags
0x7872a  ldc.i4   (loc_FFFFD+3)
0x7872f  ldc.i4.0
0x78730  call     instance void System.Web.Util.SimpleBitVector32::set_Item(int32 bit, bool value)
0x78735  br.s     loc_7876F
0x78737  ldarg.3
0x78738  ldstr    aReadonly// "readonly"
0x7873d  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x78742  brfalse.s loc_78757
0x78744  ldarg.0
0x78745  ldflda   valuetype System.Web.Util.SimpleBitVector32 System.Web.UI.TemplateParser::flags
0x7874a  ldc.i4   0x200000
0x7874f  ldc.i4.1
0x78750  call     instance void System.Web.Util.SimpleBitVector32::set_Item(int32 bit, bool value)
0x78755  br.s     loc_7876F
0x78757  ldarg.3
0x78758  call     bool System.Web.UI.Util::IsTrueString(string s)
0x7875d  brtrue.s loc_7876F
0x7875f  ldarg.0
0x78760  ldstr    aEnablesessions_0// "Enablesessionstate_must_be_true_false_o"...
0x78765  call     string System.Web.SR::GetString(string name)
0x7876a  call     instance void System.Web.UI.TemplateParser::ProcessError(string message)
0x7876f  ldarg.0
0x78770  ldflda   valuetype System.Web.Util.SimpleBitVector32 System.Web.UI.TemplateParser::flags
0x78775  ldc.i4   (loc_FFFFD+3)
0x7877a  call     instance bool System.Web.Util.SimpleBitVector32::get_Item(int32 bit)
0x7877f  brfalse  loc_78AD2
0x78784  ldarg.0
0x78785  ldarg.2
0x78786  call     instance void System.Web.UI.TemplateParser::OnFoundAttributeRequiringCompilation(string attribName)
0x7878b  br       loc_78AD2
0x78790  ldarg.0
0x78791  ldarg.2
0x78792  ldarg.3
0x78793  call     string System.Web.UI.Util::GetNonEmptyAttribute(string name, string value)
0x78798  stfld    string System.Web.UI.PageParser::_culture
0x7879d  ldc.i4   0x190
0x787a2  call     bool System.Web.HttpRuntime::HasAspNetHostingPermission(valuetype [System]System.Web.AspNetHostingPermissionLevel level)
0x787a7  brtrue.s loc_787C7
0x787a9  ldstr    aInsufficientTr// "Insufficient_trust_for_attribute"
0x787ae  ldc.i4.1
0x787af  newarr   [mscorlib]System.Object
0x787b4  dup
0x787b5  ldc.i4.0
0x787b6  ldstr    aCulture// "culture"
0x787bb  stelem.ref
0x787bc  call     string System.Web.SR::GetString(string name, object[] args)
0x787c1  newobj   instance void System.Web.HttpException::.ctor(string message)
0x787c6  throw
0x787c7  ldarg.3
0x787c8  ldsfld   string System.Web.HttpApplication::AutoCulture
0x787cd  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x787d2  brfalse.s loc_787D6
0x787d4  ldc.i4.0
0x787d5  ret
0x787d6  nop
0x787d7  ldarg.3
0x787d8  ldsfld   string System.Web.HttpApplication::AutoCulture
0x787dd  call     bool System.Web.Util.StringUtil::StringStartsWithIgnoreCase(string s1, string s2)
  ... truncated ...
```
