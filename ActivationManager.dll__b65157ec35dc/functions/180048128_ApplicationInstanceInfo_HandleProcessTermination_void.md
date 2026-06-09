# ApplicationInstanceInfo::HandleProcessTermination(void)

- ea: `0x180048128`
- end: `0x180048267`
- name: `?HandleProcessTermination@ApplicationInstanceInfo@@QEAAXXZ`
- size: `319`
- prototype: `void __fastcall(ApplicationInstanceInfo *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180089490`

## callees

- `0x180015b7c`
- `0x180048128`
- `0x180048270`
- `0x1800482a0`
- `0x180048324`
- `0x1800894e8`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048167`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048167`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180048147`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180048147`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180048188`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180048188`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800481ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048221`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004824c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800481ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048221`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004824c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800481c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800481c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ApplicationInstanceInfo::HandleProcessTermination(ApplicationInstanceInfo *this)
{
  RTL_SRWLOCK *v2; // rbx
  void *v3; // rdx
  void *v4; // rdx
  void *v5; // rdx
  unsigned int v6; // r8d
  const char *v7; // r9
  HSTRING v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rsi
  __int64 v11; // rdi
  int v12; // ebx
  __int64 v13; // rcx
  int v14; // ebx
  HSTRING string; // [rsp+20h] [rbp-50h] BYREF
  char v16; // [rsp+28h] [rbp-48h]
  __int64 v17; // [rsp+30h] [rbp-40h] BYREF
  HSTRING v18; // [rsp+38h] [rbp-38h]
  char v19; // [rsp+40h] [rbp-30h]
  int v20; // [rsp+48h] [rbp-28h]
  __int64 v21; // [rsp+50h] [rbp-20h]
  __int64 v22; // [rsp+58h] [rbp-18h]
  DWORD v23; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  DWORD ExitCode; // [rsp+90h] [rbp+20h] BYREF

  v2 = (RTL_SRWLOCK *)((char *)this + 16);
  AcquireSRWLockExclusive((PSRWLOCK)this + 2);
  wil::details::SetEvent(*((wil::details **)this + 15), v3);
  wil::details::SetEvent(*((wil::details **)this + 14), v4);
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  string = 0;
  v16 = 0;
  ExitCode = 0;
  if ( !GetExitCodeProcess(*((HANDLE *)this + 5), &ExitCode) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, v5, v6, v7);
  v8 = (HSTRING)*((_QWORD *)this + 9);
  WindowsDeleteString(string);
  string = 0;
  if ( WindowsDuplicateString(v8, &string) < 0 )
    goto LABEL_9;
  v10 = *((_QWORD *)this + 6);
  v11 = *((_QWORD *)this + 8);
  v12 = *((_DWORD *)this + 8);
  v17 = *((_QWORD *)this + 3);
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v17);
  v18 = string;
  string = 0;
  v19 = 0;
  v16 = 1;
  v20 = v12;
  v21 = v11;
  v22 = v10;
  v23 = ExitCode;
  v14 = Windows::Internal::ComTaskPool::QueueTask__lambda_bfe6e38d22b62187f3e8ec3d248faac3___(v13, &v17);
  WindowsDeleteString(v18);
  v9 = v17;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v14 < 0 )
LABEL_9:
    MicrosoftTelemetryAssertTriggeredNoArgs(v9);
  WindowsDeleteString(string);
}

```

## disassembly

```asm
0x180048128  mov     [rsp-18h+arg_8], rbx
0x18004812d  mov     [rsp-18h+arg_10], rsi
0x180048132  push    rbp
0x180048133  push    rdi
0x180048134  push    r14
0x180048136  mov     rbp, rsp
0x180048139  sub     rsp, 70h
0x18004813d  mov     r14, rcx
0x180048140  lea     rbx, [rcx+10h]
0x180048144  mov     rcx, rbx; SRWLock
0x180048147  call    cs:__imp_AcquireSRWLockExclusive
0x18004814d  mov     rcx, [r14+78h]; this
0x180048151  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180048156  mov     rcx, [r14+70h]; this
0x18004815a  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18004815f  test    rbx, rbx
0x180048162  jz      short loc_18004816D
0x180048164  mov     rcx, rbx; SRWLock
0x180048167  call    cs:__imp_ReleaseSRWLockExclusive
0x18004816d  mov     [rbp+string], 0
0x180048175  mov     [rbp+var_48], 0
0x180048179  mov     [rbp+ExitCode], 0
0x180048180  lea     rdx, [rbp+ExitCode]; lpExitCode
0x180048184  mov     rcx, [r14+28h]; hProcess
0x180048188  call    cs:__imp_GetExitCodeProcess
0x18004818e  mov     rcx, [rbp+18h]; this
0x180048192  test    eax, eax
0x180048194  jnz     short loc_18004819B
0x180048196  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18004819b  mov     rbx, [r14+48h]
0x18004819f  mov     rcx, [rbp+string]; string
0x1800481a3  test    rbx, rbx
0x1800481a6  jz      short loc_1800481AD
0x1800481a8  cmp     rbx, rcx
0x1800481ab  jz      short loc_1800481CC
0x1800481ad  call    cs:__imp_WindowsDeleteString
0x1800481b3  mov     [rbp+string], 0
0x1800481bb  lea     rdx, [rbp+string]; newString
0x1800481bf  mov     rcx, rbx; string
0x1800481c2  call    cs:__imp_WindowsDuplicateString
0x1800481c8  test    eax, eax
0x1800481ca  js      short loc_180048242
0x1800481cc  mov     rsi, [r14+30h]
0x1800481d0  mov     rdi, [r14+40h]
0x1800481d4  mov     ebx, [r14+20h]
0x1800481d8  mov     rax, [r14+18h]
0x1800481dc  mov     [rbp+var_40], rax
0x1800481e0  lea     rcx, [rbp+var_40]
0x1800481e4  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800481e9  mov     rax, [rbp+string]
0x1800481ed  mov     [rbp+var_38], rax
0x1800481f1  mov     [rbp+string], 0
0x1800481f9  mov     [rbp+var_30], 0
0x1800481fd  mov     [rbp+var_48], 1
0x180048201  mov     [rbp+var_28], ebx
0x180048204  mov     [rbp+var_20], rdi
0x180048208  mov     [rbp+var_18], rsi
0x18004820c  mov     eax, [rbp+ExitCode]
0x18004820f  mov     [rbp+var_10], eax
0x180048212  lea     rdx, [rbp+var_40]
0x180048216  call    Windows__Internal__ComTaskPool__QueueTask__lambda_bfe6e38d22b62187f3e8ec3d248faac3___
0x18004821b  mov     ebx, eax
0x18004821d  mov     rcx, [rbp+var_38]; string
0x180048221  call    cs:__imp_WindowsDeleteString
0x180048227  nop
0x180048228  mov     rcx, [rbp+var_40]
0x18004822c  test    rcx, rcx
0x18004822f  jz      short loc_18004823E
0x180048231  mov     rdx, [rcx]
0x180048234  mov     rax, [rdx+10h]
0x180048238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004823d  nop
0x18004823e  test    ebx, ebx
0x180048240  jns     short loc_180048248
0x180048242  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180048247  nop
0x180048248  mov     rcx, [rbp+string]; string
0x18004824c  call    cs:__imp_WindowsDeleteString
0x180048252  lea     r11, [rsp+70h+var_s0]
0x180048257  mov     rbx, [r11+28h]
0x18004825b  mov     rsi, [r11+30h]
0x18004825f  mov     rsp, r11
0x180048262  pop     r14
0x180048264  pop     rdi
0x180048265  pop     rbp
0x180048266  retn
```
