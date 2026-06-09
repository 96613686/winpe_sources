# Microsoft.Windows.Diagnosis.Network.FirewallApi.ManagedMethods::GetFWDiagnosticApps

- ea: `0x260`
- end: `0x30c`
- name: `Microsoft.Windows.Diagnosis.Network.FirewallApi.ManagedMethods::GetFWDiagnosticApps`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x3a0`

## callees

- `0x1a0`
- `0x1b0`
- `0x1c0`
- `0x1d0`
- `0x260`

## pseudocode

```c

```

## disassembly

```asm
0x260  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x265  stloc.0
0x266  ldc.i4.0
0x267  stloc.1
0x268  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x26d  stloc.2
0x26e  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x273  stloc.3
0x274  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Windows.Diagnosis.Network.FirewallApi.FWDiagnosticApp>::.ctor()
0x279  stloc.s  5
0x27b  ldc.i4   0x20A
0x280  ldnull
0x281  ldc.i4.5
0x282  ldc.i4.1
0x283  ldc.i4.0
0x284  ldloca.s 0
0x286  call     unsigned int32 Microsoft.Windows.Diagnosis.Network.FirewallApi.NativeMethods::FWOpenPolicyStore(unsigned int16 wBinaryVersion, string wszMachineOrGPO, valuetype Microsoft.Windows.Diagnosis.Network.FirewallApi.FW_STORE_TYPE StoreType, valuetype Microsoft.Windows.Diagnosis.Network.FirewallApi.FW_POLICY_ACCESS_RIGHT AccessRight, valuetype Microsoft.Windows.Diagnosis.Network.FirewallApi.FW_POLICY_STORE_FLAGS dwFlags, [out] native int& phPolicy)
0x28b  stloc.s  6
0x28d  ldloc.s  6
0x28f  brfalse.s loc_299
0x291  ldloc.s  6
0x293  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x298  throw
0x299  ldloc.0
0x29a  ldloca.s 1
0x29c  ldloca.s 2
0x29e  call     unsigned int32 Microsoft.Windows.Diagnosis.Network.FirewallApi.NativeMethods::FWDiagGetAppList(native int hPolicy, unsigned int32& pcchOut, native int& DiagApps)
0x2a3  stloc.s  6
0x2a5  ldloc.s  6
0x2a7  brfalse.s loc_2B1
0x2a9  ldloc.s  6
0x2ab  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x2b0  throw
0x2b1  ldloc.1
0x2b2  ldc.i4.0
0x2b3  ble.un.s loc_302
0x2b5  ldloc.2
0x2b6  stloc.3
0x2b7  ldc.i4.0
0x2b8  stloc.s  7
0x2ba  br.s     loc_2F7
0x2bc  ldloc.3
0x2bd  ldtoken  Microsoft.Windows.Diagnosis.Network.FirewallApi.FWDiagnosticApp
0x2c2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2c7  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x2cc  unbox.any Microsoft.Windows.Diagnosis.Network.FirewallApi.FWDiagnosticApp
0x2d1  stloc.s  4
0x2d3  ldloc.s  5
0x2d5  ldloc.s  4
0x2d7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Windows.Diagnosis.Network.FirewallApi.FWDiagnosticApp>::Add(var<u1>)
0x2dc  ldloca.s 3
0x2de  ldloca.s 3
0x2e0  call     instance int64 [mscorlib]System.IntPtr::ToInt64()
0x2e5  call     int32 [mscorlib]System.IntPtr::get_Size()
0x2ea  conv.i8
0x2eb  add
0x2ec  call     instance void [mscorlib]System.IntPtr::.ctor(int64)
0x2f1  ldloc.s  7
0x2f3  ldc.i4.1
0x2f4  add
0x2f5  stloc.s  7
0x2f7  ldloc.s  7
0x2f9  ldloc.1
0x2fa  blt.un.s loc_2BC
0x2fc  ldloc.2
0x2fd  call     void Microsoft.Windows.Diagnosis.Network.FirewallApi.NativeMethods::FWFreeDiagAppList(native int DiagApps)
0x302  ldloc.0
0x303  call     unsigned int32 Microsoft.Windows.Diagnosis.Network.FirewallApi.NativeMethods::FWClosePolicyStore(native int hPolicy)
0x308  pop
0x309  ldloc.s  5
0x30b  ret
```
