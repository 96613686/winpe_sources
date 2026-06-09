# CTaskCounter::Cleanup(void)

- ea: `0x180007b54`
- end: `0x180007bab`
- name: `?Cleanup@CTaskCounter@@SAXXZ`
- size: `87`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180006ad0`
- `0x18000770c`

## callees

- `0x180007b54`
- `0x180008070`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180007b7f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180007b7f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180007b8e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180007b8e`

## pseudocode

```c
void CTaskCounter::Cleanup(void)
{
  struct CTaskCounter *v0; // rax
  struct CTaskCounter *v1; // rax

  *(_DWORD *)CTaskCounter::Instance() = 0;
  if ( *((_QWORD *)CTaskCounter::Instance() + 15) )
  {
    v0 = CTaskCounter::Instance();
    CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)v0 + 15), 1, 0);
    v1 = CTaskCounter::Instance();
    CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)v1 + 15));
    CTaskCounter::Instance();
    *((_QWORD *)CTaskCounter::Instance() + 15) = 0;
  }
}

```

## disassembly

```asm
0x180007b54  sub     rsp, 28h
0x180007b58  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007b5d  mov     dword ptr [rax], 0
0x180007b63  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007b68  cmp     qword ptr [rax+78h], 0
0x180007b6d  jz      short loc_180007BA6
0x180007b6f  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007b74  xor     r8d, r8d; pvCleanupContext
0x180007b77  mov     rcx, [rax+78h]; ptpcg
0x180007b7b  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180007b7f  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180007b85  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007b8a  mov     rcx, [rax+78h]; ptpcg
0x180007b8e  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180007b94  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007b99  call    ?Instance@CTaskCounter@@SAAEAV1@XZ; CTaskCounter::Instance(void)
0x180007b9e  mov     qword ptr [rax+78h], 0
0x180007ba6  add     rsp, 28h
0x180007baa  retn
```
