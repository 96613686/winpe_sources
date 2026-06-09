# Microsoft.ManagementConsole.Internal.Utility::CreateClassNotInitializedException

- ea: `0x8490`
- end: `0x84b0`
- name: `Microsoft.ManagementConsole.Internal.Utility::CreateClassNotInitializedException`
- size: `32`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xa000`
- `0xa050`
- `0xa0c0`
- `0xa390`
- `0xa3e0`
- `0xa430`
- `0xa7e0`
- `0xa830`
- `0xa880`
- `0xa8d0`
- `0xa970`
- `0xa9f0`
- `0xaed0`
- `0xafc0`
- `0xbdf0`
- `0xc1f0`
- `0xc4b0`
- `0xc590`
- `0xc690`
- `0xca50`

## callees

- `0xc0`
- `0x8470`

## pseudocode

```c

```

## disassembly

```asm
0x8490  call     string Microsoft.ManagementConsole.Internal.Strings::get_ExceptionClassNotInitialized()
0x8495  ldc.i4.2
0x8496  newarr   [mscorlib]System.Object
0x849b  stloc.0
0x849c  ldloc.0
0x849d  ldc.i4.0
0x849e  ldarg.0
0x849f  stelem.ref
0x84a0  ldloc.0
0x84a1  ldc.i4.1
0x84a2  ldarg.1
0x84a3  stelem.ref
0x84a4  ldloc.0
0x84a5  call     string Microsoft.ManagementConsole.Internal.Utility::FormatResourceString(string resourceName, object[] parms)
0x84aa  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x84af  ret
```
