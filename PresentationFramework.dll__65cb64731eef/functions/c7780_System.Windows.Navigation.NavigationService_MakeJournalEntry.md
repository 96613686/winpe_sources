# System.Windows.Navigation.NavigationService::MakeJournalEntry

- ea: `0xc7780`
- end: `0xc7a88`
- name: `System.Windows.Navigation.NavigationService::MakeJournalEntry`
- size: `776`
- prototype: ``
- caller_count: `3`
- callee_count: `28`
- tags: `service_task, broker_com_uri`

## callers

- `0xc76d0`
- `0x166130`
- `0x23f1e0`

## callees

- `0x33430`
- `0x38c40`
- `0x38c70`
- `0xc42d0`
- `0xc4310`
- `0xc4550`
- `0xc4560`
- `0xc4570`
- `0xc45a0`
- `0xc45d0`
- `0xc46a0`
- `0xc47f0`
- `0xc54a0`
- `0xc59a0`
- `0xc5fa0`
- `0xc7780`
- `0xc82e0`
- `0xc8f70`
- `0x1815c0`
- `0x240f80`
- `0x241030`
- `0x241080`
- `0x2412b0`
- `0x2414b0`
- `0x2415e0`
- `0x241bc0`
- `0x24ea80`
- `0x24eaa0`

## string_xrefs

- `0xc77f7`: `BaseUri for root element should be absolute.`

## pseudocode

```c

```

## disassembly

```asm
0xc7780  ldarg.0
0xc7781  ldfld    object System.Windows.Navigation.NavigationService::_bp
0xc7786  brtrue.s loc_C778A
0xc7788  ldnull
0xc7789  ret
0xc778a  ldarg.0
0xc778b  ldfld    class MS.Internal.AppModel.JournalEntryGroupState System.Windows.Navigation.NavigationService::_journalEntryGroupState
0xc7790  brtrue.s loc_C77A9
0xc7792  ldarg.0
0xc7793  ldarg.0
0xc7794  ldfld    valuetype [mscorlib]System.Guid System.Windows.Navigation.NavigationService::_guidId
0xc7799  ldarg.0
0xc779a  ldfld    unsigned int32 System.Windows.Navigation.NavigationService::_contentId
0xc779f  newobj   instance void MS.Internal.AppModel.JournalEntryGroupState::.ctor(valuetype [mscorlib]System.Guid navSvcId, unsigned int32 contentId)
0xc77a4  stfld    class MS.Internal.AppModel.JournalEntryGroupState System.Windows.Navigation.NavigationService::_journalEntryGroupState
0xc77a9  ldarg.0
0xc77aa  call     instance bool System.Windows.Navigation.NavigationService::IsContentKeepAlive()
0xc77af  stloc.1
0xc77b0  ldarg.0
0xc77b1  ldfld    object System.Windows.Navigation.NavigationService::_bp
0xc77b6  isinst   System.Windows.Navigation.PageFunctionBase
0xc77bb  stloc.2
0xc77bc  ldloc.2
0xc77bd  brfalse  loc_C7856
0xc77c2  ldloc.1
0xc77c3  brfalse.s loc_C77D4
0xc77c5  ldarg.0
0xc77c6  ldfld    class MS.Internal.AppModel.JournalEntryGroupState System.Windows.Navigation.NavigationService::_journalEntryGroupState
0xc77cb  ldloc.2
0xc77cc  newobj   instance void MS.Internal.AppModel.JournalEntryPageFunctionKeepAlive::.ctor(class MS.Internal.AppModel.JournalEntryGroupState jeGroupState, class System.Windows.Navigation.PageFunctionBase pageFunction)
0xc77d1  stloc.0
0xc77d2  br.s     loc_C7848
0xc77d4  ldloc.2
0xc77d5  ldsfld   class [WindowsBase]System.Windows.DependencyProperty [PresentationCore]System.Windows.Navigation.BaseUriHelper::BaseUriProperty
0xc77da  callvirt instance object [WindowsBase]System.Windows.DependencyObject::GetValue(class [WindowsBase]System.Windows.DependencyProperty)
0xc77df  isinst   [System]System.Uri
0xc77e4  stloc.s  5
0xc77e6  ldloc.s  5
0xc77e8  ldnull
0xc77e9  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xc77ee  brfalse.s loc_C783B
0xc77f0  ldloc.s  5
0xc77f2  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0xc77f7  ldstr    aBaseuriForRoot// "BaseUri for root element should be abso"...
0xc77fc  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0xc7801  ldarg.0
0xc7802  ldfld    class [System]System.Uri System.Windows.Navigation.NavigationService::_currentCleanSource
0xc7807  ldnull
0xc7808  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xc780d  brfalse.s loc_C7826
0xc780f  ldarg.0
0xc7810  ldfld    class [System]System.Uri System.Windows.Navigation.NavigationService::_currentCleanSource
0xc7815  call     bool MS.Internal.Utility.BindUriHelper::StartWithFragment(class [System]System.Uri uri)
0xc781a  brtrue.s loc_C7826
0xc781c  ldarg.0
0xc781d  ldfld    class [System]System.Uri System.Windows.Navigation.NavigationService::_currentSource
0xc7822  stloc.s  6
0xc7824  br.s     loc_C782A
0xc7826  ldloc.s  5
0xc7828  stloc.s  6
0xc782a  ldarg.0
0xc782b  ldfld    class MS.Internal.AppModel.JournalEntryGroupState System.Windows.Navigation.NavigationService::_journalEntryGroupState
0xc7830  ldloc.2
0xc7831  ldloc.s  6
0xc7833  newobj   instance void MS.Internal.AppModel.JournalEntryPageFunctionUri::.ctor(class MS.Internal.AppModel.JournalEntryGroupState jeGroupState, class System.Windows.Navigation.PageFunctionBase pageFunction, class [System]System.Uri markupUri)
0xc7838  stloc.0
0xc7839  br.s     loc_C7848
0xc783b  ldarg.0
0xc783c  ldfld    class MS.Internal.AppModel.JournalEntryGroupState System.Windows.Navigation.NavigationService::_journalEntryGroupState
0xc7841  ldloc.2
0xc7842  newobj   instance void MS.Internal.AppModel.JournalEntryPageFunctionType::.ctor(class MS.Internal.AppModel.JournalEntryGroupState jeGroupState, class System.Windows.Navigation.PageFunctionBase pageFunction)
0xc7847  stloc.0
0xc7848  ldloc.0
0xc7849  ldarg.0
0xc784a  ldfld    class [System]System.Uri System.Windows.Navigation.NavigationService::_currentCleanSource
0xc784f  callvirt instance void System.Windows.Navigation.JournalEntry::set_Source(class [System]System.Uri value)
0xc7854  br.s     loc_C7885
0xc7856  ldloc.1
0xc7857  brfalse.s loc_C7873
0xc7859  ldarg.0
0xc785a  ldfld    class MS.Internal.AppModel.JournalEntryGroupState System.Windows.Navigation.NavigationService::_journalEntryGroupState
0xc785f  ldarg.0
0xc7860  ldfld    class [System]System.Uri System.Windows.Navigation.NavigationService::_currentCleanSource
0xc7865  ldarg.0
0xc7866  ldfld    object System.Windows.Navigation.NavigationService::_bp
0xc786b  newobj   instance void MS.Internal.AppModel.JournalEntryKeepAlive::.ctor(class MS.Internal.AppModel.JournalEntryGroupState jeGroupState, class [System]System.Uri uri, object keepAliveRoot)
0xc7870  stloc.0
0xc7871  br.s     loc_C7885
0xc7873  ldarg.0
0xc7874  ldfld    class MS.Internal.AppModel.JournalEntryGroupState System.Windows.Navigation.NavigationService::_journalEntryGroupState
0xc7879  ldarg.0
0xc787a  ldfld    class [System]System.Uri System.Windows.Navigation.NavigationService::_currentCleanSource
0xc787f  newobj   instance void MS.Internal.AppModel.JournalEntryUri::.ctor(class MS.Internal.AppModel.JournalEntryGroupState jeGroupState, class [System]System.Uri uri)
0xc7884  stloc.0
0xc7885  ldarg.0
0xc7886  ldfld    class System.Windows.Navigation.CustomContentState System.Windows.Navigation.NavigationService::_customContentStateToSave
0xc788b  stloc.3
0xc788c  ldloc.3
0xc788d  brtrue.s loc_C78A8
0xc788f  ldarg.0
0xc7890  ldfld    object System.Windows.Navigation.NavigationService::_bp
0xc7895  isinst   System.Windows.Navigation.IProvideCustomContentState
0xc789a  stloc.s  7
0xc789c  ldloc.s  7
0xc789e  brfalse.s loc_C78A8
0xc78a0  ldloc.s  7
0xc78a2  callvirt instance class System.Windows.Navigation.CustomContentState System.Windows.Navigation.IProvideCustomContentState::GetContentState()
0xc78a7  stloc.3
0xc78a8  ldloc.3
0xc78a9  brfalse.s loc_C78DE
0xc78ab  ldloc.3
0xc78ac  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc78b1  stloc.s  8
0xc78b3  ldloc.s  8
0xc78b5  callvirt instance bool [mscorlib]System.Type::get_IsSerializable()
0xc78ba  brtrue.s loc_C78D7
0xc78bc  ldstr    aCustomcontents_0// "CustomContentStateMustBeSerializable"
0xc78c1  ldc.i4.1
0xc78c2  newarr   [mscorlib]System.Object
0xc78c7  dup
0xc78c8  ldc.i4.0
0xc78c9  ldloc.s  8
0xc78cb  stelem.ref
0xc78cc  call     string System.Windows.SR::Get(string id, object[] args)
0xc78d1  newobj   instance void [mscorlib]System.SystemException::.ctor(string)
0xc78d6  throw
0xc78d7  ldloc.0
0xc78d8  ldloc.3
0xc78d9  callvirt instance void System.Windows.Navigation.JournalEntry::set_CustomContentState(class System.Windows.Navigation.CustomContentState value)
0xc78de  ldarg.0
0xc78df  ldfld    class MS.Internal.AppModel.CustomJournalStateInternal System.Windows.Navigation.NavigationService::_rootViewerStateToSave
0xc78e4  brfalse.s loc_C78FB
0xc78e6  ldloc.0
0xc78e7  ldarg.0
0xc78e8  ldfld    class MS.Internal.AppModel.CustomJournalStateInternal System.Windows.Navigation.NavigationService::_rootViewerStateToSave
0xc78ed  callvirt instance void System.Windows.Navigation.JournalEntry::set_RootViewerState(class MS.Internal.AppModel.CustomJournalStateInternal value)
0xc78f2  ldarg.0
0xc78f3  ldnull
0xc78f4  stfld    class MS.Internal.AppModel.CustomJournalStateInternal System.Windows.Navigation.NavigationService::_rootViewerStateToSave
0xc78f9  br.s     loc_C7908
0xc78fb  ldloc.0
0xc78fc  ldarg.0
0xc78fd  ldarg.1
0xc78fe  call     instance class MS.Internal.AppModel.CustomJournalStateInternal System.Windows.Navigation.NavigationService::GetRootViewerState(valuetype MS.Internal.AppModel.JournalReason journalReason)
0xc7903  callvirt instance void System.Windows.Navigation.JournalEntry::set_RootViewerState(class MS.Internal.AppModel.CustomJournalStateInternal value)
0xc7908  ldnull
0xc7909  stloc.s  4
0xc790b  ldloc.0
0xc790c  callvirt instance class System.Windows.Navigation.CustomContentState System.Windows.Navigation.JournalEntry::get_CustomContentState()
0xc7911  brfalse.s loc_C7920
0xc7913  ldloc.0
0xc7914  callvirt instance class System.Windows.Navigation.CustomContentState System.Windows.Navigation.JournalEntry::get_CustomContentState()
0xc7919  callvirt instance string System.Windows.Navigation.CustomContentState::get_JournalEntryName()
0xc791e  stloc.s  4
0xc7920  ldloc.s  4
0xc7922  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc7927  brfalse  loc_C7A6E
0xc792c  ldarg.0
0xc792d  ldfld    object System.Windows.Navigation.NavigationService::_bp
0xc7932  isinst   [WindowsBase]System.Windows.DependencyObject
0xc7937  stloc.s  9
0xc7939  ldloc.s  9
0xc793b  brfalse.s loc_C7970
0xc793d  ldloc.s  9
0xc793f  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Navigation.JournalEntry::NameProperty
0xc7944  callvirt instance object [WindowsBase]System.Windows.DependencyObject::GetValue(class [WindowsBase]System.Windows.DependencyProperty)
0xc7949  castclass [mscorlib]System.String
0xc794e  stloc.s  4
0xc7950  ldloc.s  4
0xc7952  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc7957  brfalse.s loc_C7970
0xc7959  ldloc.s  9
0xc795b  isinst   System.Windows.Controls.Page
0xc7960  brfalse.s loc_C7970
0xc7962  ldloc.s  9
0xc7964  isinst   System.Windows.Controls.Page
0xc7969  callvirt instance string System.Windows.Controls.Page::get_Title()
0xc796e  stloc.s  4
0xc7970  ldloc.s  4
0xc7972  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc7977  brtrue.s loc_C79B8
0xc7979  ldarg.0
0xc797a  ldfld    class [System]System.Uri System.Windows.Navigation.NavigationService::_currentSource
0xc797f  ldnull
0xc7980  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xc7985  brfalse  loc_C7A6E
0xc798a  ldarg.0
0xc798b  ldfld    class [System]System.Uri System.Windows.Navigation.NavigationService::_currentSource
0xc7990  call     string MS.Internal.Utility.BindUriHelper::GetFragment(class [System]System.Uri uri)
0xc7995  stloc.s  0xA
0xc7997  ldloc.s  0xA
0xc7999  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc799e  brtrue   loc_C7A6E
0xc79a3  ldloc.s  4
0xc79a5  ldstr    asc_29CD98// "#"
0xc79aa  ldloc.s  0xA
0xc79ac  call     string [mscorlib]System.String::Concat(string, string, string)
0xc79b1  stloc.s  4
0xc79b3  br       loc_C7A6E
0xc79b8  ldarg.0
0xc79b9  call     instance class MS.Internal.AppModel.JournalNavigationScope System.Windows.Navigation.NavigationService::get_JournalScope()
0xc79be  brfalse.s loc_C79D2
0xc79c0  ldarg.0
0xc79c1  call     instance class MS.Internal.AppModel.JournalNavigationScope System.Windows.Navigation.NavigationService::get_JournalScope()
0xc79c6  callvirt instance class MS.Internal.AppModel.INavigatorBase MS.Internal.AppModel.JournalNavigationScope::get_NavigatorHost()
0xc79cb  isinst   System.Windows.Navigation.NavigationWindow
0xc79d0  br.s     loc_C79D3
0xc79d2  ldnull
0xc79d3  stloc.s  0xB
0xc79d5  ldloc.s  0xB
0xc79d7  brfalse.s loc_C7A40
0xc79d9  ldarg.0
0xc79da  ldloc.s  0xB
0xc79dc  callvirt instance class System.Windows.Navigation.NavigationService System.Windows.Navigation.NavigationWindow::get_NavigationService()
0xc79e1  bne.un.s loc_C7A40
0xc79e3  ldloc.s  0xB
0xc79e5  callvirt instance string System.Windows.Window::get_Title()
0xc79ea  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc79ef  brtrue.s loc_C7A40
0xc79f1  ldarg.0
0xc79f2  call     instance class [System]System.Uri System.Windows.Navigation.NavigationService::get_CurrentSource()
0xc79f7  ldnull
0xc79f8  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xc79fd  brfalse.s loc_C7A35
0xc79ff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xc7a04  ldstr    a01_1// "{0} ({1})"
0xc7a09  ldc.i4.2
0xc7a0a  newarr   [mscorlib]System.Object
0xc7a0f  dup
0xc7a10  ldc.i4.0
0xc7a11  ldloc.s  0xB
0xc7a13  callvirt instance string System.Windows.Window::get_Title()
0xc7a18  stelem.ref
0xc7a19  dup
0xc7a1a  ldc.i4.1
0xc7a1b  ldarg.0
0xc7a1c  ldfld    class [System]System.Uri System.Windows.Navigation.NavigationService::_currentSource
0xc7a21  call     class [System]System.Uri [PresentationCore]MS.Internal.AppModel.SiteOfOriginContainer::get_SiteOfOrigin()
0xc7a26  call     string System.Windows.Navigation.JournalEntry::GetDisplayName(class [System]System.Uri uri, class [System]System.Uri siteOfOrigin)
0xc7a2b  stelem.ref
0xc7a2c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc7a31  stloc.s  4
0xc7a33  br.s     loc_C7A6E
0xc7a35  ldloc.s  0xB
0xc7a37  callvirt instance string System.Windows.Window::get_Title()
0xc7a3c  stloc.s  4
0xc7a3e  br.s     loc_C7A6E
0xc7a40  ldarg.0
0xc7a41  call     instance class [System]System.Uri System.Windows.Navigation.NavigationService::get_CurrentSource()
0xc7a46  ldnull
0xc7a47  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xc7a4c  brfalse.s loc_C7A62
0xc7a4e  ldarg.0
0xc7a4f  ldfld    class [System]System.Uri System.Windows.Navigation.NavigationService::_currentSource
0xc7a54  call     class [System]System.Uri [PresentationCore]MS.Internal.AppModel.SiteOfOriginContainer::get_SiteOfOrigin()
0xc7a59  call     string System.Windows.Navigation.JournalEntry::GetDisplayName(class [System]System.Uri uri, class [System]System.Uri siteOfOrigin)
0xc7a5e  stloc.s  4
0xc7a60  br.s     loc_C7A6E
0xc7a62  ldstr    aUntitled// "Untitled"
0xc7a67  call     string System.Windows.SR::Get(string id)
0xc7a6c  stloc.s  4
0xc7a6e  ldloc.0
0xc7a6f  ldloc.s  4
0xc7a71  callvirt instance void System.Windows.Navigation.JournalEntry::set_Name(string value)
0xc7a76  ldarg.1
0xc7a77  ldc.i4.1
0xc7a78  bne.un.s loc_C7A86
0xc7a7a  ldloc.0
0xc7a7b  ldarg.0
0xc7a7c  ldfld    object System.Windows.Navigation.NavigationService::_bp
0xc7a81  callvirt instance void System.Windows.Navigation.JournalEntry::SaveState(object contentObject)
0xc7a86  ldloc.0
0xc7a87  ret
```
