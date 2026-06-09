# MemoryTimerService::TimerHandler::CancelTimer(void)

- ea: `0x180031790`
- end: `0x1800318f8`
- name: `?CancelTimer@TimerHandler@MemoryTimerService@@QEAAXXZ`
- size: `360`
- prototype: `void __fastcall(MemoryTimerService::TimerHandler *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180017a20`
- `0x18009a980`

## callees

- `0x18000ab50`
- `0x1800119e0`
- `0x180013b50`
- `0x180031790`
- `0x180031900`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800317dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800317dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800317bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800317bc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031845`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031845`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031830`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031830`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800318c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800318c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800318e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800318e5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003181a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003181a`

## string_xrefs

- `0x18003184f`: `Wait failed for the timer event, incoming heap corruption.`
- `0x180031873`: `MemoryTimerService::TimerHandler::CancelTimer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MemoryTimerService::TimerHandler::CancelTimer(HANDLE *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  HANDLE v3; // rax
  int LastError; // eax
  void **v5; // [rsp+40h] [rbp-20h] BYREF
  HANDLE CompletionEvent; // [rsp+48h] [rbp-18h]
  void **v7; // [rsp+50h] [rbp-10h] BYREF
  HANDLE EventW; // [rsp+58h] [rbp-8h]

  CompletionEvent = 0;
  v5 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)(this + 13);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 13));
  if ( this[12] )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    v7 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(&v5);
    CompletionEvent = EventW;
    EventW = 0;
    v7 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(&v7);
    DeleteTimerQueueTimer(0, this[12], CompletionEvent);
    this[12] = 0;
  }
  if ( v2 )
    LeaveCriticalSection(v2);
  v3 = CompletionEvent;
  if ( CompletionEvent )
  {
    if ( WaitForSingleObject(CompletionEvent, 0xFFFFFFFF) )
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\memorytimer.cpp",
        0xD8u,
        "MemoryTimerService::TimerHandler::CancelTimer",
        (wchar_t *)L"Assert (%s): %s",
        L"(success == ((((NTSTATUS)0x00000000L) ) + 0 ))",
        L"Wait failed for the timer event, incoming heap corruption.");
    (*((void (__fastcall **)(HANDLE *))*this + 2))(this);
    MemoryTimerService::CleanupTimer(this[11], this + 7);
    v3 = CompletionEvent;
  }
  v5 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( v3
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v5) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x180031790  push    rbp
0x180031792  push    rbx
0x180031793  push    rdi
0x180031794  push    r12
0x180031796  push    r15
0x180031798  mov     rbp, rsp
0x18003179b  sub     rsp, 60h
0x18003179f  mov     rbx, rcx
0x1800317a2  mov     [rbp+CompletionEvent], 0
0x1800317aa  lea     r15, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1800317b1  mov     [rbp+var_20], r15
0x1800317b5  lea     rdi, [rcx+68h]
0x1800317b9  mov     rcx, rdi; lpCriticalSection
0x1800317bc  call    cs:__imp_EnterCriticalSection
0x1800317c2  lea     r12, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1800317c9  cmp     qword ptr [rbx+60h], 0
0x1800317ce  jz      short loc_180031828
0x1800317d0  xor     r9d, r9d; lpName
0x1800317d3  xor     r8d, r8d; bInitialState
0x1800317d6  lea     edx, [r9+1]; bManualReset
0x1800317da  xor     ecx, ecx; lpEventAttributes
0x1800317dc  call    cs:__imp_CreateEventW
0x1800317e2  mov     [rbp+var_8], rax
0x1800317e6  mov     [rbp+var_10], r15
0x1800317ea  lea     rcx, [rbp+var_20]
0x1800317ee  call    ?Close@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(void)
0x1800317f3  mov     rax, [rbp+var_8]
0x1800317f7  mov     [rbp+CompletionEvent], rax
0x1800317fb  mov     [rbp+var_8], 0
0x180031803  mov     [rbp+var_10], r12
0x180031807  lea     rcx, [rbp+var_10]
0x18003180b  call    ?Close@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(void)
0x180031810  mov     r8, [rbp+CompletionEvent]; CompletionEvent
0x180031814  mov     rdx, [rbx+60h]; Timer
0x180031818  xor     ecx, ecx; TimerQueue
0x18003181a  call    cs:__imp_DeleteTimerQueueTimer
0x180031820  mov     qword ptr [rbx+60h], 0
0x180031828  test    rdi, rdi
0x18003182b  jz      short loc_180031836
0x18003182d  mov     rcx, rdi; lpCriticalSection
0x180031830  call    cs:__imp_LeaveCriticalSection
0x180031836  mov     rax, [rbp+CompletionEvent]
0x18003183a  test    rax, rax
0x18003183d  jz      short loc_1800318B1
0x18003183f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180031842  mov     rcx, rax; hHandle
0x180031845  call    cs:__imp_WaitForSingleObject
0x18003184b  test    eax, eax
0x18003184d  jz      short loc_180031891
0x18003184f  lea     rax, aWaitFailedForT; "Wait failed for the timer event, incomi"...
0x180031856  mov     [rsp+60h+var_30], rax
0x18003185b  lea     rax, aSuccessNtstatu; "(success == ((((NTSTATUS)0x00000000L) )"...
0x180031862  mov     [rsp+60h+var_38], rax
0x180031867  lea     rax, aAssertSS; "Assert (%s): %s"
0x18003186e  mov     [rsp+60h+Format], rax; Format
0x180031873  lea     r9, aMemorytimerser_0; "MemoryTimerService::TimerHandler::Cance"...
0x18003187a  mov     r8d, 0D8h; unsigned int
0x180031880  lea     rdx, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\licensem"...
0x180031887  mov     ecx, 1; unsigned int
0x18003188c  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180031891  mov     rax, [rbx]
0x180031894  mov     rcx, rbx
0x180031897  mov     rax, [rax+10h]
0x18003189b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318a0  lea     rdx, [rbx+38h]
0x1800318a4  mov     rcx, [rbx+58h]
0x1800318a8  call    ?CleanupTimer@MemoryTimerService@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MemoryTimerService::CleanupTimer(std::wstring const &)
0x1800318ad  mov     rax, [rbp+CompletionEvent]
0x1800318b1  mov     [rbp+var_20], r12
0x1800318b5  test    rax, rax
0x1800318b8  jz      short loc_1800318EC
0x1800318ba  lea     rcx, [rbp+var_20]
0x1800318be  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x1800318c3  test    al, al
0x1800318c5  jnz     short loc_1800318EC
0x1800318c7  call    cs:__imp_GetLastError
0x1800318cd  test    eax, eax
0x1800318cf  jle     short loc_1800318D9
0x1800318d1  movzx   eax, ax
0x1800318d4  or      eax, 80070000h
0x1800318d9  xor     r9d, r9d; lpArguments
0x1800318dc  xor     r8d, r8d; nNumberOfArguments
0x1800318df  lea     edx, [r9+1]; dwExceptionFlags
0x1800318e3  mov     ecx, eax; dwExceptionCode
0x1800318e5  call    cs:__imp_RaiseException
0x1800318eb  int     3; Trap to Debugger
0x1800318ec  add     rsp, 60h
0x1800318f0  pop     r15
0x1800318f2  pop     r12
0x1800318f4  pop     rdi
0x1800318f5  pop     rbx
0x1800318f6  pop     rbp
0x1800318f7  retn
```
