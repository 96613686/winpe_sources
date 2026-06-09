# AutoThreadPriority::Initialize(void)

- ea: `0x1800470b0`
- end: `0x18004725d`
- name: `?Initialize@AutoThreadPriority@@AEAAXXZ`
- size: `429`
- prototype: `void __fastcall(AutoThreadPriority *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180046870`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x180027fc8`
- `0x1800470b0`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x1800471be`
- `ntdll!NtQueryInformationThread` at `0x1800471ee`
- `ntdll!NtQueryInformationThread` at `0x180047220`
- `ntdll!NtQueryInformationThread` at `0x1800471be`
- `ntdll!NtQueryInformationThread` at `0x1800471ee`
- `ntdll!NtQueryInformationThread` at `0x180047220`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800470f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047111`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800470f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180047111`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180047102`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180047170`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180047102`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180047170`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18004718c`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18004718c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047151`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180047141`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180047141`

## string_xrefs

- `0x18004715d`: `Failed to duplicate thread handle.`

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
    JUMPOUT(0x18004725CLL);
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
0x1800470b0  push    rbx
0x1800470b2  push    rbp
0x1800470b3  push    rsi
0x1800470b4  push    rdi
0x1800470b5  sub     rsp, 68h
0x1800470b9  mov     rax, cs:__security_cookie
0x1800470c0  xor     rax, rsp
0x1800470c3  mov     [rsp+88h+var_30], rax
0x1800470c8  xor     eax, eax
0x1800470ca  mov     [rsp+88h+ThreadInformation], 2
0x1800470d2  lea     rsi, [rcx+30h]
0x1800470d6  mov     [rsp+88h+var_44], 5
0x1800470de  mov     rbp, rcx
0x1800470e1  mov     [rsp+88h+var_40], rax
0x1800470e6  mov     [rsp+88h+var_38], eax
0x1800470ea  cmp     [rsi], rax
0x1800470ed  jnz     loc_180047252
0x1800470f3  call    cs:__imp_GetCurrentProcess
0x1800470fa  nop     dword ptr [rax+rax+00h]
0x1800470ff  mov     rdi, rax
0x180047102  call    cs:__imp_GetCurrentThread
0x180047109  nop     dword ptr [rax+rax+00h]
0x18004710e  mov     rbx, rax
0x180047111  call    cs:__imp_GetCurrentProcess
0x180047118  nop     dword ptr [rax+rax+00h]
0x18004711d  mov     [rsp+88h+dwOptions], 2; dwOptions
0x180047125  mov     r9, rsi; lpTargetHandle
0x180047128  mov     rcx, rax; hSourceProcessHandle
0x18004712b  mov     [rsp+88h+bInheritHandle], 0; bInheritHandle
0x180047133  mov     r8, rdi; hTargetProcessHandle
0x180047136  mov     [rsp+88h+dwDesiredAccess], 0; dwDesiredAccess
0x18004713e  mov     rdx, rbx; hSourceHandle
0x180047141  call    cs:__imp_DuplicateHandle
0x180047148  nop     dword ptr [rax+rax+00h]
0x18004714d  test    eax, eax
0x18004714f  jnz     short loc_180047189
0x180047151  call    cs:__imp_GetLastError
0x180047158  nop     dword ptr [rax+rax+00h]
0x18004715d  lea     r8, aFailedToDuplic_0; "Failed to duplicate thread handle."
0x180047164  mov     ecx, 2
0x180047169  mov     edx, eax
0x18004716b  call    ??$TraceAtLevelWin32@K$$V@LogAdapter@@YAXW4LogLevel@0@KQEBD@Z; LogAdapter::TraceAtLevelWin32<ulong,>(LogAdapter::LogLevel,ulong,char const * const)
0x180047170  call    cs:__imp_GetCurrentThread
0x180047177  nop     dword ptr [rax+rax+00h]
0x18004717c  cmp     qword ptr [rsi], 0
0x180047180  jnz     loc_180047252
0x180047186  mov     [rsi], rax
0x180047189  mov     rcx, [rsi]; hThread
0x18004718c  call    cs:__imp_GetThreadPriority
0x180047193  nop     dword ptr [rax+rax+00h]
0x180047198  cmp     eax, 7FFFFFFFh
0x18004719d  jz      short loc_1800471A2
0x18004719f  mov     [rbp+38h], eax
0x1800471a2  mov     rcx, [rsi]; ThreadHandle
0x1800471a5  lea     r8, [rsp+88h+ThreadInformation]; ThreadInformation
0x1800471aa  mov     ebx, 4
0x1800471af  mov     qword ptr [rsp+88h+dwDesiredAccess], 0; ReturnLength
0x1800471b8  mov     r9d, ebx; ThreadInformationLength
0x1800471bb  lea     edx, [rbx+12h]; ThreadInformationClass
0x1800471be  call    cs:__imp_NtQueryInformationThread
0x1800471c5  nop     dword ptr [rax+rax+00h]
0x1800471ca  test    eax, eax
0x1800471cc  js      short loc_1800471D5
0x1800471ce  mov     eax, [rsp+88h+ThreadInformation]
0x1800471d2  mov     [rbp+3Ch], eax
0x1800471d5  mov     rcx, [rsi]; ThreadHandle
0x1800471d8  lea     r8, [rsp+88h+var_44]; ThreadInformation
0x1800471dd  mov     r9d, ebx; ThreadInformationLength
0x1800471e0  mov     qword ptr [rsp+88h+dwDesiredAccess], 0; ReturnLength
0x1800471e9  mov     edx, 18h; ThreadInformationClass
0x1800471ee  call    cs:__imp_NtQueryInformationThread
0x1800471f5  nop     dword ptr [rax+rax+00h]
0x1800471fa  test    eax, eax
0x1800471fc  js      short loc_180047205
0x1800471fe  mov     eax, [rsp+88h+var_44]
0x180047202  mov     [rbp+40h], eax
0x180047205  mov     rcx, [rsi]; ThreadHandle
0x180047208  lea     r8, [rsp+88h+var_40]; ThreadInformation
0x18004720d  mov     r9d, 0Ch; ThreadInformationLength
0x180047213  mov     qword ptr [rsp+88h+dwDesiredAccess], 0; ReturnLength
0x18004721c  lea     edx, [r9+25h]; ThreadInformationClass
0x180047220  call    cs:__imp_NtQueryInformationThread
0x180047227  nop     dword ptr [rax+rax+00h]
0x18004722c  test    eax, eax
0x18004722e  js      short loc_18004723B
0x180047230  cmp     [rsp+88h+var_38], 1
0x180047235  setz    al
0x180047238  mov     [rbp+44h], al
0x18004723b  mov     rcx, [rsp+88h+var_30]
0x180047240  xor     rcx, rsp; StackCookie
0x180047243  call    __security_check_cookie
0x180047248  add     rsp, 68h
0x18004724c  pop     rdi
0x18004724d  pop     rsi
0x18004724e  pop     rbp
0x18004724f  pop     rbx
0x180047250  retn
0x180047252  mov     ecx, 0C00000E5h; int
0x180047257  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
