# <ValidateWopiUrlProperty>d__35::MoveNext

- ea: `0x1fce0`
- end: `0x1fe3c`
- name: `<ValidateWopiUrlProperty>d__35::MoveNext`
- size: `348`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x8710`
- `0x1fc80`
- `0x1fce0`

## pseudocode

```c

```

## disassembly

```asm
0x1fce0  ldarg.0
0x1fce1  ldfld    int32 <ValidateWopiUrlProperty>d__35::<>1__state
0x1fce6  stloc.0
0x1fce7  ldarg.0
0x1fce8  ldfld    class Microsoft.ReportingServices.Portal.Repositories.SystemService <ValidateWopiUrlProperty>d__35::<>4__this
0x1fced  stloc.1
0x1fcee  ldloc.0
0x1fcef  brfalse  loc_1FD94
0x1fcf4  ldarg.0
0x1fcf5  newobj   instance void <>c__DisplayClass35_0::.ctor()
0x1fcfa  stfld    class <>c__DisplayClass35_0 <ValidateWopiUrlProperty>d__35::<>8__1
0x1fcff  ldarg.0
0x1fd00  ldfld    class <>c__DisplayClass35_0 <ValidateWopiUrlProperty>d__35::<>8__1
0x1fd05  ldarg.0
0x1fd06  ldfld    string <ValidateWopiUrlProperty>d__35::discoveryPropertyName
0x1fd0b  stfld    string <>c__DisplayClass35_0::discoveryPropertyName
0x1fd10  ldarg.0
0x1fd11  ldfld    class <>c__DisplayClass35_0 <ValidateWopiUrlProperty>d__35::<>8__1
0x1fd16  ldarg.0
0x1fd17  ldfld    string <ValidateWopiUrlProperty>d__35::excelWopiUrlPropertyName
0x1fd1c  stfld    string <>c__DisplayClass35_0::excelWopiUrlPropertyName
0x1fd21  ldarg.0
0x1fd22  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> <ValidateWopiUrlProperty>d__35::propertyValues
0x1fd27  ldarg.0
0x1fd28  ldfld    class <>c__DisplayClass35_0 <ValidateWopiUrlProperty>d__35::<>8__1
0x1fd2d  ldftn    instance bool <>c__DisplayClass35_0::<ValidateWopiUrlProperty>b__0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property p)
0x1fd33  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool>::.ctor(object, native int)
0x1fd38  call     T0x2B000127
0x1fd3d  stloc.3
0x1fd3e  ldloc.3
0x1fd3f  brfalse  loc_1FE05
0x1fd44  ldnull
0x1fd45  stloc.s  4
0x1fd47  ldloc.3
0x1fd48  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::get_Value()
0x1fd4d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1fd52  brtrue.s loc_1FDBA
0x1fd54  ldloc.1
0x1fd55  ldloc.3
0x1fd56  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::get_Value()
0x1fd5b  call     instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.ReportingServices.Portal.Repositories.SystemService::GetExcelWopiUrl(string officeOnlineDiscoveryUrl)
0x1fd60  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x1fd65  stloc.s  5
0x1fd67  ldloca.s 5
0x1fd69  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x1fd6e  brtrue.s loc_1FDB1
0x1fd70  ldarg.0
0x1fd71  ldc.i4.0
0x1fd72  dup
0x1fd73  stloc.0
0x1fd74  stfld    int32 <ValidateWopiUrlProperty>d__35::<>1__state
0x1fd79  ldarg.0
0x1fd7a  ldloc.s  5
0x1fd7c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <ValidateWopiUrlProperty>d__35::<>u__1
0x1fd81  ldarg.0
0x1fd82  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>> <ValidateWopiUrlProperty>d__35::<>t__builder
0x1fd87  ldloca.s 5
0x1fd89  ldarg.0
0x1fd8a  call     T0x2B000128
0x1fd8f  leave    loc_1FE3B
0x1fd94  ldarg.0
0x1fd95  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <ValidateWopiUrlProperty>d__35::<>u__1
0x1fd9a  stloc.s  5
0x1fd9c  ldarg.0
0x1fd9d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <ValidateWopiUrlProperty>d__35::<>u__1
0x1fda2  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x1fda8  ldarg.0
0x1fda9  ldc.i4.m1
0x1fdaa  dup
0x1fdab  stloc.0
0x1fdac  stfld    int32 <ValidateWopiUrlProperty>d__35::<>1__state
0x1fdb1  ldloca.s 5
0x1fdb3  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x1fdb8  stloc.s  4
0x1fdba  ldarg.0
0x1fdbb  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> <ValidateWopiUrlProperty>d__35::propertyValues
0x1fdc0  ldarg.0
0x1fdc1  ldfld    class <>c__DisplayClass35_0 <ValidateWopiUrlProperty>d__35::<>8__1
0x1fdc6  ldftn    instance bool <>c__DisplayClass35_0::<ValidateWopiUrlProperty>b__1(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property p)
0x1fdcc  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool>::.ctor(object, native int)
0x1fdd1  call     T0x2B000129
0x1fdd6  ldc.i4.1
0x1fdd7  newarr   [Microsoft.ReportingServices.Portal.Interfaces]Model.Property
0x1fddc  dup
0x1fddd  ldc.i4.0
0x1fdde  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::.ctor()
0x1fde3  dup
0x1fde4  ldarg.0
0x1fde5  ldfld    class <>c__DisplayClass35_0 <ValidateWopiUrlProperty>d__35::<>8__1
0x1fdea  ldfld    string <>c__DisplayClass35_0::excelWopiUrlPropertyName
0x1fdef  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::set_Name(string)
0x1fdf4  dup
0x1fdf5  ldloc.s  4
0x1fdf7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::set_Value(string)
0x1fdfc  stelem.ref
0x1fdfd  call     T0x2B00012A
0x1fe02  stloc.2
0x1fe03  leave.s  loc_1FE27
0x1fe05  ldarg.0
0x1fe06  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> <ValidateWopiUrlProperty>d__35::propertyValues
0x1fe0b  stloc.2
0x1fe0c  leave.s  loc_1FE27
0x1fe0e  stloc.s  6
0x1fe10  ldarg.0
0x1fe11  ldc.i4.s 0xFE
0x1fe13  stfld    int32 <ValidateWopiUrlProperty>d__35::<>1__state
0x1fe18  ldarg.0
0x1fe19  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>> <ValidateWopiUrlProperty>d__35::<>t__builder
0x1fe1e  ldloc.s  6
0x1fe20  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>>::SetException(class [mscorlib]System.Exception)
0x1fe25  leave.s  loc_1FE3B
0x1fe27  ldarg.0
0x1fe28  ldc.i4.s 0xFE
0x1fe2a  stfld    int32 <ValidateWopiUrlProperty>d__35::<>1__state
0x1fe2f  ldarg.0
0x1fe30  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>> <ValidateWopiUrlProperty>d__35::<>t__builder
0x1fe35  ldloc.2
0x1fe36  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>>::SetResult(var<u1>)
0x1fe3b  ret
```
