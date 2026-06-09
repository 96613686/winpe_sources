# System.Web.UI.ScriptComponentDescriptor::AddComponentProperty

- ea: `0x12e00`
- end: `0x12e26`
- name: `System.Web.UI.ScriptComponentDescriptor::AddComponentProperty`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x12e00`
- `0x12eb0`
- `0x282d0`
- `0x3a9e0`

## string_xrefs

- `0x12e0d`: `componentID`

## pseudocode

```c

```

## disassembly

```asm
0x12e00  ldarg.2
0x12e01  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12e06  brfalse.s loc_12E18
0x12e08  call     string System.Web.Resources.AtlasWeb::get_Common_NullOrEmpty()
0x12e0d  ldstr    aComponentid// "componentID"
0x12e12  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x12e17  throw
0x12e18  ldarg.0
0x12e19  ldarg.1
0x12e1a  ldarg.2
0x12e1b  newobj   instance void ComponentReference::.ctor(string componentID)
0x12e20  call     instance void System.Web.UI.ScriptComponentDescriptor::AddProperty(string name, class Expression value)
0x12e25  ret
```
