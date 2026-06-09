# FwpsFlowRemoveContext0

- ea: `0x1800049c0`
- end: `0x1800049f5`
- name: `FwpsFlowRemoveContext0`
- size: `53`
- prototype: `NTSTATUS __stdcall(UINT64 flowId, UINT16 layerId, UINT32 calloutId)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004904`
- `0x1800049c0`

## import_xrefs

- `NETIO!WfpRemoveContextFromFlow` at `0x1800049c8`
- `NETIO!WfpRemoveContextFromFlow` at `0x1800049c8`

## string_xrefs

- `0x1800049e4`: `WfpRemoveContextFromFlow`

## pseudocode

```c
NTSTATUS __stdcall FwpsFlowRemoveContext0(UINT64 flowId, UINT16 layerId, UINT32 calloutId)
{
  NTSTATUS v3; // ebx
  int v4; // eax
  __int64 v5; // rcx

  v3 = 0;
  v4 = WfpRemoveContextFromFlow(flowId, layerId, calloutId);
  if ( v4 < 0 )
    return WfpReportSysErrorAsNtStatus(v5, (int)"WfpRemoveContextFromFlow", v4);
  return v3;
}

```

## disassembly

```asm
0x1800049c0  push    rbx
0x1800049c2  sub     rsp, 20h
0x1800049c6  xor     ebx, ebx
0x1800049c8  call    cs:__imp_WfpRemoveContextFromFlow
0x1800049cf  nop     dword ptr [rax+rax+00h]
0x1800049d4  test    eax, eax
0x1800049d6  js      short loc_1800049E1
0x1800049d8  mov     eax, ebx
0x1800049da  add     rsp, 20h
0x1800049de  pop     rbx
0x1800049df  retn
0x1800049e1  mov     r8d, eax
0x1800049e4  lea     rdx, aWfpremoveconte_0; "WfpRemoveContextFromFlow"
0x1800049eb  call    WfpReportSysErrorAsNtStatus
0x1800049f0  mov     rbx, rax
0x1800049f3  jmp     short loc_1800049D8
```
