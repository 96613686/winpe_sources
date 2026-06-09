# CDsmCore::ServiceStart(void)

- ea: `0x1800238e8`
- end: `0x180023b93`
- name: `?ServiceStart@CDsmCore@@QEAAXXZ`
- size: `683`
- prototype: `void __fastcall(CDsmCore *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180021db0`

## callees

- `0x180009fb0`
- `0x18000e518`
- `0x18001777c`
- `0x180018368`
- `0x18001870c`
- `0x180019970`
- `0x18001a774`
- `0x18001af70`
- `0x180021790`
- `0x18002384c`
- `0x1800238e8`
- `0x180023e70`
- `0x1800240dc`
- `0x180024374`
- `0x180024814`
- `0x180024f4c`
- `0x180024fa8`
- `0x18003ea48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002396f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002396f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180023956`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180023956`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800239ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023a75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023abe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800239ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023a75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023abe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023996`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023a61`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023aaa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023996`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023a61`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023aaa`

## pseudocode

```c
void __fastcall CDsmCore::ServiceStart(CDsmCore *this)
{
  CDsmCore *v1; // rcx
  HANDLE EventW; // rax
  unsigned int v3; // edx
  unsigned int v4; // edx
  CDsmCore *v5; // rcx
  CDsmCore *v6; // rcx
  int v7; // eax
  unsigned int v8; // edx
  __int64 v9; // rcx
  CDsmCore *v10; // rcx
  CDsmCore *v11; // rcx
  bool v12; // bl
  __int64 v13; // r8
  int updated; // ebx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  bool v18; // bl
  CDsmCore *v19; // rcx
  bool v20; // [rsp+30h] [rbp-28h] BYREF
  bool v21; // [rsp+31h] [rbp-27h] BYREF
  _BYTE v22[16]; // [rsp+38h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids);
  if ( (unsigned int)DsmDebugBreakEnabled() )
    __debugbreak();
  CDsmCore::_GetRegistryParameters(v1);
  EventW = hHandle;
  if ( hHandle || (EventW = CreateEventW(0, 1, 0, 0), (hHandle = EventW) != 0) )
  {
    ResetEvent(EventW);
    if ( (unsigned int)CDsmCore::get_CoreServiceMode() == 2 )
    {
      ReportSvcStatus(4u, v4, 0);
      CDsmCore::_WaitForShutdownEvent(v5);
      AcquireSRWLockExclusive(&stru_180059EA8);
      LODWORD(qword_180059EB0) = 128;
      ReleaseSRWLockExclusive(&stru_180059EA8);
    }
    else
    {
      ReportSvcStatus(2u, v4, 0xBB8u);
      v7 = CDsmCore::_Startup(v6);
      if ( v7 < 0 )
      {
        if ( (Microsoft_Windows_DeviceSetupManagerEnableBits & 2) != 0 )
          McTemplateU0q_EventWriteTransfer(v9, &DsmServiceStartupFailed, (unsigned int)v7);
      }
      else
      {
        ReportSvcStatus(4u, v8, 0);
        if ( (unsigned int)CDsmCore::get_CoreServiceMode() == 3 && (int)CDsmCore::_WaitForOobeExit(v10) >= 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids);
          v12 = IsCtaPolicyActive();
          if ( v12 )
          {
            if ( (Microsoft_Windows_DeviceSetupManagerEnableBits & 1) != 0 )
              McGenEventWrite_EventWriteTransfer(
                &MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context,
                &DsmInCtaOobe,
                v13,
                1,
                v22);
            AcquireSRWLockExclusive(&stru_180059EA8);
            byte_180059E48 = 1;
            ReleaseSRWLockExclusive(&stru_180059EA8);
          }
          CDsmCore::ServiceReset(v11);
          if ( v12 )
          {
            v21 = 0;
            v20 = 0;
            updated = CDsmCore::_WaitForCtaUpdateSettings(v10, &v21, &v20);
            AcquireSRWLockExclusive(&stru_180059EA8);
            byte_180059E48 = 0;
            ReleaseSRWLockExclusive(&stru_180059EA8);
            if ( updated >= 0 )
            {
              v18 = v21;
              if ( (Microsoft_Windows_DeviceSetupManagerEnableBits & 1) != 0 )
              {
                LOBYTE(v17) = v20;
                LOBYTE(v16) = v21;
                McTemplateU0uu_EventWriteTransfer(v10, v15, v16, v17);
              }
              if ( v18 )
                ContainerManager::RefreshContainers((RTL_SRWLOCK *)xmmword_180059F10, 7u, 0);
              if ( v20 )
                ContainerManager::RefreshContainers((RTL_SRWLOCK *)xmmword_180059F10, 8u, 0);
            }
          }
        }
        CDsmCore::_WaitForShutdownEvent(v10);
      }
      ReportSvcStatus(3u, v8, 0x2710u);
      CDsmCore::_Shutdown(v19);
    }
  }
  ReportSvcStatus(1u, v3, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids);
}

```

## disassembly

```asm
0x1800238e8  mov     [rsp+arg_0], rbx
0x1800238ed  push    r14
0x1800238ef  sub     rsp, 50h
0x1800238f3  mov     rax, cs:__security_cookie
0x1800238fa  xor     rax, rsp
0x1800238fd  mov     [rsp+58h+var_10], rax
0x180023902  mov     rcx, cs:WPP_GLOBAL_Control
0x180023909  lea     r14, WPP_GLOBAL_Control
0x180023910  cmp     rcx, r14
0x180023913  jz      short loc_180023930
0x180023915  test    byte ptr [rcx+1Ch], 1
0x180023919  jz      short loc_180023930
0x18002391b  mov     rcx, [rcx+10h]
0x18002391f  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x180023926  mov     edx, 0Ah
0x18002392b  call    WPP_SF_
0x180023930  call    ?DsmDebugBreakEnabled@@YAHW4_DSM_DEBUG_TYPE@@_N@Z; DsmDebugBreakEnabled(_DSM_DEBUG_TYPE,bool)
0x180023935  test    eax, eax
0x180023937  jz      short loc_18002393A
0x180023939  int     3; Trap to Debugger
0x18002393a  call    ?_GetRegistryParameters@CDsmCore@@AEAAXXZ; CDsmCore::_GetRegistryParameters(void)
0x18002393f  mov     rax, cs:hHandle
0x180023946  test    rax, rax
0x180023949  jnz     short loc_18002396C
0x18002394b  xor     r9d, r9d; lpName
0x18002394e  lea     edx, [rax+1]; bManualReset
0x180023951  xor     r8d, r8d; bInitialState
0x180023954  xor     ecx, ecx; lpEventAttributes
0x180023956  call    cs:__imp_CreateEventW
0x18002395c  mov     cs:hHandle, rax
0x180023963  test    rax, rax
0x180023966  jz      loc_180023B47
0x18002396c  mov     rcx, rax; hEvent
0x18002396f  call    cs:__imp_ResetEvent
0x180023975  call    ?get_CoreServiceMode@CDsmCore@@QEAA?AW4DSM_SERVICE_MODE@@XZ; CDsmCore::get_CoreServiceMode(void)
0x18002397a  cmp     eax, 2
0x18002397d  jnz     short loc_1800239B8
0x18002397f  xor     r8d, r8d; unsigned int
0x180023982  lea     ecx, [rax+2]; unsigned int
0x180023985  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x18002398a  call    ?_WaitForShutdownEvent@CDsmCore@@AEAAXXZ; CDsmCore::_WaitForShutdownEvent(void)
0x18002398f  lea     rcx, stru_180059EA8; SRWLock
0x180023996  call    cs:__imp_AcquireSRWLockExclusive
0x18002399c  lea     rcx, stru_180059EA8; SRWLock
0x1800239a3  mov     dword ptr cs:qword_180059EB0, 80h
0x1800239ad  call    cs:__imp_ReleaseSRWLockExclusive
0x1800239b3  jmp     loc_180023B47
0x1800239b8  mov     ecx, 2; unsigned int
0x1800239bd  mov     r8d, 0BB8h; unsigned int
0x1800239c3  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x1800239c8  call    ?_Startup@CDsmCore@@AEAAJXZ; CDsmCore::_Startup(void)
0x1800239cd  test    eax, eax
0x1800239cf  js      loc_180023B1A
0x1800239d5  xor     r8d, r8d; unsigned int
0x1800239d8  lea     ecx, [r8+4]; unsigned int
0x1800239dc  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x1800239e1  call    ?get_CoreServiceMode@CDsmCore@@QEAA?AW4DSM_SERVICE_MODE@@XZ; CDsmCore::get_CoreServiceMode(void)
0x1800239e6  cmp     eax, 3
0x1800239e9  jnz     loc_180023B13
0x1800239ef  call    ?_WaitForOobeExit@CDsmCore@@AEAAJXZ; CDsmCore::_WaitForOobeExit(void)
0x1800239f4  test    eax, eax
0x1800239f6  js      loc_180023B13
0x1800239fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a03  cmp     rcx, r14
0x180023a06  jz      short loc_180023A23
0x180023a08  test    byte ptr [rcx+1Ch], 1
0x180023a0c  jz      short loc_180023A23
0x180023a0e  mov     rcx, [rcx+10h]
0x180023a12  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x180023a19  mov     edx, 0Bh
0x180023a1e  call    WPP_SF_
0x180023a23  call    ?IsCtaPolicyActive@@YA_NXZ; IsCtaPolicyActive(void)
0x180023a28  mov     bl, al
0x180023a2a  test    al, al
0x180023a2c  jz      short loc_180023A7B
0x180023a2e  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, 1
0x180023a35  jz      short loc_180023A5A
0x180023a37  lea     rax, [rsp+58h+var_20]
0x180023a3c  mov     r9d, 1
0x180023a42  lea     rdx, DsmInCtaOobe
0x180023a49  mov     [rsp+58h+var_38], rax
0x180023a4e  lea     rcx, MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context
0x180023a55  call    McGenEventWrite_EventWriteTransfer
0x180023a5a  lea     rcx, stru_180059EA8; SRWLock
0x180023a61  call    cs:__imp_AcquireSRWLockExclusive
0x180023a67  lea     rcx, stru_180059EA8; SRWLock
0x180023a6e  mov     cs:byte_180059E48, 1
0x180023a75  call    cs:__imp_ReleaseSRWLockExclusive
0x180023a7b  call    ?ServiceReset@CDsmCore@@QEAAJXZ; CDsmCore::ServiceReset(void)
0x180023a80  test    bl, bl
0x180023a82  jz      loc_180023B13
0x180023a88  lea     r8, [rsp+58h+var_28]; bool *
0x180023a8d  mov     [rsp+58h+var_27], 0
0x180023a92  lea     rdx, [rsp+58h+var_27]; bool *
0x180023a97  mov     [rsp+58h+var_28], 0
0x180023a9c  call    ?_WaitForCtaUpdateSettings@CDsmCore@@AEAAJPEA_N0@Z; CDsmCore::_WaitForCtaUpdateSettings(bool *,bool *)
0x180023aa1  lea     rcx, stru_180059EA8; SRWLock
0x180023aa8  mov     ebx, eax
0x180023aaa  call    cs:__imp_AcquireSRWLockExclusive
0x180023ab0  lea     rcx, stru_180059EA8; SRWLock
0x180023ab7  mov     cs:byte_180059E48, 0
0x180023abe  call    cs:__imp_ReleaseSRWLockExclusive
0x180023ac4  test    ebx, ebx
0x180023ac6  js      short loc_180023B13
0x180023ac8  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, 1
0x180023acf  mov     bl, [rsp+58h+var_27]
0x180023ad3  jz      short loc_180023AE2
0x180023ad5  mov     r9b, [rsp+58h+var_28]
0x180023ada  mov     r8b, bl
0x180023add  call    McTemplateU0uu_EventWriteTransfer
0x180023ae2  test    bl, bl
0x180023ae4  jz      short loc_180023AF9
0x180023ae6  mov     rcx, qword ptr cs:xmmword_180059F10
0x180023aed  xor     r8d, r8d
0x180023af0  lea     edx, [r8+7]
0x180023af4  call    ?RefreshContainers@ContainerManager@@QEAAJW4DSM_REFRESH_TYPE@@PEBG@Z; ContainerManager::RefreshContainers(DSM_REFRESH_TYPE,ushort const *)
0x180023af9  cmp     [rsp+58h+var_28], 0
0x180023afe  jz      short loc_180023B13
0x180023b00  mov     rcx, qword ptr cs:xmmword_180059F10
0x180023b07  xor     r8d, r8d
0x180023b0a  lea     edx, [r8+8]
0x180023b0e  call    ?RefreshContainers@ContainerManager@@QEAAJW4DSM_REFRESH_TYPE@@PEBG@Z; ContainerManager::RefreshContainers(DSM_REFRESH_TYPE,ushort const *)
0x180023b13  call    ?_WaitForShutdownEvent@CDsmCore@@AEAAXXZ; CDsmCore::_WaitForShutdownEvent(void)
0x180023b18  jmp     short loc_180023B32
0x180023b1a  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, 2
0x180023b21  jz      short loc_180023B32
0x180023b23  mov     r8d, eax
0x180023b26  lea     rdx, DsmServiceStartupFailed
0x180023b2d  call    McTemplateU0q_EventWriteTransfer
0x180023b32  mov     ecx, 3; unsigned int
0x180023b37  mov     r8d, 2710h; unsigned int
0x180023b3d  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x180023b42  call    ?_Shutdown@CDsmCore@@AEAAXXZ; CDsmCore::_Shutdown(void)
0x180023b47  xor     r8d, r8d; unsigned int
0x180023b4a  lea     ecx, [r8+1]; unsigned int
0x180023b4e  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x180023b53  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b5a  cmp     rcx, r14
0x180023b5d  jz      short loc_180023B7A
0x180023b5f  test    byte ptr [rcx+1Ch], 1
0x180023b63  jz      short loc_180023B7A
0x180023b65  mov     rcx, [rcx+10h]
0x180023b69  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x180023b70  mov     edx, 0Ch
0x180023b75  call    WPP_SF_
0x180023b7a  mov     rcx, [rsp+58h+var_10]
0x180023b7f  xor     rcx, rsp; StackCookie
0x180023b82  call    __security_check_cookie
0x180023b87  mov     rbx, [rsp+58h+arg_0]
0x180023b8c  add     rsp, 50h
0x180023b90  pop     r14
0x180023b92  retn
```
