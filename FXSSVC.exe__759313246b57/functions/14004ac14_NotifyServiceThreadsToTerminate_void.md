# NotifyServiceThreadsToTerminate(void)

- ea: `0x14004ac14`
- end: `0x14004ae5d`
- name: `?NotifyServiceThreadsToTerminate@@YAHXZ`
- size: `585`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140049678`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x14004ac14`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004ac88`
- `KERNEL32!GetLastError` at `0x14004acf3`
- `KERNEL32!GetLastError` at `0x14004ad58`
- `KERNEL32!GetLastError` at `0x14004adc1`
- `KERNEL32!GetLastError` at `0x14004ae26`
- `KERNEL32!GetLastError` at `0x14004ac88`
- `KERNEL32!GetLastError` at `0x14004acf3`
- `KERNEL32!GetLastError` at `0x14004ad58`
- `KERNEL32!GetLastError` at `0x14004adc1`
- `KERNEL32!GetLastError` at `0x14004ae26`
- `KERNEL32!SetEvent` at `0x14004ac60`
- `KERNEL32!SetEvent` at `0x14004ac60`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14004accb`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14004ad30`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14004ad99`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14004adfe`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14004accb`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14004ad30`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14004ad99`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14004adfe`

## pseudocode

```c
__int64 NotifyServiceThreadsToTerminate(void)
{
  unsigned int v0; // ebx
  DWORD LastError; // eax
  DWORD v2; // eax
  DWORD v3; // eax
  void *v4; // rcx
  DWORD v5; // eax
  DWORD v6; // eax

  v0 = 1;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
  }
  if ( !SetEvent(g_hServiceShutDownEvent) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, LastError);
    }
    v0 = 0;
  }
  if ( g_hSendEventsCompPort && !PostQueuedCompletionStatus(g_hSendEventsCompPort, 0, 0xFFFFFFFF, 0) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v2 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v2);
    }
    v0 = 0;
  }
  if ( g_hDispatchEventsCompPort && !PostQueuedCompletionStatus(g_hDispatchEventsCompPort, 0, 0xFFFFFFFF, 0) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v3);
    }
    v0 = 0;
  }
  v4 = (void *)*((_QWORD *)g_pNotificationMap + 1);
  if ( v4 && !PostQueuedCompletionStatus(v4, 0, 0xFFFFFFFF, 0) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v5);
    }
    v0 = 0;
  }
  if ( g_StatusCompletionPortHandle && !PostQueuedCompletionStatus(g_StatusCompletionPortHandle, 0, 0xFFFFFFFF, 0) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v6);
    }
    return 0;
  }
  return v0;
}

```

## disassembly

```asm
0x14004ac14  push    rbx
0x14004ac16  push    rsi
0x14004ac17  push    r14
0x14004ac19  push    r15
0x14004ac1b  sub     rsp, 28h
0x14004ac1f  mov     ebx, 1
0x14004ac24  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ac2b  lea     rsi, WPP_GLOBAL_Control
0x14004ac32  lea     r14, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x14004ac39  cmp     rcx, rsi
0x14004ac3c  jz      short loc_14004AC59
0x14004ac3e  test    byte ptr [rcx+1Ch], 4
0x14004ac42  jz      short loc_14004AC59
0x14004ac44  cmp     byte ptr [rcx+19h], 5
0x14004ac48  jb      short loc_14004AC59
0x14004ac4a  mov     rcx, [rcx+10h]
0x14004ac4e  lea     edx, [rbx+2Dh]
0x14004ac51  mov     r8, r14
0x14004ac54  call    WPP_SF_
0x14004ac59  mov     rcx, cs:?g_hServiceShutDownEvent@@3PEAXEA; hEvent
0x14004ac60  call    cs:__imp_SetEvent
0x14004ac67  nop     dword ptr [rax+rax+00h]
0x14004ac6c  test    eax, eax
0x14004ac6e  jnz     short loc_14004ACB1
0x14004ac70  mov     rax, cs:WPP_GLOBAL_Control
0x14004ac77  cmp     rax, rsi
0x14004ac7a  jz      short loc_14004ACAF
0x14004ac7c  test    byte ptr [rax+1Ch], 4
0x14004ac80  jz      short loc_14004ACAF
0x14004ac82  cmp     byte ptr [rax+19h], 2
0x14004ac86  jb      short loc_14004ACAF
0x14004ac88  call    cs:__imp_GetLastError
0x14004ac8f  nop     dword ptr [rax+rax+00h]
0x14004ac94  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ac9b  mov     edx, 2Fh ; '/'
0x14004aca0  mov     r9d, eax
0x14004aca3  mov     r8, r14
0x14004aca6  mov     rcx, [rcx+10h]
0x14004acaa  call    WPP_SF_d
0x14004acaf  xor     ebx, ebx
0x14004acb1  mov     rcx, cs:?g_hSendEventsCompPort@@3PEAXEA; CompletionPort
0x14004acb8  mov     r15d, 0FFFFFFFFh
0x14004acbe  test    rcx, rcx
0x14004acc1  jz      short loc_14004AD1C
0x14004acc3  xor     r9d, r9d; lpOverlapped
0x14004acc6  mov     r8d, r15d; dwCompletionKey
0x14004acc9  xor     edx, edx; dwNumberOfBytesTransferred
0x14004accb  call    cs:__imp_PostQueuedCompletionStatus
0x14004acd2  nop     dword ptr [rax+rax+00h]
0x14004acd7  test    eax, eax
0x14004acd9  jnz     short loc_14004AD1C
0x14004acdb  mov     rax, cs:WPP_GLOBAL_Control
0x14004ace2  cmp     rax, rsi
0x14004ace5  jz      short loc_14004AD1A
0x14004ace7  test    byte ptr [rax+1Ch], 4
0x14004aceb  jz      short loc_14004AD1A
0x14004aced  cmp     byte ptr [rax+19h], 2
0x14004acf1  jb      short loc_14004AD1A
0x14004acf3  call    cs:__imp_GetLastError
0x14004acfa  nop     dword ptr [rax+rax+00h]
0x14004acff  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ad06  mov     edx, 30h ; '0'
0x14004ad0b  mov     r9d, eax
0x14004ad0e  mov     r8, r14
0x14004ad11  mov     rcx, [rcx+10h]
0x14004ad15  call    WPP_SF_d
0x14004ad1a  xor     ebx, ebx
0x14004ad1c  mov     rcx, cs:?g_hDispatchEventsCompPort@@3PEAXEA; CompletionPort
0x14004ad23  test    rcx, rcx
0x14004ad26  jz      short loc_14004AD81
0x14004ad28  xor     r9d, r9d; lpOverlapped
0x14004ad2b  mov     r8, r15; dwCompletionKey
0x14004ad2e  xor     edx, edx; dwNumberOfBytesTransferred
0x14004ad30  call    cs:__imp_PostQueuedCompletionStatus
0x14004ad37  nop     dword ptr [rax+rax+00h]
0x14004ad3c  test    eax, eax
0x14004ad3e  jnz     short loc_14004AD81
0x14004ad40  mov     rax, cs:WPP_GLOBAL_Control
0x14004ad47  cmp     rax, rsi
0x14004ad4a  jz      short loc_14004AD7F
0x14004ad4c  test    byte ptr [rax+1Ch], 4
0x14004ad50  jz      short loc_14004AD7F
0x14004ad52  cmp     byte ptr [rax+19h], 2
0x14004ad56  jb      short loc_14004AD7F
0x14004ad58  call    cs:__imp_GetLastError
0x14004ad5f  nop     dword ptr [rax+rax+00h]
0x14004ad64  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ad6b  mov     edx, 31h ; '1'
0x14004ad70  mov     r9d, eax
0x14004ad73  mov     r8, r14
0x14004ad76  mov     rcx, [rcx+10h]
0x14004ad7a  call    WPP_SF_d
0x14004ad7f  xor     ebx, ebx
0x14004ad81  mov     rax, cs:?g_pNotificationMap@@3PEAVCNotificationMap@@EA; CNotificationMap * g_pNotificationMap
0x14004ad88  mov     rcx, [rax+8]; CompletionPort
0x14004ad8c  test    rcx, rcx
0x14004ad8f  jz      short loc_14004ADEA
0x14004ad91  xor     r9d, r9d; lpOverlapped
0x14004ad94  mov     r8, r15; dwCompletionKey
0x14004ad97  xor     edx, edx; dwNumberOfBytesTransferred
0x14004ad99  call    cs:__imp_PostQueuedCompletionStatus
0x14004ada0  nop     dword ptr [rax+rax+00h]
0x14004ada5  test    eax, eax
0x14004ada7  jnz     short loc_14004ADEA
0x14004ada9  mov     rax, cs:WPP_GLOBAL_Control
0x14004adb0  cmp     rax, rsi
0x14004adb3  jz      short loc_14004ADE8
0x14004adb5  test    byte ptr [rax+1Ch], 4
0x14004adb9  jz      short loc_14004ADE8
0x14004adbb  cmp     byte ptr [rax+19h], 2
0x14004adbf  jb      short loc_14004ADE8
0x14004adc1  call    cs:__imp_GetLastError
0x14004adc8  nop     dword ptr [rax+rax+00h]
0x14004adcd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004add4  mov     edx, 32h ; '2'
0x14004add9  mov     r9d, eax
0x14004addc  mov     r8, r14
0x14004addf  mov     rcx, [rcx+10h]
0x14004ade3  call    WPP_SF_d
0x14004ade8  xor     ebx, ebx
0x14004adea  mov     rcx, cs:?g_StatusCompletionPortHandle@@3PEAXEA; CompletionPort
0x14004adf1  test    rcx, rcx
0x14004adf4  jz      short loc_14004AE4F
0x14004adf6  xor     r9d, r9d; lpOverlapped
0x14004adf9  mov     r8, r15; dwCompletionKey
0x14004adfc  xor     edx, edx; dwNumberOfBytesTransferred
0x14004adfe  call    cs:__imp_PostQueuedCompletionStatus
0x14004ae05  nop     dword ptr [rax+rax+00h]
0x14004ae0a  test    eax, eax
0x14004ae0c  jnz     short loc_14004AE4F
0x14004ae0e  mov     rax, cs:WPP_GLOBAL_Control
0x14004ae15  cmp     rax, rsi
0x14004ae18  jz      short loc_14004AE4D
0x14004ae1a  test    byte ptr [rax+1Ch], 4
0x14004ae1e  jz      short loc_14004AE4D
0x14004ae20  cmp     byte ptr [rax+19h], 2
0x14004ae24  jb      short loc_14004AE4D
0x14004ae26  call    cs:__imp_GetLastError
0x14004ae2d  nop     dword ptr [rax+rax+00h]
0x14004ae32  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ae39  mov     edx, 33h ; '3'
0x14004ae3e  mov     r9d, eax
0x14004ae41  mov     r8, r14
0x14004ae44  mov     rcx, [rcx+10h]
0x14004ae48  call    WPP_SF_d
0x14004ae4d  xor     ebx, ebx
0x14004ae4f  mov     eax, ebx
0x14004ae51  add     rsp, 28h
0x14004ae55  pop     r15
0x14004ae57  pop     r14
0x14004ae59  pop     rsi
0x14004ae5a  pop     rbx
0x14004ae5b  retn
```
