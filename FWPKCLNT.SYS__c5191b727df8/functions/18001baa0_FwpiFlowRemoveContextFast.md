# FwpiFlowRemoveContextFast

- ea: `0x18001baa0`
- end: `0x18001bad3`
- name: `FwpiFlowRemoveContextFast`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004904`
- `0x18001baa0`

## import_xrefs

- `NETIO!WfpRemoveContextFromFlowFast` at `0x18001baa8`
- `NETIO!WfpRemoveContextFromFlowFast` at `0x18001baa8`

## string_xrefs

- `0x18001babb`: `WfpRemoveContextFromFlowFast`

## pseudocode

```c
__int64 FwpiFlowRemoveContextFast()
{
  unsigned int v0; // ebx
  int v1; // eax
  __int64 v2; // rcx

  v0 = 0;
  v1 = WfpRemoveContextFromFlowFast();
  if ( v1 < 0 )
    return (unsigned int)WfpReportSysErrorAsNtStatus(v2, (int)"WfpRemoveContextFromFlowFast", v1);
  return v0;
}

```

## disassembly

```asm
0x18001baa0  push    rbx
0x18001baa2  sub     rsp, 20h
0x18001baa6  xor     ebx, ebx
0x18001baa8  call    cs:__imp_WfpRemoveContextFromFlowFast
0x18001baaf  nop     dword ptr [rax+rax+00h]
0x18001bab4  test    eax, eax
0x18001bab6  jns     short loc_18001BACA
0x18001bab8  mov     r8d, eax
0x18001babb  lea     rdx, aWfpremoveconte; "WfpRemoveContextFromFlowFast"
0x18001bac2  call    WfpReportSysErrorAsNtStatus
0x18001bac7  mov     rbx, rax
0x18001baca  mov     eax, ebx
0x18001bacc  add     rsp, 20h
0x18001bad0  pop     rbx
0x18001bad1  retn
```
