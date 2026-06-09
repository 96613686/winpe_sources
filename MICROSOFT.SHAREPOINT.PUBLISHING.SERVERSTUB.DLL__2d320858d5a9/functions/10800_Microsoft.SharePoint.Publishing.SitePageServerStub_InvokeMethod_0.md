# Microsoft.SharePoint.Publishing.SitePageServerStub::InvokeMethod_0

- ea: `0x10800`
- end: `0x10ad3`
- name: `Microsoft.SharePoint.Publishing.SitePageServerStub::InvokeMethod_0`
- size: `723`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x106f0`
- `0x10700`
- `0x10710`
- `0x10720`
- `0x10730`
- `0x10740`
- `0x10750`
- `0x10760`
- `0x10780`
- `0x10790`
- `0x107b0`
- `0x107d0`
- `0x107e0`
- `0x10800`

## string_xrefs

- `0x1084b`: `Delete`
- `0x10949`: `Delete`
- `0x108ab`: `Update`
- `0x10a3b`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0x10800  ldarg.s  4
0x10802  brtrue.s loc_1080F
0x10804  ldstr    aProxycontext// "proxyContext"
0x10809  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1080e  throw
0x1080f  ldarg.1
0x10810  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage
0x10815  stloc.0
0x10816  ldloc.0
0x10817  brtrue.s loc_10824
0x10819  ldstr    aTarget// "target"
0x1081e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10823  throw
0x10824  ldarg.0
0x10825  ldarg.2
0x10826  ldarg.s  4
0x10828  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1082d  starg.s  2
0x1082f  ldarg.2
0x10830  dup
0x10831  stloc.1
0x10832  brfalse  loc_10AC5
0x10837  volatile.
0x10839  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60002de-1
0x1083e  brtrue   loc_108F1
0x10843  ldc.i4.s 0xD
0x10845  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x1084a  dup
0x1084b  ldstr    aDelete// "Delete"
0x10850  ldc.i4.0
0x10851  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x10856  dup
0x10857  ldstr    aCheckout// "CheckOut"
0x1085c  ldc.i4.1
0x1085d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x10862  dup
0x10863  ldstr    aDiscardpage// "DiscardPage"
0x10868  ldc.i4.2
0x10869  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1086e  dup
0x1086f  ldstr    aCheckoutpage// "CheckoutPage"
0x10874  ldc.i4.3
0x10875  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1087a  dup
0x1087b  ldstr    aPublish// "Publish"
0x10880  ldc.i4.4
0x10881  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x10886  dup
0x10887  ldstr    aPromotetonews// "PromoteToNews"
0x1088c  ldc.i4.5
0x1088d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x10892  dup
0x10893  ldstr    aDemotefromnews// "DemoteFromNews"
0x10898  ldc.i4.6
0x10899  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1089e  dup
0x1089f  ldstr    aSavedraft// "SaveDraft"
0x108a4  ldc.i4.7
0x108a5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x108aa  dup
0x108ab  ldstr    aUpdate// "Update"
0x108b0  ldc.i4.8
0x108b1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x108b6  dup
0x108b7  ldstr    aSavepage// "SavePage"
0x108bc  ldc.i4.s 9
0x108be  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x108c3  dup
0x108c4  ldstr    aSavepageasdraf// "SavePageAsDraft"
0x108c9  ldc.i4.s 0xA
0x108cb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x108d0  dup
0x108d1  ldstr    aCopy// "Copy"
0x108d6  ldc.i4.s 0xB
0x108d8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x108dd  dup
0x108de  ldstr    aSharepageprevi// "SharePagePreviewByEmail"
0x108e3  ldc.i4.s 0xC
0x108e5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x108ea  volatile.
0x108ec  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60002de-1
0x108f1  volatile.
0x108f3  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60002de-1
0x108f8  ldloc.1
0x108f9  ldloca.s 2
0x108fb  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x10900  brfalse  loc_10AC5
0x10905  ldloc.2
0x10906  switch   loc_10944, loc_10960, loc_10980, loc_1099B, loc_109B6, loc_109D6, loc_109F6, loc_10A16, loc_10A36, loc_10A52, loc_10A6E, loc_10A8E, loc_10AA9
0x1093f  br       loc_10AC5
0x10944  ldarg.s  5
0x10946  ldc.i4.1
0x10947  stind.i1
0x10948  ldarg.0
0x10949  ldstr    aDelete// "Delete"
0x1094e  ldarg.s  4
0x10950  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10955  ldloc.0
0x10956  ldarg.3
0x10957  ldarg.s  4
0x10959  call     void Microsoft.SharePoint.Publishing.SitePageServerStub::Delete_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1095e  ldnull
0x1095f  ret
0x10960  ldarg.s  5
0x10962  ldc.i4.0
0x10963  stind.i1
0x10964  ldarg.0
0x10965  ldstr    aCheckout// "CheckOut"
0x1096a  ldarg.s  4
0x1096c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10971  ldloc.0
0x10972  ldarg.3
0x10973  ldarg.s  4
0x10975  call     bool Microsoft.SharePoint.Publishing.SitePageServerStub::CheckOut_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1097a  box      [mscorlib]System.Boolean
0x1097f  ret
0x10980  ldarg.s  5
0x10982  ldc.i4.0
0x10983  stind.i1
0x10984  ldarg.0
0x10985  ldstr    aDiscardpage// "DiscardPage"
0x1098a  ldarg.s  4
0x1098c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10991  ldloc.0
0x10992  ldarg.3
0x10993  ldarg.s  4
0x10995  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage Microsoft.SharePoint.Publishing.SitePageServerStub::DiscardPage_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1099a  ret
0x1099b  ldarg.s  5
0x1099d  ldc.i4.0
0x1099e  stind.i1
0x1099f  ldarg.0
0x109a0  ldstr    aCheckoutpage// "CheckoutPage"
0x109a5  ldarg.s  4
0x109a7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x109ac  ldloc.0
0x109ad  ldarg.3
0x109ae  ldarg.s  4
0x109b0  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage Microsoft.SharePoint.Publishing.SitePageServerStub::CheckoutPage_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x109b5  ret
0x109b6  ldarg.s  5
0x109b8  ldc.i4.0
0x109b9  stind.i1
0x109ba  ldarg.0
0x109bb  ldstr    aPublish// "Publish"
0x109c0  ldarg.s  4
0x109c2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x109c7  ldloc.0
0x109c8  ldarg.3
0x109c9  ldarg.s  4
0x109cb  call     bool Microsoft.SharePoint.Publishing.SitePageServerStub::Publish_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x109d0  box      [mscorlib]System.Boolean
0x109d5  ret
0x109d6  ldarg.s  5
0x109d8  ldc.i4.0
0x109d9  stind.i1
0x109da  ldarg.0
0x109db  ldstr    aPromotetonews// "PromoteToNews"
0x109e0  ldarg.s  4
0x109e2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x109e7  ldloc.0
0x109e8  ldarg.3
0x109e9  ldarg.s  4
0x109eb  call     bool Microsoft.SharePoint.Publishing.SitePageServerStub::PromoteToNews_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x109f0  box      [mscorlib]System.Boolean
0x109f5  ret
0x109f6  ldarg.s  5
0x109f8  ldc.i4.0
0x109f9  stind.i1
0x109fa  ldarg.0
0x109fb  ldstr    aDemotefromnews// "DemoteFromNews"
0x10a00  ldarg.s  4
0x10a02  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10a07  ldloc.0
0x10a08  ldarg.3
0x10a09  ldarg.s  4
0x10a0b  call     bool Microsoft.SharePoint.Publishing.SitePageServerStub::DemoteFromNews_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10a10  box      [mscorlib]System.Boolean
0x10a15  ret
0x10a16  ldarg.s  5
0x10a18  ldc.i4.0
0x10a19  stind.i1
0x10a1a  ldarg.0
0x10a1b  ldstr    aSavedraft// "SaveDraft"
0x10a20  ldarg.s  4
0x10a22  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10a27  ldloc.0
0x10a28  ldarg.3
0x10a29  ldarg.s  4
0x10a2b  call     bool Microsoft.SharePoint.Publishing.SitePageServerStub::SaveDraft_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10a30  box      [mscorlib]System.Boolean
0x10a35  ret
0x10a36  ldarg.s  5
0x10a38  ldc.i4.1
0x10a39  stind.i1
0x10a3a  ldarg.0
0x10a3b  ldstr    aUpdate// "Update"
0x10a40  ldarg.s  4
0x10a42  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10a47  ldloc.0
0x10a48  ldarg.3
0x10a49  ldarg.s  4
0x10a4b  call     void Microsoft.SharePoint.Publishing.SitePageServerStub::Update_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10a50  ldnull
0x10a51  ret
0x10a52  ldarg.s  5
0x10a54  ldc.i4.1
0x10a55  stind.i1
0x10a56  ldarg.0
0x10a57  ldstr    aSavepage// "SavePage"
0x10a5c  ldarg.s  4
0x10a5e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10a63  ldloc.0
0x10a64  ldarg.3
0x10a65  ldarg.s  4
0x10a67  call     void Microsoft.SharePoint.Publishing.SitePageServerStub::SavePage_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10a6c  ldnull
0x10a6d  ret
0x10a6e  ldarg.s  5
0x10a70  ldc.i4.0
0x10a71  stind.i1
0x10a72  ldarg.0
0x10a73  ldstr    aSavepageasdraf// "SavePageAsDraft"
0x10a78  ldarg.s  4
0x10a7a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10a7f  ldloc.0
0x10a80  ldarg.3
0x10a81  ldarg.s  4
0x10a83  call     bool Microsoft.SharePoint.Publishing.SitePageServerStub::SavePageAsDraft_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10a88  box      [mscorlib]System.Boolean
0x10a8d  ret
0x10a8e  ldarg.s  5
0x10a90  ldc.i4.0
0x10a91  stind.i1
0x10a92  ldarg.0
0x10a93  ldstr    aCopy// "Copy"
0x10a98  ldarg.s  4
0x10a9a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10a9f  ldloc.0
0x10aa0  ldarg.3
0x10aa1  ldarg.s  4
0x10aa3  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage Microsoft.SharePoint.Publishing.SitePageServerStub::Copy_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10aa8  ret
0x10aa9  ldarg.s  5
0x10aab  ldc.i4.1
0x10aac  stind.i1
0x10aad  ldarg.0
0x10aae  ldstr    aSharepageprevi// "SharePagePreviewByEmail"
0x10ab3  ldarg.s  4
0x10ab5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10aba  ldloc.0
0x10abb  ldarg.3
0x10abc  ldarg.s  4
0x10abe  call     void Microsoft.SharePoint.Publishing.SitePageServerStub::SharePagePreviewByEmail_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x10ac3  ldnull
0x10ac4  ret
0x10ac5  ldarg.0
0x10ac6  ldarg.1
0x10ac7  ldarg.2
0x10ac8  ldarg.3
0x10ac9  ldarg.s  4
0x10acb  ldarg.s  5
0x10acd  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x10ad2  ret
```
