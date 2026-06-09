# OnDemand::InternalHandleL3Disconnected(_GUID const *,ushort)

- ea: `0x18003a7d4`
- end: `0x18003ab8b`
- name: `?InternalHandleL3Disconnected@OnDemand@@AEAAXPEBU_GUID@@G@Z`
- size: `951`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, const struct _GUID *, unsigned __int16)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006c1e0`

## callees

- `0x180007ff8`
- `0x180008394`
- `0x180010080`
- `0x180011bb0`
- `0x180011c20`
- `0x1800137a0`
- `0x180019434`
- `0x18003a7d4`
- `0x1800748e4`
- `0x1800822ac`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a82b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a82b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ab73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ab73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a9ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a9ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa80`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003a998`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003a9fb`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003aa5e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003a998`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003a9fb`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003aa5e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall OnDemand::InternalHandleL3Disconnected(
        LPCRITICAL_SECTION lpCriticalSection,
        const struct _GUID *a2,
        __int16 a3)
{
  const char *v6; // r9
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r15
  __int64 v8; // rax
  std::_Ref_count_base *v9; // rsi
  bool v10; // zf
  _QWORD *LockSemaphore; // r14
  ULONG_PTR SpinCount; // r12
  __int64 v13; // rcx
  void (__fastcall *v14)(_QWORD, __int64, __int64); // rax
  __int64 v15; // rdx
  void *v16; // rdx
  DWORD LastError; // eax
  void *v18; // rdx
  DWORD v19; // eax
  void *v20; // rdx
  DWORD v21; // eax
  unsigned int v22; // r9d
  struct _GUID v23; // xmm1
  __int128 v24; // xmm0
  std::_Ref_count_base *v25; // rcx
  std::_Ref_count_base *v26[2]; // [rsp+30h] [rbp-78h] BYREF
  struct _GUID v27; // [rsp+40h] [rbp-68h] BYREF
  __int64 v28; // [rsp+50h] [rbp-58h] BYREF
  __int128 v29; // [rsp+58h] [rbp-50h]
  LPCRITICAL_SECTION v30; // [rsp+68h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      107,
      WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids,
      "OnDemand::InternalHandleL3Disconnected");
  }
  EnterCriticalSection(lpCriticalSection);
  v30 = lpCriticalSection;
  DebugInfo = lpCriticalSection[1].DebugInfo;
  try
  {
    while ( DebugInfo != *(PRTL_CRITICAL_SECTION_DEBUG *)&lpCriticalSection[1].LockCount )
    {
      v8 = *(_QWORD *)(*(_QWORD *)&DebugInfo->Type + 2600LL) - *(_QWORD *)&a2->Data1;
      if ( !v8 )
        v8 = *(_QWORD *)(*(_QWORD *)&DebugInfo->Type + 2608LL) - *(_QWORD *)a2->Data4;
      if ( !v8 )
      {
        *(_OWORD *)v26 = 0;
        std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(v26);
        if ( a3 == 2 )
        {
          v9 = v26[0];
          *((_BYTE *)v26[0] + 3182) = 0;
        }
        else
        {
          v10 = a3 == 23;
          v9 = v26[0];
          if ( v10 )
            *((_BYTE *)v26[0] + 3183) = 0;
        }
        if ( !*((_BYTE *)v9 + 3182) && !*((_BYTE *)v9 + 3183) )
        {
          *((_DWORD *)v9 + 787) = -1;
          LockSemaphore = lpCriticalSection[1].LockSemaphore;
          SpinCount = lpCriticalSection[1].SpinCount;
          while ( LockSemaphore != (_QWORD *)SpinCount )
          {
            v13 = *LockSemaphore;
            if ( *(std::_Ref_count_base **)(*LockSemaphore + 200LL) == v9 )
            {
              v14 = *(void (__fastcall **)(_QWORD, __int64, __int64))(v13 + 224);
              if ( v14 )
              {
                v15 = *(_QWORD *)(v13 + 232);
                *(_QWORD *)(v13 + 224) = 0;
                *(_QWORD *)(*LockSemaphore + 232LL) = 0;
                v14(*LockSemaphore, v15, 55);
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                {
                  WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 108, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids);
                }
              }
              v27 = 0;
              std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::operator=(
                *LockSemaphore + 200LL,
                &v27);
              if ( *(_QWORD *)v27.Data4 )
                std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v27.Data4);
            }
            LockSemaphore += 2;
          }
          v16 = (void *)*((_QWORD *)v9 + 394);
          if ( v16 )
          {
            if ( !DeleteTimerQueueTimer(0, v16, 0)
              && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              LastError = GetLastError();
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                109,
                WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids,
                LastError);
            }
            *((_QWORD *)v9 + 394) = 0;
          }
          v18 = (void *)*((_QWORD *)v9 + 395);
          if ( v18 )
          {
            if ( !DeleteTimerQueueTimer(0, v18, 0)
              && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v19 = GetLastError();
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                110,
                WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids,
                v19);
            }
            *((_QWORD *)v9 + 395) = 0;
          }
          v20 = (void *)*((_QWORD *)v9 + 396);
          if ( v20 )
          {
            if ( !DeleteTimerQueueTimer(0, v20, 0)
              && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v21 = GetLastError();
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                111,
                WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids,
                v21);
            }
            *((_QWORD *)v9 + 396) = 0;
          }
          v22 = *((_DWORD *)v9 + 649);
          v23 = *(struct _GUID *)((char *)v9 + 2600);
          v24 = *(_OWORD *)((char *)v9 + 2616);
          v28 = 4;
          v29 = v24;
          v27 = v23;
          NetworkingTriageScenario::OnDemand::OnDemandConnectionStoppedAction(
            (const struct NetworkingTriageScenario::OnDemand::RequiredFields *)&v28,
            "InterfaceDisconnected",
            &v27,
            v22,
            -2147024841);
          std::_Move_unchecked<std::shared_ptr<OnDemand::OnDemandInterfaceInfo> *,std::shared_ptr<OnDemand::OnDemandInterfaceInfo> *>(
            &DebugInfo->ProcessLocksList,
            *(_QWORD *)&lpCriticalSection[1].LockCount,
            DebugInfo);
          v25 = *(std::_Ref_count_base **)(*(_QWORD *)&lpCriticalSection[1].LockCount - 8LL);
          if ( v25 )
            std::_Ref_count_base::_Decref(v25);
          *(_QWORD *)&lpCriticalSection[1].LockCount -= 16LL;
        }
        if ( v26[1] )
          std::_Ref_count_base::_Decref(v26[1]);
        break;
      }
      DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)((char *)DebugInfo + 16);
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_sL(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        112,
        (unsigned int)WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids,
        (unsigned int)"OnDemand::InternalHandleL3Disconnected",
        0);
    }
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x63D,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\ondemand.cpp",
      v6);
  }
}

```

## disassembly

```asm
0x18003a7d4  push    rbx
0x18003a7d6  push    rsi
0x18003a7d7  push    r12
0x18003a7d9  push    r13
0x18003a7db  push    r14
0x18003a7dd  push    r15
0x18003a7df  sub     rsp, 78h
0x18003a7e3  movzx   esi, r8w
0x18003a7e7  mov     r14, rdx
0x18003a7ea  mov     rbx, rcx
0x18003a7ed  lea     r13, WPP_GLOBAL_Control
0x18003a7f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a7fb  cmp     rcx, r13
0x18003a7fe  jz      short loc_18003A828
0x18003a800  cmp     byte ptr [rcx+19h], 5
0x18003a804  jb      short loc_18003A828
0x18003a806  test    byte ptr [rcx+1Ch], 1
0x18003a80a  jz      short loc_18003A828
0x18003a80c  mov     edx, 6Bh ; 'k'
0x18003a811  lea     r9, aOndemandIntern_12; "OnDemand::InternalHandleL3Disconnected"
0x18003a818  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x18003a81f  mov     rcx, [rcx+10h]
0x18003a823  call    WPP_SF_s
0x18003a828  mov     rcx, rbx; lpCriticalSection
0x18003a82b  call    cs:__imp_EnterCriticalSection
0x18003a831  mov     [rsp+0A8h+var_40], rbx
0x18003a836  mov     r15, [rbx+28h]
0x18003a83a  jmp     short loc_18003A85F
0x18003a83c  mov     rcx, [r15]
0x18003a83f  mov     rax, [rcx+0A28h]
0x18003a846  sub     rax, [r14]
0x18003a849  jnz     short loc_18003A856
0x18003a84b  mov     rax, [rcx+0A30h]
0x18003a852  sub     rax, [r14+8]
0x18003a856  test    rax, rax
0x18003a859  jz      short loc_18003A86A
0x18003a85b  add     r15, 10h
0x18003a85f  cmp     r15, [rbx+30h]
0x18003a863  jnz     short loc_18003A83C
0x18003a865  jmp     loc_18003AB2E
0x18003a86a  xorps   xmm0, xmm0
0x18003a86d  movups  xmmword ptr [rsp+0A8h+var_78], xmm0
0x18003a872  mov     rdx, r15
0x18003a875  lea     rcx, [rsp+0A8h+var_78]
0x18003a87a  call    ??$?0V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<std::tuple<long,std::unique_ptr<_WCM_ONDEMAND_STATE_INFO,wil::function_deleter<void (*)(void *),&WcmFree(void *)>>>>> const &)
0x18003a87f  nop
0x18003a880  cmp     si, 2
0x18003a884  jnz     short loc_18003A894
0x18003a886  mov     rsi, [rsp+0A8h+var_78]
0x18003a88b  mov     byte ptr [rsi+0C6Eh], 0
0x18003a892  jmp     short loc_18003A8A6
0x18003a894  cmp     si, 17h
0x18003a898  mov     rsi, [rsp+0A8h+var_78]
0x18003a89d  jnz     short loc_18003A8A6
0x18003a89f  mov     byte ptr [rsi+0C6Fh], 0
0x18003a8a6  cmp     byte ptr [rsi+0C6Eh], 0
0x18003a8ad  jnz     loc_18003AB1F
0x18003a8b3  cmp     byte ptr [rsi+0C6Fh], 0
0x18003a8ba  jnz     loc_18003AB1F
0x18003a8c0  mov     dword ptr [rsi+0C4Ch], 0FFFFFFFFh
0x18003a8ca  mov     r14, [rbx+40h]
0x18003a8ce  mov     r12, [rbx+48h]
0x18003a8d2  cmp     r14, r12
0x18003a8d5  jz      loc_18003A987
0x18003a8db  mov     rcx, [r14]
0x18003a8de  cmp     [rcx+0C8h], rsi
0x18003a8e5  jnz     loc_18003A97E
0x18003a8eb  mov     rax, [rcx+0E0h]
0x18003a8f2  test    rax, rax
0x18003a8f5  jz      short loc_18003A952
0x18003a8f7  mov     rdx, [rcx+0E8h]
0x18003a8fe  mov     qword ptr [rcx+0E0h], 0
0x18003a909  mov     rcx, [r14]
0x18003a90c  mov     qword ptr [rcx+0E8h], 0
0x18003a917  mov     r8d, 37h ; '7'
0x18003a91d  mov     rcx, [r14]
0x18003a920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a925  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a92c  cmp     rcx, r13
0x18003a92f  jz      short loc_18003A952
0x18003a931  cmp     byte ptr [rcx+19h], 4
0x18003a935  jb      short loc_18003A952
0x18003a937  test    byte ptr [rcx+1Ch], 1
0x18003a93b  jz      short loc_18003A952
0x18003a93d  mov     edx, 6Ch ; 'l'
0x18003a942  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x18003a949  mov     rcx, [rcx+10h]
0x18003a94d  call    WPP_SF_
0x18003a952  xorps   xmm0, xmm0
0x18003a955  movdqu  xmmword ptr [rsp+0A8h+var_68.Data1], xmm0
0x18003a95b  mov     rcx, [r14]
0x18003a95e  add     rcx, 0C8h
0x18003a965  lea     rdx, [rsp+0A8h+var_68]
0x18003a96a  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &&)
0x18003a96f  mov     rcx, qword ptr [rsp+0A8h+var_68.Data4]; this
0x18003a974  test    rcx, rcx
0x18003a977  jz      short loc_18003A97E
0x18003a979  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003a97e  add     r14, 10h
0x18003a982  jmp     loc_18003A8D2
0x18003a987  mov     rdx, [rsi+0C50h]; Timer
0x18003a98e  test    rdx, rdx
0x18003a991  jz      short loc_18003A9EA
0x18003a993  xor     r8d, r8d; CompletionEvent
0x18003a996  xor     ecx, ecx; TimerQueue
0x18003a998  call    cs:__imp_DeleteTimerQueueTimer
0x18003a99e  test    eax, eax
0x18003a9a0  jnz     short loc_18003A9DF
0x18003a9a2  mov     rax, cs:WPP_GLOBAL_Control
0x18003a9a9  cmp     rax, r13
0x18003a9ac  jz      short loc_18003A9DF
0x18003a9ae  cmp     byte ptr [rax+19h], 3
0x18003a9b2  jb      short loc_18003A9DF
0x18003a9b4  test    byte ptr [rax+1Ch], 1
0x18003a9b8  jz      short loc_18003A9DF
0x18003a9ba  call    cs:__imp_GetLastError
0x18003a9c0  mov     edx, 6Dh ; 'm'
0x18003a9c5  mov     r9d, eax
0x18003a9c8  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x18003a9cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a9d6  mov     rcx, [rcx+10h]
0x18003a9da  call    WPP_SF_d
0x18003a9df  mov     qword ptr [rsi+0C50h], 0
0x18003a9ea  mov     rdx, [rsi+0C58h]; Timer
0x18003a9f1  test    rdx, rdx
0x18003a9f4  jz      short loc_18003AA4D
0x18003a9f6  xor     r8d, r8d; CompletionEvent
0x18003a9f9  xor     ecx, ecx; TimerQueue
0x18003a9fb  call    cs:__imp_DeleteTimerQueueTimer
0x18003aa01  test    eax, eax
0x18003aa03  jnz     short loc_18003AA42
0x18003aa05  mov     rax, cs:WPP_GLOBAL_Control
0x18003aa0c  cmp     rax, r13
0x18003aa0f  jz      short loc_18003AA42
0x18003aa11  cmp     byte ptr [rax+19h], 3
0x18003aa15  jb      short loc_18003AA42
0x18003aa17  test    byte ptr [rax+1Ch], 1
0x18003aa1b  jz      short loc_18003AA42
0x18003aa1d  call    cs:__imp_GetLastError
0x18003aa23  mov     edx, 6Eh ; 'n'
0x18003aa28  mov     r9d, eax
0x18003aa2b  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x18003aa32  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aa39  mov     rcx, [rcx+10h]
0x18003aa3d  call    WPP_SF_d
0x18003aa42  mov     qword ptr [rsi+0C58h], 0
0x18003aa4d  mov     rdx, [rsi+0C60h]; Timer
0x18003aa54  test    rdx, rdx
0x18003aa57  jz      short loc_18003AAB0
0x18003aa59  xor     r8d, r8d; CompletionEvent
0x18003aa5c  xor     ecx, ecx; TimerQueue
0x18003aa5e  call    cs:__imp_DeleteTimerQueueTimer
0x18003aa64  test    eax, eax
0x18003aa66  jnz     short loc_18003AAA5
0x18003aa68  mov     rax, cs:WPP_GLOBAL_Control
0x18003aa6f  cmp     rax, r13
0x18003aa72  jz      short loc_18003AAA5
0x18003aa74  cmp     byte ptr [rax+19h], 3
0x18003aa78  jb      short loc_18003AAA5
0x18003aa7a  test    byte ptr [rax+1Ch], 1
0x18003aa7e  jz      short loc_18003AAA5
0x18003aa80  call    cs:__imp_GetLastError
0x18003aa86  mov     edx, 6Fh ; 'o'
0x18003aa8b  mov     r9d, eax
0x18003aa8e  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x18003aa95  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aa9c  mov     rcx, [rcx+10h]
0x18003aaa0  call    WPP_SF_d
0x18003aaa5  mov     qword ptr [rsi+0C60h], 0
0x18003aab0  mov     r9d, [rsi+0A24h]; unsigned int
0x18003aab7  movups  xmm1, xmmword ptr [rsi+0A28h]
0x18003aabe  movups  xmm0, xmmword ptr [rsi+0A38h]
0x18003aac5  mov     [rsp+0A8h+var_58], 4
0x18003aace  movdqu  [rsp+0A8h+var_50], xmm0
0x18003aad4  movdqu  xmmword ptr [rsp+0A8h+var_68.Data1], xmm1
0x18003aada  mov     [rsp+0A8h+var_88], 80070037h; int
0x18003aae2  lea     r8, [rsp+0A8h+var_68]; struct _GUID *
0x18003aae7  lea     rdx, aInterfacedisco; "InterfaceDisconnected"
0x18003aaee  lea     rcx, [rsp+0A8h+var_58]; struct NetworkingTriageScenario::OnDemand::RequiredFields *
0x18003aaf3  call    ?OnDemandConnectionStoppedAction@OnDemand@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBDU_GUID@@IJ@Z; NetworkingTriageScenario::OnDemand::OnDemandConnectionStoppedAction(NetworkingTriageScenario::OnDemand::RequiredFields const &,char const *,_GUID,uint,long)
0x18003aaf8  lea     rcx, [r15+10h]
0x18003aafc  mov     r8, r15
0x18003aaff  mov     rdx, [rbx+30h]
0x18003ab03  call    ??$_Move_unchecked@PEAV?$shared_ptr@UOnDemandInterfaceInfo@OnDemand@@@std@@PEAV12@@std@@YAPEAV?$shared_ptr@UOnDemandInterfaceInfo@OnDemand@@@0@PEAV10@00@Z; std::_Move_unchecked<std::shared_ptr<OnDemand::OnDemandInterfaceInfo> *,std::shared_ptr<OnDemand::OnDemandInterfaceInfo> *>(std::shared_ptr<OnDemand::OnDemandInterfaceInfo> *,std::shared_ptr<OnDemand::OnDemandInterfaceInfo> *,std::shared_ptr<OnDemand::OnDemandInterfaceInfo> *)
0x18003ab08  mov     rax, [rbx+30h]
0x18003ab0c  mov     rcx, [rax-8]; this
0x18003ab10  test    rcx, rcx
0x18003ab13  jz      short loc_18003AB1A
0x18003ab15  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003ab1a  add     qword ptr [rbx+30h], 0FFFFFFFFFFFFFFF0h
0x18003ab1f  mov     rcx, [rsp+0A8h+var_78+8]; this
0x18003ab24  test    rcx, rcx
0x18003ab27  jz      short loc_18003AB2E
0x18003ab29  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003ab2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ab35  cmp     rcx, r13
0x18003ab38  jz      short loc_18003AB6B
0x18003ab3a  cmp     byte ptr [rcx+19h], 5
0x18003ab3e  jb      short loc_18003AB6B
0x18003ab40  test    byte ptr [rcx+1Ch], 1
0x18003ab44  jz      short loc_18003AB6B
0x18003ab46  mov     edx, 70h ; 'p'
0x18003ab4b  mov     [rsp+0A8h+var_88], 0
0x18003ab53  lea     r9, aOndemandIntern_12; "OnDemand::InternalHandleL3Disconnected"
0x18003ab5a  lea     r8, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x18003ab61  mov     rcx, [rcx+10h]
0x18003ab65  call    WPP_SF_sL
0x18003ab6a  nop
0x18003ab6b  test    rbx, rbx
0x18003ab6e  jz      short loc_18003AB7A
0x18003ab70  mov     rcx, rbx; lpCriticalSection
0x18003ab73  call    cs:__imp_LeaveCriticalSection
0x18003ab79  nop
0x18003ab7a  jmp     short $+2
0x18003ab7c  add     rsp, 78h
0x18003ab80  pop     r15
0x18003ab82  pop     r14
0x18003ab84  pop     r13
0x18003ab86  pop     r12
0x18003ab88  pop     rsi
0x18003ab89  pop     rbx
0x18003ab8a  retn
```
