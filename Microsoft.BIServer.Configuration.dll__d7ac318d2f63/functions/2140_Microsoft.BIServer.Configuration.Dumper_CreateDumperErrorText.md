# Microsoft.BIServer.Configuration.Dumper::CreateDumperErrorText

- ea: `0x2140`
- end: `0x21a8`
- name: `Microsoft.BIServer.Configuration.Dumper::CreateDumperErrorText`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1f90`

## callees

- `0x2140`

## pseudocode

```c

```

## disassembly

```asm
0x2140  ldarg.0
0x2141  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x2146  dup
0x2147  brtrue.s loc_2160
0x2149  pop
0x214a  ldarg.0
0x214b  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x2150  brtrue.s loc_2155
0x2152  ldnull
0x2153  br.s     loc_2160
0x2155  ldarg.0
0x2156  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x215b  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x2160  stloc.0
0x2161  ldarg.0
0x2162  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x2167  callvirt instance string [mscorlib]System.Object::ToString()
0x216c  ldstr    aAt// " at \r\n "
0x2171  call     string [mscorlib]System.String::Concat(string, string)
0x2176  stloc.1
0x2177  ldloc.0
0x2178  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x217d  brfalse.s loc_21A0
0x217f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2184  ldstr    aExceptionMessa// "Exception message: {0}:{1}\r\n"
0x2189  ldarg.0
0x218a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x218f  callvirt instance string [mscorlib]System.Object::ToString()
0x2194  ldarg.0
0x2195  callvirt instance string [mscorlib]System.Exception::get_Message()
0x219a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x219f  ret
0x21a0  ldloc.1
0x21a1  ldloc.0
0x21a2  call     string [mscorlib]System.String::Concat(string, string)
0x21a7  ret
```
