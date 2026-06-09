# <BackoffAsync>d__9::MoveNext

- ea: `0x5170`
- end: `0x5312`
- name: `<BackoffAsync>d__9::MoveNext`
- size: `418`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xa00`
- `0xa10`
- `0x1470`
- `0x5170`

## pseudocode

```c

```

## disassembly

```asm
0x5170  ldarg.0
0x5171  ldfld    int32 <BackoffAsync>d__9::<>1__state
0x5176  stloc.0
0x5177  ldarg.0
0x5178  ldfld    class Microsoft.BIServer.HostingEnvironment.ExponentialBackoff <BackoffAsync>d__9::<>4__this
0x517d  stloc.1
0x517e  ldloc.0
0x517f  brfalse  loc_5233
0x5184  ldloc.1
0x5185  ldfld    class Microsoft.BIServer.HostingEnvironment.IClock Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::_clock
0x518a  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.BIServer.HostingEnvironment.IClock::get_Now()
0x518f  stloc.3
0x5190  ldloc.3
0x5191  ldloc.1
0x5192  ldfld    valuetype [mscorlib]System.DateTime Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::_lastCallToWait
0x5197  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x519c  stloc.s  4
0x519e  ldarg.0
0x519f  ldloc.1
0x51a0  ldflda   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::_period
0x51a5  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x51aa  ldloca.s 4
0x51ac  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x51b1  sub
0x51b2  stfld    float64 <BackoffAsync>d__9::<sleepInMilliseconds>5__2
0x51b7  ldarg.0
0x51b8  ldfld    float64 <BackoffAsync>d__9::<sleepInMilliseconds>5__2
0x51bd  ldc.r8   0.0
0x51c6  ble.un   loc_5296
0x51cb  ldstr    aThrottlingBy0M// "Throttling by {0} MS"
0x51d0  ldc.i4.1
0x51d1  newarr   [mscorlib]System.Object
0x51d6  dup
0x51d7  ldc.i4.0
0x51d8  ldarg.0
0x51d9  ldfld    float64 <BackoffAsync>d__9::<sleepInMilliseconds>5__2
0x51de  box      [mscorlib]System.Double
0x51e3  stelem.ref
0x51e4  call     void Microsoft.BIServer.HostingEnvironment.Logger::Debug(string formatString, object[] formatParams)
0x51e9  ldloc.1
0x51ea  ldfld    class Microsoft.BIServer.HostingEnvironment.IClock Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::_clock
0x51ef  ldarg.0
0x51f0  ldfld    float64 <BackoffAsync>d__9::<sleepInMilliseconds>5__2
0x51f5  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMilliseconds(float64)
0x51fa  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype [mscorlib]System.TimeSpan> Microsoft.BIServer.HostingEnvironment.IClock::WaitAsync(valuetype [mscorlib]System.TimeSpan timeSpan)
0x51ff  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<valuetype [mscorlib]System.TimeSpan>::GetAwaiter()
0x5204  stloc.s  5
0x5206  ldloca.s 5
0x5208  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [mscorlib]System.TimeSpan>::get_IsCompleted()
0x520d  brtrue.s loc_5250
0x520f  ldarg.0
0x5210  ldc.i4.0
0x5211  dup
0x5212  stloc.0
0x5213  stfld    int32 <BackoffAsync>d__9::<>1__state
0x5218  ldarg.0
0x5219  ldloc.s  5
0x521b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [mscorlib]System.TimeSpan> <BackoffAsync>d__9::<>u__1
0x5220  ldarg.0
0x5221  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<float64> <BackoffAsync>d__9::<>t__builder
0x5226  ldloca.s 5
0x5228  ldarg.0
0x5229  call     T0x2B000038
0x522e  leave    loc_5311
0x5233  ldarg.0
0x5234  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [mscorlib]System.TimeSpan> <BackoffAsync>d__9::<>u__1
0x5239  stloc.s  5
0x523b  ldarg.0
0x523c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [mscorlib]System.TimeSpan> <BackoffAsync>d__9::<>u__1
0x5241  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [mscorlib]System.TimeSpan>
0x5247  ldarg.0
0x5248  ldc.i4.m1
0x5249  dup
0x524a  stloc.0
0x524b  stfld    int32 <BackoffAsync>d__9::<>1__state
0x5250  ldloca.s 5
0x5252  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [mscorlib]System.TimeSpan>::GetResult()
0x5257  pop
0x5258  ldloc.1
0x5259  ldloc.1
0x525a  ldflda   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::_period
0x525f  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x5264  ldloc.1
0x5265  ldfld    float64 Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::_backOffMultiplier
0x526a  mul
0x526b  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMilliseconds(float64)
0x5270  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::_period
0x5275  ldloc.1
0x5276  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::_period
0x527b  ldloc.1
0x527c  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::_maxWaitPeriod
0x5281  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x5286  brfalse.s loc_52CA
0x5288  ldloc.1
0x5289  ldloc.1
0x528a  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::_maxWaitPeriod
0x528f  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::_period
0x5294  br.s     loc_52CA
0x5296  ldarg.0
0x5297  ldc.r8   0.0
0x52a0  stfld    float64 <BackoffAsync>d__9::<sleepInMilliseconds>5__2
0x52a5  ldloc.3
0x52a6  ldloc.1
0x52a7  ldflda   valuetype [mscorlib]System.DateTime Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::_lastCallToWait
0x52ac  ldloc.1
0x52ad  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::_backOffExpirePeriod
0x52b2  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0x52b7  call     bool [mscorlib]System.DateTime::op_GreaterThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x52bc  brfalse.s loc_52CA
0x52be  ldloc.1
0x52bf  ldloc.1
0x52c0  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::_initialWaitPeriod
0x52c5  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::_period
0x52ca  ldloc.1
0x52cb  ldloc.1
0x52cc  ldfld    class Microsoft.BIServer.HostingEnvironment.IClock Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::_clock
0x52d1  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.BIServer.HostingEnvironment.IClock::get_Now()
0x52d6  stfld    valuetype [mscorlib]System.DateTime Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::_lastCallToWait
0x52db  ldarg.0
0x52dc  ldfld    float64 <BackoffAsync>d__9::<sleepInMilliseconds>5__2
0x52e1  stloc.2
0x52e2  leave.s  loc_52FD
0x52e4  stloc.s  6
0x52e6  ldarg.0
0x52e7  ldc.i4.s 0xFE
0x52e9  stfld    int32 <BackoffAsync>d__9::<>1__state
0x52ee  ldarg.0
0x52ef  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<float64> <BackoffAsync>d__9::<>t__builder
0x52f4  ldloc.s  6
0x52f6  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<float64>::SetException(class [mscorlib]System.Exception)
0x52fb  leave.s  loc_5311
0x52fd  ldarg.0
0x52fe  ldc.i4.s 0xFE
0x5300  stfld    int32 <BackoffAsync>d__9::<>1__state
0x5305  ldarg.0
0x5306  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<float64> <BackoffAsync>d__9::<>t__builder
0x530b  ldloc.2
0x530c  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<float64>::SetResult(var<u1>)
0x5311  ret
```
