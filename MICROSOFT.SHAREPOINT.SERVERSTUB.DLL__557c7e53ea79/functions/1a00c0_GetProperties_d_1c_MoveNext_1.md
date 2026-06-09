# <GetProperties>d__1c::MoveNext_1

- ea: `0x1a00c0`
- end: `0x1a116d`
- name: `<GetProperties>d__1c::MoveNext_1`
- size: `4269`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0xa7660`
- `0x1a00c0`
- `0x1a1190`
- `0x1a11f0`

## string_xrefs

- `0x1a0615`: `Created`
- `0x1a068f`: `Created`
- `0x1a0451`: `AutoStartCreate`
- `0x1a04c3`: `AutoStartCreate`
- `0x1a0fb3`: `TaskListTitle`
- `0x1a1020`: `TaskListTitle`

## pseudocode

```c

```

## disassembly

```asm
0x1a00c0  ldarg.0
0x1a00c1  ldfld    int32 <GetProperties>d__1c::<>1__state
0x1a00c6  stloc.1
0x1a00c7  ldloc.1
0x1a00c8  switch   loc_1A0126, loc_1A1160, loc_1A0190, loc_1A0281, loc_1A035A, loc_1A0438, loc_1A0516, loc_1A05FC, loc_1A06E2, loc_1A07BC, loc_1A089B, loc_1A0975, loc_1A0A5D, loc_1A0B37, loc_1A0C11, loc_1A0CF0, loc_1A0DD8, loc_1A0EC0, loc_1A0F9A, loc_1A1074, loc_1A1159
0x1a0121  br       loc_1A1160
0x1a0126  ldarg.0
0x1a0127  ldc.i4.m1
0x1a0128  stfld    int32 <GetProperties>d__1c::<>1__state
0x1a012d  ldarg.0
0x1a012e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__1c::proxyContext
0x1a0133  brtrue.s loc_1A0140
0x1a0135  ldstr    aProxycontext// "proxyContext"
0x1a013a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1a013f  throw
0x1a0140  ldarg.0
0x1a0141  ldarg.0
0x1a0142  ldfld    class Microsoft.SharePoint.ServerStub.Workflow.SPWorkflowAssociationServerStub <GetProperties>d__1c::<>4__this
0x1a0147  ldarg.0
0x1a0148  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__1c::proxyContext
0x1a014d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.Workflow.SPWorkflowAssociationServerStub::<>n__FabricatedMethod20(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x1a0152  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x1a0157  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1c::<>7__wrap1e
0x1a015c  ldarg.0
0x1a015d  ldc.i4.1
0x1a015e  stfld    int32 <GetProperties>d__1c::<>1__state
0x1a0163  br.s     loc_1A0197
0x1a0165  ldarg.0
0x1a0166  ldarg.0
0x1a0167  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1c::<>7__wrap1e
0x1a016c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x1a0171  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<item>5__1d
0x1a0176  ldarg.0
0x1a0177  ldarg.0
0x1a0178  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<item>5__1d
0x1a017d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>2__current
0x1a0182  ldarg.0
0x1a0183  ldc.i4.2
0x1a0184  stfld    int32 <GetProperties>d__1c::<>1__state
0x1a0189  ldc.i4.1
0x1a018a  stloc.0
0x1a018b  leave    loc_1A116B
0x1a0190  ldarg.0
0x1a0191  ldc.i4.1
0x1a0192  stfld    int32 <GetProperties>d__1c::<>1__state
0x1a0197  ldarg.0
0x1a0198  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__1c::<>7__wrap1e
0x1a019d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a01a2  brtrue.s loc_1A0165
0x1a01a4  ldarg.0
0x1a01a5  call     instance void <GetProperties>d__1c::<>m__Finally1f()
0x1a01aa  ldarg.0
0x1a01ab  ldarg.0
0x1a01ac  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a01b1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocala
0x1a01b6  ldarg.0
0x1a01b7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocala
0x1a01bc  ldstr    aAllowmanual// "AllowManual"
0x1a01c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a01c6  ldarg.0
0x1a01c7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocala
0x1a01cc  ldc.i4.0
0x1a01cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a01d2  ldarg.0
0x1a01d3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocala
0x1a01d8  ldc.i4.1
0x1a01d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a01de  ldarg.0
0x1a01df  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocala
0x1a01e4  ldc.i4.0
0x1a01e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1a01ea  ldarg.0
0x1a01eb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocala
0x1a01f0  ldtoken  [mscorlib]System.Boolean
0x1a01f5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a01fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1a01ff  ldarg.0
0x1a0200  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocala
0x1a0205  ldc.i4.0
0x1a0206  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1a020b  ldarg.0
0x1a020c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocala
0x1a0211  ldc.i4.1
0x1a0212  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1a0217  ldarg.0
0x1a0218  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocala
0x1a021d  ldc.i4.0
0x1a021e  box      [mscorlib]System.Boolean
0x1a0223  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1a0228  ldarg.0
0x1a0229  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocala
0x1a022e  ldstr    aAllowmanual// "AllowManual"
0x1a0233  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1a0238  ldarg.0
0x1a0239  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocala
0x1a023e  ldnull
0x1a023f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1a0244  ldarg.0
0x1a0245  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocala
0x1a024a  ldc.i4.0
0x1a024b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1a0250  ldarg.0
0x1a0251  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocala
0x1a0256  ldc.i4.0
0x1a0257  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1a025c  ldarg.0
0x1a025d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocala
0x1a0262  ldc.i4.0
0x1a0263  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1a0268  ldarg.0
0x1a0269  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocala
0x1a026e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>2__current
0x1a0273  ldarg.0
0x1a0274  ldc.i4.3
0x1a0275  stfld    int32 <GetProperties>d__1c::<>1__state
0x1a027a  ldc.i4.1
0x1a027b  stloc.0
0x1a027c  leave    loc_1A116B
0x1a0281  ldarg.0
0x1a0282  ldc.i4.m1
0x1a0283  stfld    int32 <GetProperties>d__1c::<>1__state
0x1a0288  ldarg.0
0x1a0289  ldarg.0
0x1a028a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a028f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1a0294  ldarg.0
0x1a0295  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1a029a  ldstr    aAssociationdat// "AssociationData"
0x1a029f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a02a4  ldarg.0
0x1a02a5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1a02aa  ldc.i4.0
0x1a02ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a02b0  ldarg.0
0x1a02b1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1a02b6  ldc.i4.1
0x1a02b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a02bc  ldarg.0
0x1a02bd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1a02c2  ldc.i4.0
0x1a02c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1a02c8  ldarg.0
0x1a02c9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1a02ce  ldtoken  [mscorlib]System.String
0x1a02d3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a02d8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1a02dd  ldarg.0
0x1a02de  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1a02e3  ldc.i4.0
0x1a02e4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1a02e9  ldarg.0
0x1a02ea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1a02ef  ldc.i4.1
0x1a02f0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1a02f5  ldarg.0
0x1a02f6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1a02fb  ldnull
0x1a02fc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1a0301  ldarg.0
0x1a0302  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1a0307  ldstr    aAssociationdat// "AssociationData"
0x1a030c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1a0311  ldarg.0
0x1a0312  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1a0317  ldnull
0x1a0318  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1a031d  ldarg.0
0x1a031e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1a0323  ldc.i4.0
0x1a0324  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1a0329  ldarg.0
0x1a032a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1a032f  ldc.i4.0
0x1a0330  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1a0335  ldarg.0
0x1a0336  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1a033b  ldc.i4.0
0x1a033c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1a0341  ldarg.0
0x1a0342  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalb
0x1a0347  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>2__current
0x1a034c  ldarg.0
0x1a034d  ldc.i4.4
0x1a034e  stfld    int32 <GetProperties>d__1c::<>1__state
0x1a0353  ldc.i4.1
0x1a0354  stloc.0
0x1a0355  leave    loc_1A116B
0x1a035a  ldarg.0
0x1a035b  ldc.i4.m1
0x1a035c  stfld    int32 <GetProperties>d__1c::<>1__state
0x1a0361  ldarg.0
0x1a0362  ldarg.0
0x1a0363  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a0368  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1a036d  ldarg.0
0x1a036e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1a0373  ldstr    aAutostartchang// "AutoStartChange"
0x1a0378  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a037d  ldarg.0
0x1a037e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1a0383  ldc.i4.0
0x1a0384  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a0389  ldarg.0
0x1a038a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1a038f  ldc.i4.1
0x1a0390  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a0395  ldarg.0
0x1a0396  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1a039b  ldc.i4.0
0x1a039c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1a03a1  ldarg.0
0x1a03a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1a03a7  ldtoken  [mscorlib]System.Boolean
0x1a03ac  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a03b1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1a03b6  ldarg.0
0x1a03b7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1a03bc  ldc.i4.0
0x1a03bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1a03c2  ldarg.0
0x1a03c3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1a03c8  ldc.i4.1
0x1a03c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1a03ce  ldarg.0
0x1a03cf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1a03d4  ldc.i4.0
0x1a03d5  box      [mscorlib]System.Boolean
0x1a03da  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1a03df  ldarg.0
0x1a03e0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1a03e5  ldstr    aAutostartchang// "AutoStartChange"
0x1a03ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1a03ef  ldarg.0
0x1a03f0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1a03f5  ldnull
0x1a03f6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1a03fb  ldarg.0
0x1a03fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1a0401  ldc.i4.0
0x1a0402  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1a0407  ldarg.0
0x1a0408  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1a040d  ldc.i4.0
0x1a040e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1a0413  ldarg.0
0x1a0414  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1a0419  ldc.i4.0
0x1a041a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x1a041f  ldarg.0
0x1a0420  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocalc
0x1a0425  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>2__current
0x1a042a  ldarg.0
0x1a042b  ldc.i4.5
0x1a042c  stfld    int32 <GetProperties>d__1c::<>1__state
0x1a0431  ldc.i4.1
0x1a0432  stloc.0
0x1a0433  leave    loc_1A116B
0x1a0438  ldarg.0
0x1a0439  ldc.i4.m1
0x1a043a  stfld    int32 <GetProperties>d__1c::<>1__state
0x1a043f  ldarg.0
0x1a0440  ldarg.0
0x1a0441  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1a0446  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x1a044b  ldarg.0
0x1a044c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x1a0451  ldstr    aAutostartcreat// "AutoStartCreate"
0x1a0456  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1a045b  ldarg.0
0x1a045c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x1a0461  ldc.i4.0
0x1a0462  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1a0467  ldarg.0
0x1a0468  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x1a046d  ldc.i4.1
0x1a046e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1a0473  ldarg.0
0x1a0474  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x1a0479  ldc.i4.0
0x1a047a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1a047f  ldarg.0
0x1a0480  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x1a0485  ldtoken  [mscorlib]System.Boolean
0x1a048a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a048f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1a0494  ldarg.0
0x1a0495  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x1a049a  ldc.i4.0
0x1a049b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1a04a0  ldarg.0
0x1a04a1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x1a04a6  ldc.i4.1
0x1a04a7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1a04ac  ldarg.0
0x1a04ad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
0x1a04b2  ldc.i4.0
0x1a04b3  box      [mscorlib]System.Boolean
0x1a04b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1a04bd  ldarg.0
0x1a04be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__1c::<>g__initLocald
  ... truncated ...
```
