# System.Web.UI.Design.WebControls.CreateDataSourceDialog::CreateNewDataSource

- ea: `0x19200`
- end: `0x193a8`
- name: `System.Web.UI.Design.WebControls.CreateDataSourceDialog::CreateNewDataSource`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x199c0`

## callees

- `0xe160`
- `0xe1c0`
- `0xe420`
- `0xe480`
- `0x12d20`
- `0x19200`
- `0x196f0`
- `0x19770`
- `0x52bb0`
- `0x8eec0`
- `0x8ef40`

## string_xrefs

- `0x1927b`: `CreateDataSource_NameNotValid`
- `0x192d4`: `CreateDataSource_NameNotUnique`

## pseudocode

```c

```

## disassembly

```asm
0x19200  ldarg.0
0x19201  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.CreateDataSourceDialog::_idTextBox
0x19206  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x1920b  stloc.0
0x1920c  ldsfld   string [mscorlib]System.String::Empty
0x19211  stloc.1
0x19212  ldarg.1
0x19213  ldnull
0x19214  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x19219  brfalse  loc_193A3
0x1921e  ldarg.1
0x1921f  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x19224  stloc.2
0x19225  ldloc.2
0x19226  brfalse  loc_193A3
0x1922b  ldloc.2
0x1922c  isinst   [System.Web]System.Web.UI.Control
0x19231  stloc.3
0x19232  ldloc.3
0x19233  brfalse  loc_193A3
0x19238  ldloc.3
0x19239  ldloc.0
0x1923a  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1923f  ldarg.0
0x19240  call     instance class [System]System.ComponentModel.ISite System.Web.UI.Design.WebControls.CreateDataSourceDialog::GetSite()
0x19245  stloc.s  4
0x19247  ldloc.s  4
0x19249  brfalse  loc_193A3
0x1924e  ldloc.s  4
0x19250  ldtoken  [System]System.ComponentModel.Design.Serialization.INameCreationService
0x19255  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1925a  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x1925f  castclass [System]System.ComponentModel.Design.Serialization.INameCreationService
0x19264  stloc.s  5
0x19266  ldloc.s  5
0x19268  brfalse  loc_192F1
0x1926d  ldloc.s  5
0x1926f  ldloc.0
0x19270  callvirt instance void [System]System.ComponentModel.Design.Serialization.INameCreationService::ValidateName(string)
0x19275  leave.s  loc_192AE
0x19277  stloc.s  8
0x19279  ldloc.s  4
0x1927b  ldstr    aCreatedatasour// "CreateDataSource_NameNotValid"
0x19280  ldc.i4.1
0x19281  newarr   [mscorlib]System.Object
0x19286  dup
0x19287  ldc.i4.0
0x19288  ldloc.s  8
0x1928a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1928f  stelem.ref
0x19290  call     string System.Design.SR::GetString(string name, object[] args)
0x19295  call     void System.Web.UI.Design.Util.UIServiceHelper::ShowError(class [mscorlib]System.IServiceProvider serviceProvider, string message)
0x1929a  ldarg.0
0x1929b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.CreateDataSourceDialog::_idTextBox
0x192a0  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::Focus()
0x192a5  pop
0x192a6  ldloc.1
0x192a7  stloc.s  9
0x192a9  leave    loc_193A5
0x192ae  ldloc.s  4
0x192b0  callvirt instance class [System]System.ComponentModel.IContainer [System]System.ComponentModel.ISite::get_Container()
0x192b5  stloc.s  7
0x192b7  ldloc.s  7
0x192b9  brfalse.s loc_192F1
0x192bb  ldloc.s  7
0x192bd  callvirt instance class [System]System.ComponentModel.ComponentCollection [System]System.ComponentModel.IContainer::get_Components()
0x192c2  stloc.s  0xA
0x192c4  ldloc.s  0xA
0x192c6  brfalse.s loc_192F1
0x192c8  ldloc.s  0xA
0x192ca  ldloc.0
0x192cb  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.ComponentCollection::get_Item(string)
0x192d0  brfalse.s loc_192F1
0x192d2  ldloc.s  4
0x192d4  ldstr    aCreatedatasour_0// "CreateDataSource_NameNotUnique"
0x192d9  call     string System.Design.SR::GetString(string name)
0x192de  call     void System.Web.UI.Design.Util.UIServiceHelper::ShowError(class [mscorlib]System.IServiceProvider serviceProvider, string message)
0x192e3  ldarg.0
0x192e4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.CreateDataSourceDialog::_idTextBox
0x192e9  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::Focus()
0x192ee  pop
0x192ef  ldloc.1
0x192f0  ret
0x192f1  ldloc.s  4
0x192f3  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0x192f8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x192fd  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x19302  castclass [System]System.ComponentModel.Design.IDesignerHost
0x19307  stloc.s  6
0x19309  ldloc.s  6
0x1930b  brfalse  loc_193A3
0x19310  ldloc.s  6
0x19312  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.IDesignerHost::get_RootComponent()
0x19317  stloc.s  0xB
0x19319  ldloc.s  0xB
0x1931b  brfalse  loc_193A3
0x19320  ldloc.s  6
0x19322  ldloc.s  0xB
0x19324  callvirt instance class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.Design.IDesignerHost::GetDesigner(class [System]System.ComponentModel.IComponent)
0x19329  isinst   System.Web.UI.Design.WebFormsRootDesigner
0x1932e  stloc.s  0xC
0x19330  ldloc.s  0xC
0x19332  brfalse.s loc_193A3
0x19334  ldarg.0
0x19335  call     instance class [System]System.ComponentModel.IComponent System.Web.UI.Design.WebControls.CreateDataSourceDialog::GetComponent()
0x1933a  isinst   [System.Web]System.Web.UI.Control
0x1933f  stloc.s  0xD
0x19341  ldloc.s  0xC
0x19343  ldloc.3
0x19344  ldloc.s  0xD
0x19346  ldc.i4.1
0x19347  callvirt instance string System.Web.UI.Design.WebFormsRootDesigner::AddControlToDocument(class [System.Web]System.Web.UI.Control newControl, class [System.Web]System.Web.UI.Control referenceControl, valuetype System.Web.UI.Design.ControlLocation location)
0x1934c  stloc.1
0x1934d  ldloc.s  6
0x1934f  ldloc.3
0x19350  callvirt instance class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.Design.IDesignerHost::GetDesigner(class [System]System.ComponentModel.IComponent)
0x19355  stloc.s  0xE
0x19357  ldloc.s  0xE
0x19359  isinst   System.Web.UI.Design.IDataSourceDesigner
0x1935e  stloc.s  0xF
0x19360  ldloc.s  0xF
0x19362  brfalse.s loc_1937E
0x19364  ldloc.s  0xF
0x19366  callvirt instance bool System.Web.UI.Design.IDataSourceDesigner::get_CanConfigure()
0x1936b  brfalse.s loc_193A3
0x1936d  ldarg.0
0x1936e  ldfld    bool System.Web.UI.Design.WebControls.CreateDataSourceDialog::_configure
0x19373  brfalse.s loc_193A3
0x19375  ldloc.s  0xF
0x19377  callvirt instance void System.Web.UI.Design.IDataSourceDesigner::Configure()
0x1937c  br.s     loc_193A3
0x1937e  ldloc.s  0xE
0x19380  isinst   System.Web.UI.Design.IHierarchicalDataSourceDesigner
0x19385  stloc.s  0x10
0x19387  ldloc.s  0x10
0x19389  brfalse.s loc_193A3
0x1938b  ldloc.s  0x10
0x1938d  callvirt instance bool System.Web.UI.Design.IHierarchicalDataSourceDesigner::get_CanConfigure()
0x19392  brfalse.s loc_193A3
0x19394  ldarg.0
0x19395  ldfld    bool System.Web.UI.Design.WebControls.CreateDataSourceDialog::_configure
0x1939a  brfalse.s loc_193A3
0x1939c  ldloc.s  0x10
0x1939e  callvirt instance void System.Web.UI.Design.IHierarchicalDataSourceDesigner::Configure()
0x193a3  ldloc.1
0x193a4  ret
0x193a5  ldloc.s  9
0x193a7  ret
```
