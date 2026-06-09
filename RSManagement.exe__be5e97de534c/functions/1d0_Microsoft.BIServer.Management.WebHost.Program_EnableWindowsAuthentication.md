# Microsoft.BIServer.Management.WebHost.Program::EnableWindowsAuthentication

- ea: `0x1d0`
- end: `0x1ec`
- name: `Microsoft.BIServer.Management.WebHost.Program::EnableWindowsAuthentication`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1b0`

## pseudocode

```c

```

## disassembly

```asm
0x1d0  ldarg.0
0x1d1  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Owin]Owin.IAppBuilder::get_Properties()
0x1d6  ldstr    aSystemNetHttpl// "System.Net.HttpListener"
0x1db  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0x1e0  castclass [System]System.Net.HttpListener
0x1e5  ldc.i4.4
0x1e6  callvirt instance void [System]System.Net.HttpListener::set_AuthenticationSchemes(valuetype [System]System.Net.AuthenticationSchemes)
0x1eb  ret
```
