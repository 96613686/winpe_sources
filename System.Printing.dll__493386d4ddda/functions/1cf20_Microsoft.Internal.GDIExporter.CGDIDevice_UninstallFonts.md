# Microsoft.Internal.GDIExporter.CGDIDevice::UninstallFonts

- ea: `0x1cf20`
- end: `0x1cf65`
- name: `Microsoft.Internal.GDIExporter.CGDIDevice::UninstallFonts`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c9b0`

## callees

- `0x1cf20`
- `0x22d60`

## pseudocode

```c

```

## disassembly

```asm
0x1cf20  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Internal.GDIExporter.CGDIDevice::s_InstalledFonts
0x1cf25  brfalse.s loc_1CF64
0x1cf27  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.Internal.GDIExporter.CGDIDevice::s_InstalledFonts
0x1cf2c  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0x1cf31  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x1cf36  stloc.0
0x1cf37  ldloc.0
0x1cf38  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1cf3d  brfalse.s loc_1CF51
0x1cf3f  ldloc.0
0x1cf40  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1cf45  castclass Microsoft.Internal.GDIExporter.FontInfo
0x1cf4a  call     instance void Microsoft.Internal.GDIExporter.FontInfo::UninstallPrivate()
0x1cf4f  br.s     loc_1CF37
0x1cf51  leave.s  loc_1CF64
0x1cf53  ldloc.0
0x1cf54  isinst   [mscorlib]System.IDisposable
0x1cf59  stloc.1
0x1cf5a  ldloc.1
0x1cf5b  brfalse.s loc_1CF63
0x1cf5d  ldloc.1
0x1cf5e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1cf63  endfinally
0x1cf64  ret
```
