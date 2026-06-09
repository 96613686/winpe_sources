# System.Windows.AccessibilitySwitches::.cctor

- ea: `0x2f4a0`
- end: `0x2f4e0`
- name: `System.Windows.AccessibilitySwitches::.cctor`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x2f4b4`: `UseNetFx47CompatibleAccessibilityFeatures`
- `0x2f4bc`: `UseNetFx471CompatibleAccessibilityFeatures`
- `0x2f4c4`: `UseNetFx472CompatibleAccessibilityFeatures`
- `0x2f4cc`: `UseNetFx48CompatibleAccessibilityFeatures`
- `0x2f4d4`: `UseNetFx48aCompatibleAccessibilityFeatures`

## pseudocode

```c

```

## disassembly

```asm
0x2f4a0  ldc.i4.0
0x2f4a1  stsfld   int32 System.Windows.AccessibilitySwitches::s_DefaultsSet
0x2f4a6  ldc.i4.0
0x2f4a7  stsfld   int32 System.Windows.AccessibilitySwitches::s_SwitchesVerified
0x2f4ac  ldc.i4.5
0x2f4ad  newarr   [mscorlib]System.String
0x2f4b2  dup
0x2f4b3  ldc.i4.0
0x2f4b4  ldstr    aUsenetfx47comp// "UseNetFx47CompatibleAccessibilityFeatur"...
0x2f4b9  stelem.ref
0x2f4ba  dup
0x2f4bb  ldc.i4.1
0x2f4bc  ldstr    aUsenetfx471com// "UseNetFx471CompatibleAccessibilityFeatu"...
0x2f4c1  stelem.ref
0x2f4c2  dup
0x2f4c3  ldc.i4.2
0x2f4c4  ldstr    aUsenetfx472com// "UseNetFx472CompatibleAccessibilityFeatu"...
0x2f4c9  stelem.ref
0x2f4ca  dup
0x2f4cb  ldc.i4.3
0x2f4cc  ldstr    aUsenetfx48comp// "UseNetFx48CompatibleAccessibilityFeatur"...
0x2f4d1  stelem.ref
0x2f4d2  dup
0x2f4d3  ldc.i4.4
0x2f4d4  ldstr    aUsenetfx48acom// "UseNetFx48aCompatibleAccessibilityFeatu"...
0x2f4d9  stelem.ref
0x2f4da  stsfld   string[] System.Windows.AccessibilitySwitches::AccessibilityPropertyNames
0x2f4df  ret
```
