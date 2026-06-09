# System.Windows.Freezable::CreateInstance

- ea: `0x34f30`
- end: `0x34f45`
- name: `System.Windows.Freezable::CreateInstance`
- size: `21`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x34d90`
- `0x34db0`
- `0x34dd0`
- `0x34e00`

## callees

- `0x34f50`
- `0x35c50`

## string_xrefs

- `0x34f37`: `CreateInstance`

## pseudocode

```c

```

## disassembly

```asm
0x34f30  ldarg.0
0x34f31  callvirt instance class System.Windows.Freezable System.Windows.Freezable::CreateInstanceCore()
0x34f36  stloc.0
0x34f37  ldstr    aCreateinstance// "CreateInstance"
0x34f3c  ldarg.0
0x34f3d  ldloc.0
0x34f3e  call     void System.Windows.Freezable::Debug_VerifyInstance(string methodName, class System.Windows.Freezable original, class System.Windows.Freezable newInstance)
0x34f43  ldloc.0
0x34f44  ret
```
