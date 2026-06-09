# AutoThreadPriority::SetPriority(int,_IO_PRIORITY_HINT,ulong,bool)

- ea: `0x140024bf4`
- end: `0x140024cf0`
- name: `?SetPriority@AutoThreadPriority@@AEAAXHW4_IO_PRIORITY_HINT@@K_N@Z`
- size: `252`
- prototype: `NTSTATUS __fastcall(__int64, int, int, int, unsigned __int8)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000e550`
- `0x140024cf8`

## callees

- `0x140002310`
- `0x140010d90`
- `0x140024048`
- `0x140024bf4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024c2f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140024c25`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140024c25`
- `ntdll!NtSetInformationThread` at `0x140024c56`
- `ntdll!NtSetInformationThread` at `0x140024c81`
- `ntdll!NtSetInformationThread` at `0x140024cc1`
- `ntdll!NtSetInformationThread` at `0x140024c56`
- `ntdll!NtSetInformationThread` at `0x140024c81`
- `ntdll!NtSetInformationThread` at `0x140024cc1`

## string_xrefs

- `0x140024c37`: `Unable to set thread CPU priority`
- `0x140024c60`: `Unable to set thread I/O priority`
- `0x140024c8b`: `Unable to set thread memory priority`
- `0x140024ccb`: `Unable to set thread throttling state`

## pseudocode

```c
NTSTATUS __fastcall AutoThreadPriority::SetPriority(__int64 a1, int a2, int a3, int a4, unsigned __int8 a5)
{
  void *v6; // rcx
  DWORD LastError; // eax
  __int64 v8; // rcx
  NTSTATUS v9; // eax
  __int64 v10; // rcx
  NTSTATUS v11; // eax
  __int64 v12; // rcx
  void *v13; // rcx
  NTSTATUS result; // eax
  __int64 v15; // rcx
  int ThreadInformation; // [rsp+20h] [rbp-28h] BYREF
  int v17; // [rsp+24h] [rbp-24h] BYREF
  __int64 v18; // [rsp+28h] [rbp-20h] BYREF
  int v19; // [rsp+30h] [rbp-18h]

  ThreadInformation = a3;
  v18 = 0;
  v6 = *(void **)(a1 + 48);
  v19 = 0;
  v17 = a4;
  if ( !SetThreadPriority(v6, a2) )
  {
    LastError = GetLastError();
    LogAdapter::TraceAtLevelWin32<unsigned long,>(v8, LastError, "Unable to set thread CPU priority");
  }
  v9 = NtSetInformationThread(*(HANDLE *)(a1 + 48), ThreadIoPriority, &ThreadInformation, 4u);
  if ( v9 < 0 )
    LogAdapter::TraceAtLevelNtStatus<long,>(v10, (unsigned int)v9, "Unable to set thread I/O priority");
  v11 = NtSetInformationThread(*(HANDLE *)(a1 + 48), ThreadPagePriority, &v17, 4u);
  if ( v11 < 0 )
    LogAdapter::TraceAtLevelNtStatus<long,>(v12, (unsigned int)v11, "Unable to set thread memory priority");
  v13 = *(void **)(a1 + 48);
  LODWORD(v18) = 1;
  HIDWORD(v18) = a5;
  v19 = a5;
  result = NtSetInformationThread(v13, ThreadHideFromDebugger|0x20, &v18, 0xCu);
  if ( result < 0 )
    result = LogAdapter::TraceAtLevelNtStatus<long,>(v15, (unsigned int)result, "Unable to set thread throttling state");
  *(_BYTE *)(a1 + 72) = 1;
  return result;
}

```

## disassembly

```asm
0x140024bf4  push    rbx
0x140024bf6  sub     rsp, 40h
0x140024bfa  mov     rax, cs:__security_cookie
0x140024c01  xor     rax, rsp
0x140024c04  mov     [rsp+48h+var_10], rax
0x140024c09  xor     eax, eax
0x140024c0b  mov     [rsp+48h+ThreadInformation], r8d
0x140024c10  mov     rbx, rcx
0x140024c13  mov     [rsp+48h+var_20], rax
0x140024c18  mov     rcx, [rcx+30h]; hThread
0x140024c1c  mov     [rsp+48h+var_18], eax
0x140024c20  mov     [rsp+48h+var_24], r9d
0x140024c25  call    cs:__imp_SetThreadPriority
0x140024c2b  test    eax, eax
0x140024c2d  jnz     short loc_140024C43
0x140024c2f  call    cs:__imp_GetLastError
0x140024c35  mov     edx, eax
0x140024c37  lea     r8, aUnableToSetThr_0; "Unable to set thread CPU priority"
0x140024c3e  call    ??$TraceAtLevelWin32@K$$V@LogAdapter@@YAXW4LogLevel@0@KQEBD@Z; LogAdapter::TraceAtLevelWin32<ulong,>(LogAdapter::LogLevel,ulong,char const * const)
0x140024c43  mov     rcx, [rbx+30h]; ThreadHandle
0x140024c47  lea     r8, [rsp+48h+ThreadInformation]; ThreadInformation
0x140024c4c  mov     r9d, 4; ThreadInformationLength
0x140024c52  lea     edx, [r9+12h]; ThreadInformationClass
0x140024c56  call    cs:__imp_NtSetInformationThread
0x140024c5c  test    eax, eax
0x140024c5e  jns     short loc_140024C6E
0x140024c60  lea     r8, aUnableToSetThr_2; "Unable to set thread I/O priority"
0x140024c67  mov     edx, eax
0x140024c69  call    ??$TraceAtLevelNtStatus@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelNtStatus<long,>(LogAdapter::LogLevel,long,char const * const)
0x140024c6e  mov     rcx, [rbx+30h]; ThreadHandle
0x140024c72  lea     r8, [rsp+48h+var_24]; ThreadInformation
0x140024c77  mov     r9d, 4; ThreadInformationLength
0x140024c7d  lea     edx, [r9+14h]; ThreadInformationClass
0x140024c81  call    cs:__imp_NtSetInformationThread
0x140024c87  test    eax, eax
0x140024c89  jns     short loc_140024C99
0x140024c8b  lea     r8, aUnableToSetThr; "Unable to set thread memory priority"
0x140024c92  mov     edx, eax
0x140024c94  call    ??$TraceAtLevelNtStatus@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelNtStatus<long,>(LogAdapter::LogLevel,long,char const * const)
0x140024c99  movzx   eax, [rsp+48h+arg_20]
0x140024c9e  lea     r8, [rsp+48h+var_20]; ThreadInformation
0x140024ca3  mov     rcx, [rbx+30h]; ThreadHandle
0x140024ca7  mov     r9d, 0Ch; ThreadInformationLength
0x140024cad  mov     dword ptr [rsp+48h+var_20], 1
0x140024cb5  mov     dword ptr [rsp+48h+var_20+4], eax
0x140024cb9  mov     [rsp+48h+var_18], eax
0x140024cbd  lea     edx, [r9+25h]; ThreadInformationClass
0x140024cc1  call    cs:__imp_NtSetInformationThread
0x140024cc7  test    eax, eax
0x140024cc9  jns     short loc_140024CD9
0x140024ccb  lea     r8, aUnableToSetThr_1; "Unable to set thread throttling state"
0x140024cd2  mov     edx, eax
0x140024cd4  call    ??$TraceAtLevelNtStatus@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelNtStatus<long,>(LogAdapter::LogLevel,long,char const * const)
0x140024cd9  mov     byte ptr [rbx+48h], 1
0x140024cdd  mov     rcx, [rsp+48h+var_10]
0x140024ce2  xor     rcx, rsp; StackCookie
0x140024ce5  call    __security_check_cookie
0x140024cea  add     rsp, 40h
0x140024cee  pop     rbx
0x140024cef  retn
```
