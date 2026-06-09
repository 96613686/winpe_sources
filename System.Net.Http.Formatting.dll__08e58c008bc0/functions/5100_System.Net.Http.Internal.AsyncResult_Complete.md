# System.Net.Http.Internal.AsyncResult::Complete

- ea: `0x5100`
- end: `0x515d`
- name: `System.Net.Http.Internal.AsyncResult::Complete`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x4990`
- `0x5160`

## callees

- `0x30f0`
- `0x3110`
- `0x5100`
- `0xb4b0`
- `0xb4c0`

## pseudocode

```c

```

## disassembly

```asm
0x5100  ldarg.0
0x5101  ldfld    bool System.Net.Http.Internal.AsyncResult::_isCompleted
0x5106  brfalse.s loc_5127
0x5108  call     string System.Net.Http.Properties.Resources::get_AsyncResult_MultipleCompletes()
0x510d  ldc.i4.1
0x510e  newarr   [mscorlib]System.Object
0x5113  dup
0x5114  ldc.i4.0
0x5115  ldarg.0
0x5116  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x511b  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x5120  stelem.ref
0x5121  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x5126  throw
0x5127  ldarg.0
0x5128  ldarg.1
0x5129  stfld    bool System.Net.Http.Internal.AsyncResult::_completedSynchronously
0x512e  ldarg.0
0x512f  ldc.i4.1
0x5130  stfld    bool System.Net.Http.Internal.AsyncResult::_isCompleted
0x5135  ldarg.0
0x5136  ldfld    class [mscorlib]System.AsyncCallback System.Net.Http.Internal.AsyncResult::_callback
0x513b  brfalse.s loc_515C
0x513d  ldarg.0
0x513e  ldfld    class [mscorlib]System.AsyncCallback System.Net.Http.Internal.AsyncResult::_callback
0x5143  ldarg.0
0x5144  callvirt instance void [mscorlib]System.AsyncCallback::Invoke(class [mscorlib]System.IAsyncResult)
0x5149  leave.s  loc_515C
0x514b  call     string System.Net.Http.Properties.Resources::get_AsyncResult_CallbackThrewException()
0x5150  ldc.i4.0
0x5151  newarr   [mscorlib]System.Object
0x5156  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(class [mscorlib]System.Exception innerException, string messageFormat, object[] messageArgs)
0x515b  throw
0x515c  ret
```
