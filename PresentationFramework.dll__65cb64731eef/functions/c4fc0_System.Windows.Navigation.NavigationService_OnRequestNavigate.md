# System.Windows.Navigation.NavigationService::OnRequestNavigate

- ea: `0xc4fc0`
- end: `0xc51a5`
- name: `System.Windows.Navigation.NavigationService::OnRequestNavigate`
- size: `485`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callees

- `0x61c0`
- `0x38c40`
- `0x38c70`
- `0xc4fc0`
- `0xc55f0`
- `0xc56e0`
- `0xc5920`
- `0xc5fa0`
- `0xc7cb0`
- `0xc7e80`
- `0xc82e0`
- `0xc98f0`
- `0xc9900`
- `0x23f9c0`
- `0x240cd0`
- `0x241ac0`
- `0x24e9c0`
- `0x2675b0`

## string_xrefs

- `0xc5013`: `MustImplementIUriContext`
- `0xc5184`: `FailToNavigateUsingHyperlinkTarget`
- `0xc5194`: `HyperLinkTargetNotFound`

## pseudocode

```c

```

## disassembly

```asm
0xc4fc0  newobj   instance void <>c__DisplayClass2_0::.ctor()
0xc4fc5  stloc.0
0xc4fc6  ldarg.2
0xc4fc7  ldc.i4.1
0xc4fc8  callvirt instance void [PresentationCore]System.Windows.RoutedEventArgs::set_Handled(bool)
0xc4fcd  ldarg.2
0xc4fce  callvirt instance string System.Windows.Navigation.RequestNavigateEventArgs::get_Target()
0xc4fd3  stloc.1
0xc4fd4  ldloc.0
0xc4fd5  ldarg.2
0xc4fd6  callvirt instance class [System]System.Uri System.Windows.Navigation.RequestNavigateEventArgs::get_Uri()
0xc4fdb  stfld    class [System]System.Uri <>c__DisplayClass2_0::bpu
0xc4fe0  ldloc.0
0xc4fe1  ldfld    class [System]System.Uri <>c__DisplayClass2_0::bpu
0xc4fe6  ldnull
0xc4fe7  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xc4fec  brfalse.s loc_C504F
0xc4fee  ldloc.0
0xc4fef  ldfld    class [System]System.Uri <>c__DisplayClass2_0::bpu
0xc4ff4  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0xc4ff9  brtrue.s loc_C504F
0xc4ffb  ldarg.2
0xc4ffc  callvirt instance object [PresentationCore]System.Windows.RoutedEventArgs::get_OriginalSource()
0xc5001  isinst   [WindowsBase]System.Windows.DependencyObject
0xc5006  stloc.3
0xc5007  ldloc.3
0xc5008  isinst   [System.Xaml]System.Windows.Markup.IUriContext
0xc500d  stloc.s  4
0xc500f  ldloc.s  4
0xc5011  brtrue.s loc_C5036
0xc5013  ldstr    aMustimplementi// "MustImplementIUriContext"
0xc5018  ldc.i4.1
0xc5019  newarr   [mscorlib]System.Object
0xc501e  dup
0xc501f  ldc.i4.0
0xc5020  ldtoken  [System.Xaml]System.Windows.Markup.IUriContext
0xc5025  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc502a  stelem.ref
0xc502b  call     string System.Windows.SR::Get(string id, object[] args)
0xc5030  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0xc5035  throw
0xc5036  ldloc.0
0xc5037  ldloc.3
0xc5038  ldloc.s  4
0xc503a  callvirt instance class [System]System.Uri [System.Xaml]System.Windows.Markup.IUriContext::get_BaseUri()
0xc503f  ldarg.2
0xc5040  callvirt instance class [System]System.Uri System.Windows.Navigation.RequestNavigateEventArgs::get_Uri()
0xc5045  call     class [System]System.Uri MS.Internal.Utility.BindUriHelper::GetUriToNavigate(class [WindowsBase]System.Windows.DependencyObject element, class [System]System.Uri baseUri, class [System]System.Uri inputUri)
0xc504a  stfld    class [System]System.Uri <>c__DisplayClass2_0::bpu
0xc504f  ldloc.0
0xc5050  ldnull
0xc5051  stfld    class MS.Internal.AppModel.INavigatorBase <>c__DisplayClass2_0::navigator
0xc5056  ldc.i4.1
0xc5057  stloc.2
0xc5058  ldloc.1
0xc5059  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc505e  brtrue   loc_C50E3
0xc5063  ldloc.0
0xc5064  ldarg.0
0xc5065  ldloc.1
0xc5066  call     instance class MS.Internal.AppModel.INavigatorBase System.Windows.Navigation.NavigationService::FindTarget(string name)
0xc506b  stfld    class MS.Internal.AppModel.INavigatorBase <>c__DisplayClass2_0::navigator
0xc5070  ldloc.0
0xc5071  ldfld    class MS.Internal.AppModel.INavigatorBase <>c__DisplayClass2_0::navigator
0xc5076  brtrue.s loc_C5092
0xc5078  ldarg.0
0xc5079  call     instance class MS.Internal.AppModel.JournalNavigationScope System.Windows.Navigation.NavigationService::get_JournalScope()
0xc507e  brfalse.s loc_C5092
0xc5080  ldloc.0
0xc5081  ldarg.0
0xc5082  call     instance class MS.Internal.AppModel.JournalNavigationScope System.Windows.Navigation.NavigationService::get_JournalScope()
0xc5087  ldloc.1
0xc5088  callvirt instance class MS.Internal.AppModel.INavigatorBase MS.Internal.AppModel.JournalNavigationScope::FindTarget(string name)
0xc508d  stfld    class MS.Internal.AppModel.INavigatorBase <>c__DisplayClass2_0::navigator
0xc5092  ldloc.0
0xc5093  ldfld    class MS.Internal.AppModel.INavigatorBase <>c__DisplayClass2_0::navigator
0xc5098  brtrue.s loc_C50EF
0xc509a  ldarg.0
0xc509b  call     instance class System.Windows.Navigation.NavigationWindow System.Windows.Navigation.NavigationService::FindNavigationWindow()
0xc50a0  stloc.s  5
0xc50a2  ldloc.s  5
0xc50a4  brfalse.s loc_C50B4
0xc50a6  ldloc.0
0xc50a7  ldloc.s  5
0xc50a9  ldloc.1
0xc50aa  call     class MS.Internal.AppModel.INavigatorBase System.Windows.Navigation.NavigationService::FindTargetInNavigationWindow(class System.Windows.Navigation.NavigationWindow navigationWindow, string navigatorId)
0xc50af  stfld    class MS.Internal.AppModel.INavigatorBase <>c__DisplayClass2_0::navigator
0xc50b4  ldloc.0
0xc50b5  ldfld    class MS.Internal.AppModel.INavigatorBase <>c__DisplayClass2_0::navigator
0xc50ba  brtrue.s loc_C50EF
0xc50bc  ldloc.0
0xc50bd  ldloc.1
0xc50be  call     class MS.Internal.AppModel.INavigatorBase System.Windows.Navigation.NavigationService::FindTargetInApplication(string targetName)
0xc50c3  stfld    class MS.Internal.AppModel.INavigatorBase <>c__DisplayClass2_0::navigator
0xc50c8  ldloc.0
0xc50c9  ldfld    class MS.Internal.AppModel.INavigatorBase <>c__DisplayClass2_0::navigator
0xc50ce  brfalse.s loc_C50EF
0xc50d0  ldloc.0
0xc50d1  ldfld    class MS.Internal.AppModel.INavigatorBase <>c__DisplayClass2_0::navigator
0xc50d6  castclass [WindowsBase]System.Windows.Threading.DispatcherObject
0xc50db  callvirt instance bool [WindowsBase]System.Windows.Threading.DispatcherObject::CheckAccess()
0xc50e0  stloc.2
0xc50e1  br.s     loc_C50EF
0xc50e3  ldloc.0
0xc50e4  ldarg.0
0xc50e5  call     instance class MS.Internal.AppModel.INavigator System.Windows.Navigation.NavigationService::get_INavigatorHost()
0xc50ea  stfld    class MS.Internal.AppModel.INavigatorBase <>c__DisplayClass2_0::navigator
0xc50ef  ldloc.0
0xc50f0  ldfld    class MS.Internal.AppModel.INavigatorBase <>c__DisplayClass2_0::navigator
0xc50f5  brfalse.s loc_C5133
0xc50f7  ldloc.2
0xc50f8  brfalse.s loc_C510D
0xc50fa  ldloc.0
0xc50fb  ldfld    class MS.Internal.AppModel.INavigatorBase <>c__DisplayClass2_0::navigator
0xc5100  ldloc.0
0xc5101  ldfld    class [System]System.Uri <>c__DisplayClass2_0::bpu
0xc5106  callvirt instance bool MS.Internal.AppModel.INavigatorBase::Navigate(class [System]System.Uri source)
0xc510b  pop
0xc510c  ret
0xc510d  ldloc.0
0xc510e  ldfld    class MS.Internal.AppModel.INavigatorBase <>c__DisplayClass2_0::navigator
0xc5113  castclass [WindowsBase]System.Windows.Threading.DispatcherObject
0xc5118  callvirt instance class [WindowsBase]System.Windows.Threading.Dispatcher [WindowsBase]System.Windows.Threading.DispatcherObject::get_Dispatcher()
0xc511d  ldc.i4.s 0xA
0xc511f  ldloc.0
0xc5120  ldftn    instance object <>c__DisplayClass2_0::<OnRequestNavigate>b__0(object unused)
0xc5126  newobj   instance void [WindowsBase]System.Windows.Threading.DispatcherOperationCallback::.ctor(object, native int)
0xc512b  ldnull
0xc512c  callvirt instance class [WindowsBase]System.Windows.Threading.DispatcherOperation [WindowsBase]System.Windows.Threading.Dispatcher::BeginInvoke(valuetype [WindowsBase]System.Windows.Threading.DispatcherPriority, class [mscorlib]System.Delegate, object)
0xc5131  pop
0xc5132  ret
0xc5133  call     bool System.Windows.Application::InBrowserHostedApp()
0xc5138  brfalse.s loc_C5194
0xc513a  ldc.i4.1
0xc513b  stloc.s  6
0xc513d  ldloc.0
0xc513e  ldfld    class [System]System.Uri <>c__DisplayClass2_0::bpu
0xc5143  callvirt instance string [System]System.Uri::get_Scheme()
0xc5148  call     class [System]System.Uri [PresentationCore]System.Windows.Navigation.BaseUriHelper::get_PackAppBaseUri()
0xc514d  callvirt instance string [System]System.Uri::get_Scheme()
0xc5152  call     bool [PresentationCore]MS.Internal.SecurityHelper::AreStringTypesEqual(string, string)
0xc5157  brfalse.s loc_C516A
0xc5159  ldloc.0
0xc515a  ldloc.0
0xc515b  ldfld    class [System]System.Uri <>c__DisplayClass2_0::bpu
0xc5160  call     class [System]System.Uri [PresentationCore]System.Windows.Navigation.BaseUriHelper::ConvertPackUriToAbsoluteExternallyVisibleUri(class [System]System.Uri)
0xc5165  stfld    class [System]System.Uri <>c__DisplayClass2_0::bpu
0xc516a  ldarg.0
0xc516b  call     instance class [System]System.Uri System.Windows.Navigation.NavigationService::get_CurrentSource()
0xc5170  ldloc.0
0xc5171  ldfld    class [System]System.Uri <>c__DisplayClass2_0::bpu
0xc5176  ldloc.1
0xc5177  ldc.i4.1
0xc5178  call     valuetype MS.Internal.AppModel.LaunchResult MS.Internal.AppModel.AppSecurityManager::SafeLaunchBrowserOnlyIfPossible(class [System]System.Uri originatingUri, class [System]System.Uri destinationUri, string targetName, bool fIsTopLevel)
0xc517d  stloc.s  6
0xc517f  ldloc.s  6
0xc5181  ldc.i4.1
0xc5182  bne.un.s loc_C51A4
0xc5184  ldstr    aFailtonavigate// "FailToNavigateUsingHyperlinkTarget"
0xc5189  call     string System.Windows.SR::Get(string id)
0xc518e  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0xc5193  throw
0xc5194  ldstr    aHyperlinktarge// "HyperLinkTargetNotFound"
0xc5199  call     string System.Windows.SR::Get(string id)
0xc519e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xc51a3  throw
0xc51a4  ret
```
