# System.Xml.Xsl.Qil.QilPatternFactory::XsltInvokeEarlyBound

- ea: `0x38420`
- end: `0x3844f`
- name: `System.Xml.Xsl.Qil.QilPatternFactory::XsltInvokeEarlyBound`
- size: `47`
- prototype: ``
- caller_count: `38`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1aee0`
- `0x26480`
- `0x264b0`
- `0x264e0`
- `0x26510`
- `0x26540`
- `0x26570`
- `0x265a0`
- `0x265d0`
- `0x26600`
- `0x26640`
- `0x266c0`
- `0x26720`
- `0x26750`
- `0x26790`
- `0x267c0`
- `0x26800`
- `0x26840`
- `0x26870`
- `0x268a0`
- `0x268d0`
- `0x26900`
- `0x29630`
- `0x29660`
- `0x296d0`
- `0x29b50`
- `0x29bc0`
- `0x29bf0`
- `0x29c20`
- `0x29c50`
- `0x29c80`
- `0x29cb0`
- `0x29ce0`
- `0x29d10`
- `0x29d40`
- `0x29d70`
- `0x29da0`
- `0x29dd0`

## callees

- `0x360b0`
- `0x363d0`
- `0x36d60`
- `0x377d0`

## pseudocode

```c

```

## disassembly

```asm
0x38420  ldarg.0
0x38421  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilPatternFactory::f
0x38426  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilFactory::ActualParameterList()
0x3842b  stloc.0
0x3842c  ldloc.0
0x3842d  ldarg.s  4
0x3842f  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode> list)
0x38434  ldarg.0
0x38435  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilPatternFactory::f
0x3843a  ldarg.1
0x3843b  ldarg.0
0x3843c  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilPatternFactory::f
0x38441  ldarg.2
0x38442  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralObject(object value)
0x38447  ldloc.0
0x38448  ldarg.3
0x38449  callvirt instance class System.Xml.Xsl.Qil.QilInvokeEarlyBound System.Xml.Xsl.Qil.QilFactory::XsltInvokeEarlyBound(class System.Xml.Xsl.Qil.QilNode name, class System.Xml.Xsl.Qil.QilNode clrMethod, class System.Xml.Xsl.Qil.QilNode arguments, class System.Xml.Xsl.XmlQueryType xmlType)
0x3844e  ret
```
