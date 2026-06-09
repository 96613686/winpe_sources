# System.Xml.Xsl.IlGen.XmlILMethods::.cctor

- ea: `0x3d2e0`
- end: `0x3ef05`
- name: `System.Xml.Xsl.IlGen.XmlILMethods::.cctor`
- size: `7205`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3cc60`
- `0x3ef10`
- `0x3ef20`

## string_xrefs

- `0x3d2ea`: `Create`
- `0x3d31c`: `Create`
- `0x3d34e`: `Create`
- `0x3d380`: `Create`
- `0x3d3b2`: `Create`
- `0x3d3e4`: `Create`
- `0x3d416`: `Create`
- `0x3d448`: `Create`
- `0x3d47a`: `Create`
- `0x3d4ac`: `Create`
- `0x3d4f7`: `Create`
- `0x3d529`: `Create`
- `0x3d55b`: `Create`
- `0x3d58d`: `Create`
- `0x3d5bf`: `Create`
- `0x3d5f1`: `Create`
- `0x3d623`: `Create`
- `0x3d655`: `Create`
- `0x3d687`: `Create`
- `0x3d6b9`: `Create`
- `0x3d6eb`: `Create`
- `0x3d71d`: `Create`
- `0x3d74f`: `Create`
- `0x3d849`: `Create`
- `0x3d87b`: `Create`
- `0x3d8ad`: `Create`
- `0x3d8df`: `Create`
- `0x3d911`: `Create`
- `0x3d943`: `Create`
- `0x3d303`: `MoveNext`
- `0x3d335`: `MoveNext`
- `0x3d367`: `MoveNext`
- `0x3d399`: `MoveNext`
- `0x3d3cb`: `MoveNext`
- `0x3d3fd`: `MoveNext`
- `0x3d42f`: `MoveNext`
- `0x3d461`: `MoveNext`
- `0x3d493`: `MoveNext`
- `0x3d510`: `MoveNext`
- `0x3d542`: `MoveNext`
- `0x3d574`: `MoveNext`
- `0x3d5a6`: `MoveNext`
- `0x3d5d8`: `MoveNext`
- `0x3d60a`: `MoveNext`
- `0x3d63c`: `MoveNext`
- `0x3d66e`: `MoveNext`
- `0x3d6a0`: `MoveNext`
- `0x3d6d2`: `MoveNext`
- `0x3d704`: `MoveNext`
- `0x3d736`: `MoveNext`
- `0x3d862`: `MoveNext`
- `0x3d894`: `MoveNext`
- `0x3d8c6`: `MoveNext`
- `0x3d8f8`: `MoveNext`
- `0x3d92a`: `MoveNext`
- `0x3d95c`: `MoveNext`
- `0x3d9ed`: `ComparePosition`
- `0x3da1f`: `CreateCollation`
- `0x3db64`: `IsGlobalComputed`
- `0x3db7d`: `MatchesXmlType`
- `0x3dbb6`: `MatchesXmlType`
- `0x3dca0`: `MatchesXmlType`
- `0x3dcd9`: `MatchesXmlType`
- `0x3df34`: `MoveToAttribute`
- `0x3df6d`: `MoveToId`
- `0x3df86`: `MoveToParent`
- `0x3df9f`: `MoveToRoot`
- `0x3dfb8`: `MoveTo`
- `0x3dfd1`: `get_NamespaceURI`
- `0x3e035`: `WriteStartElement`
- `0x3e07b`: `WriteStartElementLocalName`
- `0x3e0a7`: `WriteEndElement`
- `0x3e0c0`: `WriteStartAttribute`
- `0x3e106`: `WriteStartAttributeLocalName`
- `0x3e132`: `WriteEndAttribute`
- `0x3e14b`: `WriteString`
- `0x3e164`: `WriteRaw`
- `0x3e1c2`: `WriteStartElementUnchecked`
- `0x3e208`: `WriteStartElementUnchecked`
- `0x3e24d`: `WriteEndElementUnchecked`
- `0x3e293`: `WriteEndElementUnchecked`
- `0x3e2bf`: `WriteStartAttributeUnchecked`
- `0x3e305`: `WriteStartAttributeUnchecked`
- `0x3e331`: `WriteEndAttributeUnchecked`
- `0x3e34a`: `WriteNamespaceDeclarationUnchecked`
- `0x3e363`: `WriteStringUnchecked`
- `0x3e37c`: `WriteRawUnchecked`
- `0x3e395`: `WriteStartRoot`
- `0x3e3ae`: `WriteEndRoot`
- `0x3e3c7`: `WriteStartElementComputed`
- `0x3e3f3`: `WriteStartElementComputed`
- `0x3e42c`: `WriteStartElementComputed`
- `0x3e465`: `WriteStartElementComputed`
- `0x3e491`: `WriteStartAttributeComputed`
- `0x3e4bd`: `WriteStartAttributeComputed`
- `0x3e4f6`: `WriteStartAttributeComputed`
- `0x3e52f`: `WriteStartAttributeComputed`
- `0x3e55b`: `WriteNamespaceDeclaration`
- `0x3e574`: `WriteStartComment`
- `0x3e58d`: `WriteCommentString`
- `0x3e5a6`: `WriteEndComment`
- `0x3e5bf`: `WriteStartProcessingInstruction`
- `0x3e5d8`: `WriteProcessingInstructionString`
- `0x3e5f1`: `WriteEndProcessingInstruction`
- `0x3e60a`: `WriteItem`
- `0x3e623`: `XsltCopyOf`
- `0x3e63c`: `StartCopy`
- `0x3e655`: `EndCopy`
- `0x3e687`: `Compare`
- `0x3e89a`: `CompareOrdinal`

## pseudocode

```c

```

## disassembly

```asm
0x3d2e0  ldtoken  System.Xml.Xsl.Runtime.AncestorIterator
0x3d2e5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d2ea  ldstr    aCreate// "Create"
0x3d2ef  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d2f4  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::AncCreate
0x3d2f9  ldtoken  System.Xml.Xsl.Runtime.AncestorIterator
0x3d2fe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d303  ldstr    aMovenext// "MoveNext"
0x3d308  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d30d  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::AncNext
0x3d312  ldtoken  System.Xml.Xsl.Runtime.AncestorDocOrderIterator
0x3d317  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d31c  ldstr    aCreate// "Create"
0x3d321  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d326  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::AncDOCreate
0x3d32b  ldtoken  System.Xml.Xsl.Runtime.AncestorDocOrderIterator
0x3d330  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d335  ldstr    aMovenext// "MoveNext"
0x3d33a  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d33f  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::AncDONext
0x3d344  ldtoken  System.Xml.Xsl.Runtime.AttributeContentIterator
0x3d349  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d34e  ldstr    aCreate// "Create"
0x3d353  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d358  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::AttrContentCreate
0x3d35d  ldtoken  System.Xml.Xsl.Runtime.AttributeContentIterator
0x3d362  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d367  ldstr    aMovenext// "MoveNext"
0x3d36c  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d371  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::AttrContentNext
0x3d376  ldtoken  System.Xml.Xsl.Runtime.AttributeIterator
0x3d37b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d380  ldstr    aCreate// "Create"
0x3d385  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d38a  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::AttrCreate
0x3d38f  ldtoken  System.Xml.Xsl.Runtime.AttributeIterator
0x3d394  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d399  ldstr    aMovenext// "MoveNext"
0x3d39e  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d3a3  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::AttrNext
0x3d3a8  ldtoken  System.Xml.Xsl.Runtime.ContentIterator
0x3d3ad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d3b2  ldstr    aCreate// "Create"
0x3d3b7  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d3bc  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ContentCreate
0x3d3c1  ldtoken  System.Xml.Xsl.Runtime.ContentIterator
0x3d3c6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d3cb  ldstr    aMovenext// "MoveNext"
0x3d3d0  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d3d5  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ContentNext
0x3d3da  ldtoken  System.Xml.Xsl.Runtime.ContentMergeIterator
0x3d3df  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d3e4  ldstr    aCreate// "Create"
0x3d3e9  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d3ee  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ContentMergeCreate
0x3d3f3  ldtoken  System.Xml.Xsl.Runtime.ContentMergeIterator
0x3d3f8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d3fd  ldstr    aMovenext// "MoveNext"
0x3d402  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d407  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ContentMergeNext
0x3d40c  ldtoken  System.Xml.Xsl.Runtime.DescendantIterator
0x3d411  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d416  ldstr    aCreate// "Create"
0x3d41b  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d420  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::DescCreate
0x3d425  ldtoken  System.Xml.Xsl.Runtime.DescendantIterator
0x3d42a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d42f  ldstr    aMovenext// "MoveNext"
0x3d434  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d439  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::DescNext
0x3d43e  ldtoken  System.Xml.Xsl.Runtime.DescendantMergeIterator
0x3d443  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d448  ldstr    aCreate// "Create"
0x3d44d  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d452  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::DescMergeCreate
0x3d457  ldtoken  System.Xml.Xsl.Runtime.DescendantMergeIterator
0x3d45c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d461  ldstr    aMovenext// "MoveNext"
0x3d466  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d46b  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::DescMergeNext
0x3d470  ldtoken  System.Xml.Xsl.Runtime.DifferenceIterator
0x3d475  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d47a  ldstr    aCreate// "Create"
0x3d47f  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d484  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::DiffCreate
0x3d489  ldtoken  System.Xml.Xsl.Runtime.DifferenceIterator
0x3d48e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d493  ldstr    aMovenext// "MoveNext"
0x3d498  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d49d  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::DiffNext
0x3d4a2  ldtoken  System.Xml.Xsl.Runtime.DodSequenceMerge
0x3d4a7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d4ac  ldstr    aCreate// "Create"
0x3d4b1  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d4b6  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::DodMergeCreate
0x3d4bb  ldtoken  System.Xml.Xsl.Runtime.DodSequenceMerge
0x3d4c0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d4c5  ldstr    aAddsequence// "AddSequence"
0x3d4ca  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d4cf  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::DodMergeAdd
0x3d4d4  ldtoken  System.Xml.Xsl.Runtime.DodSequenceMerge
0x3d4d9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d4de  ldstr    aMergesequences// "MergeSequences"
0x3d4e3  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d4e8  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::DodMergeSeq
0x3d4ed  ldtoken  System.Xml.Xsl.Runtime.ElementContentIterator
0x3d4f2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d4f7  ldstr    aCreate// "Create"
0x3d4fc  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d501  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ElemContentCreate
0x3d506  ldtoken  System.Xml.Xsl.Runtime.ElementContentIterator
0x3d50b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d510  ldstr    aMovenext// "MoveNext"
0x3d515  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d51a  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ElemContentNext
0x3d51f  ldtoken  System.Xml.Xsl.Runtime.FollowingSiblingIterator
0x3d524  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d529  ldstr    aCreate// "Create"
0x3d52e  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d533  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::FollSibCreate
0x3d538  ldtoken  System.Xml.Xsl.Runtime.FollowingSiblingIterator
0x3d53d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d542  ldstr    aMovenext// "MoveNext"
0x3d547  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d54c  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::FollSibNext
0x3d551  ldtoken  System.Xml.Xsl.Runtime.FollowingSiblingMergeIterator
0x3d556  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d55b  ldstr    aCreate// "Create"
0x3d560  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d565  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::FollSibMergeCreate
0x3d56a  ldtoken  System.Xml.Xsl.Runtime.FollowingSiblingMergeIterator
0x3d56f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d574  ldstr    aMovenext// "MoveNext"
0x3d579  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d57e  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::FollSibMergeNext
0x3d583  ldtoken  System.Xml.Xsl.Runtime.IdIterator
0x3d588  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d58d  ldstr    aCreate// "Create"
0x3d592  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d597  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::IdCreate
0x3d59c  ldtoken  System.Xml.Xsl.Runtime.IdIterator
0x3d5a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d5a6  ldstr    aMovenext// "MoveNext"
0x3d5ab  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d5b0  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::IdNext
0x3d5b5  ldtoken  System.Xml.Xsl.Runtime.IntersectIterator
0x3d5ba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d5bf  ldstr    aCreate// "Create"
0x3d5c4  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d5c9  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::InterCreate
0x3d5ce  ldtoken  System.Xml.Xsl.Runtime.IntersectIterator
0x3d5d3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d5d8  ldstr    aMovenext// "MoveNext"
0x3d5dd  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d5e2  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::InterNext
0x3d5e7  ldtoken  System.Xml.Xsl.Runtime.NodeKindContentIterator
0x3d5ec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d5f1  ldstr    aCreate// "Create"
0x3d5f6  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d5fb  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::KindContentCreate
0x3d600  ldtoken  System.Xml.Xsl.Runtime.NodeKindContentIterator
0x3d605  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d60a  ldstr    aMovenext// "MoveNext"
0x3d60f  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d614  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::KindContentNext
0x3d619  ldtoken  System.Xml.Xsl.Runtime.NamespaceIterator
0x3d61e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d623  ldstr    aCreate// "Create"
0x3d628  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d62d  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::NmspCreate
0x3d632  ldtoken  System.Xml.Xsl.Runtime.NamespaceIterator
0x3d637  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d63c  ldstr    aMovenext// "MoveNext"
0x3d641  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d646  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::NmspNext
0x3d64b  ldtoken  System.Xml.Xsl.Runtime.NodeRangeIterator
0x3d650  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d655  ldstr    aCreate// "Create"
0x3d65a  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d65f  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::NodeRangeCreate
0x3d664  ldtoken  System.Xml.Xsl.Runtime.NodeRangeIterator
0x3d669  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d66e  ldstr    aMovenext// "MoveNext"
0x3d673  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d678  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::NodeRangeNext
0x3d67d  ldtoken  System.Xml.Xsl.Runtime.ParentIterator
0x3d682  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d687  ldstr    aCreate// "Create"
0x3d68c  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d691  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ParentCreate
0x3d696  ldtoken  System.Xml.Xsl.Runtime.ParentIterator
0x3d69b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d6a0  ldstr    aMovenext// "MoveNext"
0x3d6a5  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d6aa  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ParentNext
0x3d6af  ldtoken  System.Xml.Xsl.Runtime.PrecedingIterator
0x3d6b4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d6b9  ldstr    aCreate// "Create"
0x3d6be  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d6c3  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::PrecCreate
0x3d6c8  ldtoken  System.Xml.Xsl.Runtime.PrecedingIterator
0x3d6cd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d6d2  ldstr    aMovenext// "MoveNext"
0x3d6d7  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d6dc  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::PrecNext
0x3d6e1  ldtoken  System.Xml.Xsl.Runtime.PrecedingSiblingIterator
0x3d6e6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d6eb  ldstr    aCreate// "Create"
0x3d6f0  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d6f5  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::PreSibCreate
0x3d6fa  ldtoken  System.Xml.Xsl.Runtime.PrecedingSiblingIterator
0x3d6ff  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d704  ldstr    aMovenext// "MoveNext"
0x3d709  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d70e  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::PreSibNext
0x3d713  ldtoken  System.Xml.Xsl.Runtime.PrecedingSiblingDocOrderIterator
0x3d718  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d71d  ldstr    aCreate// "Create"
0x3d722  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d727  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::PreSibDOCreate
0x3d72c  ldtoken  System.Xml.Xsl.Runtime.PrecedingSiblingDocOrderIterator
0x3d731  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d736  ldstr    aMovenext// "MoveNext"
0x3d73b  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d740  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::PreSibDONext
0x3d745  ldtoken  System.Xml.Xsl.Runtime.XmlSortKeyAccumulator
0x3d74a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d74f  ldstr    aCreate// "Create"
0x3d754  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d759  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::SortKeyCreate
0x3d75e  ldtoken  System.Xml.Xsl.Runtime.XmlSortKeyAccumulator
0x3d763  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d768  ldstr    aAdddatetimesor// "AddDateTimeSortKey"
0x3d76d  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d772  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::SortKeyDateTime
0x3d777  ldtoken  System.Xml.Xsl.Runtime.XmlSortKeyAccumulator
0x3d77c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d781  ldstr    aAdddecimalsort// "AddDecimalSortKey"
0x3d786  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d78b  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::SortKeyDecimal
0x3d790  ldtoken  System.Xml.Xsl.Runtime.XmlSortKeyAccumulator
0x3d795  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d79a  ldstr    aAdddoublesortk// "AddDoubleSortKey"
0x3d79f  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d7a4  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::SortKeyDouble
0x3d7a9  ldtoken  System.Xml.Xsl.Runtime.XmlSortKeyAccumulator
0x3d7ae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d7b3  ldstr    aAddemptysortke// "AddEmptySortKey"
0x3d7b8  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d7bd  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::SortKeyEmpty
0x3d7c2  ldtoken  System.Xml.Xsl.Runtime.XmlSortKeyAccumulator
0x3d7c7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d7cc  ldstr    aFinishsortkeys// "FinishSortKeys"
0x3d7d1  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d7d6  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::SortKeyFinish
0x3d7db  ldtoken  System.Xml.Xsl.Runtime.XmlSortKeyAccumulator
0x3d7e0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d7e5  ldstr    aAddintsortkey// "AddIntSortKey"
0x3d7ea  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d7ef  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::SortKeyInt
0x3d7f4  ldtoken  System.Xml.Xsl.Runtime.XmlSortKeyAccumulator
0x3d7f9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d7fe  ldstr    aAddintegersort// "AddIntegerSortKey"
0x3d803  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d808  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::SortKeyInteger
0x3d80d  ldtoken  System.Xml.Xsl.Runtime.XmlSortKeyAccumulator
0x3d812  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d817  ldstr    aGetKeys// "get_Keys"
0x3d81c  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d821  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::SortKeyKeys
0x3d826  ldtoken  System.Xml.Xsl.Runtime.XmlSortKeyAccumulator
0x3d82b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d830  ldstr    aAddstringsortk// "AddStringSortKey"
0x3d835  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d83a  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::SortKeyString
0x3d83f  ldtoken  System.Xml.Xsl.Runtime.UnionIterator
0x3d844  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d849  ldstr    aCreate// "Create"
0x3d84e  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d853  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::UnionCreate
0x3d858  ldtoken  System.Xml.Xsl.Runtime.UnionIterator
0x3d85d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d862  ldstr    aMovenext// "MoveNext"
0x3d867  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d86c  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::UnionNext
0x3d871  ldtoken  System.Xml.Xsl.Runtime.XPathFollowingIterator
0x3d876  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d87b  ldstr    aCreate// "Create"
0x3d880  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d885  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::XPFollCreate
0x3d88a  ldtoken  System.Xml.Xsl.Runtime.XPathFollowingIterator
0x3d88f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d894  ldstr    aMovenext// "MoveNext"
0x3d899  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d89e  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::XPFollNext
0x3d8a3  ldtoken  System.Xml.Xsl.Runtime.XPathFollowingMergeIterator
0x3d8a8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d8ad  ldstr    aCreate// "Create"
0x3d8b2  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d8b7  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::XPFollMergeCreate
  ... truncated ...
```
