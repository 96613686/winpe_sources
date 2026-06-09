# CReader::CloseThreadpool(void)

- ea: `0x18002d62c`
- end: `0x18002d6ae`
- name: `?CloseThreadpool@CReader@@IEAAXXZ`
- size: `130`
- prototype: `void __fastcall(PTP_CLEANUP_GROUP *this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180017c60`
- `0x18002d530`

## callees

- `0x1800044e0`
- `0x18000457c`
- `0x18000d7a0`
- `0x18000d9c0`
- `0x18002d62c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002d670`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002d670`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002d663`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002d663`

## pseudocode

```c
void __fastcall CReader::CloseThreadpool(PTP_CLEANUP_GROUP *this)
{
  struct _TP_CLEANUP_GROUP *v2; // rcx
  char v3; // [rsp+30h] [rbp+8h] BYREF

  CReader::PowerDownTimeoutStop((CReader *)this);
  CReader::TransactionTimeoutStop((CReader *)this);
  CLockWrite::CLockWrite((CLockWrite *)&v3, (struct CAccessLock *)(this + 7));
  v2 = this[87];
  if ( v2 )
  {
    CloseThreadpoolCleanupGroupMembers(v2, 1, 0);
    CloseThreadpoolCleanupGroup(this[87]);
    this[87] = 0;
  }
  this[88] = 0;
  this[89] = 0;
  *((_DWORD *)this + 11) = 0;
  CLockWrite::~CLockWrite((CLockWrite *)&v3);
}

```

## disassembly

```asm
0x18002d62c  push    rbx
0x18002d62e  sub     rsp, 20h
0x18002d632  mov     rbx, rcx
0x18002d635  call    ?PowerDownTimeoutStop@CReader@@IEAAXXZ; CReader::PowerDownTimeoutStop(void)
0x18002d63a  mov     rcx, rbx; this
0x18002d63d  call    ?TransactionTimeoutStop@CReader@@IEAAXXZ; CReader::TransactionTimeoutStop(void)
0x18002d642  lea     rdx, [rbx+38h]; struct CAccessLock *
0x18002d646  lea     rcx, [rsp+28h+arg_0]; this
0x18002d64b  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x18002d650  mov     rcx, [rbx+2B8h]; ptpcg
0x18002d657  test    rcx, rcx
0x18002d65a  jz      short loc_18002D681
0x18002d65c  xor     r8d, r8d; pvCleanupContext
0x18002d65f  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18002d663  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18002d669  mov     rcx, [rbx+2B8h]; ptpcg
0x18002d670  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18002d676  mov     qword ptr [rbx+2B8h], 0
0x18002d681  lea     rcx, [rsp+28h+arg_0]; this
0x18002d686  mov     qword ptr [rbx+2C0h], 0
0x18002d691  mov     qword ptr [rbx+2C8h], 0
0x18002d69c  mov     dword ptr [rbx+2Ch], 0
0x18002d6a3  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x18002d6a8  add     rsp, 20h
0x18002d6ac  pop     rbx
0x18002d6ad  retn
```
