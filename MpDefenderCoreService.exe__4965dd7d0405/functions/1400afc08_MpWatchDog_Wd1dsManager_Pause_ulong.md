# MpWatchDog::Wd1dsManager::Pause(ulong)

- ea: `0x1400afc08`
- end: `0x1400afe61`
- name: `?Pause@Wd1dsManager@MpWatchDog@@IEAAJK@Z`
- size: `601`
- prototype: `__int64 __fastcall(MpWatchDog::Wd1dsManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400add08`

## callees

- `0x140013394`
- `0x14007d1e0`
- `0x14007d210`
- `0x1400adae0`
- `0x1400afc08`
- `0x1400afe64`
- `0x1400b12a4`
- `0x1400b77f8`
- `0x140166250`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x1400afd18`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1400afd18`

## pseudocode

```c
__int64 __fastcall MpWatchDog::Wd1dsManager::Pause(MpWatchDog::Wd1dsManager *this, int a2)
{
  __int64 v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // esi
  __int64 v8; // rcx
  __int64 v9; // rdx
  void *v10; // rdx
  int TimerQueueTimer; // eax
  int v12; // eax
  __int64 v13; // [rsp+0h] [rbp-58h] BYREF
  void *v14; // [rsp+28h] [rbp-30h]
  int v15; // [rsp+30h] [rbp-28h]
  int v16; // [rsp+38h] [rbp-20h]
  MpWatchDog::Wd1dsManager *v17; // [rsp+40h] [rbp-18h]
  const std::exception *v18; // [rsp+48h] [rbp-10h] BYREF

  v17 = this;
  v16 = a2;
  if ( byte_1401E7431 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(MpWatchDog::Wd1dsManager *))(*(_QWORD *)this + 160LL))(this) )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        return 0;
      v6 = 58;
      goto LABEL_28;
    }
    try
    {
      Microsoft::Applications::Events::LogManagerBase<Microsoft::Applications::Events::ModuleLogConfiguration>::PauseTransmission();
      Microsoft::Applications::Events::LogManagerBase<Microsoft::Applications::Events::ModuleLogConfiguration>::DeleteData();
    }
    catch ( const std::exception *v18 )
    {
      CommonUtil::HrFromStdException(v18, (const struct std::exception *)&v13);
    }
    catch ( ... )
    {
      v15 = -2147467259;
      v7 = v15;
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        return v7;
      v9 = 59;
LABEL_33:
      WPP_SF_d(*(_QWORD *)(v8 + 16), v9, &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids, v7);
      return v7;
    }
    v7 = MpWatchDog::Wd1dsManager::StopResumeTimerInternal(this);
    if ( (v7 & 0x80000000) != 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        return v7;
      v9 = 60;
      goto LABEL_33;
    }
    v10 = (void *)*((_QWORD *)this + 40);
    if ( v10 )
    {
      DeleteTimerQueueTimer(0, v10, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      *((_QWORD *)this + 40) = 0;
    }
    LODWORD(v14) = 0;
    TimerQueueTimer = CommonUtil::UtilCreateTimerQueueTimer(
                        (MpWatchDog::Wd1dsManager *)((char *)this + 320),
                        (void **)(unsigned int)(1000 * a2),
                        0x7D0u,
                        (void (__stdcall *)(PVOID, BOOLEAN))MpWatchDog::Wd1dsManager::ResumeTelemetryServiceTimerCallback,
                        0,
                        v14);
    if ( TimerQueueTimer < 0
      && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        61,
        &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids,
        (unsigned int)TimerQueueTimer);
    }
    MpWatchDog::Wd1dsManager::m_bPaused = 1;
    v12 = MpWatchDog::MpCoreSvcDiagnostics::ModifyCoreServiceStatusBitfield(0x20u, MpWatchDog::SetBitsFunc, L"Set");
    if ( v12 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return 0;
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_25;
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        62,
        &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids,
        (unsigned int)v12);
    }
    v5 = WPP_GLOBAL_Control;
LABEL_25:
    if ( (_UNKNOWN *)v5 == &WPP_GLOBAL_Control || (*(_BYTE *)(v5 + 28) & 2) == 0 )
      return 0;
    v6 = 63;
LABEL_28:
    WPP_SF_(*(_QWORD *)(v5 + 16), v6, &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids);
    return 0;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 57, &WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids);
  return 2147942421LL;
}

```

## disassembly

```asm
0x1400afc08  mov     [rsp+arg_10], rbx
0x1400afc0d  mov     [rsp+arg_18], rsi
0x1400afc12  push    rdi
0x1400afc13  sub     rsp, 50h
0x1400afc17  mov     edi, edx
0x1400afc19  mov     rbx, rcx
0x1400afc1c  mov     [rsp+58h+var_18], rcx
0x1400afc21  mov     [rsp+58h+var_20], edx
0x1400afc25  cmp     cs:byte_1401E7431, 0
0x1400afc2c  jnz     short loc_1400AFC69
0x1400afc2e  lea     rbx, WPP_GLOBAL_Control
0x1400afc35  mov     rcx, cs:WPP_GLOBAL_Control
0x1400afc3c  cmp     rcx, rbx
0x1400afc3f  jz      short loc_1400AFC5F
0x1400afc41  mov     edi, 1
0x1400afc46  test    [rcx+1Ch], dil
0x1400afc4a  jz      short loc_1400AFC5F
0x1400afc4c  lea     edx, [rdi+38h]
0x1400afc4f  lea     r8, WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids
0x1400afc56  mov     rcx, [rcx+10h]
0x1400afc5a  call    WPP_SF_
0x1400afc5f  mov     eax, 80070015h
0x1400afc64  jmp     loc_1400AFE51
0x1400afc69  mov     rax, [rcx]
0x1400afc6c  mov     rax, [rax+0A0h]
0x1400afc73  call    cs:__guard_dispatch_icall_fptr
0x1400afc79  test    al, al
0x1400afc7b  jz      short loc_1400AFCA8
0x1400afc7d  lea     rbx, WPP_GLOBAL_Control
0x1400afc84  mov     rcx, cs:WPP_GLOBAL_Control
0x1400afc8b  cmp     rcx, rbx
0x1400afc8e  jz      loc_1400AFE13
0x1400afc94  test    byte ptr [rcx+1Ch], 2
0x1400afc98  jz      loc_1400AFE13
0x1400afc9e  mov     edx, 3Ah ; ':'
0x1400afca3  jmp     loc_1400AFE03
0x1400afca8  call    ?PauseTransmission@?$LogManagerBase@VModuleLogConfiguration@Events@Applications@Microsoft@@@Events@Applications@Microsoft@@SA?AW4status_t@234@XZ; Microsoft::Applications::Events::LogManagerBase<Microsoft::Applications::Events::ModuleLogConfiguration>::PauseTransmission(void)
0x1400afcad  call    ?DeleteData@?$LogManagerBase@VModuleLogConfiguration@Events@Applications@Microsoft@@@Events@Applications@Microsoft@@SA?AW4status_t@234@XZ; Microsoft::Applications::Events::LogManagerBase<Microsoft::Applications::Events::ModuleLogConfiguration>::DeleteData(void)
0x1400afcb2  nop
0x1400afcb3  jmp     short loc_1400AFCCA
0x1400afcb5  mov     esi, [rsp+58h+var_28]
0x1400afcb9  test    esi, esi
0x1400afcbb  js      loc_1400AFE1B
0x1400afcc1  mov     rbx, [rsp+58h+var_18]
0x1400afcc6  mov     edi, [rsp+58h+var_20]
0x1400afcca  mov     rcx, rbx; this
0x1400afccd  call    ?StopResumeTimerInternal@Wd1dsManager@MpWatchDog@@AEAAJXZ; MpWatchDog::Wd1dsManager::StopResumeTimerInternal(void)
0x1400afcd2  mov     esi, eax
0x1400afcd4  test    eax, eax
0x1400afcd6  jns     short loc_1400AFD06
0x1400afcd8  lea     rbx, WPP_GLOBAL_Control
0x1400afcdf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400afce6  cmp     rcx, rbx
0x1400afce9  jz      loc_1400AFE4F
0x1400afcef  mov     edi, 1
0x1400afcf4  test    [rcx+1Ch], dil
0x1400afcf8  jz      loc_1400AFE4F
0x1400afcfe  lea     edx, [rdi+3Bh]
0x1400afd01  jmp     loc_1400AFE3C
0x1400afd06  mov     rdx, [rbx+140h]; Timer
0x1400afd0d  test    rdx, rdx
0x1400afd10  jz      short loc_1400AFD29
0x1400afd12  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1400afd16  xor     ecx, ecx; TimerQueue
0x1400afd18  call    cs:__imp_DeleteTimerQueueTimer
0x1400afd1e  mov     qword ptr [rbx+140h], 0
0x1400afd29  imul    edx, edi, 3E8h; void **
0x1400afd2f  mov     dword ptr [rsp+58h+var_30], 0; void *
0x1400afd37  mov     [rsp+58h+var_38], 0; void (*)(void *, unsigned __int8)
0x1400afd40  lea     r9, ?ResumeTelemetryServiceTimerCallback@Wd1dsManager@MpWatchDog@@CAXPEAXE@Z; unsigned int
0x1400afd47  mov     r8d, 7D0h; unsigned int
0x1400afd4d  lea     rcx, [rbx+140h]; this
0x1400afd54  call    ?UtilCreateTimerQueueTimer@CommonUtil@@YAJPEAPEAXKKP6AXPEAXE@Z1K@Z; CommonUtil::UtilCreateTimerQueueTimer(void * *,ulong,ulong,void (*)(void *,uchar),void *,ulong)
0x1400afd59  test    eax, eax
0x1400afd5b  jns     short loc_1400AFD93
0x1400afd5d  lea     rbx, WPP_GLOBAL_Control
0x1400afd64  mov     rcx, cs:WPP_GLOBAL_Control
0x1400afd6b  mov     edi, 1
0x1400afd70  cmp     rcx, rbx
0x1400afd73  jz      short loc_1400AFD9F
0x1400afd75  test    [rcx+1Ch], dil
0x1400afd79  jz      short loc_1400AFD9F
0x1400afd7b  lea     edx, [rdi+3Ch]
0x1400afd7e  mov     r9d, eax
0x1400afd81  lea     r8, WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids
0x1400afd88  mov     rcx, [rcx+10h]
0x1400afd8c  call    WPP_SF_d
0x1400afd91  jmp     short loc_1400AFD9F
0x1400afd93  lea     rbx, WPP_GLOBAL_Control
0x1400afd9a  mov     edi, 1
0x1400afd9f  xchg    dil, cs:?m_bPaused@Wd1dsManager@MpWatchDog@@0U?$atomic@_N@std@@A; std::atomic<bool> MpWatchDog::Wd1dsManager::m_bPaused
0x1400afda6  lea     r8, aSet; "Set"
0x1400afdad  lea     rdx, MpWatchDog__SetBitsFunc; unsigned int (*)(unsigned int, unsigned int)
0x1400afdb4  mov     ecx, 20h ; ' '; unsigned int
0x1400afdb9  call    ?ModifyCoreServiceStatusBitfield@MpCoreSvcDiagnostics@MpWatchDog@@CAJKP6AKKK@ZPEB_W@Z; MpWatchDog::MpCoreSvcDiagnostics::ModifyCoreServiceStatusBitfield(ulong,ulong (*)(ulong,ulong),wchar_t const *)
0x1400afdbe  test    eax, eax
0x1400afdc0  jns     short loc_1400AFDEC
0x1400afdc2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400afdc9  cmp     rcx, rbx
0x1400afdcc  jz      short loc_1400AFE13
0x1400afdce  test    byte ptr [rcx+1Ch], 2
0x1400afdd2  jz      short loc_1400AFDF3
0x1400afdd4  mov     edx, 3Eh ; '>'
0x1400afdd9  mov     r9d, eax
0x1400afddc  lea     r8, WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids
0x1400afde3  mov     rcx, [rcx+10h]
0x1400afde7  call    WPP_SF_d
0x1400afdec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400afdf3  cmp     rcx, rbx
0x1400afdf6  jz      short loc_1400AFE13
0x1400afdf8  test    byte ptr [rcx+1Ch], 2
0x1400afdfc  jz      short loc_1400AFE13
0x1400afdfe  mov     edx, 3Fh ; '?'
0x1400afe03  lea     r8, WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids
0x1400afe0a  mov     rcx, [rcx+10h]
0x1400afe0e  call    WPP_SF_
0x1400afe13  xor     eax, eax
0x1400afe15  jmp     short loc_1400AFE51
0x1400afe17  mov     esi, [rsp+58h+var_28]
0x1400afe1b  lea     rbx, WPP_GLOBAL_Control
0x1400afe22  mov     rcx, cs:WPP_GLOBAL_Control
0x1400afe29  cmp     rcx, rbx
0x1400afe2c  jz      short loc_1400AFE4F
0x1400afe2e  mov     edi, 1
0x1400afe33  test    [rcx+1Ch], dil
0x1400afe37  jz      short loc_1400AFE4F
0x1400afe39  lea     edx, [rdi+3Ah]
0x1400afe3c  mov     r9d, esi
0x1400afe3f  lea     r8, WPP_9a4cfdb0823e399e86aef668d2b00e61_Traceguids
0x1400afe46  mov     rcx, [rcx+10h]
0x1400afe4a  call    WPP_SF_d
0x1400afe4f  mov     eax, esi
0x1400afe51  mov     rbx, [rsp+58h+arg_10]
0x1400afe56  mov     rsi, [rsp+58h+arg_18]
0x1400afe5b  add     rsp, 50h
0x1400afe5f  pop     rdi
0x1400afe60  retn
```
