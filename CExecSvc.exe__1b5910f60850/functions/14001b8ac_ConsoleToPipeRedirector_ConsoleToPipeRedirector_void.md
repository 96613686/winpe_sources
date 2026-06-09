# ConsoleToPipeRedirector::~ConsoleToPipeRedirector(void)

- ea: `0x14001b8ac`
- end: `0x14001b97b`
- name: `??1ConsoleToPipeRedirector@@QEAA@XZ`
- size: `207`
- prototype: `void __fastcall(ConsoleToPipeRedirector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400159f4`
- `0x140015b40`

## callees

- `0x14001b8ac`
- `0x14001eb64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001b8df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001b8df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001b8f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001b8f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b948`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b95c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b948`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b95c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001b90e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001b90e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001b925`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001b925`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x14001b8d2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x14001b8d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x14001b934`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x14001b934`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001b91c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001b91c`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x14001b8c6`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x14001b8c6`

## pseudocode

```c
void __fastcall ConsoleToPipeRedirector::~ConsoleToPipeRedirector(ConsoleToPipeRedirector *this)
{
  struct _TP_TIMER *v2; // rdi
  struct _TP_IO *v3; // rcx
  char *v4; // rcx
  char *v5; // rcx

  if ( *((_QWORD *)this + 8) )
  {
    CancelIoEx(*((HANDLE *)this + 6), 0);
    WaitForThreadpoolIoCallbacks(*((PTP_IO *)this + 8), 0);
  }
  AcquireSRWLockExclusive((PSRWLOCK)this + 5);
  *((_DWORD *)this + 3) = 0;
  if ( this != (ConsoleToPipeRedirector *)-40LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 5);
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 9);
  if ( v2 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 9), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
  }
  v3 = (struct _TP_IO *)*((_QWORD *)this + 8);
  if ( v3 )
    CloseThreadpoolIo(v3);
  v4 = (char *)*((_QWORD *)this + 7);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  v5 = (char *)*((_QWORD *)this + 6);
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  if ( *(_QWORD *)this )
    CsCloseConsole(*(PVOID *)this);
}

```

## disassembly

```asm
0x14001b8ac  mov     [rsp+arg_8], rbx
0x14001b8b1  push    rdi
0x14001b8b2  sub     rsp, 20h
0x14001b8b6  mov     rbx, rcx
0x14001b8b9  cmp     qword ptr [rcx+40h], 0
0x14001b8be  jz      short loc_14001B8D8
0x14001b8c0  xor     edx, edx; lpOverlapped
0x14001b8c2  mov     rcx, [rcx+30h]; hFile
0x14001b8c6  call    cs:__imp_CancelIoEx
0x14001b8cc  xor     edx, edx; fCancelPendingCallbacks
0x14001b8ce  mov     rcx, [rbx+40h]; pio
0x14001b8d2  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x14001b8d8  lea     rdi, [rbx+28h]
0x14001b8dc  mov     rcx, rdi; SRWLock
0x14001b8df  call    cs:__imp_AcquireSRWLockExclusive
0x14001b8e5  mov     dword ptr [rbx+0Ch], 0
0x14001b8ec  test    rdi, rdi
0x14001b8ef  jz      short loc_14001B8FA
0x14001b8f1  mov     rcx, rdi; SRWLock
0x14001b8f4  call    cs:__imp_ReleaseSRWLockExclusive
0x14001b8fa  mov     rdi, [rbx+48h]
0x14001b8fe  test    rdi, rdi
0x14001b901  jz      short loc_14001B92B
0x14001b903  xor     r9d, r9d; msWindowLength
0x14001b906  xor     r8d, r8d; msPeriod
0x14001b909  xor     edx, edx; pftDueTime
0x14001b90b  mov     rcx, rdi; pti
0x14001b90e  call    cs:__imp_SetThreadpoolTimer
0x14001b914  mov     edx, 1; fCancelPendingCallbacks
0x14001b919  mov     rcx, rdi; pti
0x14001b91c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14001b922  mov     rcx, rdi; pti
0x14001b925  call    cs:__imp_CloseThreadpoolTimer
0x14001b92b  mov     rcx, [rbx+40h]; pio
0x14001b92f  test    rcx, rcx
0x14001b932  jz      short loc_14001B93A
0x14001b934  call    cs:__imp_CloseThreadpoolIo
0x14001b93a  mov     rcx, [rbx+38h]; hObject
0x14001b93e  lea     rax, [rcx-1]
0x14001b942  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001b946  ja      short loc_14001B94E
0x14001b948  call    cs:__imp_CloseHandle
0x14001b94e  mov     rcx, [rbx+30h]; hObject
0x14001b952  lea     rax, [rcx-1]
0x14001b956  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001b95a  ja      short loc_14001B962
0x14001b95c  call    cs:__imp_CloseHandle
0x14001b962  mov     rcx, [rbx]; P
0x14001b965  test    rcx, rcx
0x14001b968  jz      short loc_14001B970
0x14001b96a  call    CsCloseConsole
0x14001b96f  nop
0x14001b970  mov     rbx, [rsp+28h+arg_8]
0x14001b975  add     rsp, 20h
0x14001b979  pop     rdi
0x14001b97a  retn
```
