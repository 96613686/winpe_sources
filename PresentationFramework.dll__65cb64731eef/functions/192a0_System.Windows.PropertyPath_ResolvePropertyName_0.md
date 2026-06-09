# System.Windows.PropertyPath::ResolvePropertyName_0

- ea: `0x192a0`
- end: `0x19473`
- name: `System.Windows.PropertyPath::ResolvePropertyName_0`
- size: `467`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18e00`
- `0x19180`

## callees

- `0x18c10`
- `0x192a0`
- `0x19480`
- `0x197b0`
- `0x198e0`
- `0x19910`
- `0x19950`
- `0x38c70`
- `0x1dc410`
- `0x1dc430`

## string_xrefs

- `0x192d6`: `PropertyPathInvalidAccessor`
- `0x1930a`: `PathParametersIndexOutOfRange`
- `0x1939a`: `PropertyPathNoOwnerType`
- `0x1944b`: `PropertyPathNoProperty`

## pseudocode

```c

```

## disassembly

```asm
0x192a0  ldarg.1
0x192a1  stloc.0
0x192a2  ldarg.1
0x192a3  ldloca.s 1
0x192a5  call     bool System.Windows.PropertyPath::IsParameterIndex(string name, [out] int32& index)
0x192aa  brfalse  loc_1933E
0x192af  ldc.i4.0
0x192b0  ldloc.1
0x192b1  bgt.s    loc_19306
0x192b3  ldloc.1
0x192b4  ldarg.0
0x192b5  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<object> System.Windows.PropertyPath::get_PathParameters()
0x192ba  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::get_Count()
0x192bf  bge.s    loc_19306
0x192c1  ldarg.0
0x192c2  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<object> System.Windows.PropertyPath::get_PathParameters()
0x192c7  ldloc.1
0x192c8  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::get_Item(!!T0)
0x192cd  stloc.2
0x192ce  ldloc.2
0x192cf  call     bool System.Windows.PropertyPath::IsValidAccessor(object accessor)
0x192d4  brtrue.s loc_19304
0x192d6  ldstr    aPropertypathin// "PropertyPathInvalidAccessor"
0x192db  ldc.i4.1
0x192dc  newarr   [mscorlib]System.Object
0x192e1  dup
0x192e2  ldc.i4.0
0x192e3  ldloc.2
0x192e4  brtrue.s loc_192ED
0x192e6  ldstr    aNull// "null"
0x192eb  br.s     loc_192F8
0x192ed  ldloc.2
0x192ee  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x192f3  callvirt instance string [mscorlib]System.Type::get_FullName()
0x192f8  stelem.ref
0x192f9  call     string System.Windows.SR::Get(string id, object[] args)
0x192fe  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x19303  throw
0x19304  ldloc.2
0x19305  ret
0x19306  ldarg.s  5
0x19308  brfalse.s loc_1933C
0x1930a  ldstr    aPathparameters// "PathParametersIndexOutOfRange"
0x1930f  ldc.i4.2
0x19310  newarr   [mscorlib]System.Object
0x19315  dup
0x19316  ldc.i4.0
0x19317  ldloc.1
0x19318  box      [mscorlib]System.Int32
0x1931d  stelem.ref
0x1931e  dup
0x1931f  ldc.i4.1
0x19320  ldarg.0
0x19321  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<object> System.Windows.PropertyPath::get_PathParameters()
0x19326  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::get_Count()
0x1932b  box      [mscorlib]System.Int32
0x19330  stelem.ref
0x19331  call     string System.Windows.SR::Get(string id, object[] args)
0x19336  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1933b  throw
0x1933c  ldnull
0x1933d  ret
0x1933e  ldarg.1
0x1933f  call     bool System.Windows.PropertyPath::IsPropertyReference(string name)
0x19344  brfalse.s loc_193B7
0x19346  ldarg.1
0x19347  ldc.i4.1
0x19348  ldarg.1
0x19349  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1934e  ldc.i4.2
0x1934f  sub
0x19350  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x19355  starg.s  1
0x19357  ldarg.1
0x19358  ldc.i4.s 0x2E
0x1935a  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0x1935f  stloc.3
0x19360  ldloc.3
0x19361  ldc.i4.0
0x19362  blt.s    loc_193B5
0x19364  ldarg.1
0x19365  ldloc.3
0x19366  ldc.i4.1
0x19367  add
0x19368  callvirt instance string [mscorlib]System.String::Substring(int32)
0x1936d  callvirt instance string [mscorlib]System.String::Trim()
0x19372  stloc.0
0x19373  ldarg.1
0x19374  ldc.i4.0
0x19375  ldloc.3
0x19376  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1937b  callvirt instance string [mscorlib]System.String::Trim()
0x19380  stloc.s  4
0x19382  ldarg.0
0x19383  ldloc.s  4
0x19385  ldarg.s  4
0x19387  call     instance class [mscorlib]System.Type System.Windows.PropertyPath::GetTypeFromName(string name, object context)
0x1938c  starg.s  3
0x1938e  ldarg.3
0x1938f  ldnull
0x19390  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x19395  ldarg.s  5
0x19397  and
0x19398  brfalse.s loc_193B7
0x1939a  ldstr    aPropertypathno// "PropertyPathNoOwnerType"
0x1939f  ldc.i4.1
0x193a0  newarr   [mscorlib]System.Object
0x193a5  dup
0x193a6  ldc.i4.0
0x193a7  ldloc.s  4
0x193a9  stelem.ref
0x193aa  call     string System.Windows.SR::Get(string id, object[] args)
0x193af  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x193b4  throw
0x193b5  ldarg.1
0x193b6  stloc.0
0x193b7  ldarg.3
0x193b8  ldnull
0x193b9  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x193be  brfalse  loc_19471
0x193c3  ldloc.0
0x193c4  ldarg.3
0x193c5  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::FromName(string, class [mscorlib]System.Type)
0x193ca  stloc.s  5
0x193cc  ldloc.s  5
0x193ce  brtrue.s loc_193E6
0x193d0  ldarg.2
0x193d1  isinst   [System]System.ComponentModel.ICustomTypeDescriptor
0x193d6  brfalse.s loc_193E6
0x193d8  ldarg.2
0x193d9  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x193de  ldloc.0
0x193df  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x193e4  stloc.s  5
0x193e6  ldloc.s  5
0x193e8  brtrue.s loc_19404
0x193ea  ldarg.2
0x193eb  isinst   [System]System.ComponentModel.INotifyPropertyChanged
0x193f0  brtrue.s loc_193FA
0x193f2  ldarg.2
0x193f3  isinst   [WindowsBase]System.Windows.DependencyObject
0x193f8  brfalse.s loc_19404
0x193fa  ldarg.0
0x193fb  ldarg.3
0x193fc  ldloc.0
0x193fd  call     instance class [mscorlib]System.Reflection.PropertyInfo System.Windows.PropertyPath::GetPropertyHelper(class [mscorlib]System.Type ownerType, string propertyName)
0x19402  stloc.s  5
0x19404  ldloc.s  5
0x19406  brtrue.s loc_19419
0x19408  ldarg.2
0x19409  brfalse.s loc_19419
0x1940b  ldarg.2
0x1940c  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x19411  ldloc.0
0x19412  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x19417  stloc.s  5
0x19419  ldloc.s  5
0x1941b  brtrue.s loc_19427
0x1941d  ldarg.0
0x1941e  ldarg.3
0x1941f  ldloc.0
0x19420  call     instance class [mscorlib]System.Reflection.PropertyInfo System.Windows.PropertyPath::GetPropertyHelper(class [mscorlib]System.Type ownerType, string propertyName)
0x19425  stloc.s  5
0x19427  ldloc.s  5
0x19429  brtrue.s loc_19441
0x1942b  ldarg.2
0x1942c  call     bool MS.Internal.SystemCoreHelper::IsIDynamicMetaObjectProvider(object item)
0x19431  brfalse.s loc_19441
0x19433  ldarg.2
0x19434  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x19439  ldloc.0
0x1943a  call     object MS.Internal.SystemCoreHelper::NewDynamicPropertyAccessor(class [mscorlib]System.Type ownerType, string propertyName)
0x1943f  stloc.s  5
0x19441  ldloc.s  5
0x19443  ldnull
0x19444  ceq
0x19446  ldarg.s  5
0x19448  and
0x19449  brfalse.s loc_1946E
0x1944b  ldstr    aPropertypathno_0// "PropertyPathNoProperty"
0x19450  ldc.i4.2
0x19451  newarr   [mscorlib]System.Object
0x19456  dup
0x19457  ldc.i4.0
0x19458  ldarg.3
0x19459  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1945e  stelem.ref
0x1945f  dup
0x19460  ldc.i4.1
0x19461  ldloc.0
0x19462  stelem.ref
0x19463  call     string System.Windows.SR::Get(string id, object[] args)
0x19468  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1946d  throw
0x1946e  ldloc.s  5
0x19470  ret
0x19471  ldnull
0x19472  ret
```
