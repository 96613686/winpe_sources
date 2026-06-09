# System.Deployment.Application.ManifestGenerator::CloneAssemblyTemplate

- ea: `0x192a0`
- end: `0x192e8`
- name: `System.Deployment.Application.ManifestGenerator::CloneAssemblyTemplate`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18f40`
- `0x18fd0`

## callees

- `0x192a0`

## string_xrefs

- `0x192ae`: `AssemblyTemplate.xml`

## pseudocode

```c

```

## disassembly

```asm
0x192a0  ldsfld   object System.Deployment.Application.ManifestGenerator::assemblyTemplateDoc
0x192a5  brtrue.s loc_192D3
0x192a7  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x192ac  stloc.0
0x192ad  ldloc.0
0x192ae  ldstr    aAssemblytempla// "AssemblyTemplate.xml"
0x192b3  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(string)
0x192b8  stloc.1
0x192b9  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x192be  stloc.2
0x192bf  ldloc.2
0x192c0  ldloc.1
0x192c1  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [mscorlib]System.IO.Stream)
0x192c6  ldsflda  object System.Deployment.Application.ManifestGenerator::assemblyTemplateDoc
0x192cb  ldloc.2
0x192cc  ldnull
0x192cd  call     object [mscorlib]System.Threading.Interlocked::CompareExchange(object&, object, object)
0x192d2  pop
0x192d3  ldsfld   object System.Deployment.Application.ManifestGenerator::assemblyTemplateDoc
0x192d8  castclass [System.Xml]System.Xml.XmlDocument
0x192dd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::Clone()
0x192e2  castclass [System.Xml]System.Xml.XmlDocument
0x192e7  ret
```
