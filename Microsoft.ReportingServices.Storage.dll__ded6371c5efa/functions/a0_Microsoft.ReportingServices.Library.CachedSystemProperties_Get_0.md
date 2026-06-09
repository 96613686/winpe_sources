# Microsoft.ReportingServices.Library.CachedSystemProperties::Get_0

- ea: `0xa0`
- end: `0x116`
- name: `Microsoft.ReportingServices.Library.CachedSystemProperties::Get_0`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x90`

## callees

- `0xa0`
- `0x870`
- `0x8e0`

## pseudocode

```c

```

## disassembly

```asm
0xa0  call     class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.CachedSystemProperties::get_Cache()
0xa5  stloc.0
0xa6  ldloc.0
0xa7  stloc.3
0xa8  ldc.i4.0
0xa9  stloc.s  4
0xab  ldloc.3
0xac  ldloca.s 4
0xae  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xb3  ldloc.0
0xb4  ldarg.0
0xb5  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0xba  stloc.2
0xbb  ldloc.0
0xbc  ldarg.0
0xbd  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xc2  castclass [mscorlib]System.String
0xc7  stloc.1
0xc8  leave.s  loc_D5
0xca  ldloc.s  4
0xcc  brfalse.s loc_D4
0xce  ldloc.3
0xcf  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xd4  endfinally
0xd5  ldloc.2
0xd6  brtrue.s loc_114
0xd8  ldnull
0xd9  stloc.1
0xda  ldarg.1
0xdb  brfalse.s loc_EB
0xdd  ldarg.0
0xde  call     string Microsoft.ReportingServices.Library.CachedSystemProperties::GetSystemProperty(string name)
0xe3  stloc.1
0xe4  leave.s  loc_F2
0xe6  pop
0xe7  ldnull
0xe8  stloc.1
0xe9  leave.s  loc_F2
0xeb  ldarg.0
0xec  call     string Microsoft.ReportingServices.Library.CachedSystemProperties::GetSystemProperty(string name)
0xf1  stloc.1
0xf2  ldloc.0
0xf3  stloc.3
0xf4  ldc.i4.0
0xf5  stloc.s  4
0xf7  ldloc.3
0xf8  ldloca.s 4
0xfa  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xff  ldloc.0
0x100  ldarg.0
0x101  ldloc.1
0x102  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x107  leave.s  loc_114
0x109  ldloc.s  4
0x10b  brfalse.s loc_113
0x10d  ldloc.3
0x10e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x113  endfinally
0x114  ldloc.1
0x115  ret
```
