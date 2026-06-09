# CtapHidDeviceChangeNotifyCallback

- ea: `0x180016c90`
- end: `0x180016e39`
- name: `CtapHidDeviceChangeNotifyCallback`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800d937c`

## callees

- `0x180016c90`
- `0x1800dd0f0`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016dc6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016e14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016dc6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016e14`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016cb2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016d9c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016cb2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016d9c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016cd8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016cd8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180016d2a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180016d2a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180016d52`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180016d52`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180016d76`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180016d76`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180016d83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180016d83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016df0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016df0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016dde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016dde`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x180016dd5`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x180016dd5`
- `HID!HidD_GetHidGuid` at `0x180016cf7`
- `HID!HidD_GetHidGuid` at `0x180016cf7`

## pseudocode

```c
void __fastcall CtapHidDeviceChangeNotifyCallback(int a1)
{
  PTP_WAIT ThreadpoolWait; // rax
  _QWORD *v3; // rbx
  __int64 v4; // rdx
  _QWORD *v5; // rax
  GUID HidGuid; // [rsp+20h] [rbp-28h] BYREF

  AcquireSRWLockExclusive(&stru_1801AF250);
  if ( a1 != (_DWORD)xmmword_1801AF200 )
  {
    if ( a1 )
    {
      a1 = 0;
      *((_QWORD *)&xmmword_1801AF200 + 1) = CreateEventW(0, 0, 0, 0);
      if ( *((_QWORD *)&xmmword_1801AF200 + 1) )
      {
        HidGuid = 0;
        HidD_GetHidGuid(&HidGuid);
        CtapSrvRegisterDeviceNotification(&HidGuid, *((_QWORD *)&xmmword_1801AF200 + 1), &hMem);
      }
      if ( hMem )
      {
        ThreadpoolWait = CreateThreadpoolWait(CtapHidDeviceChangeNotifyWaitCallback, 0, 0);
        *(&hMem + 1) = ThreadpoolWait;
      }
      else
      {
        ThreadpoolWait = (PTP_WAIT)*(&hMem + 1);
      }
      if ( ThreadpoolWait )
      {
        SetThreadpoolWait(ThreadpoolWait, *((HANDLE *)&xmmword_1801AF200 + 1), 0);
        a1 = 1;
LABEL_21:
        LODWORD(xmmword_1801AF200) = a1;
        goto LABEL_22;
      }
    }
    else if ( *(&hMem + 1) )
    {
      WaitForThreadpoolWaitCallbacks((PTP_WAIT)*(&hMem + 1), 1);
      CloseThreadpoolWait((PTP_WAIT)*(&hMem + 1));
    }
    v3 = hMem;
    if ( hMem )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v4 = *v3;
      if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v5 = (_QWORD *)v3[1], (_QWORD *)*v5 != v3) )
        __fastfail(3u);
      *v5 = v4;
      *(_QWORD *)(v4 + 8) = v5;
      ReleaseSRWLockExclusive(&SRWLock);
      if ( v3[5] )
        I_ScUnregisterDeviceNotification();
      LocalFree(v3);
    }
    if ( *((_QWORD *)&xmmword_1801AF200 + 1) )
      CloseHandle(*((HANDLE *)&xmmword_1801AF200 + 1));
    xmmword_1801AF200 = 0;
    *(_OWORD *)&hMem = 0;
    goto LABEL_21;
  }
LABEL_22:
  ReleaseSRWLockExclusive(&stru_1801AF250);
}

```

## disassembly

```asm
0x180016c90  mov     [rsp+arg_0], rbx
0x180016c95  push    rdi
0x180016c96  sub     rsp, 40h
0x180016c9a  mov     rax, cs:__security_cookie
0x180016ca1  xor     rax, rsp
0x180016ca4  mov     [rsp+48h+var_18], rax
0x180016ca9  mov     edi, ecx
0x180016cab  lea     rcx, stru_1801AF250; SRWLock
0x180016cb2  call    cs:__imp_AcquireSRWLockExclusive
0x180016cb8  cmp     edi, dword ptr cs:xmmword_1801AF200
0x180016cbe  jz      loc_180016E0D
0x180016cc4  test    edi, edi
0x180016cc6  jz      loc_180016D62
0x180016ccc  xor     r9d, r9d; lpName
0x180016ccf  xor     r8d, r8d; bInitialState
0x180016cd2  xor     edx, edx; bManualReset
0x180016cd4  xor     ecx, ecx; lpEventAttributes
0x180016cd6  xor     edi, edi
0x180016cd8  call    cs:__imp_CreateEventW
0x180016cde  mov     qword ptr cs:xmmword_1801AF200+8, rax
0x180016ce5  test    rax, rax
0x180016ce8  jz      short loc_180016D15
0x180016cea  xorps   xmm0, xmm0
0x180016ced  lea     rcx, [rsp+48h+HidGuid]; HidGuid
0x180016cf2  movups  xmmword ptr [rsp+48h+HidGuid.Data1], xmm0
0x180016cf7  call    cs:__imp_HidD_GetHidGuid
0x180016cfd  mov     rdx, qword ptr cs:xmmword_1801AF200+8
0x180016d04  lea     r8, hMem
0x180016d0b  lea     rcx, [rsp+48h+HidGuid]
0x180016d10  call    CtapSrvRegisterDeviceNotification
0x180016d15  cmp     qword ptr cs:hMem, rdi
0x180016d1c  jz      short loc_180016D39
0x180016d1e  xor     r8d, r8d; pcbe
0x180016d21  lea     rcx, CtapHidDeviceChangeNotifyWaitCallback; pfnwa
0x180016d28  xor     edx, edx; pv
0x180016d2a  call    cs:__imp_CreateThreadpoolWait
0x180016d30  mov     qword ptr cs:hMem+8, rax
0x180016d37  jmp     short loc_180016D40
0x180016d39  mov     rax, qword ptr cs:hMem+8
0x180016d40  test    rax, rax
0x180016d43  jz      short loc_180016D89
0x180016d45  mov     rdx, qword ptr cs:xmmword_1801AF200+8; h
0x180016d4c  xor     r8d, r8d; pftTimeout
0x180016d4f  mov     rcx, rax; pwa
0x180016d52  call    cs:__imp_SetThreadpoolWait
0x180016d58  mov     edi, 1
0x180016d5d  jmp     loc_180016E07
0x180016d62  mov     rax, qword ptr cs:hMem+8
0x180016d69  test    rax, rax
0x180016d6c  jz      short loc_180016D89
0x180016d6e  mov     edx, 1; fCancelPendingCallbacks
0x180016d73  mov     rcx, rax; pwa
0x180016d76  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180016d7c  mov     rcx, qword ptr cs:hMem+8; pwa
0x180016d83  call    cs:__imp_CloseThreadpoolWait
0x180016d89  mov     rbx, qword ptr cs:hMem
0x180016d90  test    rbx, rbx
0x180016d93  jz      short loc_180016DE4
0x180016d95  lea     rcx, SRWLock; SRWLock
0x180016d9c  call    cs:__imp_AcquireSRWLockExclusive
0x180016da2  mov     rdx, [rbx]
0x180016da5  cmp     [rdx+8], rbx
0x180016da9  jnz     loc_180016E32
0x180016daf  mov     rax, [rbx+8]
0x180016db3  cmp     [rax], rbx
0x180016db6  jnz     short loc_180016E32
0x180016db8  mov     [rax], rdx
0x180016dbb  lea     rcx, SRWLock; SRWLock
0x180016dc2  mov     [rdx+8], rax
0x180016dc6  call    cs:__imp_ReleaseSRWLockExclusive
0x180016dcc  mov     rcx, [rbx+28h]
0x180016dd0  test    rcx, rcx
0x180016dd3  jz      short loc_180016DDB
0x180016dd5  call    cs:__imp_I_ScUnregisterDeviceNotification
0x180016ddb  mov     rcx, rbx; hMem
0x180016dde  call    cs:__imp_LocalFree
0x180016de4  mov     rcx, qword ptr cs:xmmword_1801AF200+8; hObject
0x180016deb  test    rcx, rcx
0x180016dee  jz      short loc_180016DF6
0x180016df0  call    cs:__imp_CloseHandle
0x180016df6  xorps   xmm0, xmm0
0x180016df9  movups  cs:xmmword_1801AF200, xmm0
0x180016e00  movups  cs:hMem, xmm0
0x180016e07  mov     dword ptr cs:xmmword_1801AF200, edi
0x180016e0d  lea     rcx, stru_1801AF250; SRWLock
0x180016e14  call    cs:__imp_ReleaseSRWLockExclusive
0x180016e1a  mov     rcx, [rsp+48h+var_18]
0x180016e1f  xor     rcx, rsp; StackCookie
0x180016e22  call    __security_check_cookie
0x180016e27  mov     rbx, [rsp+48h+arg_0]
0x180016e2c  add     rsp, 40h
0x180016e30  pop     rdi
0x180016e31  retn
0x180016e32  mov     ecx, 3
0x180016e37  int     29h; Win8: RtlFailFast(ecx)
```
