# System.Web.UI.TemplateControl::GetDelegateInformationWithNoAssert

- ea: `0x7fe30`
- end: `0x7ff26`
- name: `System.Web.UI.TemplateControl::GetDelegateInformationWithNoAssert`
- size: `246`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x7fe00`
- `0x7fe20`

## callees

- `0x7fe30`
- `0x7ff30`
- `0x7ff90`

## string_xrefs

- `0x7fe7b`: `Page_InitComplete`
- `0x7fe61`: `Page_LoadComplete`
- `0x7fe6e`: `Page_PreRenderComplete`
- `0x7fe88`: `Page_SaveStateComplete`
- `0x7ff0b`: `Page_CommitTransaction`
- `0x7ff19`: `OnTransactionCommit`
- `0x7fe95`: `Page_PreRenderCompleteAsync`

## pseudocode

```c

```

## disassembly

```asm
0x7fe30  ldarg.1
0x7fe31  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, class SyncEventMethodInfo> EventList::SyncEvents
0x7fe36  stloc.0
0x7fe37  ldarg.1
0x7fe38  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, class AsyncEventMethodInfo> EventList::AsyncEvents
0x7fe3d  stloc.1
0x7fe3e  ldarg.0
0x7fe3f  isinst   System.Web.UI.Page
0x7fe44  brfalse.s loc_7FEA1
0x7fe46  ldarg.0
0x7fe47  ldstr    aPagePreinit// "Page_PreInit"
0x7fe4c  ldloc.0
0x7fe4d  call     instance bool System.Web.UI.TemplateControl::GetDelegateInformationFromSyncMethod(string methodName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class SyncEventMethodInfo> dictionary)
0x7fe52  pop
0x7fe53  ldarg.0
0x7fe54  ldstr    aPagePreload// "Page_PreLoad"
0x7fe59  ldloc.0
0x7fe5a  call     instance bool System.Web.UI.TemplateControl::GetDelegateInformationFromSyncMethod(string methodName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class SyncEventMethodInfo> dictionary)
0x7fe5f  pop
0x7fe60  ldarg.0
0x7fe61  ldstr    aPageLoadcomple// "Page_LoadComplete"
0x7fe66  ldloc.0
0x7fe67  call     instance bool System.Web.UI.TemplateControl::GetDelegateInformationFromSyncMethod(string methodName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class SyncEventMethodInfo> dictionary)
0x7fe6c  pop
0x7fe6d  ldarg.0
0x7fe6e  ldstr    aPagePrerenderc// "Page_PreRenderComplete"
0x7fe73  ldloc.0
0x7fe74  call     instance bool System.Web.UI.TemplateControl::GetDelegateInformationFromSyncMethod(string methodName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class SyncEventMethodInfo> dictionary)
0x7fe79  pop
0x7fe7a  ldarg.0
0x7fe7b  ldstr    aPageInitcomple// "Page_InitComplete"
0x7fe80  ldloc.0
0x7fe81  call     instance bool System.Web.UI.TemplateControl::GetDelegateInformationFromSyncMethod(string methodName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class SyncEventMethodInfo> dictionary)
0x7fe86  pop
0x7fe87  ldarg.0
0x7fe88  ldstr    aPageSavestatec// "Page_SaveStateComplete"
0x7fe8d  ldloc.0
0x7fe8e  call     instance bool System.Web.UI.TemplateControl::GetDelegateInformationFromSyncMethod(string methodName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class SyncEventMethodInfo> dictionary)
0x7fe93  pop
0x7fe94  ldarg.0
0x7fe95  ldstr    aPagePrerenderc_0// "Page_PreRenderCompleteAsync"
0x7fe9a  ldloc.1
0x7fe9b  call     instance bool System.Web.UI.TemplateControl::GetDelegateInformationFromAsyncMethod(string methodName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class AsyncEventMethodInfo> dictionary)
0x7fea0  pop
0x7fea1  ldarg.0
0x7fea2  ldstr    aPageInit// "Page_Init"
0x7fea7  ldloc.0
0x7fea8  call     instance bool System.Web.UI.TemplateControl::GetDelegateInformationFromSyncMethod(string methodName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class SyncEventMethodInfo> dictionary)
0x7fead  pop
0x7feae  ldarg.0
0x7feaf  ldstr    aPageLoad// "Page_Load"
0x7feb4  ldloc.0
0x7feb5  call     instance bool System.Web.UI.TemplateControl::GetDelegateInformationFromSyncMethod(string methodName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class SyncEventMethodInfo> dictionary)
0x7feba  pop
0x7febb  ldarg.0
0x7febc  ldstr    aPageDatabind// "Page_DataBind"
0x7fec1  ldloc.0
0x7fec2  call     instance bool System.Web.UI.TemplateControl::GetDelegateInformationFromSyncMethod(string methodName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class SyncEventMethodInfo> dictionary)
0x7fec7  pop
0x7fec8  ldarg.0
0x7fec9  ldstr    aPagePrerender// "Page_PreRender"
0x7fece  ldloc.0
0x7fecf  call     instance bool System.Web.UI.TemplateControl::GetDelegateInformationFromSyncMethod(string methodName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class SyncEventMethodInfo> dictionary)
0x7fed4  pop
0x7fed5  ldarg.0
0x7fed6  ldstr    aPageUnload// "Page_Unload"
0x7fedb  ldloc.0
0x7fedc  call     instance bool System.Web.UI.TemplateControl::GetDelegateInformationFromSyncMethod(string methodName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class SyncEventMethodInfo> dictionary)
0x7fee1  pop
0x7fee2  ldarg.0
0x7fee3  ldstr    aPageError// "Page_Error"
0x7fee8  ldloc.0
0x7fee9  call     instance bool System.Web.UI.TemplateControl::GetDelegateInformationFromSyncMethod(string methodName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class SyncEventMethodInfo> dictionary)
0x7feee  pop
0x7feef  ldarg.0
0x7fef0  ldstr    aPageAborttrans// "Page_AbortTransaction"
0x7fef5  ldloc.0
0x7fef6  call     instance bool System.Web.UI.TemplateControl::GetDelegateInformationFromSyncMethod(string methodName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class SyncEventMethodInfo> dictionary)
0x7fefb  brtrue.s loc_7FF0A
0x7fefd  ldarg.0
0x7fefe  ldstr    aOntransactiona// "OnTransactionAbort"
0x7ff03  ldloc.0
0x7ff04  call     instance bool System.Web.UI.TemplateControl::GetDelegateInformationFromSyncMethod(string methodName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class SyncEventMethodInfo> dictionary)
0x7ff09  pop
0x7ff0a  ldarg.0
0x7ff0b  ldstr    aPageCommittran// "Page_CommitTransaction"
0x7ff10  ldloc.0
0x7ff11  call     instance bool System.Web.UI.TemplateControl::GetDelegateInformationFromSyncMethod(string methodName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class SyncEventMethodInfo> dictionary)
0x7ff16  brtrue.s loc_7FF25
0x7ff18  ldarg.0
0x7ff19  ldstr    aOntransactionc// "OnTransactionCommit"
0x7ff1e  ldloc.0
0x7ff1f  call     instance bool System.Web.UI.TemplateControl::GetDelegateInformationFromSyncMethod(string methodName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class SyncEventMethodInfo> dictionary)
0x7ff24  pop
0x7ff25  ret
```
