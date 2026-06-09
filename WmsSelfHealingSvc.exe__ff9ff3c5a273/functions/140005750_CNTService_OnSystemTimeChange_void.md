# CNTService::OnSystemTimeChange(void)

- ea: `0x140005750`
- end: `0x14000575c`
- name: `?OnSystemTimeChange@CNTService@@UEAAXXZ`
- size: `12`
- prototype: `void __fastcall(CNTService *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400036a0`

## string_xrefs

- `0x140005750`: `CNTService::OnSystemTimeChange\n`

## pseudocode

```c
void __fastcall CNTService::OnSystemTimeChange(CNTService *this)
{
  DEBUGMSG(L"CNTService::OnSystemTimeChange\n");
}

```

## disassembly

```asm
0x140005750  lea     rcx, aCntserviceOnsy; "CNTService::OnSystemTimeChange\n"
0x140005757  jmp     ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
```
