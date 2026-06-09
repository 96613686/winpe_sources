# CNetworkExplorerFolderViewCB::_StopTimer(void)

- ea: `0x18000ced8`
- end: `0x18000cf09`
- name: `?_StopTimer@CNetworkExplorerFolderViewCB@@AEAAJXZ`
- size: `49`
- prototype: `__int64 __fastcall(CNetworkExplorerFolderViewCB *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800069c0`
- `0x180008c48`
- `0x18000cc44`
- `0x18000ce34`

## callees

- `0x18000ced8`

## import_xrefs

- `KERNEL32!DeleteTimerQueueEx` at `0x18000cefc`
- `KERNEL32!DeleteTimerQueueEx` at `0x18000cefc`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolderViewCB::_StopTimer(CNetworkExplorerFolderViewCB *this)
{
  void *v1; // rax

  v1 = (void *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 6) = 0;
  if ( v1 )
  {
    *((_QWORD *)this + 5) = 0;
    DeleteTimerQueueEx(v1, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ced8  sub     rsp, 28h
0x18000cedc  mov     rax, [rcx+28h]
0x18000cee0  mov     qword ptr [rcx+30h], 0
0x18000cee8  test    rax, rax
0x18000ceeb  jz      short loc_18000CF02
0x18000ceed  mov     qword ptr [rcx+28h], 0
0x18000cef5  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000cef9  mov     rcx, rax; TimerQueue
0x18000cefc  call    cs:__imp_DeleteTimerQueueEx
0x18000cf02  xor     eax, eax
0x18000cf04  add     rsp, 28h
0x18000cf08  retn
```
