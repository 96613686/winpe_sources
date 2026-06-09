# Container::Manager::Service::CmsService::~CmsService(void)

- ea: `0x180023a28`
- end: `0x180023b60`
- name: `??1CmsService@Service@Manager@Container@@QEAA@XZ`
- size: `312`
- prototype: `void __fastcall(Container::Manager::Service::CmsService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1801b1a30`

## callees

- `0x180016658`
- `0x180023a28`
- `0x180190918`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023a46`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023a46`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023a81`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023aeb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023a81`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023aeb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023a5b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023a5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023a8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023a8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023b2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023b2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ac1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ad6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023b00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ac1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ad6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023b00`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180023b1a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180023b1a`

## pseudocode

```c
void __fastcall Container::Manager::Service::CmsService::~CmsService(PTP_TIMER *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  PTP_TIMER v4; // rcx
  PTP_TIMER v5; // rcx
  struct _TP_TIMER *v6; // rcx
  PTP_TIMER v7; // rcx
  PTP_TIMER v8; // rcx
  PTP_TIMER v9; // rcx
  unsigned int v10; // r8d
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  SetThreadpoolTimer(this[11], 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(this[11], 1);
  v2 = this[11];
  if ( v2 )
  {
    LastError = GetLastError();
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  this[11] = 0;
  Container::Manager::Rpc::Server::~Server((Container::Manager::Rpc::Server *)(this + 18));
  Container::Manager::Rpc::Server::~Server((Container::Manager::Rpc::Server *)(this + 15));
  v4 = this[14];
  if ( v4 )
    LocalFree(v4);
  v5 = this[13];
  if ( v5 )
    LocalFree(v5);
  v6 = this[11];
  if ( v6 )
    CloseThreadpoolTimer(v6);
  v7 = this[9];
  if ( v7 )
    LocalFree(v7);
  v8 = this[8];
  if ( (unsigned __int64)v8 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    UnregisterWait(v8);
  v9 = this[7];
  if ( v9 )
  {
    if ( !CloseHandle(v9) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
  }
}

```

## disassembly

```asm
0x180023a28  mov     [rsp+arg_0], rbx
0x180023a2d  mov     [rsp+arg_8], rsi
0x180023a32  push    rdi
0x180023a33  sub     rsp, 20h
0x180023a37  mov     rdi, rcx
0x180023a3a  xor     r9d, r9d; msWindowLength
0x180023a3d  mov     rcx, [rcx+58h]; pti
0x180023a41  xor     r8d, r8d; msPeriod
0x180023a44  xor     edx, edx; pftDueTime
0x180023a46  call    cs:__imp_SetThreadpoolTimer
0x180023a4d  nop     dword ptr [rax+rax+00h]
0x180023a52  mov     rcx, [rdi+58h]; pti
0x180023a56  mov     edx, 1; fCancelPendingCallbacks
0x180023a5b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180023a62  nop     dword ptr [rax+rax+00h]
0x180023a67  mov     rsi, [rdi+58h]
0x180023a6b  test    rsi, rsi
0x180023a6e  jz      short loc_180023A9B
0x180023a70  call    cs:__imp_GetLastError
0x180023a77  nop     dword ptr [rax+rax+00h]
0x180023a7c  mov     rcx, rsi; pti
0x180023a7f  mov     ebx, eax
0x180023a81  call    cs:__imp_CloseThreadpoolTimer
0x180023a88  nop     dword ptr [rax+rax+00h]
0x180023a8d  mov     ecx, ebx; dwErrCode
0x180023a8f  call    cs:__imp_SetLastError
0x180023a96  nop     dword ptr [rax+rax+00h]
0x180023a9b  lea     rcx, [rdi+90h]; this
0x180023aa2  mov     qword ptr [rdi+58h], 0
0x180023aaa  call    ??1Server@Rpc@Manager@Container@@QEAA@XZ; Container::Manager::Rpc::Server::~Server(void)
0x180023aaf  lea     rcx, [rdi+78h]; this
0x180023ab3  call    ??1Server@Rpc@Manager@Container@@QEAA@XZ; Container::Manager::Rpc::Server::~Server(void)
0x180023ab8  mov     rcx, [rdi+70h]; hMem
0x180023abc  test    rcx, rcx
0x180023abf  jz      short loc_180023ACD
0x180023ac1  call    cs:__imp_LocalFree
0x180023ac8  nop     dword ptr [rax+rax+00h]
0x180023acd  mov     rcx, [rdi+68h]; hMem
0x180023ad1  test    rcx, rcx
0x180023ad4  jz      short loc_180023AE2
0x180023ad6  call    cs:__imp_LocalFree
0x180023add  nop     dword ptr [rax+rax+00h]
0x180023ae2  mov     rcx, [rdi+58h]; pti
0x180023ae6  test    rcx, rcx
0x180023ae9  jz      short loc_180023AF7
0x180023aeb  call    cs:__imp_CloseThreadpoolTimer
0x180023af2  nop     dword ptr [rax+rax+00h]
0x180023af7  mov     rcx, [rdi+48h]; hMem
0x180023afb  test    rcx, rcx
0x180023afe  jz      short loc_180023B0C
0x180023b00  call    cs:__imp_LocalFree
0x180023b07  nop     dword ptr [rax+rax+00h]
0x180023b0c  mov     rcx, [rdi+40h]; WaitHandle
0x180023b10  lea     rax, [rcx-1]
0x180023b14  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023b18  ja      short loc_180023B26
0x180023b1a  call    cs:__imp_UnregisterWait
0x180023b21  nop     dword ptr [rax+rax+00h]
0x180023b26  mov     rcx, [rdi+38h]; hObject
0x180023b2a  test    rcx, rcx
0x180023b2d  jz      short loc_180023B3F
0x180023b2f  call    cs:__imp_CloseHandle
0x180023b36  nop     dword ptr [rax+rax+00h]
0x180023b3b  test    eax, eax
0x180023b3d  jz      short loc_180023B50
0x180023b3f  mov     rbx, [rsp+28h+arg_0]
0x180023b44  mov     rsi, [rsp+28h+arg_8]
0x180023b49  add     rsp, 20h
0x180023b4d  pop     rdi
0x180023b4e  retn
0x180023b50  mov     rcx, [rsp+28h]; this
0x180023b55  mov     edx, 0A0Bh; void *
0x180023b5a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
