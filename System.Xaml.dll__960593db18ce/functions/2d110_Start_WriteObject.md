# Start::WriteObject

- ea: `0x2d110`
- end: `0x2d158`
- name: `Start::WriteObject`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x8860`
- `0x11f20`
- `0x2cb20`
- `0x2cba0`
- `0x2cf60`
- `0x2d110`
- `0x2d490`

## string_xrefs

- `0x2d135`: `XamlXmlWriterWriteObjectNotSupportedInCurrentState`

## pseudocode

```c

```

## disassembly

```asm
0x2d110  ldarg.1
0x2d111  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d116  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d11b  ldarg.2
0x2d11c  callvirt instance void Frame::set_Type(class System.Xaml.XamlType value)
0x2d121  ldarg.1
0x2d122  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d127  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d12c  ldarg.3
0x2d12d  callvirt instance void Frame::set_IsObjectFromMember(bool value)
0x2d132  ldarg.3
0x2d133  brfalse.s loc_2D145
0x2d135  ldstr    aXamlxmlwriterw_0// "XamlXmlWriterWriteObjectNotSupportedInC"...
0x2d13a  call     string System.Xaml.SR::Get(string id)
0x2d13f  newobj   instance void System.Xaml.XamlXmlWriterException::.ctor(string message)
0x2d144  throw
0x2d145  ldarg.1
0x2d146  ldarg.2
0x2d147  call     void WriterState::WriteStartElementForObject(class System.Xaml.XamlXmlWriter writer, class System.Xaml.XamlType type)
0x2d14c  ldarg.1
0x2d14d  call     class WriterState InRecordTryAttributes::get_State()
0x2d152  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d157  ret
```
