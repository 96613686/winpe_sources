# CNTService::OnShutdown(void)

- ea: `0x140005730`
- end: `0x14000573c`
- name: `?OnShutdown@CNTService@@UEAAXXZ`
- size: `12`
- prototype: `void __fastcall(CNTService *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400036a0`

## string_xrefs

- `0x140005730`: `CNTService::OnShutdown\n`

## pseudocode

```c
void __fastcall CNTService::OnShutdown(CNTService *this)
{
  DEBUGMSG(L"CNTService::OnShutdown\n");
}

```

## disassembly

```asm
0x140005730  lea     rcx, aCntserviceOnsh; "CNTService::OnShutdown\n"
0x140005737  jmp     ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
```
