# Microsoft.BIServer.Configuration.SqlDumperAdapter::Microsoft.BIServer.Configuration.IDumperAdapter.Dump

- ea: `0x43b0`
- end: `0x447f`
- name: `Microsoft.BIServer.Configuration.SqlDumperAdapter::Microsoft.BIServer.Configuration.IDumperAdapter.Dump`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0xcc0`
- `0xce0`
- `0xd00`
- `0xd20`
- `0xd40`
- `0xd60`
- `0xd80`
- `0xda0`
- `0x43b0`
- `0x4480`

## pseudocode

```c

```

## disassembly

```asm
0x43b0  call     class [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.DumpClient::GetDumper()
0x43b5  stloc.0
0x43b6  ldloc.0
0x43b7  ldc.i4   0x121
0x43bc  ldc.i4.0
0x43bd  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::SetMiniDumpFlags(valuetype [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.MiniDumpFlags, valuetype [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.MiniDumpFlags)
0x43c2  ldloc.0
0x43c3  ldarg.1
0x43c4  callvirt instance valuetype Microsoft.BIServer.Configuration.DumperFlags Microsoft.BIServer.Configuration.DumpInstructions::get_Flags()
0x43c9  call     valuetype [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.DumperFlags Microsoft.BIServer.Configuration.SqlDumperAdapter::ConvertFlags(valuetype Microsoft.BIServer.Configuration.DumperFlags flags)
0x43ce  ldc.i4.0
0x43cf  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::SetFlags(valuetype [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.DumperFlags, valuetype [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.DumperFlags)
0x43d4  ldloc.0
0x43d5  ldarg.1
0x43d6  callvirt instance int32 Microsoft.BIServer.Configuration.DumpInstructions::get_FramesToInclude()
0x43db  ldc.i4.0
0x43dc  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::SetBucket(int32, int32)
0x43e1  ldarg.1
0x43e2  callvirt instance string Microsoft.BIServer.Configuration.DumpInstructions::get_Location()
0x43e7  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x43ec  brtrue.s loc_43FA
0x43ee  ldloc.0
0x43ef  ldarg.1
0x43f0  callvirt instance string Microsoft.BIServer.Configuration.DumpInstructions::get_Location()
0x43f5  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::SetDirectory(string)
0x43fa  ldarg.1
0x43fb  callvirt instance string Microsoft.BIServer.Configuration.DumpInstructions::get_LogFileToInclude()
0x4400  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x4405  brtrue.s loc_4419
0x4407  ldloc.0
0x4408  ldarg.1
0x4409  callvirt instance string Microsoft.BIServer.Configuration.DumpInstructions::get_LogFileToInclude()
0x440e  ldarg.1
0x440f  callvirt instance int32 Microsoft.BIServer.Configuration.DumpInstructions::get_SizeOfLogFileToInclude()
0x4414  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::SetLogFile(string, int32)
0x4419  ldarg.1
0x441a  callvirt instance string Microsoft.BIServer.Configuration.DumpInstructions::get_InstanceName()
0x441f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x4424  brtrue.s loc_4432
0x4426  ldloc.0
0x4427  ldarg.1
0x4428  callvirt instance string Microsoft.BIServer.Configuration.DumpInstructions::get_InstanceName()
0x442d  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::SetInstanceName(string)
0x4432  ldarg.1
0x4433  callvirt instance string Microsoft.BIServer.Configuration.DumpInstructions::get_ServiceName()
0x4438  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x443d  brtrue.s loc_444B
0x443f  ldloc.0
0x4440  ldarg.1
0x4441  callvirt instance string Microsoft.BIServer.Configuration.DumpInstructions::get_ServiceName()
0x4446  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::SetServiceName(string)
0x444b  ldarg.1
0x444c  callvirt instance string Microsoft.BIServer.Configuration.DumpInstructions::get_ErrorText()
0x4451  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x4456  brtrue.s loc_4464
0x4458  ldloc.0
0x4459  ldarg.1
0x445a  callvirt instance string Microsoft.BIServer.Configuration.DumpInstructions::get_ErrorText()
0x445f  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::SetErrorText(string)
0x4464  ldloc.0
0x4465  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::Dump()
0x446a  ldloc.0
0x446b  callvirt instance string [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::GetDumpResultText()
0x4470  stloc.1
0x4471  leave.s  loc_447D
0x4473  ldloc.0
0x4474  brfalse.s loc_447C
0x4476  ldloc.0
0x4477  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x447c  endfinally
0x447d  ldloc.1
0x447e  ret
```
