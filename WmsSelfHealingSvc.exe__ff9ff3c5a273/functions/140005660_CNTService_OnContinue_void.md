# CNTService::OnContinue(void)

- ea: `0x140005660`
- end: `0x14000566c`
- name: `?OnContinue@CNTService@@UEAAXXZ`
- size: `12`
- prototype: `void __fastcall(CNTService *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400036a0`

## string_xrefs

- `0x140005660`: `CNTService::OnContinue\n`

## pseudocode

```c
void __fastcall CNTService::OnContinue(CNTService *this)
{
  DEBUGMSG(L"CNTService::OnContinue\n");
}

```

## disassembly

```asm
0x140005660  lea     rcx, aCntserviceOnco; "CNTService::OnContinue\n"
0x140005667  jmp     ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
```
