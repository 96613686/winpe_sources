# Microsoft::WRL::Wrappers::HandleT<TpCleanupGroupTraits>::InternalClose(void)

- ea: `0x18005a6c0`
- end: `0x18005a6f6`
- name: `?InternalClose@?$HandleT@UTpCleanupGroupTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18005a6d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18005a6d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18005a6e1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18005a6e1`

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
0x18005a6c0  push    rbx
0x18005a6c2  sub     rsp, 20h
0x18005a6c6  mov     rbx, [rcx+8]
0x18005a6ca  xor     r8d, r8d; pvCleanupContext
0x18005a6cd  mov     rcx, rbx; ptpcg
0x18005a6d0  xor     edx, edx; fCancelPendingCallbacks
0x18005a6d2  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18005a6d9  nop     dword ptr [rax+rax+00h]
0x18005a6de  mov     rcx, rbx; ptpcg
0x18005a6e1  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18005a6e8  nop     dword ptr [rax+rax+00h]
0x18005a6ed  mov     al, 1
0x18005a6ef  add     rsp, 20h
0x18005a6f3  pop     rbx
0x18005a6f4  retn
```
