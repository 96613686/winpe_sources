# CNTService::OnAddParameterKeys(HKEY__ *)

- ea: `0x140005640`
- end: `0x14000564c`
- name: `?OnAddParameterKeys@CNTService@@UEAAXPEAUHKEY__@@@Z`
- size: `12`
- prototype: `void __fastcall(CNTService *__hidden this, HKEY)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400036a0`

## string_xrefs

- `0x140005640`: `CNTService::OnAddParameterKeys\n`

## pseudocode

```c
void __fastcall CNTService::OnAddParameterKeys(CNTService *this, HKEY a2)
{
  DEBUGMSG(L"CNTService::OnAddParameterKeys\n", a2);
}

```

## disassembly

```asm
0x140005640  lea     rcx, aCntserviceOnad; "CNTService::OnAddParameterKeys\n"
0x140005647  jmp     ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
```
