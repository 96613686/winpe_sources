# Container::Manager::Agent::Core::_anonymous_namespace_::HeartbeatThread

- ea: `0x1800170d0`
- end: `0x1800171cf`
- name: `Container::Manager::Agent::Core::_anonymous_namespace_::HeartbeatThread`
- size: `255`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180003ce4`
- `0x1800170d0`
- `0x180020e20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetWaitableTimerEx` at `0x18001711a`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimerEx` at `0x18001711a`
- `ntdll!NtSetEvent` at `0x180017156`
- `ntdll!NtSetEvent` at `0x180017156`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001717b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001717b`

## string_xrefs

- `0x1800171a6`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x1800171bd`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Core::_anonymous_namespace_::HeartbeatThread(PVOID Parameter)
{
  const char *v1; // r9
  NTSTATUS v2; // eax
  void *v3; // rdx
  unsigned int v4; // r8d
  DWORD v5; // eax
  const char *v6; // r9
  int v8; // [rsp+20h] [rbp-38h]
  HANDLE Handles[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LONG PreviousState; // [rsp+68h] [rbp+10h] BYREF
  LARGE_INTEGER v12; // [rsp+70h] [rbp+18h] BYREF

  v12.QuadPart = -10000LL * (unsigned int)lPeriod;
  if ( !SetWaitableTimerEx(hTimer, &v12, lPeriod, 0, 0, 0, (unsigned int)lPeriod > 0x1388 ? 0x3E8 : 0) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x8E,
      (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      v1);
  Handles[0] = hTimer;
  Handles[1] = qword_18004B938;
  do
  {
    PreviousState = 0;
    v2 = NtSetEvent(EventHandle, &PreviousState);
    if ( v2 < 0 )
      wil::details::in1diag3::_FailFast_NtStatus(retaddr, v3, v4, (const char *)(unsigned int)v2, v8);
    v5 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
  }
  while ( !v5 );
  if ( v5 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xA5,
      (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      v6);
  return 0;
}

```

## disassembly

```asm
0x1800170d0  mov     r11, rsp
0x1800170d3  sub     rsp, 58h
0x1800170d7  mov     r8d, cs:lPeriod; lPeriod
0x1800170de  lea     rdx, [r11+18h]; lpDueTime
0x1800170e2  imul    rcx, r8, 0FFFFFFFFFFFFD8F0h
0x1800170e9  mov     eax, 1388h
0x1800170ee  cmp     eax, r8d
0x1800170f1  mov     [r11+18h], rcx
0x1800170f5  mov     rcx, cs:hTimer; hTimer
0x1800170fc  sbb     eax, eax
0x1800170fe  xor     r9d, r9d; pfnCompletionRoutine
0x180017101  and     eax, 3E8h
0x180017106  mov     [rsp+58h+TolerableDelay], eax; TolerableDelay
0x18001710a  mov     qword ptr [r11-30h], 0
0x180017112  mov     qword ptr [r11-38h], 0
0x18001711a  call    cs:__imp_SetWaitableTimerEx
0x180017121  nop     dword ptr [rax+rax+00h]
0x180017126  test    eax, eax
0x180017128  jz      short loc_1800171A1
0x18001712a  mov     rax, cs:hTimer
0x180017131  mov     [rsp+58h+Handles], rax
0x180017136  mov     rax, cs:qword_18004B938
0x18001713d  mov     [rsp+58h+var_10], rax
0x180017142  mov     rcx, cs:EventHandle; EventHandle
0x180017149  lea     rdx, [rsp+58h+PreviousState]; PreviousState
0x18001714e  mov     [rsp+58h+PreviousState], 0
0x180017156  call    cs:__imp_NtSetEvent
0x18001715d  nop     dword ptr [rax+rax+00h]
0x180017162  mov     rcx, [rsp+58h]; this
0x180017167  test    eax, eax
0x180017169  js      short loc_180017198
0x18001716b  xor     r8d, r8d; bWaitAll
0x18001716e  lea     rdx, [rsp+58h+Handles]; lpHandles
0x180017173  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180017177  lea     ecx, [r8+2]; nCount
0x18001717b  call    cs:__imp_WaitForMultipleObjects
0x180017182  nop     dword ptr [rax+rax+00h]
0x180017187  test    eax, eax
0x180017189  jz      short loc_180017142
0x18001718b  cmp     eax, 0FFFFFFFFh
0x18001718e  jz      short loc_1800171B8
0x180017190  xor     eax, eax
0x180017192  add     rsp, 58h
0x180017196  retn
0x180017198  mov     r9d, eax; char *
0x18001719b  call    ?_FailFast_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_NtStatus(void *,uint,char const *,long)
0x1800171a1  mov     rcx, [rsp+58h]; this
0x1800171a6  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800171ad  mov     edx, 8Eh; void *
0x1800171b2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800171b8  mov     rcx, [rsp+58h]; this
0x1800171bd  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800171c4  mov     edx, 0A5h; void *
0x1800171c9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
