# <ReadAsync>d__36::MoveNext

- ea: `0xf5360`
- end: `0xf5d11`
- name: `<ReadAsync>d__36::MoveNext`
- size: `2481`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config`

## callees

- `0xf280`
- `0x128e0`
- `0x1ab30`
- `0x1ab40`
- `0x1ab50`
- `0x1ab80`
- `0x1ab90`
- `0x1abc0`
- `0x1ad70`
- `0x214b0`
- `0x214c0`
- `0x21500`
- `0x21520`
- `0x21540`
- `0x21b60`
- `0x21c20`
- `0x21c30`
- `0x21c40`
- `0x21c90`
- `0x22fb0`
- `0x23140`
- `0xf5360`

## string_xrefs

- `0xf5b0f`: `Xml_InvalidCharacter`
- `0xf56a8`: `Xml_DtdIsProhibitedEx`
- `0xf5a07`: `Xml_DtdIsProhibitedEx`

## pseudocode

```c

```

## disassembly

```asm
0xf5360  ldarg.0
0xf5361  ldfld    int32 <ReadAsync>d__36::<>1__state
0xf5366  stloc.0
0xf5367  ldarg.0
0xf5368  ldfld    class System.Xml.XmlCharCheckingReader <ReadAsync>d__36::<>4__this
0xf536d  stloc.1
0xf536e  ldloc.0
0xf536f  switch   loc_F542E, loc_F54A2, loc_F5577, loc_F55F4, loc_F5671, loc_F5706, loc_F5863, loc_F5903, loc_F59AF, loc_F5A66, loc_F5B74, loc_F5BF7, loc_F5C7F
0xf53a8  ldloc.1
0xf53a9  ldfld    valuetype State System.Xml.XmlCharCheckingReader::state
0xf53ae  stloc.3
0xf53af  ldloc.3
0xf53b0  switch   loc_F53CA, loc_F53EA, loc_F53E3, loc_F5459
0xf53c5  br       loc_F54D3
0xf53ca  ldloc.1
0xf53cb  ldc.i4.3
0xf53cc  stfld    valuetype State System.Xml.XmlCharCheckingReader::state
0xf53d1  ldloc.1
0xf53d2  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0xf53d7  callvirt instance valuetype System.Xml.ReadState System.Xml.XmlReader::get_ReadState()
0xf53dc  brtrue   loc_F54DA
0xf53e1  br.s     loc_F5459
0xf53e3  ldc.i4.0
0xf53e4  stloc.2
0xf53e5  leave    loc_F5CFC
0xf53ea  ldloc.1
0xf53eb  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlCharCheckingReader::FinishReadBinaryAsync()
0xf53f0  ldc.i4.0
0xf53f1  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0xf53f6  stloc.s  5
0xf53f8  ldloca.s 5
0xf53fa  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0xf53ff  stloc.s  4
0xf5401  ldloca.s 4
0xf5403  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0xf5408  brtrue.s loc_F544B
0xf540a  ldarg.0
0xf540b  ldc.i4.0
0xf540c  dup
0xf540d  stloc.0
0xf540e  stfld    int32 <ReadAsync>d__36::<>1__state
0xf5413  ldarg.0
0xf5414  ldloc.s  4
0xf5416  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ReadAsync>d__36::<>u__1
0xf541b  ldarg.0
0xf541c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ReadAsync>d__36::<>t__builder
0xf5421  ldloca.s 4
0xf5423  ldarg.0
0xf5424  call     T0x2B000176
0xf5429  leave    loc_F5D10
0xf542e  ldarg.0
0xf542f  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ReadAsync>d__36::<>u__1
0xf5434  stloc.s  4
0xf5436  ldarg.0
0xf5437  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ReadAsync>d__36::<>u__1
0xf543c  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0xf5442  ldarg.0
0xf5443  ldc.i4.m1
0xf5444  dup
0xf5445  stloc.0
0xf5446  stfld    int32 <ReadAsync>d__36::<>1__state
0xf544b  ldloca.s 4
0xf544d  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0xf5452  ldloc.1
0xf5453  ldc.i4.3
0xf5454  stfld    valuetype State System.Xml.XmlCharCheckingReader::state
0xf5459  ldloc.1
0xf545a  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0xf545f  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlReader::ReadAsync()
0xf5464  ldc.i4.0
0xf5465  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0xf546a  stloc.s  8
0xf546c  ldloca.s 8
0xf546e  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0xf5473  stloc.s  7
0xf5475  ldloca.s 7
0xf5477  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0xf547c  brtrue.s loc_F54BF
0xf547e  ldarg.0
0xf547f  ldc.i4.1
0xf5480  dup
0xf5481  stloc.0
0xf5482  stfld    int32 <ReadAsync>d__36::<>1__state
0xf5487  ldarg.0
0xf5488  ldloc.s  7
0xf548a  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ReadAsync>d__36::<>u__2
0xf548f  ldarg.0
0xf5490  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ReadAsync>d__36::<>t__builder
0xf5495  ldloca.s 7
0xf5497  ldarg.0
0xf5498  call     T0x2B000177
0xf549d  leave    loc_F5D10
0xf54a2  ldarg.0
0xf54a3  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ReadAsync>d__36::<>u__2
0xf54a8  stloc.s  7
0xf54aa  ldarg.0
0xf54ab  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ReadAsync>d__36::<>u__2
0xf54b0  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>
0xf54b6  ldarg.0
0xf54b7  ldc.i4.m1
0xf54b8  dup
0xf54b9  stloc.0
0xf54ba  stfld    int32 <ReadAsync>d__36::<>1__state
0xf54bf  ldloca.s 7
0xf54c1  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0xf54c6  stloc.s  6
0xf54c8  ldloc.s  6
0xf54ca  brtrue.s loc_F54DA
0xf54cc  ldc.i4.0
0xf54cd  stloc.2
0xf54ce  leave    loc_F5CFC
0xf54d3  ldc.i4.0
0xf54d4  stloc.2
0xf54d5  leave    loc_F5CFC
0xf54da  ldarg.0
0xf54db  ldloc.1
0xf54dc  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0xf54e1  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0xf54e6  stfld    valuetype System.Xml.XmlNodeType <ReadAsync>d__36::<nodeType>5__2
0xf54eb  ldloc.1
0xf54ec  ldfld    bool System.Xml.XmlCharCheckingReader::checkCharacters
0xf54f1  brtrue   loc_F573B
0xf54f6  ldarg.0
0xf54f7  ldfld    valuetype System.Xml.XmlNodeType <ReadAsync>d__36::<nodeType>5__2
0xf54fc  stloc.s  9
0xf54fe  ldloc.s  9
0xf5500  ldc.i4.7
0xf5501  sub
0xf5502  switch   loc_F5622, loc_F5528, loc_F5734, loc_F569F, loc_F5734, loc_F5734, loc_F55A5
0xf5523  br       loc_F5734
0xf5528  ldloc.1
0xf5529  ldfld    bool System.Xml.XmlCharCheckingReader::ignoreComments
0xf552e  brfalse  loc_F5734
0xf5533  ldloc.1
0xf5534  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlReader::ReadAsync()
0xf5539  ldc.i4.0
0xf553a  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0xf553f  stloc.s  8
0xf5541  ldloca.s 8
0xf5543  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0xf5548  stloc.s  0xB
0xf554a  ldloca.s 0xB
0xf554c  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0xf5551  brtrue.s loc_F5594
0xf5553  ldarg.0
0xf5554  ldc.i4.2
0xf5555  dup
0xf5556  stloc.0
0xf5557  stfld    int32 <ReadAsync>d__36::<>1__state
0xf555c  ldarg.0
0xf555d  ldloc.s  0xB
0xf555f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ReadAsync>d__36::<>u__2
0xf5564  ldarg.0
0xf5565  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ReadAsync>d__36::<>t__builder
0xf556a  ldloca.s 0xB
0xf556c  ldarg.0
0xf556d  call     T0x2B000177
0xf5572  leave    loc_F5D10
0xf5577  ldarg.0
0xf5578  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ReadAsync>d__36::<>u__2
0xf557d  stloc.s  0xB
0xf557f  ldarg.0
0xf5580  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ReadAsync>d__36::<>u__2
0xf5585  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>
0xf558b  ldarg.0
0xf558c  ldc.i4.m1
0xf558d  dup
0xf558e  stloc.0
0xf558f  stfld    int32 <ReadAsync>d__36::<>1__state
0xf5594  ldloca.s 0xB
0xf5596  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0xf559b  stloc.s  0xA
0xf559d  ldloc.s  0xA
0xf559f  stloc.2
0xf55a0  leave    loc_F5CFC
0xf55a5  ldloc.1
0xf55a6  ldfld    bool System.Xml.XmlCharCheckingReader::ignoreWhitespace
0xf55ab  brfalse  loc_F5734
0xf55b0  ldloc.1
0xf55b1  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlReader::ReadAsync()
0xf55b6  ldc.i4.0
0xf55b7  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0xf55bc  stloc.s  8
0xf55be  ldloca.s 8
0xf55c0  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0xf55c5  stloc.s  0xD
0xf55c7  ldloca.s 0xD
0xf55c9  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0xf55ce  brtrue.s loc_F5611
0xf55d0  ldarg.0
0xf55d1  ldc.i4.3
0xf55d2  dup
0xf55d3  stloc.0
0xf55d4  stfld    int32 <ReadAsync>d__36::<>1__state
0xf55d9  ldarg.0
0xf55da  ldloc.s  0xD
0xf55dc  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ReadAsync>d__36::<>u__2
0xf55e1  ldarg.0
0xf55e2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ReadAsync>d__36::<>t__builder
0xf55e7  ldloca.s 0xD
0xf55e9  ldarg.0
0xf55ea  call     T0x2B000177
0xf55ef  leave    loc_F5D10
0xf55f4  ldarg.0
0xf55f5  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ReadAsync>d__36::<>u__2
0xf55fa  stloc.s  0xD
0xf55fc  ldarg.0
0xf55fd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ReadAsync>d__36::<>u__2
0xf5602  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>
0xf5608  ldarg.0
0xf5609  ldc.i4.m1
0xf560a  dup
0xf560b  stloc.0
0xf560c  stfld    int32 <ReadAsync>d__36::<>1__state
0xf5611  ldloca.s 0xD
0xf5613  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0xf5618  stloc.s  0xC
0xf561a  ldloc.s  0xC
0xf561c  stloc.2
0xf561d  leave    loc_F5CFC
0xf5622  ldloc.1
0xf5623  ldfld    bool System.Xml.XmlCharCheckingReader::ignorePis
0xf5628  brfalse  loc_F5734
0xf562d  ldloc.1
0xf562e  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlReader::ReadAsync()
0xf5633  ldc.i4.0
0xf5634  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0xf5639  stloc.s  8
0xf563b  ldloca.s 8
0xf563d  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0xf5642  stloc.s  0xF
0xf5644  ldloca.s 0xF
0xf5646  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0xf564b  brtrue.s loc_F568E
0xf564d  ldarg.0
0xf564e  ldc.i4.4
0xf564f  dup
0xf5650  stloc.0
0xf5651  stfld    int32 <ReadAsync>d__36::<>1__state
0xf5656  ldarg.0
0xf5657  ldloc.s  0xF
0xf5659  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ReadAsync>d__36::<>u__2
0xf565e  ldarg.0
0xf565f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ReadAsync>d__36::<>t__builder
0xf5664  ldloca.s 0xF
0xf5666  ldarg.0
0xf5667  call     T0x2B000177
0xf566c  leave    loc_F5D10
0xf5671  ldarg.0
0xf5672  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ReadAsync>d__36::<>u__2
0xf5677  stloc.s  0xF
0xf5679  ldarg.0
0xf567a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ReadAsync>d__36::<>u__2
0xf567f  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>
0xf5685  ldarg.0
0xf5686  ldc.i4.m1
0xf5687  dup
0xf5688  stloc.0
0xf5689  stfld    int32 <ReadAsync>d__36::<>1__state
0xf568e  ldloca.s 0xF
0xf5690  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0xf5695  stloc.s  0xE
0xf5697  ldloc.s  0xE
0xf5699  stloc.2
0xf569a  leave    loc_F5CFC
0xf569f  ldloc.1
0xf56a0  ldfld    valuetype System.Xml.DtdProcessing System.Xml.XmlCharCheckingReader::dtdProcessing
0xf56a5  brtrue.s loc_F56B9
0xf56a7  ldloc.1
0xf56a8  ldstr    aXmlDtdisprohib// "Xml_DtdIsProhibitedEx"
0xf56ad  ldsfld   string [mscorlib]System.String::Empty
0xf56b2  call     instance void System.Xml.XmlCharCheckingReader::Throw(string res, string arg)
0xf56b7  br.s     loc_F5734
0xf56b9  ldloc.1
0xf56ba  ldfld    valuetype System.Xml.DtdProcessing System.Xml.XmlCharCheckingReader::dtdProcessing
0xf56bf  ldc.i4.1
0xf56c0  bne.un.s loc_F5734
0xf56c2  ldloc.1
0xf56c3  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlReader::ReadAsync()
0xf56c8  ldc.i4.0
0xf56c9  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0xf56ce  stloc.s  8
0xf56d0  ldloca.s 8
0xf56d2  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0xf56d7  stloc.s  0x11
0xf56d9  ldloca.s 0x11
0xf56db  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0xf56e0  brtrue.s loc_F5723
0xf56e2  ldarg.0
0xf56e3  ldc.i4.5
0xf56e4  dup
0xf56e5  stloc.0
0xf56e6  stfld    int32 <ReadAsync>d__36::<>1__state
0xf56eb  ldarg.0
0xf56ec  ldloc.s  0x11
0xf56ee  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ReadAsync>d__36::<>u__2
0xf56f3  ldarg.0
0xf56f4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ReadAsync>d__36::<>t__builder
0xf56f9  ldloca.s 0x11
0xf56fb  ldarg.0
  ... truncated ...
```
