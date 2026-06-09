# AutoThreadPriority::SetPriority(int,_IO_PRIORITY_HINT,ulong,bool)

- ea: `0x18010fcf4`
- end: `0x18010fe07`
- name: `?SetPriority@AutoThreadPriority@@AEAAXHW4_IO_PRIORITY_HINT@@K_N@Z`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18009f7a4`

## callees

- `0x1800eb920`
- `0x1800f8580`
- `0x180107778`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18010fd25`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18010fd25`
- `ntdll!NtSetInformationThread` at `0x18010fd57`
- `ntdll!NtSetInformationThread` at `0x18010fd89`
- `ntdll!NtSetInformationThread` at `0x18010fdd0`
- `ntdll!NtSetInformationThread` at `0x18010fd57`
- `ntdll!NtSetInformationThread` at `0x18010fd89`
- `ntdll!NtSetInformationThread` at `0x18010fdd0`

## string_xrefs

- `0x18010fd31`: `Unable to set thread CPU priority`
- `0x18010fddc`: `Unable to set thread throttling state`
- `0x18010fd95`: `Unable to set thread memory priority`
- `0x18010fd63`: `Unable to set thread I/O priority`

## pseudocode

```c
__int64 __fastcall AutoThreadPriority::SetPriority(__int64 a1, int a2, int a3, int a4, unsigned __int8 a5)
{
  void *v6; // rcx
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  void *v10; // rcx
  unsigned int v11; // eax
  __int64 result; // rax
  int ThreadInformation; // [rsp+20h] [rbp-28h] BYREF
  int v14; // [rsp+24h] [rbp-24h] BYREF
  __int64 v15; // [rsp+28h] [rbp-20h] BYREF
  int v16; // [rsp+30h] [rbp-18h]

  ThreadInformation = a3;
  v15 = 0;
  v6 = *(void **)(a1 + 48);
  v16 = 0;
  v14 = a4;
  v7 = SetThreadPriority(v6, a2);
  LogAdapter::TraceAtLevelIfWin32BoolFalse<>(2, v7, "Unable to set thread CPU priority");
  v8 = NtSetInformationThread(*(HANDLE *)(a1 + 48), ThreadIoPriority, &ThreadInformation, 4u);
  LogAdapter::TraceAtLevelIfNtStatusFailed<long,>(2, v8, "Unable to set thread I/O priority");
  v9 = NtSetInformationThread(*(HANDLE *)(a1 + 48), ThreadPagePriority, &v14, 4u);
  LogAdapter::TraceAtLevelIfNtStatusFailed<long,>(2, v9, "Unable to set thread memory priority");
  v10 = *(void **)(a1 + 48);
  LODWORD(v15) = 1;
  HIDWORD(v15) = a5;
  v16 = a5;
  v11 = NtSetInformationThread(v10, ThreadHideFromDebugger|0x20, &v15, 0xCu);
  result = LogAdapter::TraceAtLevelIfNtStatusFailed<long,>(2, v11, "Unable to set thread throttling state");
  *(_BYTE *)(a1 + 72) = 1;
  return result;
}

```

## disassembly

```asm
0x18010fcf4  push    rbx
0x18010fcf6  sub     rsp, 40h
0x18010fcfa  mov     rax, cs:__security_cookie
0x18010fd01  xor     rax, rsp
0x18010fd04  mov     [rsp+48h+var_10], rax
0x18010fd09  xor     eax, eax
0x18010fd0b  mov     [rsp+48h+ThreadInformation], r8d
0x18010fd10  mov     rbx, rcx
0x18010fd13  mov     [rsp+48h+var_20], rax
0x18010fd18  mov     rcx, [rcx+30h]; hThread
0x18010fd1c  mov     [rsp+48h+var_18], eax
0x18010fd20  mov     [rsp+48h+var_24], r9d
0x18010fd25  call    cs:__imp_SetThreadPriority
0x18010fd2c  nop     dword ptr [rax+rax+00h]
0x18010fd31  lea     r8, aUnableToSetThr_1; "Unable to set thread CPU priority"
0x18010fd38  mov     ecx, 2
0x18010fd3d  mov     edx, eax
0x18010fd3f  call    ??$TraceAtLevelIfWin32BoolFalse@$$V@LogAdapter@@YAXW4LogLevel@0@HQEBD@Z; LogAdapter::TraceAtLevelIfWin32BoolFalse<>(LogAdapter::LogLevel,int,char const * const)
0x18010fd44  mov     rcx, [rbx+30h]; ThreadHandle
0x18010fd48  lea     r8, [rsp+48h+ThreadInformation]; ThreadInformation
0x18010fd4d  mov     r9d, 4; ThreadInformationLength
0x18010fd53  lea     edx, [r9+12h]; ThreadInformationClass
0x18010fd57  call    cs:__imp_NtSetInformationThread
0x18010fd5e  nop     dword ptr [rax+rax+00h]
0x18010fd63  lea     r8, aUnableToSetThr_3; "Unable to set thread I/O priority"
0x18010fd6a  mov     ecx, 2
0x18010fd6f  mov     edx, eax
0x18010fd71  call    ??$TraceAtLevelIfNtStatusFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfNtStatusFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x18010fd76  mov     rcx, [rbx+30h]; ThreadHandle
0x18010fd7a  lea     r8, [rsp+48h+var_24]; ThreadInformation
0x18010fd7f  mov     r9d, 4; ThreadInformationLength
0x18010fd85  lea     edx, [r9+14h]; ThreadInformationClass
0x18010fd89  call    cs:__imp_NtSetInformationThread
0x18010fd90  nop     dword ptr [rax+rax+00h]
0x18010fd95  lea     r8, aUnableToSetThr_0; "Unable to set thread memory priority"
0x18010fd9c  mov     ecx, 2
0x18010fda1  mov     edx, eax
0x18010fda3  call    ??$TraceAtLevelIfNtStatusFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfNtStatusFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x18010fda8  movzx   eax, [rsp+48h+arg_20]
0x18010fdad  lea     r8, [rsp+48h+var_20]; ThreadInformation
0x18010fdb2  mov     rcx, [rbx+30h]; ThreadHandle
0x18010fdb6  mov     r9d, 0Ch; ThreadInformationLength
0x18010fdbc  mov     dword ptr [rsp+48h+var_20], 1
0x18010fdc4  mov     dword ptr [rsp+48h+var_20+4], eax
0x18010fdc8  mov     [rsp+48h+var_18], eax
0x18010fdcc  lea     edx, [r9+25h]; ThreadInformationClass
0x18010fdd0  call    cs:__imp_NtSetInformationThread
0x18010fdd7  nop     dword ptr [rax+rax+00h]
0x18010fddc  lea     r8, aUnableToSetThr_2; "Unable to set thread throttling state"
0x18010fde3  mov     ecx, 2
0x18010fde8  mov     edx, eax
0x18010fdea  call    ??$TraceAtLevelIfNtStatusFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfNtStatusFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x18010fdef  mov     byte ptr [rbx+48h], 1
0x18010fdf3  mov     rcx, [rsp+48h+var_10]
0x18010fdf8  xor     rcx, rsp; StackCookie
0x18010fdfb  call    __security_check_cookie
0x18010fe00  add     rsp, 40h
0x18010fe04  pop     rbx
0x18010fe05  retn
```
