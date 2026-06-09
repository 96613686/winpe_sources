# Microsoft::WRL::Wrappers::HandleT<TpCleanupGroupTraits>::InternalClose(void)

- ea: `0x1800744d0`
- end: `0x1800744f9`
- name: `?InternalClose@?$HandleT@UTpCleanupGroupTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800744e2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800744e2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800744eb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800744eb`

## pseudocode

```c
char __fastcall Microsoft::WRL::Wrappers::HandleT<TpCleanupGroupTraits>::InternalClose(__int64 a1)
{
  struct _TP_CLEANUP_GROUP *v1; // rbx

  v1 = *(struct _TP_CLEANUP_GROUP **)(a1 + 8);
  CloseThreadpoolCleanupGroupMembers(v1, 0, 0);
  CloseThreadpoolCleanupGroup(v1);
  return 1;
}

```

## disassembly

```asm
0x1800744d0  push    rbx
0x1800744d2  sub     rsp, 20h
0x1800744d6  mov     rbx, [rcx+8]
0x1800744da  xor     r8d, r8d; pvCleanupContext
0x1800744dd  mov     rcx, rbx; ptpcg
0x1800744e0  xor     edx, edx; fCancelPendingCallbacks
0x1800744e2  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800744e8  mov     rcx, rbx; ptpcg
0x1800744eb  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800744f1  mov     al, 1
0x1800744f3  add     rsp, 20h
0x1800744f7  pop     rbx
0x1800744f8  retn
```
