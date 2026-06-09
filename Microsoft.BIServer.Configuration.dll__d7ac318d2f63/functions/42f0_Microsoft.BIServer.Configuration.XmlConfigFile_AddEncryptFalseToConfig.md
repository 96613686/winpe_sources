# Microsoft.BIServer.Configuration.XmlConfigFile::AddEncryptFalseToConfig

- ea: `0x42f0`
- end: `0x434c`
- name: `Microsoft.BIServer.Configuration.XmlConfigFile::AddEncryptFalseToConfig`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3f10`
- `0x3f50`
- `0x42f0`

## string_xrefs

- `0x42f0`: `Start adding Encrypt=false to the config file`
- `0x4330`: `Add Encrypt False to the config file`

## pseudocode

```c

```

## disassembly

```asm
0x42f0  ldstr    aStartAddingEnc// "Start adding Encrypt=false to the confi"...
0x42f5  call     T0x2B000015
0x42fa  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x42ff  ldarg.0
0x4300  call     instance string Microsoft.BIServer.Configuration.XmlConfigFile::GetDsn()
0x4305  stloc.0
0x4306  ldloc.0
0x4307  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x430c  brtrue.s loc_434B
0x430e  ldloc.0
0x430f  ldstr    aEncrypt// "Encrypt="
0x4314  ldc.i4.5
0x4315  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x431a  ldc.i4.m1
0x431b  bne.un.s loc_434B
0x431d  ldloc.0
0x431e  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnectionStringBuilder::.ctor(string)
0x4323  stloc.1
0x4324  ldloc.1
0x4325  ldc.i4.0
0x4326  call     class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnectionEncryptOption [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnectionEncryptOption::op_Implicit(bool)
0x432b  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnectionStringBuilder::set_Encrypt(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnectionEncryptOption)
0x4330  ldstr    aAddEncryptFals// "Add Encrypt False to the config file"
0x4335  call     T0x2B000015
0x433a  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x433f  ldarg.0
0x4340  ldloc.1
0x4341  callvirt instance string [mscorlib]System.Object::ToString()
0x4346  call     instance void Microsoft.BIServer.Configuration.XmlConfigFile::SetDsn(string value)
0x434b  ret
```
