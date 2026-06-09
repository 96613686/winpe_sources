# <ParseSubsetAsync>d__160::MoveNext

- ea: `0x11a110`
- end: `0x11a73a`
- name: `<ParseSubsetAsync>d__160::MoveNext`
- size: `1578`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5c5e0`
- `0x609b0`
- `0x60cd0`
- `0x60de0`
- `0x60f10`
- `0x612c0`
- `0x613a0`
- `0x614c0`
- `0x61500`
- `0x61540`
- `0x61580`
- `0x615c0`
- `0x61650`
- `0xc9b80`
- `0x11a110`

## string_xrefs

- `0x11a499`: `Xml_InvalidConditionalSection`
- `0x11a57b`: `Xml_UnexpectedCDataEnd`
- `0x11a5a4`: `Xml_UnclosedConditionalSection`
- `0x11a6ab`: `Xml_UnclosedConditionalSection`
- `0x11a66c`: `Xml_ExpectDtdMarkup`
- `0x11a692`: `Xml_IncompleteDtdContent`

## pseudocode

```c

```

## disassembly

```asm
0x11a110  ldarg.0
0x11a111  ldfld    int32 <ParseSubsetAsync>d__160::<>1__state
0x11a116  stloc.0
0x11a117  ldarg.0
0x11a118  ldfld    class System.Xml.DtdParser <ParseSubsetAsync>d__160::<>4__this
0x11a11d  stloc.1
0x11a11e  ldloc.0
0x11a11f  switch   loc_11A18D, loc_11A23E, loc_11A2AB, loc_11A318, loc_11A385, loc_11A3F2, loc_11A45F, loc_11A4E7, loc_11A626
0x11a148  ldloc.1
0x11a149  ldc.i4.0
0x11a14a  call     instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token> System.Xml.DtdParser::GetTokenAsync(bool needWhiteSpace)
0x11a14f  ldc.i4.0
0x11a150  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token>::ConfigureAwait(!!T0)
0x11a155  stloc.s  5
0x11a157  ldloca.s 5
0x11a159  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<valuetype Token>::GetAwaiter()
0x11a15e  stloc.s  4
0x11a160  ldloca.s 4
0x11a162  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>::get_IsCompleted()
0x11a167  brtrue.s loc_11A1AA
0x11a169  ldarg.0
0x11a16a  ldc.i4.0
0x11a16b  dup
0x11a16c  stloc.0
0x11a16d  stfld    int32 <ParseSubsetAsync>d__160::<>1__state
0x11a172  ldarg.0
0x11a173  ldloc.s  4
0x11a175  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ParseSubsetAsync>d__160::<>u__1
0x11a17a  ldarg.0
0x11a17b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ParseSubsetAsync>d__160::<>t__builder
0x11a180  ldloca.s 4
0x11a182  ldarg.0
0x11a183  call     T0x2B0002A7
0x11a188  leave    loc_11A739
0x11a18d  ldarg.0
0x11a18e  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ParseSubsetAsync>d__160::<>u__1
0x11a193  stloc.s  4
0x11a195  ldarg.0
0x11a196  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ParseSubsetAsync>d__160::<>u__1
0x11a19b  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>
0x11a1a1  ldarg.0
0x11a1a2  ldc.i4.m1
0x11a1a3  dup
0x11a1a4  stloc.0
0x11a1a5  stfld    int32 <ParseSubsetAsync>d__160::<>1__state
0x11a1aa  ldloca.s 4
0x11a1ac  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>::GetResult()
0x11a1b1  stloc.3
0x11a1b2  ldloc.3
0x11a1b3  stloc.2
0x11a1b4  ldarg.0
0x11a1b5  ldloc.1
0x11a1b6  ldfld    int32 System.Xml.DtdParser::currentEntityId
0x11a1bb  stfld    int32 <ParseSubsetAsync>d__160::<startTagEntityId>5__2
0x11a1c0  ldloc.2
0x11a1c1  ldc.i4.s 0xB
0x11a1c3  sub
0x11a1c4  switch   loc_11A1FA, loc_11A267, loc_11A2D4, loc_11A341, loc_11A3AE, loc_11A41B, loc_11A488, loc_11A51C, loc_11A67B
0x11a1ed  ldloc.2
0x11a1ee  ldc.i4.s 0x20
0x11a1f0  beq      loc_11A58A
0x11a1f5  br       loc_11A6B7
0x11a1fa  ldloc.1
0x11a1fb  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.DtdParser::ParseAttlistDeclAsync()
0x11a200  ldc.i4.0
0x11a201  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x11a206  stloc.s  7
0x11a208  ldloca.s 7
0x11a20a  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x11a20f  stloc.s  6
0x11a211  ldloca.s 6
0x11a213  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x11a218  brtrue.s loc_11A25B
0x11a21a  ldarg.0
0x11a21b  ldc.i4.1
0x11a21c  dup
0x11a21d  stloc.0
0x11a21e  stfld    int32 <ParseSubsetAsync>d__160::<>1__state
0x11a223  ldarg.0
0x11a224  ldloc.s  6
0x11a226  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a22b  ldarg.0
0x11a22c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ParseSubsetAsync>d__160::<>t__builder
0x11a231  ldloca.s 6
0x11a233  ldarg.0
0x11a234  call     T0x2B0002A8
0x11a239  leave    loc_11A739
0x11a23e  ldarg.0
0x11a23f  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a244  stloc.s  6
0x11a246  ldarg.0
0x11a247  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a24c  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x11a252  ldarg.0
0x11a253  ldc.i4.m1
0x11a254  dup
0x11a255  stloc.0
0x11a256  stfld    int32 <ParseSubsetAsync>d__160::<>1__state
0x11a25b  ldloca.s 6
0x11a25d  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x11a262  br       loc_11A6B7
0x11a267  ldloc.1
0x11a268  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.DtdParser::ParseElementDeclAsync()
0x11a26d  ldc.i4.0
0x11a26e  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x11a273  stloc.s  7
0x11a275  ldloca.s 7
0x11a277  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x11a27c  stloc.s  8
0x11a27e  ldloca.s 8
0x11a280  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x11a285  brtrue.s loc_11A2C8
0x11a287  ldarg.0
0x11a288  ldc.i4.2
0x11a289  dup
0x11a28a  stloc.0
0x11a28b  stfld    int32 <ParseSubsetAsync>d__160::<>1__state
0x11a290  ldarg.0
0x11a291  ldloc.s  8
0x11a293  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a298  ldarg.0
0x11a299  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ParseSubsetAsync>d__160::<>t__builder
0x11a29e  ldloca.s 8
0x11a2a0  ldarg.0
0x11a2a1  call     T0x2B0002A8
0x11a2a6  leave    loc_11A739
0x11a2ab  ldarg.0
0x11a2ac  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a2b1  stloc.s  8
0x11a2b3  ldarg.0
0x11a2b4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a2b9  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x11a2bf  ldarg.0
0x11a2c0  ldc.i4.m1
0x11a2c1  dup
0x11a2c2  stloc.0
0x11a2c3  stfld    int32 <ParseSubsetAsync>d__160::<>1__state
0x11a2c8  ldloca.s 8
0x11a2ca  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x11a2cf  br       loc_11A6B7
0x11a2d4  ldloc.1
0x11a2d5  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.DtdParser::ParseEntityDeclAsync()
0x11a2da  ldc.i4.0
0x11a2db  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x11a2e0  stloc.s  7
0x11a2e2  ldloca.s 7
0x11a2e4  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x11a2e9  stloc.s  9
0x11a2eb  ldloca.s 9
0x11a2ed  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x11a2f2  brtrue.s loc_11A335
0x11a2f4  ldarg.0
0x11a2f5  ldc.i4.3
0x11a2f6  dup
0x11a2f7  stloc.0
0x11a2f8  stfld    int32 <ParseSubsetAsync>d__160::<>1__state
0x11a2fd  ldarg.0
0x11a2fe  ldloc.s  9
0x11a300  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a305  ldarg.0
0x11a306  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ParseSubsetAsync>d__160::<>t__builder
0x11a30b  ldloca.s 9
0x11a30d  ldarg.0
0x11a30e  call     T0x2B0002A8
0x11a313  leave    loc_11A739
0x11a318  ldarg.0
0x11a319  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a31e  stloc.s  9
0x11a320  ldarg.0
0x11a321  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a326  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x11a32c  ldarg.0
0x11a32d  ldc.i4.m1
0x11a32e  dup
0x11a32f  stloc.0
0x11a330  stfld    int32 <ParseSubsetAsync>d__160::<>1__state
0x11a335  ldloca.s 9
0x11a337  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x11a33c  br       loc_11A6B7
0x11a341  ldloc.1
0x11a342  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.DtdParser::ParseNotationDeclAsync()
0x11a347  ldc.i4.0
0x11a348  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x11a34d  stloc.s  7
0x11a34f  ldloca.s 7
0x11a351  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x11a356  stloc.s  0xA
0x11a358  ldloca.s 0xA
0x11a35a  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x11a35f  brtrue.s loc_11A3A2
0x11a361  ldarg.0
0x11a362  ldc.i4.4
0x11a363  dup
0x11a364  stloc.0
0x11a365  stfld    int32 <ParseSubsetAsync>d__160::<>1__state
0x11a36a  ldarg.0
0x11a36b  ldloc.s  0xA
0x11a36d  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a372  ldarg.0
0x11a373  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ParseSubsetAsync>d__160::<>t__builder
0x11a378  ldloca.s 0xA
0x11a37a  ldarg.0
0x11a37b  call     T0x2B0002A8
0x11a380  leave    loc_11A739
0x11a385  ldarg.0
0x11a386  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a38b  stloc.s  0xA
0x11a38d  ldarg.0
0x11a38e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a393  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x11a399  ldarg.0
0x11a39a  ldc.i4.m1
0x11a39b  dup
0x11a39c  stloc.0
0x11a39d  stfld    int32 <ParseSubsetAsync>d__160::<>1__state
0x11a3a2  ldloca.s 0xA
0x11a3a4  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x11a3a9  br       loc_11A6B7
0x11a3ae  ldloc.1
0x11a3af  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.DtdParser::ParseCommentAsync()
0x11a3b4  ldc.i4.0
0x11a3b5  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x11a3ba  stloc.s  7
0x11a3bc  ldloca.s 7
0x11a3be  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x11a3c3  stloc.s  0xB
0x11a3c5  ldloca.s 0xB
0x11a3c7  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x11a3cc  brtrue.s loc_11A40F
0x11a3ce  ldarg.0
0x11a3cf  ldc.i4.5
0x11a3d0  dup
0x11a3d1  stloc.0
0x11a3d2  stfld    int32 <ParseSubsetAsync>d__160::<>1__state
0x11a3d7  ldarg.0
0x11a3d8  ldloc.s  0xB
0x11a3da  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a3df  ldarg.0
0x11a3e0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ParseSubsetAsync>d__160::<>t__builder
0x11a3e5  ldloca.s 0xB
0x11a3e7  ldarg.0
0x11a3e8  call     T0x2B0002A8
0x11a3ed  leave    loc_11A739
0x11a3f2  ldarg.0
0x11a3f3  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a3f8  stloc.s  0xB
0x11a3fa  ldarg.0
0x11a3fb  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a400  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x11a406  ldarg.0
0x11a407  ldc.i4.m1
0x11a408  dup
0x11a409  stloc.0
0x11a40a  stfld    int32 <ParseSubsetAsync>d__160::<>1__state
0x11a40f  ldloca.s 0xB
0x11a411  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x11a416  br       loc_11A6B7
0x11a41b  ldloc.1
0x11a41c  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.DtdParser::ParsePIAsync()
0x11a421  ldc.i4.0
0x11a422  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x11a427  stloc.s  7
0x11a429  ldloca.s 7
0x11a42b  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x11a430  stloc.s  0xC
0x11a432  ldloca.s 0xC
0x11a434  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x11a439  brtrue.s loc_11A47C
0x11a43b  ldarg.0
0x11a43c  ldc.i4.6
0x11a43d  dup
0x11a43e  stloc.0
0x11a43f  stfld    int32 <ParseSubsetAsync>d__160::<>1__state
0x11a444  ldarg.0
0x11a445  ldloc.s  0xC
0x11a447  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a44c  ldarg.0
0x11a44d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ParseSubsetAsync>d__160::<>t__builder
0x11a452  ldloca.s 0xC
0x11a454  ldarg.0
0x11a455  call     T0x2B0002A8
0x11a45a  leave    loc_11A739
0x11a45f  ldarg.0
0x11a460  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a465  stloc.s  0xC
0x11a467  ldarg.0
0x11a468  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseSubsetAsync>d__160::<>u__2
0x11a46d  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x11a473  ldarg.0
0x11a474  ldc.i4.m1
0x11a475  dup
0x11a476  stloc.0
0x11a477  stfld    int32 <ParseSubsetAsync>d__160::<>1__state
0x11a47c  ldloca.s 0xC
0x11a47e  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x11a483  br       loc_11A6B7
0x11a488  ldloc.1
0x11a489  call     instance bool System.Xml.DtdParser::get_ParsingInternalSubset()
0x11a48e  brfalse.s loc_11A4A3
0x11a490  ldloc.1
  ... truncated ...
```
