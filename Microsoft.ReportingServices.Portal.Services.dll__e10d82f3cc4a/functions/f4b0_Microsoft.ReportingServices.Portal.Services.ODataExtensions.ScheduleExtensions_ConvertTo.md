# Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ConvertTo

- ea: `0xf4b0`
- end: `0xf530`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ConvertTo`
- size: `128`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xf060`
- `0xf190`
- `0xf330`
- `0xf4b0`

## callees

- `0xf4b0`
- `0xf530`

## pseudocode

```c

```

## disassembly

```asm
0xf4b0  ldarg.1
0xf4b1  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0xf4b6  stloc.0
0xf4b7  ldarg.0
0xf4b8  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xf4bd  callvirt instance class [mscorlib]System.Reflection.PropertyInfo[] [mscorlib]System.Type::GetProperties()
0xf4c2  stloc.1
0xf4c3  ldc.i4.0
0xf4c4  stloc.2
0xf4c5  br.s     loc_F528
0xf4c7  ldloc.1
0xf4c8  ldloc.2
0xf4c9  ldelem.ref
0xf4ca  stloc.3
0xf4cb  ldloc.0
0xf4cc  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xf4d1  ldloc.3
0xf4d2  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xf4d7  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0xf4dc  stloc.s  4
0xf4de  ldloc.s  4
0xf4e0  ldnull
0xf4e1  call     bool [mscorlib]System.Reflection.PropertyInfo::op_Inequality(class [mscorlib]System.Reflection.PropertyInfo, class [mscorlib]System.Reflection.PropertyInfo)
0xf4e6  brfalse.s loc_F524
0xf4e8  ldloc.s  4
0xf4ea  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0xf4ef  call     bool Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::IsSystemType(class [mscorlib]System.Type type)
0xf4f4  brfalse.s loc_F508
0xf4f6  ldloc.s  4
0xf4f8  ldloc.0
0xf4f9  ldloc.3
0xf4fa  ldarg.0
0xf4fb  ldnull
0xf4fc  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0xf501  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object)
0xf506  br.s     loc_F524
0xf508  ldloc.s  4
0xf50a  ldloc.0
0xf50b  ldloc.3
0xf50c  ldarg.0
0xf50d  ldnull
0xf50e  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0xf513  ldloc.s  4
0xf515  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0xf51a  call     object Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ConvertTo(object source, class [mscorlib]System.Type type)
0xf51f  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object)
0xf524  ldloc.2
0xf525  ldc.i4.1
0xf526  add
0xf527  stloc.2
0xf528  ldloc.2
0xf529  ldloc.1
0xf52a  ldlen
0xf52b  conv.i4
0xf52c  blt.s    loc_F4C7
0xf52e  ldloc.0
0xf52f  ret
```
