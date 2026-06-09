# CUserModeHangReport::_PreCreateReport(void)

- ea: `0x140027d70`
- end: `0x1400281fb`
- name: `?_PreCreateReport@CUserModeHangReport@@EEAAJXZ`
- size: `1163`
- prototype: `__int64 __fastcall(CUserModeHangReport *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400030f8`
- `0x140003d34`
- `0x140005550`
- `0x140014ee4`
- `0x140014f14`
- `0x1400166ec`
- `0x14001d9ec`
- `0x140023e8c`
- `0x140027d70`
- `0x140030e9c`
- `0x140031044`
- `0x140034f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400280a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400280a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400280de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400280de`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140027f28`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140027f28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140027f9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140027f9d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140027f54`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140027f54`
- `RMCLIENT!HamConnectToServer` at `0x1400280c4`
- `RMCLIENT!HamConnectToServer` at `0x1400280c4`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x14002816e`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x14002816e`
- `ext-ms-win-wer-ui-l1-1-1!WerUIpHeadlessOrImersive` at `0x140027e8d`
- `ext-ms-win-wer-ui-l1-1-1!WerUIpHeadlessOrImersive` at `0x140027e8d`

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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids);
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
              WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids,
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
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids);
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
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids);
            }
          }
          else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              67,
              WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids,
              RecoveryRoutine);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids);
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
            WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids,
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
          WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids,
          (unsigned int)v7);
      }
      return v8;
    }
  }
}

```

## disassembly

```asm
0x140027d70  push    rbp
0x140027d72  push    rbx
0x140027d73  push    rsi
0x140027d74  push    rdi
0x140027d75  push    r12
0x140027d77  push    r13
0x140027d79  push    r14
0x140027d7b  push    r15
0x140027d7d  mov     rbp, rsp
0x140027d80  sub     rsp, 78h
0x140027d84  xor     r12d, r12d
0x140027d87  mov     rbx, rcx
0x140027d8a  xor     edx, edx; Val
0x140027d8c  mov     dword ptr [rbp+TokenHandle], r12d
0x140027d90  lea     rcx, [rbp+var_48]; void *
0x140027d94  lea     r15d, [r12+40h]
0x140027d99  mov     r8d, r15d; Size
0x140027d9c  call    memset_0
0x140027da1  mov     [rbp+arg_10], r12d
0x140027da5  mov     [rbp+arg_18], r12d
0x140027da9  mov     [rbp+TokenInformation], r12d
0x140027dad  cmp     [rbx+5F70h], r12
0x140027db4  jnz     short loc_140027DBB
0x140027db6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140027dbb  cmp     [rbx+5D60h], r12
0x140027dc2  jnz     short loc_140027DC9
0x140027dc4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140027dc9  mov     rax, [rbx+5F70h]
0x140027dd0  test    dword ptr [rax+5A0h], 83C5h
0x140027dda  jz      short loc_140027E20
0x140027ddc  mov     rcx, rbx; this
0x140027ddf  call    ?AcquireReportingLocks@CUserModeHangReport@@AEAAJXZ; CUserModeHangReport::AcquireReportingLocks(void)
0x140027de4  test    eax, eax
0x140027de6  jns     short loc_140027E20
0x140027de8  mov     rcx, cs:WPP_GLOBAL_Control
0x140027def  lea     rdi, WPP_GLOBAL_Control
0x140027df6  cmp     rcx, rdi
0x140027df9  jz      short loc_140027E16
0x140027dfb  test    byte ptr [rcx+1Ch], 1
0x140027dff  jz      short loc_140027E16
0x140027e01  mov     rcx, [rcx+10h]
0x140027e05  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140027e0c  mov     edx, 3Eh ; '>'
0x140027e11  call    WPP_SF_
0x140027e16  mov     eax, 801B8004h
0x140027e1b  jmp     loc_1400281E9
0x140027e20  lea     rcx, [rbx+6220h]; this
0x140027e27  call    ?Init@CThreadChasing@@QEAAJXZ; CThreadChasing::Init(void)
0x140027e2c  mov     r14d, eax
0x140027e2f  test    eax, eax
0x140027e31  jns     short loc_140027E6C
0x140027e33  mov     rcx, cs:WPP_GLOBAL_Control
0x140027e3a  lea     rdi, WPP_GLOBAL_Control
0x140027e41  cmp     rcx, rdi
0x140027e44  jz      short loc_140027E64
0x140027e46  test    byte ptr [rcx+1Ch], 1
0x140027e4a  jz      short loc_140027E64
0x140027e4c  mov     rcx, [rcx+10h]
0x140027e50  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140027e57  mov     edx, 3Fh ; '?'
0x140027e5c  mov     r9d, eax
0x140027e5f  call    WPP_SF_d
0x140027e64  mov     eax, r14d
0x140027e67  jmp     loc_1400281E9
0x140027e6c  lea     r14, [rbx+615Ch]
0x140027e73  or      dword ptr [r14], 8000100h
0x140027e7a  call    IsWerUIpSetWindowSubclassPresent
0x140027e7f  test    al, al
0x140027e81  jz      short loc_140027E99
0x140027e83  mov     rcx, [rbx+5F70h]
0x140027e8a  mov     rdx, r14
0x140027e8d  call    cs:__imp_WerUIpHeadlessOrImersive
0x140027e94  nop     dword ptr [rax+rax+00h]
0x140027e99  mov     rax, [rbx+5F70h]
0x140027ea0  lea     rsi, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140027ea7  mov     r13d, 4
0x140027ead  lea     rdi, WPP_GLOBAL_Control
0x140027eb4  test    dword ptr [rax+5A0h], 1C8h
0x140027ebe  jnz     loc_140027FD8
0x140027ec4  mov     rax, [rbx+5D60h]
0x140027ecb  test    dword ptr [rax+748h], 0FFFFFFFDh
0x140027ed5  jnz     loc_140027FD8
0x140027edb  mov     rcx, [rbx+6090h]
0x140027ee2  lea     r9, [rbp+arg_10]
0x140027ee6  lea     r8, [rbp+TokenHandle]
0x140027eea  xor     edx, edx
0x140027eec  call    WerpGetRestartCommandLine
0x140027ef1  test    eax, eax
0x140027ef3  js      loc_140027FAB
0x140027ef9  cmp     dword ptr [rbp+TokenHandle], r12d
0x140027efd  jbe     loc_140027FD8
0x140027f03  test    byte ptr [rbp+arg_10], 2
0x140027f07  jnz     loc_140027FD8
0x140027f0d  lea     rcx, [rbp+TokenHandle]
0x140027f11  mov     [rbp+TokenHandle], r12
0x140027f15  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x140027f1a  mov     rcx, [rbx+6090h]; ProcessHandle
0x140027f21  lea     edx, [r13+4]; DesiredAccess
0x140027f25  mov     r8, rax; TokenHandle
0x140027f28  call    cs:__imp_OpenProcessToken
0x140027f2f  nop     dword ptr [rax+rax+00h]
0x140027f34  test    eax, eax
0x140027f36  jz      short loc_140027F8F
0x140027f38  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140027f3c  lea     rax, [rbp+arg_18]
0x140027f40  mov     r9d, r13d; TokenInformationLength
0x140027f43  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x140027f48  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140027f4c  mov     [rbp+TokenInformation], r12d
0x140027f50  lea     edx, [r13+19h]; TokenInformationClass
0x140027f54  call    cs:__imp_GetTokenInformation
0x140027f5b  nop     dword ptr [rax+rax+00h]
0x140027f60  test    eax, eax
0x140027f62  jz      short loc_140027F8F
0x140027f64  cmp     [rbp+TokenInformation], r12d
0x140027f68  jnz     short loc_140027F8F
0x140027f6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140027f71  cmp     rcx, rdi
0x140027f74  jz      short loc_140027F8B
0x140027f76  test    [rcx+1Ch], r13b
0x140027f7a  jz      short loc_140027F8B
0x140027f7c  mov     rcx, [rcx+10h]
0x140027f80  mov     edx, r15d
0x140027f83  mov     r8, rsi
0x140027f86  call    WPP_SF_
0x140027f8b  or      dword ptr [r14], 2
0x140027f8f  mov     rcx, [rbp+TokenHandle]; hObject
0x140027f93  lea     rax, [rcx+1]
0x140027f97  cmp     rax, 1
0x140027f9b  jbe     short loc_140027FD8
0x140027f9d  call    cs:__imp_CloseHandle
0x140027fa4  nop     dword ptr [rax+rax+00h]
0x140027fa9  jmp     short loc_140027FD8
0x140027fab  cmp     eax, 80070490h
0x140027fb0  jz      short loc_140027FD8
0x140027fb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140027fb9  cmp     rcx, rdi
0x140027fbc  jz      short loc_140027FD8
0x140027fbe  test    byte ptr [rcx+1Ch], 1
0x140027fc2  jz      short loc_140027FD8
0x140027fc4  mov     rcx, [rcx+10h]
0x140027fc8  mov     edx, 41h ; 'A'
0x140027fcd  mov     r9d, eax
0x140027fd0  mov     r8, rsi
0x140027fd3  call    WPP_SF_d
0x140027fd8  mov     rax, [rbx+5F70h]
0x140027fdf  test    dword ptr [rax+5A0h], 1C8h
0x140027fe9  jnz     loc_140028089
0x140027fef  mov     rcx, [rbx+6090h]; hProcess
0x140027ff6  lea     rdx, [rbp+var_48]
0x140027ffa  call    WerpGetRecoveryRoutine
0x140027fff  mov     r9d, eax
0x140028002  test    eax, eax
0x140028004  jnz     short loc_14002802D
0x140028006  mov     rcx, cs:WPP_GLOBAL_Control
0x14002800d  cmp     rcx, rdi
0x140028010  jz      short loc_140028027
0x140028012  test    [rcx+1Ch], r13b
0x140028016  jz      short loc_140028027
0x140028018  mov     rcx, [rcx+10h]
0x14002801c  lea     edx, [rax+42h]
0x14002801f  mov     r8, rsi
0x140028022  call    WPP_SF_
0x140028027  or      dword ptr [r14], 1
0x14002802b  jmp     short loc_140028089
0x14002802d  mov     ecx, 80000000h
0x140028032  add     eax, ecx
0x140028034  test    ecx, eax
0x140028036  jnz     short loc_140028066
0x140028038  cmp     r9d, 80070490h
0x14002803f  jz      short loc_140028066
0x140028041  mov     rcx, cs:WPP_GLOBAL_Control
0x140028048  cmp     rcx, rdi
0x14002804b  jz      short loc_140028089
0x14002804d  test    byte ptr [rcx+1Ch], 1
0x140028051  jz      short loc_140028089
0x140028053  mov     rcx, [rcx+10h]
0x140028057  mov     edx, 43h ; 'C'
0x14002805c  mov     r8, rsi
0x14002805f  call    WPP_SF_d
0x140028064  jmp     short loc_140028089
0x140028066  mov     rcx, cs:WPP_GLOBAL_Control
0x14002806d  cmp     rcx, rdi
0x140028070  jz      short loc_140028089
0x140028072  test    [rcx+1Ch], r13b
0x140028076  jz      short loc_140028089
0x140028078  mov     rcx, [rcx+10h]
0x14002807c  mov     edx, 44h ; 'D'
0x140028081  mov     r8, rsi
0x140028084  call    WPP_SF_
0x140028089  mov     rax, [rbx+5D60h]
0x140028090  test    byte ptr [rax+708h], 10h
0x140028097  jz      short loc_14002809E
0x140028099  bts     dword ptr [r14], 18h
0x14002809e  lea     r13, [rbx+61F0h]
0x1400280a5  mov     rcx, r13; SRWLock
0x1400280a8  call    cs:__imp_AcquireSRWLockExclusive
0x1400280af  nop     dword ptr [rax+rax+00h]
0x1400280b4  lea     rdx, [r13+8]
0x1400280b8  cmp     [rdx], r12
0x1400280bb  jnz     short loc_1400280D5
0x1400280bd  lea     rcx, ?HamActivityCallback@HamConnector@@CAXPEAU_HAM_ACTIVITY_CALLBACK_PAYLOAD@@@Z; HamConnector::HamActivityCallback(_HAM_ACTIVITY_CALLBACK_PAYLOAD *)
0x1400280c4  call    cs:__imp_HamConnectToServer
0x1400280cb  nop     dword ptr [rax+rax+00h]
0x1400280d0  mov     r15d, eax
0x1400280d3  jmp     short loc_1400280DB
0x1400280d5  mov     r15d, 0C0000510h
0x1400280db  mov     rcx, r13; SRWLock
0x1400280de  call    cs:__imp_ReleaseSRWLockExclusive
0x1400280e5  nop     dword ptr [rax+rax+00h]
0x1400280ea  or      r15d, 10000000h
0x1400280f1  js      loc_14002819E
0x1400280f7  mov     rdx, [rbx+5D60h]
0x1400280fe  cmp     [rdx+710h], r12d
0x140028105  jz      short loc_140028137
0x140028107  cmp     [rbx+6154h], r12d
0x14002810e  jz      short loc_140028123
0x140028110  mov     rax, [rbx+5F70h]
0x140028117  mov     r9b, 1
0x14002811a  test    byte ptr [rax+5A0h], 8
0x140028121  jz      short loc_140028126
0x140028123  mov     r9b, r12b; bool
0x140028126  mov     r8, [rbx+6088h]; void *
0x14002812d  mov     rcx, r13; SRWLock
0x140028130  mov     edx, [rdx]; dwProcessId
0x140028132  call    ?AddExemptionForProcess@HamConnector@@QEAAJKPEAX_N@Z; HamConnector::AddExemptionForProcess(ulong,void *,bool)
0x140028137  mov     edi, 1
0x14002813c  mov     rax, [rbx+5F70h]
0x140028143  lea     ecx, [rdi-1]
0x140028146  mov     esi, [rax+rcx*4+48Ch]
0x14002814d  test    esi, esi
0x14002814f  jz      short loc_140028195
0x140028151  mov     rcx, [rbx+rcx*8+60C0h]; hProcess
0x140028159  lea     rax, [rcx+1]
0x14002815d  cmp     rax, 1
0x140028161  jbe     short loc_140028195
0x140028163  xor     r8d, r8d; packageFullName
0x140028166  mov     dword ptr [rbp+TokenHandle], r12d
0x14002816a  lea     rdx, [rbp+TokenHandle]; packageFullNameLength
0x14002816e  call    cs:__imp_GetPackageFullName
0x140028175  nop     dword ptr [rax+rax+00h]
0x14002817a  cmp     eax, 3D54h
0x14002817f  jz      short loc_140028195
0x140028181  mov     r8, [rbx+6088h]; void *
0x140028188  xor     r9d, r9d; bool
0x14002818b  mov     edx, esi; dwProcessId
0x14002818d  mov     rcx, r13; SRWLock
0x140028190  call    ?AddExemptionForProcess@HamConnector@@QEAAJKPEAX_N@Z; HamConnector::AddExemptionForProcess(ulong,void *,bool)
0x140028195  inc     edi
0x140028197  cmp     edi, 10h
0x14002819a  jb      short loc_14002813C
0x14002819c  jmp     short loc_1400281C4
0x14002819e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400281a5  cmp     rcx, rdi
0x1400281a8  jz      short loc_1400281C4
0x1400281aa  test    byte ptr [rcx+1Ch], 1
0x1400281ae  jz      short loc_1400281C4
0x1400281b0  mov     rcx, [rcx+10h]
0x1400281b4  mov     edx, 45h ; 'E'
0x1400281b9  mov     r9d, r15d
0x1400281bc  mov     r8, rsi
0x1400281bf  call    WPP_SF_d
0x1400281c4  mov     rax, [rbx+5F70h]
0x1400281cb  mov     ecx, [rax+5A0h]
0x1400281d1  and     ecx, 1C0h
0x1400281d7  neg     ecx
0x1400281d9  mov     ecx, 10000h
0x1400281de  sbb     eax, eax
0x1400281e0  and     eax, ecx
0x1400281e2  add     eax, ecx
0x1400281e4  or      [r14], eax
0x1400281e7  xor     eax, eax
0x1400281e9  add     rsp, 78h
0x1400281ed  pop     r15
0x1400281ef  pop     r14
0x1400281f1  pop     r13
0x1400281f3  pop     r12
0x1400281f5  pop     rdi
0x1400281f6  pop     rsi
0x1400281f7  pop     rbx
0x1400281f8  pop     rbp
0x1400281f9  retn
```
