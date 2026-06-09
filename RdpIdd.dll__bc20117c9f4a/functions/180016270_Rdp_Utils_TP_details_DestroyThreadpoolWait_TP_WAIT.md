# Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *)

- ea: `0x180016270`
- end: `0x1800162b2`
- name: `?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAXPEAU_TP_WAIT@@@Z`
- size: `66`
- prototype: `void __fastcall(PTP_WAIT pwa, struct _TP_WAIT *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800217dc`
- `0x18002a4e4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800162a6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180016292`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180016292`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001627e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001627e`

## pseudocode

```c
void __fastcall Rdp::Utils::TP::details::DestroyThreadpoolWait(PTP_WAIT pwa, struct _TP_WAIT *a2)
{
  SetThreadpoolWait(pwa, 0, 0);
  WaitForThreadpoolWaitCallbacks(pwa, 1);
  CloseThreadpoolWait(pwa);
}

```

## disassembly

```asm
0x180016270  push    rbx
0x180016272  sub     rsp, 20h
0x180016276  xor     r8d, r8d; pftTimeout
0x180016279  xor     edx, edx; h
0x18001627b  mov     rbx, rcx
0x18001627e  call    cs:__imp_SetThreadpoolWait
0x180016285  nop     dword ptr [rax+rax+00h]
0x18001628a  mov     edx, 1; fCancelPendingCallbacks
0x18001628f  mov     rcx, rbx; pwa
0x180016292  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180016299  nop     dword ptr [rax+rax+00h]
0x18001629e  mov     rcx, rbx
0x1800162a1  add     rsp, 20h
0x1800162a5  pop     rbx
0x1800162a6  jmp     cs:__imp_CloseThreadpoolWait
```
