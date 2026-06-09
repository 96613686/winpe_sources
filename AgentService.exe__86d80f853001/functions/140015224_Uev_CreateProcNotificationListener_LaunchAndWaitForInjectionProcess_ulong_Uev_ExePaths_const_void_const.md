# Uev::CreateProcNotificationListener::LaunchAndWaitForInjectionProcess(ulong,Uev::ExePaths const &,void * const)

- ea: `0x140015224`
- end: `0x14001561c`
- name: `?LaunchAndWaitForInjectionProcess@CreateProcNotificationListener@Uev@@AEAAXKAEBVExePaths@2@QEAX@Z`
- size: `1016`
- prototype: `void __fastcall(Uev::CreateProcNotificationListener *this, unsigned int, const struct Uev::ExePaths *, void *const)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140014b0c`

## callees

- `0x140003e50`
- `0x140003f88`
- `0x140004a78`
- `0x140004b14`
- `0x14000ac28`
- `0x14000ac88`
- `0x14000acc4`
- `0x14000ba60`
- `0x14000bc7c`
- `0x14000c2b8`
- `0x14000ef6c`
- `0x140012a14`
- `0x140013bb0`
- `0x140015224`
- `0x140015874`
- `0x140015d58`
- `0x140015f38`

## import_xrefs

- `ADVAPI32!CreateProcessAsUserW` at `0x14001531f`
- `ADVAPI32!CreateProcessAsUserW` at `0x14001531f`
- `KERNEL32!CloseHandle` at `0x140015361`
- `KERNEL32!CloseHandle` at `0x140015370`
- `KERNEL32!CloseHandle` at `0x140015361`
- `KERNEL32!CloseHandle` at `0x140015370`
- `KERNEL32!GetLastError` at `0x140015378`
- `KERNEL32!GetLastError` at `0x140015378`
- `KERNEL32!WaitForSingleObject` at `0x140015339`
- `KERNEL32!WaitForSingleObject` at `0x140015339`

## string_xrefs

- `0x140015276`: `AgentService.CreateProcNotificationListener::LaunchAndWaitForInjectionProcess: Entry`
- `0x1400152cb`: `AgentService.CreateProcNotificationListener::LaunchAndWaitForInjectionProcess: Injecting the AppAgent into process %lu`
- `0x140015349`: `AgentService.CreateProcNotificationListener::LaunchAndWaitForInjectionProcess: Error waiting for MavInject to exit, 0x%X`
- `0x140015380`: `AgentService.CreateProcNotificationListener::LaunchAndWaitForInjectionProcess: CreateProcess failed, error = 0x%X`
- `0x14001538f`: `AgentService.CreateProcNotificationListener::LaunchAndWaitForInjectionProcess: CreateProcess command line = %s`
- `0x1400153b0`: `AgentService.CreateProcNotificationListener::LaunchAndWaitForInjectionProcess: Failed to allocate buffer`
- `0x1400153da`: `AgentService.CreateProcNotificationListener::LaunchAndWaitForInjectionProcess: AppAgent succeessfully injected into process %lu`
- `0x1400155ef`: `AgentService.CreateProcNotificationListener::LaunchAndWaitForInjectionProcess: Exit`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Uev::CreateProcNotificationListener::LaunchAndWaitForInjectionProcess(
        Uev::CreateProcNotificationListener *this,
        unsigned int a2,
        const struct Uev::ExePaths *a3,
        void *const a4)
{
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  int v12; // edi
  WCHAR *v13; // rbx
  wchar_t *v14; // rcx
  __int64 *v15; // rdx
  __int128 v16; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v17; // [rsp+70h] [rbp-90h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR lpCommandLine; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v20[7]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v21[32]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v22[40]; // [rsp+F8h] [rbp-8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+120h] [rbp+20h] BYREF
  __int128 v24; // [rsp+190h] [rbp+90h] BYREF
  __int128 v25; // [rsp+1A0h] [rbp+A0h]
  wchar_t Buffer[256]; // [rsp+1B0h] [rbp+B0h] BYREF

  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  DbgTrace<5>(L"AgentService.CreateProcNotificationListener::LaunchAndWaitForInjectionProcess: Entry");
  if ( !(unsigned __int8)Uev::CreateProcNotificationListener::ValidateDigitalSignature(v8, a3)
    || !(unsigned __int8)Uev::CreateProcNotificationListener::ValidateDigitalSignature(v9, (char *)a3 + 32) )
  {
    v12 = 1;
    goto LABEL_19;
  }
  v12 = 3;
  Uev::CreateProcNotificationListener::SetupLaunchCmdLine(v11, &lpCommandLine, a2, a3);
  v13 = lpCommandLine;
  if ( lpCommandLine )
  {
    DbgTraceFrmt<4,unsigned long>((wchar_t *)L"AgentService.CreateProcNotificationListener::LaunchAndWaitForInjectionProce"
                                              "ss: Injecting the AppAgent into process %lu");
    if ( CreateProcessAsUserW(a4, 0, v13, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation)
      && ProcessInformation.hProcess )
    {
      if ( WaitForSingleObject(ProcessInformation.hProcess, *((_DWORD *)this + 72)) )
      {
        DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.CreateProcNotificationListener::LaunchAndWaitForInjectionProcess: "
                                          "Error waiting for MavInject to exit, 0x%X");
        v12 = 2;
      }
      else
      {
        v12 = 0;
      }
      if ( ProcessInformation.hProcess )
        CloseHandle(ProcessInformation.hProcess);
      if ( ProcessInformation.hThread )
        CloseHandle(ProcessInformation.hThread);
      goto LABEL_16;
    }
    GetLastError();
    DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.CreateProcNotificationListener::LaunchAndWaitForInjectionProcess: Crea"
                                      "teProcess failed, error = 0x%X");
    swprintf_s(
      Buffer,
      0x100u,
      L"AgentService.CreateProcNotificationListener::LaunchAndWaitForInjectionProcess: CreateProcess command line = %s",
      v13);
    v14 = Buffer;
  }
  else
  {
    v14 = L"AgentService.CreateProcNotificationListener::LaunchAndWaitForInjectionProcess: Failed to allocate buffer";
  }
  DbgTrace<2>(v14);
LABEL_16:
  if ( v13 )
    operator delete(v13);
LABEL_19:
  if ( !v12 )
  {
    DbgTraceFrmt<4,unsigned long>((wchar_t *)L"AgentService.CreateProcNotificationListener::LaunchAndWaitForInjectionProce"
                                              "ss: AppAgent succeessfully injected into process %lu");
    v24 = 0;
    v25 = 0;
    std::wstring::_Construct<1,wchar_t *>(&v24, L"Injected successfully", 21);
    v16 = 0;
    v17 = 0;
    std::wstring::_Construct<1,wchar_t *>(&v16, &Data, 0);
    Uev::UevHealthEvent::UevHealthEvent((unsigned int)v20, (unsigned int)&v16, (unsigned int)&v24, 53, 4);
    std::wstring::_Tidy_deallocate(&v16);
    std::wstring::_Tidy_deallocate(&v24);
    Uev::UevIPC::Send((Uev::UevIPC *)v20);
LABEL_28:
    v20[0] = &Uev::UevHealthEvent::`vftable';
    std::wstring::_Tidy_deallocate(v22);
    std::wstring::_Tidy_deallocate(v21);
    Uev::UevIPC::~UevIPC((Uev::UevIPC *)v20);
    goto LABEL_32;
  }
  if ( v12 != 2 )
  {
    if ( v12 == 1 )
    {
      if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 0x10) != 0 )
      {
        LODWORD(lpCommandLine) = a2;
        *(_QWORD *)&v25 = &lpCommandLine;
        *((_QWORD *)&v25 + 1) = 4;
        McGenEventWrite_EventWriteTransfer(
          UevAppAgentProvider_Context,
          AgentServiceLog_InvalidMavinjectOrAppAgentCertificate,
          v10,
          2,
          &v24);
      }
      v16 = 0;
      v17 = 0;
      std::wstring::_Construct<1,wchar_t *>(&v16, L"Invalid mavinject", 17);
      v24 = 0;
      v25 = 0;
      std::wstring::_Construct<1,wchar_t *>(&v24, &Data, 0);
      Uev::UevHealthEvent::UevHealthEvent((unsigned int)v20, (unsigned int)&v24, (unsigned int)&v16, 750, 2);
      std::wstring::_Tidy_deallocate(&v24);
      std::wstring::_Tidy_deallocate(&v16);
      Uev::UevIPC::Send((Uev::UevIPC *)v20);
      goto LABEL_28;
    }
    if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 4) == 0 )
      goto LABEL_32;
    v15 = AgentServiceLog_AppAgentInjectionFailed;
LABEL_31:
    *(_QWORD *)&v25 = &lpCommandLine;
    LODWORD(lpCommandLine) = a2;
    *((_QWORD *)&v25 + 1) = 4;
    McGenEventWrite_EventWriteTransfer(UevAppAgentProvider_Context, v15, v10, 2, &v24);
    goto LABEL_32;
  }
  if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 4) != 0 )
  {
    v15 = AgentServiceLog_AppAgentInjectionTimedOut;
    goto LABEL_31;
  }
LABEL_32:
  DbgTrace<5>(L"AgentService.CreateProcNotificationListener::LaunchAndWaitForInjectionProcess: Exit");
}

```

## disassembly

```asm
0x140015224  push    rbp
0x140015226  push    rbx
0x140015227  push    rsi
0x140015228  push    rdi
0x140015229  push    r13
0x14001522b  push    r14
0x14001522d  push    r15
0x14001522f  lea     rbp, [rsp-2C0h]
0x140015237  sub     rsp, 3C0h
0x14001523e  mov     rax, cs:__security_cookie
0x140015245  xor     rax, rsp
0x140015248  mov     [rbp+2F0h+var_40], rax
0x14001524f  mov     r15, r9
0x140015252  mov     rbx, r8
0x140015255  mov     esi, edx
0x140015257  mov     r14, rcx
0x14001525a  xorps   xmm0, xmm0
0x14001525d  xor     eax, eax
0x14001525f  movups  xmmword ptr [rbp+2F0h+ProcessInformation.hProcess], xmm0
0x140015263  mov     qword ptr [rbp+2F0h+ProcessInformation.dwProcessId], rax
0x140015267  xor     edx, edx; Val
0x140015269  lea     r8d, [rax+68h]; Size
0x14001526d  lea     rcx, [rbp+2F0h+StartupInfo]; void *
0x140015271  call    memset_0
0x140015276  lea     rcx, aAgentserviceCr_12; "AgentService.CreateProcNotificationList"...
0x14001527d  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x140015282  mov     rdx, rbx
0x140015285  call    ?ValidateDigitalSignature@CreateProcNotificationListener@Uev@@AEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::CreateProcNotificationListener::ValidateDigitalSignature(std::wstring const &)
0x14001528a  mov     r13d, 2
0x140015290  test    al, al
0x140015292  jz      loc_1400153CB
0x140015298  lea     rdx, [rbx+20h]
0x14001529c  call    ?ValidateDigitalSignature@CreateProcNotificationListener@Uev@@AEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::CreateProcNotificationListener::ValidateDigitalSignature(std::wstring const &)
0x1400152a1  test    al, al
0x1400152a3  jz      loc_1400153CB
0x1400152a9  lea     edi, [r13+1]
0x1400152ad  mov     r9, rbx
0x1400152b0  mov     r8d, esi
0x1400152b3  lea     rdx, [rbp+2F0h+lpCommandLine]
0x1400152b7  call    ?SetupLaunchCmdLine@CreateProcNotificationListener@Uev@@AEAA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@std@@@std@@KAEBVExePaths@2@@Z; Uev::CreateProcNotificationListener::SetupLaunchCmdLine(ulong,Uev::ExePaths const &)
0x1400152bc  mov     rbx, [rbp+2F0h+lpCommandLine]
0x1400152c0  test    rbx, rbx
0x1400152c3  jz      loc_1400153B0
0x1400152c9  mov     edx, esi
0x1400152cb  lea     rcx, aAgentserviceCr_31; "AgentService.CreateProcNotificationList"...
0x1400152d2  call    ??$DbgTraceFrmt@$03K@@YAXPEB_WK@Z; DbgTraceFrmt<4,ulong>(wchar_t const *,ulong)
0x1400152d7  lea     rax, [rbp+2F0h+ProcessInformation]
0x1400152db  mov     [rsp+3F0h+lpProcessInformation], rax; lpProcessInformation
0x1400152e0  lea     rax, [rbp+2F0h+StartupInfo]
0x1400152e4  mov     [rsp+3F0h+lpStartupInfo], rax; lpStartupInfo
0x1400152e9  mov     [rsp+3F0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1400152f2  mov     [rsp+3F0h+lpEnvironment], 0; lpEnvironment
0x1400152fb  mov     [rsp+3F0h+dwCreationFlags], 0; dwCreationFlags
0x140015303  mov     [rsp+3F0h+bInheritHandles], 0; bInheritHandles
0x14001530b  mov     [rsp+3F0h+lpThreadAttributes], 0; lpThreadAttributes
0x140015314  xor     r9d, r9d; lpProcessAttributes
0x140015317  mov     r8, rbx; lpCommandLine
0x14001531a  xor     edx, edx; lpApplicationName
0x14001531c  mov     rcx, r15; hToken
0x14001531f  call    cs:__imp_CreateProcessAsUserW
0x140015325  test    eax, eax
0x140015327  jz      short loc_140015378
0x140015329  mov     rcx, [rbp+2F0h+ProcessInformation.hProcess]; hHandle
0x14001532d  test    rcx, rcx
0x140015330  jz      short loc_140015378
0x140015332  mov     edx, [r14+120h]; dwMilliseconds
0x140015339  call    cs:__imp_WaitForSingleObject
0x14001533f  test    eax, eax
0x140015341  jnz     short loc_140015347
0x140015343  xor     edi, edi
0x140015345  jmp     short loc_140015358
0x140015347  mov     edx, eax
0x140015349  lea     rcx, aAgentserviceCr_42; "AgentService.CreateProcNotificationList"...
0x140015350  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x140015355  mov     edi, r13d
0x140015358  mov     rcx, [rbp+2F0h+ProcessInformation.hProcess]; hObject
0x14001535c  test    rcx, rcx
0x14001535f  jz      short loc_140015367
0x140015361  call    cs:__imp_CloseHandle
0x140015367  mov     rcx, [rbp+2F0h+ProcessInformation.hThread]; hObject
0x14001536b  test    rcx, rcx
0x14001536e  jz      short loc_1400153BC
0x140015370  call    cs:__imp_CloseHandle
0x140015376  jmp     short loc_1400153BC
0x140015378  call    cs:__imp_GetLastError
0x14001537e  mov     edx, eax
0x140015380  lea     rcx, aAgentserviceCr_46; "AgentService.CreateProcNotificationList"...
0x140015387  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x14001538c  mov     r9, rbx
0x14001538f  lea     r8, aAgentserviceCr_40; "AgentService.CreateProcNotificationList"...
0x140015396  mov     edx, 100h; BufferCount
0x14001539b  lea     rcx, [rbp+2F0h+Buffer]; Buffer
0x1400153a2  call    swprintf_s
0x1400153a7  lea     rcx, [rbp+2F0h+Buffer]
0x1400153ae  jmp     short loc_1400153B7
0x1400153b0  lea     rcx, aAgentserviceCr_20; "AgentService.CreateProcNotificationList"...
0x1400153b7  call    ??$DbgTrace@$01@@YAXPEB_W@Z; DbgTrace<2>(wchar_t const *)
0x1400153bc  test    rbx, rbx
0x1400153bf  jz      short loc_1400153D0
0x1400153c1  mov     rcx, rbx; Block
0x1400153c4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400153c9  jmp     short loc_1400153D0
0x1400153cb  mov     edi, 1
0x1400153d0  test    edi, edi
0x1400153d2  jnz     loc_140015481
0x1400153d8  mov     edx, esi
0x1400153da  lea     rcx, aAgentserviceCr_2; "AgentService.CreateProcNotificationList"...
0x1400153e1  call    ??$DbgTraceFrmt@$03K@@YAXPEB_WK@Z; DbgTraceFrmt<4,ulong>(wchar_t const *,ulong)
0x1400153e6  xorps   xmm0, xmm0
0x1400153e9  movups  [rbp+2F0h+var_260], xmm0
0x1400153f0  xorps   xmm1, xmm1
0x1400153f3  movdqu  [rbp+2F0h+var_250], xmm1
0x1400153fb  lea     r8d, [rdi+15h]
0x1400153ff  lea     rdx, aInjectedSucces; "Injected successfully"
0x140015406  lea     rcx, [rbp+2F0h+var_260]
0x14001540d  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140015412  nop
0x140015413  xorps   xmm0, xmm0
0x140015416  movups  [rsp+3F0h+var_390], xmm0
0x14001541b  xorps   xmm1, xmm1
0x14001541e  movdqu  [rsp+3F0h+var_380], xmm1
0x140015424  xor     r8d, r8d
0x140015427  lea     rdx, Data
0x14001542e  lea     rcx, [rsp+3F0h+var_390]
0x140015433  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140015438  nop
0x140015439  mov     dword ptr [rsp+3F0h+lpThreadAttributes], 4
0x140015441  lea     r9d, [rdi+35h]
0x140015445  lea     r8, [rbp+2F0h+var_260]
0x14001544c  lea     rdx, [rsp+3F0h+var_390]
0x140015451  lea     rcx, [rbp+2F0h+var_350]
0x140015455  call    ??0UevHealthEvent@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4HealthEventOpcode@1@W4HealthEventLevel@1@@Z; Uev::UevHealthEvent::UevHealthEvent(std::wstring const &,std::wstring const &,Uev::HealthEventOpcode,Uev::HealthEventLevel)
0x14001545a  nop
0x14001545b  lea     rcx, [rsp+3F0h+var_390]
0x140015460  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140015465  nop
0x140015466  lea     rcx, [rbp+2F0h+var_260]
0x14001546d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140015472  lea     rcx, [rbp+2F0h+var_350]; this
0x140015476  call    ?Send@UevIPC@Uev@@QEAAXXZ; Uev::UevIPC::Send(void)
0x14001547b  nop
0x14001547c  jmp     loc_140015583
0x140015481  cmp     edi, r13d
0x140015484  jnz     short loc_14001549F
0x140015486  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 4
0x14001548d  jz      loc_1400155EF
0x140015493  lea     rdx, AgentServiceLog_AppAgentInjectionTimedOut
0x14001549a  jmp     loc_1400155BB
0x14001549f  cmp     edi, 1
0x1400154a2  jnz     loc_1400155AB
0x1400154a8  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 10h
0x1400154af  jz      short loc_1400154EC
0x1400154b1  mov     dword ptr [rbp+2F0h+lpCommandLine], esi
0x1400154b4  lea     rax, [rbp+2F0h+lpCommandLine]
0x1400154b8  mov     qword ptr [rbp+2F0h+var_250], rax
0x1400154bf  mov     qword ptr [rbp+2F0h+var_250+8], 4
0x1400154ca  lea     rax, [rbp+2F0h+var_260]
0x1400154d1  mov     [rsp+3F0h+lpThreadAttributes], rax
0x1400154d6  mov     r9d, r13d
0x1400154d9  lea     rdx, AgentServiceLog_InvalidMavinjectOrAppAgentCertificate
0x1400154e0  lea     rcx, UevAppAgentProvider_Context
0x1400154e7  call    McGenEventWrite_EventWriteTransfer
0x1400154ec  xorps   xmm0, xmm0
0x1400154ef  movups  [rsp+3F0h+var_390], xmm0
0x1400154f4  xorps   xmm1, xmm1
0x1400154f7  movdqu  [rsp+3F0h+var_380], xmm1
0x1400154fd  mov     r8d, 11h
0x140015503  lea     rdx, aInvalidMavinje; "Invalid mavinject"
0x14001550a  lea     rcx, [rsp+3F0h+var_390]
0x14001550f  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140015514  nop
0x140015515  xorps   xmm0, xmm0
0x140015518  movups  [rbp+2F0h+var_260], xmm0
0x14001551f  xorps   xmm1, xmm1
0x140015522  movdqu  [rbp+2F0h+var_250], xmm1
0x14001552a  xor     r8d, r8d
0x14001552d  lea     rdx, Data
0x140015534  lea     rcx, [rbp+2F0h+var_260]
0x14001553b  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140015540  nop
0x140015541  mov     dword ptr [rsp+3F0h+lpThreadAttributes], r13d
0x140015546  mov     r9d, 2EEh
0x14001554c  lea     r8, [rsp+3F0h+var_390]
0x140015551  lea     rdx, [rbp+2F0h+var_260]
0x140015558  lea     rcx, [rbp+2F0h+var_350]
0x14001555c  call    ??0UevHealthEvent@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4HealthEventOpcode@1@W4HealthEventLevel@1@@Z; Uev::UevHealthEvent::UevHealthEvent(std::wstring const &,std::wstring const &,Uev::HealthEventOpcode,Uev::HealthEventLevel)
0x140015561  nop
0x140015562  lea     rcx, [rbp+2F0h+var_260]
0x140015569  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001556e  nop
0x14001556f  lea     rcx, [rsp+3F0h+var_390]
0x140015574  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140015579  lea     rcx, [rbp+2F0h+var_350]; this
0x14001557d  call    ?Send@UevIPC@Uev@@QEAAXXZ; Uev::UevIPC::Send(void)
0x140015582  nop
0x140015583  lea     rax, ??_7UevHealthEvent@Uev@@6B@; const Uev::UevHealthEvent::`vftable'
0x14001558a  mov     [rbp+2F0h+var_350], rax
0x14001558e  lea     rcx, [rbp+2F0h+var_2F8]
0x140015592  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140015597  lea     rcx, [rbp+2F0h+var_318]
0x14001559b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400155a0  lea     rcx, [rbp+2F0h+var_350]; this
0x1400155a4  call    ??1UevIPC@Uev@@UEAA@XZ; Uev::UevIPC::~UevIPC(void)
0x1400155a9  jmp     short loc_1400155EF
0x1400155ab  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 4
0x1400155b2  jz      short loc_1400155EF
0x1400155b4  lea     rdx, AgentServiceLog_AppAgentInjectionFailed
0x1400155bb  lea     rax, [rbp+2F0h+lpCommandLine]
0x1400155bf  mov     qword ptr [rbp+2F0h+var_250], rax
0x1400155c6  lea     rax, [rbp+2F0h+var_260]
0x1400155cd  mov     [rsp+3F0h+lpThreadAttributes], rax
0x1400155d2  mov     dword ptr [rbp+2F0h+lpCommandLine], esi
0x1400155d5  mov     qword ptr [rbp+2F0h+var_250+8], 4
0x1400155e0  mov     r9d, r13d
0x1400155e3  lea     rcx, UevAppAgentProvider_Context
0x1400155ea  call    McGenEventWrite_EventWriteTransfer
0x1400155ef  lea     rcx, aAgentserviceCr_48; "AgentService.CreateProcNotificationList"...
0x1400155f6  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x1400155fb  mov     rcx, [rbp+2F0h+var_40]
0x140015602  xor     rcx, rsp; StackCookie
0x140015605  call    __security_check_cookie
0x14001560a  add     rsp, 3C0h
0x140015611  pop     r15
0x140015613  pop     r14
0x140015615  pop     r13
0x140015617  pop     rdi
0x140015618  pop     rsi
0x140015619  pop     rbx
0x14001561a  pop     rbp
0x14001561b  retn
```
