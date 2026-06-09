# AutoThreadPriority::SetPlatformPriority(AutoThreadPriority::PlatformPriority const &)

- ea: `0x18004769c`
- end: `0x1800477c6`
- name: `?SetPlatformPriority@AutoThreadPriority@@QEAAXAEBUPlatformPriority@1@@Z`
- size: `298`
- prototype: `void __fastcall(AutoThreadPriority *__hidden this, const struct AutoThreadPriority::PlatformPriority *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800477cc`

## callees

- `0x1800031d0`
- `0x180027fc8`
- `0x18002a9f8`
- `0x18004769c`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18004771d`
- `ntdll!NtSetInformationThread` at `0x18004774a`
- `ntdll!NtSetInformationThread` at `0x18004778f`
- `ntdll!NtSetInformationThread` at `0x18004771d`
- `ntdll!NtSetInformationThread` at `0x18004774a`
- `ntdll!NtSetInformationThread` at `0x18004778f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800476db`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800476db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800476eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800476eb`

## string_xrefs

- `0x18004772b`: `Unable to set thread I/O priority`
- `0x180047758`: `Unable to set thread memory priority`
- `0x1800476f7`: `Unable to set thread CPU priority`
- `0x18004779d`: `Unable to set thread throttling state`

## pseudocode

```c
void __fastcall AutoThreadPriority::SetPlatformPriority(
        AutoThreadPriority *this,
        const struct AutoThreadPriority::PlatformPriority *a2)
{
  char v2; // di
  void *v4; // rcx
  int v5; // eax
  int v6; // edx
  DWORD LastError; // eax
  unsigned int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // rcx
  void *v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // rcx
  int ThreadInformation; // [rsp+20h] [rbp-28h] BYREF
  int v16; // [rsp+24h] [rbp-24h] BYREF
  __int64 v17; // [rsp+28h] [rbp-20h] BYREF
  int v18; // [rsp+30h] [rbp-18h]

  v2 = *((_BYTE *)a2 + 12);
  v17 = 0;
  v4 = (void *)*((_QWORD *)this + 6);
  v18 = 0;
  ThreadInformation = *((_DWORD *)a2 + 1);
  v5 = *((_DWORD *)a2 + 2);
  v6 = *(_DWORD *)a2;
  v16 = v5;
  if ( !SetThreadPriority(v4, v6) )
  {
    LastError = GetLastError();
    LogAdapter::TraceAtLevelWin32<unsigned long,>(2, LastError, "Unable to set thread CPU priority");
  }
  v8 = NtSetInformationThread(*((HANDLE *)this + 6), ThreadIoPriority, &ThreadInformation, 4u);
  LogAdapter::TraceAtLevelIfNtStatusFailed<long,>(v9, v8, "Unable to set thread I/O priority");
  v10 = NtSetInformationThread(*((HANDLE *)this + 6), ThreadPagePriority, &v16, 4u);
  LogAdapter::TraceAtLevelIfNtStatusFailed<long,>(v11, v10, "Unable to set thread memory priority");
  v12 = (void *)*((_QWORD *)this + 6);
  LODWORD(v17) = 1;
  HIDWORD(v17) = v2 != 0;
  v18 = HIDWORD(v17);
  v13 = NtSetInformationThread(v12, ThreadHideFromDebugger|0x20, &v17, 0xCu);
  LogAdapter::TraceAtLevelIfNtStatusFailed<long,>(v14, v13, "Unable to set thread throttling state");
  *((_BYTE *)this + 72) = 1;
}

```

## disassembly

```asm
0x18004769c  mov     [rsp+arg_10], rbx
0x1800476a1  push    rdi
0x1800476a2  sub     rsp, 40h
0x1800476a6  mov     rax, cs:__security_cookie
0x1800476ad  xor     rax, rsp
0x1800476b0  mov     [rsp+48h+var_10], rax
0x1800476b5  mov     dil, [rdx+0Ch]
0x1800476b9  xor     eax, eax
0x1800476bb  mov     [rsp+48h+var_20], rax
0x1800476c0  mov     rbx, rcx
0x1800476c3  mov     rcx, [rcx+30h]; hThread
0x1800476c7  mov     [rsp+48h+var_18], eax
0x1800476cb  mov     eax, [rdx+4]
0x1800476ce  mov     [rsp+48h+ThreadInformation], eax
0x1800476d2  mov     eax, [rdx+8]
0x1800476d5  mov     edx, [rdx]; nPriority
0x1800476d7  mov     [rsp+48h+var_24], eax
0x1800476db  call    cs:__imp_SetThreadPriority
0x1800476e2  nop     dword ptr [rax+rax+00h]
0x1800476e7  test    eax, eax
0x1800476e9  jnz     short loc_18004770A
0x1800476eb  call    cs:__imp_GetLastError
0x1800476f2  nop     dword ptr [rax+rax+00h]
0x1800476f7  lea     r8, aUnableToSetThr_0; "Unable to set thread CPU priority"
0x1800476fe  mov     ecx, 2
0x180047703  mov     edx, eax
0x180047705  call    ??$TraceAtLevelWin32@K$$V@LogAdapter@@YAXW4LogLevel@0@KQEBD@Z; LogAdapter::TraceAtLevelWin32<ulong,>(LogAdapter::LogLevel,ulong,char const * const)
0x18004770a  mov     rcx, [rbx+30h]; ThreadHandle
0x18004770e  lea     r8, [rsp+48h+ThreadInformation]; ThreadInformation
0x180047713  mov     r9d, 4; ThreadInformationLength
0x180047719  lea     edx, [r9+12h]; ThreadInformationClass
0x18004771d  call    cs:__imp_NtSetInformationThread
0x180047724  nop     dword ptr [rax+rax+00h]
0x180047729  mov     edx, eax
0x18004772b  lea     r8, aUnableToSetThr_2; "Unable to set thread I/O priority"
0x180047732  call    ??$TraceAtLevelIfNtStatusFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfNtStatusFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x180047737  mov     rcx, [rbx+30h]; ThreadHandle
0x18004773b  lea     r8, [rsp+48h+var_24]; ThreadInformation
0x180047740  mov     r9d, 4; ThreadInformationLength
0x180047746  lea     edx, [r9+14h]; ThreadInformationClass
0x18004774a  call    cs:__imp_NtSetInformationThread
0x180047751  nop     dword ptr [rax+rax+00h]
0x180047756  mov     edx, eax
0x180047758  lea     r8, aUnableToSetThr; "Unable to set thread memory priority"
0x18004775f  call    ??$TraceAtLevelIfNtStatusFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfNtStatusFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x180047764  mov     rcx, [rbx+30h]; ThreadHandle
0x180047768  lea     r8, [rsp+48h+var_20]; ThreadInformation
0x18004776d  xor     eax, eax
0x18004776f  mov     dword ptr [rsp+48h+var_20], 1
0x180047777  mov     r9d, 0Ch; ThreadInformationLength
0x18004777d  test    dil, dil
0x180047780  setnz   al
0x180047783  mov     dword ptr [rsp+48h+var_20+4], eax
0x180047787  lea     edx, [r9+25h]; ThreadInformationClass
0x18004778b  mov     [rsp+48h+var_18], eax
0x18004778f  call    cs:__imp_NtSetInformationThread
0x180047796  nop     dword ptr [rax+rax+00h]
0x18004779b  mov     edx, eax
0x18004779d  lea     r8, aUnableToSetThr_1; "Unable to set thread throttling state"
0x1800477a4  call    ??$TraceAtLevelIfNtStatusFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfNtStatusFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800477a9  mov     byte ptr [rbx+48h], 1
0x1800477ad  mov     rcx, [rsp+48h+var_10]
0x1800477b2  xor     rcx, rsp; StackCookie
0x1800477b5  call    __security_check_cookie
0x1800477ba  mov     rbx, [rsp+48h+arg_10]
0x1800477bf  add     rsp, 40h
0x1800477c3  pop     rdi
0x1800477c4  retn
```
