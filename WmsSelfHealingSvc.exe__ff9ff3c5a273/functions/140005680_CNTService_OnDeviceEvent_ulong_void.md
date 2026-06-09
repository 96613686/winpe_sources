# CNTService::OnDeviceEvent(ulong,void *)

- ea: `0x140005680`
- end: `0x14000568c`
- name: `?OnDeviceEvent@CNTService@@UEAAXKPEAX@Z`
- size: `12`
- prototype: `void __fastcall(CNTService *this, __int64, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400036a0`

## string_xrefs

- `0x140005680`: `CNTService::OnDeviceEvent\n`

## pseudocode

```c
void __fastcall CNTService::OnDeviceEvent(CNTService *this, __int64 a2, void *a3)
{
  DEBUGMSG(L"CNTService::OnDeviceEvent\n", a2, a3);
}

```

## disassembly

```asm
0x140005680  lea     rcx, aCntserviceOnde; "CNTService::OnDeviceEvent\n"
0x140005687  jmp     ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
```
