# Microsoft.SharePoint.Activities.CommentOnItemActivityProcessor::GetOutputProperty

- ea: `0x1bacb0`
- end: `0x1bae7f`
- name: `Microsoft.SharePoint.Activities.CommentOnItemActivityProcessor::GetOutputProperty`
- size: `463`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1b8de0`
- `0x1bacb0`
- `0x93dae0`
- `0x957470`

## string_xrefs

- `0x1bacd4`: `CommentParentId`
- `0x1bad89`: `CommentParentId`
- `0x1bad9e`: `CommentParentId`
- `0x1bacec`: `CommentId`
- `0x1badd5`: `CommentId`
- `0x1bade7`: `CommentId`
- `0x1bacf8`: `CommentText`
- `0x1badf8`: `CommentText`
- `0x1bae0a`: `CommentText`
- `0x1bad04`: `CommentItemAuthorLoginName`
- `0x1bae1b`: `CommentItemAuthorLoginName`
- `0x1bae2d`: `CommentItemAuthorLoginName`
- `0x1bace0`: `CommentParentAuthor`
- `0x1bad10`: `CommentUri`
- `0x1bae3e`: `CommentUri`
- `0x1bae50`: `CommentUri`
- `0x1bae67`: `CommentOnItemActivityProcessor.GetOutputProperty {0} was not found value returning null`

## pseudocode

```c

```

## disassembly

```asm
0x1bacb0  ldarg.2
0x1bacb1  dup
0x1bacb2  stloc.0
0x1bacb3  brfalse  loc_1BAE5B
0x1bacb8  volatile.
0x1bacba  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{7F5A19CB-910C-4E1B-81E8-035FE0963D88}::$$method0x6001f58-1
0x1bacbf  brtrue.s loc_1BAD22
0x1bacc1  ldc.i4.7
0x1bacc2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x1bacc7  dup
0x1bacc8  ldstr    aIsreply// "IsReply"
0x1baccd  ldc.i4.0
0x1bacce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1bacd3  dup
0x1bacd4  ldstr    aCommentparenti// "CommentParentId"
0x1bacd9  ldc.i4.1
0x1bacda  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1bacdf  dup
0x1bace0  ldstr    aCommentparenta// "CommentParentAuthor"
0x1bace5  ldc.i4.2
0x1bace6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1baceb  dup
0x1bacec  ldstr    aCommentid_0// "CommentId"
0x1bacf1  ldc.i4.3
0x1bacf2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1bacf7  dup
0x1bacf8  ldstr    aCommenttext// "CommentText"
0x1bacfd  ldc.i4.4
0x1bacfe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1bad03  dup
0x1bad04  ldstr    aCommentitemaut// "CommentItemAuthorLoginName"
0x1bad09  ldc.i4.5
0x1bad0a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1bad0f  dup
0x1bad10  ldstr    aCommenturi// "CommentUri"
0x1bad15  ldc.i4.6
0x1bad16  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1bad1b  volatile.
0x1bad1d  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{7F5A19CB-910C-4E1B-81E8-035FE0963D88}::$$method0x6001f58-1
0x1bad22  volatile.
0x1bad24  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{7F5A19CB-910C-4E1B-81E8-035FE0963D88}::$$method0x6001f58-1
0x1bad29  ldloc.0
0x1bad2a  ldloca.s 1
0x1bad2c  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x1bad31  brfalse  loc_1BAE5B
0x1bad36  ldloc.1
0x1bad37  switch   loc_1BAD5D, loc_1BAD83, loc_1BADA9, loc_1BADCF, loc_1BADF2, loc_1BAE15, loc_1BAE38
0x1bad58  br       loc_1BAE5B
0x1bad5d  ldarg.1
0x1bad5e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Activities.SPActivityObject::get_Properties()
0x1bad63  ldstr    aIsreply// "IsReply"
0x1bad68  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x1bad6d  brfalse  loc_1BAE5B
0x1bad72  ldarg.1
0x1bad73  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Activities.SPActivityObject::get_Properties()
0x1bad78  ldstr    aIsreply// "IsReply"
0x1bad7d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x1bad82  ret
0x1bad83  ldarg.1
0x1bad84  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Activities.SPActivityObject::get_Properties()
0x1bad89  ldstr    aCommentparenti// "CommentParentId"
0x1bad8e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x1bad93  brfalse  loc_1BAE5B
0x1bad98  ldarg.1
0x1bad99  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Activities.SPActivityObject::get_Properties()
0x1bad9e  ldstr    aCommentparenti// "CommentParentId"
0x1bada3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x1bada8  ret
0x1bada9  ldarg.1
0x1badaa  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Activities.SPActivityObject::get_Properties()
0x1badaf  ldstr    aParentauthor// "ParentAuthor"
0x1badb4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x1badb9  brfalse  loc_1BAE5B
0x1badbe  ldarg.1
0x1badbf  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Activities.SPActivityObject::get_Properties()
0x1badc4  ldstr    aParentauthor// "ParentAuthor"
0x1badc9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x1badce  ret
0x1badcf  ldarg.1
0x1badd0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Activities.SPActivityObject::get_Properties()
0x1badd5  ldstr    aCommentid_0// "CommentId"
0x1badda  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x1baddf  brfalse.s loc_1BAE5B
0x1bade1  ldarg.1
0x1bade2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Activities.SPActivityObject::get_Properties()
0x1bade7  ldstr    aCommentid_0// "CommentId"
0x1badec  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x1badf1  ret
0x1badf2  ldarg.1
0x1badf3  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Activities.SPActivityObject::get_Properties()
0x1badf8  ldstr    aCommenttext// "CommentText"
0x1badfd  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x1bae02  brfalse.s loc_1BAE5B
0x1bae04  ldarg.1
0x1bae05  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Activities.SPActivityObject::get_Properties()
0x1bae0a  ldstr    aCommenttext// "CommentText"
0x1bae0f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x1bae14  ret
0x1bae15  ldarg.1
0x1bae16  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Activities.SPActivityObject::get_Properties()
0x1bae1b  ldstr    aCommentitemaut// "CommentItemAuthorLoginName"
0x1bae20  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x1bae25  brfalse.s loc_1BAE5B
0x1bae27  ldarg.1
0x1bae28  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Activities.SPActivityObject::get_Properties()
0x1bae2d  ldstr    aCommentitemaut// "CommentItemAuthorLoginName"
0x1bae32  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x1bae37  ret
0x1bae38  ldarg.1
0x1bae39  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Activities.SPActivityObject::get_Properties()
0x1bae3e  ldstr    aCommenturi// "CommentUri"
0x1bae43  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x1bae48  brfalse.s loc_1BAE5B
0x1bae4a  ldarg.1
0x1bae4b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Activities.SPActivityObject::get_Properties()
0x1bae50  ldstr    aCommenturi// "CommentUri"
0x1bae55  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x1bae5a  ret
0x1bae5b  ldc.i4   0x17564C2
0x1bae60  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x1bae65  ldc.i4.s 0x32
0x1bae67  ldstr    aCommentonitema// "CommentOnItemActivityProcessor.GetOutpu"...
0x1bae6c  ldc.i4.1
0x1bae6d  newarr   [mscorlib]System.Object
0x1bae72  stloc.2
0x1bae73  ldloc.2
0x1bae74  ldc.i4.0
0x1bae75  ldarg.2
0x1bae76  stelem.ref
0x1bae77  ldloc.2
0x1bae78  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x1bae7d  ldnull
0x1bae7e  ret
```
