# System.Xml.Xsl.XsltOld.Compiler::ChooseCodeDomProvider

- ea: `0x6740`
- end: `0x6770`
- name: `System.Xml.Xsl.XsltOld.Compiler::ChooseCodeDomProvider`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x67b0`

## callees

- `0x6740`

## string_xrefs

- `0x6753`: `Microsoft.JScript.JScriptCodeProvider, Microsoft.JScript, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`

## pseudocode

```c

```

## disassembly

```asm
0x6740  ldarg.1
0x6741  brfalse.s loc_6753
0x6743  ldarg.1
0x6744  ldc.i4.1
0x6745  beq.s    loc_674D
0x6747  newobj   instance void [System]Microsoft.CSharp.CSharpCodeProvider::.ctor()
0x674c  ret
0x674d  newobj   instance void [System]Microsoft.VisualBasic.VBCodeProvider::.ctor()
0x6752  ret
0x6753  ldstr    aMicrosoftJscri// "Microsoft.JScript.JScriptCodeProvider, "...
0x6758  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x675d  ldc.i4   0x234
0x6762  ldnull
0x6763  ldnull
0x6764  ldnull
0x6765  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, object[], class [mscorlib]System.Globalization.CultureInfo)
0x676a  castclass [System]System.CodeDom.Compiler.CodeDomProvider
0x676f  ret
```
