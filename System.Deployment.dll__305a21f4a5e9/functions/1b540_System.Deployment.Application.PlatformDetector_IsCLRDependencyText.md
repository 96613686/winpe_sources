# System.Deployment.Application.PlatformDetector::IsCLRDependencyText

- ea: `0x1b540`
- end: `0x1b560`
- name: `System.Deployment.Application.PlatformDetector::IsCLRDependencyText`
- size: `32`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1ba20`
- `0x25060`
- `0x26250`
- `0x26ea0`

## callees

- `0x1b540`

## string_xrefs

- `0x1b541`: `Microsoft-Windows-CLRCoreComp`
- `0x1b54f`: `Microsoft.Windows.CommonLanguageRuntime`

## pseudocode

```c

```

## disassembly

```asm
0x1b540  ldarg.0
0x1b541  ldstr    aMicrosoftWindo// "Microsoft-Windows-CLRCoreComp"
0x1b546  ldc.i4.5
0x1b547  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1b54c  brfalse.s loc_1B55C
0x1b54e  ldarg.0
0x1b54f  ldstr    aMicrosoftWindo_0// "Microsoft.Windows.CommonLanguageRuntime"
0x1b554  ldc.i4.5
0x1b555  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1b55a  brtrue.s loc_1B55E
0x1b55c  ldc.i4.1
0x1b55d  ret
0x1b55e  ldc.i4.0
0x1b55f  ret
```
