# AutoThreadPriority::Initialize(void)

- ea: `0x14002472c`
- end: `0x140024895`
- name: `?Initialize@AutoThreadPriority@@AEAAXXZ`
- size: `361`
- prototype: `void __fastcall(AutoThreadPriority *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400240a4`

## callees

- `0x140002310`
- `0x140006950`
- `0x140006d44`
- `0x140024048`
- `0x14002472c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400247b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400247b5`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1400247dd`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1400247dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002476f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140024781`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002476f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140024781`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140024778`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400247c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140024778`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400247c9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400247ab`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400247ab`
- `ntdll!NtQueryInformationThread` at `0x140024809`
- `ntdll!NtQueryInformationThread` at `0x140024833`
- `ntdll!NtQueryInformationThread` at `0x14002485f`
- `ntdll!NtQueryInformationThread` at `0x140024809`
- `ntdll!NtQueryInformationThread` at `0x140024833`
- `ntdll!NtQueryInformationThread` at `0x14002485f`

## string_xrefs

- `0x1400247bd`: `Failed to duplicate thread handle.`

## pseudocode

```c
void __fastcall AutoThreadPriority::Initialize(AutoThreadPriority *this)
{
  HANDLE *v1; // rsi
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v5; // rax
  DWORD LastError; // eax
  __int64 v7; // rcx
  HANDLE v8; // rax
  int ThreadPriority; // eax
  int ThreadInformation; // [rsp+40h] [rbp-48h] BYREF
  int v11; // [rsp+44h] [rbp-44h] BYREF
  __int64 v12; // [rsp+48h] [rbp-40h] BYREF
  int v13; // [rsp+50h] [rbp-38h]

  ThreadInformation = 2;
  v1 = (HANDLE *)((char *)this + 48);
  v11 = 5;
  v12 = 0;
  v13 = 0;
  if ( *((_QWORD *)this + 6) )
    INTERNAL_ERROR_ACTION(-1073741595);
  CurrentProcess = GetCurrentProcess();
  CurrentThread = GetCurrentThread();
  v5 = GetCurrentProcess();
  if ( !DuplicateHandle(v5, CurrentThread, CurrentProcess, v1, 0, 0, 2u) )
  {
    LastError = GetLastError();
    LogAdapter::TraceAtLevelWin32<unsigned long,>(v7, LastError, "Failed to duplicate thread handle.");
    v8 = GetCurrentThread();
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
      v1,
      v8);
  }
  ThreadPriority = GetThreadPriority(*v1);
  if ( ThreadPriority != 0x7FFFFFFF )
    *((_DWORD *)this + 14) = ThreadPriority;
  if ( NtQueryInformationThread(*v1, ThreadIoPriority, &ThreadInformation, 4u, 0) >= 0 )
    *((_DWORD *)this + 15) = ThreadInformation;
  if ( NtQueryInformationThread(*v1, ThreadPagePriority, &v11, 4u, 0) >= 0 )
    *((_DWORD *)this + 16) = v11;
  if ( NtQueryInformationThread(*v1, ThreadHideFromDebugger|0x20, &v12, 0xCu, 0) >= 0 )
    *((_BYTE *)this + 68) = v13 == 1;
}

```

## disassembly

```asm
0x14002472c  push    rbx
0x14002472e  push    rbp
0x14002472f  push    rsi
0x140024730  push    rdi
0x140024731  sub     rsp, 68h
0x140024735  mov     rax, cs:__security_cookie
0x14002473c  xor     rax, rsp
0x14002473f  mov     [rsp+88h+var_30], rax
0x140024744  xor     eax, eax
0x140024746  mov     [rsp+88h+ThreadInformation], 2
0x14002474e  lea     rsi, [rcx+30h]
0x140024752  mov     [rsp+88h+var_44], 5
0x14002475a  mov     rbp, rcx
0x14002475d  mov     [rsp+88h+var_40], rax
0x140024762  mov     [rsp+88h+var_38], eax
0x140024766  cmp     [rsi], rax
0x140024769  jnz     loc_14002488A
0x14002476f  call    cs:__imp_GetCurrentProcess
0x140024775  mov     rdi, rax
0x140024778  call    cs:__imp_GetCurrentThread
0x14002477e  mov     rbx, rax
0x140024781  call    cs:__imp_GetCurrentProcess
0x140024787  mov     [rsp+88h+dwOptions], 2; dwOptions
0x14002478f  mov     r9, rsi; lpTargetHandle
0x140024792  mov     rcx, rax; hSourceProcessHandle
0x140024795  mov     [rsp+88h+bInheritHandle], 0; bInheritHandle
0x14002479d  mov     r8, rdi; hTargetProcessHandle
0x1400247a0  mov     [rsp+88h+dwDesiredAccess], 0; dwDesiredAccess
0x1400247a8  mov     rdx, rbx; hSourceHandle
0x1400247ab  call    cs:__imp_DuplicateHandle
0x1400247b1  test    eax, eax
0x1400247b3  jnz     short loc_1400247DA
0x1400247b5  call    cs:__imp_GetLastError
0x1400247bb  mov     edx, eax
0x1400247bd  lea     r8, aFailedToDuplic; "Failed to duplicate thread handle."
0x1400247c4  call    ??$TraceAtLevelWin32@K$$V@LogAdapter@@YAXW4LogLevel@0@KQEBD@Z; LogAdapter::TraceAtLevelWin32<ulong,>(LogAdapter::LogLevel,ulong,char const * const)
0x1400247c9  call    cs:__imp_GetCurrentThread
0x1400247cf  mov     rdx, rax
0x1400247d2  mov     rcx, rsi
0x1400247d5  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x1400247da  mov     rcx, [rsi]; hThread
0x1400247dd  call    cs:__imp_GetThreadPriority
0x1400247e3  cmp     eax, 7FFFFFFFh
0x1400247e8  jz      short loc_1400247ED
0x1400247ea  mov     [rbp+38h], eax
0x1400247ed  mov     rcx, [rsi]; ThreadHandle
0x1400247f0  lea     r8, [rsp+88h+ThreadInformation]; ThreadInformation
0x1400247f5  mov     ebx, 4
0x1400247fa  mov     qword ptr [rsp+88h+dwDesiredAccess], 0; ReturnLength
0x140024803  mov     r9d, ebx; ThreadInformationLength
0x140024806  lea     edx, [rbx+12h]; ThreadInformationClass
0x140024809  call    cs:__imp_NtQueryInformationThread
0x14002480f  test    eax, eax
0x140024811  js      short loc_14002481A
0x140024813  mov     eax, [rsp+88h+ThreadInformation]
0x140024817  mov     [rbp+3Ch], eax
0x14002481a  mov     rcx, [rsi]; ThreadHandle
0x14002481d  lea     r8, [rsp+88h+var_44]; ThreadInformation
0x140024822  mov     r9d, ebx; ThreadInformationLength
0x140024825  mov     qword ptr [rsp+88h+dwDesiredAccess], 0; ReturnLength
0x14002482e  mov     edx, 18h; ThreadInformationClass
0x140024833  call    cs:__imp_NtQueryInformationThread
0x140024839  test    eax, eax
0x14002483b  js      short loc_140024844
0x14002483d  mov     eax, [rsp+88h+var_44]
0x140024841  mov     [rbp+40h], eax
0x140024844  mov     rcx, [rsi]; ThreadHandle
0x140024847  lea     r8, [rsp+88h+var_40]; ThreadInformation
0x14002484c  mov     r9d, 0Ch; ThreadInformationLength
0x140024852  mov     qword ptr [rsp+88h+dwDesiredAccess], 0; ReturnLength
0x14002485b  lea     edx, [r9+25h]; ThreadInformationClass
0x14002485f  call    cs:__imp_NtQueryInformationThread
0x140024865  test    eax, eax
0x140024867  js      short loc_140024874
0x140024869  cmp     [rsp+88h+var_38], 1
0x14002486e  setz    al
0x140024871  mov     [rbp+44h], al
0x140024874  mov     rcx, [rsp+88h+var_30]
0x140024879  xor     rcx, rsp; StackCookie
0x14002487c  call    __security_check_cookie
0x140024881  add     rsp, 68h
0x140024885  pop     rdi
0x140024886  pop     rsi
0x140024887  pop     rbp
0x140024888  pop     rbx
0x140024889  retn
0x14002488a  mov     ecx, 0C00000E5h; int
0x14002488f  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
