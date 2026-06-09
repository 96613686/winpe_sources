# ShieldProvider::CPeriodicTaskManager::Initialize(void)

- ea: `0x180012430`
- end: `0x1800125eb`
- name: `?Initialize@CPeriodicTaskManager@ShieldProvider@@QEAAJXZ`
- size: `443`
- prototype: `__int64 __fastcall(ShieldProvider::CPeriodicTaskManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011694`

## callees

- `0x18000d7fc`
- `0x18000e98c`
- `0x180011af4`
- `0x180012430`
- `0x1800134f8`
- `0x1800da58c`
- `0x1800da908`
- `0x1800de318`
- `0x1800dfb94`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001248f`
- `KERNEL32!CloseHandle` at `0x18001248f`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180012577`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180012577`

## string_xrefs

- `0x18001252f`: `PeriodicTaskPeriodicity`
- `0x180012546`: `PeriodicTaskInitialDelay`

## pseudocode

```c
__int64 __fastcall ShieldProvider::CPeriodicTaskManager::Initialize(ShieldProvider::CPeriodicTaskManager *this)
{
  int Event; // edi
  int v3; // r9d
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  void *v7; // rcx
  struct tagMP_THREAD_POOL *v8; // rcx
  unsigned int v9; // r8d
  unsigned int v10; // esi
  unsigned int v11; // r8d
  unsigned int v12; // ebp
  unsigned int v13; // edx
  void *v14; // rdx
  int TimerQueueTimer; // eax
  unsigned int v16; // ebx
  void (*v17)(void *, unsigned __int8); // [rsp+20h] [rbp-38h]
  const struct _SECURITY_ATTRIBUTES *v18; // [rsp+28h] [rbp-30h]
  void *v19; // [rsp+28h] [rbp-30h]
  unsigned int v20; // [rsp+30h] [rbp-28h]

  Event = CommonUtil::CMpCriticalSection::Initialize((ShieldProvider::CPeriodicTaskManager *)((char *)this + 16));
  if ( Event < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)Event;
    v5 = 12;
LABEL_5:
    WPP_SF_d(v4[2], v5, WPP_c15b3361942b3cf72eefef62f859076e_Traceguids, (unsigned int)Event);
    return (unsigned int)Event;
  }
  v7 = (void *)*((_QWORD *)this + 8);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 8) = 0;
  }
  Event = CommonUtil::UtilCreateEvent(
            (ShieldProvider::CPeriodicTaskManager *)((char *)this + 64),
            (void **)1,
            0,
            v3,
            (const unsigned __int16 *)v17,
            v18);
  if ( Event < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)Event;
    v5 = 13;
    goto LABEL_5;
  }
  *((_QWORD *)this + 14) = 0;
  v8 = (struct tagMP_THREAD_POOL *)*((_QWORD *)this + 10);
  if ( v8 )
  {
    CommonUtil::CAutoMpThreadPoolClose::Release(v8);
    *((_QWORD *)this + 10) = 0;
  }
  Event = MpThreadPoolCreate((char *)this + 80);
  if ( Event < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)Event;
    v5 = 14;
    goto LABEL_5;
  }
  v10 = 1000
      * ShieldProvider::GetMiscDwordIfApplicable(
          (ShieldProvider *)L"PeriodicTaskPeriodicity",
          (const unsigned __int16 *)0x15180,
          v9);
  v12 = 1000
      * ShieldProvider::GetMiscDwordIfApplicable(
          (ShieldProvider *)L"PeriodicTaskInitialDelay",
          (const unsigned __int16 *)0x258,
          v11);
  *((_DWORD *)this + 24) = ShieldProvider::CalculateTimerTrigger((ShieldProvider *)v12, v13);
  *((_DWORD *)this + 25) = v10;
  v14 = (void *)*((_QWORD *)this + 11);
  if ( v14 )
  {
    DeleteTimerQueueTimer(0, v14, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *((_QWORD *)this + 11) = 0;
  }
  LODWORD(v19) = 0;
  TimerQueueTimer = CommonUtil::UtilCreateTimerQueueTimer(
                      (ShieldProvider::CPeriodicTaskManager *)((char *)this + 88),
                      (void **)v12,
                      v10,
                      (unsigned int)ShieldProvider::CPeriodicTaskManager::PeriodicTimerCallback,
                      (void (*)(void *, unsigned __int8))this,
                      v19,
                      v20);
  v16 = TimerQueueTimer;
  if ( TimerQueueTimer >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_c15b3361942b3cf72eefef62f859076e_Traceguids,
      (unsigned int)TimerQueueTimer);
  return v16;
}

```

## disassembly

```asm
0x180012430  push    rbx
0x180012432  push    rbp
0x180012433  push    rsi
0x180012434  push    rdi
0x180012435  sub     rsp, 38h
0x180012439  mov     rbx, rcx
0x18001243c  add     rcx, 10h; this
0x180012440  call    ?Initialize@CMpCriticalSection@CommonUtil@@QEAAJXZ; CommonUtil::CMpCriticalSection::Initialize(void)
0x180012445  mov     edi, eax
0x180012447  test    eax, eax
0x180012449  jns     short loc_180012483
0x18001244b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012452  lea     rdx, WPP_GLOBAL_Control
0x180012459  cmp     rcx, rdx
0x18001245c  jz      short loc_18001247C
0x18001245e  test    byte ptr [rcx+1Ch], 1
0x180012462  jz      short loc_18001247C
0x180012464  mov     edx, 0Ch
0x180012469  mov     rcx, [rcx+10h]
0x18001246d  lea     r8, WPP_c15b3361942b3cf72eefef62f859076e_Traceguids
0x180012474  mov     r9d, edi
0x180012477  call    WPP_SF_d
0x18001247c  mov     eax, edi
0x18001247e  jmp     loc_1800125E2
0x180012483  lea     rdi, [rbx+40h]
0x180012487  mov     rcx, [rdi]; hObject
0x18001248a  test    rcx, rcx
0x18001248d  jz      short loc_18001249C
0x18001248f  call    cs:__imp_CloseHandle
0x180012495  mov     qword ptr [rdi], 0
0x18001249c  xor     r8d, r8d; int
0x18001249f  mov     rcx, rdi; this
0x1800124a2  lea     edx, [r8+1]; void **
0x1800124a6  call    ?UtilCreateEvent@CommonUtil@@YAJPEAPEAXHHPEBGPEBU_SECURITY_ATTRIBUTES@@@Z; CommonUtil::UtilCreateEvent(void * *,int,int,ushort const *,_SECURITY_ATTRIBUTES const *)
0x1800124ab  mov     edi, eax
0x1800124ad  test    eax, eax
0x1800124af  jns     short loc_1800124D1
0x1800124b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124b8  lea     rdx, WPP_GLOBAL_Control
0x1800124bf  cmp     rcx, rdx
0x1800124c2  jz      short loc_18001247C
0x1800124c4  test    byte ptr [rcx+1Ch], 1
0x1800124c8  jz      short loc_18001247C
0x1800124ca  mov     edx, 0Dh
0x1800124cf  jmp     short loc_180012469
0x1800124d1  lea     rdi, [rbx+50h]
0x1800124d5  mov     qword ptr [rbx+70h], 0
0x1800124dd  mov     rcx, [rdi]; struct tagMP_THREAD_POOL *
0x1800124e0  test    rcx, rcx
0x1800124e3  jz      short loc_1800124F1
0x1800124e5  call    ?Release@CAutoMpThreadPoolClose@CommonUtil@@SAXPEAUtagMP_THREAD_POOL@@@Z; CommonUtil::CAutoMpThreadPoolClose::Release(tagMP_THREAD_POOL *)
0x1800124ea  mov     qword ptr [rdi], 0
0x1800124f1  mov     rcx, rdi
0x1800124f4  call    MpThreadPoolCreate
0x1800124f9  mov     edi, eax
0x1800124fb  test    eax, eax
0x1800124fd  jns     short loc_18001252A
0x1800124ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180012506  lea     rdx, WPP_GLOBAL_Control
0x18001250d  cmp     rcx, rdx
0x180012510  jz      loc_18001247C
0x180012516  test    byte ptr [rcx+1Ch], 1
0x18001251a  jz      loc_18001247C
0x180012520  mov     edx, 0Eh
0x180012525  jmp     loc_180012469
0x18001252a  mov     edx, 15180h; unsigned __int16 *
0x18001252f  lea     rcx, aPeriodictaskpe; "PeriodicTaskPeriodicity"
0x180012536  call    ?GetMiscDwordIfApplicable@ShieldProvider@@YAKPEBGK@Z; ShieldProvider::GetMiscDwordIfApplicable(ushort const *,ulong)
0x18001253b  mov     edx, 258h; unsigned __int16 *
0x180012540  imul    esi, eax, 3E8h
0x180012546  lea     rcx, aPeriodictaskin; "PeriodicTaskInitialDelay"
0x18001254d  call    ?GetMiscDwordIfApplicable@ShieldProvider@@YAKPEBGK@Z; ShieldProvider::GetMiscDwordIfApplicable(ushort const *,ulong)
0x180012552  imul    ebp, eax, 3E8h
0x180012558  mov     ecx, ebp; this
0x18001255a  call    ?CalculateTimerTrigger@ShieldProvider@@YAKK@Z; ShieldProvider::CalculateTimerTrigger(ulong)
0x18001255f  lea     rdi, [rbx+58h]
0x180012563  mov     [rbx+60h], eax
0x180012566  mov     [rbx+64h], esi
0x180012569  mov     rdx, [rdi]; Timer
0x18001256c  test    rdx, rdx
0x18001256f  jz      short loc_180012584
0x180012571  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180012575  xor     ecx, ecx; TimerQueue
0x180012577  call    cs:__imp_DeleteTimerQueueTimer
0x18001257d  mov     qword ptr [rdi], 0
0x180012584  mov     dword ptr [rsp+58h+var_30], 0; void *
0x18001258c  lea     r9, ?PeriodicTimerCallback@CPeriodicTaskManager@ShieldProvider@@CAXPEAXE@Z; unsigned int
0x180012593  mov     r8d, esi; unsigned int
0x180012596  mov     [rsp+58h+var_38], rbx; void (*)(void *, unsigned __int8)
0x18001259b  mov     edx, ebp; void **
0x18001259d  mov     rcx, rdi; this
0x1800125a0  call    ?UtilCreateTimerQueueTimer@CommonUtil@@YAJPEAPEAXKKP6AXPEAXE@Z1K@Z; CommonUtil::UtilCreateTimerQueueTimer(void * *,ulong,ulong,void (*)(void *,uchar),void *,ulong)
0x1800125a5  mov     ebx, eax
0x1800125a7  test    eax, eax
0x1800125a9  jns     short loc_1800125E0
0x1800125ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125b2  lea     rdx, WPP_GLOBAL_Control
0x1800125b9  cmp     rcx, rdx
0x1800125bc  jz      short loc_1800125DC
0x1800125be  test    byte ptr [rcx+1Ch], 1
0x1800125c2  jz      short loc_1800125DC
0x1800125c4  mov     rcx, [rcx+10h]
0x1800125c8  lea     r8, WPP_c15b3361942b3cf72eefef62f859076e_Traceguids
0x1800125cf  mov     edx, 0Fh
0x1800125d4  mov     r9d, eax
0x1800125d7  call    WPP_SF_d
0x1800125dc  mov     eax, ebx
0x1800125de  jmp     short loc_1800125E2
0x1800125e0  xor     eax, eax
0x1800125e2  add     rsp, 38h
0x1800125e6  pop     rdi
0x1800125e7  pop     rsi
0x1800125e8  pop     rbp
0x1800125e9  pop     rbx
0x1800125ea  retn
```
