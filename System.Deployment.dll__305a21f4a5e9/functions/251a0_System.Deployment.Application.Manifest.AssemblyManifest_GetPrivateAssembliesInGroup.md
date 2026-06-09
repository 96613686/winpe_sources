# System.Deployment.Application.Manifest.AssemblyManifest::GetPrivateAssembliesInGroup

- ea: `0x251a0`
- end: `0x25260`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::GetPrivateAssembliesInGroup`
- size: `192`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0xe9c0`
- `0xf280`
- `0x13c30`
- `0x252e0`

## callees

- `0x147a0`
- `0x23020`
- `0x24380`
- `0x243b0`
- `0x24400`
- `0x24410`
- `0x24c50`
- `0x25170`
- `0x251a0`

## pseudocode

```c

```

## disassembly

```asm
0x251a0  ldc.i4.3
0x251a1  stloc.0
0x251a2  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x251a7  stloc.1
0x251a8  ldarg.0
0x251a9  call     instance class System.Deployment.Application.Manifest.DependentAssembly[] System.Deployment.Application.Manifest.AssemblyManifest::get_DependentAssemblies()
0x251ae  stloc.3
0x251af  ldc.i4.0
0x251b0  stloc.s  4
0x251b2  br       loc_2523B
0x251b7  ldloc.3
0x251b8  ldloc.s  4
0x251ba  ldelem.ref
0x251bb  stloc.s  5
0x251bd  ldloc.s  5
0x251bf  callvirt instance bool System.Deployment.Application.Manifest.DependentAssembly::get_IsPreRequisite()
0x251c4  brtrue.s loc_25235
0x251c6  ldarg.1
0x251c7  brtrue.s loc_251D2
0x251c9  ldloc.s  5
0x251cb  callvirt instance bool System.Deployment.Application.Manifest.DependentAssembly::get_IsOptional()
0x251d0  brfalse.s loc_251F1
0x251d2  ldarg.1
0x251d3  brfalse.s loc_25235
0x251d5  ldarg.1
0x251d6  ldloc.s  5
0x251d8  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Group()
0x251dd  ldloc.0
0x251de  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x251e3  brfalse.s loc_25235
0x251e5  ldloc.s  5
0x251e7  callvirt instance bool System.Deployment.Application.Manifest.DependentAssembly::get_IsOptional()
0x251ec  brtrue.s loc_251F1
0x251ee  ldarg.2
0x251ef  brtrue.s loc_25235
0x251f1  ldnull
0x251f2  stloc.s  6
0x251f4  ldloc.s  5
0x251f6  call     bool System.Deployment.Application.Manifest.AssemblyManifest::IsResourceReference(class System.Deployment.Application.Manifest.DependentAssembly dependentAssembly)
0x251fb  brfalse.s loc_2520F
0x251fd  ldc.i4.s 0x10
0x251ff  ldstr    aExSatelliteres// "Ex_SatelliteResourcesNotSupported"
0x25204  call     string System.Deployment.Application.Resources::GetString(string s)
0x25209  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x2520e  throw
0x2520f  ldloc.s  5
0x25211  stloc.s  6
0x25213  ldloc.s  6
0x25215  brfalse.s loc_25235
0x25217  ldloc.1
0x25218  ldloc.s  6
0x2521a  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x2521f  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x25224  brtrue.s loc_25235
0x25226  ldloc.1
0x25227  ldloc.s  6
0x25229  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x2522e  ldloc.s  6
0x25230  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x25235  ldloc.s  4
0x25237  ldc.i4.1
0x25238  add
0x25239  stloc.s  4
0x2523b  ldloc.s  4
0x2523d  ldloc.3
0x2523e  ldlen
0x2523f  conv.i4
0x25240  blt      loc_251B7
0x25245  ldloc.1
0x25246  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x2524b  newarr   System.Deployment.Application.Manifest.DependentAssembly
0x25250  stloc.2
0x25251  ldloc.1
0x25252  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0x25257  ldloc.2
0x25258  ldc.i4.0
0x25259  callvirt instance void [mscorlib]System.Collections.ICollection::CopyTo(class [mscorlib]System.Array, int32)
0x2525e  ldloc.2
0x2525f  ret
```
