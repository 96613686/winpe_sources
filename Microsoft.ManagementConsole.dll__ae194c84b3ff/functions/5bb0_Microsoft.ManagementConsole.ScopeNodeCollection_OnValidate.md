# Microsoft.ManagementConsole.ScopeNodeCollection::OnValidate

- ea: `0x5bb0`
- end: `0x5bed`
- name: `Microsoft.ManagementConsole.ScopeNodeCollection::OnValidate`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x100`
- `0x1480`
- `0x2e60`
- `0x5a00`
- `0x5bb0`
- `0x8530`

## pseudocode

```c

```

## disassembly

```asm
0x5bb0  ldarg.0
0x5bb1  ldarg.1
0x5bb2  ldarg.2
0x5bb3  call     instance void Microsoft.ManagementConsole.BaseCollection::OnValidate(object objectToValidate, bool testForDuplicate)
0x5bb8  ldarg.1
0x5bb9  castclass Microsoft.ManagementConsole.ScopeNode
0x5bbe  stloc.0
0x5bbf  ldarg.0
0x5bc0  call     instance class Microsoft.ManagementConsole.ScopeNode Microsoft.ManagementConsole.ScopeNodeCollection::get_ContainerNode()
0x5bc5  stloc.1
0x5bc6  br.s     loc_5BE9
0x5bc8  ldloc.0
0x5bc9  ldloc.1
0x5bca  bne.un.s loc_5BE2
0x5bcc  ldstr    aObjecttovalida// "objectToValidate"
0x5bd1  call     string Microsoft.ManagementConsole.Internal.Strings::get_ArgumentExceptionCircularReference()
0x5bd6  ldc.i4.0
0x5bd7  newarr   [mscorlib]System.Object
0x5bdc  call     class [mscorlib]System.ArgumentException Microsoft.ManagementConsole.Internal.Utility::CreateArgumentException(string name, string resourceName, object[] parms)
0x5be1  throw
0x5be2  ldloc.1
0x5be3  callvirt instance class Microsoft.ManagementConsole.ScopeNode Microsoft.ManagementConsole.ScopeNode::get_Parent()
0x5be8  stloc.1
0x5be9  ldloc.1
0x5bea  brtrue.s loc_5BC8
0x5bec  ret
```
