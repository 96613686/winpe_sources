# System.Web.DynamicCompileErrorFormatter::get_MiscSectionContent

- ea: `0xb3d0`
- end: `0xbaa0`
- name: `System.Web.DynamicCompileErrorFormatter::get_MiscSectionContent`
- size: `1744`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x45180`

## callees

- `0xa360`
- `0xa470`
- `0xb0d0`
- `0xb3d0`
- `0x18d90`
- `0x18db0`
- `0x18dc0`
- `0x241d0`
- `0x24240`
- `0x26030`
- `0x34f20`
- `0x34fa0`

## string_xrefs

- `0xb4ee`: `TmplCompilerSourceSecTitle`
- `0xb781`: `TmplCompilerSourceSecTitle`
- `0xb3fc`: `TmplCompilerFatalError`
- `0xb5d1`: `TmplCompilerSourceFileTitle`
- `0xb631`: `TmplCompilerSourceFileLine`
- `0xb6ad`: `TmplCompilerWarningBanner`
- `0xb70e`: `TmplCompilerWarningSecTitle`
- `0xb8e8`: `compilerOutputDiv`
- `0xb8f0`: `TmplCompilerCompleteOutput`
- `0xb9b6`: `TmplCompilerGeneratedFile`
- `0xba1c`: `TmplCompilerLineHeader`

## pseudocode

```c

```

## disassembly

```asm
0xb3d0  ldc.i4   0x80
0xb3d5  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0xb3da  stloc.0
0xb3db  ldarg.0
0xb3dc  ldfld    class System.Web.HttpCompileException System.Web.DynamicCompileErrorFormatter::_excep
0xb3e1  callvirt instance class [System]System.CodeDom.Compiler.CompilerResults System.Web.HttpCompileException::get_ResultsWithoutDemand()
0xb3e6  stloc.1
0xb3e7  ldloc.1
0xb3e8  callvirt instance class [System]System.CodeDom.Compiler.CompilerErrorCollection [System]System.CodeDom.Compiler.CompilerResults::get_Errors()
0xb3ed  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xb3f2  brtrue.s loc_B449
0xb3f4  ldloc.1
0xb3f5  callvirt instance int32 [System]System.CodeDom.Compiler.CompilerResults::get_NativeCompilerReturnValue()
0xb3fa  brfalse.s loc_B449
0xb3fc  ldstr    aTmplcompilerfa// "TmplCompilerFatalError"
0xb401  ldc.i4.1
0xb402  newarr   [mscorlib]System.Object
0xb407  dup
0xb408  ldc.i4.0
0xb409  ldloc.1
0xb40a  callvirt instance int32 [System]System.CodeDom.Compiler.CompilerResults::get_NativeCompilerReturnValue()
0xb40f  stloc.3
0xb410  ldloca.s 3
0xb412  ldstr    aG// "G"
0xb417  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb41c  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0xb421  stelem.ref
0xb422  call     string System.Web.SR::GetString(string name, object[] args)
0xb427  stloc.2
0xb428  ldarg.0
0xb429  callvirt instance class [System]System.Collections.Specialized.StringCollection System.Web.ErrorFormatter::get_AdaptiveMiscContent()
0xb42e  ldloc.2
0xb42f  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xb434  pop
0xb435  ldloc.0
0xb436  ldloc.2
0xb437  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb43c  pop
0xb43d  ldloc.0
0xb43e  ldstr    aBrBr_2// "<br><br>\r\n"
0xb443  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb448  pop
0xb449  ldloc.1
0xb44a  callvirt instance class [System]System.CodeDom.Compiler.CompilerErrorCollection [System]System.CodeDom.Compiler.CompilerResults::get_Errors()
0xb44f  callvirt instance bool [System]System.CodeDom.Compiler.CompilerErrorCollection::get_HasErrors()
0xb454  brfalse  loc_B690
0xb459  ldarg.0
0xb45a  ldfld    class System.Web.HttpCompileException System.Web.DynamicCompileErrorFormatter::_excep
0xb45f  callvirt instance class [System]System.CodeDom.Compiler.CompilerError System.Web.HttpCompileException::get_FirstCompileError()
0xb464  stloc.s  4
0xb466  ldloc.s  4
0xb468  brfalse  loc_B690
0xb46d  ldloc.s  4
0xb46f  callvirt instance string [System]System.CodeDom.Compiler.CompilerError::get_ErrorNumber()
0xb474  call     string System.Web.HttpUtility::HtmlEncode(string s)
0xb479  stloc.s  5
0xb47b  ldloc.s  5
0xb47d  stloc.s  6
0xb47f  ldloc.0
0xb480  ldloc.s  5
0xb482  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb487  pop
0xb488  ldc.i4   0x190
0xb48d  call     bool System.Web.HttpRuntime::HasAspNetHostingPermission(valuetype [System]System.Web.AspNetHostingPermissionLevel level)
0xb492  brfalse.s loc_B4C7
0xb494  ldloc.s  4
0xb496  callvirt instance string [System]System.CodeDom.Compiler.CompilerError::get_ErrorText()
0xb49b  call     string System.Web.HttpUtility::HtmlEncode(string s)
0xb4a0  stloc.s  5
0xb4a2  ldloc.0
0xb4a3  ldstr    asc_1B2CCE// ": "
0xb4a8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb4ad  pop
0xb4ae  ldloc.0
0xb4af  ldloc.s  5
0xb4b1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb4b6  pop
0xb4b7  ldloc.s  6
0xb4b9  ldstr    asc_1B2CCE// ": "
0xb4be  ldloc.s  5
0xb4c0  call     string [mscorlib]System.String::Concat(string, string, string)
0xb4c5  stloc.s  6
0xb4c7  ldarg.0
0xb4c8  callvirt instance class [System]System.Collections.Specialized.StringCollection System.Web.ErrorFormatter::get_AdaptiveMiscContent()
0xb4cd  ldloc.s  6
0xb4cf  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xb4d4  pop
0xb4d5  ldloc.0
0xb4d6  ldstr    aBrBr_2// "<br><br>\r\n"
0xb4db  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb4e0  pop
0xb4e1  ldloc.0
0xb4e2  ldstr    aB_6// "<b>"
0xb4e7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb4ec  pop
0xb4ed  ldloc.0
0xb4ee  ldstr    aTmplcompilerso// "TmplCompilerSourceSecTitle"
0xb4f3  call     string System.Web.SR::GetString(string name)
0xb4f8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb4fd  pop
0xb4fe  ldloc.0
0xb4ff  ldstr    aBBrBr// ":</b><br><br>\r\n"
0xb504  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb509  pop
0xb50a  ldloc.0
0xb50b  ldstr    aTableWidth100B_1// "            <table width=100% bgcolor="...
0xb510  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb515  pop
0xb516  ldloc.0
0xb517  ldstr    aTrTd// "               <tr><td>\r\n"
0xb51c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb521  pop
0xb522  ldloc.0
0xb523  ldstr    asc_1B3576// "               "
0xb528  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb52d  pop
0xb52e  ldloc.0
0xb52f  ldstr    aTdTr// "               </td></tr>\r\n"
0xb534  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb539  pop
0xb53a  ldloc.0
0xb53b  ldstr    aTr// "               <tr>\r\n"
0xb540  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb545  pop
0xb546  ldloc.0
0xb547  ldstr    aTd// "                  <td>\r\n"
0xb54c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb551  pop
0xb552  ldloc.0
0xb553  ldstr    aCodePre// "                      <code><pre>\r\n\r"...
0xb558  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb55d  pop
0xb55e  ldloc.0
0xb55f  ldloc.s  4
0xb561  callvirt instance string [System]System.CodeDom.Compiler.CompilerError::get_FileName()
0xb566  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Default()
0xb56b  ldarg.0
0xb56c  ldfld    class System.Web.HttpCompileException System.Web.DynamicCompileErrorFormatter::_excep
0xb571  callvirt instance string System.Web.HttpCompileException::get_SourceCodeWithoutDemand()
0xb576  ldloc.s  4
0xb578  callvirt instance int32 [System]System.CodeDom.Compiler.CompilerError::get_Line()
0xb57d  call     string System.Web.FormatterWithFileInfo::GetSourceFileLines(string fileName, class [mscorlib]System.Text.Encoding encoding, string sourceCode, int32 lineNumber)
0xb582  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb587  pop
0xb588  ldloc.0
0xb589  ldstr    aPreCode// "</pre></code>\r\n\r\n"
0xb58e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb593  pop
0xb594  ldloc.0
0xb595  ldstr    aTd_0// "                  </td>\r\n"
0xb59a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb59f  pop
0xb5a0  ldloc.0
0xb5a1  ldstr    aTr_0// "               </tr>\r\n"
0xb5a6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb5ab  pop
0xb5ac  ldloc.0
0xb5ad  ldstr    aTable// "            </table>\r\n\r\n"
0xb5b2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb5b7  pop
0xb5b8  ldloc.0
0xb5b9  ldstr    aBr_2// "            <br>\r\n\r\n"
0xb5be  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb5c3  pop
0xb5c4  ldloc.0
0xb5c5  ldstr    aB_1// "            <b>"
0xb5ca  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb5cf  pop
0xb5d0  ldloc.0
0xb5d1  ldstr    aTmplcompilerso_0// "TmplCompilerSourceFileTitle"
0xb5d6  call     string System.Web.SR::GetString(string name)
0xb5db  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb5e0  pop
0xb5e1  ldloc.0
0xb5e2  ldstr    aB_4// ":</b> "
0xb5e7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb5ec  pop
0xb5ed  ldarg.0
0xb5ee  ldloc.s  4
0xb5f0  callvirt instance string [System]System.CodeDom.Compiler.CompilerError::get_FileName()
0xb5f5  call     string System.Web.ErrorFormatter::GetSafePath(string linePragma)
0xb5fa  stfld    string System.Web.DynamicCompileErrorFormatter::_sourceFilePath
0xb5ff  ldloc.0
0xb600  ldarg.0
0xb601  ldfld    string System.Web.DynamicCompileErrorFormatter::_sourceFilePath
0xb606  call     string System.Web.HttpUtility::HtmlEncode(string s)
0xb60b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb610  pop
0xb611  ldloc.0
0xb612  ldstr    asc_1B2016// "\r\n"
0xb617  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb61c  pop
0xb61d  newobj   instance void [System]System.ComponentModel.Int32Converter::.ctor()
0xb622  stloc.s  7
0xb624  ldloc.0
0xb625  ldstr    aNbspNbspB// "            &nbsp;&nbsp; <b>"
0xb62a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb62f  pop
0xb630  ldloc.0
0xb631  ldstr    aTmplcompilerso_1// "TmplCompilerSourceFileLine"
0xb636  call     string System.Web.SR::GetString(string name)
0xb63b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb640  pop
0xb641  ldloc.0
0xb642  ldstr    aB_7// ":</b>  "
0xb647  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb64c  pop
0xb64d  ldarg.0
0xb64e  ldloc.s  4
0xb650  callvirt instance int32 [System]System.CodeDom.Compiler.CompilerError::get_Line()
0xb655  stfld    int32 System.Web.DynamicCompileErrorFormatter::_sourceFileLineNumber
0xb65a  ldloc.0
0xb65b  ldloc.s  7
0xb65d  ldarg.0
0xb65e  ldfld    int32 System.Web.DynamicCompileErrorFormatter::_sourceFileLineNumber
0xb663  box      [mscorlib]System.Int32
0xb668  callvirt instance string [System]System.ComponentModel.TypeConverter::ConvertToString(object)
0xb66d  call     string System.Web.HttpUtility::HtmlEncode(string s)
0xb672  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb677  pop
0xb678  ldloc.0
0xb679  ldstr    asc_1B2016// "\r\n"
0xb67e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb683  pop
0xb684  ldloc.0
0xb685  ldstr    aBrBr_3// "            <br><br>\r\n"
0xb68a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb68f  pop
0xb690  ldloc.1
0xb691  callvirt instance class [System]System.CodeDom.Compiler.CompilerErrorCollection [System]System.CodeDom.Compiler.CompilerResults::get_Errors()
0xb696  callvirt instance bool [System]System.CodeDom.Compiler.CompilerErrorCollection::get_HasWarnings()
0xb69b  brfalse  loc_B8AA
0xb6a0  ldloc.0
0xb6a1  ldstr    aBrDivClassExpa_0// "<br><div class=\"expandable\" onclick="...
0xb6a6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb6ab  pop
0xb6ac  ldloc.0
0xb6ad  ldstr    aTmplcompilerwa// "TmplCompilerWarningBanner"
0xb6b2  call     string System.Web.SR::GetString(string name)
0xb6b7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb6bc  pop
0xb6bd  ldloc.0
0xb6be  ldstr    aDiv_1// ":</div>\r\n"
0xb6c3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb6c8  pop
0xb6c9  ldloc.0
0xb6ca  ldstr    aDivIdWarningdi// "<div id=\"warningDiv\" style=\"display:"...
0xb6cf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb6d4  pop
0xb6d5  ldloc.1
0xb6d6  callvirt instance class [System]System.CodeDom.Compiler.CompilerErrorCollection [System]System.CodeDom.Compiler.CompilerResults::get_Errors()
0xb6db  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xb6e0  stloc.s  8
0xb6e2  br       loc_B87B
0xb6e7  ldloc.s  8
0xb6e9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xb6ee  castclass [System]System.CodeDom.Compiler.CompilerError
0xb6f3  stloc.s  9
0xb6f5  ldloc.s  9
0xb6f7  callvirt instance bool [System]System.CodeDom.Compiler.CompilerError::get_IsWarning()
0xb6fc  brfalse  loc_B87B
0xb701  ldloc.0
0xb702  ldstr    aB_6// "<b>"
0xb707  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb70c  pop
0xb70d  ldloc.0
0xb70e  ldstr    aTmplcompilerwa_0// "TmplCompilerWarningSecTitle"
0xb713  call     string System.Web.SR::GetString(string name)
0xb718  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb71d  pop
0xb71e  ldloc.0
0xb71f  ldstr    aB_4// ":</b> "
0xb724  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb729  pop
0xb72a  ldloc.0
0xb72b  ldloc.s  9
0xb72d  callvirt instance string [System]System.CodeDom.Compiler.CompilerError::get_ErrorNumber()
0xb732  call     string System.Web.HttpUtility::HtmlEncode(string s)
0xb737  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb73c  pop
0xb73d  ldc.i4   0x190
0xb742  call     bool System.Web.HttpRuntime::HasAspNetHostingPermission(valuetype [System]System.Web.AspNetHostingPermissionLevel level)
0xb747  brfalse.s loc_B768
0xb749  ldloc.0
0xb74a  ldstr    asc_1B2CCE// ": "
0xb74f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb754  pop
0xb755  ldloc.0
0xb756  ldloc.s  9
0xb758  callvirt instance string [System]System.CodeDom.Compiler.CompilerError::get_ErrorText()
0xb75d  call     string System.Web.HttpUtility::HtmlEncode(string s)
0xb762  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb767  pop
0xb768  ldloc.0
0xb769  ldstr    aBr_3// "<br>\r\n"
0xb76e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb773  pop
0xb774  ldloc.0
0xb775  ldstr    aB_6// "<b>"
0xb77a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
  ... truncated ...
```
