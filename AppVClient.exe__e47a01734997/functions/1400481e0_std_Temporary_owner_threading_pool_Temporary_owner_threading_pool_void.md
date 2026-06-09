# std::_Temporary_owner<threading::pool>::~_Temporary_owner<threading::pool>(void)

- ea: `0x1400481e0`
- end: `0x14004822f`
- name: `??1?$_Temporary_owner@Upool@threading@@@std@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(PTP_POOL **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400680cd`

## callees

- `0x140004558`
- `0x1400481e0`

## import_xrefs

- `KERNEL32!CloseThreadpool` at `0x140048216`
- `KERNEL32!CloseThreadpool` at `0x140048216`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x140048208`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x140048208`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1400481fe`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1400481fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Temporary_owner<threading::pool>::~_Temporary_owner<threading::pool>(PTP_POOL **a1)
{
  PTP_POOL *v1; // rbx
  struct _TP_CLEANUP_GROUP *v2; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v2 = v1[10];
    if ( v2 )
    {
      CloseThreadpoolCleanupGroupMembers(v2, 1, 0);
      CloseThreadpoolCleanupGroup(v1[10]);
    }
    if ( *v1 )
      CloseThreadpool(*v1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x1400481e0  push    rbx
0x1400481e2  sub     rsp, 20h
0x1400481e6  mov     rbx, [rcx]
0x1400481e9  test    rbx, rbx
0x1400481ec  jz      short loc_140048229
0x1400481ee  mov     rcx, [rbx+50h]; ptpcg
0x1400481f2  test    rcx, rcx
0x1400481f5  jz      short loc_14004820E
0x1400481f7  xor     r8d, r8d; pvCleanupContext
0x1400481fa  lea     edx, [r8+1]; fCancelPendingCallbacks
0x1400481fe  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x140048204  mov     rcx, [rbx+50h]; ptpcg
0x140048208  call    cs:__imp_CloseThreadpoolCleanupGroup
0x14004820e  mov     rcx, [rbx]; ptpp
0x140048211  test    rcx, rcx
0x140048214  jz      short loc_14004821C
0x140048216  call    cs:__imp_CloseThreadpool
0x14004821c  mov     edx, 58h ; 'X'
0x140048221  mov     rcx, rbx; Block
0x140048224  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140048229  add     rsp, 20h
0x14004822d  pop     rbx
0x14004822e  retn
```
