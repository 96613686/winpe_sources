# System.Xml.Xsl.Qil.QilPatternFactory::Loop

- ea: `0x38120`
- end: `0x38141`
- name: `System.Xml.Xsl.Qil.QilPatternFactory::Loop`
- size: `33`
- prototype: ``
- caller_count: `39`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x148d0`
- `0x15aa0`
- `0x165a0`
- `0x17280`
- `0x18290`
- `0x18510`
- `0x18750`
- `0x18860`
- `0x18ac0`
- `0x19030`
- `0x19200`
- `0x193a0`
- `0x194f0`
- `0x195f0`
- `0x198c0`
- `0x19e80`
- `0x1a790`
- `0x1b310`
- `0x1b460`
- `0x1b580`
- `0x1b7d0`
- `0x1b960`
- `0x1b9e0`
- `0x1bba0`
- `0x1d0b0`
- `0x27310`
- `0x279e0`
- `0x27ac0`
- `0x27b40`
- `0x28030`
- `0x28080`
- `0x280d0`
- `0x281a0`
- `0x281f0`
- `0x295c0`
- `0x298a0`
- `0x29b80`
- `0x55fb0`
- `0x56140`

## callees

- `0x367f0`
- `0x37100`
- `0x38120`

## pseudocode

```c

```

## disassembly

```asm
0x38120  ldarg.0
0x38121  ldfld    bool System.Xml.Xsl.Qil.QilPatternFactory::debug
0x38126  brtrue.s loc_38133
0x38128  ldarg.2
0x38129  ldarg.1
0x3812a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilIterator::get_Binding()
0x3812f  bne.un.s loc_38133
0x38131  ldarg.2
0x38132  ret
0x38133  ldarg.0
0x38134  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilPatternFactory::f
0x38139  ldarg.1
0x3813a  ldarg.2
0x3813b  callvirt instance class System.Xml.Xsl.Qil.QilLoop System.Xml.Xsl.Qil.QilFactory::Loop(class System.Xml.Xsl.Qil.QilNode variable, class System.Xml.Xsl.Qil.QilNode body)
0x38140  ret
```
