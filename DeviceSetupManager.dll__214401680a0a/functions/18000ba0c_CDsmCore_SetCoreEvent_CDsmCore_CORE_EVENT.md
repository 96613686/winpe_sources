# CDsmCore::_SetCoreEvent(CDsmCore::CORE_EVENT)

- ea: `0x18000ba0c`
- end: `0x18000bd94`
- name: `?_SetCoreEvent@CDsmCore@@AEAAXW4CORE_EVENT@1@@Z`
- size: `904`
- prototype: `void __fastcall(__int64, int, __int64)`
- caller_count: `5`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000b9dc`
- `0x180017e80`
- `0x180022000`
- `0x1800240dc`
- `0x180024374`

## callees

- `0x180009fb0`
- `0x18000ba0c`
- `0x18000f2bc`
- `0x1800164d0`
- `0x18001870c`
- `0x18001af70`
- `0x180021790`
- `0x180024f4c`
- `0x180025214`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000bbe7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000bbe7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bb55`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bbce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bb55`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bbce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bb42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bbbc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bb42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bbbc`

## string_xrefs

- `0x18000ba5d`: `SERVICE_STARTED`
- `0x18000ba87`: `JOB_COMPLETE`

## pseudocode

```c
void __fastcall CDsmCore::_SetCoreEvent(__int64 a1, int a2, __int64 a3)
{
  const wchar_t *v5; // rax
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // ebp
  int v14; // esi
  __int64 v15; // rcx
  const wchar_t *v16; // rax
  const wchar_t *v17; // rax
  bool v18; // [rsp+30h] [rbp-38h] BYREF
  bool v19; // [rsp+31h] [rbp-37h] BYREF
  _BYTE v20[16]; // [rsp+38h] [rbp-30h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    switch ( a2 )
    {
      case 1:
        v5 = L"SERVICE_STARTED";
        break;
      case 6:
        v5 = L"SHUTDOWN_REQUEST";
        break;
      case 3:
        v5 = L"JOB_QUEUED";
        break;
      case 4:
        v5 = L"JOB_COMPLETE";
        break;
      case 2:
        v5 = L"TIMEOUT";
        break;
      default:
        v5 = L"NETWORK_AVAILABLE";
        if ( a2 != 5 )
          v5 = L"???";
        break;
    }
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)&WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids,
      a2,
      (__int64)v5);
  }
  v18 = 0;
  v19 = 0;
  v6 = a2 - 1;
  if ( !v6 )
  {
    v11 = 1;
    goto LABEL_65;
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          if ( v10 != 1 )
            return;
          v11 = 15;
          v12 = 128;
        }
        else
        {
          if ( (Microsoft_Windows_DeviceSetupManagerEnableBits & 1) != 0 )
            McGenEventWrite_EventWriteTransfer(
              &MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context,
              NetworkAvailable,
              a3,
              1,
              v20);
          AcquireSRWLockExclusive((PSRWLOCK)(a1 + 168));
          *(_DWORD *)(a1 + 180) = 0;
          ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 168));
          v11 = 8;
          v12 = 8;
        }
      }
      else
      {
        ContainerManager::PostSetupCycleAction(*(ContainerManager **)(a1 + 272), &v18, &v19);
        if ( v18 )
          return;
        v11 = 4;
        v12 = v19 ? 8 : 2;
      }
    }
    else
    {
      v11 = 15;
      v12 = 4;
    }
    goto LABEL_66;
  }
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 168));
  v13 = *(_DWORD *)(a1 + 176);
  v14 = *(_DWORD *)(a1 + 48);
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 168));
  if ( v13 == 2 )
  {
    if ( *(_DWORD *)(a1 + 48) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        switch ( v14 )
        {
          case 1:
            v16 = L"PAUSED";
            break;
          case 2:
            v16 = L"IN_SETUP";
            break;
          case 3:
            v16 = L"IN_OOBE";
            break;
          default:
            v16 = L"IN_AUDIT";
            if ( v14 != 4 )
              v16 = L"???";
            break;
        }
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)&WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids,
          v14,
          (__int64)v16);
      }
    }
    else
    {
      SetEvent(*(HANDLE *)(a1 + 64));
    }
    return;
  }
  if ( v13 != 8 )
    return;
  if ( (Microsoft_Windows_DeviceSetupManagerEnableBits & 1) != 0 )
    McTemplateU0q_EventWriteTransfer(v15, RetrySequenceStart, *(unsigned int *)(a1 + 524));
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      switch ( v14 )
      {
        case 1:
          v17 = L"PAUSED";
          break;
        case 2:
          v17 = L"IN_SETUP";
          break;
        case 3:
          v17 = L"IN_OOBE";
          break;
        default:
          v17 = L"IN_AUDIT";
          if ( v14 != 4 )
            v17 = L"???";
          break;
      }
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)&WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids,
        v14,
        (__int64)v17);
    }
    goto LABEL_63;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids);
  if ( (int)ContainerManager::RefreshContainers(*(RTL_SRWLOCK **)(a1 + 272), 4u, 0) < 0 )
  {
LABEL_63:
    v11 = 8;
LABEL_65:
    v12 = 2;
LABEL_66:
    CDsmCore::_SwitchServiceState(a1, v11, v12);
  }
}

```

## disassembly

```asm
0x18000ba0c  mov     [rsp+arg_10], rbx
0x18000ba11  mov     [rsp+arg_18], rbp
0x18000ba16  push    rsi
0x18000ba17  push    rdi
0x18000ba18  push    r14
0x18000ba1a  sub     rsp, 50h
0x18000ba1e  mov     rax, cs:__security_cookie
0x18000ba25  xor     rax, rsp
0x18000ba28  mov     [rsp+68h+var_20], rax
0x18000ba2d  mov     ebx, edx
0x18000ba2f  mov     rdi, rcx
0x18000ba32  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba39  lea     rax, WPP_GLOBAL_Control
0x18000ba40  lea     rdx, asc_18004CE68; "???"
0x18000ba47  mov     r14d, 1
0x18000ba4d  cmp     rcx, rax
0x18000ba50  jz      short loc_18000BAC9
0x18000ba52  test    [rcx+1Ch], r14b
0x18000ba56  jz      short loc_18000BAC9
0x18000ba58  cmp     ebx, r14d
0x18000ba5b  jnz     short loc_18000BA66
0x18000ba5d  lea     rax, aServiceStarted; "SERVICE_STARTED"
0x18000ba64  jmp     short loc_18000BAAC
0x18000ba66  cmp     ebx, 6
0x18000ba69  jnz     short loc_18000BA74
0x18000ba6b  lea     rax, aShutdownReques; "SHUTDOWN_REQUEST"
0x18000ba72  jmp     short loc_18000BAAC
0x18000ba74  cmp     ebx, 3
0x18000ba77  jnz     short loc_18000BA82
0x18000ba79  lea     rax, aJobQueued; "JOB_QUEUED"
0x18000ba80  jmp     short loc_18000BAAC
0x18000ba82  cmp     ebx, 4
0x18000ba85  jnz     short loc_18000BA90
0x18000ba87  lea     rax, aJobComplete; "JOB_COMPLETE"
0x18000ba8e  jmp     short loc_18000BAAC
0x18000ba90  cmp     ebx, 2
0x18000ba93  jnz     short loc_18000BA9E
0x18000ba95  lea     rax, aTimeout; "TIMEOUT"
0x18000ba9c  jmp     short loc_18000BAAC
0x18000ba9e  cmp     ebx, 5
0x18000baa1  lea     rax, aNetworkAvailab; "NETWORK_AVAILABLE"
0x18000baa8  cmovnz  rax, rdx
0x18000baac  mov     rcx, [rcx+10h]
0x18000bab0  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x18000bab7  mov     edx, 13h
0x18000babc  mov     [rsp+68h+var_48], rax
0x18000bac1  mov     r9d, ebx
0x18000bac4  call    WPP_SF_dS
0x18000bac9  mov     [rsp+68h+var_38], 0
0x18000bace  mov     [rsp+68h+var_37], 0
0x18000bad3  sub     ebx, r14d
0x18000bad6  jz      loc_18000BD61
0x18000badc  sub     ebx, r14d
0x18000badf  jz      loc_18000BBB2
0x18000bae5  sub     ebx, r14d
0x18000bae8  jz      loc_18000BBA4
0x18000baee  sub     ebx, r14d
0x18000baf1  jz      short loc_18000BB68
0x18000baf3  sub     ebx, r14d
0x18000baf6  jz      short loc_18000BB0F
0x18000baf8  cmp     ebx, r14d
0x18000bafb  jnz     loc_18000BD72
0x18000bb01  mov     edx, 0Fh
0x18000bb06  lea     r8d, [rdx+71h]
0x18000bb0a  jmp     loc_18000BD6A
0x18000bb0f  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, r14b
0x18000bb16  jz      short loc_18000BB38
0x18000bb18  lea     rax, [rsp+68h+var_30]
0x18000bb1d  mov     r9d, r14d
0x18000bb20  lea     rdx, NetworkAvailable
0x18000bb27  mov     [rsp+68h+var_48], rax
0x18000bb2c  lea     rcx, MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context
0x18000bb33  call    McGenEventWrite_EventWriteTransfer
0x18000bb38  lea     rbx, [rdi+0A8h]
0x18000bb3f  mov     rcx, rbx; SRWLock
0x18000bb42  call    cs:__imp_AcquireSRWLockExclusive
0x18000bb48  mov     rcx, rbx; SRWLock
0x18000bb4b  mov     dword ptr [rdi+0B4h], 0
0x18000bb55  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bb5b  mov     edx, 8
0x18000bb60  mov     r8d, edx
0x18000bb63  jmp     loc_18000BD6A
0x18000bb68  mov     rcx, [rdi+110h]; this
0x18000bb6f  lea     r8, [rsp+68h+var_37]; bool *
0x18000bb74  lea     rdx, [rsp+68h+var_38]; bool *
0x18000bb79  call    ?PostSetupCycleAction@ContainerManager@@QEAAXPEA_N0@Z; ContainerManager::PostSetupCycleAction(bool *,bool *)
0x18000bb7e  cmp     [rsp+68h+var_38], 0
0x18000bb83  jnz     loc_18000BD72
0x18000bb89  mov     al, [rsp+68h+var_37]
0x18000bb8d  mov     edx, 4
0x18000bb92  neg     al
0x18000bb94  sbb     r8d, r8d
0x18000bb97  and     r8d, 6
0x18000bb9b  add     r8d, 2
0x18000bb9f  jmp     loc_18000BD6A
0x18000bba4  mov     edx, 0Fh
0x18000bba9  lea     r8d, [rdx-0Bh]
0x18000bbad  jmp     loc_18000BD6A
0x18000bbb2  lea     rbx, [rdi+0A8h]
0x18000bbb9  mov     rcx, rbx; SRWLock
0x18000bbbc  call    cs:__imp_AcquireSRWLockExclusive
0x18000bbc2  mov     ebp, [rdi+0B0h]
0x18000bbc8  mov     rcx, rbx; SRWLock
0x18000bbcb  mov     esi, [rdi+30h]
0x18000bbce  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bbd4  cmp     ebp, 2
0x18000bbd7  jnz     loc_18000BC74
0x18000bbdd  cmp     dword ptr [rdi+30h], 0
0x18000bbe1  jnz     short loc_18000BBF2
0x18000bbe3  mov     rcx, [rdi+40h]; hEvent
0x18000bbe7  call    cs:__imp_SetEvent
0x18000bbed  jmp     loc_18000BD72
0x18000bbf2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bbf9  lea     rax, WPP_GLOBAL_Control
0x18000bc00  cmp     rcx, rax
0x18000bc03  jz      loc_18000BD72
0x18000bc09  test    [rcx+1Ch], r14b
0x18000bc0d  jz      loc_18000BD72
0x18000bc13  cmp     esi, r14d
0x18000bc16  jnz     short loc_18000BC21
0x18000bc18  lea     rax, aPaused; "PAUSED"
0x18000bc1f  jmp     short loc_18000BC52
0x18000bc21  cmp     esi, 2
0x18000bc24  jnz     short loc_18000BC2F
0x18000bc26  lea     rax, aInSetup; "IN_SETUP"
0x18000bc2d  jmp     short loc_18000BC52
0x18000bc2f  cmp     esi, 3
0x18000bc32  jnz     short loc_18000BC3D
0x18000bc34  lea     rax, aInOobe; "IN_OOBE"
0x18000bc3b  jmp     short loc_18000BC52
0x18000bc3d  cmp     esi, 4
0x18000bc40  lea     rax, aInAudit; "IN_AUDIT"
0x18000bc47  lea     rdx, asc_18004CE68; "???"
0x18000bc4e  cmovnz  rax, rdx
0x18000bc52  mov     rcx, [rcx+10h]
0x18000bc56  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x18000bc5d  mov     edx, 14h
0x18000bc62  mov     [rsp+68h+var_48], rax
0x18000bc67  mov     r9d, esi
0x18000bc6a  call    WPP_SF_dS
0x18000bc6f  jmp     loc_18000BD72
0x18000bc74  cmp     ebp, 8
0x18000bc77  jnz     loc_18000BD72
0x18000bc7d  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, r14b
0x18000bc84  jz      short loc_18000BC99
0x18000bc86  mov     r8d, [rdi+20Ch]
0x18000bc8d  lea     rdx, RetrySequenceStart
0x18000bc94  call    McTemplateU0q_EventWriteTransfer
0x18000bc99  test    esi, esi
0x18000bc9b  jnz     short loc_18000BCE5
0x18000bc9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bca4  lea     rax, WPP_GLOBAL_Control
0x18000bcab  cmp     rcx, rax
0x18000bcae  jz      short loc_18000BCC9
0x18000bcb0  test    [rcx+1Ch], r14b
0x18000bcb4  jz      short loc_18000BCC9
0x18000bcb6  mov     rcx, [rcx+10h]
0x18000bcba  lea     edx, [rsi+15h]
0x18000bcbd  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x18000bcc4  call    WPP_SF_
0x18000bcc9  mov     rcx, [rdi+110h]
0x18000bcd0  xor     r8d, r8d
0x18000bcd3  lea     edx, [r8+4]
0x18000bcd7  call    ?RefreshContainers@ContainerManager@@QEAAJW4DSM_REFRESH_TYPE@@PEBG@Z; ContainerManager::RefreshContainers(DSM_REFRESH_TYPE,ushort const *)
0x18000bcdc  test    eax, eax
0x18000bcde  js      short loc_18000BD5A
0x18000bce0  jmp     loc_18000BD72
0x18000bce5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcec  lea     rax, WPP_GLOBAL_Control
0x18000bcf3  cmp     rcx, rax
0x18000bcf6  jz      short loc_18000BD5A
0x18000bcf8  test    [rcx+1Ch], r14b
0x18000bcfc  jz      short loc_18000BD5A
0x18000bcfe  cmp     esi, r14d
0x18000bd01  jnz     short loc_18000BD0C
0x18000bd03  lea     rax, aPaused; "PAUSED"
0x18000bd0a  jmp     short loc_18000BD3D
0x18000bd0c  cmp     esi, 2
0x18000bd0f  jnz     short loc_18000BD1A
0x18000bd11  lea     rax, aInSetup; "IN_SETUP"
0x18000bd18  jmp     short loc_18000BD3D
0x18000bd1a  cmp     esi, 3
0x18000bd1d  jnz     short loc_18000BD28
0x18000bd1f  lea     rax, aInOobe; "IN_OOBE"
0x18000bd26  jmp     short loc_18000BD3D
0x18000bd28  cmp     esi, 4
0x18000bd2b  lea     rax, aInAudit; "IN_AUDIT"
0x18000bd32  lea     rdx, asc_18004CE68; "???"
0x18000bd39  cmovnz  rax, rdx
0x18000bd3d  mov     rcx, [rcx+10h]
0x18000bd41  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x18000bd48  mov     edx, 16h
0x18000bd4d  mov     [rsp+68h+var_48], rax
0x18000bd52  mov     r9d, esi
0x18000bd55  call    WPP_SF_dS
0x18000bd5a  mov     edx, 8
0x18000bd5f  jmp     short loc_18000BD64
0x18000bd61  mov     edx, r14d
0x18000bd64  mov     r8d, 2
0x18000bd6a  mov     rcx, rdi
0x18000bd6d  call    ?_SwitchServiceState@CDsmCore@@AEAAXW4DSM_SERVICE_STATE@@0@Z; CDsmCore::_SwitchServiceState(DSM_SERVICE_STATE,DSM_SERVICE_STATE)
0x18000bd72  mov     rcx, [rsp+68h+var_20]
0x18000bd77  xor     rcx, rsp; StackCookie
0x18000bd7a  call    __security_check_cookie
0x18000bd7f  lea     r11, [rsp+68h+var_18]
0x18000bd84  mov     rbx, [r11+30h]
0x18000bd88  mov     rbp, [r11+38h]
0x18000bd8c  mov     rsp, r11
0x18000bd8f  pop     r14
0x18000bd91  pop     rdi
0x18000bd92  pop     rsi
0x18000bd93  retn
```
