# System.Deployment.Application.Logger::GetCurrentThreadLogger

- ea: `0x17390`
- end: `0x17409`
- name: `System.Deployment.Application.Logger::GetCurrentThreadLogger`
- size: `121`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x17660`
- `0x176f0`
- `0x17760`
- `0x177b0`
- `0x177e0`
- `0x17810`
- `0x17870`
- `0x178a0`
- `0x17910`
- `0x179b0`
- `0x17a50`
- `0x17ac0`
- `0x17af0`
- `0x17b20`
- `0x17ba0`
- `0x17c20`
- `0x17d90`
- `0x17e00`

## callees

- `0x17380`
- `0x17390`

## pseudocode

```c

```

## disassembly

```asm
0x17390  ldnull
0x17391  stloc.0
0x17392  call     unsigned int32 System.Deployment.Application.Logger::GetCurrentLogThreadId()
0x17397  stloc.1
0x17398  ldsfld   object System.Deployment.Application.Logger::_logAccessLock
0x1739d  stloc.2
0x1739e  ldc.i4.0
0x1739f  stloc.3
0x173a0  ldloc.2
0x173a1  ldloca.s 3
0x173a3  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x173a8  ldsfld   class [mscorlib]System.Collections.Hashtable System.Deployment.Application.Logger::_threadLogIdTable
0x173ad  ldloc.1
0x173ae  box      [mscorlib]System.UInt32
0x173b3  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x173b8  brfalse.s loc_173FB
0x173ba  ldsfld   class [mscorlib]System.Collections.Hashtable System.Deployment.Application.Logger::_threadLogIdTable
0x173bf  ldloc.1
0x173c0  box      [mscorlib]System.UInt32
0x173c5  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x173ca  castclass LogIdentity
0x173cf  stloc.s  4
0x173d1  ldsfld   class [mscorlib]System.Collections.Hashtable System.Deployment.Application.Logger::_loggerCollection
0x173d6  ldloc.s  4
0x173d8  callvirt instance string [mscorlib]System.Object::ToString()
0x173dd  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x173e2  brfalse.s loc_173FB
0x173e4  ldsfld   class [mscorlib]System.Collections.Hashtable System.Deployment.Application.Logger::_loggerCollection
0x173e9  ldloc.s  4
0x173eb  callvirt instance string [mscorlib]System.Object::ToString()
0x173f0  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x173f5  castclass System.Deployment.Application.Logger
0x173fa  stloc.0
0x173fb  leave.s  loc_17407
0x173fd  ldloc.3
0x173fe  brfalse.s loc_17406
0x17400  ldloc.2
0x17401  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x17406  endfinally
0x17407  ldloc.0
0x17408  ret
```
