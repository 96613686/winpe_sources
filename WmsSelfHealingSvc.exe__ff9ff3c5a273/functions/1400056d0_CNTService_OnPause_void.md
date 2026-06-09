# CNTService::OnPause(void)

- ea: `0x1400056d0`
- end: `0x1400056dc`
- name: `?OnPause@CNTService@@UEAAXXZ`
- size: `12`
- prototype: `void __fastcall(CNTService *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400036a0`

## string_xrefs

- `0x1400056d0`: `CNTService::OnPause\n`

## pseudocode

```c
void __fastcall CNTService::OnPause(CNTService *this)
{
  DEBUGMSG(L"CNTService::OnPause\n");
}

```

## disassembly

```asm
0x1400056d0  lea     rcx, aCntserviceOnpa; "CNTService::OnPause\n"
0x1400056d7  jmp     ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
```
