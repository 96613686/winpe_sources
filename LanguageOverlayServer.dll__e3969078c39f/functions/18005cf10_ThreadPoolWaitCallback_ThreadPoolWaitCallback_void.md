# ThreadPoolWaitCallback::~ThreadPoolWaitCallback(void)

- ea: `0x18005cf10`
- end: `0x18005cfee`
- name: `??1ThreadPoolWaitCallback@@UEAA@XZ`
- size: `222`
- prototype: `void __fastcall(PTP_WAIT *this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18005d090`

## callees

- `0x18000a008`
- `0x18005cf10`
- `0x18005d0d0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cf3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cf3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005cf5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005cf5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cf75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cf75`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005cf53`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005cfc0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005cf53`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005cfc0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005cf4a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005cfb7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005cf4a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005cfb7`

## string_xrefs

- `0x18005cfdc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall ThreadPoolWaitCallback::~ThreadPoolWaitCallback(PTP_WAIT *this)
{
  __int64 v2; // rdx
  struct _TP_WAIT *v3; // rsi
  DWORD LastError; // ebx
  PTP_WAIT v5; // rcx
  const char *v6; // r9
  PTP_WAIT *v7; // rcx
  struct _TP_WAIT *v8; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *this = (PTP_WAIT)&ThreadPoolWaitCallback::`vftable';
  ThreadPoolWaitCallback::Shutdown((ThreadPoolWaitCallback *)this);
  v3 = this[1];
  if ( v3 )
  {
    LastError = GetLastError();
    WaitForThreadpoolWaitCallbacks(v3, 1);
    CloseThreadpoolWait(v3);
    SetLastError(LastError);
  }
  this[1] = 0;
  v5 = this[20];
  if ( v5 && !CloseHandle(v5) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v6);
  v7 = (PTP_WAIT *)this[9];
  if ( v7 )
  {
    LOBYTE(v2) = v7 != this + 2;
    (*((void (__fastcall **)(PTP_WAIT *, __int64))*v7 + 4))(v7, v2);
    this[9] = 0;
  }
  v8 = this[1];
  if ( v8 )
  {
    WaitForThreadpoolWaitCallbacks(this[1], 1);
    CloseThreadpoolWait(v8);
  }
}

```

## disassembly

```asm
0x18005cf10  mov     [rsp+arg_0], rbx
0x18005cf15  mov     [rsp+arg_8], rsi
0x18005cf1a  push    rdi
0x18005cf1b  sub     rsp, 20h
0x18005cf1f  mov     rdi, rcx
0x18005cf22  lea     rax, ??_7ThreadPoolWaitCallback@@6B@; const ThreadPoolWaitCallback::`vftable'
0x18005cf29  mov     [rcx], rax
0x18005cf2c  call    ?Shutdown@ThreadPoolWaitCallback@@UEAAXXZ; ThreadPoolWaitCallback::Shutdown(void)
0x18005cf31  mov     rsi, [rdi+8]
0x18005cf35  test    rsi, rsi
0x18005cf38  jz      short loc_18005CF61
0x18005cf3a  call    cs:__imp_GetLastError
0x18005cf40  mov     ebx, eax
0x18005cf42  mov     edx, 1; fCancelPendingCallbacks
0x18005cf47  mov     rcx, rsi; pwa
0x18005cf4a  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18005cf50  mov     rcx, rsi; pwa
0x18005cf53  call    cs:__imp_CloseThreadpoolWait
0x18005cf59  mov     ecx, ebx; dwErrCode
0x18005cf5b  call    cs:__imp_SetLastError
0x18005cf61  mov     qword ptr [rdi+8], 0
0x18005cf69  mov     rcx, [rdi+0A0h]; hObject
0x18005cf70  test    rcx, rcx
0x18005cf73  jz      short loc_18005CF7F
0x18005cf75  call    cs:__imp_CloseHandle
0x18005cf7b  test    eax, eax
0x18005cf7d  jz      short loc_18005CFD7
0x18005cf7f  lea     rbx, [rdi+10h]
0x18005cf83  mov     rcx, [rbx+38h]
0x18005cf87  test    rcx, rcx
0x18005cf8a  jz      short loc_18005CFA6
0x18005cf8c  mov     rax, [rcx]
0x18005cf8f  cmp     rcx, rbx
0x18005cf92  setnz   dl
0x18005cf95  mov     rax, [rax+20h]
0x18005cf99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cf9e  mov     qword ptr [rbx+38h], 0
0x18005cfa6  mov     rbx, [rdi+8]
0x18005cfaa  test    rbx, rbx
0x18005cfad  jz      short loc_18005CFC7
0x18005cfaf  mov     edx, 1; fCancelPendingCallbacks
0x18005cfb4  mov     rcx, rbx; pwa
0x18005cfb7  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18005cfbd  mov     rcx, rbx; pwa
0x18005cfc0  call    cs:__imp_CloseThreadpoolWait
0x18005cfc6  nop
0x18005cfc7  mov     rbx, [rsp+28h+arg_0]
0x18005cfcc  mov     rsi, [rsp+28h+arg_8]
0x18005cfd1  add     rsp, 20h
0x18005cfd5  pop     rdi
0x18005cfd6  retn
0x18005cfd7  mov     rcx, [rsp+28h]; this
0x18005cfdc  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005cfe3  mov     edx, 0A0Bh; void *
0x18005cfe8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
