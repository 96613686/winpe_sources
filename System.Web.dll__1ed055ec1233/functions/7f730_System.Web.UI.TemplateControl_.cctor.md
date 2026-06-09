# System.Web.UI.TemplateControl::.cctor

- ea: `0x7f730`
- end: `0x7f8b9`
- name: `System.Web.UI.TemplateControl::.cctor`
- size: `393`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x19c120`

## string_xrefs

- `0x7f7a5`: `Page_InitComplete`
- `0x7f7e1`: `Page_LoadComplete`
- `0x7f7f5`: `Page_PreRenderComplete`
- `0x7f831`: `Page_SaveStateComplete`
- `0x7f895`: `Page_CommitTransaction`
- `0x7f8a9`: `OnTransactionCommit`

## pseudocode

```c

```

## disassembly

```asm
0x7f730  newobj   instance void [mscorlib]System.Object::.ctor()
0x7f735  stsfld   object System.Web.UI.TemplateControl::_lockObject
0x7f73a  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x7f73f  stsfld   class [mscorlib]System.Collections.Hashtable System.Web.UI.TemplateControl::_eventListCache
0x7f744  newobj   instance void EventList::.ctor()
0x7f749  stsfld   object System.Web.UI.TemplateControl::_emptyEventSingleton
0x7f74e  newobj   instance void [mscorlib]System.Object::.ctor()
0x7f753  stsfld   object System.Web.UI.TemplateControl::EventCommitTransaction
0x7f758  newobj   instance void [mscorlib]System.Object::.ctor()
0x7f75d  stsfld   object System.Web.UI.TemplateControl::EventAbortTransaction
0x7f762  newobj   instance void [mscorlib]System.Object::.ctor()
0x7f767  stsfld   object System.Web.UI.TemplateControl::EventError
0x7f76c  ldc.i4.s 0x10
0x7f76e  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(int32)
0x7f773  stsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControl::_eventObjects
0x7f778  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControl::_eventObjects
0x7f77d  ldstr    aPagePreinit// "Page_PreInit"
0x7f782  ldsfld   object System.Web.UI.Page::EventPreInit
0x7f787  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x7f78c  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControl::_eventObjects
0x7f791  ldstr    aPageInit// "Page_Init"
0x7f796  ldsfld   object System.Web.UI.Control::EventInit
0x7f79b  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x7f7a0  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControl::_eventObjects
0x7f7a5  ldstr    aPageInitcomple// "Page_InitComplete"
0x7f7aa  ldsfld   object System.Web.UI.Page::EventInitComplete
0x7f7af  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x7f7b4  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControl::_eventObjects
0x7f7b9  ldstr    aPageLoad// "Page_Load"
0x7f7be  ldsfld   object System.Web.UI.Control::EventLoad
0x7f7c3  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x7f7c8  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControl::_eventObjects
0x7f7cd  ldstr    aPagePreload// "Page_PreLoad"
0x7f7d2  ldsfld   object System.Web.UI.Page::EventPreLoad
0x7f7d7  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x7f7dc  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControl::_eventObjects
0x7f7e1  ldstr    aPageLoadcomple// "Page_LoadComplete"
0x7f7e6  ldsfld   object System.Web.UI.Page::EventLoadComplete
0x7f7eb  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x7f7f0  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControl::_eventObjects
0x7f7f5  ldstr    aPagePrerenderc// "Page_PreRenderComplete"
0x7f7fa  ldsfld   object System.Web.UI.Page::EventPreRenderComplete
0x7f7ff  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x7f804  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControl::_eventObjects
0x7f809  ldstr    aPageDatabind// "Page_DataBind"
0x7f80e  ldsfld   object System.Web.UI.Control::EventDataBinding
0x7f813  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x7f818  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControl::_eventObjects
0x7f81d  ldstr    aPagePrerender// "Page_PreRender"
0x7f822  ldsfld   object System.Web.UI.Control::EventPreRender
0x7f827  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x7f82c  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControl::_eventObjects
0x7f831  ldstr    aPageSavestatec// "Page_SaveStateComplete"
0x7f836  ldsfld   object System.Web.UI.Page::EventSaveStateComplete
0x7f83b  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x7f840  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControl::_eventObjects
0x7f845  ldstr    aPageUnload// "Page_Unload"
0x7f84a  ldsfld   object System.Web.UI.Control::EventUnload
0x7f84f  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x7f854  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControl::_eventObjects
0x7f859  ldstr    aPageError// "Page_Error"
0x7f85e  ldsfld   object System.Web.UI.TemplateControl::EventError
0x7f863  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x7f868  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControl::_eventObjects
0x7f86d  ldstr    aPageAborttrans// "Page_AbortTransaction"
0x7f872  ldsfld   object System.Web.UI.TemplateControl::EventAbortTransaction
0x7f877  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x7f87c  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControl::_eventObjects
0x7f881  ldstr    aOntransactiona// "OnTransactionAbort"
0x7f886  ldsfld   object System.Web.UI.TemplateControl::EventAbortTransaction
0x7f88b  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x7f890  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControl::_eventObjects
0x7f895  ldstr    aPageCommittran// "Page_CommitTransaction"
0x7f89a  ldsfld   object System.Web.UI.TemplateControl::EventCommitTransaction
0x7f89f  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x7f8a4  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.TemplateControl::_eventObjects
0x7f8a9  ldstr    aOntransactionc// "OnTransactionCommit"
0x7f8ae  ldsfld   object System.Web.UI.TemplateControl::EventCommitTransaction
0x7f8b3  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x7f8b8  ret
```
