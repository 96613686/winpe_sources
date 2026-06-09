# System.Web.DataAccess.DataConnectionErrorFormatter::get_MiscSectionContent

- ea: `0x4bf80`
- end: `0x4c1c5`
- name: `System.Web.DataAccess.DataConnectionErrorFormatter::get_MiscSectionContent`
- size: `581`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x49c70`
- `0x4bf80`
- `0x4c200`
- `0x4c220`

## string_xrefs

- `0x4bf85`: `DataAccessError_MiscSection_1`
- `0x4bfc4`: `DataAccessError_MiscSection_2_CanNotCreateDataDir`
- `0x4bfe4`: `DataAccessError_MiscSection_2`
- `0x4c006`: `DataAccessError_MiscSection_2`
- `0x4c028`: `DataAccessError_MiscSection_2_CanNotWriteToDBFile_a`
- `0x4c048`: `DataAccessError_MiscSection_2_CanNotWriteToDBFile_b`
- `0x4c068`: `DataAccessError_MiscSection_3`
- `0x4c08f`: `properties_security_tab.gif`
- `0x4c0b0`: `DataAccessError_MiscSection_ClickAdd`
- `0x4c105`: `DataAccessError_MiscSection_4`
- `0x4c11c`: `DataAccessError_MiscSection_4_2`
- `0x4c13e`: `DataAccessError_MiscSection_ClickOK`
- `0x4c1a6`: `DataAccessError_MiscSection_ClickOK`
- `0x4c15e`: `DataAccessError_MiscSection_5`
- `0x4c185`: `properties_security_tab_w_user.gif`

## pseudocode

```c

```

## disassembly

```asm
0x4bf80  ldc.i4.1
0x4bf81  stloc.1
0x4bf82  ldarg.0
0x4bf83  ldloca.s 1
0x4bf85  ldstr    aDataaccesserro_0// "DataAccessError_MiscSection_1"
0x4bf8a  call     instance string System.Web.DataAccess.DataConnectionErrorFormatter::GetResourceStringAndSetAdaptiveNumberedText(int32& currentNumber, string resourceId)
0x4bf8f  stloc.2
0x4bf90  ldstr    aOlLi// "<ol>\n<li>"
0x4bf95  ldloc.2
0x4bf96  ldstr    aLi// "</li>\n"
0x4bf9b  call     string [mscorlib]System.String::Concat(string, string, string)
0x4bfa0  stloc.3
0x4bfa1  ldarg.0
0x4bfa2  ldfld    valuetype System.Web.DataAccess.DataConnectionErrorEnum System.Web.DataAccess.DataConnectionErrorFormatter::_Error
0x4bfa7  stloc.s  5
0x4bfa9  ldloc.s  5
0x4bfab  switch   loc_4BFC1, loc_4C003, loc_4C025
0x4bfbc  br       loc_4C065
0x4bfc1  ldarg.0
0x4bfc2  ldloca.s 1
0x4bfc4  ldstr    aDataaccesserro_1// "DataAccessError_MiscSection_2_CanNotCre"...
0x4bfc9  call     instance string System.Web.DataAccess.DataConnectionErrorFormatter::GetResourceStringAndSetAdaptiveNumberedText(int32& currentNumber, string resourceId)
0x4bfce  stloc.2
0x4bfcf  ldloc.3
0x4bfd0  ldstr    aLi_0// "<li>"
0x4bfd5  ldloc.2
0x4bfd6  ldstr    aLi// "</li>\n"
0x4bfdb  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4bfe0  stloc.3
0x4bfe1  ldarg.0
0x4bfe2  ldloca.s 1
0x4bfe4  ldstr    aDataaccesserro_2// "DataAccessError_MiscSection_2"
0x4bfe9  call     instance string System.Web.DataAccess.DataConnectionErrorFormatter::GetResourceStringAndSetAdaptiveNumberedText(int32& currentNumber, string resourceId)
0x4bfee  stloc.2
0x4bfef  ldloc.3
0x4bff0  ldstr    aLi_0// "<li>"
0x4bff5  ldloc.2
0x4bff6  ldstr    aLi// "</li>\n"
0x4bffb  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4c000  stloc.3
0x4c001  br.s     loc_4C065
0x4c003  ldarg.0
0x4c004  ldloca.s 1
0x4c006  ldstr    aDataaccesserro_2// "DataAccessError_MiscSection_2"
0x4c00b  call     instance string System.Web.DataAccess.DataConnectionErrorFormatter::GetResourceStringAndSetAdaptiveNumberedText(int32& currentNumber, string resourceId)
0x4c010  stloc.2
0x4c011  ldloc.3
0x4c012  ldstr    aLi_0// "<li>"
0x4c017  ldloc.2
0x4c018  ldstr    aLi// "</li>\n"
0x4c01d  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4c022  stloc.3
0x4c023  br.s     loc_4C065
0x4c025  ldarg.0
0x4c026  ldloca.s 1
0x4c028  ldstr    aDataaccesserro_3// "DataAccessError_MiscSection_2_CanNotWri"...
0x4c02d  call     instance string System.Web.DataAccess.DataConnectionErrorFormatter::GetResourceStringAndSetAdaptiveNumberedText(int32& currentNumber, string resourceId)
0x4c032  stloc.2
0x4c033  ldloc.3
0x4c034  ldstr    aLi_0// "<li>"
0x4c039  ldloc.2
0x4c03a  ldstr    aLi// "</li>\n"
0x4c03f  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4c044  stloc.3
0x4c045  ldarg.0
0x4c046  ldloca.s 1
0x4c048  ldstr    aDataaccesserro_4// "DataAccessError_MiscSection_2_CanNotWri"...
0x4c04d  call     instance string System.Web.DataAccess.DataConnectionErrorFormatter::GetResourceStringAndSetAdaptiveNumberedText(int32& currentNumber, string resourceId)
0x4c052  stloc.2
0x4c053  ldloc.3
0x4c054  ldstr    aLi_0// "<li>"
0x4c059  ldloc.2
0x4c05a  ldstr    aLi// "</li>\n"
0x4c05f  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4c064  stloc.3
0x4c065  ldarg.0
0x4c066  ldloca.s 1
0x4c068  ldstr    aDataaccesserro_5// "DataAccessError_MiscSection_3"
0x4c06d  call     instance string System.Web.DataAccess.DataConnectionErrorFormatter::GetResourceStringAndSetAdaptiveNumberedText(int32& currentNumber, string resourceId)
0x4c072  stloc.2
0x4c073  ldloc.3
0x4c074  ldstr    aLi_0// "<li>"
0x4c079  ldloc.2
0x4c07a  ldstr    aBrLi// "<br></li>\n"
0x4c07f  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4c084  stloc.3
0x4c085  ldtoken  System.Web.UI.Page
0x4c08a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4c08f  ldstr    aPropertiesSecu// "properties_security_tab.gif"
0x4c094  ldc.i4.1
0x4c095  call     string System.Web.Handlers.AssemblyResourceLoader::GetWebResourceUrl(class [mscorlib]System.Type type, string resourceName, bool htmlEncoded)
0x4c09a  stloc.0
0x4c09b  ldloc.3
0x4c09c  ldstr    aBrBrImgSrc// "<br><br><IMG SRC=\""
0x4c0a1  ldloc.0
0x4c0a2  ldstr    aBrBrBr// "\"><br><br><br>"
0x4c0a7  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4c0ac  stloc.3
0x4c0ad  ldarg.0
0x4c0ae  ldloca.s 1
0x4c0b0  ldstr    aDataaccesserro_6// "DataAccessError_MiscSection_ClickAdd"
0x4c0b5  call     instance string System.Web.DataAccess.DataConnectionErrorFormatter::GetResourceStringAndSetAdaptiveNumberedText(int32& currentNumber, string resourceId)
0x4c0ba  stloc.2
0x4c0bb  ldloc.3
0x4c0bc  ldstr    aLi_0// "<li>"
0x4c0c1  ldloc.2
0x4c0c2  ldstr    aLi// "</li>\n"
0x4c0c7  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4c0cc  stloc.3
0x4c0cd  ldtoken  System.Web.UI.Page
0x4c0d2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4c0d7  ldstr    aAddPermissions// "add_permissions_for_users.gif"
0x4c0dc  ldc.i4.1
0x4c0dd  call     string System.Web.Handlers.AssemblyResourceLoader::GetWebResourceUrl(class [mscorlib]System.Type type, string resourceName, bool htmlEncoded)
0x4c0e2  stloc.0
0x4c0e3  ldloc.3
0x4c0e4  ldstr    aBrBrImgSrc// "<br><br><IMG SRC=\""
0x4c0e9  ldloc.0
0x4c0ea  ldstr    aBrBr_4// "\"><br><br>"
0x4c0ef  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4c0f4  stloc.3
0x4c0f5  ldarg.0
0x4c0f6  ldfld    string System.Web.DataAccess.DataConnectionErrorFormatter::_UserName
0x4c0fb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4c100  brtrue.s loc_4C119
0x4c102  ldarg.0
0x4c103  ldloca.s 1
0x4c105  ldstr    aDataaccesserro_7// "DataAccessError_MiscSection_4"
0x4c10a  ldarg.0
0x4c10b  ldfld    string System.Web.DataAccess.DataConnectionErrorFormatter::_UserName
0x4c110  call     instance string System.Web.DataAccess.DataConnectionErrorFormatter::GetResourceStringAndSetAdaptiveNumberedText(int32& currentNumber, string resourceId, string parameter1)
0x4c115  stloc.s  4
0x4c117  br.s     loc_4C128
0x4c119  ldarg.0
0x4c11a  ldloca.s 1
0x4c11c  ldstr    aDataaccesserro_8// "DataAccessError_MiscSection_4_2"
0x4c121  call     instance string System.Web.DataAccess.DataConnectionErrorFormatter::GetResourceStringAndSetAdaptiveNumberedText(int32& currentNumber, string resourceId)
0x4c126  stloc.s  4
0x4c128  ldloc.3
0x4c129  ldstr    aLi_0// "<li>"
0x4c12e  ldloc.s  4
0x4c130  ldstr    aLi// "</li>\n"
0x4c135  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4c13a  stloc.3
0x4c13b  ldarg.0
0x4c13c  ldloca.s 1
0x4c13e  ldstr    aDataaccesserro_9// "DataAccessError_MiscSection_ClickOK"
0x4c143  call     instance string System.Web.DataAccess.DataConnectionErrorFormatter::GetResourceStringAndSetAdaptiveNumberedText(int32& currentNumber, string resourceId)
0x4c148  stloc.2
0x4c149  ldloc.3
0x4c14a  ldstr    aLi_0// "<li>"
0x4c14f  ldloc.2
0x4c150  ldstr    aLi// "</li>\n"
0x4c155  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4c15a  stloc.3
0x4c15b  ldarg.0
0x4c15c  ldloca.s 1
0x4c15e  ldstr    aDataaccesserro_10// "DataAccessError_MiscSection_5"
0x4c163  call     instance string System.Web.DataAccess.DataConnectionErrorFormatter::GetResourceStringAndSetAdaptiveNumberedText(int32& currentNumber, string resourceId)
0x4c168  stloc.2
0x4c169  ldloc.3
0x4c16a  ldstr    aLi_0// "<li>"
0x4c16f  ldloc.2
0x4c170  ldstr    aLi// "</li>\n"
0x4c175  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4c17a  stloc.3
0x4c17b  ldtoken  System.Web.UI.Page
0x4c180  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4c185  ldstr    aPropertiesSecu_0// "properties_security_tab_w_user.gif"
0x4c18a  ldc.i4.1
0x4c18b  call     string System.Web.Handlers.AssemblyResourceLoader::GetWebResourceUrl(class [mscorlib]System.Type type, string resourceName, bool htmlEncoded)
0x4c190  stloc.0
0x4c191  ldloc.3
0x4c192  ldstr    aBrBrImgSrc// "<br><br><IMG SRC=\""
0x4c197  ldloc.0
0x4c198  ldstr    aBrBr_4// "\"><br><br>"
0x4c19d  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4c1a2  stloc.3
0x4c1a3  ldarg.0
0x4c1a4  ldloca.s 1
0x4c1a6  ldstr    aDataaccesserro_9// "DataAccessError_MiscSection_ClickOK"
0x4c1ab  call     instance string System.Web.DataAccess.DataConnectionErrorFormatter::GetResourceStringAndSetAdaptiveNumberedText(int32& currentNumber, string resourceId)
0x4c1b0  stloc.2
0x4c1b1  ldloc.3
0x4c1b2  ldstr    aLi_0// "<li>"
0x4c1b7  ldloc.2
0x4c1b8  ldstr    aLi// "</li>\n"
0x4c1bd  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4c1c2  stloc.3
0x4c1c3  ldloc.3
0x4c1c4  ret
```
