# System.Windows.Controls.DocumentViewer::OnFindInvoked

- ea: `0x1609a0`
- end: `0x160a8c`
- name: `System.Windows.Controls.DocumentViewer::OnFindInvoked`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x160ab0`

## callees

- `0x67f0`
- `0x6820`
- `0x38c40`
- `0xe4580`
- `0x1609a0`
- `0x1ba5e0`
- `0x1ba640`
- `0x21bc40`
- `0x24fdd0`

## string_xrefs

- `0x160a11`: `DocumentViewerSearchDownCompleteLabel`
- `0x160a1d`: `DocumentViewerSearchUpCompleteLabel`
- `0x160a6a`: `DocumentViewerSearchCompleteTitle`

## pseudocode

```c

```

## disassembly

```asm
0x1609a0  ldc.i4.s 0x40
0x1609a2  ldc.i4   0x139F
0x1609a7  call     void [WindowsBase]MS.Utility.EventTrace::EasyTraceEvent(valuetype [WindowsBase]MS.Utility.EventTrace/Keyword, valuetype [WindowsBase]MS.Utility.EventTrace/Event)
0x1609ac  ldarg.0
0x1609ad  ldfld    class [PresentationUI]MS.Internal.Documents.FindToolBar System.Windows.Controls.DocumentViewer::_findToolbar
0x1609b2  brfalse  loc_160A7C
0x1609b7  ldarg.0
0x1609b8  call     instance class System.Windows.Documents.TextEditor System.Windows.Controls.Primitives.DocumentViewerBase::get_TextEditor()
0x1609bd  brfalse  loc_160A7C
0x1609c2  ldarg.0
0x1609c3  ldarg.0
0x1609c4  ldfld    class [PresentationUI]MS.Internal.Documents.FindToolBar System.Windows.Controls.DocumentViewer::_findToolbar
0x1609c9  call     instance class System.Windows.Documents.ITextRange System.Windows.Controls.Primitives.DocumentViewerBase::Find(class [PresentationUI]MS.Internal.Documents.FindToolBar findToolBar)
0x1609ce  stloc.0
0x1609cf  ldloc.0
0x1609d0  brfalse.s loc_160A04
0x1609d2  ldloc.0
0x1609d3  callvirt instance bool System.Windows.Documents.ITextRange::get_IsEmpty()
0x1609d8  brtrue.s loc_160A04
0x1609da  ldarg.0
0x1609db  call     instance bool [PresentationCore]System.Windows.UIElement::Focus()
0x1609e0  pop
0x1609e1  ldarg.0
0x1609e2  ldfld    class MS.Internal.Documents.IDocumentScrollInfo System.Windows.Controls.DocumentViewer::_documentScrollInfo
0x1609e7  brfalse.s loc_1609F4
0x1609e9  ldarg.0
0x1609ea  ldfld    class MS.Internal.Documents.IDocumentScrollInfo System.Windows.Controls.DocumentViewer::_documentScrollInfo
0x1609ef  callvirt instance void MS.Internal.Documents.IDocumentScrollInfo::MakeSelectionVisible()
0x1609f4  ldarg.0
0x1609f5  ldfld    class [PresentationUI]MS.Internal.Documents.FindToolBar System.Windows.Controls.DocumentViewer::_findToolbar
0x1609fa  callvirt instance void [PresentationUI]MS.Internal.Documents.FindToolBar::GoToTextBox()
0x1609ff  leave    loc_160A8B
0x160a04  ldarg.0
0x160a05  ldfld    class [PresentationUI]MS.Internal.Documents.FindToolBar System.Windows.Controls.DocumentViewer::_findToolbar
0x160a0a  callvirt instance bool [PresentationUI]MS.Internal.Documents.FindToolBar::get_SearchUp()
0x160a0f  brtrue.s loc_160A1D
0x160a11  ldstr    aDocumentviewer_9// "DocumentViewerSearchDownCompleteLabel"
0x160a16  call     string System.Windows.SR::Get(string id)
0x160a1b  br.s     loc_160A27
0x160a1d  ldstr    aDocumentviewer_10// "DocumentViewerSearchUpCompleteLabel"
0x160a22  call     string System.Windows.SR::Get(string id)
0x160a27  stloc.1
0x160a28  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x160a2d  ldloc.1
0x160a2e  ldc.i4.1
0x160a2f  newarr   [mscorlib]System.Object
0x160a34  dup
0x160a35  ldc.i4.0
0x160a36  ldarg.0
0x160a37  ldfld    class [PresentationUI]MS.Internal.Documents.FindToolBar System.Windows.Controls.DocumentViewer::_findToolbar
0x160a3c  callvirt instance string [PresentationUI]MS.Internal.Documents.FindToolBar::get_SearchText()
0x160a41  stelem.ref
0x160a42  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x160a47  stloc.1
0x160a48  ldnull
0x160a49  stloc.2
0x160a4a  call     class System.Windows.Application System.Windows.Application::get_Current()
0x160a4f  brfalse.s loc_160A68
0x160a51  call     class System.Windows.Application System.Windows.Application::get_Current()
0x160a56  callvirt instance bool [WindowsBase]System.Windows.Threading.DispatcherObject::CheckAccess()
0x160a5b  brfalse.s loc_160A68
0x160a5d  call     class System.Windows.Application System.Windows.Application::get_Current()
0x160a62  callvirt instance class System.Windows.Window System.Windows.Application::get_MainWindow()
0x160a67  stloc.2
0x160a68  ldloc.2
0x160a69  ldloc.1
0x160a6a  ldstr    aDocumentviewer_11// "DocumentViewerSearchCompleteTitle"
0x160a6f  call     string System.Windows.SR::Get(string id)
0x160a74  ldc.i4.0
0x160a75  ldc.i4.s 0x40
0x160a77  call     void MS.Internal.PresentationFramework.SecurityHelper::ShowMessageBoxHelper(class System.Windows.Window parent, string text, string title, valuetype System.Windows.MessageBoxButton buttons, valuetype System.Windows.MessageBoxImage image)
0x160a7c  leave.s  loc_160A8B
0x160a7e  ldc.i4.s 0x40
0x160a80  ldc.i4   0x13A0
0x160a85  call     void [WindowsBase]MS.Utility.EventTrace::EasyTraceEvent(valuetype [WindowsBase]MS.Utility.EventTrace/Keyword, valuetype [WindowsBase]MS.Utility.EventTrace/Event)
0x160a8a  endfinally
0x160a8b  ret
```
