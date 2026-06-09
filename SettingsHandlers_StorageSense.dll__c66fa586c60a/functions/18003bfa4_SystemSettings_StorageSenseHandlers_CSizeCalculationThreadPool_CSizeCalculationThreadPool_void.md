# SystemSettings::StorageSenseHandlers::CSizeCalculationThreadPool::~CSizeCalculationThreadPool(void)

- ea: `0x18003bfa4`
- end: `0x18003c022`
- name: `??1CSizeCalculationThreadPool@StorageSenseHandlers@SystemSettings@@QEAA@XZ`
- size: `126`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::CSizeCalculationThreadPool *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e2a60`

## callees

- `0x18001f53c`
- `0x18003bfa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003c01b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bfb8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bfb8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18003bfe5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18003bfe5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18003bff4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18003bff4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18003bfdb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18003bfdb`

## pseudocode

```c
void __fastcall SystemSettings::StorageSenseHandlers::CSizeCalculationThreadPool::~CSizeCalculationThreadPool(
        SystemSettings::StorageSenseHandlers::CSizeCalculationThreadPool *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  bool v3; // zf
  struct _TP_CLEANUP_GROUP *v4; // rcx
  struct _TP_POOL *v5; // rcx
  struct _RTL_CRITICAL_SECTION *v6; // [rsp+30h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v3 = *(_BYTE *)this == 0;
  v6 = v1;
  if ( !v3 )
  {
    v4 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 1);
    *(_BYTE *)this = 0;
    if ( v4 )
    {
      CloseThreadpoolCleanupGroupMembers(v4, 1, 0);
      CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 1));
    }
    v5 = (struct _TP_POOL *)*((_QWORD *)this + 11);
    if ( v5 )
      CloseThreadpool(v5);
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v6);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v6);
  DeleteCriticalSection(v1);
}

```

## disassembly

```asm
0x18003bfa4  mov     [rsp+arg_8], rbx
0x18003bfa9  push    rdi
0x18003bfaa  sub     rsp, 20h
0x18003bfae  lea     rdi, [rcx+60h]
0x18003bfb2  mov     rbx, rcx
0x18003bfb5  mov     rcx, rdi; lpCriticalSection
0x18003bfb8  call    cs:__imp_EnterCriticalSection
0x18003bfbe  cmp     byte ptr [rbx], 0
0x18003bfc1  mov     [rsp+28h+arg_0], rdi
0x18003bfc6  jz      short loc_18003BFFA
0x18003bfc8  mov     rcx, [rbx+8]; ptpcg
0x18003bfcc  mov     byte ptr [rbx], 0
0x18003bfcf  test    rcx, rcx
0x18003bfd2  jz      short loc_18003BFEB
0x18003bfd4  xor     r8d, r8d; pvCleanupContext
0x18003bfd7  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18003bfdb  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18003bfe1  mov     rcx, [rbx+8]; ptpcg
0x18003bfe5  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18003bfeb  mov     rcx, [rbx+58h]; ptpp
0x18003bfef  test    rcx, rcx
0x18003bff2  jz      short loc_18003BFFA
0x18003bff4  call    cs:__imp_CloseThreadpool
0x18003bffa  lea     rcx, [rsp+28h+arg_0]; this
0x18003bfff  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003c004  lea     rcx, [rsp+28h+arg_0]; this
0x18003c009  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003c00e  mov     rcx, rdi
0x18003c011  mov     rbx, [rsp+28h+arg_8]
0x18003c016  add     rsp, 20h
0x18003c01a  pop     rdi
0x18003c01b  jmp     cs:__imp_DeleteCriticalSection
```
