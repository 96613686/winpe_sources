# MS.Internal.Printing.Configuration.FallbackPTProvider::Validate

- ea: `0xdd00`
- end: `0xdda5`
- name: `MS.Internal.Printing.Configuration.FallbackPTProvider::Validate`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0xdb20`

## callees

- `0xdd00`
- `0xde00`
- `0xde20`
- `0x14730`
- `0x18de0`
- `0x18e30`
- `0x18e40`
- `0x18ec0`
- `0x18ed0`
- `0x19150`
- `0x19160`
- `0x192b0`
- `0x19300`
- `0x1a130`

## pseudocode

```c

```

## disassembly

```asm
0xdd00  ldc.i4.0
0xdd01  stloc.0
0xdd02  ldarg.1
0xdd03  callvirt instance class MS.Internal.Printing.Configuration.DevMode MS.Internal.Printing.Configuration.DevMode::Clone()
0xdd08  stloc.1
0xdd09  ldarg.0
0xdd0a  ldarg.1
0xdd0b  callvirt instance unsigned int8[] MS.Internal.Printing.Configuration.DevMode::get_ByteData()
0xdd10  ldc.i4.1
0xdd11  call     instance void MS.Internal.Printing.Configuration.FallbackPTProvider::SetDocumentProperties(unsigned int8[] devModeBytes, bool biDirectional)
0xdd16  ldloc.1
0xdd17  ldc.i4.s 0xE
0xdd19  callvirt instance bool MS.Internal.Printing.Configuration.DevMode::IsAnyFieldSet(valuetype MS.Internal.Printing.Configuration.DevModeFields fields)
0xdd1e  brfalse.s loc_DD57
0xdd20  ldloc.1
0xdd21  dup
0xdd22  callvirt instance valuetype MS.Internal.Printing.Configuration.DevModeFields MS.Internal.Printing.Configuration.DevMode::get_Fields()
0xdd27  ldc.i4   0xFFFEFFFF
0xdd2c  and
0xdd2d  callvirt instance void MS.Internal.Printing.Configuration.DevMode::set_Fields(valuetype MS.Internal.Printing.Configuration.DevModeFields value)
0xdd32  ldloc.1
0xdd33  dup
0xdd34  callvirt instance valuetype MS.Internal.Printing.Configuration.DevModeFields MS.Internal.Printing.Configuration.DevMode::get_Fields()
0xdd39  ldarg.1
0xdd3a  callvirt instance valuetype MS.Internal.Printing.Configuration.DevModeFields MS.Internal.Printing.Configuration.DevMode::get_Fields()
0xdd3f  ldc.i4   0x10000
0xdd44  and
0xdd45  or
0xdd46  callvirt instance void MS.Internal.Printing.Configuration.DevMode::set_Fields(valuetype MS.Internal.Printing.Configuration.DevModeFields value)
0xdd4b  ldloc.1
0xdd4c  ldarg.1
0xdd4d  callvirt instance string MS.Internal.Printing.Configuration.DevMode::get_FormName()
0xdd52  callvirt instance void MS.Internal.Printing.Configuration.DevMode::set_FormName(string value)
0xdd57  ldloc.1
0xdd58  ldarg.1
0xdd59  callvirt instance string MS.Internal.Printing.Configuration.DevMode::get_DeviceName()
0xdd5e  callvirt instance void MS.Internal.Printing.Configuration.DevMode::set_DeviceName(string value)
0xdd63  ldc.i4.0
0xdd64  stloc.3
0xdd65  br.s     loc_DD7F
0xdd67  ldloc.1
0xdd68  callvirt instance unsigned int8[] MS.Internal.Printing.Configuration.DevMode::get_ByteData()
0xdd6d  ldloc.3
0xdd6e  ldelem.u1
0xdd6f  ldarg.1
0xdd70  callvirt instance unsigned int8[] MS.Internal.Printing.Configuration.DevMode::get_ByteData()
0xdd75  ldloc.3
0xdd76  ldelem.u1
0xdd77  beq.s    loc_DD7B
0xdd79  ldc.i4.1
0xdd7a  stloc.0
0xdd7b  ldloc.3
0xdd7c  ldc.i4.1
0xdd7d  add
0xdd7e  stloc.3
0xdd7f  ldloc.3
0xdd80  ldloc.1
0xdd81  callvirt instance unsigned int8[] MS.Internal.Printing.Configuration.DevMode::get_ByteData()
0xdd86  ldlen
0xdd87  conv.i4
0xdd88  blt.s    loc_DD67
0xdd8a  ldarg.0
0xdd8b  ldnull
0xdd8c  call     instance class MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities MS.Internal.Printing.Configuration.FallbackPTProvider::GetCapabilities(class MS.Internal.Printing.Configuration.DevMode devMode)
0xdd91  stloc.2
0xdd92  ldarg.1
0xdd93  ldloc.2
0xdd94  call     bool MS.Internal.Printing.Configuration.PrintSchemaShim::PruneFeatures(class MS.Internal.Printing.Configuration.DevMode inDevMode, class MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities capabilities)
0xdd99  pop
0xdd9a  leave.s  loc_DDA3
0xdd9c  ldloc.2
0xdd9d  callvirt instance void MS.Internal.Printing.Configuration.WinSpoolPrinterCapabilities::Release()
0xdda2  endfinally
0xdda3  ldloc.0
0xdda4  ret
```
