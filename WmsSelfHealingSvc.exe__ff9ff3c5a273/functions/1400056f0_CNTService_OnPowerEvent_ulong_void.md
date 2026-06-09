# CNTService::OnPowerEvent(ulong,void *)

- ea: `0x1400056f0`
- end: `0x1400056fc`
- name: `?OnPowerEvent@CNTService@@UEAAXKPEAX@Z`
- size: `12`
- prototype: `void __fastcall(CNTService *this, __int64, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400036a0`

## string_xrefs

- `0x1400056f0`: `CNTService::OnPowerEvent\n`

## pseudocode

```c
void __fastcall CNTService::OnPowerEvent(CNTService *this, __int64 a2, void *a3)
{
  DEBUGMSG(L"CNTService::OnPowerEvent\n", a2, a3);
}

```

## disassembly

```asm
0x1400056f0  lea     rcx, aCntserviceOnpo; "CNTService::OnPowerEvent\n"
0x1400056f7  jmp     ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
```
