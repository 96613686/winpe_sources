# FxStubDriverUnloadCommon(void)

- ea: `0x140015754`
- end: `0x140015784`
- name: `?FxStubDriverUnloadCommon@@YAXXZ`
- size: `48`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400157c4`
- `0x140015940`

## callees

- `0x140015ad4`

## import_xrefs

- `WDFLDR!WdfVersionUnbind` at `0x140015772`
- `WDFLDR!WdfVersionUnbind` at `0x140015772`

## pseudocode

```c
void __fastcall FxStubDriverUnloadCommon(struct _WDF_BIND_INFO *a1)
{
  FxStubUnbindClasses(a1);
  WdfVersionUnbind(&WPP_MAIN_CB.Queue, &WdfBindInfo, WdfDriverGlobals);
}

```

## disassembly

```asm
0x140015754  sub     rsp, 28h
0x140015758  call    ?FxStubUnbindClasses@@YAXPEAU_WDF_BIND_INFO@@@Z; FxStubUnbindClasses(_WDF_BIND_INFO *)
0x14001575d  mov     r8, cs:WdfDriverGlobals
0x140015764  lea     rdx, WdfBindInfo
0x14001576b  lea     rcx, WPP_MAIN_CB.Queue
0x140015772  call    cs:__imp_WdfVersionUnbind
0x140015779  nop     dword ptr [rax+rax+00h]
0x14001577e  add     rsp, 28h
0x140015782  retn
```
