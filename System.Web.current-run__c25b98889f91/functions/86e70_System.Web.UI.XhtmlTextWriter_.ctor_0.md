# System.Web.UI.XhtmlTextWriter::.ctor_0

- ea: `0x86e70`
- end: `0x8750b`
- name: `System.Web.UI.XhtmlTextWriter::.ctor_0`
- size: `1691`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x86e60`

## callees

- `0x6cba0`
- `0x87530`

## string_xrefs

- `0x87031`: `accesskey`
- `0x870b4`: `accesskey`
- `0x8711f`: `accesskey`
- `0x871ab`: `accesskey`
- `0x8730a`: `classid`
- `0x86eeb`: `xml:lang`
- `0x86f09`: `xml:lang`
- `0x86f38`: `xml:lang`
- `0x86f77`: `xml:lang`
- `0x873af`: `xml:lang`
- `0x874c9`: `xml:lang`
- `0x86f48`: `xmlns`
- `0x86ffe`: `xml:space`
- `0x874e9`: `xml:space`

## pseudocode

```c

```

## disassembly

```asm
0x86e70  ldarg.0
0x86e71  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x86e76  stfld    class [mscorlib]System.Collections.Hashtable System.Web.UI.XhtmlTextWriter::_commonAttributes
0x86e7b  ldarg.0
0x86e7c  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_CurrentCultureIgnoreCase()
0x86e81  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0x86e86  stfld    class [mscorlib]System.Collections.Hashtable System.Web.UI.XhtmlTextWriter::_elementSpecificAttributes
0x86e8b  ldarg.0
0x86e8c  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_CurrentCultureIgnoreCase()
0x86e91  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0x86e96  stfld    class [mscorlib]System.Collections.Hashtable System.Web.UI.XhtmlTextWriter::_suppressCommonAttributes
0x86e9b  ldarg.0
0x86e9c  ldarg.1
0x86e9d  ldarg.2
0x86e9e  call     instance void System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter writer, string tabString)
0x86ea3  ldarg.0
0x86ea4  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.UI.XhtmlTextWriter::_commonAttributes
0x86ea9  ldstr    aClass// "class"
0x86eae  ldc.i4.1
0x86eaf  box      [mscorlib]System.Boolean
0x86eb4  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x86eb9  ldarg.0
0x86eba  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.UI.XhtmlTextWriter::_commonAttributes
0x86ebf  ldstr    aId// "id"
0x86ec4  ldc.i4.1
0x86ec5  box      [mscorlib]System.Boolean
0x86eca  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x86ecf  ldarg.0
0x86ed0  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.UI.XhtmlTextWriter::_commonAttributes
0x86ed5  ldstr    aTitle_1// "title"
0x86eda  ldc.i4.1
0x86edb  box      [mscorlib]System.Boolean
0x86ee0  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x86ee5  ldarg.0
0x86ee6  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.UI.XhtmlTextWriter::_commonAttributes
0x86eeb  ldstr    aXmlLang// "xml:lang"
0x86ef0  ldc.i4.1
0x86ef1  box      [mscorlib]System.Boolean
0x86ef6  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x86efb  ldarg.0
0x86efc  ldstr    aHead_4// "head"
0x86f01  ldc.i4.1
0x86f02  newarr   [mscorlib]System.String
0x86f07  dup
0x86f08  ldc.i4.0
0x86f09  ldstr    aXmlLang// "xml:lang"
0x86f0e  stelem.ref
0x86f0f  call     instance void System.Web.UI.XhtmlTextWriter::AddRecognizedAttributes(string elementName, string[] attributes)
0x86f14  ldarg.0
0x86f15  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.UI.XhtmlTextWriter::_suppressCommonAttributes
0x86f1a  ldstr    aHead_4// "head"
0x86f1f  ldc.i4.1
0x86f20  box      [mscorlib]System.Boolean
0x86f25  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x86f2a  ldarg.0
0x86f2b  ldstr    aHtml_2// "html"
0x86f30  ldc.i4.3
0x86f31  newarr   [mscorlib]System.String
0x86f36  dup
0x86f37  ldc.i4.0
0x86f38  ldstr    aXmlLang// "xml:lang"
0x86f3d  stelem.ref
0x86f3e  dup
0x86f3f  ldc.i4.1
0x86f40  ldstr    aVersion// "version"
0x86f45  stelem.ref
0x86f46  dup
0x86f47  ldc.i4.2
0x86f48  ldstr    aXmlns_0// "xmlns"
0x86f4d  stelem.ref
0x86f4e  call     instance void System.Web.UI.XhtmlTextWriter::AddRecognizedAttributes(string elementName, string[] attributes)
0x86f53  ldarg.0
0x86f54  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.UI.XhtmlTextWriter::_suppressCommonAttributes
0x86f59  ldstr    aHtml_2// "html"
0x86f5e  ldc.i4.1
0x86f5f  box      [mscorlib]System.Boolean
0x86f64  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x86f69  ldarg.0
0x86f6a  ldstr    aTitle_1// "title"
0x86f6f  ldc.i4.1
0x86f70  newarr   [mscorlib]System.String
0x86f75  dup
0x86f76  ldc.i4.0
0x86f77  ldstr    aXmlLang// "xml:lang"
0x86f7c  stelem.ref
0x86f7d  call     instance void System.Web.UI.XhtmlTextWriter::AddRecognizedAttributes(string elementName, string[] attributes)
0x86f82  ldarg.0
0x86f83  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.UI.XhtmlTextWriter::_suppressCommonAttributes
0x86f88  ldstr    aTitle_1// "title"
0x86f8d  ldc.i4.1
0x86f8e  box      [mscorlib]System.Boolean
0x86f93  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x86f98  ldarg.0
0x86f99  ldstr    aBlockquote// "blockquote"
0x86f9e  ldc.i4.1
0x86f9f  newarr   [mscorlib]System.String
0x86fa4  dup
0x86fa5  ldc.i4.0
0x86fa6  ldstr    aCite// "cite"
0x86fab  stelem.ref
0x86fac  call     instance void System.Web.UI.XhtmlTextWriter::AddRecognizedAttributes(string elementName, string[] attributes)
0x86fb1  ldarg.0
0x86fb2  ldstr    aBr_5// "br"
0x86fb7  ldc.i4.3
0x86fb8  newarr   [mscorlib]System.String
0x86fbd  dup
0x86fbe  ldc.i4.0
0x86fbf  ldstr    aClass// "class"
0x86fc4  stelem.ref
0x86fc5  dup
0x86fc6  ldc.i4.1
0x86fc7  ldstr    aId// "id"
0x86fcc  stelem.ref
0x86fcd  dup
0x86fce  ldc.i4.2
0x86fcf  ldstr    aTitle_1// "title"
0x86fd4  stelem.ref
0x86fd5  call     instance void System.Web.UI.XhtmlTextWriter::AddRecognizedAttributes(string elementName, string[] attributes)
0x86fda  ldarg.0
0x86fdb  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.UI.XhtmlTextWriter::_suppressCommonAttributes
0x86fe0  ldstr    aBr_5// "br"
0x86fe5  ldc.i4.1
0x86fe6  box      [mscorlib]System.Boolean
0x86feb  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x86ff0  ldarg.0
0x86ff1  ldstr    aPre_1// "pre"
0x86ff6  ldc.i4.1
0x86ff7  newarr   [mscorlib]System.String
0x86ffc  dup
0x86ffd  ldc.i4.0
0x86ffe  ldstr    aXmlSpace// "xml:space"
0x87003  stelem.ref
0x87004  call     instance void System.Web.UI.XhtmlTextWriter::AddRecognizedAttributes(string elementName, string[] attributes)
0x87009  ldarg.0
0x8700a  ldstr    aQ// "q"
0x8700f  ldc.i4.1
0x87010  newarr   [mscorlib]System.String
0x87015  dup
0x87016  ldc.i4.0
0x87017  ldstr    aCite// "cite"
0x8701c  stelem.ref
0x8701d  call     instance void System.Web.UI.XhtmlTextWriter::AddRecognizedAttributes(string elementName, string[] attributes)
0x87022  ldarg.0
0x87023  ldstr    aA_4// "a"
0x87028  ldc.i4.s 9
0x8702a  newarr   [mscorlib]System.String
0x8702f  dup
0x87030  ldc.i4.0
0x87031  ldstr    aAccesskey// "accesskey"
0x87036  stelem.ref
0x87037  dup
0x87038  ldc.i4.1
0x87039  ldstr    aCharset// "charset"
0x8703e  stelem.ref
0x8703f  dup
0x87040  ldc.i4.2
0x87041  ldstr    aHref// "href"
0x87046  stelem.ref
0x87047  dup
0x87048  ldc.i4.3
0x87049  ldstr    aHreflang// "hreflang"
0x8704e  stelem.ref
0x8704f  dup
0x87050  ldc.i4.4
0x87051  ldstr    aRel// "rel"
0x87056  stelem.ref
0x87057  dup
0x87058  ldc.i4.5
0x87059  ldstr    aRev// "rev"
0x8705e  stelem.ref
0x8705f  dup
0x87060  ldc.i4.6
0x87061  ldstr    aTabindex// "tabindex"
0x87066  stelem.ref
0x87067  dup
0x87068  ldc.i4.7
0x87069  ldstr    aType// "type"
0x8706e  stelem.ref
0x8706f  dup
0x87070  ldc.i4.8
0x87071  ldstr    aTitle_1// "title"
0x87076  stelem.ref
0x87077  call     instance void System.Web.UI.XhtmlTextWriter::AddRecognizedAttributes(string elementName, string[] attributes)
0x8707c  ldarg.0
0x8707d  ldstr    aForm// "form"
0x87082  ldc.i4.3
0x87083  newarr   [mscorlib]System.String
0x87088  dup
0x87089  ldc.i4.0
0x8708a  ldstr    aAction// "action"
0x8708f  stelem.ref
0x87090  dup
0x87091  ldc.i4.1
0x87092  ldstr    aMethod// "method"
0x87097  stelem.ref
0x87098  dup
0x87099  ldc.i4.2
0x8709a  ldstr    aEnctype// "enctype"
0x8709f  stelem.ref
0x870a0  call     instance void System.Web.UI.XhtmlTextWriter::AddRecognizedAttributes(string elementName, string[] attributes)
0x870a5  ldarg.0
0x870a6  ldstr    aInput// "input"
0x870ab  ldc.i4.s 0xB
0x870ad  newarr   [mscorlib]System.String
0x870b2  dup
0x870b3  ldc.i4.0
0x870b4  ldstr    aAccesskey// "accesskey"
0x870b9  stelem.ref
0x870ba  dup
0x870bb  ldc.i4.1
0x870bc  ldstr    aChecked// "checked"
0x870c1  stelem.ref
0x870c2  dup
0x870c3  ldc.i4.2
0x870c4  ldstr    aMaxlength// "maxlength"
0x870c9  stelem.ref
0x870ca  dup
0x870cb  ldc.i4.3
0x870cc  ldstr    aName// "name"
0x870d1  stelem.ref
0x870d2  dup
0x870d3  ldc.i4.4
0x870d4  ldstr    aSize// "size"
0x870d9  stelem.ref
0x870da  dup
0x870db  ldc.i4.5
0x870dc  ldstr    aSrc// "src"
0x870e1  stelem.ref
0x870e2  dup
0x870e3  ldc.i4.6
0x870e4  ldstr    aTabindex// "tabindex"
0x870e9  stelem.ref
0x870ea  dup
0x870eb  ldc.i4.7
0x870ec  ldstr    aType// "type"
0x870f1  stelem.ref
0x870f2  dup
0x870f3  ldc.i4.8
0x870f4  ldstr    aValue// "value"
0x870f9  stelem.ref
0x870fa  dup
0x870fb  ldc.i4.s 9
0x870fd  ldstr    aTitle_1// "title"
0x87102  stelem.ref
0x87103  dup
0x87104  ldc.i4.s 0xA
0x87106  ldstr    aDisabled// "disabled"
0x8710b  stelem.ref
0x8710c  call     instance void System.Web.UI.XhtmlTextWriter::AddRecognizedAttributes(string elementName, string[] attributes)
0x87111  ldarg.0
0x87112  ldstr    aLabel// "label"
0x87117  ldc.i4.1
0x87118  newarr   [mscorlib]System.String
0x8711d  dup
0x8711e  ldc.i4.0
0x8711f  ldstr    aAccesskey// "accesskey"
0x87124  stelem.ref
0x87125  call     instance void System.Web.UI.XhtmlTextWriter::AddRecognizedAttributes(string elementName, string[] attributes)
0x8712a  ldarg.0
0x8712b  ldstr    aLabel// "label"
0x87130  ldc.i4.1
0x87131  newarr   [mscorlib]System.String
0x87136  dup
0x87137  ldc.i4.0
0x87138  ldstr    aFor// "for"
0x8713d  stelem.ref
0x8713e  call     instance void System.Web.UI.XhtmlTextWriter::AddRecognizedAttributes(string elementName, string[] attributes)
0x87143  ldarg.0
0x87144  ldstr    aSelect// "select"
0x87149  ldc.i4.5
0x8714a  newarr   [mscorlib]System.String
0x8714f  dup
0x87150  ldc.i4.0
0x87151  ldstr    aMultiple// "multiple"
0x87156  stelem.ref
0x87157  dup
0x87158  ldc.i4.1
0x87159  ldstr    aName// "name"
0x8715e  stelem.ref
0x8715f  dup
0x87160  ldc.i4.2
0x87161  ldstr    aSize// "size"
0x87166  stelem.ref
0x87167  dup
0x87168  ldc.i4.3
0x87169  ldstr    aTabindex// "tabindex"
0x8716e  stelem.ref
0x8716f  dup
0x87170  ldc.i4.4
0x87171  ldstr    aDisabled// "disabled"
0x87176  stelem.ref
0x87177  call     instance void System.Web.UI.XhtmlTextWriter::AddRecognizedAttributes(string elementName, string[] attributes)
0x8717c  ldarg.0
0x8717d  ldstr    aOption// "option"
0x87182  ldc.i4.2
0x87183  newarr   [mscorlib]System.String
0x87188  dup
0x87189  ldc.i4.0
0x8718a  ldstr    aSelected// "selected"
0x8718f  stelem.ref
  ... truncated ...
```
