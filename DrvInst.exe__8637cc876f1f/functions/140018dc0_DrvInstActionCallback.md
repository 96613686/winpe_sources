# DrvInstActionCallback

- ea: `0x140018dc0`
- end: `0x140019084`
- name: `DrvInstActionCallback`
- size: `708`
- prototype: `_BOOL8 __fastcall(int, unsigned int *)`
- caller_count: `12`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140009050`
- `0x140011a78`
- `0x140012d44`
- `0x140014150`
- `0x140014be0`
- `0x140019278`
- `0x140019700`
- `0x14001c718`
- `0x14001d150`
- `0x14001d2c4`
- `0x14001dc80`
- `0x14001e944`

## callees

- `0x1400165ac`
- `0x140016de0`
- `0x14001883c`
- `0x140018b38`
- `0x140018dc0`
- `0x140019148`
- `0x14001923c`
- `0x140019278`
- `0x140019700`
- `0x14002144c`
- `0x140023a7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140018e4e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140018e4e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140018ecf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140018ecf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140018f1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140018f1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018e5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018e5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001906c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001906c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018edc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018edc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018f28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018f28`
- `DEVRTL!DevRtlWriteTextLog` at `0x140018e86`
- `DEVRTL!DevRtlWriteTextLog` at `0x140018eac`
- `DEVRTL!DevRtlWriteTextLog` at `0x140018e86`
- `DEVRTL!DevRtlWriteTextLog` at `0x140018eac`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140018e69`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140018e93`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140018f75`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14001903e`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140018e69`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140018e93`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140018f75`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14001903e`

## string_xrefs

- `0x140018e7b`: `Unable to reset install timeout. Error = 0x%08X`
- `0x140018e9e`: `Unable to reset install timeout.`

## pseudocode

```c
_BOOL8 __fastcall DrvInstActionCallback(int a1, unsigned int *a2)
{
  DWORD LastError; // edi
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  unsigned int ShouldAbort; // eax
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  _QWORD *v13; // rbx
  void *v14; // r8
  __int64 v15; // rax
  __int64 DeviceInstallStatus; // rax
  __int64 v17; // rbx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  __int64 v26; // rax
  wchar_t *v27; // rdx
  BOOL v28; // ecx
  __int64 v29; // rbx
  __int64 v31; // [rsp+30h] [rbp-18h]
  __int64 ThreadLogToken; // [rsp+30h] [rbp-18h]

  LastError = 0;
  if ( a2 )
    *((_QWORD *)a2 + 5) = 0;
  if ( a1 > 10 )
  {
    v18 = a1 - 11;
    if ( !v18 )
    {
      v29 = *((_QWORD *)a2 + 4);
      ThreadLogToken = DevRtlGetThreadLogToken();
      CommitDeviceInstallStatus((unsigned int)&g_SessionGuid, v29, 0, 0, 0, 1, ThreadLogToken);
      goto LABEL_63;
    }
    v19 = v18 - 1;
    if ( !v19 )
    {
      LogDevNodeState(*a2);
      goto LABEL_63;
    }
    v20 = v19 - 1;
    if ( !v20 )
    {
      SpUtilsGenerateRandomGuid();
      goto LABEL_63;
    }
    v21 = v20 - 1;
    if ( !v21 )
    {
      g_SessionGuid = 0;
      goto LABEL_63;
    }
    v22 = v21 - 1;
    if ( !v22 )
    {
      *((_QWORD *)a2 + 5) = &g_SessionGuid;
      goto LABEL_63;
    }
    v23 = v22 - 1;
    if ( !v23 )
    {
      v27 = (wchar_t *)*((_QWORD *)a2 + 3);
      if ( v27 )
        v28 = DevNodeNeedsUpdate(*a2, v27) == 0;
      else
        v28 = 0;
      a2[10] = v28;
      goto LABEL_63;
    }
    v24 = v23 - 1;
    if ( v24 )
    {
      v25 = v24 - 1;
      if ( v25 )
      {
        if ( v25 != 1 )
          goto LABEL_47;
        v15 = g_CriticalAction;
        goto LABEL_33;
      }
      v26 = 0;
    }
    else
    {
      v26 = *((_QWORD *)a2 + 4);
    }
    _InterlockedExchange64(&g_CriticalAction, v26);
    goto LABEL_63;
  }
  if ( a1 == 10 )
  {
    v17 = *((_QWORD *)a2 + 4);
    v31 = DevRtlGetThreadLogToken();
    CommitDeviceInstallStatus((unsigned int)&g_SessionGuid, v17, 0, 0, 0, 0, v31);
    goto LABEL_63;
  }
  if ( a1 > 5 )
  {
    v10 = a1 - 6;
    if ( !v10 )
    {
      a2[10] = g_BootCriticalDevice;
      goto LABEL_63;
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      DeviceInstallStatus = CreateDeviceInstallStatus(
                              *a2,
                              *((_QWORD *)a2 + 1),
                              *((_QWORD *)a2 + 2),
                              *((_QWORD *)a2 + 3));
LABEL_35:
      *((_QWORD *)a2 + 5) = DeviceInstallStatus;
      goto LABEL_63;
    }
    v12 = v11 - 1;
    if ( v12 )
    {
      if ( v12 != 1 )
        goto LABEL_47;
      v13 = (_QWORD *)*((_QWORD *)a2 + 4);
      v14 = (void *)v13[365];
      if ( v14 )
        HeapFree(hHeap, 0, v14);
      LocalFree(v13);
      goto LABEL_63;
    }
    v15 = _InterlockedExchange64(&g_DeviceInstallStatus, *((_QWORD *)a2 + 4));
LABEL_33:
    *((_QWORD *)a2 + 5) = v15;
    goto LABEL_63;
  }
  if ( a1 != 5 )
  {
    if ( !a1 )
    {
      if ( g_hResetTimeoutEvent )
      {
        if ( SetEvent(g_hResetTimeoutEvent) )
          goto LABEL_63;
        LastError = GetLastError();
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v8 = DevRtlGetThreadLogToken();
        DevRtlWriteTextLog(v8, 1, 2, "Unable to reset install timeout. Error = 0x%08X", LastError);
      }
      else
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v9 = DevRtlGetThreadLogToken();
        DevRtlWriteTextLog(v9, 1, 2, "Unable to reset install timeout.");
      }
      if ( !LastError )
        goto LABEL_63;
      goto LABEL_48;
    }
    v4 = a1 - 1;
    if ( !v4 )
    {
      ShouldAbort = WaitForDevicePostInstall(*a2, *((_QWORD *)a2 + 1));
      goto LABEL_13;
    }
    v5 = v4 - 1;
    if ( !v5 )
    {
      ShouldAbort = InstallShouldAbort(*a2);
      goto LABEL_13;
    }
    v6 = v5 - 1;
    if ( !v6 )
    {
      ShouldAbort = ShutdownPending();
      goto LABEL_13;
    }
    if ( v6 == 1 )
    {
      ShouldAbort = WaitForInstallMutex(*((_QWORD *)a2 + 1));
LABEL_13:
      a2[10] = ShouldAbort;
      goto LABEL_63;
    }
LABEL_47:
    LastError = 50;
LABEL_48:
    if ( !a2 )
      goto LABEL_63;
    DeviceInstallStatus = 0;
    goto LABEL_35;
  }
  if ( g_hMutex )
  {
    ReleaseMutex(g_hMutex);
    CloseHandle(g_hMutex);
    g_hMutex = 0;
  }
LABEL_63:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x140018dc0  mov     [rsp+arg_0], rbx
0x140018dc5  push    rdi
0x140018dc6  sub     rsp, 40h
0x140018dca  xor     edi, edi
0x140018dcc  mov     rbx, rdx
0x140018dcf  test    rdx, rdx
0x140018dd2  jz      short loc_140018DDA
0x140018dd4  xor     eax, eax
0x140018dd6  mov     [rdx+28h], rax
0x140018dda  cmp     ecx, 0Ah
0x140018ddd  jg      loc_140018F89
0x140018de3  jz      loc_140018F71
0x140018de9  cmp     ecx, 5
0x140018dec  jg      loc_140018EEE
0x140018df2  jz      loc_140018EBF
0x140018df8  test    ecx, ecx
0x140018dfa  jz      short loc_140018E42
0x140018dfc  sub     ecx, 1
0x140018dff  jz      short loc_140018E35
0x140018e01  sub     ecx, 1
0x140018e04  jz      short loc_140018E2C
0x140018e06  sub     ecx, 1
0x140018e09  jz      short loc_140018E25
0x140018e0b  cmp     ecx, 1
0x140018e0e  jnz     loc_140018FC2
0x140018e14  mov     rcx, [rdx+8]
0x140018e18  call    WaitForInstallMutex
0x140018e1d  mov     [rbx+28h], eax
0x140018e20  jmp     loc_14001906A
0x140018e25  call    ShutdownPending
0x140018e2a  jmp     short loc_140018E1D
0x140018e2c  mov     ecx, [rdx]
0x140018e2e  call    InstallShouldAbort
0x140018e33  jmp     short loc_140018E1D
0x140018e35  mov     rdx, [rdx+8]
0x140018e39  mov     ecx, [rbx]
0x140018e3b  call    WaitForDevicePostInstall
0x140018e40  jmp     short loc_140018E1D
0x140018e42  mov     rcx, cs:g_hResetTimeoutEvent; hEvent
0x140018e49  test    rcx, rcx
0x140018e4c  jz      short loc_140018E8E
0x140018e4e  call    cs:__imp_SetEvent
0x140018e54  test    eax, eax
0x140018e56  jnz     loc_14001906A
0x140018e5c  call    cs:__imp_GetLastError
0x140018e62  mov     edi, eax
0x140018e64  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140018e69  call    cs:__imp_DevRtlGetThreadLogToken
0x140018e6f  mov     edx, 1
0x140018e74  mov     [rsp+48h+var_28], edi
0x140018e78  mov     rcx, rax
0x140018e7b  lea     r9, aUnableToResetI; "Unable to reset install timeout. Error "...
0x140018e82  lea     r8d, [rdx+1]
0x140018e86  call    cs:__imp_DevRtlWriteTextLog
0x140018e8c  jmp     short loc_140018EB2
0x140018e8e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140018e93  call    cs:__imp_DevRtlGetThreadLogToken
0x140018e99  mov     edx, 1
0x140018e9e  lea     r9, aUnableToResetI_0; "Unable to reset install timeout."
0x140018ea5  mov     rcx, rax
0x140018ea8  lea     r8d, [rdx+1]
0x140018eac  call    cs:__imp_DevRtlWriteTextLog
0x140018eb2  test    edi, edi
0x140018eb4  jz      loc_14001906A
0x140018eba  jmp     loc_140018FC7
0x140018ebf  mov     rcx, cs:g_hMutex; hMutex
0x140018ec6  test    rcx, rcx
0x140018ec9  jz      loc_14001906A
0x140018ecf  call    cs:__imp_ReleaseMutex
0x140018ed5  mov     rcx, cs:g_hMutex; hObject
0x140018edc  call    cs:__imp_CloseHandle
0x140018ee2  mov     cs:g_hMutex, rdi
0x140018ee9  jmp     loc_14001906A
0x140018eee  sub     ecx, 6
0x140018ef1  jz      short loc_140018F63
0x140018ef3  sub     ecx, 1
0x140018ef6  jz      short loc_140018F47
0x140018ef8  sub     ecx, 1
0x140018efb  jz      short loc_140018F33
0x140018efd  cmp     ecx, 1
0x140018f00  jnz     loc_140018FC2
0x140018f06  mov     rbx, [rdx+20h]
0x140018f0a  mov     r8, [rbx+0B68h]; lpMem
0x140018f11  test    r8, r8
0x140018f14  jz      short loc_140018F25
0x140018f16  mov     rcx, cs:hHeap; hHeap
0x140018f1d  xor     edx, edx; dwFlags
0x140018f1f  call    cs:__imp_HeapFree
0x140018f25  mov     rcx, rbx; hMem
0x140018f28  call    cs:__imp_LocalFree
0x140018f2e  jmp     loc_14001906A
0x140018f33  mov     rax, [rdx+20h]
0x140018f37  xchg    rax, cs:g_DeviceInstallStatus
0x140018f3e  mov     [rdx+28h], rax
0x140018f42  jmp     loc_14001906A
0x140018f47  mov     r9, [rdx+18h]
0x140018f4b  mov     r8, [rdx+10h]
0x140018f4f  mov     rdx, [rdx+8]
0x140018f53  mov     ecx, [rbx]
0x140018f55  call    CreateDeviceInstallStatus
0x140018f5a  mov     [rbx+28h], rax
0x140018f5e  jmp     loc_14001906A
0x140018f63  mov     eax, cs:g_BootCriticalDevice
0x140018f69  mov     [rdx+28h], eax
0x140018f6c  jmp     loc_14001906A
0x140018f71  mov     rbx, [rdx+20h]
0x140018f75  call    cs:__imp_DevRtlGetThreadLogToken
0x140018f7b  mov     [rsp+48h+var_18], rax
0x140018f80  mov     [rsp+48h+var_20], edi
0x140018f84  jmp     loc_140019051
0x140018f89  sub     ecx, 0Bh
0x140018f8c  jz      loc_14001903A
0x140018f92  sub     ecx, 1
0x140018f95  jz      loc_140019031
0x140018f9b  sub     ecx, 1
0x140018f9e  jz      loc_14001902A
0x140018fa4  sub     ecx, 1
0x140018fa7  jz      short loc_14001901E
0x140018fa9  sub     ecx, 1
0x140018fac  jz      short loc_140019011
0x140018fae  sub     ecx, 1
0x140018fb1  jz      short loc_140018FF1
0x140018fb3  sub     ecx, 1
0x140018fb6  jz      short loc_140018FEB
0x140018fb8  sub     ecx, 1
0x140018fbb  jz      short loc_140018FE0
0x140018fbd  cmp     ecx, 1
0x140018fc0  jz      short loc_140018FD4
0x140018fc2  mov     edi, 32h ; '2'
0x140018fc7  test    rbx, rbx
0x140018fca  jz      loc_14001906A
0x140018fd0  xor     eax, eax
0x140018fd2  jmp     short loc_140018F5A
0x140018fd4  mov     rax, cs:g_CriticalAction
0x140018fdb  jmp     loc_140018F3E
0x140018fe0  xor     eax, eax
0x140018fe2  xchg    rax, cs:g_CriticalAction
0x140018fe9  jmp     short loc_14001906A
0x140018feb  mov     rax, [rdx+20h]
0x140018fef  jmp     short loc_140018FE2
0x140018ff1  mov     rdx, [rdx+18h]; Str
0x140018ff5  test    rdx, rdx
0x140018ff8  jz      short loc_14001900A
0x140018ffa  mov     ecx, [rbx]; dnDevInst
0x140018ffc  call    DevNodeNeedsUpdate
0x140019001  xor     ecx, ecx
0x140019003  test    eax, eax
0x140019005  setz    cl
0x140019008  jmp     short loc_14001900C
0x14001900a  xor     ecx, ecx
0x14001900c  mov     [rbx+28h], ecx
0x14001900f  jmp     short loc_14001906A
0x140019011  lea     rcx, g_SessionGuid
0x140019018  mov     [rdx+28h], rcx
0x14001901c  jmp     short loc_14001906A
0x14001901e  xorps   xmm0, xmm0
0x140019021  movups  cs:g_SessionGuid, xmm0
0x140019028  jmp     short loc_14001906A
0x14001902a  call    SpUtilsGenerateRandomGuid
0x14001902f  jmp     short loc_14001906A
0x140019031  mov     ecx, [rdx]; dnDevInst
0x140019033  call    LogDevNodeState
0x140019038  jmp     short loc_14001906A
0x14001903a  mov     rbx, [rdx+20h]
0x14001903e  call    cs:__imp_DevRtlGetThreadLogToken
0x140019044  mov     [rsp+48h+var_18], rax
0x140019049  mov     [rsp+48h+var_20], 1
0x140019051  xor     r9d, r9d
0x140019054  mov     [rsp+48h+var_28], edi
0x140019058  xor     r8d, r8d
0x14001905b  lea     rcx, g_SessionGuid
0x140019062  mov     rdx, rbx
0x140019065  call    CommitDeviceInstallStatus
0x14001906a  mov     ecx, edi; dwErrCode
0x14001906c  call    cs:__imp_SetLastError
0x140019072  mov     rbx, [rsp+48h+arg_0]
0x140019077  xor     eax, eax
0x140019079  test    edi, edi
0x14001907b  setz    al
0x14001907e  add     rsp, 40h
0x140019082  pop     rdi
0x140019083  retn
```
