# CUserLogonProcessingList::LaunchDeviceEncryptionProcess(DeviceEncryptionEventArgs &,CNgscbToken const &)

- ea: `0x180020a90`
- end: `0x180021040`
- name: `?LaunchDeviceEncryptionProcess@CUserLogonProcessingList@@IEAAJAEAUDeviceEncryptionEventArgs@@AEBVCNgscbToken@@@Z`
- size: `1456`
- prototype: `__int64 __fastcall(CUserLogonProcessingList *this, struct DeviceEncryptionEventArgs *, const struct CNgscbToken *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002ac10`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18001a1d0`
- `0x180020a90`
- `0x180021048`
- `0x18002b6ac`
- `0x18002e628`
- `0x18002fb58`
- `0x180034070`
- `0x180034440`
- `0x180034d28`
- `0x180051e78`
- `0x180054fac`
- `0x180056580`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180020ecb`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180020ecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e32`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180020ee7`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180020ee7`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180020e22`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180020e22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002100a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002100a`
- `profapi!__imp_CreateEnvBlock` at `0x180020d9b`
- `profapi!__imp_CreateEnvBlock` at `0x180020d9b`
- `profapi!__imp_DestroyEnvBlock` at `0x180020fb6`
- `profapi!__imp_DestroyEnvBlock` at `0x180020fb6`

## string_xrefs

- `0x180020c30`: `EventArgs.CheckCommonResourceRequirements`
- `0x180020cb5`: `ConnectedUserToken.CheckIsElevatedAdminToken`
- `0x180020d62`: `ConnectedUserToken.GetRestrictedToken`
- `0x180020dd3`: `CreateEnvBlock`
- `0x180020e51`: `CreateProcessAsUserW`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUserLogonProcessingList::LaunchDeviceEncryptionProcess(
        CUserLogonProcessingList *this,
        struct DeviceEncryptionEventArgs *a2,
        const struct CNgscbToken *a3)
{
  HANDLE v6; // rbx
  const struct std::nothrow_t *v7; // rdx
  const char *KnownLastErrorHR; // rdi
  PVOID *v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // eax
  const char *v12; // rax
  __int64 v13; // rdx
  unsigned int v14; // eax
  CUserLogonProcessingList *v15; // rcx
  unsigned int AdminUserProfile; // eax
  unsigned int v17; // r8d
  unsigned int RestrictedToken; // eax
  unsigned int v19; // eax
  signed int LastError; // eax
  __int64 v21; // rdx
  __int64 v22; // r9
  const char *bInheritHandles; // [rsp+28h] [rbp-D8h]
  const char *bInheritHandlesa; // [rsp+28h] [rbp-D8h]
  bool v26; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hToken; // [rsp+68h] [rbp-98h] BYREF
  int v28[4]; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR lpCommandLine; // [rsp+80h] [rbp-80h] BYREF
  LPVOID lpEnvironment; // [rsp+88h] [rbp-78h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v32[4]; // [rsp+A8h] [rbp-58h] BYREF
  DWORD ExitCode; // [rsp+ACh] [rbp-54h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE Handles[2]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  lpCommandLine = 0;
  lpEnvironment = 0;
  v32[0] = 0;
  ExitCode = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v28[0] = 22;
  v28[1] = 23;
  v28[2] = 18;
  v6 = 0;
  hToken = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  *(_OWORD *)Handles = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 221, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
  LODWORD(KnownLastErrorHR) = CUserLogonProcessingList::GetDeviceEncryptionProcessCmdLine(this, a2, a3, &lpCommandLine);
  if ( !(_DWORD)KnownLastErrorHR )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_11;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      222,
      &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
      (unsigned int)KnownLastErrorHR);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (int)KnownLastErrorHR >= 0 )
  {
LABEL_11:
    if ( !lpCommandLine )
    {
      if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 8) == 0 )
        goto LABEL_64;
      v10 = 223;
LABEL_15:
      WPP_SF_(v9[2], v10, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
      goto LABEL_63;
    }
    v11 = std::_Func_class<long,bool *>::operator()((char *)a2 + 24, v32);
    LODWORD(KnownLastErrorHR) = v11;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 224, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v11);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (int)KnownLastErrorHR >= 0 )
    {
      if ( !v32[0] )
      {
        if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 4) == 0 )
          goto LABEL_64;
        v10 = 225;
        goto LABEL_15;
      }
      v14 = CNgscbToken::CheckIsElevatedAdminToken(a3, &v26);
      LODWORD(KnownLastErrorHR) = v14;
      v15 = (CUserLogonProcessingList *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 226, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v14);
      if ( (int)KnownLastErrorHR >= 0 )
      {
        if ( !v26 )
        {
          LODWORD(KnownLastErrorHR) = CUserLogonProcessingList::ProcessNonAdminUserLogon(v15, lpCommandLine);
          goto LABEL_63;
        }
        AdminUserProfile = CUserLogonProcessingList::LoadAdminUserProfile(a3);
        LODWORD(KnownLastErrorHR) = AdminUserProfile;
        if ( AdminUserProfile )
        {
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              227,
              &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
              AdminUserProfile);
            v9 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( (int)KnownLastErrorHR < 0 )
            goto LABEL_64;
        }
        RestrictedToken = CNgscbToken::GetRestrictedToken(a3, v28, v17, (struct CNgscbToken *)&hToken);
        LODWORD(KnownLastErrorHR) = RestrictedToken;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            228,
            &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
            RestrictedToken);
        if ( (int)KnownLastErrorHR < 0 )
        {
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0xC3B,
            (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
            (const char *)(unsigned int)KnownLastErrorHR,
            (int)"ConnectedUserToken.GetRestrictedToken",
            bInheritHandles);
          v6 = hToken;
          goto LABEL_63;
        }
        v6 = hToken;
        v19 = CreateEnvBlock(&lpEnvironment, hToken, 0);
        LODWORD(KnownLastErrorHR) = v19;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v19);
        if ( (int)KnownLastErrorHR >= 0 )
        {
          if ( CreateProcessAsUserW(
                 v6,
                 0,
                 lpCommandLine,
                 0,
                 0,
                 0,
                 0x4400u,
                 lpEnvironment,
                 0,
                 &StartupInfo,
                 &ProcessInformation) )
          {
            Handles[0] = ProcessInformation.hProcess;
            Handles[1] = *((HANDLE *)this + 16);
            if ( !WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0) )
            {
              if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
              {
                v9 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                  goto LABEL_64;
                v21 = 232;
                v22 = ExitCode;
              }
              else
              {
                KnownLastErrorHR = (const char *)(unsigned int)NgscbGetKnownLastErrorHR();
                wil::details::in1diag3::Log_HrMsg(
                  retaddr,
                  (void *)0xC6E,
                  (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
                  KnownLastErrorHR,
                  (int)"ProcessExit",
                  bInheritHandlesa);
                v9 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
                  goto LABEL_64;
                v21 = 231;
                v22 = (unsigned int)KnownLastErrorHR;
              }
              WPP_SF_d(v9[2], v21, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v22);
            }
          }
          else
          {
            LastError = GetLastError();
            LODWORD(KnownLastErrorHR) = LastError;
            if ( LastError > 0 )
              LODWORD(KnownLastErrorHR) = (unsigned __int16)LastError | 0x80070000;
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0xC56,
              (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
              (const char *)(unsigned int)KnownLastErrorHR,
              (int)"CreateProcessAsUserW",
              bInheritHandlesa);
            v9 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_64;
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              230,
              &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
              (unsigned int)KnownLastErrorHR);
          }
LABEL_63:
          v9 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_64;
        }
        v12 = "CreateEnvBlock";
        v13 = 3135;
      }
      else
      {
        v12 = "ConnectedUserToken.CheckIsElevatedAdminToken";
        v13 = 3100;
      }
    }
    else
    {
      v12 = "EventArgs.CheckCommonResourceRequirements";
      v13 = 3091;
    }
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v13,
      (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
      (const char *)(unsigned int)KnownLastErrorHR,
      (int)v12,
      bInheritHandles);
    goto LABEL_63;
  }
LABEL_64:
  if ( ProcessInformation.hThread )
  {
    CloseHandle(ProcessInformation.hThread);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( ProcessInformation.hProcess )
  {
    CloseHandle(ProcessInformation.hProcess);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( lpEnvironment )
  {
    DestroyEnvBlock(lpEnvironment);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( lpCommandLine )
  {
    operator delete(lpCommandLine, v7);
    lpCommandLine = 0;
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x20) != 0 )
    WPP_SF_(v9[2], 233, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
  if ( v6 )
    CloseHandle(v6);
  return (unsigned int)KnownLastErrorHR;
}

```

## disassembly

```asm
0x180020a90  mov     [rsp-8+arg_18], rbx
0x180020a95  push    rbp
0x180020a96  push    rsi
0x180020a97  push    rdi
0x180020a98  push    r12
0x180020a9a  push    r13
0x180020a9c  push    r14
0x180020a9e  push    r15
0x180020aa0  lea     rbp, [rsp-40h]
0x180020aa5  sub     rsp, 140h
0x180020aac  mov     rax, cs:__security_cookie
0x180020ab3  xor     rax, rsp
0x180020ab6  mov     [rbp+70h+var_40], rax
0x180020aba  mov     rsi, r8
0x180020abd  mov     r14, rdx
0x180020ac0  mov     r15, rcx
0x180020ac3  xor     r12d, r12d
0x180020ac6  mov     [rbp+70h+lpCommandLine], r12
0x180020aca  mov     [rbp+70h+var_E8], r12
0x180020ace  mov     [rbp+70h+var_C8], r12b
0x180020ad2  mov     [rbp+70h+ExitCode], r12d
0x180020ad6  xorps   xmm0, xmm0
0x180020ad9  xor     eax, eax
0x180020adb  movups  xmmword ptr [rbp+70h+ProcessInformation.hProcess], xmm0
0x180020adf  mov     qword ptr [rbp+70h+ProcessInformation.dwProcessId], rax
0x180020ae3  mov     [rsp+170h+var_100], 16h
0x180020aeb  mov     [rsp+170h+var_FC], 17h
0x180020af3  mov     [rsp+170h+var_F8], 12h
0x180020afb  mov     ebx, r12d
0x180020afe  mov     [rsp+170h+hToken], rbx
0x180020b03  xor     edx, edx; Val
0x180020b05  lea     r8d, [r12+68h]; Size
0x180020b0a  lea     rcx, [rbp+70h+StartupInfo]; void *
0x180020b0e  call    memset_0
0x180020b13  xorps   xmm0, xmm0
0x180020b16  movups  xmmword ptr [rbp+70h+Handles], xmm0
0x180020b1a  mov     [rsp+170h+var_110], r12b
0x180020b1f  lea     rax, WPP_GLOBAL_Control
0x180020b26  lea     r13, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x180020b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b34  cmp     rcx, rax
0x180020b37  jz      short loc_180020B50
0x180020b39  test    byte ptr [rcx+1Ch], 20h
0x180020b3d  jz      short loc_180020B50
0x180020b3f  mov     edx, 0DDh
0x180020b44  mov     r8, r13
0x180020b47  mov     rcx, [rcx+10h]
0x180020b4b  call    WPP_SF_
0x180020b50  lea     r9, [rbp+70h+lpCommandLine]; unsigned __int16 **
0x180020b54  mov     r8, rsi; struct CNgscbToken *
0x180020b57  mov     rdx, r14; struct DeviceEncryptionEventArgs *
0x180020b5a  mov     rcx, r15; this
0x180020b5d  call    ?GetDeviceEncryptionProcessCmdLine@CUserLogonProcessingList@@IEAAJAEBUDeviceEncryptionEventArgs@@AEBVCNgscbToken@@PEAPEAG@Z; CUserLogonProcessingList::GetDeviceEncryptionProcessCmdLine(DeviceEncryptionEventArgs const &,CNgscbToken const &,ushort * *)
0x180020b62  mov     edi, eax
0x180020b64  test    eax, eax
0x180020b66  jz      short loc_180020BAC
0x180020b68  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b6f  lea     rax, WPP_GLOBAL_Control
0x180020b76  cmp     rcx, rax
0x180020b79  jz      short loc_180020B9C
0x180020b7b  test    byte ptr [rcx+1Ch], 40h
0x180020b7f  jz      short loc_180020B9C
0x180020b81  mov     edx, 0DEh
0x180020b86  mov     r9d, edi
0x180020b89  mov     r8, r13
0x180020b8c  mov     rcx, [rcx+10h]
0x180020b90  call    WPP_SF_d
0x180020b95  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b9c  test    edi, edi
0x180020b9e  jns     short loc_180020BB3
0x180020ba0  lea     r14, WPP_GLOBAL_Control
0x180020ba7  jmp     loc_180020F6C
0x180020bac  mov     rcx, cs:WPP_GLOBAL_Control
0x180020bb3  cmp     [rbp+70h+lpCommandLine], r12
0x180020bb7  jnz     short loc_180020BE9
0x180020bb9  lea     r14, WPP_GLOBAL_Control
0x180020bc0  cmp     rcx, r14
0x180020bc3  jz      loc_180020F6C
0x180020bc9  test    byte ptr [rcx+1Ch], 8
0x180020bcd  jz      loc_180020F6C
0x180020bd3  mov     edx, 0DFh
0x180020bd8  mov     r8, r13
0x180020bdb  mov     rcx, [rcx+10h]
0x180020bdf  call    WPP_SF_
0x180020be4  jmp     loc_180020F65
0x180020be9  lea     rcx, [r14+18h]
0x180020bed  lea     rdx, [rbp+70h+var_C8]
0x180020bf1  call    ??R?$_Func_class@JPEA_N@std@@QEBAJPEA_N@Z; std::_Func_class<long,bool *>::operator()(bool *)
0x180020bf6  mov     edi, eax
0x180020bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180020bff  lea     r14, WPP_GLOBAL_Control
0x180020c06  cmp     rcx, r14
0x180020c09  jz      short loc_180020C2C
0x180020c0b  test    byte ptr [rcx+1Ch], 40h
0x180020c0f  jz      short loc_180020C2C
0x180020c11  mov     edx, 0E0h
0x180020c16  mov     r9d, eax
0x180020c19  mov     r8, r13
0x180020c1c  mov     rcx, [rcx+10h]
0x180020c20  call    WPP_SF_d
0x180020c25  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c2c  test    edi, edi
0x180020c2e  jns     short loc_180020C59
0x180020c30  lea     rax, aEventargsCheck; "EventArgs.CheckCommonResourceRequiremen"...
0x180020c37  mov     edx, 0C13h; void *
0x180020c3c  mov     rcx, [rbp+78h]; this
0x180020c40  mov     [rsp+170h+lpThreadAttributes], rax; int
0x180020c45  mov     r9d, edi; char *
0x180020c48  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x180020c4f  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180020c54  jmp     loc_180020F65
0x180020c59  cmp     [rbp+70h+var_C8], r12b
0x180020c5d  jnz     short loc_180020C7C
0x180020c5f  cmp     rcx, r14
0x180020c62  jz      loc_180020F6C
0x180020c68  test    byte ptr [rcx+1Ch], 4
0x180020c6c  jz      loc_180020F6C
0x180020c72  mov     edx, 0E1h
0x180020c77  jmp     loc_180020BD8
0x180020c7c  lea     rdx, [rsp+170h+var_110]; bool *
0x180020c81  mov     rcx, rsi; this
0x180020c84  call    ?CheckIsElevatedAdminToken@CNgscbToken@@QEBAJPEA_N@Z; CNgscbToken::CheckIsElevatedAdminToken(bool *)
0x180020c89  mov     edi, eax
0x180020c8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c92  cmp     rcx, r14
0x180020c95  jz      short loc_180020CB1
0x180020c97  test    byte ptr [rcx+1Ch], 40h
0x180020c9b  jz      short loc_180020CB1
0x180020c9d  mov     edx, 0E2h
0x180020ca2  mov     r9d, eax
0x180020ca5  mov     r8, r13
0x180020ca8  mov     rcx, [rcx+10h]
0x180020cac  call    WPP_SF_d
0x180020cb1  test    edi, edi
0x180020cb3  jns     short loc_180020CC6
0x180020cb5  lea     rax, aConnectedusert; "ConnectedUserToken.CheckIsElevatedAdmin"...
0x180020cbc  mov     edx, 0C1Ch
0x180020cc1  jmp     loc_180020C3C
0x180020cc6  cmp     [rsp+170h+var_110], r12b
0x180020ccb  jnz     short loc_180020CDD
0x180020ccd  mov     rdx, [rbp+70h+lpCommandLine]; unsigned __int16 *
0x180020cd1  call    ?ProcessNonAdminUserLogon@CUserLogonProcessingList@@IEAAJQEAG@Z; CUserLogonProcessingList::ProcessNonAdminUserLogon(ushort * const)
0x180020cd6  mov     edi, eax
0x180020cd8  jmp     loc_180020F65
0x180020cdd  mov     rcx, rsi; struct CNgscbToken *
0x180020ce0  call    ?LoadAdminUserProfile@CUserLogonProcessingList@@KAJAEBVCNgscbToken@@@Z; CUserLogonProcessingList::LoadAdminUserProfile(CNgscbToken const &)
0x180020ce5  mov     edi, eax
0x180020ce7  test    eax, eax
0x180020ce9  jz      short loc_180020D20
0x180020ceb  mov     rcx, cs:WPP_GLOBAL_Control
0x180020cf2  cmp     rcx, r14
0x180020cf5  jz      short loc_180020D18
0x180020cf7  test    byte ptr [rcx+1Ch], 40h
0x180020cfb  jz      short loc_180020D18
0x180020cfd  mov     edx, 0E3h
0x180020d02  mov     r9d, eax
0x180020d05  mov     r8, r13
0x180020d08  mov     rcx, [rcx+10h]
0x180020d0c  call    WPP_SF_d
0x180020d11  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d18  test    edi, edi
0x180020d1a  js      loc_180020F6C
0x180020d20  lea     r9, [rsp+170h+hToken]; struct CNgscbToken *
0x180020d25  lea     rdx, [rsp+170h+var_100]; int *
0x180020d2a  mov     rcx, rsi; this
0x180020d2d  call    ?GetRestrictedToken@CNgscbToken@@QEBAJPEBJKAEAV1@@Z; CNgscbToken::GetRestrictedToken(long const *,ulong,CNgscbToken &)
0x180020d32  mov     edi, eax
0x180020d34  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d3b  cmp     rcx, r14
0x180020d3e  jz      short loc_180020D5A
0x180020d40  test    byte ptr [rcx+1Ch], 40h
0x180020d44  jz      short loc_180020D5A
0x180020d46  mov     edx, 0E4h
0x180020d4b  mov     r9d, eax
0x180020d4e  mov     r8, r13
0x180020d51  mov     rcx, [rcx+10h]
0x180020d55  call    WPP_SF_d
0x180020d5a  test    edi, edi
0x180020d5c  jns     short loc_180020D8C
0x180020d5e  mov     rcx, [rbp+78h]; this
0x180020d62  lea     rax, aConnectedusert_0; "ConnectedUserToken.GetRestrictedToken"
0x180020d69  mov     [rsp+170h+lpThreadAttributes], rax; int
0x180020d6e  mov     r9d, edi; char *
0x180020d71  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x180020d78  mov     edx, 0C3Bh; void *
0x180020d7d  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180020d82  mov     rbx, [rsp+170h+hToken]
0x180020d87  jmp     loc_180020F65
0x180020d8c  xor     r8d, r8d
0x180020d8f  mov     rbx, [rsp+170h+hToken]
0x180020d94  mov     rdx, rbx
0x180020d97  lea     rcx, [rbp+70h+var_E8]
0x180020d9b  call    cs:__imp_CreateEnvBlock
0x180020da2  nop     dword ptr [rax+rax+00h]
0x180020da7  mov     edi, eax
0x180020da9  mov     rcx, cs:WPP_GLOBAL_Control
0x180020db0  cmp     rcx, r14
0x180020db3  jz      short loc_180020DCF
0x180020db5  test    byte ptr [rcx+1Ch], 40h
0x180020db9  jz      short loc_180020DCF
0x180020dbb  mov     edx, 0E5h
0x180020dc0  mov     r9d, eax
0x180020dc3  mov     r8, r13
0x180020dc6  mov     rcx, [rcx+10h]
0x180020dca  call    WPP_SF_d
0x180020dcf  test    edi, edi
0x180020dd1  jns     short loc_180020DE4
0x180020dd3  lea     rax, aCreateenvblock; "CreateEnvBlock"
0x180020dda  mov     edx, 0C3Fh
0x180020ddf  jmp     loc_180020C3C
0x180020de4  mov     rax, [rbp+70h+var_E8]
0x180020de8  lea     rcx, [rbp+70h+ProcessInformation]
0x180020dec  mov     [rsp+170h+lpProcessInformation], rcx; lpProcessInformation
0x180020df1  lea     rcx, [rbp+70h+StartupInfo]
0x180020df5  mov     [rsp+170h+lpStartupInfo], rcx; lpStartupInfo
0x180020dfa  mov     [rsp+170h+lpCurrentDirectory], r12; lpCurrentDirectory
0x180020dff  mov     [rsp+170h+lpEnvironment], rax; lpEnvironment
0x180020e04  mov     [rsp+170h+dwCreationFlags], 4400h; dwCreationFlags
0x180020e0c  mov     dword ptr [rsp+170h+bInheritHandles], r12d; char *
0x180020e11  mov     [rsp+170h+lpThreadAttributes], r12; lpThreadAttributes
0x180020e16  xor     r9d, r9d; lpProcessAttributes
0x180020e19  mov     r8, [rbp+70h+lpCommandLine]; lpCommandLine
0x180020e1d  xor     edx, edx; lpApplicationName
0x180020e1f  mov     rcx, rbx; hToken
0x180020e22  call    cs:__imp_CreateProcessAsUserW
0x180020e29  nop     dword ptr [rax+rax+00h]
0x180020e2e  test    eax, eax
0x180020e30  jnz     short loc_180020EA4
0x180020e32  call    cs:__imp_GetLastError
0x180020e39  nop     dword ptr [rax+rax+00h]
0x180020e3e  mov     edi, eax
0x180020e40  test    eax, eax
0x180020e42  jle     short loc_180020E4D
0x180020e44  movzx   edi, ax
0x180020e47  or      edi, 80070000h
0x180020e4d  mov     rcx, [rbp+78h]; this
0x180020e51  lea     rax, aCreateprocessa; "CreateProcessAsUserW"
0x180020e58  mov     [rsp+170h+lpThreadAttributes], rax; int
0x180020e5d  mov     r9d, edi; char *
0x180020e60  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x180020e67  mov     edx, 0C56h; void *
0x180020e6c  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180020e71  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e78  cmp     rcx, r14
0x180020e7b  jz      loc_180020F6C
0x180020e81  test    byte ptr [rcx+1Ch], 2
0x180020e85  jz      loc_180020F6C
0x180020e8b  mov     edx, 0E6h
0x180020e90  mov     r9d, edi
0x180020e93  mov     r8, r13
0x180020e96  mov     rcx, [rcx+10h]
0x180020e9a  call    WPP_SF_d
0x180020e9f  jmp     loc_180020F65
0x180020ea4  mov     rax, [rbp+70h+ProcessInformation.hProcess]
0x180020ea8  mov     [rbp+70h+Handles], rax
0x180020eac  mov     rax, [r15+80h]
0x180020eb3  mov     [rbp+70h+Handles+8], rax
0x180020eb7  mov     dword ptr [rsp+170h+lpThreadAttributes], r12d; bAlertable
0x180020ebc  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180020ec0  xor     r8d, r8d; bWaitAll
0x180020ec3  lea     rdx, [rbp+70h+Handles]; lpHandles
0x180020ec7  lea     ecx, [r8+2]; nCount
0x180020ecb  call    cs:__imp_WaitForMultipleObjectsEx
0x180020ed2  nop     dword ptr [rax+rax+00h]
0x180020ed7  test    eax, eax
0x180020ed9  jnz     loc_180020F65
0x180020edf  lea     rdx, [rbp+70h+ExitCode]; lpExitCode
0x180020ee3  mov     rcx, [rbp+70h+ProcessInformation.hProcess]; hProcess
0x180020ee7  call    cs:__imp_GetExitCodeProcess
0x180020eee  nop     dword ptr [rax+rax+00h]
0x180020ef3  test    eax, eax
0x180020ef5  jnz     short loc_180020F3E
0x180020ef7  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x180020efc  mov     edi, eax
0x180020efe  mov     rcx, [rbp+78h]; this
0x180020f02  lea     rax, aProcessexit; "ProcessExit"
0x180020f09  mov     [rsp+170h+lpThreadAttributes], rax; int
0x180020f0e  mov     r9d, edi; char *
0x180020f11  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x180020f18  mov     edx, 0C6Eh; void *
0x180020f1d  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180020f22  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f29  cmp     rcx, r14
0x180020f2c  jz      short loc_180020F6C
0x180020f2e  test    byte ptr [rcx+1Ch], 40h
0x180020f32  jz      short loc_180020F6C
0x180020f34  mov     edx, 0E7h
0x180020f39  mov     r9d, edi
0x180020f3c  jmp     short loc_180020F59
0x180020f3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f45  cmp     rcx, r14
0x180020f48  jz      short loc_180020F6C
0x180020f4a  test    byte ptr [rcx+1Ch], 8
0x180020f4e  jz      short loc_180020F6C
0x180020f50  mov     edx, 0E8h
0x180020f55  mov     r9d, [rbp+70h+ExitCode]
0x180020f59  mov     r8, r13
0x180020f5c  mov     rcx, [rcx+10h]
0x180020f60  call    WPP_SF_d
0x180020f65  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
