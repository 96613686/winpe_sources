# CUserModeHangReport::_PreCreateReport(void)

- ea: `0x140026410`
- end: `0x14002686a`
- name: `?_PreCreateReport@CUserModeHangReport@@EEAAJXZ`
- size: `1114`
- prototype: `__int64 __fastcall(CUserModeHangReport *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400030a8`
- `0x140003ce4`
- `0x140005498`
- `0x14001444c`
- `0x140014474`
- `0x140015b40`
- `0x14001c7f8`
- `0x1400227ec`
- `0x140026410`
- `0x14002f008`
- `0x14002f194`
- `0x140032bbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140026730`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140026730`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002675a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002675a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400265c2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400265c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002662b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002662b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400265e8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400265e8`
- `RMCLIENT!HamConnectToServer` at `0x140026746`
- `RMCLIENT!HamConnectToServer` at `0x140026746`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x1400267e4`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x1400267e4`
- `ext-ms-win-wer-ui-l1-1-1!WerUIpHeadlessOrImersive` at `0x14002652d`
- `ext-ms-win-wer-ui-l1-1-1!WerUIpHeadlessOrImersive` at `0x14002652d`

## pseudocode

```c
__int64 __fastcall CUserModeHangReport::_PreCreateReport(RTL_SRWLOCK *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  int v7; // eax
  unsigned int v8; // r14d
  _DWORD *v9; // r14
  int RestartCommandLine; // eax
  void **v11; // rax
  unsigned int RecoveryRoutine; // eax
  int v13; // r15d
  int v14; // r15d
  DWORD *Ptr; // rdx
  bool v16; // r9
  unsigned int i; // edi
  __int64 v18; // rcx
  DWORD v19; // esi
  PVOID v20; // rcx
  _BYTE v21[72]; // [rsp+30h] [rbp-48h] BYREF
  int TokenInformation; // [rsp+C0h] [rbp+48h] BYREF
  HANDLE TokenHandle; // [rsp+C8h] [rbp+50h] BYREF
  int v24; // [rsp+D0h] [rbp+58h] BYREF
  DWORD ReturnLength; // [rsp+D8h] [rbp+60h] BYREF

  LODWORD(TokenHandle) = 0;
  memset_0(v21, 0, 0x40u);
  v24 = 0;
  ReturnLength = 0;
  TokenInformation = 0;
  if ( !this[3054].Ptr )
    MicrosoftTelemetryAssertTriggeredNoArgs(v3, v2, v4, v5);
  if ( !this[2988].Ptr )
    MicrosoftTelemetryAssertTriggeredNoArgs(v3, v2, v4, v5);
  if ( (*((_DWORD *)this[3054].Ptr + 360) & 0x83C5) != 0
    && (int)CUserModeHangReport::AcquireReportingLocks((CUserModeHangReport *)this, v2, v4, v5) < 0 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids);
    }
    return 2149285892LL;
  }
  else
  {
    v7 = CThreadChasing::Init((CThreadChasing *)&this[3140]);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v9 = (_DWORD *)&this[3115].Ptr + 1;
      HIDWORD(this[3115].Ptr) |= 0x8000100u;
      if ( (unsigned __int8)IsWerUIpSetWindowSubclassPresent() )
        WerUIpHeadlessOrImersive(this[3054].Ptr, (char *)&this[3115].Ptr + 4);
      if ( (*((_DWORD *)this[3054].Ptr + 360) & 0x1C8) == 0 && (*((_DWORD *)this[2988].Ptr + 466) & 0xFFFFFFFD) == 0 )
      {
        RestartCommandLine = WerpGetRestartCommandLine(this[3090].Ptr, 0, &TokenHandle, &v24);
        if ( RestartCommandLine < 0 )
        {
          if ( RestartCommandLine != -2147023728
            && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              65,
              &WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids,
              (unsigned int)RestartCommandLine);
          }
        }
        else if ( (_DWORD)TokenHandle && (v24 & 2) == 0 )
        {
          TokenHandle = 0;
          v11 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
          if ( OpenProcessToken(this[3090].Ptr, 8u, v11) )
          {
            TokenInformation = 0;
            if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
            {
              if ( !TokenInformation )
              {
                if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids);
                }
                *v9 |= 2u;
              }
            }
          }
          if ( (unsigned __int64)TokenHandle + 1 > 1 )
            CloseHandle(TokenHandle);
        }
      }
      if ( (*((_DWORD *)this[3054].Ptr + 360) & 0x1C8) == 0 )
      {
        RecoveryRoutine = WerpGetRecoveryRoutine(this[3090].Ptr);
        if ( RecoveryRoutine )
        {
          if ( (int)(RecoveryRoutine + 0x80000000) < 0 || RecoveryRoutine == -2147023728 )
          {
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids);
            }
          }
          else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              67,
              &WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids,
              RecoveryRoutine);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids);
          }
          *v9 |= 1u;
        }
      }
      if ( (*((_BYTE *)this[2988].Ptr + 1800) & 0x10) != 0 )
        *v9 |= 0x1000000u;
      AcquireSRWLockExclusive(this + 3134);
      if ( this[3135].Ptr )
        v13 = -1073740528;
      else
        v13 = HamConnectToServer(HamConnector::HamActivityCallback);
      ReleaseSRWLockExclusive(this + 3134);
      v14 = v13 | 0x10000000;
      if ( v14 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            69,
            &WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids,
            (unsigned int)v14);
        }
      }
      else
      {
        Ptr = (DWORD *)this[2988].Ptr;
        if ( Ptr[452] )
        {
          if ( !HIDWORD(this[3114].Ptr) || (v16 = 1, (*((_BYTE *)this[3054].Ptr + 1440) & 8) != 0) )
            v16 = 0;
          HamConnector::AddExemptionForProcess(this + 3134, *Ptr, this[3089].Ptr, v16);
        }
        for ( i = 1; i < 0x10; ++i )
        {
          v18 = i - 1;
          v19 = *((_DWORD *)this[3054].Ptr + v18 + 291);
          if ( v19 )
          {
            v20 = this[v18 + 3096].Ptr;
            if ( (unsigned __int64)v20 + 1 > 1 )
            {
              LODWORD(TokenHandle) = 0;
              if ( GetPackageFullName(v20, (UINT32 *)&TokenHandle, 0) != 15700 )
                HamConnector::AddExemptionForProcess(this + 3134, v19, this[3089].Ptr, 0);
            }
          }
        }
      }
      *v9 |= (*((_DWORD *)this[3054].Ptr + 360) & 0x1C0) != 0 ? 0x20000 : 0x10000;
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          63,
          &WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids,
          (unsigned int)v7);
      }
      return v8;
    }
  }
}

```

## disassembly

```asm
0x140026410  push    rbp
0x140026412  push    rbx
0x140026413  push    rsi
0x140026414  push    rdi
0x140026415  push    r12
0x140026417  push    r13
0x140026419  push    r14
0x14002641b  push    r15
0x14002641d  mov     rbp, rsp
0x140026420  sub     rsp, 78h
0x140026424  xor     r12d, r12d
0x140026427  mov     rbx, rcx
0x14002642a  xor     edx, edx; Val
0x14002642c  mov     dword ptr [rbp+TokenHandle], r12d
0x140026430  lea     rcx, [rbp+var_48]; void *
0x140026434  lea     r15d, [r12+40h]
0x140026439  mov     r8d, r15d; Size
0x14002643c  call    memset_0
0x140026441  mov     [rbp+arg_10], r12d
0x140026445  mov     [rbp+arg_18], r12d
0x140026449  mov     [rbp+TokenInformation], r12d
0x14002644d  cmp     [rbx+5F70h], r12
0x140026454  jnz     short loc_14002645B
0x140026456  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002645b  cmp     [rbx+5D60h], r12
0x140026462  jnz     short loc_140026469
0x140026464  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140026469  mov     rax, [rbx+5F70h]
0x140026470  test    dword ptr [rax+5A0h], 83C5h
0x14002647a  jz      short loc_1400264C0
0x14002647c  mov     rcx, rbx; this
0x14002647f  call    ?AcquireReportingLocks@CUserModeHangReport@@AEAAJXZ; CUserModeHangReport::AcquireReportingLocks(void)
0x140026484  test    eax, eax
0x140026486  jns     short loc_1400264C0
0x140026488  mov     rcx, cs:WPP_GLOBAL_Control
0x14002648f  lea     rdi, WPP_GLOBAL_Control
0x140026496  cmp     rcx, rdi
0x140026499  jz      short loc_1400264B6
0x14002649b  test    byte ptr [rcx+1Ch], 1
0x14002649f  jz      short loc_1400264B6
0x1400264a1  mov     rcx, [rcx+10h]
0x1400264a5  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x1400264ac  mov     edx, 3Eh ; '>'
0x1400264b1  call    WPP_SF_
0x1400264b6  mov     eax, 801B8004h
0x1400264bb  jmp     loc_140026859
0x1400264c0  lea     rcx, [rbx+6220h]; this
0x1400264c7  call    ?Init@CThreadChasing@@QEAAJXZ; CThreadChasing::Init(void)
0x1400264cc  mov     r14d, eax
0x1400264cf  test    eax, eax
0x1400264d1  jns     short loc_14002650C
0x1400264d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400264da  lea     rdi, WPP_GLOBAL_Control
0x1400264e1  cmp     rcx, rdi
0x1400264e4  jz      short loc_140026504
0x1400264e6  test    byte ptr [rcx+1Ch], 1
0x1400264ea  jz      short loc_140026504
0x1400264ec  mov     rcx, [rcx+10h]
0x1400264f0  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x1400264f7  mov     edx, 3Fh ; '?'
0x1400264fc  mov     r9d, eax
0x1400264ff  call    WPP_SF_d
0x140026504  mov     eax, r14d
0x140026507  jmp     loc_140026859
0x14002650c  lea     r14, [rbx+615Ch]
0x140026513  or      dword ptr [r14], 8000100h
0x14002651a  call    IsWerUIpSetWindowSubclassPresent
0x14002651f  test    al, al
0x140026521  jz      short loc_140026533
0x140026523  mov     rcx, [rbx+5F70h]
0x14002652a  mov     rdx, r14
0x14002652d  call    cs:__imp_WerUIpHeadlessOrImersive
0x140026533  mov     rax, [rbx+5F70h]
0x14002653a  lea     rsi, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140026541  mov     r13d, 4
0x140026547  lea     rdi, WPP_GLOBAL_Control
0x14002654e  test    dword ptr [rax+5A0h], 1C8h
0x140026558  jnz     loc_140026660
0x14002655e  mov     rax, [rbx+5D60h]
0x140026565  test    dword ptr [rax+748h], 0FFFFFFFDh
0x14002656f  jnz     loc_140026660
0x140026575  mov     rcx, [rbx+6090h]
0x14002657c  lea     r9, [rbp+arg_10]
0x140026580  lea     r8, [rbp+TokenHandle]
0x140026584  xor     edx, edx
0x140026586  call    WerpGetRestartCommandLine
0x14002658b  test    eax, eax
0x14002658d  js      loc_140026633
0x140026593  cmp     dword ptr [rbp+TokenHandle], r12d
0x140026597  jbe     loc_140026660
0x14002659d  test    byte ptr [rbp+arg_10], 2
0x1400265a1  jnz     loc_140026660
0x1400265a7  lea     rcx, [rbp+TokenHandle]
0x1400265ab  mov     [rbp+TokenHandle], r12
0x1400265af  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1400265b4  mov     rcx, [rbx+6090h]; ProcessHandle
0x1400265bb  lea     edx, [r13+4]; DesiredAccess
0x1400265bf  mov     r8, rax; TokenHandle
0x1400265c2  call    cs:__imp_OpenProcessToken
0x1400265c8  test    eax, eax
0x1400265ca  jz      short loc_14002661D
0x1400265cc  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400265d0  lea     rax, [rbp+arg_18]
0x1400265d4  mov     r9d, r13d; TokenInformationLength
0x1400265d7  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x1400265dc  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1400265e0  mov     [rbp+TokenInformation], r12d
0x1400265e4  lea     edx, [r13+19h]; TokenInformationClass
0x1400265e8  call    cs:__imp_GetTokenInformation
0x1400265ee  test    eax, eax
0x1400265f0  jz      short loc_14002661D
0x1400265f2  cmp     [rbp+TokenInformation], r12d
0x1400265f6  jnz     short loc_14002661D
0x1400265f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400265ff  cmp     rcx, rdi
0x140026602  jz      short loc_140026619
0x140026604  test    [rcx+1Ch], r13b
0x140026608  jz      short loc_140026619
0x14002660a  mov     rcx, [rcx+10h]
0x14002660e  mov     edx, r15d
0x140026611  mov     r8, rsi
0x140026614  call    WPP_SF_
0x140026619  or      dword ptr [r14], 2
0x14002661d  mov     rcx, [rbp+TokenHandle]; hObject
0x140026621  lea     rax, [rcx+1]
0x140026625  cmp     rax, 1
0x140026629  jbe     short loc_140026660
0x14002662b  call    cs:__imp_CloseHandle
0x140026631  jmp     short loc_140026660
0x140026633  cmp     eax, 80070490h
0x140026638  jz      short loc_140026660
0x14002663a  mov     rcx, cs:WPP_GLOBAL_Control
0x140026641  cmp     rcx, rdi
0x140026644  jz      short loc_140026660
0x140026646  test    byte ptr [rcx+1Ch], 1
0x14002664a  jz      short loc_140026660
0x14002664c  mov     rcx, [rcx+10h]
0x140026650  mov     edx, 41h ; 'A'
0x140026655  mov     r9d, eax
0x140026658  mov     r8, rsi
0x14002665b  call    WPP_SF_d
0x140026660  mov     rax, [rbx+5F70h]
0x140026667  test    dword ptr [rax+5A0h], 1C8h
0x140026671  jnz     loc_140026711
0x140026677  mov     rcx, [rbx+6090h]; hProcess
0x14002667e  lea     rdx, [rbp+var_48]
0x140026682  call    WerpGetRecoveryRoutine
0x140026687  mov     r9d, eax
0x14002668a  test    eax, eax
0x14002668c  jnz     short loc_1400266B5
0x14002668e  mov     rcx, cs:WPP_GLOBAL_Control
0x140026695  cmp     rcx, rdi
0x140026698  jz      short loc_1400266AF
0x14002669a  test    [rcx+1Ch], r13b
0x14002669e  jz      short loc_1400266AF
0x1400266a0  mov     rcx, [rcx+10h]
0x1400266a4  lea     edx, [rax+42h]
0x1400266a7  mov     r8, rsi
0x1400266aa  call    WPP_SF_
0x1400266af  or      dword ptr [r14], 1
0x1400266b3  jmp     short loc_140026711
0x1400266b5  mov     ecx, 80000000h
0x1400266ba  add     eax, ecx
0x1400266bc  test    ecx, eax
0x1400266be  jnz     short loc_1400266EE
0x1400266c0  cmp     r9d, 80070490h
0x1400266c7  jz      short loc_1400266EE
0x1400266c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400266d0  cmp     rcx, rdi
0x1400266d3  jz      short loc_140026711
0x1400266d5  test    byte ptr [rcx+1Ch], 1
0x1400266d9  jz      short loc_140026711
0x1400266db  mov     rcx, [rcx+10h]
0x1400266df  mov     edx, 43h ; 'C'
0x1400266e4  mov     r8, rsi
0x1400266e7  call    WPP_SF_d
0x1400266ec  jmp     short loc_140026711
0x1400266ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400266f5  cmp     rcx, rdi
0x1400266f8  jz      short loc_140026711
0x1400266fa  test    [rcx+1Ch], r13b
0x1400266fe  jz      short loc_140026711
0x140026700  mov     rcx, [rcx+10h]
0x140026704  mov     edx, 44h ; 'D'
0x140026709  mov     r8, rsi
0x14002670c  call    WPP_SF_
0x140026711  mov     rax, [rbx+5D60h]
0x140026718  test    byte ptr [rax+708h], 10h
0x14002671f  jz      short loc_140026726
0x140026721  bts     dword ptr [r14], 18h
0x140026726  lea     r13, [rbx+61F0h]
0x14002672d  mov     rcx, r13; SRWLock
0x140026730  call    cs:__imp_AcquireSRWLockExclusive
0x140026736  lea     rdx, [r13+8]
0x14002673a  cmp     [rdx], r12
0x14002673d  jnz     short loc_140026751
0x14002673f  lea     rcx, ?HamActivityCallback@HamConnector@@CAXPEAU_HAM_ACTIVITY_CALLBACK_PAYLOAD@@@Z; HamConnector::HamActivityCallback(_HAM_ACTIVITY_CALLBACK_PAYLOAD *)
0x140026746  call    cs:__imp_HamConnectToServer
0x14002674c  mov     r15d, eax
0x14002674f  jmp     short loc_140026757
0x140026751  mov     r15d, 0C0000510h
0x140026757  mov     rcx, r13; SRWLock
0x14002675a  call    cs:__imp_ReleaseSRWLockExclusive
0x140026760  or      r15d, 10000000h
0x140026767  js      loc_14002680E
0x14002676d  mov     rdx, [rbx+5D60h]
0x140026774  cmp     [rdx+710h], r12d
0x14002677b  jz      short loc_1400267AD
0x14002677d  cmp     [rbx+6154h], r12d
0x140026784  jz      short loc_140026799
0x140026786  mov     rax, [rbx+5F70h]
0x14002678d  mov     r9b, 1
0x140026790  test    byte ptr [rax+5A0h], 8
0x140026797  jz      short loc_14002679C
0x140026799  mov     r9b, r12b; bool
0x14002679c  mov     r8, [rbx+6088h]; void *
0x1400267a3  mov     rcx, r13; SRWLock
0x1400267a6  mov     edx, [rdx]; dwProcessId
0x1400267a8  call    ?AddExemptionForProcess@HamConnector@@QEAAJKPEAX_N@Z; HamConnector::AddExemptionForProcess(ulong,void *,bool)
0x1400267ad  mov     edi, 1
0x1400267b2  mov     rax, [rbx+5F70h]
0x1400267b9  lea     ecx, [rdi-1]
0x1400267bc  mov     esi, [rax+rcx*4+48Ch]
0x1400267c3  test    esi, esi
0x1400267c5  jz      short loc_140026805
0x1400267c7  mov     rcx, [rbx+rcx*8+60C0h]; hProcess
0x1400267cf  lea     rax, [rcx+1]
0x1400267d3  cmp     rax, 1
0x1400267d7  jbe     short loc_140026805
0x1400267d9  xor     r8d, r8d; packageFullName
0x1400267dc  mov     dword ptr [rbp+TokenHandle], r12d
0x1400267e0  lea     rdx, [rbp+TokenHandle]; packageFullNameLength
0x1400267e4  call    cs:__imp_GetPackageFullName
0x1400267ea  cmp     eax, 3D54h
0x1400267ef  jz      short loc_140026805
0x1400267f1  mov     r8, [rbx+6088h]; void *
0x1400267f8  xor     r9d, r9d; bool
0x1400267fb  mov     edx, esi; dwProcessId
0x1400267fd  mov     rcx, r13; SRWLock
0x140026800  call    ?AddExemptionForProcess@HamConnector@@QEAAJKPEAX_N@Z; HamConnector::AddExemptionForProcess(ulong,void *,bool)
0x140026805  inc     edi
0x140026807  cmp     edi, 10h
0x14002680a  jb      short loc_1400267B2
0x14002680c  jmp     short loc_140026834
0x14002680e  mov     rcx, cs:WPP_GLOBAL_Control
0x140026815  cmp     rcx, rdi
0x140026818  jz      short loc_140026834
0x14002681a  test    byte ptr [rcx+1Ch], 1
0x14002681e  jz      short loc_140026834
0x140026820  mov     rcx, [rcx+10h]
0x140026824  mov     edx, 45h ; 'E'
0x140026829  mov     r9d, r15d
0x14002682c  mov     r8, rsi
0x14002682f  call    WPP_SF_d
0x140026834  mov     rax, [rbx+5F70h]
0x14002683b  mov     ecx, [rax+5A0h]
0x140026841  and     ecx, 1C0h
0x140026847  neg     ecx
0x140026849  mov     ecx, 10000h
0x14002684e  sbb     eax, eax
0x140026850  and     eax, ecx
0x140026852  add     eax, ecx
0x140026854  or      [r14], eax
0x140026857  xor     eax, eax
0x140026859  add     rsp, 78h
0x14002685d  pop     r15
0x14002685f  pop     r14
0x140026861  pop     r13
0x140026863  pop     r12
0x140026865  pop     rdi
0x140026866  pop     rsi
0x140026867  pop     rbx
0x140026868  pop     rbp
0x140026869  retn
```
