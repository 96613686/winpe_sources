# System.Web.UI.WebControls.CompareValidator::ControlPropertiesValid

- ea: `0x9c8d0`
- end: `0x9c9a5`
- name: `System.Web.UI.WebControls.CompareValidator::ControlPropertiesValid`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x18990`
- `0x34f20`
- `0x58d50`
- `0x5f1b0`
- `0x7b640`
- `0x8fe80`
- `0x8fed0`
- `0x900b0`
- `0x91680`
- `0x91ae0`
- `0x91b50`
- `0x9c6f0`
- `0x9c740`
- `0x9c790`
- `0x9c8d0`

## string_xrefs

- `0x9c8e5`: `ControlToCompare`
- `0x9c965`: `ValueToCompare`
- `0x9c905`: `Validator_bad_compare_control`

## pseudocode

```c

```

## disassembly

```asm
0x9c8d0  ldarg.0
0x9c8d1  call     instance string System.Web.UI.WebControls.CompareValidator::get_ControlToCompare()
0x9c8d6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9c8db  ldc.i4.0
0x9c8dc  ble.s    loc_9C92D
0x9c8de  ldarg.0
0x9c8df  ldarg.0
0x9c8e0  call     instance string System.Web.UI.WebControls.CompareValidator::get_ControlToCompare()
0x9c8e5  ldstr    aControltocompa// "ControlToCompare"
0x9c8ea  call     instance void System.Web.UI.WebControls.BaseValidator::CheckControlValidationProperty(string name, string propertyName)
0x9c8ef  ldarg.0
0x9c8f0  call     instance string System.Web.UI.WebControls.BaseValidator::get_ControlToValidate()
0x9c8f5  ldarg.0
0x9c8f6  call     instance string System.Web.UI.WebControls.CompareValidator::get_ControlToCompare()
0x9c8fb  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x9c900  brfalse  loc_9C99E
0x9c905  ldstr    aValidatorBadCo_0// "Validator_bad_compare_control"
0x9c90a  ldc.i4.2
0x9c90b  newarr   [mscorlib]System.Object
0x9c910  dup
0x9c911  ldc.i4.0
0x9c912  ldarg.0
0x9c913  callvirt instance string System.Web.UI.Control::get_ID()
0x9c918  stelem.ref
0x9c919  dup
0x9c91a  ldc.i4.1
0x9c91b  ldarg.0
0x9c91c  call     instance string System.Web.UI.WebControls.CompareValidator::get_ControlToCompare()
0x9c921  stelem.ref
0x9c922  call     string System.Web.SR::GetString(string name, object[] args)
0x9c927  newobj   instance void System.Web.HttpException::.ctor(string message)
0x9c92c  throw
0x9c92d  ldarg.0
0x9c92e  call     instance valuetype System.Web.UI.WebControls.ValidationCompareOperator System.Web.UI.WebControls.CompareValidator::get_Operator()
0x9c933  ldc.i4.6
0x9c934  beq.s    loc_9C99E
0x9c936  ldarg.0
0x9c937  call     instance string System.Web.UI.WebControls.CompareValidator::get_ValueToCompare()
0x9c93c  ldarg.0
0x9c93d  call     instance valuetype System.Web.UI.WebControls.ValidationDataType System.Web.UI.WebControls.BaseCompareValidator::get_Type()
0x9c942  ldarg.0
0x9c943  call     instance bool System.Web.UI.WebControls.BaseCompareValidator::get_CultureInvariantValues()
0x9c948  call     bool System.Web.UI.WebControls.BaseCompareValidator::CanConvert(string text, valuetype System.Web.UI.WebControls.ValidationDataType type, bool cultureInvariant)
0x9c94d  brtrue.s loc_9C99E
0x9c94f  ldstr    aValidatorValue// "Validator_value_bad_type"
0x9c954  ldc.i4.4
0x9c955  newarr   [mscorlib]System.String
0x9c95a  dup
0x9c95b  ldc.i4.0
0x9c95c  ldarg.0
0x9c95d  call     instance string System.Web.UI.WebControls.CompareValidator::get_ValueToCompare()
0x9c962  stelem.ref
0x9c963  dup
0x9c964  ldc.i4.1
0x9c965  ldstr    aValuetocompare// "ValueToCompare"
0x9c96a  stelem.ref
0x9c96b  dup
0x9c96c  ldc.i4.2
0x9c96d  ldarg.0
0x9c96e  callvirt instance string System.Web.UI.Control::get_ID()
0x9c973  stelem.ref
0x9c974  dup
0x9c975  ldc.i4.3
0x9c976  ldtoken  System.Web.UI.WebControls.ValidationDataType
0x9c97b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9c980  ldarg.0
0x9c981  call     instance valuetype System.Web.UI.WebControls.ValidationDataType System.Web.UI.WebControls.BaseCompareValidator::get_Type()
0x9c986  box      System.Web.UI.WebControls.ValidationDataType
0x9c98b  call     string System.Web.UI.PropertyConverter::EnumToString(class [mscorlib]System.Type enumType, object enumValue)
0x9c990  stelem.ref
0x9c991  stloc.0
0x9c992  ldloc.0
0x9c993  call     string System.Web.SR::GetString(string name, object[] args)
0x9c998  newobj   instance void System.Web.HttpException::.ctor(string message)
0x9c99d  throw
0x9c99e  ldarg.0
0x9c99f  call     instance bool System.Web.UI.WebControls.BaseValidator::ControlPropertiesValid()
0x9c9a4  ret
```
