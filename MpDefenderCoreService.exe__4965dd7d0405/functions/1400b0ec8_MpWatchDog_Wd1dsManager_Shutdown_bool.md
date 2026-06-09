# MpWatchDog::Wd1dsManager::Shutdown(bool)

- ea: `0x1400b0ec8`
- end: `0x1400b0f86`
- name: `?Shutdown@Wd1dsManager@MpWatchDog@@QEAAX_N@Z`
- size: `190`
- prototype: `void __fastcall(MpWatchDog::Wd1dsManager *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400a5c40`

## callees

- `0x14007d210`
- `0x140082efc`
- `0x1400adae0`
- `0x1400ade88`
- `0x1400af85c`
- `0x1400b0ec8`
- `0x1400b12a4`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x1400b0ef6`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1400b0ef6`

## pseudocode

```c
void __fastcall MpWatchDog::Wd1dsManager::Shutdown(MpWatchDog::Wd1dsManager *this, char a2)
{
  void *v3; // rdx
  MpWatchDog *v4; // rcx

  v3 = (void *)*((_QWORD *)this + 39);
  *((_QWORD *)this + 39) = 0;
  if ( v3 )
    DeleteTimerQueueTimer(0, v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  MpWatchDog::Wd1dsManager::StopResumeTimerInternal(this);
  if ( a2 )
  {
    MpWatchDog::Wd1dsManager::FlushDeviceMetrics(this);
    MpWatchDog::Wd1dsManager::LogManagerTeardown();
  }
  else if ( MpWatchDog::Is1dsDisabled(v4) && MpWatchDog::Wd1dsManager::g_pOneDsLogger )
  {
    Microsoft::Applications::Events::LogManagerBase<Microsoft::Applications::Events::ModuleLogConfiguration>::DeleteData();
  }
  MpWatchDog::Wd1dsManager::StopResumeTimerInternal(this);
}

```

## disassembly

```asm
0x1400b0ec8  mov     [rsp+arg_8], dl
0x1400b0ecc  push    rbx
0x1400b0ecd  sub     rsp, 40h
0x1400b0ed1  mov     rbx, rcx
0x1400b0ed4  mov     [rsp+48h+var_20], rcx
0x1400b0ed9  mov     rdx, [rcx+138h]; Timer
0x1400b0ee0  mov     qword ptr [rcx+138h], 0
0x1400b0eeb  test    rdx, rdx
0x1400b0eee  jz      short loc_1400B0EFD
0x1400b0ef0  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1400b0ef4  xor     ecx, ecx; TimerQueue
0x1400b0ef6  call    cs:__imp_DeleteTimerQueueTimer
0x1400b0efc  nop
0x1400b0efd  jmp     short loc_1400B0F43
0x1400b0eff  mov     r9d, [rsp+48h+var_28]
0x1400b0f04  jmp     short loc_1400B0F10
0x1400b0f06  mov     r9d, [rsp+48h+var_28]
0x1400b0f0b  test    r9d, r9d
0x1400b0f0e  jns     short loc_1400B0F3E
0x1400b0f10  lea     rax, WPP_GLOBAL_Control
0x1400b0f17  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0f1e  cmp     rcx, rax
0x1400b0f21  jz      short loc_1400B0F3E
0x1400b0f23  test    byte ptr [rcx+1Ch], 1
0x1400b0f27  jz      short loc_1400B0F3E
0x1400b0f29  mov     edx, 58h ; 'X'
0x1400b0f2e  lea     r8, WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids
0x1400b0f35  mov     rcx, [rcx+10h]
0x1400b0f39  call    WPP_SF_d
0x1400b0f3e  mov     rbx, [rsp+48h+var_20]
0x1400b0f43  mov     rcx, rbx; this
0x1400b0f46  call    ?StopResumeTimerInternal@Wd1dsManager@MpWatchDog@@AEAAJXZ; MpWatchDog::Wd1dsManager::StopResumeTimerInternal(void)
0x1400b0f4b  cmp     [rsp+48h+arg_8], 0
0x1400b0f50  jz      short loc_1400B0F61
0x1400b0f52  mov     rcx, rbx; this
0x1400b0f55  call    ?FlushDeviceMetrics@Wd1dsManager@MpWatchDog@@AEAAXXZ; MpWatchDog::Wd1dsManager::FlushDeviceMetrics(void)
0x1400b0f5a  call    ?LogManagerTeardown@Wd1dsManager@MpWatchDog@@CAXXZ; MpWatchDog::Wd1dsManager::LogManagerTeardown(void)
0x1400b0f5f  jmp     short loc_1400B0F79
0x1400b0f61  call    ?Is1dsDisabled@MpWatchDog@@YA_NXZ; MpWatchDog::Is1dsDisabled(void)
0x1400b0f66  test    al, al
0x1400b0f68  jz      short loc_1400B0F79
0x1400b0f6a  cmp     cs:?g_pOneDsLogger@Wd1dsManager@MpWatchDog@@0PEAVILogger@Events@Applications@Microsoft@@EA, 0; Microsoft::Applications::Events::ILogger * MpWatchDog::Wd1dsManager::g_pOneDsLogger
0x1400b0f72  jz      short loc_1400B0F79
0x1400b0f74  call    ?DeleteData@?$LogManagerBase@VModuleLogConfiguration@Events@Applications@Microsoft@@@Events@Applications@Microsoft@@SA?AW4status_t@234@XZ; Microsoft::Applications::Events::LogManagerBase<Microsoft::Applications::Events::ModuleLogConfiguration>::DeleteData(void)
0x1400b0f79  mov     rcx, rbx; this
0x1400b0f7c  add     rsp, 40h
0x1400b0f80  pop     rbx
0x1400b0f81  jmp     ?StopResumeTimerInternal@Wd1dsManager@MpWatchDog@@AEAAJXZ; MpWatchDog::Wd1dsManager::StopResumeTimerInternal(void)
```
