# System.Web.HttpApplication::BuildEventMaskDictionary

- ea: `0xfe10`
- end: `0xff46`
- name: `System.Web.HttpApplication::BuildEventMaskDictionary`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0xff50`

## string_xrefs

- `0xfe4d`: `ResolveRequestCache`
- `0xfe59`: `PostResolveRequestCache`
- `0xfed6`: `UpdateRequestCache`
- `0xfee6`: `PostUpdateRequestCache`

## pseudocode

```c

```

## disassembly

```asm
0xfe10  ldarg.1
0xfe11  ldstr    aBeginrequest// "BeginRequest"
0xfe16  ldc.i4.1
0xfe17  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xfe1c  ldarg.1
0xfe1d  ldstr    aAuthenticatere// "AuthenticateRequest"
0xfe22  ldc.i4.2
0xfe23  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xfe28  ldarg.1
0xfe29  ldstr    aPostauthentica// "PostAuthenticateRequest"
0xfe2e  ldc.i4.2
0xfe2f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xfe34  ldarg.1
0xfe35  ldstr    aAuthorizereque// "AuthorizeRequest"
0xfe3a  ldc.i4.4
0xfe3b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xfe40  ldarg.1
0xfe41  ldstr    aPostauthorizer// "PostAuthorizeRequest"
0xfe46  ldc.i4.4
0xfe47  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xfe4c  ldarg.1
0xfe4d  ldstr    aResolverequest// "ResolveRequestCache"
0xfe52  ldc.i4.8
0xfe53  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xfe58  ldarg.1
0xfe59  ldstr    aPostresolvereq// "PostResolveRequestCache"
0xfe5e  ldc.i4.8
0xfe5f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xfe64  ldarg.1
0xfe65  ldstr    aMaprequesthand// "MapRequestHandler"
0xfe6a  ldc.i4.s 0x10
0xfe6c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xfe71  ldarg.1
0xfe72  ldstr    aPostmaprequest// "PostMapRequestHandler"
0xfe77  ldc.i4.s 0x10
0xfe79  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xfe7e  ldarg.1
0xfe7f  ldstr    aAcquirerequest// "AcquireRequestState"
0xfe84  ldc.i4.s 0x20
0xfe86  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xfe8b  ldarg.1
0xfe8c  ldstr    aPostacquirereq// "PostAcquireRequestState"
0xfe91  ldc.i4.s 0x20
0xfe93  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xfe98  ldarg.1
0xfe99  ldstr    aPrerequesthand// "PreRequestHandlerExecute"
0xfe9e  ldc.i4.s 0x40
0xfea0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xfea5  ldarg.1
0xfea6  ldstr    aPostrequesthan// "PostRequestHandlerExecute"
0xfeab  ldc.i4   0x80
0xfeb0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xfeb5  ldarg.1
0xfeb6  ldstr    aReleaserequest// "ReleaseRequestState"
0xfebb  ldc.i4   0x100
0xfec0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xfec5  ldarg.1
0xfec6  ldstr    aPostreleasereq// "PostReleaseRequestState"
0xfecb  ldc.i4   0x100
0xfed0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xfed5  ldarg.1
0xfed6  ldstr    aUpdaterequestc// "UpdateRequestCache"
0xfedb  ldc.i4   0x200
0xfee0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xfee5  ldarg.1
0xfee6  ldstr    aPostupdaterequ// "PostUpdateRequestCache"
0xfeeb  ldc.i4   0x200
0xfef0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xfef5  ldarg.1
0xfef6  ldstr    aLogrequest// "LogRequest"
0xfefb  ldc.i4   0x400
0xff00  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xff05  ldarg.1
0xff06  ldstr    aPostlogrequest// "PostLogRequest"
0xff0b  ldc.i4   0x400
0xff10  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xff15  ldarg.1
0xff16  ldstr    aEndrequest// "EndRequest"
0xff1b  ldc.i4   0x800
0xff20  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xff25  ldarg.1
0xff26  ldstr    aPresendrequest// "PreSendRequestHeaders"
0xff2b  ldc.i4   0x20000000
0xff30  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xff35  ldarg.1
0xff36  ldstr    aPresendrequest_0// "PreSendRequestContent"
0xff3b  ldc.i4   0x20000000
0xff40  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype System.Web.RequestNotification>::set_Item(var<u1>, !!T0)
0xff45  ret
```
