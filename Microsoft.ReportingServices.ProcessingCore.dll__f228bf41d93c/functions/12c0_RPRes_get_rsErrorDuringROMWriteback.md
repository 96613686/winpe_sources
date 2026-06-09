# RPRes::get_rsErrorDuringROMWriteback

- ea: `0x12c0`
- end: `0x12d5`
- name: `RPRes::get_rsErrorDuringROMWriteback`
- size: `21`
- prototype: ``
- caller_count: `46`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x56e80`
- `0x56fd0`
- `0x57160`
- `0x57850`
- `0x70f70`
- `0x70fe0`
- `0x747a0`
- `0x74970`
- `0x78cc0`
- `0x78db0`
- `0x78ea0`
- `0x7ded0`
- `0x7e070`
- `0x7e260`
- `0x80470`
- `0x80520`
- `0x805d0`
- `0x80690`
- `0x80750`
- `0x80810`
- `0x808d0`
- `0x80990`
- `0x80a60`
- `0x80b30`
- `0x80c00`
- `0x80cd0`
- `0x80d90`
- `0x80e50`
- `0x80f20`
- `0x80fe0`
- `0x81090`
- `0x81150`
- `0x81210`
- `0x812c0`
- `0x81370`
- `0x81420`
- `0x814d0`
- `0x81580`
- `0x81630`
- `0x816f0`
- `0x817c0`
- `0x81880`
- `0x81930`
- `0x828d0`
- `0x829c0`
- `0x82b00`

## callees

- `0x2f0`

## string_xrefs

- `0x12c5`: `rsErrorDuringROMWriteback`

## pseudocode

```c

```

## disassembly

```asm
0x12c0  call     class [mscorlib]System.Resources.ResourceManager RPRes::get_ResourceManager()
0x12c5  ldstr    aRserrorduringr_0// "rsErrorDuringROMWriteback"
0x12ca  ldsfld   class [mscorlib]System.Globalization.CultureInfo RPRes::resourceCulture
0x12cf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x12d4  ret
```
