# RadioManager::_ChangeSystemRadioState(bool,bool,bool)

- ea: `0x18002036c`
- end: `0x180020563`
- name: `?_ChangeSystemRadioState@RadioManager@@AEAAJ_N00@Z`
- size: `503`
- prototype: `__int64 __fastcall(RadioManager *__hidden this, bool, bool, bool)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001f530`
- `0x18001fd00`

## callees

- `0x1800088e0`
- `0x18000af44`
- `0x18000c2a4`
- `0x18000d2a0`
- `0x18001da90`
- `0x18002036c`
- `0x18002195c`
- `0x180021d48`
- `0x1800222d0`
- `0x180023270`
- `0x180023308`
- `0x18002336c`
- `0x180023af0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800203a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800203a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002045f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002045f`

## string_xrefs

- `0x1800203e4`: `System is already in the desired radio state (off), but continuing to process because ABSlider was set to off`
- `0x1800204ab`: `System is already in the desired radio state`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RadioManager::_ChangeSystemRadioState(RadioManager *this, char a2, bool a3, bool a4)
{
  char *v8; // rbx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  unsigned int v12; // ebx
  struct MEDIA_RADIO_MANAGER **v13; // r13
  struct MEDIA_RADIO_MANAGER **i; // r14
  int v15; // eax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  __int64 *v19; // rdx
  const char *v21; // [rsp+30h] [rbp-30h] BYREF
  char *v22; // [rsp+38h] [rbp-28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR pftDueTime; // [rsp+40h] [rbp-20h] BYREF

  v8 = (char *)this + 240;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 6);
  v22 = v8;
  if ( *(_BYTE *)(ProtectedSystemState::GetSystemState((char *)this + 48, &pftDueTime) + 8) == a2 )
  {
    if ( !a4 || a2 )
    {
      if ( (unsigned int)dword_180037050 > 4 )
      {
        v21 = "System is already in the desired radio state";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v9,
          (unsigned int)byte_18002F37D,
          v10,
          v11,
          (__int64)&v21);
      }
      v12 = 0;
      goto LABEL_24;
    }
    if ( (unsigned int)dword_180037050 > 4 )
    {
      v21 = "System is already in the desired radio state (off), but continuing to process because ABSlider was set to off";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v9,
        (unsigned int)&byte_18002F3BF,
        v10,
        v11,
        (__int64)&v21);
    }
  }
  if ( !_InterlockedExchange((volatile __int32 *)this + 106, 1) )
  {
    if ( (unsigned int)dword_180037050 > 4 )
    {
      v21 = "TP timer started";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v9,
        (unsigned int)byte_18002F33B,
        v10,
        v11,
        (__int64)&v21);
    }
    AddRefSingleton(this);
    pftDueTime.Ptr = -300000000;
    SetThreadpoolTimer(*((PTP_TIMER *)this + 52), (PFILETIME)&pftDueTime, 0, 0);
  }
  ProtectedSystemState::IncrementRadioChangeInProgress((RadioManager *)((char *)this + 48));
  ProtectedSystemState::UpdateSystemState((RadioManager *)((char *)this + 48), a2, a3);
  RadioManager::_NotifySysRadioChanged(this);
  RadioManager::_RefreshPreferredMediaManager(this, a4);
  v12 = 0;
  v13 = (struct MEDIA_RADIO_MANAGER **)*((_QWORD *)this + 36);
  for ( i = (struct MEDIA_RADIO_MANAGER **)*((_QWORD *)this + 35); i != v13; ++i )
  {
    v15 = RadioManager::_SetSysRadio(this, a2, a4, *i);
    if ( v15 < 0 )
      v12 = v15;
  }
  ProtectedSystemState::DecrementRadioChangeInProgress((RadioManager *)((char *)this + 48));
  RadioManager::_NotifySysRadioChanged(this);
  if ( a2 )
  {
    if ( (Microsoft_Windows_RadioManagerEnableBits & 1) != 0 )
    {
      v19 = SystemRadio_TurnOn_Stop;
LABEL_23:
      McGenEventWrite_EventWriteTransfer(v16, (int)v19, v17, v18, &pftDueTime);
    }
  }
  else if ( (Microsoft_Windows_RadioManagerEnableBits & 1) != 0 )
  {
    v19 = (__int64 *)&SystemRadio_TurnOff_Stop;
    goto LABEL_23;
  }
LABEL_24:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v22);
  return v12;
}

```

## disassembly

```asm
0x18002036c  mov     [rsp-38h+arg_10], rbx
0x180020371  push    rbp
0x180020372  push    rsi
0x180020373  push    rdi
0x180020374  push    r12
0x180020376  push    r13
0x180020378  push    r14
0x18002037a  push    r15
0x18002037c  mov     rbp, rsp
0x18002037f  sub     rsp, 60h
0x180020383  mov     rax, cs:__security_cookie
0x18002038a  xor     rax, rsp
0x18002038d  mov     [rbp+var_10], rax
0x180020391  mov     r15b, r9b
0x180020394  mov     r14b, r8b
0x180020397  mov     sil, dl
0x18002039a  mov     rdi, rcx
0x18002039d  lea     rbx, [rcx+0F0h]
0x1800203a4  mov     rcx, rbx; lpCriticalSection
0x1800203a7  call    cs:__imp_EnterCriticalSection
0x1800203ad  mov     [rbp+var_28], rbx
0x1800203b1  lea     r12, [rdi+30h]
0x1800203b5  lea     rdx, [rbp+pftDueTime]
0x1800203b9  mov     rcx, r12
0x1800203bc  call    ?GetSystemState@ProtectedSystemState@@QEBA?AUSystemState@@XZ; ProtectedSystemState::GetSystemState(void)
0x1800203c1  cmp     [rax+8], sil
0x1800203c5  jnz     short loc_180020404
0x1800203c7  test    r15b, r15b
0x1800203ca  jz      loc_1800204A0
0x1800203d0  test    sil, sil
0x1800203d3  jnz     loc_1800204A0
0x1800203d9  mov     eax, cs:dword_180037050
0x1800203df  cmp     eax, 4
0x1800203e2  jbe     short loc_180020404
0x1800203e4  lea     rax, aSystemIsAlread; "System is already in the desired radio "...
0x1800203eb  mov     [rbp+var_30], rax
0x1800203ef  lea     rax, [rbp+var_30]
0x1800203f3  mov     [rsp+60h+var_40], rax
0x1800203f8  lea     rdx, byte_18002F3BF
0x1800203ff  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180020404  mov     eax, 1
0x180020409  xchg    eax, [rdi+1A8h]
0x18002040f  test    eax, eax
0x180020411  jnz     short loc_180020465
0x180020413  mov     eax, cs:dword_180037050
0x180020419  cmp     eax, 4
0x18002041c  jbe     short loc_18002043E
0x18002041e  lea     rax, aTpTimerStarted; "TP timer started"
0x180020425  mov     [rbp+var_30], rax
0x180020429  lea     rax, [rbp+var_30]
0x18002042d  mov     [rsp+60h+var_40], rax
0x180020432  lea     rdx, byte_18002F33B
0x180020439  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002043e  mov     rcx, rdi; struct RadioManager *
0x180020441  call    ?AddRefSingleton@@YAXPEAVRadioManager@@@Z; AddRefSingleton(RadioManager *)
0x180020446  mov     qword ptr [rbp+pftDueTime], 0FFFFFFFFEE1E5D00h
0x18002044e  xor     r9d, r9d; msWindowLength
0x180020451  xor     r8d, r8d; msPeriod
0x180020454  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x180020458  mov     rcx, [rdi+1A0h]; pti
0x18002045f  call    cs:__imp_SetThreadpoolTimer
0x180020465  mov     rcx, r12; this
0x180020468  call    ?IncrementRadioChangeInProgress@ProtectedSystemState@@QEAAXXZ; ProtectedSystemState::IncrementRadioChangeInProgress(void)
0x18002046d  mov     r8b, r14b; bool
0x180020470  mov     dl, sil; bool
0x180020473  mov     rcx, r12; this
0x180020476  call    ?UpdateSystemState@ProtectedSystemState@@QEAAX_N0@Z; ProtectedSystemState::UpdateSystemState(bool,bool)
0x18002047b  mov     rcx, rdi; this
0x18002047e  call    ?_NotifySysRadioChanged@RadioManager@@AEAAXXZ; RadioManager::_NotifySysRadioChanged(void)
0x180020483  mov     dl, r15b; bool
0x180020486  mov     rcx, rdi; this
0x180020489  call    ?_RefreshPreferredMediaManager@RadioManager@@AEAAX_N@Z; RadioManager::_RefreshPreferredMediaManager(bool)
0x18002048e  xor     ebx, ebx
0x180020490  mov     r13, [rdi+120h]
0x180020497  mov     r14, [rdi+118h]
0x18002049e  jmp     short loc_1800204E9
0x1800204a0  mov     eax, cs:dword_180037050
0x1800204a6  cmp     eax, 4
0x1800204a9  jbe     short loc_1800204CB
0x1800204ab  lea     rax, aSystemIsAlread_0; "System is already in the desired radio "...
0x1800204b2  mov     [rbp+var_30], rax
0x1800204b6  lea     rax, [rbp+var_30]
0x1800204ba  mov     [rsp+60h+var_40], rax
0x1800204bf  lea     rdx, byte_18002F37D
0x1800204c6  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800204cb  xor     ebx, ebx
0x1800204cd  jmp     short loc_180020534
0x1800204cf  mov     r9, [r14]; struct MEDIA_RADIO_MANAGER *
0x1800204d2  mov     r8b, r15b; bool
0x1800204d5  mov     dl, sil; bool
0x1800204d8  mov     rcx, rdi; this
0x1800204db  call    ?_SetSysRadio@RadioManager@@AEAAJ_N0PEAUMEDIA_RADIO_MANAGER@@@Z; RadioManager::_SetSysRadio(bool,bool,MEDIA_RADIO_MANAGER *)
0x1800204e0  test    eax, eax
0x1800204e2  cmovs   ebx, eax
0x1800204e5  add     r14, 8
0x1800204e9  cmp     r14, r13
0x1800204ec  jnz     short loc_1800204CF
0x1800204ee  mov     rcx, r12; this
0x1800204f1  call    ?DecrementRadioChangeInProgress@ProtectedSystemState@@QEAA_NXZ; ProtectedSystemState::DecrementRadioChangeInProgress(void)
0x1800204f6  mov     rcx, rdi; this
0x1800204f9  call    ?_NotifySysRadioChanged@RadioManager@@AEAAXXZ; RadioManager::_NotifySysRadioChanged(void)
0x1800204fe  test    sil, sil
0x180020501  jz      short loc_180020515
0x180020503  test    cs:Microsoft_Windows_RadioManagerEnableBits, 1
0x18002050a  jz      short loc_180020534
0x18002050c  lea     rdx, SystemRadio_TurnOn_Stop
0x180020513  jmp     short loc_180020525
0x180020515  test    cs:Microsoft_Windows_RadioManagerEnableBits, 1
0x18002051c  jz      short loc_180020534
0x18002051e  lea     rdx, SystemRadio_TurnOff_Stop; int
0x180020525  lea     rax, [rbp+pftDueTime]
0x180020529  mov     [rsp+60h+var_40], rax; PEVENT_DATA_DESCRIPTOR
0x18002052e  call    McGenEventWrite_EventWriteTransfer
0x180020533  nop
0x180020534  lea     rcx, [rbp+var_28]
0x180020538  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002053d  mov     eax, ebx
0x18002053f  mov     rcx, [rbp+var_10]
0x180020543  xor     rcx, rsp; StackCookie
0x180020546  call    __security_check_cookie
0x18002054b  mov     rbx, [rsp+60h+arg_10]
0x180020553  add     rsp, 60h
0x180020557  pop     r15
0x180020559  pop     r14
0x18002055b  pop     r13
0x18002055d  pop     r12
0x18002055f  pop     rdi
0x180020560  pop     rsi
0x180020561  pop     rbp
0x180020562  retn
```
