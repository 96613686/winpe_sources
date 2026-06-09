# Microsoft.VisualStudio.Setup.Services.FileLogger::RetryOpenIfFaulted

- ea: `0x3cd80`
- end: `0x3ce49`
- name: `Microsoft.VisualStudio.Setup.Services.FileLogger::RetryOpenIfFaulted`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xab10`

## callees

- `0x3cd80`
- `0x3cea0`
- `0x3ced0`

## string_xrefs

- `0x3cdbd`: `File Logger failed to open after initial retry`
- `0x3ce2d`: `File Logger failed to open on fault retry`

## pseudocode

```c

```

## disassembly

```asm
0x3cd80  ldarg.0
0x3cd81  ldfld    class [mscorlib]System.Exception Microsoft.VisualStudio.Setup.Services.FileLogger::lastFault
0x3cd86  brtrue.s loc_3CD8A
0x3cd88  ldc.i4.1
0x3cd89  ret
0x3cd8a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x3cd8f  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x3cd94  stloc.1
0x3cd95  dup
0x3cd96  ldloc.1
0x3cd97  ldstr    aFilelogger// "FileLogger"
0x3cd9c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x3cda1  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x3cda6  stloc.2
0x3cda7  dup
0x3cda8  ldloc.2
0x3cda9  ldstr    aOpen// "Open"
0x3cdae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x3cdb3  stloc.0
0x3cdb4  ldarg.1
0x3cdb5  brfalse.s loc_3CDD4
0x3cdb7  ldarg.1
0x3cdb8  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x3cdbd  ldstr    aFileLoggerFail// "File Logger failed to open after initia"...
0x3cdc2  ldloc.0
0x3cdc3  ldarg.0
0x3cdc4  ldfld    class [mscorlib]System.Exception Microsoft.VisualStudio.Setup.Services.FileLogger::lastFault
0x3cdc9  ldnull
0x3cdca  ldc.i4.0
0x3cdcb  ldnull
0x3cdcc  ldc.i4.0
0x3cdcd  ldnull
0x3cdce  ldc.i4.0
0x3cdcf  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x3cdd4  ldarg.0
0x3cdd5  ldnull
0x3cdd6  stfld    class [mscorlib]System.Exception Microsoft.VisualStudio.Setup.Services.FileLogger::lastFault
0x3cddb  ldarg.0
0x3cddc  call     instance void Microsoft.VisualStudio.Setup.Services.FileLogger::Open()
0x3cde1  ldarg.0
0x3cde2  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.Services.FileLogger::faultedInMemoryLog
0x3cde7  brfalse.s loc_3CE0A
0x3cde9  ldarg.0
0x3cdea  ldfld    class [mscorlib]System.IO.TextWriter Microsoft.VisualStudio.Setup.Services.FileLogger::writer
0x3cdef  dup
0x3cdf0  brtrue.s loc_3CDF5
0x3cdf2  pop
0x3cdf3  br.s     loc_3CE0A
0x3cdf5  call     string [mscorlib]System.Environment::get_NewLine()
0x3cdfa  ldarg.0
0x3cdfb  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.Services.FileLogger::faultedInMemoryLog
0x3ce00  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x3ce05  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x3ce0a  ldarg.0
0x3ce0b  ldnull
0x3ce0c  stfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.Services.FileLogger::faultedInMemoryLog
0x3ce11  ldarg.0
0x3ce12  ldstr    aSuccessfullyRe// "Successfully recovered file logger."
0x3ce17  call     T0x2B000003
0x3ce1c  callvirt instance void Microsoft.VisualStudio.Setup.Services.FileLogger::WriteVerbose(string format, object[] args)
0x3ce21  leave.s  loc_3CE44
0x3ce23  stloc.3
0x3ce24  ldarg.1
0x3ce25  brfalse.s loc_3CE3F
0x3ce27  ldarg.1
0x3ce28  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x3ce2d  ldstr    aFileLoggerFail_0// "File Logger failed to open on fault ret"...
0x3ce32  ldloc.0
0x3ce33  ldloc.3
0x3ce34  ldnull
0x3ce35  ldc.i4.0
0x3ce36  ldnull
0x3ce37  ldc.i4.0
0x3ce38  ldnull
0x3ce39  ldc.i4.0
0x3ce3a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x3ce3f  ldc.i4.0
0x3ce40  stloc.s  4
0x3ce42  leave.s  loc_3CE46
0x3ce44  ldc.i4.1
0x3ce45  ret
0x3ce46  ldloc.s  4
0x3ce48  ret
```
