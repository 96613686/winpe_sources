# Microsoft.Office.Server.Security.SecurityContext::Dispose

- ea: `0x2ccb0`
- end: `0x2cdad`
- name: `Microsoft.Office.Server.Security.SecurityContext::Dispose`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x2cb20`

## callees

- `0x2ccb0`
- `0x2ce20`
- `0x2ce30`
- `0x2ce40`
- `0x2ce70`

## string_xrefs

- `0x2ccd1`: `SecurityContext must be disposed on original calling thread (ID: {0} CurrentID: {1}).`

## pseudocode

```c

```

## disassembly

```asm
0x2ccb0  ldarg.0
0x2ccb1  ldfld    bool Microsoft.Office.Server.Security.SecurityContext::m_IsAlive
0x2ccb6  brfalse  loc_2CDAC
0x2ccbb  ldc.i4.m1
0x2ccbc  stloc.0
0x2ccbd  call     int32 NativeMethods::GetCurrentThreadId()
0x2ccc2  stloc.0
0x2ccc3  ldloc.0
0x2ccc4  ldarg.0
0x2ccc5  ldfld    int32 Microsoft.Office.Server.Security.SecurityContext::m_ThreadId
0x2ccca  beq.s    loc_2CD04
0x2cccc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ccd1  ldstr    aSecuritycontex_0// "SecurityContext must be disposed on ori"...
0x2ccd6  ldc.i4.2
0x2ccd7  newarr   [mscorlib]System.Object
0x2ccdc  stloc.s  6
0x2ccde  ldloc.s  6
0x2cce0  ldc.i4.0
0x2cce1  ldarg.0
0x2cce2  ldfld    int32 Microsoft.Office.Server.Security.SecurityContext::m_ThreadId
0x2cce7  box      [mscorlib]System.Int32
0x2ccec  stelem.ref
0x2cced  ldloc.s  6
0x2ccef  ldc.i4.1
0x2ccf0  ldloc.0
0x2ccf1  box      [mscorlib]System.Int32
0x2ccf6  stelem.ref
0x2ccf7  ldloc.s  6
0x2ccf9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2ccfe  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2cd03  throw
0x2cd04  ldarg.0
0x2cd05  ldc.i4.0
0x2cd06  stfld    bool Microsoft.Office.Server.Security.SecurityContext::m_IsAlive
0x2cd0b  ldarg.0
0x2cd0c  call     void [mscorlib]System.GC::SuppressFinalize(object)
0x2cd11  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x2cd16  ldarg.0
0x2cd17  ldfld    native int Microsoft.Office.Server.Security.SecurityContext::m_hPriorToken
0x2cd1c  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x2cd21  brfalse.s loc_2CD37
0x2cd23  call     bool NativeMethods::Win32RevertToSelf()
0x2cd28  brtrue.s loc_2CD56
0x2cd2a  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x2cd2f  stloc.1
0x2cd30  ldloc.1
0x2cd31  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x2cd36  throw
0x2cd37  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x2cd3c  ldarg.0
0x2cd3d  ldfld    native int Microsoft.Office.Server.Security.SecurityContext::m_hPriorToken
0x2cd42  call     bool NativeMethods::SetThreadToken(native int Thread, native int Token)
0x2cd47  brtrue.s loc_2CD56
0x2cd49  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x2cd4e  stloc.2
0x2cd4f  ldloc.2
0x2cd50  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x2cd55  throw
0x2cd56  leave.s  loc_2CD76
0x2cd58  stloc.3
0x2cd59  ldc.i4.s 0x10
0x2cd5b  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0x2cd60  stloc.s  4
0x2cd62  ldloc.s  4
0x2cd64  callvirt instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x2cd69  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2cd6e  ldloc.3
0x2cd6f  callvirt instance void [mscorlib]System.Threading.Thread::Abort(object)
0x2cd74  leave.s  loc_2CD76
0x2cd76  leave.s  loc_2CDA6
0x2cd78  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x2cd7d  ldarg.0
0x2cd7e  ldfld    native int Microsoft.Office.Server.Security.SecurityContext::m_hPriorToken
0x2cd83  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x2cd88  brfalse.s loc_2CDA5
0x2cd8a  ldarg.0
0x2cd8b  ldfld    native int Microsoft.Office.Server.Security.SecurityContext::m_hPriorToken
0x2cd90  stloc.s  5
0x2cd92  ldarg.0
0x2cd93  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x2cd98  stfld    native int Microsoft.Office.Server.Security.SecurityContext::m_hPriorToken
0x2cd9d  ldloc.s  5
0x2cd9f  call     bool NativeMethods::CloseHandle(native int hObject)
0x2cda4  pop
0x2cda5  endfinally
0x2cda6  ldarg.0
0x2cda7  call     void [mscorlib]System.GC::KeepAlive(object)
0x2cdac  ret
```
