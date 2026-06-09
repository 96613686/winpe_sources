# System.Xml.Xsl.XsltOld.HtmlAttributeProps::CreatePropsTable

- ea: `0x9e80`
- end: `0xa081`
- name: `System.Xml.Xsl.XsltOld.HtmlAttributeProps::CreatePropsTable`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0xa0a0`

## callees

- `0x9e10`

## string_xrefs

- `0x9ecb`: `classid`
- `0x9ef1`: `compact`
- `0xa034`: `readonly`

## pseudocode

```c

```

## disassembly

```asm
0x9e80  ldc.i4.0
0x9e81  stloc.0
0x9e82  ldc.i4.1
0x9e83  stloc.1
0x9e84  ldc.i4.s 0x1A
0x9e86  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x9e8b  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(int32, class [mscorlib]System.Collections.IEqualityComparer)
0x9e90  stloc.2
0x9e91  ldloc.2
0x9e92  ldstr    aAction// "action"
0x9e97  ldloc.0
0x9e98  ldloc.1
0x9e99  ldloc.0
0x9e9a  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9e9f  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9ea4  ldloc.2
0x9ea5  ldstr    aChecked// "checked"
0x9eaa  ldloc.1
0x9eab  ldloc.0
0x9eac  ldloc.0
0x9ead  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9eb2  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9eb7  ldloc.2
0x9eb8  ldstr    aCite// "cite"
0x9ebd  ldloc.0
0x9ebe  ldloc.1
0x9ebf  ldloc.0
0x9ec0  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9ec5  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9eca  ldloc.2
0x9ecb  ldstr    aClassid// "classid"
0x9ed0  ldloc.0
0x9ed1  ldloc.1
0x9ed2  ldloc.0
0x9ed3  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9ed8  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9edd  ldloc.2
0x9ede  ldstr    aCodebase// "codebase"
0x9ee3  ldloc.0
0x9ee4  ldloc.1
0x9ee5  ldloc.0
0x9ee6  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9eeb  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9ef0  ldloc.2
0x9ef1  ldstr    aCompact// "compact"
0x9ef6  ldloc.1
0x9ef7  ldloc.0
0x9ef8  ldloc.0
0x9ef9  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9efe  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9f03  ldloc.2
0x9f04  ldstr    aData// "data"
0x9f09  ldloc.0
0x9f0a  ldloc.1
0x9f0b  ldloc.0
0x9f0c  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9f11  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9f16  ldloc.2
0x9f17  ldstr    aDatasrc// "datasrc"
0x9f1c  ldloc.0
0x9f1d  ldloc.1
0x9f1e  ldloc.0
0x9f1f  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9f24  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9f29  ldloc.2
0x9f2a  ldstr    aDeclare// "declare"
0x9f2f  ldloc.1
0x9f30  ldloc.0
0x9f31  ldloc.0
0x9f32  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9f37  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9f3c  ldloc.2
0x9f3d  ldstr    aDefer// "defer"
0x9f42  ldloc.1
0x9f43  ldloc.0
0x9f44  ldloc.0
0x9f45  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9f4a  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9f4f  ldloc.2
0x9f50  ldstr    aDisabled// "disabled"
0x9f55  ldloc.1
0x9f56  ldloc.0
0x9f57  ldloc.0
0x9f58  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9f5d  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9f62  ldloc.2
0x9f63  ldstr    aFor// "for"
0x9f68  ldloc.0
0x9f69  ldloc.1
0x9f6a  ldloc.0
0x9f6b  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9f70  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9f75  ldloc.2
0x9f76  ldstr    aHref// "href"
0x9f7b  ldloc.0
0x9f7c  ldloc.1
0x9f7d  ldloc.0
0x9f7e  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9f83  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9f88  ldloc.2
0x9f89  ldstr    aIsmap// "ismap"
0x9f8e  ldloc.1
0x9f8f  ldloc.0
0x9f90  ldloc.0
0x9f91  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9f96  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9f9b  ldloc.2
0x9f9c  ldstr    aLongdesc// "longdesc"
0x9fa1  ldloc.0
0x9fa2  ldloc.1
0x9fa3  ldloc.0
0x9fa4  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9fa9  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9fae  ldloc.2
0x9faf  ldstr    aMultiple// "multiple"
0x9fb4  ldloc.1
0x9fb5  ldloc.0
0x9fb6  ldloc.0
0x9fb7  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9fbc  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9fc1  ldloc.2
0x9fc2  ldstr    aName// "name"
0x9fc7  ldloc.0
0x9fc8  ldloc.0
0x9fc9  ldloc.1
0x9fca  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9fcf  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9fd4  ldloc.2
0x9fd5  ldstr    aNohref// "nohref"
0x9fda  ldloc.1
0x9fdb  ldloc.0
0x9fdc  ldloc.0
0x9fdd  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9fe2  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9fe7  ldloc.2
0x9fe8  ldstr    aNoresize// "noresize"
0x9fed  ldloc.1
0x9fee  ldloc.0
0x9fef  ldloc.0
0x9ff0  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0x9ff5  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x9ffa  ldloc.2
0x9ffb  ldstr    aNoshade// "noshade"
0xa000  ldloc.1
0xa001  ldloc.0
0xa002  ldloc.0
0xa003  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0xa008  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xa00d  ldloc.2
0xa00e  ldstr    aNowrap// "nowrap"
0xa013  ldloc.1
0xa014  ldloc.0
0xa015  ldloc.0
0xa016  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0xa01b  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xa020  ldloc.2
0xa021  ldstr    aProfile// "profile"
0xa026  ldloc.0
0xa027  ldloc.1
0xa028  ldloc.0
0xa029  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0xa02e  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xa033  ldloc.2
0xa034  ldstr    aReadonly// "readonly"
0xa039  ldloc.1
0xa03a  ldloc.0
0xa03b  ldloc.0
0xa03c  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0xa041  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xa046  ldloc.2
0xa047  ldstr    aSelected// "selected"
0xa04c  ldloc.1
0xa04d  ldloc.0
0xa04e  ldloc.0
0xa04f  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0xa054  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xa059  ldloc.2
0xa05a  ldstr    aSrc// "src"
0xa05f  ldloc.0
0xa060  ldloc.1
0xa061  ldloc.0
0xa062  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0xa067  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xa06c  ldloc.2
0xa06d  ldstr    aUsemap// "usemap"
0xa072  ldloc.0
0xa073  ldloc.1
0xa074  ldloc.0
0xa075  call     class System.Xml.Xsl.XsltOld.HtmlAttributeProps System.Xml.Xsl.XsltOld.HtmlAttributeProps::Create(bool abr, bool uri, bool name)
0xa07a  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xa07f  ldloc.2
0xa080  ret
```
