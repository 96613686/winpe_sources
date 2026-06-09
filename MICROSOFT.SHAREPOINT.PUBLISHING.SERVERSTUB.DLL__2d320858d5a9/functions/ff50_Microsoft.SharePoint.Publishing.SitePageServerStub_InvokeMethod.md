# Microsoft.SharePoint.Publishing.SitePageServerStub::InvokeMethod

- ea: `0xff50`
- end: `0x10223`
- name: `Microsoft.SharePoint.Publishing.SitePageServerStub::InvokeMethod`
- size: `723`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0xfe40`
- `0xfe50`
- `0xfe60`
- `0xfe70`
- `0xfe80`
- `0xfe90`
- `0xfea0`
- `0xfeb0`
- `0xfed0`
- `0xfee0`
- `0xff00`
- `0xff20`
- `0xff30`
- `0xff50`

## string_xrefs

- `0xff9b`: `Delete`
- `0x10099`: `Delete`
- `0xfffb`: `Update`
- `0x1018b`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0xff50  ldarg.s  4
0xff52  brtrue.s loc_FF5F
0xff54  ldstr    aProxycontext// "proxyContext"
0xff59  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xff5e  throw
0xff5f  ldarg.1
0xff60  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage
0xff65  stloc.0
0xff66  ldloc.0
0xff67  brtrue.s loc_FF74
0xff69  ldstr    aTarget// "target"
0xff6e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xff73  throw
0xff74  ldarg.0
0xff75  ldarg.2
0xff76  ldarg.s  4
0xff78  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xff7d  starg.s  2
0xff7f  ldarg.2
0xff80  dup
0xff81  stloc.1
0xff82  brfalse  loc_10215
0xff87  volatile.
0xff89  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60002c7-1
0xff8e  brtrue   loc_10041
0xff93  ldc.i4.s 0xD
0xff95  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xff9a  dup
0xff9b  ldstr    aDelete// "Delete"
0xffa0  ldc.i4.0
0xffa1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xffa6  dup
0xffa7  ldstr    aCheckout// "CheckOut"
0xffac  ldc.i4.1
0xffad  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xffb2  dup
0xffb3  ldstr    aDiscardpage// "DiscardPage"
0xffb8  ldc.i4.2
0xffb9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xffbe  dup
0xffbf  ldstr    aCheckoutpage// "CheckoutPage"
0xffc4  ldc.i4.3
0xffc5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xffca  dup
0xffcb  ldstr    aPublish// "Publish"
0xffd0  ldc.i4.4
0xffd1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xffd6  dup
0xffd7  ldstr    aPromotetonews// "PromoteToNews"
0xffdc  ldc.i4.5
0xffdd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xffe2  dup
0xffe3  ldstr    aDemotefromnews// "DemoteFromNews"
0xffe8  ldc.i4.6
0xffe9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xffee  dup
0xffef  ldstr    aSavedraft// "SaveDraft"
0xfff4  ldc.i4.7
0xfff5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xfffa  dup
0xfffb  ldstr    aUpdate// "Update"
0x10000  ldc.i4.8
0x10001  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x10006  dup
0x10007  ldstr    aSavepage// "SavePage"
0x1000c  ldc.i4.s 9
0x1000e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x10013  dup
0x10014  ldstr    aSavepageasdraf// "SavePageAsDraft"
0x10019  ldc.i4.s 0xA
0x1001b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x10020  dup
0x10021  ldstr    aCopy// "Copy"
0x10026  ldc.i4.s 0xB
0x10028  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1002d  dup
0x1002e  ldstr    aSharepageprevi// "SharePagePreviewByEmail"
0x10033  ldc.i4.s 0xC
0x10035  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1003a  volatile.
0x1003c  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60002c7-1
0x10041  volatile.
0x10043  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60002c7-1
0x10048  ldloc.1
0x10049  ldloca.s 2
0x1004b  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x10050  brfalse  loc_10215
0x10055  ldloc.2
0x10056  switch   loc_10094, loc_100B0, loc_100D0, loc_100EB, loc_10106, loc_10126, loc_10146, loc_10166, loc_10186, loc_101A2, loc_101BE, loc_101DE, loc_101F9
0x1008f  br       loc_10215
0x10094  ldarg.s  5
0x10096  ldc.i4.1
0x10097  stind.i1
0x10098  ldarg.0
0x10099  ldstr    aDelete// "Delete"
0x1009e  ldarg.s  4
0x100a0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x100a5  ldloc.0
0x100a6  ldarg.3
0x100a7  ldarg.s  4
0x100a9  call     void Microsoft.SharePoint.Publishing.SitePageServerStub::Delete_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x100ae  ldnull
0x100af  ret
0x100b0  ldarg.s  5
0x100b2  ldc.i4.0
0x100b3  stind.i1
0x100b4  ldarg.0
0x100b5  ldstr    aCheckout// "CheckOut"
0x100ba  ldarg.s  4
0x100bc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x100c1  ldloc.0
0x100c2  ldarg.3
0x100c3  ldarg.s  4
0x100c5  call     bool Microsoft.SharePoint.Publishing.SitePageServerStub::CheckOut_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x100ca  box      [mscorlib]System.Boolean
0x100cf  ret
0x100d0  ldarg.s  5
0x100d2  ldc.i4.0
0x100d3  stind.i1
0x100d4  ldarg.0
0x100d5  ldstr    aDiscardpage// "DiscardPage"
0x100da  ldarg.s  4
0x100dc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x100e1  ldloc.0
0x100e2  ldarg.3
0x100e3  ldarg.s  4
0x100e5  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage Microsoft.SharePoint.Publishing.SitePageServerStub::DiscardPage_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x100ea  ret
0x100eb  ldarg.s  5
0x100ed  ldc.i4.0
0x100ee  stind.i1
0x100ef  ldarg.0
0x100f0  ldstr    aCheckoutpage// "CheckoutPage"
0x100f5  ldarg.s  4
0x100f7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x100fc  ldloc.0
0x100fd  ldarg.3
0x100fe  ldarg.s  4
0x10100  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage Microsoft.SharePoint.Publishing.SitePageServerStub::CheckoutPage_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10105  ret
0x10106  ldarg.s  5
0x10108  ldc.i4.0
0x10109  stind.i1
0x1010a  ldarg.0
0x1010b  ldstr    aPublish// "Publish"
0x10110  ldarg.s  4
0x10112  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10117  ldloc.0
0x10118  ldarg.3
0x10119  ldarg.s  4
0x1011b  call     bool Microsoft.SharePoint.Publishing.SitePageServerStub::Publish_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10120  box      [mscorlib]System.Boolean
0x10125  ret
0x10126  ldarg.s  5
0x10128  ldc.i4.0
0x10129  stind.i1
0x1012a  ldarg.0
0x1012b  ldstr    aPromotetonews// "PromoteToNews"
0x10130  ldarg.s  4
0x10132  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10137  ldloc.0
0x10138  ldarg.3
0x10139  ldarg.s  4
0x1013b  call     bool Microsoft.SharePoint.Publishing.SitePageServerStub::PromoteToNews_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10140  box      [mscorlib]System.Boolean
0x10145  ret
0x10146  ldarg.s  5
0x10148  ldc.i4.0
0x10149  stind.i1
0x1014a  ldarg.0
0x1014b  ldstr    aDemotefromnews// "DemoteFromNews"
0x10150  ldarg.s  4
0x10152  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10157  ldloc.0
0x10158  ldarg.3
0x10159  ldarg.s  4
0x1015b  call     bool Microsoft.SharePoint.Publishing.SitePageServerStub::DemoteFromNews_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10160  box      [mscorlib]System.Boolean
0x10165  ret
0x10166  ldarg.s  5
0x10168  ldc.i4.0
0x10169  stind.i1
0x1016a  ldarg.0
0x1016b  ldstr    aSavedraft// "SaveDraft"
0x10170  ldarg.s  4
0x10172  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10177  ldloc.0
0x10178  ldarg.3
0x10179  ldarg.s  4
0x1017b  call     bool Microsoft.SharePoint.Publishing.SitePageServerStub::SaveDraft_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10180  box      [mscorlib]System.Boolean
0x10185  ret
0x10186  ldarg.s  5
0x10188  ldc.i4.1
0x10189  stind.i1
0x1018a  ldarg.0
0x1018b  ldstr    aUpdate// "Update"
0x10190  ldarg.s  4
0x10192  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10197  ldloc.0
0x10198  ldarg.3
0x10199  ldarg.s  4
0x1019b  call     void Microsoft.SharePoint.Publishing.SitePageServerStub::Update_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x101a0  ldnull
0x101a1  ret
0x101a2  ldarg.s  5
0x101a4  ldc.i4.1
0x101a5  stind.i1
0x101a6  ldarg.0
0x101a7  ldstr    aSavepage// "SavePage"
0x101ac  ldarg.s  4
0x101ae  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x101b3  ldloc.0
0x101b4  ldarg.3
0x101b5  ldarg.s  4
0x101b7  call     void Microsoft.SharePoint.Publishing.SitePageServerStub::SavePage_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x101bc  ldnull
0x101bd  ret
0x101be  ldarg.s  5
0x101c0  ldc.i4.0
0x101c1  stind.i1
0x101c2  ldarg.0
0x101c3  ldstr    aSavepageasdraf// "SavePageAsDraft"
0x101c8  ldarg.s  4
0x101ca  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x101cf  ldloc.0
0x101d0  ldarg.3
0x101d1  ldarg.s  4
0x101d3  call     bool Microsoft.SharePoint.Publishing.SitePageServerStub::SavePageAsDraft_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x101d8  box      [mscorlib]System.Boolean
0x101dd  ret
0x101de  ldarg.s  5
0x101e0  ldc.i4.0
0x101e1  stind.i1
0x101e2  ldarg.0
0x101e3  ldstr    aCopy// "Copy"
0x101e8  ldarg.s  4
0x101ea  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x101ef  ldloc.0
0x101f0  ldarg.3
0x101f1  ldarg.s  4
0x101f3  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage Microsoft.SharePoint.Publishing.SitePageServerStub::Copy_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x101f8  ret
0x101f9  ldarg.s  5
0x101fb  ldc.i4.1
0x101fc  stind.i1
0x101fd  ldarg.0
0x101fe  ldstr    aSharepageprevi// "SharePagePreviewByEmail"
0x10203  ldarg.s  4
0x10205  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1020a  ldloc.0
0x1020b  ldarg.3
0x1020c  ldarg.s  4
0x1020e  call     void Microsoft.SharePoint.Publishing.SitePageServerStub::SharePagePreviewByEmail_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10213  ldnull
0x10214  ret
0x10215  ldarg.0
0x10216  ldarg.1
0x10217  ldarg.2
0x10218  ldarg.3
0x10219  ldarg.s  4
0x1021b  ldarg.s  5
0x1021d  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x10222  ret
```
