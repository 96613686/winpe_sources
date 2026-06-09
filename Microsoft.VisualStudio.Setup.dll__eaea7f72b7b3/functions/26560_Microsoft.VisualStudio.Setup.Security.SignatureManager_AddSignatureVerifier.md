# Microsoft.VisualStudio.Setup.Security.SignatureManager::AddSignatureVerifier

- ea: `0x26560`
- end: `0x265de`
- name: `Microsoft.VisualStudio.Setup.Security.SignatureManager::AddSignatureVerifier`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x26470`

## callees

- `0x26560`
- `0x26c50`

## string_xrefs

- `0x26590`: `NullExtension`
- `0x265ac`: `extension is null in signature verifier`
- `0x265be`: `extension`

## pseudocode

```c

```

## disassembly

```asm
0x26560  ldarg.1
0x26561  brtrue.s loc_2656E
0x26563  ldstr    aVerifier// "verifier"
0x26568  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2656d  throw
0x2656e  ldarg.2
0x2656f  brtrue.s loc_265C9
0x26571  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x26576  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x2657b  stloc.1
0x2657c  dup
0x2657d  ldloc.1
0x2657e  ldstr    aSignaturemanag_3// "SignatureManager"
0x26583  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x26588  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x2658d  stloc.2
0x2658e  dup
0x2658f  ldloc.2
0x26590  ldstr    aNullextension// "NullExtension"
0x26595  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2659a  stloc.0
0x2659b  ldarg.0
0x2659c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Security.SignatureManager::telemetry
0x265a1  dup
0x265a2  brtrue.s loc_265A7
0x265a4  pop
0x265a5  br.s     loc_265BE
0x265a7  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x265ac  ldstr    aExtensionIsNul// "extension is null in signature verifier"
0x265b1  ldloc.0
0x265b2  ldnull
0x265b3  ldnull
0x265b4  ldc.i4.0
0x265b5  ldnull
0x265b6  ldc.i4.0
0x265b7  ldnull
0x265b8  ldc.i4.0
0x265b9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x265be  ldstr    aExtension// "extension"
0x265c3  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x265c8  throw
0x265c9  ldarga.s 2
0x265cb  call     void Microsoft.VisualStudio.Setup.Security.SignatureManager::NormalizeExtension(string& extension)
0x265d0  ldarg.0
0x265d1  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifier> Microsoft.VisualStudio.Setup.Security.SignatureManager::verifiers
0x265d6  ldarg.2
0x265d7  ldarg.1
0x265d8  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifier>::Add(var<u1>, !!T0)
0x265dd  ret
```
