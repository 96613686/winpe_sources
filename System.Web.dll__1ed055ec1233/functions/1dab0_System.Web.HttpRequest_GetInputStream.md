# System.Web.HttpRequest::GetInputStream

- ea: `0x1dab0`
- end: `0x1db22`
- name: `System.Web.HttpRequest::GetInputStream`
- size: `114`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1da80`
- `0x1da90`
- `0x1daa0`

## callees

- `0x12310`
- `0x18990`
- `0x1dab0`
- `0x1db60`
- `0x34fa0`

## string_xrefs

- `0x1db0b`: `Incompatible_with_get_bufferless_input_stream`
- `0x1dae8`: `Incompatible_with_input_stream`
- `0x1daff`: `Incompatible_with_get_buffered_input_stream`

## pseudocode

```c

```

## disassembly

```asm
0x1dab0  ldarg.0
0x1dab1  call     instance void System.Web.HttpRequest::EnsureHasNotTransitionedToWebSocket()
0x1dab6  ldarg.1
0x1dab7  brtrue.s loc_1DABC
0x1dab9  ldc.i4.2
0x1daba  br.s     loc_1DABD
0x1dabc  ldc.i4.3
0x1dabd  stloc.0
0x1dabe  ldarg.0
0x1dabf  ldfld    valuetype System.Web.ReadEntityBodyMode System.Web.HttpRequest::_readEntityBodyMode
0x1dac4  stloc.1
0x1dac5  ldloc.1
0x1dac6  brtrue.s loc_1DAE4
0x1dac8  ldarg.0
0x1dac9  ldloc.0
0x1daca  stfld    valuetype System.Web.ReadEntityBodyMode System.Web.HttpRequest::_readEntityBodyMode
0x1dacf  ldarg.0
0x1dad0  ldarg.0
0x1dad1  ldfld    class System.Web.HttpContext System.Web.HttpRequest::_context
0x1dad6  ldarg.1
0x1dad7  ldarg.2
0x1dad8  newobj   instance void System.Web.HttpBufferlessInputStream::.ctor(class System.Web.HttpContext context, bool persistEntityBody, bool disableMaxRequestLength)
0x1dadd  stfld    class [mscorlib]System.IO.Stream System.Web.HttpRequest::_readEntityBodyStream
0x1dae2  br.s     loc_1DB1B
0x1dae4  ldloc.1
0x1dae5  ldc.i4.1
0x1dae6  bne.un.s loc_1DAF8
0x1dae8  ldstr    aIncompatibleWi_0// "Incompatible_with_input_stream"
0x1daed  call     string System.Web.SR::GetString(string name)
0x1daf2  newobj   instance void System.Web.HttpException::.ctor(string message)
0x1daf7  throw
0x1daf8  ldloc.1
0x1daf9  ldloc.0
0x1dafa  beq.s    loc_1DB1B
0x1dafc  ldarg.1
0x1dafd  brtrue.s loc_1DB0B
0x1daff  ldstr    aIncompatibleWi_1// "Incompatible_with_get_buffered_input_st"...
0x1db04  call     string System.Web.SR::GetString(string name)
0x1db09  br.s     loc_1DB15
0x1db0b  ldstr    aIncompatibleWi// "Incompatible_with_get_bufferless_input_"...
0x1db10  call     string System.Web.SR::GetString(string name)
0x1db15  newobj   instance void System.Web.HttpException::.ctor(string message)
0x1db1a  throw
0x1db1b  ldarg.0
0x1db1c  ldfld    class [mscorlib]System.IO.Stream System.Web.HttpRequest::_readEntityBodyStream
0x1db21  ret
```
