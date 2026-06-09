# CDiskProtection::SetMode(__MIDL___MIDL_itf_wmssvc_0000_0000_0019)

- ea: `0x14000b980`
- end: `0x14000be2b`
- name: `?SetMode@CDiskProtection@@UEAAJW4__MIDL___MIDL_itf_wmssvc_0000_0000_0019@@@Z`
- size: `1195`
- prototype: `__int64 __fastcall(CDiskProtection *, unsigned int)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x14000b980`
- `0x14000be34`
- `0x140010538`
- `0x140010808`
- `0x140012788`
- `0x140014b54`
- `0x140031424`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x140060820`
- `0x140060de8`
- `0x140068b1c`
- `0x14006c590`
- `0x14006cafc`
- `0x14006cb40`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x14000bc69`
- `ADVAPI32!EventWrite` at `0x14000bd48`
- `ADVAPI32!EventWrite` at `0x14000bc69`
- `ADVAPI32!EventWrite` at `0x14000bd48`
- `KERNEL32!GetWindowsDirectoryW` at `0x14000baa6`
- `KERNEL32!GetWindowsDirectoryW` at `0x14000baa6`
- `KERNEL32!GetLastError` at `0x14000bab0`
- `KERNEL32!GetLastError` at `0x14000bab0`
- `KERNEL32!IsDebuggerPresent` at `0x14000ba61`
- `KERNEL32!IsDebuggerPresent` at `0x14000bbad`
- `KERNEL32!IsDebuggerPresent` at `0x14000bca3`
- `KERNEL32!IsDebuggerPresent` at `0x14000bd84`
- `KERNEL32!IsDebuggerPresent` at `0x14000ba61`
- `KERNEL32!IsDebuggerPresent` at `0x14000bbad`
- `KERNEL32!IsDebuggerPresent` at `0x14000bca3`
- `KERNEL32!IsDebuggerPresent` at `0x14000bd84`
- `OLEAUT32!__imp_VariantInit` at `0x14000b9ff`
- `OLEAUT32!__imp_VariantInit` at `0x14000b9ff`
- `OLEAUT32!__imp_VariantClear` at `0x14000bdef`
- `OLEAUT32!__imp_VariantClear` at `0x14000bdef`

## pseudocode

```c
__int64 __fastcall CDiskProtection::SetMode(CDiskProtection *a1, unsigned int a2)
{
  int DoesVolumeContainPageFileAndCrashDump; // ebx
  const unsigned __int16 *v5; // r15
  const unsigned __int16 *v6; // r12
  unsigned int v7; // r14d
  signed int LastError; // eax
  CSoftwareUpdates *v9; // rcx
  const unsigned __int16 *v10; // r9
  const unsigned __int16 *v11; // r9
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v15[328]; // [rsp+60h] [rbp-A0h] BYREF
  int v16; // [rsp+1A8h] [rbp+A8h]
  WCHAR Buffer[264]; // [rsp+1C0h] [rbp+C0h] BYREF

  v13 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset_0(Buffer, 0, 0x208u);
  CSetDisablePasswordChangeHostThread::CSetDisablePasswordChangeHostThread((CSetDisablePasswordChangeHostThread *)v15);
  DoesVolumeContainPageFileAndCrashDump = CUserManagement::s_VerifyAccessLevelEx(3u, 0);
  if ( DoesVolumeContainPageFileAndCrashDump >= 0 )
  {
    VariantInit(&pvarg);
    DEBUGMSG(L"CDiskProtection::SetMode - dpm = %d\n", a2);
    if ( a2 )
    {
      if ( a2 != 1 )
      {
        DoesVolumeContainPageFileAndCrashDump = -2147024809;
        v5 = L"((HRESULT)0x80070057L)";
        v6 = L"CHRA";
        v7 = 971;
LABEL_5:
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          v7,
          L"CDiskProtection::SetMode",
          v6,
          v5,
          DoesVolumeContainPageFileAndCrashDump);
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
            v7,
            L"CDiskProtection::SetMode",
            v6,
            v5,
            DoesVolumeContainPageFileAndCrashDump);
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
            v7,
            L"CDiskProtection::SetMode",
            v6,
            v5,
            DoesVolumeContainPageFileAndCrashDump);
        goto LABEL_38;
      }
      if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
      {
        LastError = GetLastError();
        DoesVolumeContainPageFileAndCrashDump = LastError;
        if ( LastError > 0 )
          DoesVolumeContainPageFileAndCrashDump = (unsigned __int16)LastError | 0x80070000;
        v5 = L"fSuccess";
        v6 = L"CBRAEx";
        if ( DoesVolumeContainPageFileAndCrashDump >= 0 )
          DoesVolumeContainPageFileAndCrashDump = -2147467259;
        v7 = 933;
        goto LABEL_5;
      }
      DoesVolumeContainPageFileAndCrashDump = CDiskProtection::s_DoesVolumeContainPageFileAndCrashDump(
                                                Buffer[0],
                                                1,
                                                &v13);
      if ( DoesVolumeContainPageFileAndCrashDump >= 0 )
      {
        if ( v13 )
        {
          DoesVolumeContainPageFileAndCrashDump = -2147467259;
          DEBUGMSGLEVEL(
            4u,
            L"%s(%d) - %s - Test failed:  %s\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
            939,
            L"CDiskProtection::SetMode",
            L"System volume contains page file or crash dumps");
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
            0x3ABu,
            L"CDiskProtection::SetMode",
            L"CBRLA",
            L"!fContainsPageFileOrCrashDump",
            -2147467259);
          if ( IsDebuggerPresent() )
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              939,
              L"CDiskProtection::SetMode",
              L"CBRLA",
              L"!fContainsPageFileOrCrashDump",
              -2147467259);
          else
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              939,
              L"CDiskProtection::SetMode",
              L"CBRLA",
              L"!fContainsPageFileOrCrashDump",
              -2147467259);
        }
        else
        {
          DoesVolumeContainPageFileAndCrashDump = CSoftwareUpdates::SetWindowsUpdateNoAutoUpdateSetting(v9, 1u);
          if ( DoesVolumeContainPageFileAndCrashDump >= 0 )
          {
            DoesVolumeContainPageFileAndCrashDump = CDiskProtection::s_ModifyBootStatusPolicy();
            if ( DoesVolumeContainPageFileAndCrashDump >= 0 )
            {
              DoesVolumeContainPageFileAndCrashDump = CDiskProtection::s_EnableDefragTask(0);
              if ( DoesVolumeContainPageFileAndCrashDump >= 0 )
              {
                DoesVolumeContainPageFileAndCrashDump = SetDisablePasswordChange(1u);
                if ( DoesVolumeContainPageFileAndCrashDump >= 0 )
                {
                  v16 = 1;
                  DoesVolumeContainPageFileAndCrashDump = CWorkerThread::Start((CWorkerThread *)v15);
                  if ( DoesVolumeContainPageFileAndCrashDump >= 0 )
                  {
                    DoesVolumeContainPageFileAndCrashDump = CDiskProtection::SetModeInternal(a1, 1u);
                    if ( DoesVolumeContainPageFileAndCrashDump >= 0 )
                    {
                      if ( EventWrite(g_hEventProviderHandle, &WmsSvc_DiskProtectionEnabled, 0, 0) )
                      {
                        LOGASSERT(
                          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                          0x3C2u,
                          L"CDiskProtection::SetMode",
                          v10,
                          L"err == ERROR_SUCCESS");
                        if ( IsDebuggerPresent() )
                          DEBUGMSGLEVEL(
                            2u,
                            L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
                            L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                            962,
                            L"CDiskProtection::SetMode",
                            L"ASSERT",
                            L"err == ERROR_SUCCESS");
                        else
                          DEBUGMSGBOX(
                            L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
                            L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                            962,
                            L"CDiskProtection::SetMode",
                            L"ASSERT",
                            L"err == ERROR_SUCCESS");
                      }
                      DoesVolumeContainPageFileAndCrashDump = CWorkerThread::WaitForThreadToStop((CWorkerThread *)v15);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      DoesVolumeContainPageFileAndCrashDump = CDiskProtection::s_SetFirstBootAfterSwitchingFromActiveToPassive(1);
      if ( DoesVolumeContainPageFileAndCrashDump >= 0 )
      {
        DoesVolumeContainPageFileAndCrashDump = CDiskProtection::SetModeInternal(a1, 0);
        if ( DoesVolumeContainPageFileAndCrashDump >= 0 )
        {
          if ( EventWrite(g_hEventProviderHandle, &WmsSvc_DiskProtectionDisabled, 0, 0) )
          {
            LOGASSERT(
              L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
              0x39Du,
              L"CDiskProtection::SetMode",
              v11,
              L"err == ERROR_SUCCESS");
            if ( IsDebuggerPresent() )
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                925,
                L"CDiskProtection::SetMode",
                L"ASSERT",
                L"err == ERROR_SUCCESS");
            else
              DEBUGMSGBOX(
                L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                925,
                L"CDiskProtection::SetMode",
                L"ASSERT",
                L"err == ERROR_SUCCESS");
          }
        }
      }
    }
  }
LABEL_38:
  DEBUGMSG(L"CDiskProtection::SetMode - Exiting, hr = 0x%08X\n", (unsigned int)DoesVolumeContainPageFileAndCrashDump);
  VariantClear(&pvarg);
  CSetDisablePasswordChangeHostThread::~CSetDisablePasswordChangeHostThread((CSetDisablePasswordChangeHostThread *)v15);
  return (unsigned int)DoesVolumeContainPageFileAndCrashDump;
}

```

## disassembly

```asm
0x14000b980  mov     [rsp-8+arg_10], rbx
0x14000b985  push    rbp
0x14000b986  push    rsi
0x14000b987  push    rdi
0x14000b988  push    r12
0x14000b98a  push    r13
0x14000b98c  push    r14
0x14000b98e  push    r15
0x14000b990  lea     rbp, [rsp-2E0h]
0x14000b998  sub     rsp, 3E0h
0x14000b99f  mov     rax, cs:__security_cookie
0x14000b9a6  xor     rax, rsp
0x14000b9a9  mov     [rbp+310h+var_40], rax
0x14000b9b0  xor     eax, eax
0x14000b9b2  mov     edi, edx
0x14000b9b4  mov     rsi, rcx
0x14000b9b7  mov     qword ptr [rsp+410h+pvarg+10h], rax
0x14000b9bc  xorps   xmm0, xmm0
0x14000b9bf  mov     [rsp+410h+var_3D0], eax
0x14000b9c3  xor     edx, edx; Val
0x14000b9c5  lea     rcx, [rbp+310h+Buffer]; void *
0x14000b9cc  mov     r8d, 208h; Size
0x14000b9d2  movups  xmmword ptr [rsp+410h+pvarg], xmm0
0x14000b9d7  call    memset_0
0x14000b9dc  lea     rcx, [rsp+410h+var_3B0]; this
0x14000b9e1  call    ??0CSetDisablePasswordChangeHostThread@@QEAA@XZ; CSetDisablePasswordChangeHostThread::CSetDisablePasswordChangeHostThread(void)
0x14000b9e6  xor     edx, edx
0x14000b9e8  lea     ecx, [rdx+3]
0x14000b9eb  call    ?s_VerifyAccessLevelEx@CUserManagement@@SAJW4EUserAccessLevel@@H@Z; CUserManagement::s_VerifyAccessLevelEx(EUserAccessLevel,int)
0x14000b9f0  mov     ebx, eax
0x14000b9f2  test    eax, eax
0x14000b9f4  js      loc_14000BDDC
0x14000b9fa  lea     rcx, [rsp+410h+pvarg]; pvarg
0x14000b9ff  call    cs:__imp_VariantInit
0x14000ba05  mov     edx, edi
0x14000ba07  lea     rcx, aCdiskprotectio_65; "CDiskProtection::SetMode - dpm = %d\n"
0x14000ba0e  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000ba13  test    edi, edi
0x14000ba15  jz      loc_14000BD0C
0x14000ba1b  cmp     edi, 1
0x14000ba1e  jz      short loc_14000BA9A
0x14000ba20  mov     ebx, 80070057h
0x14000ba25  lea     r15, aHresult0x80070; "((HRESULT)0x80070057L)"
0x14000ba2c  lea     r12, aChra; "CHRA"
0x14000ba33  mov     r14d, 3CBh
0x14000ba39  lea     rsi, aCdiskprotectio_146; "CDiskProtection::SetMode"
0x14000ba40  mov     [rsp+410h+var_3E8], ebx; int
0x14000ba44  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000ba4b  mov     [rsp+410h+var_3F0], r15; unsigned __int16 *
0x14000ba50  mov     r8, rsi; unsigned __int16 *
0x14000ba53  mov     rcx, rdi; unsigned __int16 *
0x14000ba56  mov     r9, r12; unsigned __int16 *
0x14000ba59  mov     edx, r14d; unsigned int
0x14000ba5c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000ba61  call    cs:__imp_IsDebuggerPresent
0x14000ba67  test    eax, eax
0x14000ba69  jz      short loc_14000BAEA
0x14000ba6b  mov     [rsp+410h+var_3D8], ebx
0x14000ba6f  mov     r9d, r14d
0x14000ba72  mov     [rsp+410h+var_3E0], r15
0x14000ba77  mov     qword ptr [rsp+410h+var_3E8], r12
0x14000ba7c  mov     r8, rdi
0x14000ba7f  mov     [rsp+410h+var_3F0], rsi
0x14000ba84  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000ba8b  mov     ecx, 2; unsigned __int8
0x14000ba90  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000ba95  jmp     loc_14000BDDC
0x14000ba9a  mov     edx, 104h; uSize
0x14000ba9f  lea     rcx, [rbp+310h+Buffer]; lpBuffer
0x14000baa6  call    cs:__imp_GetWindowsDirectoryW
0x14000baac  test    eax, eax
0x14000baae  jnz     short loc_14000BB12
0x14000bab0  call    cs:__imp_GetLastError
0x14000bab6  mov     ebx, eax
0x14000bab8  test    eax, eax
0x14000baba  jle     short loc_14000BAC5
0x14000babc  movzx   ebx, ax
0x14000babf  or      ebx, 80070000h
0x14000bac5  mov     r14d, 80004005h
0x14000bacb  lea     r15, aFsuccess; "fSuccess"
0x14000bad2  test    ebx, ebx
0x14000bad4  lea     r12, aCbraex; "CBRAEx"
0x14000badb  cmovns  ebx, r14d
0x14000badf  mov     r14d, 3A5h
0x14000bae5  jmp     loc_14000BA39
0x14000baea  mov     dword ptr [rsp+410h+var_3E0], ebx
0x14000baee  mov     r8d, r14d
0x14000baf1  mov     qword ptr [rsp+410h+var_3E8], r15
0x14000baf6  mov     [rsp+410h+var_3F0], r12
0x14000bafb  mov     r9, rsi
0x14000bafe  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000bb05  mov     rdx, rdi
0x14000bb08  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000bb0d  jmp     loc_14000BDDC
0x14000bb12  movzx   ecx, [rbp+310h+Buffer]
0x14000bb19  lea     r8, [rsp+410h+var_3D0]
0x14000bb1e  mov     edi, 1
0x14000bb23  mov     edx, edi
0x14000bb25  call    ?s_DoesVolumeContainPageFileAndCrashDump@CDiskProtection@@KAJGW4EDiskProtectionConstraint@1@PEAH@Z; CDiskProtection::s_DoesVolumeContainPageFileAndCrashDump(ushort,CDiskProtection::EDiskProtectionConstraint,int *)
0x14000bb2a  mov     ebx, eax
0x14000bb2c  test    eax, eax
0x14000bb2e  js      loc_14000BDDC
0x14000bb34  cmp     [rsp+410h+var_3D0], 0
0x14000bb39  jz      loc_14000BBE5
0x14000bb3f  lea     rax, aSystemVolumeCo; "System volume contains page file or cra"...
0x14000bb46  mov     r15d, 3ABh
0x14000bb4c  mov     qword ptr [rsp+410h+var_3E8], rax
0x14000bb51  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000bb58  mov     r14d, 80004005h
0x14000bb5e  lea     rsi, aCdiskprotectio_146; "CDiskProtection::SetMode"
0x14000bb65  mov     r9d, r15d
0x14000bb68  mov     [rsp+410h+var_3F0], rsi
0x14000bb6d  mov     r8, rdi
0x14000bb70  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x14000bb77  mov     ecx, 4; unsigned __int8
0x14000bb7c  mov     ebx, r14d
0x14000bb7f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000bb84  lea     r13, aCbrla; "CBRLA"
0x14000bb8b  mov     [rsp+410h+var_3E8], r14d; int
0x14000bb90  lea     r12, aFcontainspagef; "!fContainsPageFileOrCrashDump"
0x14000bb97  mov     r9, r13; unsigned __int16 *
0x14000bb9a  mov     r8, rsi; unsigned __int16 *
0x14000bb9d  mov     [rsp+410h+var_3F0], r12; unsigned __int16 *
0x14000bba2  mov     edx, r15d; unsigned int
0x14000bba5  mov     rcx, rdi; unsigned __int16 *
0x14000bba8  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000bbad  call    cs:__imp_IsDebuggerPresent
0x14000bbb3  test    eax, eax
0x14000bbb5  jz      short loc_14000BBCE
0x14000bbb7  mov     [rsp+410h+var_3D8], r14d
0x14000bbbc  mov     r9d, r15d
0x14000bbbf  mov     [rsp+410h+var_3E0], r12
0x14000bbc4  mov     qword ptr [rsp+410h+var_3E8], r13
0x14000bbc9  jmp     loc_14000BA7C
0x14000bbce  mov     dword ptr [rsp+410h+var_3E0], r14d
0x14000bbd3  mov     r8d, r15d
0x14000bbd6  mov     qword ptr [rsp+410h+var_3E8], r12
0x14000bbdb  mov     [rsp+410h+var_3F0], r13
0x14000bbe0  jmp     loc_14000BAFB
0x14000bbe5  mov     edx, edi; unsigned int
0x14000bbe7  call    ?SetWindowsUpdateNoAutoUpdateSetting@CSoftwareUpdates@@AEAAJK@Z; CSoftwareUpdates::SetWindowsUpdateNoAutoUpdateSetting(ulong)
0x14000bbec  mov     ebx, eax
0x14000bbee  test    eax, eax
0x14000bbf0  js      loc_14000BDDC
0x14000bbf6  call    ?s_ModifyBootStatusPolicy@CDiskProtection@@KAJXZ; CDiskProtection::s_ModifyBootStatusPolicy(void)
0x14000bbfb  mov     ebx, eax
0x14000bbfd  test    eax, eax
0x14000bbff  js      loc_14000BDDC
0x14000bc05  xor     ecx, ecx; int
0x14000bc07  call    ?s_EnableDefragTask@CDiskProtection@@KAJH@Z; CDiskProtection::s_EnableDefragTask(int)
0x14000bc0c  mov     ebx, eax
0x14000bc0e  test    eax, eax
0x14000bc10  js      loc_14000BDDC
0x14000bc16  mov     ecx, edi; unsigned int
0x14000bc18  call    ?SetDisablePasswordChange@@YAJK@Z; SetDisablePasswordChange(ulong)
0x14000bc1d  mov     ebx, eax
0x14000bc1f  test    eax, eax
0x14000bc21  js      loc_14000BDDC
0x14000bc27  lea     rcx, [rsp+410h+var_3B0]; this
0x14000bc2c  mov     [rbp+310h+var_268], edi
0x14000bc32  call    ?Start@CWorkerThread@@UEAAJXZ; CWorkerThread::Start(void)
0x14000bc37  mov     ebx, eax
0x14000bc39  test    eax, eax
0x14000bc3b  js      loc_14000BDDC
0x14000bc41  mov     edx, edi
0x14000bc43  mov     rcx, rsi
0x14000bc46  call    ?SetModeInternal@CDiskProtection@@QEAAJW4__MIDL___MIDL_itf_wmssvc_0000_0000_0019@@@Z; CDiskProtection::SetModeInternal(__MIDL___MIDL_itf_wmssvc_0000_0000_0019)
0x14000bc4b  mov     ebx, eax
0x14000bc4d  test    eax, eax
0x14000bc4f  js      loc_14000BDDC
0x14000bc55  mov     rcx, cs:?g_hEventProviderHandle@@3_KA; RegHandle
0x14000bc5c  lea     rdx, WmsSvc_DiskProtectionEnabled; EventDescriptor
0x14000bc63  xor     r9d, r9d; UserData
0x14000bc66  xor     r8d, r8d; UserDataCount
0x14000bc69  call    cs:__imp_EventWrite
0x14000bc6f  test    eax, eax
0x14000bc71  jz      loc_14000BCFB
0x14000bc77  lea     rsi, aCdiskprotectio_146; "CDiskProtection::SetMode"
0x14000bc7e  mov     ebx, 3C2h
0x14000bc83  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000bc8a  mov     r8, rsi; unsigned __int16 *
0x14000bc8d  lea     r14, aErrErrorSucces; "err == ERROR_SUCCESS"
0x14000bc94  mov     edx, ebx; unsigned int
0x14000bc96  mov     rcx, rdi; unsigned __int16 *
0x14000bc99  mov     [rsp+410h+var_3F0], r14; unsigned __int16 *
0x14000bc9e  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x14000bca3  call    cs:__imp_IsDebuggerPresent
0x14000bca9  test    eax, eax
0x14000bcab  lea     rax, aAssert; "ASSERT"
0x14000bcb2  jz      short loc_14000BCDC
0x14000bcb4  mov     [rsp+410h+var_3E0], r14
0x14000bcb9  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000bcc0  mov     qword ptr [rsp+410h+var_3E8], rax
0x14000bcc5  mov     r9d, ebx
0x14000bcc8  mov     r8, rdi
0x14000bccb  mov     [rsp+410h+var_3F0], rsi
0x14000bcd0  mov     ecx, 2; unsigned __int8
0x14000bcd5  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000bcda  jmp     short loc_14000BCFB
0x14000bcdc  mov     qword ptr [rsp+410h+var_3E8], r14
0x14000bce1  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000bce8  mov     r9, rsi
0x14000bceb  mov     [rsp+410h+var_3F0], rax
0x14000bcf0  mov     r8d, ebx
0x14000bcf3  mov     rdx, rdi
0x14000bcf6  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000bcfb  lea     rcx, [rsp+410h+var_3B0]; this
0x14000bd00  call    ?WaitForThreadToStop@CWorkerThread@@QEAAJXZ; CWorkerThread::WaitForThreadToStop(void)
0x14000bd05  mov     ebx, eax
0x14000bd07  jmp     loc_14000BDDC
0x14000bd0c  mov     ecx, 1; int
0x14000bd11  call    ?s_SetFirstBootAfterSwitchingFromActiveToPassive@CDiskProtection@@KAJH@Z; CDiskProtection::s_SetFirstBootAfterSwitchingFromActiveToPassive(int)
0x14000bd16  mov     ebx, eax
0x14000bd18  test    eax, eax
0x14000bd1a  js      loc_14000BDDC
0x14000bd20  xor     edx, edx
0x14000bd22  mov     rcx, rsi
0x14000bd25  call    ?SetModeInternal@CDiskProtection@@QEAAJW4__MIDL___MIDL_itf_wmssvc_0000_0000_0019@@@Z; CDiskProtection::SetModeInternal(__MIDL___MIDL_itf_wmssvc_0000_0000_0019)
0x14000bd2a  mov     ebx, eax
0x14000bd2c  test    eax, eax
0x14000bd2e  js      loc_14000BDDC
0x14000bd34  mov     rcx, cs:?g_hEventProviderHandle@@3_KA; RegHandle
0x14000bd3b  lea     rdx, WmsSvc_DiskProtectionDisabled; EventDescriptor
0x14000bd42  xor     r9d, r9d; UserData
0x14000bd45  xor     r8d, r8d; UserDataCount
0x14000bd48  call    cs:__imp_EventWrite
0x14000bd4e  test    eax, eax
0x14000bd50  jz      loc_14000BDDC
0x14000bd56  lea     rsi, aCdiskprotectio_146; "CDiskProtection::SetMode"
0x14000bd5d  mov     r15d, 39Dh
0x14000bd63  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000bd6a  mov     r8, rsi; unsigned __int16 *
0x14000bd6d  lea     r14, aErrErrorSucces; "err == ERROR_SUCCESS"
0x14000bd74  mov     edx, r15d; unsigned int
0x14000bd77  mov     rcx, rdi; unsigned __int16 *
0x14000bd7a  mov     [rsp+410h+var_3F0], r14; unsigned __int16 *
0x14000bd7f  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x14000bd84  call    cs:__imp_IsDebuggerPresent
0x14000bd8a  test    eax, eax
0x14000bd8c  lea     rax, aAssert; "ASSERT"
0x14000bd93  jz      short loc_14000BDBD
0x14000bd95  mov     [rsp+410h+var_3E0], r14
0x14000bd9a  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000bda1  mov     qword ptr [rsp+410h+var_3E8], rax
0x14000bda6  mov     r9d, r15d
0x14000bda9  mov     r8, rdi
0x14000bdac  mov     [rsp+410h+var_3F0], rsi
0x14000bdb1  mov     ecx, 2; unsigned __int8
0x14000bdb6  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000bdbb  jmp     short loc_14000BDDC
0x14000bdbd  mov     qword ptr [rsp+410h+var_3E8], r14
0x14000bdc2  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000bdc9  mov     r9, rsi
0x14000bdcc  mov     [rsp+410h+var_3F0], rax
0x14000bdd1  mov     r8d, r15d
0x14000bdd4  mov     rdx, rdi
0x14000bdd7  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000bddc  mov     edx, ebx
0x14000bdde  lea     rcx, aCdiskprotectio_162; "CDiskProtection::SetMode - Exiting, hr "...
0x14000bde5  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000bdea  lea     rcx, [rsp+410h+pvarg]; pvarg
0x14000bdef  call    cs:__imp_VariantClear
0x14000bdf5  lea     rcx, [rsp+410h+var_3B0]; this
0x14000bdfa  call    ??1CSetDisablePasswordChangeHostThread@@UEAA@XZ; CSetDisablePasswordChangeHostThread::~CSetDisablePasswordChangeHostThread(void)
0x14000bdff  mov     eax, ebx
0x14000be01  mov     rcx, [rbp+310h+var_40]
0x14000be08  xor     rcx, rsp; StackCookie
0x14000be0b  call    __security_check_cookie
0x14000be10  mov     rbx, [rsp+410h+arg_10]
0x14000be18  add     rsp, 3E0h
0x14000be1f  pop     r15
0x14000be21  pop     r14
0x14000be23  pop     r13
0x14000be25  pop     r12
0x14000be27  pop     rdi
0x14000be28  pop     rsi
0x14000be29  pop     rbp
0x14000be2a  retn
```
