# _CSurrogate::LoadDllServer_::_1_::dtor$0

- ea: `0x14000fc30`
- end: `0x14000fc3c`
- name: `_CSurrogate::LoadDllServer_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002720`

## pseudocode

```c
__int64 __fastcall CSurrogate::LoadDllServer_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return CommonUtil::AutoRef<IManagementShield3>::~AutoRef<IManagementShield3>((__int64 *)(a2 + 152));
}

```

## disassembly

```asm
0x14000fc30  lea     rcx, [rdx+98h]
0x14000fc37  jmp     ??1?$AutoRef@UIManagementShield3@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IManagementShield3>::~AutoRef<IManagementShield3>(void)
```
