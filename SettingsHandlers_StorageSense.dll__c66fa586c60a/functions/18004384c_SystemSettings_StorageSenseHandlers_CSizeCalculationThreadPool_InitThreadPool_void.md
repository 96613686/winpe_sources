# SystemSettings::StorageSenseHandlers::CSizeCalculationThreadPool::InitThreadPool(void)

- ea: `0x18004384c`
- end: `0x180043974`
- name: `?InitThreadPool@CSizeCalculationThreadPool@StorageSenseHandlers@SystemSettings@@QEAAJXZ`
- size: `296`
- prototype: `int(SystemSettings::StorageSenseHandlers::CSizeCalculationThreadPool *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003df40`

## callees

- `0x18000e6cc`
- `0x18001f53c`
- `0x18004384c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043860`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043860`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180043880`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180043880`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18004392f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18004392f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800438e3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800438e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18004391d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18004391d`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::CSizeCalculationThreadPool::InitThreadPool(
        struct _RTL_CRITICAL_SECTION *this)
{
  unsigned int v1; // ebx
  __int64 v2; // rdx
  struct _TP_POOL *Threadpool; // rax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = this;
  EnterCriticalSection(&CriticalSection);
  v7 = &CriticalSection;
  v1 = 0;
  if ( SystemSettings::StorageSenseHandlers::g_SizeThreadPool )
    goto LABEL_8;
  SystemSettings::StorageSenseHandlers::g_SizeThreadPool = 1;
  qword_18018A6A8 = (__int64)CreateThreadpoolCleanupGroup();
  if ( qword_18018A6A8 )
  {
    pcbe.Version = 3;
    *(_OWORD *)&pcbe.CleanupGroup = 0;
    *(_OWORD *)&pcbe.RaceDll = 0;
    pcbe.Pool = 0;
    pcbe.FinalizationCallback = 0;
    pcbe.u.Flags = 0;
    pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
    pcbe.Size = 72;
    Threadpool = CreateThreadpool(0);
    ptpp = Threadpool;
    if ( !Threadpool )
    {
      v2 = 4176;
      goto LABEL_6;
    }
    SetThreadpoolThreadMinimum(Threadpool, 1u);
    SetThreadpoolThreadMaximum(ptpp, 2u);
    pcbe.Pool = ptpp;
    pcbe.CleanupGroup = (PTP_CLEANUP_GROUP)qword_18018A6A8;
    pcbe.CleanupGroupCancelCallback = 0;
LABEL_8:
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v7);
    goto LABEL_9;
  }
  v2 = 4172;
LABEL_6:
  v1 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v2,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
    (const char *)0x8007000ELL,
    v5);
LABEL_9:
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v7);
  return v1;
}

```

## disassembly

```asm
0x18004384c  mov     [rsp+arg_0], rcx
0x180043851  push    rbx; int
0x180043852  sub     rsp, 20h
0x180043856  lea     rbx, CriticalSection
0x18004385d  mov     rcx, rbx; lpCriticalSection
0x180043860  call    cs:__imp_EnterCriticalSection
0x180043866  mov     [rsp+28h+arg_0], rbx
0x18004386b  xor     ebx, ebx
0x18004386d  cmp     cs:?g_SizeThreadPool@StorageSenseHandlers@SystemSettings@@3VCSizeCalculationThreadPool@12@A, bl; SystemSettings::StorageSenseHandlers::CSizeCalculationThreadPool SystemSettings::StorageSenseHandlers::g_SizeThreadPool
0x180043873  jnz     loc_180043958
0x180043879  mov     cs:?g_SizeThreadPool@StorageSenseHandlers@SystemSettings@@3VCSizeCalculationThreadPool@12@A, 1; SystemSettings::StorageSenseHandlers::CSizeCalculationThreadPool SystemSettings::StorageSenseHandlers::g_SizeThreadPool
0x180043880  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180043886  mov     cs:qword_18018A6A8, rax
0x18004388d  test    rax, rax
0x180043890  jnz     short loc_180043899
0x180043892  mov     edx, 104Ch
0x180043897  jmp     short loc_1800438FA
0x180043899  xorps   xmm0, xmm0
0x18004389c  mov     cs:pcbe.Version, 3
0x1800438a6  xorps   xmm1, xmm1
0x1800438a9  movdqa  xmmword ptr cs:pcbe.CleanupGroup, xmm0
0x1800438b1  xor     ecx, ecx; reserved
0x1800438b3  movdqa  xmmword ptr cs:pcbe.RaceDll, xmm1
0x1800438bb  mov     cs:pcbe.Pool, rbx
0x1800438c2  mov     cs:pcbe.FinalizationCallback, rbx
0x1800438c9  mov     dword ptr cs:pcbe.u, ebx
0x1800438cf  mov     cs:pcbe.CallbackPriority, 1
0x1800438d9  mov     cs:pcbe.Size, 48h ; 'H'
0x1800438e3  call    cs:__imp_CreateThreadpool
0x1800438e9  mov     cs:ptpp, rax
0x1800438f0  test    rax, rax
0x1800438f3  jnz     short loc_180043915
0x1800438f5  mov     edx, 1050h; void *
0x1800438fa  mov     rcx, [rsp+28h]; this
0x1800438ff  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x180043906  mov     ebx, 8007000Eh
0x18004390b  mov     r9d, ebx; char *
0x18004390e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043913  jmp     short loc_180043962
0x180043915  mov     edx, 1; cthrdMic
0x18004391a  mov     rcx, rax; ptpp
0x18004391d  call    cs:__imp_SetThreadpoolThreadMinimum
0x180043923  mov     rcx, cs:ptpp; ptpp
0x18004392a  mov     edx, 2; cthrdMost
0x18004392f  call    cs:__imp_SetThreadpoolThreadMaximum
0x180043935  mov     rax, cs:ptpp
0x18004393c  mov     cs:pcbe.Pool, rax
0x180043943  mov     rax, cs:qword_18018A6A8
0x18004394a  mov     cs:pcbe.CleanupGroup, rax
0x180043951  mov     cs:pcbe.CleanupGroupCancelCallback, rbx
0x180043958  lea     rcx, [rsp+28h+arg_0]; this
0x18004395d  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180043962  lea     rcx, [rsp+28h+arg_0]; this
0x180043967  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18004396c  mov     eax, ebx
0x18004396e  add     rsp, 20h
0x180043972  pop     rbx
0x180043973  retn
```
