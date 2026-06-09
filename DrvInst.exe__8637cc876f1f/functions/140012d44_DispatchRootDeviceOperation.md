# DispatchRootDeviceOperation

- ea: `0x140012d44`
- end: `0x1400130ed`
- name: `DispatchRootDeviceOperation`
- size: `937`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD dwMilliseconds, __int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140013f6c`
- `0x1400149e0`

## callees

- `0x140012d44`
- `0x140018478`
- `0x140018dc0`
- `0x14002144c`
- `0x140047010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140012ed3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140012ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012f65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012f9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012f65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012f9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14001306f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14001306f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140012e68`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140012e68`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x140012f5b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x140012f5b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140012ee7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140012ee7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400130d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400130d9`
- `DEVRTL!DevRtlWriteTextLog` at `0x140012eb4`
- `DEVRTL!DevRtlWriteTextLog` at `0x140012f32`
- `DEVRTL!DevRtlWriteTextLog` at `0x140012fde`
- `DEVRTL!DevRtlWriteTextLog` at `0x140012eb4`
- `DEVRTL!DevRtlWriteTextLog` at `0x140012f32`
- `DEVRTL!DevRtlWriteTextLog` at `0x140012fde`

## string_xrefs

- `0x140012e9a`: `Failed to create thread for device '%ws'. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall DispatchRootDeviceOperation(
        __int64 a1,
        unsigned int a2,
        __int64 (__fastcall *a3)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD),
        __int64 a4,
        DWORD dwMilliseconds,
        __int64 a6,
        __int64 a7)
{
  LPDWORD lpThreadId; // [rsp+28h] [rbp-B0h]
  DWORD ExitCode; // [rsp+30h] [rbp-A8h] BYREF
  int v10; // [rsp+34h] [rbp-A4h]
  DWORD v11; // [rsp+38h] [rbp-A0h]
  HANDLE hHandle; // [rsp+40h] [rbp-98h]
  DWORD ThreadId; // [rsp+48h] [rbp-90h] BYREF
  DWORD CurrentProcessId; // [rsp+4Ch] [rbp-8Ch]
  BOOL v15; // [rsp+50h] [rbp-88h]
  int v16; // [rsp+54h] [rbp-84h]
  __int64 v17; // [rsp+58h] [rbp-80h]
  __int64 (__fastcall *v18)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // [rsp+60h] [rbp-78h]
  _QWORD Parameter[6]; // [rsp+68h] [rbp-70h] BYREF
  _QWORD v20[8]; // [rsp+98h] [rbp-40h] BYREF

  ExitCode = 0;
  hHandle = 0;
  v11 = 0;
  ThreadId = 0;
  CurrentProcessId = 0;
  v17 = 0;
  memset(v20, 0, 0x30u);
  v10 = 0;
  memset(Parameter, 0, sizeof(Parameter));
  if ( dwMilliseconds )
  {
    memset(Parameter, 0, sizeof(Parameter));
    Parameter[0] = a1;
    LODWORD(Parameter[1]) = a2;
    Parameter[2] = a3;
    Parameter[3] = a4;
    Parameter[4] = a6;
    Parameter[5] = a7;
    hHandle = CreateThread(0, 0, DispatchRootDeviceThreadWorker, Parameter, 0, &ThreadId);
    if ( hHandle )
    {
      do
        v11 = WaitForSingleObject(hHandle, dwMilliseconds);
      while ( v11 == 258 && IsDebuggerPresent() );
      if ( v11 == 258 )
      {
        ExitCode = 1460;
        LODWORD(lpThreadId) = 1460;
        DevRtlWriteTextLog(a7, 1, 2, "Timed out waiting for device '%ws'. Error = 0x%08X", a1, lpThreadId);
        v10 = 1;
      }
      else if ( v11 )
      {
        if ( v11 == -1 )
          ExitCode = GetLastError();
        else
          ExitCode = 13;
        LODWORD(lpThreadId) = ExitCode;
        DevRtlWriteTextLog(a7, 1, 1, "Failed to wait for device '%ws'. Error = 0x%08X", a1, lpThreadId);
        v10 = 2;
      }
      else if ( GetExitCodeThread(hHandle, &ExitCode) )
      {
        if ( ExitCode )
          v10 = 3;
      }
      else
      {
        ExitCode = GetLastError();
        v10 = 3;
      }
    }
    else
    {
      ExitCode = GetLastError();
      LODWORD(lpThreadId) = ExitCode;
      DevRtlWriteTextLog(a7, 1, 1, "Failed to create thread for device '%ws'. Error = 0x%08X", a1, lpThreadId);
      v10 = 3;
    }
  }
  else
  {
    v18 = a3;
    ExitCode = a3(a1, a2, a4, a6, a7);
  }
  if ( v10 )
  {
    if ( v10 != 3 )
    {
      DrvInstActionCallback(19, (unsigned int *)v20);
      v17 = v20[5];
      if ( v20[5] )
      {
        CurrentProcessId = GetCurrentProcessId();
        SendErrorReport(CurrentProcessId, ThreadId, 1, a7);
      }
    }
  }
  v15 = v10 != 0;
  if ( v10 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v16 = 0;
  }
  else
  {
    v16 = 1;
  }
  if ( hHandle )
    CloseHandle(hHandle);
  return ExitCode;
}

```

## disassembly

```asm
0x140012d44  mov     [rsp+arg_18], r9
0x140012d49  mov     [rsp+arg_10], r8
0x140012d4e  mov     [rsp+arg_8], edx
0x140012d52  mov     [rsp+arg_0], rcx
0x140012d57  push    rdi
0x140012d58  sub     rsp, 0D0h
0x140012d5f  mov     [rsp+0D8h+ExitCode], 0
0x140012d67  mov     [rsp+0D8h+hHandle], 0
0x140012d70  mov     [rsp+0D8h+var_A0], 0
0x140012d78  mov     [rsp+0D8h+ThreadId], 0
0x140012d80  mov     [rsp+0D8h+var_8C], 0
0x140012d88  mov     [rsp+0D8h+var_80], 0
0x140012d91  lea     rax, [rsp+0D8h+var_3C]
0x140012d99  mov     rdi, rax
0x140012d9c  xor     eax, eax
0x140012d9e  mov     ecx, 4
0x140012da3  rep stosb
0x140012da5  lea     rax, [rsp+0D8h+var_40]
0x140012dad  mov     rdi, rax
0x140012db0  xor     eax, eax
0x140012db2  mov     ecx, 30h ; '0'
0x140012db7  rep stosb
0x140012db9  mov     [rsp+0D8h+var_A4], 0
0x140012dc1  lea     rax, [rsp+0D8h+Parameter]
0x140012dc6  mov     rdi, rax
0x140012dc9  xor     eax, eax
0x140012dcb  mov     ecx, 30h ; '0'
0x140012dd0  rep stosb
0x140012dd2  cmp     [rsp+0D8h+dwMilliseconds], 0
0x140012dda  jz      loc_140012FF0
0x140012de0  lea     rax, [rsp+0D8h+Parameter]
0x140012de5  mov     rdi, rax
0x140012de8  xor     eax, eax
0x140012dea  mov     ecx, 30h ; '0'
0x140012def  rep stosb
0x140012df1  mov     rax, [rsp+0D8h+arg_0]
0x140012df9  mov     [rsp+0D8h+Parameter], rax
0x140012dfe  mov     eax, [rsp+0D8h+arg_8]
0x140012e05  mov     [rsp+0D8h+var_68], eax
0x140012e09  mov     rax, [rsp+0D8h+arg_10]
0x140012e11  mov     [rsp+0D8h+var_60], rax
0x140012e16  mov     rax, [rsp+0D8h+arg_18]
0x140012e1e  mov     [rsp+0D8h+var_58], rax
0x140012e26  mov     rax, [rsp+0D8h+arg_28]
0x140012e2e  mov     [rsp+0D8h+var_50], rax
0x140012e36  mov     rax, [rsp+0D8h+arg_30]
0x140012e3e  mov     [rsp+0D8h+var_48], rax
0x140012e46  lea     rax, [rsp+0D8h+ThreadId]
0x140012e4b  mov     [rsp+0D8h+lpThreadId], rax; lpThreadId
0x140012e50  mov     [rsp+0D8h+dwCreationFlags], 0; dwCreationFlags
0x140012e58  lea     r9, [rsp+0D8h+Parameter]; lpParameter
0x140012e5d  lea     r8, DispatchRootDeviceThreadWorker; lpStartAddress
0x140012e64  xor     edx, edx; dwStackSize
0x140012e66  xor     ecx, ecx; lpThreadAttributes
0x140012e68  call    cs:__imp_CreateThread
0x140012e6e  mov     [rsp+0D8h+hHandle], rax
0x140012e73  cmp     [rsp+0D8h+hHandle], 0
0x140012e79  jnz     short loc_140012EC7
0x140012e7b  call    cs:__imp_GetLastError
0x140012e81  mov     [rsp+0D8h+ExitCode], eax
0x140012e85  mov     eax, [rsp+0D8h+ExitCode]
0x140012e89  mov     dword ptr [rsp+0D8h+lpThreadId], eax
0x140012e8d  mov     rax, [rsp+0D8h+arg_0]
0x140012e95  mov     qword ptr [rsp+0D8h+dwCreationFlags], rax
0x140012e9a  lea     r9, aFailedToCreate_7; "Failed to create thread for device '%ws"...
0x140012ea1  mov     r8d, 1
0x140012ea7  mov     edx, 1
0x140012eac  mov     rcx, [rsp+0D8h+arg_30]
0x140012eb4  call    cs:__imp_DevRtlWriteTextLog
0x140012eba  mov     [rsp+0D8h+var_A4], 3
0x140012ec2  jmp     loc_140013037
0x140012ec7  mov     edx, [rsp+0D8h+dwMilliseconds]; dwMilliseconds
0x140012ece  mov     rcx, [rsp+0D8h+hHandle]; hHandle
0x140012ed3  call    cs:__imp_WaitForSingleObject
0x140012ed9  mov     [rsp+0D8h+var_A0], eax
0x140012edd  cmp     [rsp+0D8h+var_A0], 102h
0x140012ee5  jnz     short loc_140012EF1
0x140012ee7  call    cs:__imp_IsDebuggerPresent
0x140012eed  test    eax, eax
0x140012eef  jnz     short loc_140012EC7
0x140012ef1  cmp     [rsp+0D8h+var_A0], 102h
0x140012ef9  jnz     short loc_140012F4A
0x140012efb  mov     [rsp+0D8h+ExitCode], 5B4h
0x140012f03  mov     eax, [rsp+0D8h+ExitCode]
0x140012f07  mov     dword ptr [rsp+0D8h+lpThreadId], eax
0x140012f0b  mov     rax, [rsp+0D8h+arg_0]
0x140012f13  mov     qword ptr [rsp+0D8h+dwCreationFlags], rax
0x140012f18  lea     r9, aTimedOutWaitin_0; "Timed out waiting for device '%ws'. Err"...
0x140012f1f  mov     r8d, 2
0x140012f25  mov     edx, 1
0x140012f2a  mov     rcx, [rsp+0D8h+arg_30]
0x140012f32  call    cs:__imp_DevRtlWriteTextLog
0x140012f38  mov     [rsp+0D8h+var_A4], 1
0x140012f40  jmp     loc_140013037
0x140012f45  jmp     loc_140012FEE
0x140012f4a  cmp     [rsp+0D8h+var_A0], 0
0x140012f4f  jnz     short loc_140012F94
0x140012f51  lea     rdx, [rsp+0D8h+ExitCode]; lpExitCode
0x140012f56  mov     rcx, [rsp+0D8h+hHandle]; hThread
0x140012f5b  call    cs:__imp_GetExitCodeThread
0x140012f61  test    eax, eax
0x140012f63  jnz     short loc_140012F7E
0x140012f65  call    cs:__imp_GetLastError
0x140012f6b  mov     [rsp+0D8h+ExitCode], eax
0x140012f6f  mov     [rsp+0D8h+var_A4], 3
0x140012f77  jmp     loc_140013037
0x140012f7c  jmp     short loc_140012F92
0x140012f7e  cmp     [rsp+0D8h+ExitCode], 0
0x140012f83  jz      short loc_140012F92
0x140012f85  mov     [rsp+0D8h+var_A4], 3
0x140012f8d  jmp     loc_140013037
0x140012f92  jmp     short loc_140012FEE
0x140012f94  cmp     [rsp+0D8h+var_A0], 0FFFFFFFFh
0x140012f99  jnz     short loc_140012FA7
0x140012f9b  call    cs:__imp_GetLastError
0x140012fa1  mov     [rsp+0D8h+ExitCode], eax
0x140012fa5  jmp     short loc_140012FAF
0x140012fa7  mov     [rsp+0D8h+ExitCode], 0Dh
0x140012faf  mov     eax, [rsp+0D8h+ExitCode]
0x140012fb3  mov     dword ptr [rsp+0D8h+lpThreadId], eax
0x140012fb7  mov     rax, [rsp+0D8h+arg_0]
0x140012fbf  mov     qword ptr [rsp+0D8h+dwCreationFlags], rax
0x140012fc4  lea     r9, aFailedToWaitFo; "Failed to wait for device '%ws'. Error "...
0x140012fcb  mov     r8d, 1
0x140012fd1  mov     edx, 1
0x140012fd6  mov     rcx, [rsp+0D8h+arg_30]
0x140012fde  call    cs:__imp_DevRtlWriteTextLog
0x140012fe4  mov     [rsp+0D8h+var_A4], 2
0x140012fec  jmp     short loc_140013037
0x140012fee  jmp     short loc_140013037
0x140012ff0  mov     rax, [rsp+0D8h+arg_10]
0x140012ff8  mov     [rsp+0D8h+var_78], rax
0x140012ffd  mov     rax, [rsp+0D8h+arg_30]
0x140013005  mov     qword ptr [rsp+0D8h+dwCreationFlags], rax
0x14001300a  mov     r9, [rsp+0D8h+arg_28]
0x140013012  mov     r8, [rsp+0D8h+arg_18]
0x14001301a  mov     edx, [rsp+0D8h+arg_8]
0x140013021  mov     rcx, [rsp+0D8h+arg_0]
0x140013029  mov     rax, [rsp+0D8h+var_78]
0x14001302e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013033  mov     [rsp+0D8h+ExitCode], eax
0x140013037  cmp     [rsp+0D8h+var_A4], 0
0x14001303c  jz      short loc_140013095
0x14001303e  cmp     [rsp+0D8h+var_A4], 3
0x140013043  jz      short loc_140013095
0x140013045  xor     r8d, r8d
0x140013048  lea     rdx, [rsp+0D8h+var_40]
0x140013050  mov     ecx, 13h
0x140013055  call    DrvInstActionCallback
0x14001305a  mov     rax, [rsp+0D8h+var_18]
0x140013062  mov     [rsp+0D8h+var_80], rax
0x140013067  cmp     [rsp+0D8h+var_80], 0
0x14001306d  jz      short loc_140013095
0x14001306f  call    cs:__imp_GetCurrentProcessId
0x140013075  mov     [rsp+0D8h+var_8C], eax
0x140013079  mov     r9, [rsp+0D8h+arg_30]
0x140013081  mov     r8d, 1
0x140013087  mov     edx, [rsp+0D8h+ThreadId]
0x14001308b  mov     ecx, [rsp+0D8h+var_8C]
0x14001308f  call    SendErrorReport
0x140013094  nop
0x140013095  cmp     [rsp+0D8h+var_A4], 0
0x14001309a  jz      short loc_1400130A6
0x14001309c  mov     [rsp+0D8h+var_88], 1
0x1400130a4  jmp     short loc_1400130AE
0x1400130a6  mov     [rsp+0D8h+var_88], 0
0x1400130ae  cmp     [rsp+0D8h+var_88], 0
0x1400130b3  jz      short loc_1400130C4
0x1400130b5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1400130ba  mov     [rsp+0D8h+var_84], 0
0x1400130c2  jmp     short loc_1400130CC
0x1400130c4  mov     [rsp+0D8h+var_84], 1
0x1400130cc  cmp     [rsp+0D8h+hHandle], 0
0x1400130d2  jz      short loc_1400130E0
0x1400130d4  mov     rcx, [rsp+0D8h+hHandle]; hObject
0x1400130d9  call    cs:__imp_CloseHandle
0x1400130df  nop
0x1400130e0  mov     eax, [rsp+0D8h+ExitCode]
0x1400130e4  add     rsp, 0D0h
0x1400130eb  pop     rdi
0x1400130ec  retn
```
