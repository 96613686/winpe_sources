# Microsoft.ManagementConsole.Internal.Utility::LoadResourceString

- ea: `0x8440`
- end: `0x8461`
- name: `Microsoft.ManagementConsole.Internal.Utility::LoadResourceString`
- size: `33`
- prototype: ``
- caller_count: `74`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x710`
- `0xa80`
- `0xb40`
- `0xd20`
- `0xd60`
- `0xe00`
- `0x10b0`
- `0x1230`
- `0x1350`
- `0x1d40`
- `0x20d0`
- `0x2120`
- `0x2d20`
- `0x2e60`
- `0x3ae0`
- `0x3ff0`
- `0x4340`
- `0x4680`
- `0x48d0`
- `0x4900`
- `0x4a60`
- `0x4aa0`
- `0x5020`
- `0x5280`
- `0x5300`
- `0x55c0`
- `0x60b0`
- `0x6160`
- `0x6630`
- `0x66d0`
- `0x6b30`
- `0x6f10`
- `0x6fc0`
- `0x70d0`
- `0x7140`
- `0x7410`
- `0x79b0`
- `0x8370`
- `0x8470`
- `0x95b0`
- `0x96c0`
- `0x9880`
- `0xaf50`
- `0xb020`
- `0xb190`
- `0xb220`
- `0xb470`
- `0xb540`
- `0xb5b0`
- `0xb720`

## callees

- `0x80`
- `0x8430`
- `0x8440`

## pseudocode

```c

```

## disassembly

```asm
0x8440  call     class [mscorlib]System.Resources.ResourceManager Microsoft.ManagementConsole.Internal.Utility::get_Resources()
0x8445  ldarg.0
0x8446  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x844b  stloc.0
0x844c  ldloc.0
0x844d  brtrue.s loc_845F
0x844f  call     class [mscorlib]System.Resources.ResourceManager Microsoft.ManagementConsole.Internal.Utility::get_Resources()
0x8454  call     string Microsoft.ManagementConsole.Internal.Strings::get_InvalidResourceName()
0x8459  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x845e  stloc.0
0x845f  ldloc.0
0x8460  ret
```
