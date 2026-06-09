# _ExecuteSsoAuthHostCommand

- ea: `0x180010494`
- end: `0x1800109b1`
- name: `_ExecuteSsoAuthHostCommand`
- size: `1309`
- prototype: `__int64 __fastcall(unsigned int brokerFlags, const wchar_t *commandLineArg)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800119e0`

## callees

- `0x180004940`
- `0x18000737c`
- `0x180007a68`
- `0x18000f488`
- `0x18000fcfc`
- `0x18001009c`
- `0x180010494`
- `0x1800109b8`
- `0x180010e58`
- `0x180011b30`
- `0x180011b58`
- `0x1800204ee`
- `0x180020520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010829`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001084f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001084f`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180010845`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180010845`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010666`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010666`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180010975`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180010975`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x1800107b5`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x1800107b5`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180010674`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180010674`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x1800106f9`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x1800106f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010951`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010951`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800105e8`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800105e8`

## pseudocode

```c
__int64 __fastcall ExecuteSsoAuthHostCommand(unsigned int brokerFlags, const wchar_t *commandLineArg)
{
  unsigned int AuthHostRegDWORDValue; // eax
  unsigned int v5; // esi
  int v6; // eax
  unsigned int v7; // r12d
  signed int v8; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v9; // rcx
  unsigned __int16 v10; // dx
  unsigned int v11; // r9d
  unsigned int v12; // r14d
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  WPP_PROJECT_CONTROL_BLOCK *v15; // rcx
  signed int v16; // eax
  signed int AuthHostProcess; // eax
  signed int v18; // eax
  unsigned int v19; // eax
  signed int v20; // eax
  unsigned int capabilityCount; // [rsp+40h] [rbp-C0h] BYREF
  int isWow64; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int exitCode; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *systemDirectoryPath; // [rsp+50h] [rbp-B0h] BYREF
  void *appContainerSid; // [rsp+58h] [rbp-A8h] BYREF
  void *prevRedirect; // [rsp+60h] [rbp-A0h] BYREF
  _AUTH_HOST_PROCESS_CONTEXT processContext; // [rsp+68h] [rbp-98h] BYREF
  _SID_AND_ATTRIBUTES capabilitySidAndAttributes[5]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t applicationName[264]; // [rsp+D0h] [rbp-30h] BYREF

  systemDirectoryPath = 0;
  capabilitySidAndAttributes[0].Sid = 0;
  processContext = 0;
  memset_0(&capabilitySidAndAttributes[0].Attributes, 0, 0x48u);
  capabilityCount = 0;
  appContainerSid = 0;
  AuthHostRegDWORDValue = GetAuthHostRegDWORDValue(L"EnablePrivateNetwork");
  isWow64 = 0;
  prevRedirect = 0;
  v5 = AuthHostRegDWORDValue;
  v6 = InitializeAuthHostCapabilitySidAndAttributes(
         brokerFlags,
         AuthHostRegDWORDValue,
         capabilitySidAndAttributes,
         &capabilityCount);
  v7 = 5;
  v8 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) == 0
      || WPP_GLOBAL_Control[1].Control.Level < 2u )
    {
      goto LABEL_78;
    }
    v10 = 78;
    goto LABEL_6;
  }
  v12 = capabilityCount;
  v6 = CreateAuthHostAppContainer(
         brokerFlags,
         1,
         v5,
         capabilitySidAndAttributes,
         capabilityCount,
         &appContainerSid,
         &processContext.appContainerIndex);
  v8 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0 )
    {
      if ( WPP_GLOBAL_Control[1].Control.Level >= 2u )
      {
        v10 = 79;
LABEL_6:
        v11 = v6;
LABEL_77:
        WPP_SF_d(v9[1].Control.Logger, v10, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v11);
      }
LABEL_78:
      v12 = capabilityCount;
      goto $Exit_9;
    }
    goto $Exit_9;
  }
  v8 = SHGetKnownFolderPath(&FOLDERID_System, 0, 0, &systemDirectoryPath);
  if ( v8 >= 0 )
  {
    v8 = StringCchPrintfW(applicationName, 0x104u, L"\"%s\\%s\"", systemDirectoryPath, L"AuthHost.exe");
    if ( v8 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 5u )
      {
        WPP_SF_S(
          WPP_GLOBAL_Control[1].Control.Logger,
          0x51u,
          WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
          applicationName);
      }
      CurrentProcess = GetCurrentProcess();
      if ( !IsWow64Process(CurrentProcess, &isWow64) )
      {
        isWow64 = 0;
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) == 0
          || WPP_GLOBAL_Control[1].Control.Level < 2u )
        {
          goto LABEL_26;
        }
        WPP_SF_d(
          WPP_GLOBAL_Control[1].Control.Logger,
          0x52u,
          WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
          LastError);
      }
      v15 = WPP_GLOBAL_Control;
LABEL_26:
      if ( !isWow64 )
        goto LABEL_39;
      if ( v15 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (v15[1].ReserveSpace[28] & 0x10) != 0
        && v15[1].Control.Level >= 5u )
      {
        WPP_SF_(v15[1].Control.Logger, 0x53u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids);
      }
      if ( Wow64DisableWow64FsRedirection(&prevRedirect) )
      {
LABEL_39:
        AuthHostProcess = CreateAuthHostProcess(
                            applicationName,
                            commandLineArg,
                            appContainerSid,
                            capabilitySidAndAttributes,
                            capabilityCount,
                            0,
                            &processContext.processHandle);
        v8 = AuthHostProcess;
        if ( AuthHostProcess < 0
          && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
          && WPP_GLOBAL_Control[1].Control.Level >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control[1].Control.Logger,
            0x55u,
            WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
            AuthHostProcess);
        }
        if ( isWow64 && !Wow64RevertWow64FsRedirection(prevRedirect) )
        {
          v18 = GetLastError();
          v8 = v18;
          if ( v18 > 0 )
            v8 = (unsigned __int16)v18 | 0x80070000;
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
            && WPP_GLOBAL_Control[1].Control.Level >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x56u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v8);
          }
        }
        if ( v8 < 0 )
          goto LABEL_78;
        v19 = GetAuthHostRegDWORDValue(L"DisableActivateTimeout");
        if ( WaitForSingleObject(processContext.processHandle, v19 != 0 ? -1 : 15000) )
        {
          v8 = -2147023436;
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
            && WPP_GLOBAL_Control[1].Control.Level >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Control.Logger, 0x59u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids);
          }
          goto LABEL_78;
        }
        exitCode = 0;
        if ( GetExitCodeProcess(processContext.processHandle, &exitCode) )
        {
          v8 = 0;
          if ( !exitCode )
            goto LABEL_78;
          v8 = (int)exitCode > 0 ? (unsigned __int16)exitCode | 0x80070000 : exitCode;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) == 0
            || WPP_GLOBAL_Control[1].Control.Level < 2u )
          {
            goto LABEL_78;
          }
          v10 = 88;
        }
        else
        {
          v20 = GetLastError();
          v8 = v20;
          if ( v20 > 0 )
            v8 = (unsigned __int16)v20 | 0x80070000;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) == 0
            || WPP_GLOBAL_Control[1].Control.Level < 2u )
          {
            goto LABEL_78;
          }
          v10 = 87;
        }
      }
      else
      {
        v16 = GetLastError();
        v8 = v16;
        if ( v16 > 0 )
          v8 = (unsigned __int16)v16 | 0x80070000;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) == 0
          || WPP_GLOBAL_Control[1].Control.Level < 2u )
        {
          goto LABEL_78;
        }
        v10 = 84;
      }
      v11 = v8;
      goto LABEL_77;
    }
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0 )
  {
    if ( WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      v10 = 80;
      v11 = v8;
      goto LABEL_77;
    }
    goto LABEL_78;
  }
$Exit_9:
  if ( systemDirectoryPath )
    CoTaskMemFree(systemDirectoryPath);
  if ( v12 < 5 )
    v7 = v12;
  FreeAuthHostCapabilitySidAndAttributes(capabilitySidAndAttributes, v7);
  if ( appContainerSid )
    FreeSid(appContainerSid);
  ReleaseAuthHostProcess(&processContext);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180010494  mov     [rsp-8+arg_10], rbx
0x180010499  push    rbp
0x18001049a  push    rsi
0x18001049b  push    rdi
0x18001049c  push    r12
0x18001049e  push    r13
0x1800104a0  push    r14
0x1800104a2  push    r15
0x1800104a4  lea     rbp, [rsp-1F0h]
0x1800104ac  sub     rsp, 2F0h
0x1800104b3  mov     rax, cs:__security_cookie
0x1800104ba  xor     rax, rsp
0x1800104bd  mov     [rbp+220h+var_40], rax
0x1800104c4  xor     r14d, r14d
0x1800104c7  mov     r13, commandLineArg
0x1800104ca  mov     edi, brokerFlags
0x1800104cc  mov     [rsp+320h+systemDirectoryPath], r14
0x1800104d1  xorps   xmm0, xmm0
0x1800104d4  mov     [rbp+220h+capabilitySidAndAttributes.Sid], r14
0x1800104d8  xor     edx, edx; Val
0x1800104da  lea     rcx, [rbp+220h+capabilitySidAndAttributes.Attributes]; void *
0x1800104de  lea     r8d, [r14+48h]; Size
0x1800104e2  movups  xmmword ptr [rsp+320h+processContext.appContainerIndex], xmm0
0x1800104e7  call    memset_0
0x1800104ec  lea     rcx, aEnableprivaten; "EnablePrivateNetwork"
0x1800104f3  mov     [rsp+320h+capabilityCount], r14d
0x1800104f8  mov     [rsp+320h+appContainerSid], r14
0x1800104fd  call    ?GetAuthHostRegDWORDValue@@YAKPEBG@Z; GetAuthHostRegDWORDValue(ushort const *)
0x180010502  lea     r9, [rsp+320h+capabilityCount]; capabilityCount
0x180010507  mov     [rsp+320h+isWow64], r14d
0x18001050c  lea     r8, [rbp+220h+capabilitySidAndAttributes]; capabilitySidAndAttributes
0x180010510  mov     [rsp+320h+prevRedirect], r14
0x180010515  mov     edx, eax; enablePrivateNetwork
0x180010517  mov     brokerFlags, edi; brokerFlags
0x180010519  mov     esi, eax
0x18001051b  call    _InitializeAuthHostCapabilitySidAndAttributes
0x180010520  lea     r12d, [r14+5]
0x180010524  mov     ebx, eax
0x180010526  test    eax, eax
0x180010528  jns     short loc_180010568
0x18001052a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180010531  lea     rdi, WPP_GLOBAL_Control
0x180010538  cmp     rcx, rdi
0x18001053b  jz      loc_180010942
0x180010541  mov     sil, 10h
0x180010544  test    [rcx+44h], sil
0x180010548  jz      loc_180010942
0x18001054e  mov     r14b, 2
0x180010551  cmp     [rcx+41h], r14b
0x180010555  jb      loc_180010942
0x18001055b  lea     edx, [r12+49h]
0x180010560  mov     r9d, eax
0x180010563  jmp     loc_180010932
0x180010568  mov     r14d, [rsp+320h+capabilityCount]
0x18001056d  lea     rax, [rsp+320h+processContext]
0x180010572  mov     [rsp+320h+slotIndex], rax; slotIndex
0x180010577  lea     r9, [rbp+220h+capabilitySidAndAttributes]; capabilities
0x18001057b  lea     rax, [rsp+320h+appContainerSid]
0x180010580  mov     r8d, esi; enablePrivateNetwork
0x180010583  mov     [rsp+320h+var_2F8], rax; appContainerSid
0x180010588  mov     edx, 1; useSsoAppContainer
0x18001058d  mov     brokerFlags, edi; brokerFlags
0x18001058f  mov     [rsp+320h+var_300], r14d; capabilityCount
0x180010594  call    _CreateAuthHostAppContainer
0x180010599  mov     ebx, eax
0x18001059b  test    eax, eax
0x18001059d  jns     short loc_1800105D7
0x18001059f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800105a6  lea     rdi, WPP_GLOBAL_Control
0x1800105ad  cmp     rcx, rdi
0x1800105b0  jz      $Exit_9
0x1800105b6  mov     sil, 10h
0x1800105b9  test    [rcx+44h], sil
0x1800105bd  jz      $Exit_9
0x1800105c3  mov     r14b, 2
0x1800105c6  cmp     [rcx+41h], r14b
0x1800105ca  jb      loc_180010942
0x1800105d0  mov     edx, 4Fh ; 'O'
0x1800105d5  jmp     short loc_180010560
0x1800105d7  lea     r9, [rsp+320h+systemDirectoryPath]; ppszPath
0x1800105dc  xor     r8d, r8d; hToken
0x1800105df  xor     edx, edx; dwFlags
0x1800105e1  lea     rcx, FOLDERID_System; rfid
0x1800105e8  call    cs:__imp_SHGetKnownFolderPath
0x1800105ee  mov     ebx, eax
0x1800105f0  test    eax, eax
0x1800105f2  js      loc_180010905
0x1800105f8  mov     r9, [rsp+320h+systemDirectoryPath]
0x1800105fd  lea     rax, aAuthhostExe; "AuthHost.exe"
0x180010604  lea     r8, aSS; "\"%s\\%s\""
0x18001060b  mov     qword ptr [rsp+320h+var_300], rax
0x180010610  mov     edx, 104h; cchDest
0x180010615  lea     rcx, [rbp+220h+applicationName]; pszDest
0x180010619  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001061e  mov     ebx, eax
0x180010620  test    eax, eax
0x180010622  js      loc_180010905
0x180010628  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001062f  lea     rdi, WPP_GLOBAL_Control
0x180010636  lea     r15, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids
0x18001063d  mov     sil, 10h
0x180010640  cmp     rcx, rdi
0x180010643  jz      short loc_180010666
0x180010645  test    [rcx+44h], sil
0x180010649  jz      short loc_180010666
0x18001064b  cmp     [rcx+41h], r12b
0x18001064f  jb      short loc_180010666
0x180010651  mov     rcx, [rcx+38h]; Logger
0x180010655  lea     r9, [rbp+220h+applicationName]; _a1
0x180010659  mov     edx, 51h ; 'Q'; id
0x18001065e  mov     r8, r15; TraceGuid
0x180010661  call    WPP_SF_S
0x180010666  call    cs:__imp_GetCurrentProcess
0x18001066c  mov     rcx, rax; hProcess
0x18001066f  lea     commandLineArg, [rsp+320h+isWow64]; Wow64Process
0x180010674  call    cs:__imp_IsWow64Process
0x18001067a  xor     ebx, ebx
0x18001067c  mov     r14b, 2
0x18001067f  test    eax, eax
0x180010681  jnz     short loc_1800106C5
0x180010683  mov     [rsp+320h+isWow64], ebx
0x180010687  call    cs:__imp_GetLastError
0x18001068d  test    eax, eax
0x18001068f  jle     short loc_180010699
0x180010691  movzx   eax, ax
0x180010694  or      eax, 80070000h
0x180010699  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800106a0  cmp     rcx, rdi
0x1800106a3  jz      short loc_1800106CC
0x1800106a5  test    [rcx+44h], sil
0x1800106a9  jz      short loc_1800106CC
0x1800106ab  cmp     [rcx+41h], r14b
0x1800106af  jb      short loc_1800106CC
0x1800106b1  mov     rcx, [rcx+38h]; Logger
0x1800106b5  mov     edx, 52h ; 'R'; id
0x1800106ba  mov     r9d, eax; _a1
0x1800106bd  mov     r8, r15; TraceGuid
0x1800106c0  call    WPP_SF_d
0x1800106c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106cc  cmp     [rsp+320h+isWow64], ebx
0x1800106d0  jz      short loc_18001074C
0x1800106d2  cmp     rcx, rdi; __annotation("TMF:",
0x1800106d5  jz      short loc_1800106F4
0x1800106d7  test    [rcx+44h], sil
0x1800106db  jz      short loc_1800106F4
0x1800106dd  cmp     [rcx+41h], r12b
0x1800106e1  jb      short loc_1800106F4
0x1800106e3  mov     rcx, [rcx+38h]; Logger
0x1800106e7  mov     edx, 53h ; 'S'; id
0x1800106ec  mov     r8, r15; TraceGuid
0x1800106ef  call    WPP_SF_
0x1800106f4  lea     rcx, [rsp+320h+prevRedirect]; OldValue
0x1800106f9  call    cs:__imp_Wow64DisableWow64FsRedirection
0x1800106ff  test    eax, eax
0x180010701  jnz     short loc_18001074C
0x180010703  call    cs:__imp_GetLastError
0x180010709  mov     ebx, eax
0x18001070b  test    eax, eax
0x18001070d  jle     short loc_180010718
0x18001070f  movzx   ebx, ax
0x180010712  or      ebx, 80070000h
0x180010718  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001071f  cmp     rcx, rdi
0x180010722  jz      loc_180010942
0x180010728  test    [rcx+44h], sil
0x18001072c  jz      loc_180010942
0x180010732  cmp     [rcx+41h], r14b
0x180010736  jb      loc_180010942
0x18001073c  mov     edx, 54h ; 'T'
0x180010741  mov     r9d, ebx
0x180010744  mov     r8, r15
0x180010747  jmp     loc_180010939
0x18001074c  mov     r8, [rsp+320h+appContainerSid]; appContainerSid
0x180010751  lea     rax, [rsp+320h+processContext.processHandle]
0x180010756  mov     [rsp+320h+slotIndex], rax; processHandle
0x18001075b  lea     r9, [rbp+220h+capabilitySidAndAttributes]; capabilities
0x18001075f  mov     eax, [rsp+320h+capabilityCount]
0x180010763  lea     rcx, [rbp+220h+applicationName]; applicationName
0x180010767  mov     dword ptr [rsp+320h+var_2F8], ebx; clientProcessId
0x18001076b  mov     commandLineArg, r13; commandLineArg
0x18001076e  mov     [rsp+320h+var_300], eax; capabilityCount
0x180010772  call    _CreateAuthHostProcess
0x180010777  mov     ebx, eax
0x180010779  test    eax, eax
0x18001077b  jns     short loc_1800107A9
0x18001077d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180010784  cmp     rcx, rdi
0x180010787  jz      short loc_1800107A9
0x180010789  test    [rcx+44h], sil
0x18001078d  jz      short loc_1800107A9
0x18001078f  cmp     [rcx+41h], r14b
0x180010793  jb      short loc_1800107A9
0x180010795  mov     rcx, [rcx+38h]; Logger
0x180010799  mov     edx, 55h ; 'U'; id
0x18001079e  mov     r9d, eax; _a1
0x1800107a1  mov     r8, r15; TraceGuid
0x1800107a4  call    WPP_SF_d
0x1800107a9  cmp     [rsp+320h+isWow64], 0
0x1800107ae  jz      short loc_180010800
0x1800107b0  mov     rcx, [rsp+320h+prevRedirect]; OlValue
0x1800107b5  call    cs:__imp_Wow64RevertWow64FsRedirection
0x1800107bb  test    eax, eax
0x1800107bd  jnz     short loc_180010800
0x1800107bf  call    cs:__imp_GetLastError
0x1800107c5  mov     ebx, eax
0x1800107c7  test    eax, eax
0x1800107c9  jle     short loc_1800107D4
0x1800107cb  movzx   ebx, ax
0x1800107ce  or      ebx, 80070000h
0x1800107d4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800107db  cmp     rcx, rdi
0x1800107de  jz      short loc_180010800
0x1800107e0  test    [rcx+44h], sil
0x1800107e4  jz      short loc_180010800
0x1800107e6  cmp     [rcx+41h], r14b
0x1800107ea  jb      short loc_180010800
0x1800107ec  mov     rcx, [rcx+38h]; Logger
0x1800107f0  mov     edx, 56h ; 'V'; id
0x1800107f5  mov     r9d, ebx; _a1
0x1800107f8  mov     r8, r15; TraceGuid
0x1800107fb  call    WPP_SF_d
0x180010800  test    ebx, ebx
0x180010802  js      loc_180010942
0x180010808  lea     rcx, aDisableactivat; "DisableActivateTimeout"
0x18001080f  call    ?GetAuthHostRegDWORDValue@@YAKPEBG@Z; GetAuthHostRegDWORDValue(ushort const *)
0x180010814  mov     rcx, [rsp+320h+processContext.processHandle]; hHandle
0x180010819  neg     eax
0x18001081b  sbb     edx, edx
0x18001081d  and     edx, 0FFFFC567h
0x180010823  add     edx, 3A98h; dwMilliseconds
0x180010829  call    cs:__imp_WaitForSingleObject
0x18001082f  test    eax, eax
0x180010831  jnz     loc_1800108D5
0x180010837  mov     rcx, [rsp+320h+processContext.processHandle]; hProcess
0x18001083c  lea     commandLineArg, [rsp+320h+exitCode]; lpExitCode
0x180010841  mov     [rsp+320h+exitCode], eax
0x180010845  call    cs:__imp_GetExitCodeProcess
0x18001084b  test    eax, eax
0x18001084d  jnz     short loc_180010892
0x18001084f  call    cs:__imp_GetLastError
0x180010855  mov     ebx, eax
0x180010857  test    eax, eax
0x180010859  jle     short loc_180010864
0x18001085b  movzx   ebx, ax
0x18001085e  or      ebx, 80070000h
0x180010864  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001086b  cmp     rcx, rdi
0x18001086e  jz      loc_180010942
0x180010874  test    [rcx+44h], sil
0x180010878  jz      loc_180010942
0x18001087e  cmp     [rcx+41h], r14b
0x180010882  jb      loc_180010942
0x180010888  mov     edx, 57h ; 'W'
0x18001088d  jmp     loc_180010741
0x180010892  mov     eax, [rsp+320h+exitCode]
0x180010896  xor     ebx, ebx
0x180010898  test    eax, eax
0x18001089a  jz      loc_180010942
0x1800108a0  jg      short loc_1800108A6
0x1800108a2  mov     ebx, eax
0x1800108a4  jmp     short loc_1800108AF
0x1800108a6  movzx   ebx, ax
0x1800108a9  or      ebx, 80070000h
0x1800108af  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800108b6  cmp     rcx, rdi
0x1800108b9  jz      loc_180010942
0x1800108bf  test    [rcx+44h], sil
0x1800108c3  jz      short loc_180010942
0x1800108c5  cmp     [rcx+41h], r14b
0x1800108c9  jb      short loc_180010942
0x1800108cb  mov     edx, 58h ; 'X'
0x1800108d0  jmp     loc_180010741
0x1800108d5  mov     ebx, 800705B4h
0x1800108da  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800108e1  cmp     rcx, rdi
0x1800108e4  jz      short loc_180010942
0x1800108e6  test    [rcx+44h], sil
0x1800108ea  jz      short loc_180010942
0x1800108ec  cmp     [rcx+41h], r14b
0x1800108f0  jb      short loc_180010942
0x1800108f2  mov     rcx, [rcx+38h]; Logger
0x1800108f6  mov     edx, 59h ; 'Y'; id
0x1800108fb  mov     r8, r15; TraceGuid
0x1800108fe  call    WPP_SF_
0x180010903  jmp     short loc_180010942
0x180010905  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001090c  lea     rdi, WPP_GLOBAL_Control
0x180010913  cmp     rcx, rdi
0x180010916  jz      short $Exit_9
0x180010918  mov     sil, 10h
0x18001091b  test    [rcx+44h], sil
0x18001091f  jz      short $Exit_9
0x180010921  mov     r14b, 2
0x180010924  cmp     [rcx+41h], r14b
0x180010928  jb      short loc_180010942
0x18001092a  mov     edx, 50h ; 'P'; id
0x18001092f  mov     r9d, ebx; _a1
0x180010932  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180010939  mov     rcx, [rcx+38h]; Logger
0x18001093d  call    WPP_SF_d
  ... truncated ...
```
