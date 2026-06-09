# Microsoft.VisualStudio.Setup.Extensions::CompressSigners

- ea: `0x57f0`
- end: `0x5887`
- name: `Microsoft.VisualStudio.Setup.Extensions::CompressSigners`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x8c50`

## callees

- `0x57f0`
- `0x8280`
- `0xadc0`
- `0xadd0`
- `0xbcb0`
- `0xc1a0`

## pseudocode

```c

```

## disassembly

```asm
0x57f0  ldarg.0
0x57f1  ldstr    aItem// "item"
0x57f6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x57fb  ldarg.1
0x57fc  ldstr    aLookup// "lookup"
0x5801  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x5806  ldarg.0
0x5807  isinst   Microsoft.VisualStudio.Setup.IPayloads
0x580c  dup
0x580d  brtrue.s loc_5813
0x580f  pop
0x5810  ldnull
0x5811  br.s     loc_5818
0x5813  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Payload> Microsoft.VisualStudio.Setup.IPayloads::get_Payloads()
0x5818  stloc.0
0x5819  ldloc.0
0x581a  call     T0x2B00001E
0x581f  brfalse.s loc_5822
0x5821  ret
0x5822  ldloc.0
0x5823  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Payload>::GetEnumerator()
0x5828  stloc.1
0x5829  br.s     loc_5872
0x582b  ldloc.1
0x582c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Payload>::get_Current()
0x5831  stloc.2
0x5832  ldloc.2
0x5833  callvirt instance class Microsoft.VisualStudio.Setup.Signer Microsoft.VisualStudio.Setup.Payload::get_Signer()
0x5838  dup
0x5839  brtrue.s loc_583F
0x583b  pop
0x583c  ldnull
0x583d  br.s     loc_5844
0x583f  call     instance string Microsoft.VisualStudio.Setup.Signer::get_SubjectName()
0x5844  stloc.3
0x5845  ldloc.3
0x5846  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x584b  brtrue.s loc_5872
0x584d  ldarg.1
0x584e  ldloc.3
0x584f  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Signer>::ContainsKey(var<u1>)
0x5854  brfalse.s loc_5865
0x5856  ldloc.2
0x5857  ldarg.1
0x5858  ldloc.3
0x5859  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Signer>::get_Item(void)
0x585e  callvirt instance void Microsoft.VisualStudio.Setup.Payload::set_Signer(class Microsoft.VisualStudio.Setup.Signer value)
0x5863  br.s     loc_5872
0x5865  ldarg.1
0x5866  ldloc.3
0x5867  ldloc.2
0x5868  callvirt instance class Microsoft.VisualStudio.Setup.Signer Microsoft.VisualStudio.Setup.Payload::get_Signer()
0x586d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Signer>::Add(var<u1>, !!T0)
0x5872  ldloc.1
0x5873  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5878  brtrue.s loc_582B
0x587a  leave.s  loc_5886
0x587c  ldloc.1
0x587d  brfalse.s loc_5885
0x587f  ldloc.1
0x5880  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5885  endfinally
0x5886  ret
```
