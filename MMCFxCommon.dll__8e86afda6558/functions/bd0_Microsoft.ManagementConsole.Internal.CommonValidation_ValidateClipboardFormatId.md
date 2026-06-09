# Microsoft.ManagementConsole.Internal.CommonValidation::ValidateClipboardFormatId

- ea: `0xbd0`
- end: `0xbf1`
- name: `Microsoft.ManagementConsole.Internal.CommonValidation::ValidateClipboardFormatId`
- size: `33`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xc20`
- `0xcd0`
- `0x1ec0`
- `0x1f60`
- `0x2a90`
- `0x2ea0`

## callees

- `0x70`
- `0x290`
- `0xbd0`

## pseudocode

```c

```

## disassembly

```asm
0xbd0  ldarg.0
0xbd1  brfalse.s loc_BDB
0xbd3  ldarg.0
0xbd4  callvirt instance int32 [mscorlib]System.String::get_Length()
0xbd9  brtrue.s loc_BF0
0xbdb  call     string Microsoft.ManagementConsole.Internal.Strings::get_ExceptionSnapinDataNullClipboardId()
0xbe0  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0xbe5  ldstr    aClipboardforma// "clipboardFormatId"
0xbea  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xbef  throw
0xbf0  ret
```
