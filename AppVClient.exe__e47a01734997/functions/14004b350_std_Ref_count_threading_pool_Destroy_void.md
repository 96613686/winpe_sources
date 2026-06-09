# std::_Ref_count<threading::pool>::_Destroy(void)

- ea: `0x14004b350`
- end: `0x14004b3a0`
- name: `?_Destroy@?$_Ref_count@Upool@threading@@@std@@EEAAXXZ`
- size: `80`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x140004558`
- `0x14004b350`

## import_xrefs

- `KERNEL32!CloseThreadpool` at `0x14004b387`
- `KERNEL32!CloseThreadpool` at `0x14004b387`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x14004b379`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x14004b379`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x14004b36f`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x14004b36f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Ref_count<threading::pool>::_Destroy(__int64 a1)
{
  PTP_POOL *v1; // rbx
  struct _TP_CLEANUP_GROUP *v2; // rcx

  v1 = *(PTP_POOL **)(a1 + 16);
  if ( v1 )
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
0x14004b350  push    rbx
0x14004b352  sub     rsp, 20h
0x14004b356  mov     rbx, [rcx+10h]
0x14004b35a  test    rbx, rbx
0x14004b35d  jz      short loc_14004B39A
0x14004b35f  mov     rcx, [rbx+50h]; ptpcg
0x14004b363  test    rcx, rcx
0x14004b366  jz      short loc_14004B37F
0x14004b368  xor     r8d, r8d; pvCleanupContext
0x14004b36b  lea     edx, [r8+1]; fCancelPendingCallbacks
0x14004b36f  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x14004b375  mov     rcx, [rbx+50h]; ptpcg
0x14004b379  call    cs:__imp_CloseThreadpoolCleanupGroup
0x14004b37f  mov     rcx, [rbx]; ptpp
0x14004b382  test    rcx, rcx
0x14004b385  jz      short loc_14004B38D
0x14004b387  call    cs:__imp_CloseThreadpool
0x14004b38d  mov     edx, 58h ; 'X'
0x14004b392  mov     rcx, rbx; Block
0x14004b395  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14004b39a  add     rsp, 20h
0x14004b39e  pop     rbx
0x14004b39f  retn
```
