# CNTService::OnSessionEvent(ulong,void *)

- ea: `0x140005710`
- end: `0x14000571c`
- name: `?OnSessionEvent@CNTService@@UEAAXKPEAX@Z`
- size: `12`
- prototype: `void __fastcall(CNTService *this, __int64, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400036a0`

## string_xrefs

- `0x140005710`: `CNTService::OnSessionEvent\n`

## pseudocode

```c
void __fastcall CNTService::OnSessionEvent(CNTService *this, __int64 a2, void *a3)
{
  DEBUGMSG(L"CNTService::OnSessionEvent\n", a2, a3);
}

```

## disassembly

```asm
0x140005710  lea     rcx, aCntserviceOnse; "CNTService::OnSessionEvent\n"
0x140005717  jmp     ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
```
