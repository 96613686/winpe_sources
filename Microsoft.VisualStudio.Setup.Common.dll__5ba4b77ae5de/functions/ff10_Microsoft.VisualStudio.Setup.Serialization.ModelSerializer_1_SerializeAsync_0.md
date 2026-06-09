# Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1::SerializeAsync_0

- ea: `0xff10`
- end: `0xff61`
- name: `Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1::SerializeAsync_0`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0xc1a0`

## string_xrefs

- `0xff30`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xff10  newobj   instance void class <>c__DisplayClass48_0<var<u1>>::.ctor()
0xff15  dup
0xff16  ldarg.0
0xff17  stfld    class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>> class <>c__DisplayClass48_0<var<u1>>::<>4__this
0xff1c  dup
0xff1d  ldarg.1
0xff1e  stfld    class [mscorlib]System.IO.TextWriter class <>c__DisplayClass48_0<var<u1>>::writer
0xff23  dup
0xff24  ldarg.2
0xff25  stfld    var<u1> class <>c__DisplayClass48_0<var<u1>>::object
0xff2a  dup
0xff2b  ldfld    class [mscorlib]System.IO.TextWriter class <>c__DisplayClass48_0<var<u1>>::writer
0xff30  ldstr    aWriter// "writer"
0xff35  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xff3a  dup
0xff3b  ldfld    var<u1> class <>c__DisplayClass48_0<var<u1>>::object
0xff40  box      var<u1>
0xff45  ldstr    aObject// "object"
0xff4a  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xff4f  ldftn    instance void class <>c__DisplayClass48_0<var<u1>>::<SerializeAsync>b__0()
0xff55  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0xff5a  ldarg.3
0xff5b  call     class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.Task::Run(class [mscorlib]System.Action, valuetype [mscorlib]System.Threading.CancellationToken)
0xff60  ret
```
