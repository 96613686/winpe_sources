# Microsoft.VisualStudio.Setup.Dependencies.Extensions::GetRequestedState

- ea: `0x163d0`
- end: `0x16465`
- name: `Microsoft.VisualStudio.Setup.Dependencies.Extensions::GetRequestedState`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14920`
- `0x173e0`

## callees

- `0x7f20`
- `0x7f40`
- `0x81e0`
- `0x11b00`
- `0x163d0`
- `0x16470`
- `0x16690`

## pseudocode

```c

```

## disassembly

```asm
0x163d0  ldarg.0
0x163d1  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x163d6  callvirt instance valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x163db  stloc.0
0x163dc  ldloc.0
0x163dd  switch   loc_163F8, loc_16409, loc_1640B, loc_1640B, loc_1640D
0x163f6  br.s     loc_1640F
0x163f8  ldarg.0
0x163f9  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x163fe  callvirt instance valuetype Microsoft.VisualStudio.Setup.CurrentState Microsoft.VisualStudio.Setup.IPackage::get_CurrentState()
0x16403  call     valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.Dependencies.Extensions::GetRequestedState(valuetype Microsoft.VisualStudio.Setup.CurrentState currentState)
0x16408  ret
0x16409  ldc.i4.1
0x1640a  ret
0x1640b  ldc.i4.3
0x1640c  ret
0x1640d  ldc.i4.4
0x1640e  ret
0x1640f  ldarg.1
0x16410  brtrue.s loc_16415
0x16412  ldnull
0x16413  br.s     loc_1641C
0x16415  ldarg.1
0x16416  ldc.i4.0
0x16417  call     T0x2B00003F
0x1641c  dup
0x1641d  brtrue.s loc_16422
0x1641f  pop
0x16420  br.s     loc_16463
0x16422  ldstr    aUnexpected01Fo// "Unexpected {0} {1} for {2}; interpretin"...
0x16427  ldc.i4.4
0x16428  newarr   [mscorlib]System.Object
0x1642d  dup
0x1642e  ldc.i4.0
0x1642f  ldstr    aRequestedstate// "RequestedState"
0x16434  stelem.ref
0x16435  dup
0x16436  ldc.i4.1
0x16437  ldloc.0
0x16438  box      Microsoft.VisualStudio.Setup.RequestedState
0x1643d  stelem.ref
0x1643e  dup
0x1643f  ldc.i4.2
0x16440  ldarg.0
0x16441  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x16446  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x1644b  stelem.ref
0x1644c  dup
0x1644d  ldc.i4.3
0x1644e  ldstr    aAbsent// "Absent"
0x16453  stelem.ref
0x16454  call     string [mscorlib]System.String::Format(string, object[])
0x16459  call     T0x2B000016
0x1645e  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string format, object[] args)
0x16463  ldc.i4.1
0x16464  ret
```
