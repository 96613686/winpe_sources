# ShieldProvider::CPeriodicTaskManager::~CPeriodicTaskManager(void)

- ea: `0x18001195c`
- end: `0x1800119f2`
- name: `??1CPeriodicTaskManager@ShieldProvider@@UEAA@XZ`
- size: `150`
- prototype: `void __fastcall(ShieldProvider::CPeriodicTaskManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011a10`

## callees

- `0x18000ccb0`
- `0x18001195c`
- `0x180011b84`
- `0x1800134f8`
- `0x1800de2d8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800119d3`
- `KERNEL32!CloseHandle` at `0x1800119d3`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800119a1`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800119b6`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800119a1`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800119b6`

## pseudocode

```c
void __fastcall ShieldProvider::CPeriodicTaskManager::~CPeriodicTaskManager(ShieldProvider::CPeriodicTaskManager *this)
{
  bool v1; // zf
  void *v3; // rdx
  void *v4; // rdx
  struct tagMP_THREAD_POOL *v5; // rcx
  void *v6; // rcx

  v1 = *((_BYTE *)this + 56) == 0;
  *(_QWORD *)this = &ShieldProvider::CPeriodicTaskManager::`vftable';
  if ( v1 )
    ShieldProvider::CPeriodicTaskManager::Close(this);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>((char *)this + 144);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>((char *)this + 136);
  v3 = (void *)*((_QWORD *)this + 13);
  if ( v3 )
    DeleteTimerQueueTimer(0, v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v4 = (void *)*((_QWORD *)this + 11);
  if ( v4 )
    DeleteTimerQueueTimer(0, v4, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v5 = (struct tagMP_THREAD_POOL *)*((_QWORD *)this + 10);
  if ( v5 )
    CommonUtil::CAutoMpThreadPoolClose::Release(v5);
  v6 = (void *)*((_QWORD *)this + 8);
  if ( v6 )
    CloseHandle(v6);
  CommonUtil::CMpCriticalSection::~CMpCriticalSection((ShieldProvider::CPeriodicTaskManager *)((char *)this + 16));
  *(_QWORD *)this = &CommonUtil::CRefObject::`vftable';
}

```

## disassembly

```asm
0x18001195c  push    rbx
0x18001195e  sub     rsp, 20h
0x180011962  cmp     byte ptr [rcx+38h], 0
0x180011966  lea     rax, ??_7CPeriodicTaskManager@ShieldProvider@@6B@; const ShieldProvider::CPeriodicTaskManager::`vftable'
0x18001196d  mov     [rcx], rax
0x180011970  mov     rbx, rcx
0x180011973  jnz     short loc_18001197A
0x180011975  call    ?Close@CPeriodicTaskManager@ShieldProvider@@QEAAXXZ; ShieldProvider::CPeriodicTaskManager::Close(void)
0x18001197a  lea     rcx, [rbx+90h]
0x180011981  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180011986  lea     rcx, [rbx+88h]
0x18001198d  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180011992  mov     rdx, [rbx+68h]; Timer
0x180011996  test    rdx, rdx
0x180011999  jz      short loc_1800119A7
0x18001199b  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18001199f  xor     ecx, ecx; TimerQueue
0x1800119a1  call    cs:__imp_DeleteTimerQueueTimer
0x1800119a7  mov     rdx, [rbx+58h]; Timer
0x1800119ab  test    rdx, rdx
0x1800119ae  jz      short loc_1800119BC
0x1800119b0  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800119b4  xor     ecx, ecx; TimerQueue
0x1800119b6  call    cs:__imp_DeleteTimerQueueTimer
0x1800119bc  mov     rcx, [rbx+50h]; struct tagMP_THREAD_POOL *
0x1800119c0  test    rcx, rcx
0x1800119c3  jz      short loc_1800119CA
0x1800119c5  call    ?Release@CAutoMpThreadPoolClose@CommonUtil@@SAXPEAUtagMP_THREAD_POOL@@@Z; CommonUtil::CAutoMpThreadPoolClose::Release(tagMP_THREAD_POOL *)
0x1800119ca  mov     rcx, [rbx+40h]; hObject
0x1800119ce  test    rcx, rcx
0x1800119d1  jz      short loc_1800119D9
0x1800119d3  call    cs:__imp_CloseHandle
0x1800119d9  lea     rcx, [rbx+10h]; this
0x1800119dd  call    ??1CMpCriticalSection@CommonUtil@@QEAA@XZ; CommonUtil::CMpCriticalSection::~CMpCriticalSection(void)
0x1800119e2  lea     rax, ??_7CRefObject@CommonUtil@@6B@; const CommonUtil::CRefObject::`vftable'
0x1800119e9  mov     [rbx], rax
0x1800119ec  add     rsp, 20h
0x1800119f0  pop     rbx
0x1800119f1  retn
```
