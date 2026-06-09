# System.Windows.DependencyProperty::VerifyReadOnlyKey

- ea: `0x32f30`
- end: `0x32f4a`
- name: `System.Windows.DependencyProperty::VerifyReadOnlyKey`
- size: `26`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x300a0`
- `0x32a60`

## callees

- `0x2c100`
- `0x32f30`

## string_xrefs

- `0x32f39`: `ReadOnlyKeyNotAuthorized`

## pseudocode

```c

```

## disassembly

```asm
0x32f30  ldarg.0
0x32f31  ldfld    class System.Windows.DependencyPropertyKey System.Windows.DependencyProperty::_readOnlyKey
0x32f36  ldarg.1
0x32f37  beq.s    loc_32F49
0x32f39  ldstr    aReadonlykeynot// "ReadOnlyKeyNotAuthorized"
0x32f3e  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x32f43  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x32f48  throw
0x32f49  ret
```
