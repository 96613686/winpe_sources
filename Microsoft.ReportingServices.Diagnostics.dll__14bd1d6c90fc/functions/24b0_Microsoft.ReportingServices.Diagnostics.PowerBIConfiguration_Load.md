# Microsoft.ReportingServices.Diagnostics.PowerBIConfiguration::Load

- ea: `0x24b0`
- end: `0x27a3`
- name: `Microsoft.ReportingServices.Diagnostics.PowerBIConfiguration::Load`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4170`

## callees

- `0x17c0`
- `0x2360`
- `0x2380`
- `0x23a0`
- `0x23b0`
- `0x23c0`
- `0x23e0`
- `0x2400`
- `0x2420`
- `0x2440`
- `0x2460`
- `0x2480`
- `0x24a0`
- `0x24b0`
- `0x100d0`

## string_xrefs

- `0x2665`: `TokenUrl`
- `0x2718`: `https://api.powerbi.com`

## pseudocode

```c

```

## disassembly

```asm
0x24b0  ldarg.1
0x24b1  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::GetEnumerator()
0x24b6  stloc.0
0x24b7  br       loc_2786
0x24bc  ldloca.s 0
0x24be  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Current()
0x24c3  stloc.1
0x24c4  ldloca.s 1
0x24c6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Key()
0x24cb  ldloca.s 1
0x24cd  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Value()
0x24d2  stloc.2
0x24d3  ldsfld   char[] Microsoft.ReportingServices.Diagnostics.PowerBIConfiguration::m_splitter
0x24d8  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x24dd  ldc.i4.0
0x24de  ldelem.ref
0x24df  stloc.3
0x24e0  ldloc.3
0x24e1  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x24e6  stloc.s  4
0x24e8  ldloc.s  4
0x24ea  ldc.i4   0x430901C2
0x24ef  bgt.un.s loc_2540
0x24f1  ldloc.s  4
0x24f3  ldc.i4   0xC96F19C
0x24f8  bgt.un.s loc_2517
0x24fa  ldloc.s  4
0x24fc  ldc.i4   0x98F6896
0x2501  beq      loc_25A7
0x2506  ldloc.s  4
0x2508  ldc.i4   0xC96F19C
0x250d  beq      loc_2625
0x2512  br       loc_2786
0x2517  ldloc.s  4
0x2519  ldc.i4   0x1B058C3B
0x251e  beq      loc_2664
0x2523  ldloc.s  4
0x2525  ldc.i4   0x2A54EE06
0x252a  beq      loc_25BC
0x252f  ldloc.s  4
0x2531  ldc.i4   0x430901C2
0x2536  beq      loc_263A
0x253b  br       loc_2786
0x2540  ldloc.s  4
0x2542  ldc.i4   0x7AC1B423
0x2547  bgt.un.s loc_256F
0x2549  ldloc.s  4
0x254b  ldc.i4   0x5DD37722
0x2550  beq      loc_2610
0x2555  ldloc.s  4
0x2557  ldc.i4   0x70B21C2F
0x255c  beq      loc_25FB
0x2561  ldloc.s  4
0x2563  ldc.i4   0x7AC1B423
0x2568  beq.s    loc_2592
0x256a  br       loc_2786
0x256f  ldloc.s  4
0x2571  ldc.i4   0x7DD89AF6
0x2576  beq.s    loc_25E6
0x2578  ldloc.s  4
0x257a  ldc.i4   0x8C9BFC00
0x257f  beq.s    loc_25D1
0x2581  ldloc.s  4
0x2583  ldc.i4   0xF561A1AE
0x2588  beq      loc_264F
0x258d  br       loc_2786
0x2592  ldloc.3
0x2593  ldstr    aClientid// "ClientId"
0x2598  call     bool [mscorlib]System.String::op_Equality(string, string)
0x259d  brtrue   loc_2679
0x25a2  br       loc_2786
0x25a7  ldloc.3
0x25a8  ldstr    aAppobjectid// "AppObjectId"
0x25ad  call     bool [mscorlib]System.String::op_Equality(string, string)
0x25b2  brtrue   loc_268F
0x25b7  br       loc_2786
0x25bc  ldloc.3
0x25bd  ldstr    aTenantname// "TenantName"
0x25c2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x25c7  brtrue   loc_26A5
0x25cc  br       loc_2786
0x25d1  ldloc.3
0x25d2  ldstr    aTenantid// "TenantId"
0x25d7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x25dc  brtrue   loc_26BB
0x25e1  br       loc_2786
0x25e6  ldloc.3
0x25e7  ldstr    aClientsecret// "ClientSecret"
0x25ec  call     bool [mscorlib]System.String::op_Equality(string, string)
0x25f1  brtrue   loc_26D1
0x25f6  br       loc_2786
0x25fb  ldloc.3
0x25fc  ldstr    aAuthorizationu// "AuthorizationUrl"
0x2601  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2606  brtrue   loc_26E7
0x260b  br       loc_2786
0x2610  ldloc.3
0x2611  ldstr    aPowerbiendpoin// "PowerBIEndpoint"
0x2616  call     bool [mscorlib]System.String::op_Equality(string, string)
0x261b  brtrue   loc_26FD
0x2620  br       loc_2786
0x2625  ldloc.3
0x2626  ldstr    aLogouturl// "LogoutUrl"
0x262b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2630  brtrue   loc_2724
0x2635  br       loc_2786
0x263a  ldloc.3
0x263b  ldstr    aRedirecturl// "RedirectUrl"
0x2640  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2645  brtrue   loc_2737
0x264a  br       loc_2786
0x264f  ldloc.3
0x2650  ldstr    aResourceurl// "ResourceUrl"
0x2655  call     bool [mscorlib]System.String::op_Equality(string, string)
0x265a  brtrue   loc_2762
0x265f  br       loc_2786
0x2664  ldloc.3
0x2665  ldstr    aTokenurl// "TokenUrl"
0x266a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x266f  brtrue   loc_2775
0x2674  br       loc_2786
0x2679  ldarg.0
0x267a  ldloc.2
0x267b  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2680  castclass [mscorlib]System.String
0x2685  call     instance void Microsoft.ReportingServices.Diagnostics.PowerBIConfiguration::set_ClientId(string value)
0x268a  br       loc_2786
0x268f  ldarg.0
0x2690  ldloc.2
0x2691  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2696  castclass [mscorlib]System.String
0x269b  call     instance void Microsoft.ReportingServices.Diagnostics.PowerBIConfiguration::set_AppObjectId(string value)
0x26a0  br       loc_2786
0x26a5  ldarg.0
0x26a6  ldloc.2
0x26a7  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x26ac  castclass [mscorlib]System.String
0x26b1  call     instance void Microsoft.ReportingServices.Diagnostics.PowerBIConfiguration::set_TenantName(string value)
0x26b6  br       loc_2786
0x26bb  ldarg.0
0x26bc  ldloc.2
0x26bd  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x26c2  castclass [mscorlib]System.String
0x26c7  call     instance void Microsoft.ReportingServices.Diagnostics.PowerBIConfiguration::set_TenantId(string value)
0x26cc  br       loc_2786
0x26d1  ldarg.0
0x26d2  ldloc.2
0x26d3  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x26d8  castclass [mscorlib]System.String
0x26dd  call     instance void Microsoft.ReportingServices.Diagnostics.PowerBIConfiguration::set_ClientSecret(string value)
0x26e2  br       loc_2786
0x26e7  ldarg.0
0x26e8  ldloc.2
0x26e9  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x26ee  castclass [mscorlib]System.String
0x26f3  call     instance void Microsoft.ReportingServices.Diagnostics.PowerBIConfiguration::set_AuthorizationUrl(string value)
0x26f8  br       loc_2786
0x26fd  ldloc.2
0x26fe  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2703  castclass [mscorlib]System.String
0x2708  stloc.s  5
0x270a  ldarg.0
0x270b  ldloc.s  5
0x270d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2712  brtrue.s loc_2718
0x2714  ldloc.s  5
0x2716  br.s     loc_271D
0x2718  ldstr    aHttpsApiPowerb// "https://api.powerbi.com"
0x271d  call     instance void Microsoft.ReportingServices.Diagnostics.PowerBIConfiguration::set_PowerBIEndpoint(string value)
0x2722  br.s     loc_2786
0x2724  ldarg.0
0x2725  ldloc.2
0x2726  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x272b  castclass [mscorlib]System.String
0x2730  call     instance void Microsoft.ReportingServices.Diagnostics.PowerBIConfiguration::set_LogoutUrl(string value)
0x2735  br.s     loc_2786
0x2737  ldarg.0
0x2738  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.PowerBIConfiguration::get_RedirectUrls()
0x273d  brtrue.s loc_274A
0x273f  ldarg.0
0x2740  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x2745  call     instance void Microsoft.ReportingServices.Diagnostics.PowerBIConfiguration::set_RedirectUrls(class [mscorlib]System.Collections.Generic.List`1<string> value)
0x274a  ldarg.0
0x274b  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.PowerBIConfiguration::get_RedirectUrls()
0x2750  ldloc.2
0x2751  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2756  castclass [mscorlib]System.String
0x275b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2760  br.s     loc_2786
0x2762  ldarg.0
0x2763  ldloc.2
0x2764  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2769  castclass [mscorlib]System.String
0x276e  call     instance void Microsoft.ReportingServices.Diagnostics.PowerBIConfiguration::set_ResourceUrl(string value)
0x2773  br.s     loc_2786
0x2775  ldarg.0
0x2776  ldloc.2
0x2777  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x277c  castclass [mscorlib]System.String
0x2781  call     instance void Microsoft.ReportingServices.Diagnostics.PowerBIConfiguration::set_TokenUrl(string value)
0x2786  ldloca.s 0
0x2788  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::MoveNext()
0x278d  brtrue   loc_24BC
0x2792  leave.s  loc_27A2
0x2794  ldloca.s 0
0x2796  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>
0x279c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27a1  endfinally
0x27a2  ret
```
