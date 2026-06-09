# CDiskProtection::Install(void)

- ea: `0x140009af0`
- end: `0x140009e70`
- name: `?Install@CDiskProtection@@UEAAJXZ`
- size: `896`
- prototype: `__int64 __fastcall(CDiskProtection *__hidden this)`
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1400087b0`
- `0x14000944c`
- `0x140009af0`
- `0x140010080`
- `0x140010808`
- `0x140010d60`
- `0x140012788`
- `0x140012eb4`
- `0x140013660`
- `0x140013794`
- `0x140014188`
- `0x140015874`
- `0x140029c8c`
- `0x14002f8e0`
- `0x140030474`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14006c590`
- `0x14006e19c`
- `0x14006e81c`
- `0x14007cb9e`
- `0x14007cbd0`
- `0x14007e010`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x140009d54`
- `ADVAPI32!EventWrite` at `0x140009d54`
- `ADVAPI32!RegDeleteKeyValueW` at `0x140009e2e`
- `ADVAPI32!RegDeleteKeyValueW` at `0x140009e2e`
- `KERNEL32!GetFileAttributesW` at `0x140009ba5`
- `KERNEL32!GetFileAttributesW` at `0x140009ba5`
- `KERNEL32!IsDebuggerPresent` at `0x140009d8b`
- `KERNEL32!IsDebuggerPresent` at `0x140009d8b`

## string_xrefs

- `0x140009d6e`: `CDiskProtection::Install`
- `0x140009b57`: `CDiskProtection::Install\n`
- `0x140009bdd`: `CDiskProtection::Install - Automatic Updates requires a reboot!\n`
- `0x140009c49`: `CDiskProtection::Install - Insufficient free disk space for DpReserved volume + cache file, free space = %I64u GB (%I64u bytes), space needed = %I64u GB (%I64u bytes)\n`
- `0x140009e02`: `CDiskProtection::Install - Exiting, hr = 0x%08X\n`
- `0x140009cb1`: `CDiskProtection::InstallDriver\n`
- `0x140009cc8`: `CDiskProtection::InstallDriver - failed, hr = 0x%08X\n`
- `0x140009c66`: `CDiskProtection::s_UninstallDriver\n`
- `0x140009cd4`: `CDiskProtection::s_UninstallDriver\n`

## pseudocode

```c
__int64 __fastcall CDiskProtection::Install(CDiskProtection *this)
{
  int CacheFilePath; // ebx
  int v3; // edi
  DWORD FileAttributesW; // eax
  CSoftwareUpdates *v5; // rcx
  CDiskProtection *v6; // rcx
  const unsigned __int16 *v7; // r9
  int v9; // [rsp+40h] [rbp-C0h] BYREF
  int v10; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int64 v11; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v12; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF

  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  CacheFilePath = CUserManagement::s_VerifyAccessLevelEx(3u, 0);
  if ( CacheFilePath < 0 )
    goto LABEL_29;
  DEBUGMSG(L"CDiskProtection::Install\n");
  if ( *((_DWORD *)this + 104) )
  {
    v3 = 0;
    CacheFilePath = -2147418113;
    goto LABEL_30;
  }
  memset_0(FileName, 0, 0x208u);
  CacheFilePath = CDiskProtection::s_VcfGetCacheFilePath(FileName);
  if ( CacheFilePath < 0 )
  {
LABEL_29:
    v3 = 1;
  }
  else
  {
    v3 = 0;
    FileAttributesW = GetFileAttributesW(FileName);
    if ( FileAttributesW == -1 || FileAttributesW == 6 )
    {
      v3 = 1;
      CacheFilePath = CSoftwareUpdates::CheckRebootRequired(v5, &v9);
      if ( CacheFilePath >= 0 )
      {
        if ( v9 )
        {
          DEBUGMSG(L"CDiskProtection::Install - Automatic Updates requires a reboot!\n");
          v3 = 0;
          CacheFilePath = -2147024546;
        }
        else
        {
          CacheFilePath = (*(__int64 (__fastcall **)(CDiskProtection *, unsigned __int64 *))(*(_QWORD *)this + 80LL))(
                            this,
                            &v11);
          if ( CacheFilePath >= 0 )
          {
            CacheFilePath = CDiskProtection::GetSystemVolumeFreeSpace(v6, &v12);
            if ( CacheFilePath >= 0 )
            {
              if ( v11 <= v12 )
              {
                CDiskProtection::s_DeleteCacheFile();
                DEBUGMSG(L"CDiskProtection::s_UninstallDriver\n");
                UninstallVcf(1);
                CacheFilePath = CDiskProtection::s_ModifyBootStatusPolicy();
                if ( CacheFilePath >= 0 )
                {
                  CacheFilePath = CDiskProtection::s_MovePageFileAndCrashDump(&v10);
                  if ( CacheFilePath >= 0 )
                  {
                    CacheFilePath = CDiskProtection::CreateCacheFile(this);
                    if ( CacheFilePath >= 0 )
                    {
                      DEBUGMSG(L"CDiskProtection::InstallDriver\n");
                      CacheFilePath = InstallVcf();
                      if ( CacheFilePath >= 0 )
                      {
                        CacheFilePath = CDiskProtection::s_ExcludeCacheFileFromSnapshot();
                        if ( CacheFilePath >= 0 )
                        {
                          CacheFilePath = CDiskProtection::s_RemovePostUninstallRegKey();
                          if ( CacheFilePath >= 0 )
                          {
                            CacheFilePath = CDiskProtection::s_EnableDefragTask(0);
                            if ( CacheFilePath >= 0 )
                            {
                              CacheFilePath = CSoftwareUpdates::OnDiskProtectionInstall(*((CSoftwareUpdates **)this + 56));
                              if ( CacheFilePath >= 0 )
                              {
                                CacheFilePath = ShutdownVmsAndReboot();
                                if ( CacheFilePath >= 0 )
                                {
                                  if ( EventWrite(g_hEventProviderHandle, &WmsSvc_DiskProtectionInstalled, 0, 0) )
                                  {
                                    LOGASSERT(
                                      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                                      0x28Au,
                                      L"CDiskProtection::Install",
                                      v7,
                                      L"err == ERROR_SUCCESS");
                                    if ( IsDebuggerPresent() )
                                      DEBUGMSGLEVEL(
                                        2u,
                                        L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
                                        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                                        650,
                                        L"CDiskProtection::Install",
                                        L"ASSERT",
                                        L"err == ERROR_SUCCESS");
                                    else
                                      DEBUGMSGBOX(
                                        L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
                                        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
                                        650,
                                        L"CDiskProtection::Install",
                                        L"ASSERT",
                                        L"err == ERROR_SUCCESS");
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                      else
                      {
                        DEBUGMSG(L"CDiskProtection::InstallDriver - failed, hr = 0x%08X\n");
                        DEBUGMSG(L"CDiskProtection::s_UninstallDriver\n");
                        UninstallVcf(0);
                      }
                    }
                  }
                }
              }
              else
              {
                DEBUGMSG(
                  L"CDiskProtection::Install - Insufficient free disk space for DpReserved volume + cache file, free space"
                   " = %I64u GB (%I64u bytes), space needed = %I64u GB (%I64u bytes)\n",
                  v12 >> 30,
                  v12,
                  v11 >> 30,
                  v11);
                v3 = 0;
                CacheFilePath = -2147024784;
              }
            }
          }
        }
      }
    }
    else
    {
      CacheFilePath = -2147024816;
    }
  }
LABEL_30:
  DEBUGMSG(L"CDiskProtection::Install - Exiting, hr = 0x%08X\n", (unsigned int)CacheFilePath);
  if ( CacheFilePath < 0 )
  {
    if ( v10 )
      RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows MultiPoint Server", L"DpReserveDriveLetter");
    if ( v3 )
    {
      CDiskProtection::s_PerformUninstallTasks(1);
      CDiskProtection::s_PerformPostUninstallStage();
    }
  }
  return (unsigned int)CacheFilePath;
}

```

## disassembly

```asm
0x140009af0  mov     [rsp-8+arg_8], rbx
0x140009af5  mov     [rsp-8+arg_10], rsi
0x140009afa  push    rbp
0x140009afb  push    rdi
0x140009afc  push    r13
0x140009afe  lea     rbp, [rsp-180h]
0x140009b06  sub     rsp, 280h
0x140009b0d  mov     rax, cs:__security_cookie
0x140009b14  xor     rax, rsp
0x140009b17  mov     [rbp+190h+var_20], rax
0x140009b1e  xor     edx, edx
0x140009b20  mov     [rsp+290h+var_250], 0
0x140009b28  mov     rsi, rcx
0x140009b2b  mov     [rsp+290h+var_24C], 0
0x140009b33  mov     [rsp+290h+var_248], 0
0x140009b3c  mov     [rsp+290h+var_240], 0
0x140009b45  lea     ecx, [rdx+3]
0x140009b48  call    ?s_VerifyAccessLevelEx@CUserManagement@@SAJW4EUserAccessLevel@@H@Z; CUserManagement::s_VerifyAccessLevelEx(EUserAccessLevel,int)
0x140009b4d  mov     ebx, eax
0x140009b4f  test    eax, eax
0x140009b51  js      loc_140009DFB
0x140009b57  lea     rcx, aCdiskprotectio_74; "CDiskProtection::Install\n"
0x140009b5e  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140009b63  cmp     dword ptr [rsi+1A0h], 0
0x140009b6a  jz      short loc_140009B78
0x140009b6c  xor     edi, edi
0x140009b6e  mov     ebx, 8000FFFFh
0x140009b73  jmp     loc_140009E00
0x140009b78  xor     edx, edx; Val
0x140009b7a  lea     rcx, [rsp+290h+FileName]; void *
0x140009b7f  mov     r8d, 208h; Size
0x140009b85  call    memset_0
0x140009b8a  lea     rcx, [rsp+290h+FileName]; unsigned __int16 *
0x140009b8f  call    ?s_VcfGetCacheFilePath@CDiskProtection@@KAJPEAG_K@Z; CDiskProtection::s_VcfGetCacheFilePath(ushort *,unsigned __int64)
0x140009b94  mov     ebx, eax
0x140009b96  test    eax, eax
0x140009b98  js      loc_140009DFB
0x140009b9e  lea     rcx, [rsp+290h+FileName]; lpFileName
0x140009ba3  xor     edi, edi
0x140009ba5  call    cs:__imp_GetFileAttributesW
0x140009bab  cmp     eax, 0FFFFFFFFh
0x140009bae  jz      short loc_140009BBF
0x140009bb0  cmp     eax, 6
0x140009bb3  jz      short loc_140009BBF
0x140009bb5  mov     ebx, 80070050h
0x140009bba  jmp     loc_140009E00
0x140009bbf  lea     rdx, [rsp+290h+var_250]; int *
0x140009bc4  xor     edi, 1
0x140009bc7  call    ?CheckRebootRequired@CSoftwareUpdates@@QEAAJPEAH@Z; CSoftwareUpdates::CheckRebootRequired(int *)
0x140009bcc  mov     ebx, eax
0x140009bce  test    eax, eax
0x140009bd0  js      loc_140009E00
0x140009bd6  cmp     [rsp+290h+var_250], 0
0x140009bdb  jz      short loc_140009BF5
0x140009bdd  lea     rcx, aCdiskprotectio_129; "CDiskProtection::Install - Automatic Up"...
0x140009be4  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140009be9  xor     edi, edi
0x140009beb  mov     ebx, 8007015Eh
0x140009bf0  jmp     loc_140009E00
0x140009bf5  mov     rax, [rsi]
0x140009bf8  lea     rdx, [rsp+290h+var_248]
0x140009bfd  mov     rcx, rsi
0x140009c00  mov     rax, [rax+50h]
0x140009c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c09  mov     ebx, eax
0x140009c0b  test    eax, eax
0x140009c0d  js      loc_140009E00
0x140009c13  lea     rdx, [rsp+290h+var_240]; unsigned __int64 *
0x140009c18  call    ?GetSystemVolumeFreeSpace@CDiskProtection@@IEAAJPEA_K@Z; CDiskProtection::GetSystemVolumeFreeSpace(unsigned __int64 *)
0x140009c1d  mov     ebx, eax
0x140009c1f  test    eax, eax
0x140009c21  js      loc_140009E00
0x140009c27  mov     rax, [rsp+290h+var_248]
0x140009c2c  mov     r8, [rsp+290h+var_240]
0x140009c31  cmp     rax, r8
0x140009c34  jbe     short loc_140009C61
0x140009c36  mov     r9, rax
0x140009c39  mov     [rsp+290h+var_270], rax
0x140009c3e  mov     rdx, r8
0x140009c41  shr     r9, 1Eh
0x140009c45  shr     rdx, 1Eh
0x140009c49  lea     rcx, aCdiskprotectio_155; "CDiskProtection::Install - Insufficient"...
0x140009c50  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140009c55  xor     edi, edi
0x140009c57  mov     ebx, 80070070h
0x140009c5c  jmp     loc_140009E00
0x140009c61  call    ?s_DeleteCacheFile@CDiskProtection@@KAJXZ; CDiskProtection::s_DeleteCacheFile(void)
0x140009c66  lea     rcx, aCdiskprotectio_138; "CDiskProtection::s_UninstallDriver\n"
0x140009c6d  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140009c72  mov     ecx, 1
0x140009c77  call    ?UninstallVcf@@YAJW4ERestoreDisablePasswordChangeSetting@@@Z; UninstallVcf(ERestoreDisablePasswordChangeSetting)
0x140009c7c  call    ?s_ModifyBootStatusPolicy@CDiskProtection@@KAJXZ; CDiskProtection::s_ModifyBootStatusPolicy(void)
0x140009c81  mov     ebx, eax
0x140009c83  test    eax, eax
0x140009c85  js      loc_140009E00
0x140009c8b  lea     rcx, [rsp+290h+var_24C]; int *
0x140009c90  call    ?s_MovePageFileAndCrashDump@CDiskProtection@@KAJPEAH@Z; CDiskProtection::s_MovePageFileAndCrashDump(int *)
0x140009c95  mov     ebx, eax
0x140009c97  test    eax, eax
0x140009c99  js      loc_140009E00
0x140009c9f  mov     rcx, rsi; this
0x140009ca2  call    ?CreateCacheFile@CDiskProtection@@IEAAJXZ; CDiskProtection::CreateCacheFile(void)
0x140009ca7  mov     ebx, eax
0x140009ca9  test    eax, eax
0x140009cab  js      loc_140009E00
0x140009cb1  lea     rcx, aCdiskprotectio_152; "CDiskProtection::InstallDriver\n"
0x140009cb8  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140009cbd  call    ?InstallVcf@@YAJXZ; InstallVcf(void)
0x140009cc2  mov     ebx, eax
0x140009cc4  test    eax, eax
0x140009cc6  jns     short loc_140009CEC
0x140009cc8  lea     rcx, aCdiskprotectio_27; "CDiskProtection::InstallDriver - failed"...
0x140009ccf  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140009cd4  lea     rcx, aCdiskprotectio_138; "CDiskProtection::s_UninstallDriver\n"
0x140009cdb  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140009ce0  xor     ecx, ecx
0x140009ce2  call    ?UninstallVcf@@YAJW4ERestoreDisablePasswordChangeSetting@@@Z; UninstallVcf(ERestoreDisablePasswordChangeSetting)
0x140009ce7  jmp     loc_140009E00
0x140009cec  call    ?s_ExcludeCacheFileFromSnapshot@CDiskProtection@@KAJXZ; CDiskProtection::s_ExcludeCacheFileFromSnapshot(void)
0x140009cf1  mov     ebx, eax
0x140009cf3  test    eax, eax
0x140009cf5  js      loc_140009E00
0x140009cfb  call    ?s_RemovePostUninstallRegKey@CDiskProtection@@KAJXZ; CDiskProtection::s_RemovePostUninstallRegKey(void)
0x140009d00  mov     ebx, eax
0x140009d02  test    eax, eax
0x140009d04  js      loc_140009E00
0x140009d0a  xor     ecx, ecx; int
0x140009d0c  call    ?s_EnableDefragTask@CDiskProtection@@KAJH@Z; CDiskProtection::s_EnableDefragTask(int)
0x140009d11  mov     ebx, eax
0x140009d13  test    eax, eax
0x140009d15  js      loc_140009E00
0x140009d1b  mov     rcx, [rsi+1C0h]; this
0x140009d22  call    ?OnDiskProtectionInstall@CSoftwareUpdates@@QEAAJXZ; CSoftwareUpdates::OnDiskProtectionInstall(void)
0x140009d27  mov     ebx, eax
0x140009d29  test    eax, eax
0x140009d2b  js      loc_140009E00
0x140009d31  call    ?ShutdownVmsAndReboot@@YAJXZ; ShutdownVmsAndReboot(void)
0x140009d36  mov     ebx, eax
0x140009d38  test    eax, eax
0x140009d3a  js      loc_140009E00
0x140009d40  mov     rcx, cs:?g_hEventProviderHandle@@3_KA; RegHandle
0x140009d47  lea     rdx, WmsSvc_DiskProtectionInstalled; EventDescriptor
0x140009d4e  xor     r9d, r9d; UserData
0x140009d51  xor     r8d, r8d; UserDataCount
0x140009d54  call    cs:__imp_EventWrite
0x140009d5a  test    eax, eax
0x140009d5c  jz      loc_140009E00
0x140009d62  lea     rax, aErrErrorSucces; "err == ERROR_SUCCESS"
0x140009d69  mov     esi, 28Ah
0x140009d6e  lea     r13, aCdiskprotectio_95; "CDiskProtection::Install"
0x140009d75  mov     [rsp+290h+var_270], rax; unsigned __int16 *
0x140009d7a  mov     r8, r13; unsigned __int16 *
0x140009d7d  lea     rcx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140009d84  mov     edx, esi; unsigned int
0x140009d86  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140009d8b  call    cs:__imp_IsDebuggerPresent
0x140009d91  test    eax, eax
0x140009d93  lea     rax, aErrErrorSucces; "err == ERROR_SUCCESS"
0x140009d9a  jz      short loc_140009DCF
0x140009d9c  mov     [rsp+290h+var_260], rax
0x140009da1  lea     r8, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140009da8  lea     rax, aAssert; "ASSERT"
0x140009daf  mov     r9d, esi
0x140009db2  mov     [rsp+290h+var_268], rax
0x140009db7  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140009dbe  mov     ecx, 2; unsigned __int8
0x140009dc3  mov     [rsp+290h+var_270], r13
0x140009dc8  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140009dcd  jmp     short loc_140009E00
0x140009dcf  mov     [rsp+290h+var_268], rax
0x140009dd4  lea     rdx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140009ddb  lea     rax, aAssert; "ASSERT"
0x140009de2  mov     r9, r13
0x140009de5  mov     r8d, esi
0x140009de8  mov     [rsp+290h+var_270], rax
0x140009ded  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140009df4  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140009df9  jmp     short loc_140009E00
0x140009dfb  mov     edi, 1
0x140009e00  mov     edx, ebx
0x140009e02  lea     rcx, aCdiskprotectio_103; "CDiskProtection::Install - Exiting, hr "...
0x140009e09  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140009e0e  test    ebx, ebx
0x140009e10  jns     short loc_140009E47
0x140009e12  cmp     [rsp+290h+var_24C], 0
0x140009e17  jz      short loc_140009E34
0x140009e19  lea     r8, ?s_szReserveDriveLetterValueName@CDiskProtection@@1QBGB; "DpReserveDriveLetter"
0x140009e20  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140009e27  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows MultiPoint"...
0x140009e2e  call    cs:__imp_RegDeleteKeyValueW
0x140009e34  test    edi, edi
0x140009e36  jz      short loc_140009E47
0x140009e38  mov     ecx, 1
0x140009e3d  call    ?s_PerformUninstallTasks@CDiskProtection@@SAJW4ERestoreDisablePasswordChangeSetting@@@Z; CDiskProtection::s_PerformUninstallTasks(ERestoreDisablePasswordChangeSetting)
0x140009e42  call    ?s_PerformPostUninstallStage@CDiskProtection@@SAJXZ; CDiskProtection::s_PerformPostUninstallStage(void)
0x140009e47  mov     eax, ebx
0x140009e49  mov     rcx, [rbp+190h+var_20]
0x140009e50  xor     rcx, rsp; StackCookie
0x140009e53  call    __security_check_cookie
0x140009e58  lea     r11, [rsp+290h+var_10]
0x140009e60  mov     rbx, [r11+28h]
0x140009e64  mov     rsi, [r11+30h]
0x140009e68  mov     rsp, r11
0x140009e6b  pop     r13
0x140009e6d  pop     rdi
0x140009e6e  pop     rbp
0x140009e6f  retn
```
