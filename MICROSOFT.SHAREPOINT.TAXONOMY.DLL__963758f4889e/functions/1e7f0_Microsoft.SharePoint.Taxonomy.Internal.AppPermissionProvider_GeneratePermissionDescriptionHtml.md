# Microsoft.SharePoint.Taxonomy.Internal.AppPermissionProvider::GeneratePermissionDescriptionHtml

- ea: `0x1e7f0`
- end: `0x1e876`
- name: `Microsoft.SharePoint.Taxonomy.Internal.AppPermissionProvider::GeneratePermissionDescriptionHtml`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1e7f0`
- `0x1e9d0`
- `0x1e9f0`
- `0x2acd0`

## string_xrefs

- `0x1e801`: `writer`
- `0x1e7f3`: `permissionRequestXml`
- `0x1e85a`: `PermAccessTermStore`

## pseudocode

```c

```

## disassembly

```asm
0x1e7f0  ldarg.1
0x1e7f1  brtrue.s loc_1E7FE
0x1e7f3  ldstr    aPermissionrequ_0// "permissionRequestXml"
0x1e7f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1e7fd  throw
0x1e7fe  ldarg.2
0x1e7ff  brtrue.s loc_1E80C
0x1e801  ldstr    aWriter// "writer"
0x1e806  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1e80b  throw
0x1e80c  ldarg.1
0x1e80d  call     bool Microsoft.SharePoint.Taxonomy.Internal.AppPermissionProvider::CanModifyTermStore(class [System.Xml.Linq]System.Xml.Linq.XElement permissionRequestXml)
0x1e812  brfalse.s loc_1E841
0x1e814  ldarg.2
0x1e815  ldc.i4.s 0x19
0x1e817  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x1e81c  ldarg.2
0x1e81d  ldc.i4.s 0x19
0x1e81f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x1e824  ldarg.2
0x1e825  ldstr    aPermmodifyterm// "PermModifyTermStore"
0x1e82a  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x1e82f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0x1e834  ldarg.2
0x1e835  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x1e83a  ldarg.2
0x1e83b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x1e840  ret
0x1e841  ldarg.1
0x1e842  call     bool Microsoft.SharePoint.Taxonomy.Internal.AppPermissionProvider::CanAccessTermStore(class [System.Xml.Linq]System.Xml.Linq.XElement permissionRequestXml)
0x1e847  brfalse.s loc_1E875
0x1e849  ldarg.2
0x1e84a  ldc.i4.s 0x19
0x1e84c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x1e851  ldarg.2
0x1e852  ldc.i4.s 0x19
0x1e854  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x1e859  ldarg.2
0x1e85a  ldstr    aPermaccessterm// "PermAccessTermStore"
0x1e85f  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x1e864  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEncodedText(string)
0x1e869  ldarg.2
0x1e86a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x1e86f  ldarg.2
0x1e870  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x1e875  ret
```
