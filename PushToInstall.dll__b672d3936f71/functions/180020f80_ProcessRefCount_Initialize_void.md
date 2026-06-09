# ProcessRefCount::Initialize(void)

- ea: `0x180020f80`
- end: `0x1800210da`
- name: `?Initialize@ProcessRefCount@@QEAAJXZ`
- size: `346`
- prototype: `__int64 __fastcall(_QWORD *pv)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800212ac`

## callees

- `0x18000fca8`
- `0x180010b64`
- `0x180010b84`
- `0x180011afc`
- `0x180020f80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180020f9a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180020f9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021012`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021012`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020fd6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021044`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020fd6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021044`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020fc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020fc6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002103c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002103c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180021033`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180021033`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180021000`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180021000`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180021025`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800210b2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180021025`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800210b2`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x180020fe3`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x180020fe3`

## string_xrefs

- `0x1800210c8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180021058`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`
- `0x18002107d`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ProcessRefCount::Initialize(_QWORD *pv)
{
  wil::details *v2; // rcx
  HANDLE Event; // rsi
  void *v4; // rbx
  DWORD LastError; // ebp
  const char *v6; // r9
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v8; // r9
  struct _TP_TIMER *v9; // rbp
  struct _TP_TIMER *v10; // rsi
  DWORD v11; // ebx
  int LastErrorFailHr; // eax
  unsigned int v14; // ebx
  int v15; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v4 = (void *)pv[3];
    if ( v4 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v4) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v6);
      SetLastError(LastError);
    }
    pv[3] = Event;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v2);
    v14 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
        (const char *)(unsigned int)LastErrorFailHr,
        v15);
      return v14;
    }
  }
  SetProcessReference(pv);
  if ( *((_BYTE *)pv + 20) )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(ProcessRefCount::s_TimerCallback, pv, 0);
    v9 = (struct _TP_TIMER *)pv[4];
    v10 = ThreadpoolTimer;
    if ( v9 )
    {
      v11 = GetLastError();
      SetThreadpoolTimer(v9, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v9, 1);
      CloseThreadpoolTimer(v9);
      SetLastError(v11);
    }
    pv[4] = v10;
    if ( !v10 )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x2C,
               (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
               v8);
    pftDueTime = (struct _FILETIME)-6000000000LL;
    SetThreadpoolTimer(v10, &pftDueTime, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180020f80  push    rbx
0x180020f82  push    rbp
0x180020f83  push    rsi
0x180020f84  push    rdi
0x180020f85  sub     rsp, 28h
0x180020f89  xor     edx, edx; lpName
0x180020f8b  mov     rdi, rcx
0x180020f8e  xor     ecx, ecx; lpEventAttributes
0x180020f90  mov     r9d, 1F0003h; dwDesiredAccess
0x180020f96  lea     r8d, [rdx+1]; dwFlags
0x180020f9a  call    cs:__imp_CreateEventExW
0x180020fa0  mov     rsi, rax
0x180020fa3  test    rax, rax
0x180020fa6  jz      loc_180021069
0x180020fac  call    cs:__imp_GetLastError
0x180020fb2  mov     rbx, [rdi+18h]
0x180020fb6  test    rbx, rbx
0x180020fb9  jz      short loc_180020FDC
0x180020fbb  call    cs:__imp_GetLastError
0x180020fc1  mov     rcx, rbx; hObject
0x180020fc4  mov     ebp, eax
0x180020fc6  call    cs:__imp_CloseHandle
0x180020fcc  test    eax, eax
0x180020fce  jz      loc_1800210C3
0x180020fd4  mov     ecx, ebp; dwErrCode
0x180020fd6  call    cs:__imp_SetLastError
0x180020fdc  mov     [rdi+18h], rsi
0x180020fe0  mov     rcx, rdi
0x180020fe3  call    cs:__imp_SetProcessReference
0x180020fe9  cmp     byte ptr [rdi+14h], 0
0x180020fed  jz      loc_1800210B8
0x180020ff3  xor     r8d, r8d; pcbe
0x180020ff6  lea     rcx, ?s_TimerCallback@ProcessRefCount@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180020ffd  mov     rdx, rdi; pv
0x180021000  call    cs:__imp_CreateThreadpoolTimer
0x180021006  mov     rbp, [rdi+20h]
0x18002100a  mov     rsi, rax
0x18002100d  test    rbp, rbp
0x180021010  jz      short loc_18002104A
0x180021012  call    cs:__imp_GetLastError
0x180021018  xor     r9d, r9d; msWindowLength
0x18002101b  xor     r8d, r8d; msPeriod
0x18002101e  xor     edx, edx; pftDueTime
0x180021020  mov     rcx, rbp; pti
0x180021023  mov     ebx, eax
0x180021025  call    cs:__imp_SetThreadpoolTimer
0x18002102b  mov     edx, 1; fCancelPendingCallbacks
0x180021030  mov     rcx, rbp; pti
0x180021033  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180021039  mov     rcx, rbp; pti
0x18002103c  call    cs:__imp_CloseThreadpoolTimer
0x180021042  mov     ecx, ebx; dwErrCode
0x180021044  call    cs:__imp_SetLastError
0x18002104a  mov     [rdi+20h], rsi
0x18002104e  test    rsi, rsi
0x180021051  jnz     short loc_180021095
0x180021053  mov     rcx, [rsp+48h]; this
0x180021058  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\services"...
0x18002105f  lea     edx, [rsi+2Ch]; void *
0x180021062  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021067  jmp     short loc_1800210BA
0x180021069  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002106e  mov     ebx, eax
0x180021070  test    eax, eax
0x180021072  jns     loc_180020FE0
0x180021078  mov     rcx, [rsp+48h]; this
0x18002107d  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\services"...
0x180021084  mov     r9d, eax; char *
0x180021087  mov     edx, 25h ; '%'; void *
0x18002108c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021091  mov     eax, ebx
0x180021093  jmp     short loc_1800210BA
0x180021095  mov     rax, 0FFFFFFFE9A5F4400h
0x18002109f  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800210a4  xor     r9d, r9d; msWindowLength
0x1800210a7  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x1800210ac  xor     r8d, r8d; msPeriod
0x1800210af  mov     rcx, rsi; pti
0x1800210b2  call    cs:__imp_SetThreadpoolTimer
0x1800210b8  xor     eax, eax
0x1800210ba  add     rsp, 28h
0x1800210be  pop     rdi
0x1800210bf  pop     rsi
0x1800210c0  pop     rbp
0x1800210c1  pop     rbx
0x1800210c2  retn
0x1800210c3  mov     rcx, [rsp+48h]; this
0x1800210c8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800210cf  mov     edx, 0A0Bh; void *
0x1800210d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
