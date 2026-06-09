# System.Web.UI.CompositeScriptReferenceEventArgs::.ctor

- ea: `0xfe40`
- end: `0xfe5c`
- name: `System.Web.UI.CompositeScriptReferenceEventArgs::.ctor`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x15720`

## callees

- `0xfe40`

## string_xrefs

- `0xfe49`: `compositeScript`

## pseudocode

```c

```

## disassembly

```asm
0xfe40  ldarg.0
0xfe41  call     instance void [mscorlib]System.EventArgs::.ctor()
0xfe46  ldarg.1
0xfe47  brtrue.s loc_FE54
0xfe49  ldstr    aCompositescrip// "compositeScript"
0xfe4e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfe53  throw
0xfe54  ldarg.0
0xfe55  ldarg.1
0xfe56  stfld    class System.Web.UI.CompositeScriptReference System.Web.UI.CompositeScriptReferenceEventArgs::_compositeScript
0xfe5b  ret
```
