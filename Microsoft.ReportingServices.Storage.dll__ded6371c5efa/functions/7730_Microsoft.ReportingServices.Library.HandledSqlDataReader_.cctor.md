# Microsoft.ReportingServices.Library.HandledSqlDataReader::.cctor

- ea: `0x7730`
- end: `0x79a7`
- name: `Microsoft.ReportingServices.Library.HandledSqlDataReader::.cctor`
- size: `631`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x7730  ldsfld   class <>c <>c::<>9
0x7735  ldftn    instance void <>c::<.cctor>b__74_0(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r)
0x773b  newobj   instance void class [mscorlib]System.Action`1<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader>::.ctor(object, native int)
0x7740  stsfld   class [mscorlib]System.Action`1<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader> Microsoft.ReportingServices.Library.HandledSqlDataReader::CloseMethod
0x7745  ldsfld   class <>c <>c::<>9
0x774a  ldftn    instance void <>c::<.cctor>b__74_1(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r)
0x7750  newobj   instance void class [mscorlib]System.Action`1<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader>::.ctor(object, native int)
0x7755  stsfld   class [mscorlib]System.Action`1<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader> Microsoft.ReportingServices.Library.HandledSqlDataReader::DisposeMethod
0x775a  ldsfld   class <>c <>c::<>9
0x775f  ldftn    instance int32 <>c::<.cctor>b__74_2(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r)
0x7765  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32>::.ctor(object, native int)
0x776a  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32> Microsoft.ReportingServices.Library.HandledSqlDataReader::RecordsAffectedMethod
0x776f  ldsfld   class <>c <>c::<>9
0x7774  ldftn    instance bool <>c::<.cctor>b__74_3(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r)
0x777a  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, bool>::.ctor(object, native int)
0x777f  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, bool> Microsoft.ReportingServices.Library.HandledSqlDataReader::ReadMethod
0x7784  ldsfld   class <>c <>c::<>9
0x7789  ldftn    instance bool <>c::<.cctor>b__74_4(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r)
0x778f  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, bool>::.ctor(object, native int)
0x7794  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, bool> Microsoft.ReportingServices.Library.HandledSqlDataReader::NextResultMethod
0x7799  ldsfld   class <>c <>c::<>9
0x779e  ldftn    instance bool <>c::<.cctor>b__74_5(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r)
0x77a4  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, bool>::.ctor(object, native int)
0x77a9  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, bool> Microsoft.ReportingServices.Library.HandledSqlDataReader::IsClosedMethod
0x77ae  ldsfld   class <>c <>c::<>9
0x77b3  ldftn    instance class [System.Data]System.Data.DataTable <>c::<.cctor>b__74_6(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r)
0x77b9  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, class [System.Data]System.Data.DataTable>::.ctor(object, native int)
0x77be  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, class [System.Data]System.Data.DataTable> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetSchemaTableMethod
0x77c3  ldsfld   class <>c <>c::<>9
0x77c8  ldftn    instance int32 <>c::<.cctor>b__74_7(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r)
0x77ce  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32>::.ctor(object, native int)
0x77d3  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32> Microsoft.ReportingServices.Library.HandledSqlDataReader::DepthMethod
0x77d8  ldsfld   class <>c <>c::<>9
0x77dd  ldftn    instance int32 <>c::<.cctor>b__74_8(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r)
0x77e3  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32>::.ctor(object, native int)
0x77e8  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32> Microsoft.ReportingServices.Library.HandledSqlDataReader::FieldCountMethod
0x77ed  ldsfld   class <>c <>c::<>9
0x77f2  ldftn    instance bool <>c::<.cctor>b__74_9(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x77f8  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, bool>::.ctor(object, native int)
0x77fd  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, bool> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetBooleanMethod
0x7802  ldsfld   class <>c <>c::<>9
0x7807  ldftn    instance unsigned int8 <>c::<.cctor>b__74_10(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x780d  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, unsigned int8>::.ctor(object, native int)
0x7812  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, unsigned int8> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetByteMethod
0x7817  ldsfld   class <>c <>c::<>9
0x781c  ldftn    instance char <>c::<.cctor>b__74_11(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x7822  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, char>::.ctor(object, native int)
0x7827  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, char> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetCharMethod
0x782c  ldsfld   class <>c <>c::<>9
0x7831  ldftn    instance string <>c::<.cctor>b__74_12(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x7837  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, string>::.ctor(object, native int)
0x783c  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, string> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetDataTypeNameMethod
0x7841  ldsfld   class <>c <>c::<>9
0x7846  ldftn    instance valuetype [mscorlib]System.DateTime <>c::<.cctor>b__74_13(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x784c  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, valuetype [mscorlib]System.DateTime>::.ctor(object, native int)
0x7851  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, valuetype [mscorlib]System.DateTime> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetDateTimeMethod
0x7856  ldsfld   class <>c <>c::<>9
0x785b  ldftn    instance valuetype [mscorlib]System.Decimal <>c::<.cctor>b__74_14(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x7861  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, valuetype [mscorlib]System.Decimal>::.ctor(object, native int)
0x7866  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, valuetype [mscorlib]System.Decimal> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetDecimalMethod
0x786b  ldsfld   class <>c <>c::<>9
0x7870  ldftn    instance float64 <>c::<.cctor>b__74_15(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x7876  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, float64>::.ctor(object, native int)
0x787b  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, float64> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetDoubleMethod
0x7880  ldsfld   class <>c <>c::<>9
0x7885  ldftn    instance class [mscorlib]System.Type <>c::<.cctor>b__74_16(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x788b  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, class [mscorlib]System.Type>::.ctor(object, native int)
0x7890  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, class [mscorlib]System.Type> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetFieldTypeMethod
0x7895  ldsfld   class <>c <>c::<>9
0x789a  ldftn    instance float32 <>c::<.cctor>b__74_17(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x78a0  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, float32>::.ctor(object, native int)
0x78a5  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, float32> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetFloatMethod
0x78aa  ldsfld   class <>c <>c::<>9
0x78af  ldftn    instance valuetype [mscorlib]System.Guid <>c::<.cctor>b__74_18(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x78b5  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x78ba  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, valuetype [mscorlib]System.Guid> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetGuidMethod
0x78bf  ldsfld   class <>c <>c::<>9
0x78c4  ldftn    instance int16 <>c::<.cctor>b__74_19(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x78ca  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, int16>::.ctor(object, native int)
0x78cf  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, int16> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetInt16Method
0x78d4  ldsfld   class <>c <>c::<>9
0x78d9  ldftn    instance int32 <>c::<.cctor>b__74_20(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x78df  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, int32>::.ctor(object, native int)
0x78e4  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, int32> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetInt32Method
0x78e9  ldsfld   class <>c <>c::<>9
0x78ee  ldftn    instance int64 <>c::<.cctor>b__74_21(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x78f4  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, int64>::.ctor(object, native int)
0x78f9  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, int64> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetInt64Method
0x78fe  ldsfld   class <>c <>c::<>9
0x7903  ldftn    instance string <>c::<.cctor>b__74_22(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x7909  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, string>::.ctor(object, native int)
0x790e  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, string> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetNameMethod
0x7913  ldsfld   class <>c <>c::<>9
0x7918  ldftn    instance string <>c::<.cctor>b__74_23(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x791e  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, string>::.ctor(object, native int)
0x7923  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, string> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetStringMethod
0x7928  ldsfld   class <>c <>c::<>9
0x792d  ldftn    instance object <>c::<.cctor>b__74_24(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x7933  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, object>::.ctor(object, native int)
0x7938  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, object> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetValueMethod
0x793d  ldsfld   class <>c <>c::<>9
0x7942  ldftn    instance bool <>c::<.cctor>b__74_25(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x7948  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, bool>::.ctor(object, native int)
0x794d  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, bool> Microsoft.ReportingServices.Library.HandledSqlDataReader::IsDBNullMethod
0x7952  ldsfld   class <>c <>c::<>9
0x7957  ldftn    instance object <>c::<.cctor>b__74_26(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, int32 i)
0x795d  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, object>::.ctor(object, native int)
0x7962  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32, object> Microsoft.ReportingServices.Library.HandledSqlDataReader::ThisMethod
0x7967  ldsfld   class <>c <>c::<>9
0x796c  ldftn    instance object <>c::<.cctor>b__74_27(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, string s)
0x7972  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, string, object>::.ctor(object, native int)
0x7977  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, string, object> Microsoft.ReportingServices.Library.HandledSqlDataReader::This2Method
0x797c  ldsfld   class <>c <>c::<>9
0x7981  ldftn    instance int32 <>c::<.cctor>b__74_28(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, string n)
0x7987  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, string, int32>::.ctor(object, native int)
0x798c  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, string, int32> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetOrdinalMethod
0x7991  ldsfld   class <>c <>c::<>9
0x7996  ldftn    instance int32 <>c::<.cctor>b__74_29(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader r, object[] vs)
0x799c  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, object[], int32>::.ctor(object, native int)
0x79a1  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, object[], int32> Microsoft.ReportingServices.Library.HandledSqlDataReader::GetValuesMethod
0x79a6  ret
```
