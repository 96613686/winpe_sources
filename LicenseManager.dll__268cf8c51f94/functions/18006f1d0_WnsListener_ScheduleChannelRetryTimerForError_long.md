# WnsListener::ScheduleChannelRetryTimerForError(long)

- ea: `0x18006f1d0`
- end: `0x18006f2d9`
- name: `?ScheduleChannelRetryTimerForError@WnsListener@@AEAAXJ@Z`
- size: `265`
- prototype: `void __fastcall(WnsListener *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18009de30`
- `0x18009e070`

## callees

- `0x18000b7a4`
- `0x180013b50`
- `0x18006f1d0`
- `0x18008a400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f1ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f1ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f2c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f2c0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18006f297`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18006f297`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WnsListener::ScheduleChannelRetryTimerForError(WnsListener *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 v5; // rax
  unsigned __int64 DueTime; // rdi
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close((char *)this + 56);
  if ( a2 == -2147023674 )
  {
    v5 = *((unsigned int *)this + 46);
    DueTime = 60000 * v5;
    if ( (unsigned int)v5 < 0x1E )
      *((_DWORD *)this + 46) = 2 * v5;
    if ( DueTime > 0x1B7740 )
      LODWORD(DueTime) = 1800000;
  }
  else
  {
    LODWORD(DueTime) = 60000;
    *((_DWORD *)this + 46) = 1;
  }
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
    0x26Du,
    "WnsListener::ScheduleChannelRetryTimerForError",
    (wchar_t *)L"WNS channel registration failed 0x%08X, scheduling retry in %dms",
    a2,
    DueTime);
  if ( !CreateTimerQueueTimer((PHANDLE)this + 8, 0, WnsListener::_RegisterChannelTimerCallback, 0, DueTime, 0, 0x20u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x26E,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
      v7);
  if ( v4 )
    LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x18006f1d0  mov     [rsp+arg_8], rbx
0x18006f1d5  mov     [rsp+arg_10], rbp
0x18006f1da  push    rsi
0x18006f1db  push    rdi
0x18006f1dc  push    r14
0x18006f1de  sub     rsp, 40h
0x18006f1e2  mov     ebp, edx
0x18006f1e4  mov     rbx, rcx
0x18006f1e7  lea     rsi, [rcx+10h]
0x18006f1eb  mov     rcx, rsi; lpCriticalSection
0x18006f1ee  call    cs:__imp_EnterCriticalSection
0x18006f1f4  mov     [rsp+58h+arg_0], rsi
0x18006f1f9  lea     rcx, [rbx+38h]
0x18006f1fd  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18006f202  cmp     ebp, 800704C6h
0x18006f208  jnz     short loc_18006F232
0x18006f20a  mov     eax, [rbx+0B8h]
0x18006f210  imul    rdi, rax, 0EA60h
0x18006f217  cmp     eax, 1Eh
0x18006f21a  jnb     short loc_18006F224
0x18006f21c  add     eax, eax
0x18006f21e  mov     [rbx+0B8h], eax
0x18006f224  mov     eax, 1B7740h
0x18006f229  cmp     rdi, rax
0x18006f22c  cmova   rdi, rax
0x18006f230  jmp     short loc_18006F241
0x18006f232  mov     edi, 0EA60h
0x18006f237  mov     dword ptr [rbx+0B8h], 1
0x18006f241  mov     [rsp+58h+Flags], edi
0x18006f245  mov     [rsp+58h+Period], ebp
0x18006f249  lea     rax, aWnsChannelRegi; "WNS channel registration failed 0x%08X,"...
0x18006f250  mov     qword ptr [rsp+58h+DueTime], rax; Format
0x18006f255  lea     r9, aWnslistenerSch; "WnsListener::ScheduleChannelRetryTimerF"...
0x18006f25c  mov     r8d, 26Dh; unsigned int
0x18006f262  lea     rdx, aOnecoreuapEndu_23; "onecoreuap\\enduser\\winstore\\licensem"...
0x18006f269  mov     ecx, 3; unsigned int
0x18006f26e  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18006f273  lea     rcx, [rbx+40h]; phNewTimer
0x18006f277  mov     [rsp+58h+Flags], 20h ; ' '; Flags
0x18006f27f  mov     [rsp+58h+Period], 0; Period
0x18006f287  mov     [rsp+58h+DueTime], edi; DueTime
0x18006f28b  xor     r9d, r9d; Parameter
0x18006f28e  lea     r8, ?_RegisterChannelTimerCallback@WnsListener@@CAXPEAXE@Z; Callback
0x18006f295  xor     edx, edx; TimerQueue
0x18006f297  call    cs:__imp_CreateTimerQueueTimer
0x18006f29d  mov     rcx, [rsp+58h]; this
0x18006f2a2  test    eax, eax
0x18006f2a4  jnz     short loc_18006F2B8
0x18006f2a6  lea     r8, aOnecoreuapEndu_23; "onecoreuap\\enduser\\winstore\\licensem"...
0x18006f2ad  mov     edx, 26Eh; void *
0x18006f2b2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18006f2b8  test    rsi, rsi
0x18006f2bb  jz      short loc_18006F2C6
0x18006f2bd  mov     rcx, rsi; lpCriticalSection
0x18006f2c0  call    cs:__imp_LeaveCriticalSection
0x18006f2c6  mov     rbx, [rsp+58h+arg_8]
0x18006f2cb  mov     rbp, [rsp+58h+arg_10]
0x18006f2d0  add     rsp, 40h
0x18006f2d4  pop     r14
0x18006f2d6  pop     rdi
0x18006f2d7  pop     rsi
0x18006f2d8  retn
```
