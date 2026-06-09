# CDsmTask::_SetupUXProgressThread(void)

- ea: `0x180008e20`
- end: `0x1800094f0`
- name: `?_SetupUXProgressThread@CDsmTask@@AEAAXXZ`
- size: `1744`
- prototype: `void __fastcall __noreturn(CDsmTask *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180018650`

## callees

- `0x180008dcc`
- `0x180008e20`
- `0x180009500`
- `0x180009640`
- `0x1800097e4`
- `0x180009928`
- `0x180009fb0`
- `0x18000a004`
- `0x18000a330`
- `0x18000d2e0`
- `0x180016d60`
- `0x180021790`
- `0x180022070`
- `0x180025214`
- `0x180027ba8`
- `0x18003153c`
- `0x18003f368`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180009290`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180009290`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008ec9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008ec9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000923f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000923f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009008`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000911a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009285`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009008`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000911a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009285`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008f02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800090fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000920b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008f02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800090fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000920b`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x18000918e`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x18000918e`

## pseudocode

```c
void __fastcall __noreturn CDsmTask::_SetupUXProgressThread(CDsmTask *this)
{
  __int64 v2; // r9
  PVOID *v3; // rcx
  DWORD v4; // esi
  int v5; // r14d
  DWORD v6; // eax
  DWORD v7; // ebx
  int v8; // r8d
  int v9; // edx
  int v10; // r8d
  int v11; // ebx
  unsigned int v12; // esi
  int v13; // r14d
  __int64 v14; // r8
  __int64 v15; // r14
  int v16; // r15d
  int v17; // eax
  int v18; // r8d
  HMODULE v19; // rbx
  void *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rcx
  bool IsNetworkCosted; // al
  int v24; // eax
  char v25; // [rsp+40h] [rbp-59h] BYREF
  int v26; // [rsp+48h] [rbp-51h]
  int v27; // [rsp+50h] [rbp-49h]
  _DWORD v28[4]; // [rsp+58h] [rbp-41h] BYREF
  _DWORD v29[4]; // [rsp+68h] [rbp-31h] BYREF
  DEVPROPGUID fmtid; // [rsp+78h] [rbp-21h] BYREF
  __int128 pid; // [rsp+88h] [rbp-11h]
  __int64 v32; // [rsp+98h] [rbp-1h]
  char *v33; // [rsp+A0h] [rbp+7h]

  v2 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 85);
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids, v2);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  v4 = 500;
  v5 = 0;
  v27 = 500;
  while ( 1 )
  {
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x10) != 0 )
      WPP_SF_(v3[2], 28, &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids);
    v6 = WaitForSingleObject(*((HANDLE *)this + 48), v4);
    v7 = v6;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids, v6);
    AcquireSRWLockExclusive((PSRWLOCK)this + 45);
    if ( v7 == 258 && *((_BYTE *)this + 428) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids,
          (char *)this + 24);
      *((_DWORD *)this + 93) = 3;
    }
    else
    {
      v8 = *((_DWORD *)this + 93);
      v9 = *((_DWORD *)this + 92);
      if ( v9 == v8 )
      {
        if ( *((_BYTE *)this + 428) )
        {
          v10 = v8 - 1;
          if ( v10 )
          {
            if ( v10 == 1 )
            {
              v4 = 7000;
              goto LABEL_27;
            }
          }
          else
          {
            v4 = 2000;
LABEL_27:
            v27 = v4;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_dS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              32,
              (unsigned int)&WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids,
              v4,
              (__int64)this + 24);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_ddS(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v8, v8, v9, (__int64)this + 24);
        *((_DWORD *)this + 93) = *((_DWORD *)this + 92);
      }
    }
    v11 = *((_DWORD *)this + 93);
    v12 = *((_DWORD *)this + 103);
    ReleaseSRWLockExclusive((PSRWLOCK)this + 45);
    if ( v5 == v11 )
    {
      switch ( v11 )
      {
        case 1:
          if ( v12 != *((_DWORD *)this + 104) )
          {
            v29[2] = 0;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids, v12);
            v29[0] = 0;
            v29[1] = v12;
            CDevNotify::s_BroadcastProgress(
              (const struct _GUID *)((char *)this + 8),
              (const struct DDO_PROGRESS_REPORT *)v29);
            *((_DWORD *)this + 104) = v12;
          }
          goto LABEL_92;
        case 2:
          if ( *((_DWORD *)this + 94) == 1 )
          {
            v3 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids);
              v3 = (PVOID *)WPP_GLOBAL_Control;
            }
            v24 = *((_DWORD *)this + 95);
            if ( v24 == 4 )
            {
              if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x10) != 0 )
                WPP_SF_(v3[2], 36, &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids);
              v26 = 5;
            }
            else
            {
              if ( v24 != 3 )
                goto LABEL_93;
              if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x10) != 0 )
                WPP_SF_(v3[2], 37, &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids);
              v26 = 6;
            }
            SetDeviceObjectProperty(2, (char *)this + 24, &DEVPKEY_DeviceSetup_DeviceState);
            *((_DWORD *)this + 94) = 3;
          }
          goto LABEL_92;
        case 3:
LABEL_54:
          AcquireSRWLockExclusive((PSRWLOCK)this + 45);
          v19 = (HMODULE)*((_QWORD *)this + 50);
          v20 = (void *)*((_QWORD *)this + 49);
          *(_QWORD *)((char *)this + 420) = 0;
          *((_DWORD *)this + 93) = 0;
          *((_QWORD *)this + 50) = 0;
          SetEvent(v20);
          v21 = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)this + 85);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids, v21);
          ReleaseSRWLockExclusive((PSRWLOCK)this + 45);
          FreeLibraryAndExitThread(v19, 0);
      }
      v3 = (PVOID *)WPP_GLOBAL_Control;
      v5 = v11;
      v4 = v27;
    }
    else
    {
      v13 = v5 - 1;
      if ( v13 )
      {
        if ( v13 == 1 )
        {
          v3 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids);
            v3 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( *((_DWORD *)this + 94) != 3 )
            goto LABEL_51;
          v26 = 7;
          SetDeviceObjectProperty(2, (char *)this + 24, &DEVPKEY_DeviceSetup_DeviceState);
        }
        goto LABEL_50;
      }
      CDsmTask::_CompleteDevNotifyProgress(this);
      if ( Microsoft_Windows_DeviceSetupManagerEnableBits < 0 )
      {
        *((_QWORD *)&pid + 1) = 16;
        *(_QWORD *)&pid = (char *)this + 8;
        McGenEventWrite_EventWriteTransfer(
          &MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context,
          DeviceSetupTaskStop,
          v14,
          2,
          &fmtid);
      }
      CDsmTask::_LogDeviceInformation((DsmSetupRecorder **)this);
      v15 = *((_QWORD *)this + 44);
      v16 = *((_DWORD *)this + 82);
      AcquireSRWLockExclusive((PSRWLOCK)(v15 + 8));
      if ( *(_BYTE *)(v15 + 4) )
      {
        *(_DWORD *)(v15 + 40) = v16;
        if ( v15 == -8 )
          goto LABEL_46;
LABEL_45:
        ReleaseSRWLockExclusive((PSRWLOCK)(v15 + 8));
        goto LABEL_46;
      }
      if ( v15 != -8 )
        goto LABEL_45;
LABEL_46:
      DsmSetupRecorder::RecordInstallResults(*((DsmSetupRecorder **)this + 44));
      v25 = 0;
      v33 = &v25;
      v32 = 0x100000011LL;
      fmtid = DEVPKEY_DeviceSetup_InstallInProgress.fmtid;
      pid = DEVPKEY_DeviceSetup_InstallInProgress.pid;
      v17 = DevSetObjectProperties(2, (char *)this + 24, 1, &fmtid);
      if ( v17 < 0 )
      {
        v3 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_51;
        WPP_SF__guid_dSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          v18,
          (unsigned int)&DEVPKEY_DeviceSetup_InstallInProgress,
          2,
          (__int64)this + 24,
          v17);
      }
LABEL_50:
      v3 = (PVOID *)WPP_GLOBAL_Control;
LABEL_51:
      switch ( v11 )
      {
        case 1:
          *((_DWORD *)this + 104) = -1;
          v28[2] = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids);
          v28[0] = 1;
          v28[1] = 2;
          CDevNotify::s_BroadcastProgress(
            (const struct _GUID *)((char *)this + 8),
            (const struct DDO_PROGRESS_REPORT *)v28);
          if ( Microsoft_Windows_DeviceSetupManagerEnableBits < 0 )
            McTemplateU0j_EventWriteTransfer(v22, DeviceSetupTaskStart, (char *)this + 8);
          SetContainerBoolean((const unsigned __int16 *)this + 12, &DEVPKEY_DeviceSetup_InstallInProgress, 1);
          DsmSetupRecorder::RecorderReset(*((DsmSetupRecorder **)this + 44));
          IsNetworkCosted = CNetworkEvents::IsNetworkCosted((CNetworkEvents *)&g_DsmCore);
          v5 = 1;
          v4 = v27;
          **((_DWORD **)this + 44) = **((_DWORD **)this + 44) & 0xFFFFFEFF | (IsNetworkCosted << 8);
          v3 = (PVOID *)WPP_GLOBAL_Control;
          break;
        case 2:
          if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x10) != 0 )
            WPP_SF_(v3[2], 34, &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids);
          *((_DWORD *)this + 94) = 1;
LABEL_92:
          v3 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_93;
        case 3:
          goto LABEL_54;
        default:
LABEL_93:
          v4 = v27;
          v5 = v11;
          break;
      }
    }
  }
}

```

## disassembly

```asm
0x180008e20  push    rbp
0x180008e22  push    rbx
0x180008e23  push    rsi
0x180008e24  push    rdi
0x180008e25  push    r12
0x180008e27  push    r13
0x180008e29  push    r14
0x180008e2b  push    r15
0x180008e2d  lea     rbp, [rsp-1Fh]
0x180008e32  sub     rsp, 0B8h
0x180008e39  mov     rax, cs:__security_cookie
0x180008e40  xor     rax, rsp
0x180008e43  mov     [rbp+57h+var_48], rax
0x180008e47  mov     rdi, rcx
0x180008e4a  mov     r9d, 1
0x180008e50  lock xadd [rcx+154h], r9d
0x180008e59  inc     r9d
0x180008e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e63  lea     r15, WPP_GLOBAL_Control
0x180008e6a  cmp     rcx, r15
0x180008e6d  jz      short loc_180008E91
0x180008e6f  test    byte ptr [rcx+1Ch], 10h
0x180008e73  jz      short loc_180008E91
0x180008e75  mov     rcx, [rcx+10h]
0x180008e79  lea     r8, WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids
0x180008e80  mov     edx, 1Bh
0x180008e85  call    WPP_SF_d
0x180008e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e91  mov     esi, 1F4h
0x180008e96  xor     r14d, r14d
0x180008e99  mov     [rbp+57h+var_A0], esi
0x180008e9c  nop     dword ptr [rax+00h]
0x180008ea0  cmp     rcx, r15
0x180008ea3  jz      short loc_180008EC0
0x180008ea5  test    byte ptr [rcx+1Ch], 10h
0x180008ea9  jz      short loc_180008EC0
0x180008eab  mov     rcx, [rcx+10h]
0x180008eaf  lea     r8, WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids
0x180008eb6  mov     edx, 1Ch
0x180008ebb  call    WPP_SF_
0x180008ec0  mov     rcx, [rdi+180h]; hHandle
0x180008ec7  mov     edx, esi; dwMilliseconds
0x180008ec9  call    cs:__imp_WaitForSingleObject
0x180008ecf  mov     ebx, eax
0x180008ed1  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ed8  cmp     rcx, r15
0x180008edb  jz      short loc_180008EFB
0x180008edd  test    byte ptr [rcx+1Ch], 10h
0x180008ee1  jz      short loc_180008EFB
0x180008ee3  mov     rcx, [rcx+10h]
0x180008ee7  lea     r8, WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids
0x180008eee  mov     edx, 1Dh
0x180008ef3  mov     r9d, eax
0x180008ef6  call    WPP_SF_d
0x180008efb  lea     rcx, [rdi+168h]; SRWLock
0x180008f02  call    cs:__imp_AcquireSRWLockExclusive
0x180008f08  cmp     ebx, 102h
0x180008f0e  jnz     short loc_180008F53
0x180008f10  cmp     byte ptr [rdi+1ACh], 0
0x180008f17  jz      short loc_180008F53
0x180008f19  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f20  cmp     rcx, r15
0x180008f23  jz      short loc_180008F44
0x180008f25  test    byte ptr [rcx+1Ch], 10h
0x180008f29  jz      short loc_180008F44
0x180008f2b  mov     rcx, [rcx+10h]
0x180008f2f  lea     r9, [rdi+18h]
0x180008f33  mov     edx, 1Eh
0x180008f38  lea     r8, WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids
0x180008f3f  call    WPP_SF_S
0x180008f44  mov     dword ptr [rdi+174h], 3
0x180008f4e  jmp     loc_180008FF5
0x180008f53  mov     r8d, [rdi+174h]
0x180008f5a  mov     edx, [rdi+170h]
0x180008f60  cmp     edx, r8d
0x180008f63  jz      short loc_180008F9E
0x180008f65  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f6c  cmp     rcx, r15
0x180008f6f  jz      short loc_180008F90
0x180008f71  test    byte ptr [rcx+1Ch], 10h
0x180008f75  jz      short loc_180008F90
0x180008f77  mov     rcx, [rcx+10h]
0x180008f7b  lea     rax, [rdi+18h]
0x180008f7f  mov     [rsp+0F0h+var_C8], rax
0x180008f84  mov     r9d, r8d
0x180008f87  mov     dword ptr [rsp+0F0h+var_D0], edx
0x180008f8b  call    WPP_SF_ddS
0x180008f90  mov     eax, [rdi+170h]
0x180008f96  mov     [rdi+174h], eax
0x180008f9c  jmp     short loc_180008FF5
0x180008f9e  cmp     byte ptr [rdi+1ACh], 0
0x180008fa5  jz      short loc_180008FF5
0x180008fa7  sub     r8d, 1
0x180008fab  jz      short loc_180008FBA
0x180008fad  cmp     r8d, 1
0x180008fb1  jnz     short loc_180008FC2
0x180008fb3  mov     esi, 1B58h
0x180008fb8  jmp     short loc_180008FBF
0x180008fba  mov     esi, 7D0h
0x180008fbf  mov     [rbp+57h+var_A0], esi
0x180008fc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fc9  cmp     rcx, r15
0x180008fcc  jz      short loc_180008FF5
0x180008fce  test    byte ptr [rcx+1Ch], 10h
0x180008fd2  jz      short loc_180008FF5
0x180008fd4  mov     rcx, [rcx+10h]
0x180008fd8  lea     rax, [rdi+18h]
0x180008fdc  mov     edx, 20h ; ' '
0x180008fe1  mov     [rsp+0F0h+var_D0], rax
0x180008fe6  mov     r9d, esi
0x180008fe9  lea     r8, WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids
0x180008ff0  call    WPP_SF_dS
0x180008ff5  mov     ebx, [rdi+174h]
0x180008ffb  lea     rcx, [rdi+168h]; SRWLock
0x180009002  mov     esi, [rdi+19Ch]
0x180009008  call    cs:__imp_ReleaseSRWLockExclusive
0x18000900e  cmp     r14d, ebx
0x180009011  jz      loc_180009386
0x180009017  sub     r14d, 1
0x18000901b  jz      short loc_18000909A
0x18000901d  cmp     r14d, 1
0x180009021  jnz     loc_1800091E0
0x180009027  mov     rcx, cs:WPP_GLOBAL_Control
0x18000902e  cmp     rcx, r15
0x180009031  jz      short loc_180009055
0x180009033  test    byte ptr [rcx+1Ch], 10h
0x180009037  jz      short loc_180009055
0x180009039  mov     rcx, [rcx+10h]
0x18000903d  lea     r8, WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids
0x180009044  mov     edx, 21h ; '!'
0x180009049  call    WPP_SF_
0x18000904e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009055  cmp     dword ptr [rdi+178h], 3
0x18000905c  jnz     loc_1800091E7
0x180009062  lea     rax, [rbp+57h+var_A8]
0x180009066  mov     dword ptr [rsp+0F0h+var_C8], 4
0x18000906e  lea     rdx, [rdi+18h]
0x180009072  mov     [rsp+0F0h+var_D0], rax
0x180009077  mov     r9d, 7
0x18000907d  mov     [rbp+57h+var_A8], 7
0x180009084  lea     r8, DEVPKEY_DeviceSetup_DeviceState
0x18000908b  mov     ecx, 2
0x180009090  call    ?SetDeviceObjectProperty@@YAJW4_DEV_OBJECT_TYPE@@PEBGAEBU_DEVPROPKEY@@KPEBXK@Z; SetDeviceObjectProperty(_DEV_OBJECT_TYPE,ushort const *,_DEVPROPKEY const &,ulong,void const *,ulong)
0x180009095  jmp     loc_1800091E0
0x18000909a  mov     rcx, rdi; this
0x18000909d  call    ?_CompleteDevNotifyProgress@CDsmTask@@AEAAXXZ; CDsmTask::_CompleteDevNotifyProgress(void)
0x1800090a2  cmp     cs:Microsoft_Windows_DeviceSetupManagerEnableBits, 0
0x1800090a9  jge     short loc_1800090DD
0x1800090ab  lea     rax, [rdi+8]
0x1800090af  mov     qword ptr [rbp+57h+var_68+8], 10h
0x1800090b7  mov     qword ptr [rbp+57h+var_68], rax
0x1800090bb  lea     rdx, DeviceSetupTaskStop
0x1800090c2  lea     rax, [rbp+57h+var_78]
0x1800090c6  mov     r9d, 2
0x1800090cc  lea     rcx, MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context
0x1800090d3  mov     [rsp+0F0h+var_D0], rax
0x1800090d8  call    McGenEventWrite_EventWriteTransfer
0x1800090dd  mov     rcx, rdi; this
0x1800090e0  call    ?_LogDeviceInformation@CDsmTask@@AEAAXXZ; CDsmTask::_LogDeviceInformation(void)
0x1800090e5  mov     r14, [rdi+160h]
0x1800090ec  mov     r15d, [rdi+148h]
0x1800090f3  lea     rsi, [r14+8]
0x1800090f7  mov     rcx, rsi; SRWLock
0x1800090fa  call    cs:__imp_AcquireSRWLockExclusive
0x180009100  cmp     byte ptr [r14+4], 0
0x180009105  jnz     short loc_18000910E
0x180009107  test    rsi, rsi
0x18000910a  jnz     short loc_180009117
0x18000910c  jmp     short loc_180009120
0x18000910e  mov     [r14+28h], r15d
0x180009112  test    rsi, rsi
0x180009115  jz      short loc_180009120
0x180009117  mov     rcx, rsi; SRWLock
0x18000911a  call    cs:__imp_ReleaseSRWLockExclusive
0x180009120  mov     rcx, [rdi+160h]; this
0x180009127  call    ?RecordInstallResults@DsmSetupRecorder@@QEAAJXZ; DsmSetupRecorder::RecordInstallResults(void)
0x18000912c  xorps   xmm0, xmm0
0x18000912f  mov     [rbp+57h+var_B0], 0
0x180009133  movups  [rbp+57h+var_68+4], xmm0
0x180009137  lea     rax, [rbp+57h+var_B0]
0x18000913b  mov     r8d, 1
0x180009141  movups  [rbp+57h+var_58], xmm0
0x180009145  mov     qword ptr [rbp+57h+var_58+8], rax
0x180009149  lea     rsi, [rdi+18h]
0x18000914d  mov     eax, cs:DEVPKEY_DeviceSetup_InstallInProgress.pid
0x180009153  lea     r9, [rbp+57h+var_78]
0x180009157  movups  xmmword ptr [rbp-1Dh], xmm0
0x18000915b  mov     rdx, rsi
0x18000915e  mov     ecx, 2
0x180009163  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceSetup_InstallInProgress.fmtid.Data1
0x18000916a  mov     dword ptr [rbp+57h+var_58], 11h
0x180009171  mov     dword ptr [rbp+57h+var_58+4], 1
0x180009178  movups  [rbp+57h+var_78], xmm0
0x18000917c  mov     dword ptr [rbp+57h+var_68], eax
0x18000917f  mov     dword ptr [rbp+57h+var_68+4], 0
0x180009186  mov     qword ptr [rbp+57h+var_68+8], 0
0x18000918e  call    cs:__imp_DevSetObjectProperties
0x180009194  test    eax, eax
0x180009196  jns     short loc_1800091D9
0x180009198  mov     rcx, cs:WPP_GLOBAL_Control
0x18000919f  lea     r15, WPP_GLOBAL_Control
0x1800091a6  cmp     rcx, r15
0x1800091a9  jz      short loc_1800091E7
0x1800091ab  test    byte ptr [rcx+1Ch], 1
0x1800091af  jz      short loc_1800091E7
0x1800091b1  mov     rcx, [rcx+10h]
0x1800091b5  lea     r9, DEVPKEY_DeviceSetup_InstallInProgress
0x1800091bc  mov     [rsp+0F0h+var_C0], eax
0x1800091c0  mov     edx, 0Ah
0x1800091c5  mov     [rsp+0F0h+var_C8], rsi
0x1800091ca  mov     dword ptr [rsp+0F0h+var_D0], 2
0x1800091d2  call    WPP_SF__guid_dSd
0x1800091d7  jmp     short loc_1800091E0
0x1800091d9  lea     r15, WPP_GLOBAL_Control
0x1800091e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091e7  mov     edx, ebx
0x1800091e9  sub     edx, 1
0x1800091ec  jz      loc_1800092C6
0x1800091f2  sub     edx, 1
0x1800091f5  jz      loc_180009297
0x1800091fb  cmp     edx, 1
0x1800091fe  jnz     loc_1800094E5
0x180009204  lea     rcx, [rdi+168h]; SRWLock
0x18000920b  call    cs:__imp_AcquireSRWLockExclusive
0x180009211  mov     rbx, [rdi+190h]
0x180009218  mov     rcx, [rdi+188h]; hEvent
0x18000921f  mov     qword ptr [rdi+1A4h], 0
0x18000922a  mov     dword ptr [rdi+174h], 0
0x180009234  mov     qword ptr [rdi+190h], 0
0x18000923f  call    cs:__imp_SetEvent
0x180009245  mov     r9d, 0FFFFFFFFh
0x18000924b  lock xadd [rdi+154h], r9d
0x180009254  dec     r9d
0x180009257  mov     rcx, cs:WPP_GLOBAL_Control
0x18000925e  cmp     rcx, r15
0x180009261  jz      short loc_18000927E
0x180009263  test    byte ptr [rcx+1Ch], 10h
0x180009267  jz      short loc_18000927E
0x180009269  mov     rcx, [rcx+10h]
0x18000926d  lea     r8, WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids
0x180009274  mov     edx, 26h ; '&'
0x180009279  call    WPP_SF_d
0x18000927e  lea     rcx, [rdi+168h]; SRWLock
0x180009285  call    cs:__imp_ReleaseSRWLockExclusive
0x18000928b  xor     edx, edx; dwExitCode
0x18000928d  mov     rcx, rbx; hLibModule
0x180009290  call    cs:__imp_FreeLibraryAndExitThread
0x180009296  int     3; Trap to Debugger
0x180009297  cmp     rcx, r15
0x18000929a  jz      short loc_1800092B7
0x18000929c  test    byte ptr [rcx+1Ch], 10h
0x1800092a0  jz      short loc_1800092B7
0x1800092a2  mov     rcx, [rcx+10h]
0x1800092a6  lea     r8, WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids
0x1800092ad  mov     edx, 22h ; '"'
0x1800092b2  call    WPP_SF_
0x1800092b7  mov     dword ptr [rdi+178h], 1
0x1800092c1  jmp     loc_1800094DE
0x1800092c6  mov     dword ptr [rdi+1A0h], 0FFFFFFFFh
0x1800092d0  mov     [rbp+57h+var_90], 0
0x1800092d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092de  cmp     rcx, r15
0x1800092e1  jz      short loc_1800092FE
0x1800092e3  test    byte ptr [rcx+1Ch], 10h
0x1800092e7  jz      short loc_1800092FE
0x1800092e9  mov     rcx, [rcx+10h]
0x1800092ed  lea     r8, WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids
0x1800092f4  mov     edx, 28h ; '('
0x1800092f9  call    WPP_SF_
0x1800092fe  lea     rdx, [rbp+57h+var_98]; struct DDO_PROGRESS_REPORT *
0x180009302  mov     [rbp+57h+var_98], 1
0x180009309  lea     rcx, [rdi+8]; struct _GUID *
0x18000930d  mov     [rbp+57h+var_94], 2
0x180009314  call    ?s_BroadcastProgress@CDevNotify@@SAXAEBU_GUID@@AEBUDDO_PROGRESS_REPORT@@@Z; CDevNotify::s_BroadcastProgress(_GUID const &,DDO_PROGRESS_REPORT const &)
0x180009319  cmp     cs:Microsoft_Windows_DeviceSetupManagerEnableBits, 0
0x180009320  jge     short loc_180009332
0x180009322  lea     r8, [rdi+8]
0x180009326  lea     rdx, DeviceSetupTaskStart
0x18000932d  call    McTemplateU0j_EventWriteTransfer
0x180009332  lea     rcx, [rdi+18h]; unsigned __int16 *
0x180009336  mov     r8b, 1; bool
0x180009339  lea     rdx, DEVPKEY_DeviceSetup_InstallInProgress; struct _DEVPROPKEY *
0x180009340  call    ?SetContainerBoolean@@YAJPEBGAEBU_DEVPROPKEY@@_N@Z; SetContainerBoolean(ushort const *,_DEVPROPKEY const &,bool)
0x180009345  mov     rcx, [rdi+160h]; this
0x18000934c  call    ?RecorderReset@DsmSetupRecorder@@QEAAXXZ; DsmSetupRecorder::RecorderReset(void)
0x180009351  lea     rcx, ?g_DsmCore@@3VCDsmCore@@A; this
0x180009358  call    ?IsNetworkCosted@CNetworkEvents@@QEAA_NXZ; CNetworkEvents::IsNetworkCosted(void)
0x18000935d  mov     rcx, [rdi+160h]
0x180009364  mov     r14d, ebx
0x180009367  mov     esi, [rbp+57h+var_A0]
0x18000936a  movzx   edx, al
0x18000936d  shl     edx, 8
0x180009370  mov     eax, [rcx]
0x180009372  btr     eax, 8
0x180009376  or      edx, eax
0x180009378  mov     [rcx], edx
0x18000937a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009381  jmp     loc_180008EA0
0x180009386  mov     eax, ebx
0x180009388  sub     eax, 1
  ... truncated ...
```
