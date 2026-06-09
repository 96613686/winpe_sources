# ShieldProvider::CPeriodicTaskManager::OnPeriodicTimerCallback(void)

- ea: `0x1800127d8`
- end: `0x1800128f7`
- name: `?OnPeriodicTimerCallback@CPeriodicTaskManager@ShieldProvider@@AEAAXXZ`
- size: `287`
- prototype: `void __fastcall(ShieldProvider::CPeriodicTaskManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013100`

## callees

- `0x18000f02c`
- `0x18000f094`
- `0x180010ff0`
- `0x180011af4`
- `0x1800127d8`
- `0x180015088`
- `0x1800151c4`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x180012874`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180012894`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180012874`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180012894`
- `KERNEL32!GetTickCount` at `0x180012820`
- `KERNEL32!GetTickCount` at `0x180012820`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ShieldProvider::CPeriodicTaskManager::OnPeriodicTimerCallback(
        ShieldProvider::CPeriodicTaskManager *this)
{
  void *v2; // rbx
  bool v3; // si
  unsigned int v4; // edx
  char v5; // al
  void *i; // rbp
  int v7; // ebx
  DWORD TickCount; // eax
  _BYTE v9[72]; // [rsp+20h] [rbp-48h] BYREF

  v2 = 0;
  v3 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v9,
    (char *)this + 16);
  v5 = 1;
  for ( i = 0; ; i = v2 )
  {
    v9[16] = v5;
    if ( !v5 )
      break;
    if ( *((_BYTE *)this + 56) )
    {
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v9);
      if ( i )
        DeleteTimerQueueTimer(0, v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      return;
    }
    *((_DWORD *)this + 18) |= 1u;
    v7 = *((_DWORD *)this + 24);
    *((_DWORD *)this + 24) = ShieldProvider::CalculateTimerTrigger((ShieldProvider *)*((unsigned int *)this + 25), v4);
    TickCount = GetTickCount();
    v3 = TickCount - v7 >= 0xEA60 && v7 - TickCount >= 0xEA60;
    v2 = (void *)*((_QWORD *)this + 13);
    *((_QWORD *)this + 13) = i;
    v5 = 0;
  }
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v9);
  if ( i )
    DeleteTimerQueueTimer(0, v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_c15b3361942b3cf72eefef62f859076e_Traceguids);
    ShieldProvider::CPeriodicTaskManager::SubmitWorkItemDelayedTimer(this, 0x258u);
  }
  else
  {
    ShieldProvider::CPeriodicTaskManager::SubmitWorkItem(this);
  }
}

```

## disassembly

```asm
0x1800127d8  push    rbx
0x1800127da  push    rbp
0x1800127db  push    rsi
0x1800127dc  push    rdi
0x1800127dd  sub     rsp, 48h
0x1800127e1  mov     rdi, rcx
0x1800127e4  xor     ebx, ebx
0x1800127e6  mov     [rsp+68h+arg_0], rbx
0x1800127eb  xor     sil, sil
0x1800127ee  lea     rdx, [rcx+10h]
0x1800127f2  lea     rcx, [rsp+68h+var_48]
0x1800127f7  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800127fc  mov     al, 1
0x1800127fe  xor     ebp, ebp
0x180012800  mov     [rsp+68h+var_38], al
0x180012804  test    al, al
0x180012806  jz      short loc_18001287C
0x180012808  cmp     byte ptr [rdi+38h], 0
0x18001280c  jnz     short loc_180012857
0x18001280e  or      dword ptr [rdi+48h], 1
0x180012812  mov     ebx, [rdi+60h]
0x180012815  mov     ecx, [rdi+64h]; this
0x180012818  call    ?CalculateTimerTrigger@ShieldProvider@@YAKK@Z; ShieldProvider::CalculateTimerTrigger(ulong)
0x18001281d  mov     [rdi+60h], eax
0x180012820  call    cs:__imp_GetTickCount
0x180012826  mov     ecx, eax
0x180012828  sub     ecx, ebx
0x18001282a  cmp     ecx, 0EA60h
0x180012830  jnb     short loc_180012837
0x180012832  xor     sil, sil
0x180012835  jmp     short loc_180012843
0x180012837  sub     ebx, eax
0x180012839  cmp     ebx, 0EA60h
0x18001283f  setnb   sil
0x180012843  mov     rbx, [rdi+68h]
0x180012847  mov     [rsp+68h+arg_0], rbx
0x18001284c  mov     [rdi+68h], rbp
0x180012850  xor     al, al
0x180012852  mov     rbp, rbx
0x180012855  jmp     short loc_180012800
0x180012857  lea     rcx, [rsp+68h+var_48]
0x18001285c  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180012861  nop
0x180012862  test    rbp, rbp
0x180012865  jz      loc_1800128EE
0x18001286b  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18001286f  mov     rdx, rbx; Timer
0x180012872  xor     ecx, ecx; TimerQueue
0x180012874  call    cs:__imp_DeleteTimerQueueTimer
0x18001287a  jmp     short loc_1800128EE
0x18001287c  lea     rcx, [rsp+68h+var_48]
0x180012881  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180012886  test    rbp, rbp
0x180012889  jz      short loc_1800128A3
0x18001288b  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18001288f  mov     rdx, rbx; Timer
0x180012892  xor     ecx, ecx; TimerQueue
0x180012894  call    cs:__imp_DeleteTimerQueueTimer
0x18001289a  mov     [rsp+68h+arg_0], 0
0x1800128a3  test    sil, sil
0x1800128a6  jz      short loc_1800128E5
0x1800128a8  lea     rax, WPP_GLOBAL_Control
0x1800128af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128b6  cmp     rcx, rax
0x1800128b9  jz      short loc_1800128D6
0x1800128bb  test    byte ptr [rcx+1Ch], 4
0x1800128bf  jz      short loc_1800128D6
0x1800128c1  mov     edx, 17h
0x1800128c6  lea     r8, WPP_c15b3361942b3cf72eefef62f859076e_Traceguids
0x1800128cd  mov     rcx, [rcx+10h]
0x1800128d1  call    WPP_SF_
0x1800128d6  mov     edx, 258h; unsigned int
0x1800128db  mov     rcx, rdi; this
0x1800128de  call    ?SubmitWorkItemDelayedTimer@CPeriodicTaskManager@ShieldProvider@@AEAAXK@Z; ShieldProvider::CPeriodicTaskManager::SubmitWorkItemDelayedTimer(ulong)
0x1800128e3  jmp     short loc_1800128EE
0x1800128e5  mov     rcx, rdi; this
0x1800128e8  call    ?SubmitWorkItem@CPeriodicTaskManager@ShieldProvider@@AEAAXXZ; ShieldProvider::CPeriodicTaskManager::SubmitWorkItem(void)
0x1800128ed  nop
0x1800128ee  add     rsp, 48h
0x1800128f2  pop     rdi
0x1800128f3  pop     rsi
0x1800128f4  pop     rbp
0x1800128f5  pop     rbx
0x1800128f6  retn
```
