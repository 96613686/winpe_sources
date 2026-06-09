# Microsoft.SharePoint.Taxonomy.Internal.Sandbox::GenerateFullSandboxItemsXml

- ea: `0x2b930`
- end: `0x2b9e5`
- name: `Microsoft.SharePoint.Taxonomy.Internal.Sandbox::GenerateFullSandboxItemsXml`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2b020`

## callees

- `0x2b930`
- `0x2bca0`
- `0x2bd00`

## string_xrefs

- `0x2b93c`: `Generating full XML for sandbox commit.`
- `0x2b9d9`: `Generated full XML for sandbox commit.`

## pseudocode

```c

```

## disassembly

```asm
0x2b930  ldc.i4   0x32657477
0x2b935  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2b93a  ldc.i4.s 0x64
0x2b93c  ldstr    aGeneratingFull// "Generating full XML for sandbox commit."
0x2b941  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x2b946  ldarg.0
0x2b947  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class SandboxItemKey, class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem> Microsoft.SharePoint.Taxonomy.Internal.Sandbox::sandboxItems
0x2b94c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class SandboxItemKey, class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem>::get_Values()
0x2b951  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<class SandboxItemKey, class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem>::GetEnumerator()
0x2b956  stloc.2
0x2b957  br.s     loc_2B973
0x2b959  ldloca.s 2
0x2b95b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<class SandboxItemKey, class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem>::get_Current()
0x2b960  stloc.0
0x2b961  ldloc.0
0x2b962  ldarg.0
0x2b963  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStore
0x2b968  ldarg.0
0x2b969  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.SharePoint.Taxonomy.Internal.Sandbox::xmlWriter
0x2b96e  call     void Microsoft.SharePoint.Taxonomy.Internal.SandboxXmlGenerator::GetXml(class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem item, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class [System.Xml]System.Xml.XmlWriter writer)
0x2b973  ldloca.s 2
0x2b975  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<class SandboxItemKey, class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem>::MoveNext()
0x2b97a  brtrue.s loc_2B959
0x2b97c  leave.s  loc_2B98C
0x2b97e  ldloca.s 2
0x2b980  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<class SandboxItemKey, class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem>
0x2b986  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b98b  endfinally
0x2b98c  ldarg.0
0x2b98d  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TermStoreSandboxItem Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStoreSandboxItem
0x2b992  brfalse.s loc_2B9AB
0x2b994  ldarg.0
0x2b995  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TermStoreSandboxItem Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStoreSandboxItem
0x2b99a  ldarg.0
0x2b99b  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStore
0x2b9a0  ldarg.0
0x2b9a1  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.SharePoint.Taxonomy.Internal.Sandbox::xmlWriter
0x2b9a6  call     void Microsoft.SharePoint.Taxonomy.Internal.SandboxXmlGenerator::GetTermStoreXml(class Microsoft.SharePoint.Taxonomy.Internal.TermStoreSandboxItem item, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class [System.Xml]System.Xml.XmlWriter writer)
0x2b9ab  ldarg.0
0x2b9ac  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.SharePoint.Taxonomy.Internal.Sandbox::xmlWriter
0x2b9b1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x2b9b6  ldarg.0
0x2b9b7  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.SharePoint.Taxonomy.Internal.Sandbox::xmlWriter
0x2b9bc  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x2b9c1  ldarg.0
0x2b9c2  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.Sandbox::sandboxItemsXml
0x2b9c7  callvirt instance string [mscorlib]System.Object::ToString()
0x2b9cc  stloc.1
0x2b9cd  ldc.i4   0x32657478
0x2b9d2  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2b9d7  ldc.i4.s 0x64
0x2b9d9  ldstr    aGeneratedFullX// "Generated full XML for sandbox commit."
0x2b9de  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x2b9e3  ldloc.1
0x2b9e4  ret
```
