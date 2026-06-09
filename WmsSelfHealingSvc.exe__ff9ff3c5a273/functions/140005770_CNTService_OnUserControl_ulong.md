# CNTService::OnUserControl(ulong)

- ea: `0x140005770`
- end: `0x140005787`
- name: `?OnUserControl@CNTService@@UEAAHK@Z`
- size: `23`
- prototype: `__int64 __fastcall(CNTService *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400036a0`

## string_xrefs

- `0x140005774`: `CNTService::OnUserControl\n`

## pseudocode

```c
__int64 __fastcall CNTService::OnUserControl(CNTService *this)
{
  DEBUGMSG(L"CNTService::OnUserControl\n");
  return 0;
}

```

## disassembly

```asm
0x140005770  sub     rsp, 28h
0x140005774  lea     rcx, aCntserviceOnus; "CNTService::OnUserControl\n"
0x14000577b  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140005780  xor     eax, eax
0x140005782  add     rsp, 28h
0x140005786  retn
```
