# AutoThreadPriority::Initialize(void)

- ea: `0x1801502cc`
- end: `0x180150479`
- name: `?Initialize@AutoThreadPriority@@AEAAXXZ`
- size: `429`
- prototype: `void __fastcall(AutoThreadPriority *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18015018c`

## callees

- `0x1800059d0`
- `0x18001255c`
- `0x1800692fc`
- `0x1801502cc`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x1801503da`
- `ntdll!NtQueryInformationThread` at `0x18015040a`
- `ntdll!NtQueryInformationThread` at `0x18015043c`
- `ntdll!NtQueryInformationThread` at `0x1801503da`
- `ntdll!NtQueryInformationThread` at `0x18015040a`
- `ntdll!NtQueryInformationThread` at `0x18015043c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015036d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015036d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18015030f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18015032d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18015030f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18015032d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18015031e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18015038c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18015031e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18015038c`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1801503a8`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1801503a8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18015035d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18015035d`

## string_xrefs

- `0x180150379`: `Failed to duplicate thread handle.`

## pseudocode

```c
void __fastcall AutoThreadPriority::Initialize(AutoThreadPriority *this)
{
  HANDLE *v1; // rsi
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v5; // rax
  DWORD LastError; // eax
  HANDLE v7; // rax
  int ThreadPriority; // eax
  int ThreadInformation; // [rsp+40h] [rbp-48h] BYREF
  int v10; // [rsp+44h] [rbp-44h] BYREF
  __int64 v11; // [rsp+48h] [rbp-40h] BYREF
  int v12; // [rsp+50h] [rbp-38h]

  ThreadInformation = 2;
  v1 = (HANDLE *)((char *)this + 48);
  v10 = 5;
  v11 = 0;
  v12 = 0;
  if ( *((_QWORD *)this + 6) )
    goto LABEL_14;
  CurrentProcess = GetCurrentProcess();
  CurrentThread = GetCurrentThread();
  v5 = GetCurrentProcess();
  if ( DuplicateHandle(v5, CurrentThread, CurrentProcess, v1, 0, 0, 2u) )
    goto LABEL_5;
  LastError = GetLastError();
  LogAdapter::TraceAtLevelWin32<unsigned long,>(2, LastError, "Failed to duplicate thread handle.");
  v7 = GetCurrentThread();
  if ( *v1 )
  {
LABEL_14:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x180150478LL);
  }
  *v1 = v7;
LABEL_5:
  ThreadPriority = GetThreadPriority(*v1);
  if ( ThreadPriority != 0x7FFFFFFF )
    *((_DWORD *)this + 14) = ThreadPriority;
  if ( NtQueryInformationThread(*v1, ThreadIoPriority, &ThreadInformation, 4u, 0) >= 0 )
    *((_DWORD *)this + 15) = ThreadInformation;
  if ( NtQueryInformationThread(*v1, ThreadPagePriority, &v10, 4u, 0) >= 0 )
    *((_DWORD *)this + 16) = v10;
  if ( NtQueryInformationThread(*v1, ThreadHideFromDebugger|0x20, &v11, 0xCu, 0) >= 0 )
    *((_BYTE *)this + 68) = v12 == 1;
}

```

## disassembly

```asm
0x1801502cc  push    rbx
0x1801502ce  push    rbp
0x1801502cf  push    rsi
0x1801502d0  push    rdi
0x1801502d1  sub     rsp, 68h
0x1801502d5  mov     rax, cs:__security_cookie
0x1801502dc  xor     rax, rsp
0x1801502df  mov     [rsp+88h+var_30], rax
0x1801502e4  xor     eax, eax
0x1801502e6  mov     [rsp+88h+ThreadInformation], 2
0x1801502ee  lea     rsi, [rcx+30h]
0x1801502f2  mov     [rsp+88h+var_44], 5
0x1801502fa  mov     rbp, rcx
0x1801502fd  mov     [rsp+88h+var_40], rax
0x180150302  mov     [rsp+88h+var_38], eax
0x180150306  cmp     [rsi], rax
0x180150309  jnz     loc_18015046E
0x18015030f  call    cs:__imp_GetCurrentProcess
0x180150316  nop     dword ptr [rax+rax+00h]
0x18015031b  mov     rdi, rax
0x18015031e  call    cs:__imp_GetCurrentThread
0x180150325  nop     dword ptr [rax+rax+00h]
0x18015032a  mov     rbx, rax
0x18015032d  call    cs:__imp_GetCurrentProcess
0x180150334  nop     dword ptr [rax+rax+00h]
0x180150339  mov     [rsp+88h+dwOptions], 2; dwOptions
0x180150341  mov     r9, rsi; lpTargetHandle
0x180150344  mov     rcx, rax; hSourceProcessHandle
0x180150347  mov     [rsp+88h+bInheritHandle], 0; bInheritHandle
0x18015034f  mov     r8, rdi; hTargetProcessHandle
0x180150352  mov     [rsp+88h+dwDesiredAccess], 0; dwDesiredAccess
0x18015035a  mov     rdx, rbx; hSourceHandle
0x18015035d  call    cs:__imp_DuplicateHandle
0x180150364  nop     dword ptr [rax+rax+00h]
0x180150369  test    eax, eax
0x18015036b  jnz     short loc_1801503A5
0x18015036d  call    cs:__imp_GetLastError
0x180150374  nop     dword ptr [rax+rax+00h]
0x180150379  lea     r8, aFailedToDuplic_0; "Failed to duplicate thread handle."
0x180150380  mov     ecx, 2
0x180150385  mov     edx, eax
0x180150387  call    ??$TraceAtLevelWin32@K$$V@LogAdapter@@YAXW4LogLevel@0@KQEBD@Z; LogAdapter::TraceAtLevelWin32<ulong,>(LogAdapter::LogLevel,ulong,char const * const)
0x18015038c  call    cs:__imp_GetCurrentThread
0x180150393  nop     dword ptr [rax+rax+00h]
0x180150398  cmp     qword ptr [rsi], 0
0x18015039c  jnz     loc_18015046E
0x1801503a2  mov     [rsi], rax
0x1801503a5  mov     rcx, [rsi]; hThread
0x1801503a8  call    cs:__imp_GetThreadPriority
0x1801503af  nop     dword ptr [rax+rax+00h]
0x1801503b4  cmp     eax, 7FFFFFFFh
0x1801503b9  jz      short loc_1801503BE
0x1801503bb  mov     [rbp+38h], eax
0x1801503be  mov     rcx, [rsi]; ThreadHandle
0x1801503c1  lea     r8, [rsp+88h+ThreadInformation]; ThreadInformation
0x1801503c6  mov     ebx, 4
0x1801503cb  mov     qword ptr [rsp+88h+dwDesiredAccess], 0; ReturnLength
0x1801503d4  mov     r9d, ebx; ThreadInformationLength
0x1801503d7  lea     edx, [rbx+12h]; ThreadInformationClass
0x1801503da  call    cs:__imp_NtQueryInformationThread
0x1801503e1  nop     dword ptr [rax+rax+00h]
0x1801503e6  test    eax, eax
0x1801503e8  js      short loc_1801503F1
0x1801503ea  mov     eax, [rsp+88h+ThreadInformation]
0x1801503ee  mov     [rbp+3Ch], eax
0x1801503f1  mov     rcx, [rsi]; ThreadHandle
0x1801503f4  lea     r8, [rsp+88h+var_44]; ThreadInformation
0x1801503f9  mov     r9d, ebx; ThreadInformationLength
0x1801503fc  mov     qword ptr [rsp+88h+dwDesiredAccess], 0; ReturnLength
0x180150405  mov     edx, 18h; ThreadInformationClass
0x18015040a  call    cs:__imp_NtQueryInformationThread
0x180150411  nop     dword ptr [rax+rax+00h]
0x180150416  test    eax, eax
0x180150418  js      short loc_180150421
0x18015041a  mov     eax, [rsp+88h+var_44]
0x18015041e  mov     [rbp+40h], eax
0x180150421  mov     rcx, [rsi]; ThreadHandle
0x180150424  lea     r8, [rsp+88h+var_40]; ThreadInformation
0x180150429  mov     r9d, 0Ch; ThreadInformationLength
0x18015042f  mov     qword ptr [rsp+88h+dwDesiredAccess], 0; ReturnLength
0x180150438  lea     edx, [r9+25h]; ThreadInformationClass
0x18015043c  call    cs:__imp_NtQueryInformationThread
0x180150443  nop     dword ptr [rax+rax+00h]
0x180150448  test    eax, eax
0x18015044a  js      short loc_180150457
0x18015044c  cmp     [rsp+88h+var_38], 1
0x180150451  setz    al
0x180150454  mov     [rbp+44h], al
0x180150457  mov     rcx, [rsp+88h+var_30]
0x18015045c  xor     rcx, rsp; StackCookie
0x18015045f  call    __security_check_cookie
0x180150464  add     rsp, 68h
0x180150468  pop     rdi
0x180150469  pop     rsi
0x18015046a  pop     rbp
0x18015046b  pop     rbx
0x18015046c  retn
0x18015046e  mov     ecx, 0C00000E5h; int
0x180150473  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
