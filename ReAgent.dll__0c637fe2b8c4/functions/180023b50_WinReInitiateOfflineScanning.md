# WinReInitiateOfflineScanning

- ea: `0x180023b50`
- end: `0x180023f11`
- name: `WinReInitiateOfflineScanning`
- size: `961`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x18000f044`
- `0x18001ee2c`
- `0x18001f0c0`
- `0x18001f47c`
- `0x18001fc48`
- `0x1800209a0`
- `0x180023b50`
- `0x180024df0`
- `0x180026670`
- `0x180029210`
- `0x180035204`
- `0x18004d52c`
- `0x18004d584`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005cff0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180023c5e`
- `msvcrt!_wcsnicmp` at `0x180023c5e`
- `KERNEL32!GetLastError` at `0x180023c25`
- `KERNEL32!GetLastError` at `0x180023cab`
- `KERNEL32!GetLastError` at `0x180023ce4`
- `KERNEL32!GetLastError` at `0x180023d01`
- `KERNEL32!GetLastError` at `0x180023dde`
- `KERNEL32!GetLastError` at `0x180023e03`
- `KERNEL32!GetLastError` at `0x180023e34`
- `KERNEL32!GetLastError` at `0x180023e57`
- `KERNEL32!GetLastError` at `0x180023e84`
- `KERNEL32!GetLastError` at `0x180023c25`
- `KERNEL32!GetLastError` at `0x180023cab`
- `KERNEL32!GetLastError` at `0x180023ce4`
- `KERNEL32!GetLastError` at `0x180023d01`
- `KERNEL32!GetLastError` at `0x180023dde`
- `KERNEL32!GetLastError` at `0x180023e03`
- `KERNEL32!GetLastError` at `0x180023e34`
- `KERNEL32!GetLastError` at `0x180023e57`
- `KERNEL32!GetLastError` at `0x180023e84`
- `KERNEL32!SetLastError` at `0x180023ecd`
- `KERNEL32!SetLastError` at `0x180023ecd`
- `KERNEL32!GetWindowsDirectoryW` at `0x180023c1b`
- `KERNEL32!GetWindowsDirectoryW` at `0x180023c1b`
- `ADVAPI32!InitiateSystemShutdownExW` at `0x180023e2a`
- `ADVAPI32!InitiateSystemShutdownExW` at `0x180023e2a`

## string_xrefs

- `0x180023be6`: `Parameters: applicationName: %s, commandLine: %s`
- `0x180023c2d`: `failed to get Windows directory. Error: 0x%08X`
- `0x180023cb3`: `failed to get winre config. Error: 0x%08X`
- `0x180023da9`: `failed to register offline scanning command to registry key. Error: 0x%08X`
- `0x180023de4`: `failed to configure boot app. Error: 0x%08X`
- `0x180023e09`: `Cannot enable privilege SE_SHUTDOWN_PRIVILEGE. Error: 0x%08X`
- `0x180023e5d`: `failed to delete BCD boot entry. Error: 0x%08X`

## pseudocode

```c
__int64 __fastcall WinReInitiateOfflineScanning(const wchar_t *a1, const unsigned __int16 *a2)
{
  unsigned int v4; // r15d
  const unsigned __int16 *v5; // r9
  const unsigned __int16 *v6; // r8
  __int64 v7; // rbx
  DWORD DoesPathExist; // eax
  int v9; // r14d
  unsigned __int64 v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rax
  __int64 v16; // rcx
  BYTE *v17; // rcx
  __int64 v18; // r8
  unsigned __int16 *v19; // r9
  DWORD LastError; // eax
  const wchar_t *v21; // rdx
  DWORD v22; // eax
  DWORD v23; // eax
  __int64 v24; // rdx
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  BYTE *lpData[3]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  int v30; // [rsp+68h] [rbp-98h]
  unsigned __int16 v31[1556]; // [rsp+2D8h] [rbp+1D8h] BYREF
  WCHAR Buffer[264]; // [rsp+F00h] [rbp+E00h] BYREF

  v4 = 0;
  memset_0(&v29, 0, 0xEA0u);
  v28 = 7;
  LOWORD(lpData[0]) = 0;
  v26 = 1;
  lpData[2] = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReInitiateOfflineScanning");
  v5 = a2;
  if ( !a2 )
    v5 = L"NULL";
  v6 = a1;
  if ( !a1 )
    v6 = L"NULL";
  UnattendLogW(0, L"Parameters: applicationName: %s, commandLine: %s", v6, v5);
  if ( a1 )
  {
    if ( GetWindowsDirectoryW(Buffer, 0x104u) )
    {
      if ( !Buffer[0] || !*a1 || _wcsnicmp(Buffer, a1, 1u) )
      {
        LODWORD(v7) = 13;
        goto LABEL_48;
      }
      DoesPathExist = Utils::DoesPathExist(a1);
      LODWORD(v7) = DoesPathExist;
      if ( DoesPathExist )
      {
        UnattendLogW(1, L"File %s does not exist. Error: 0x%08X", a1, DoesPathExist);
        goto LABEL_48;
      }
      v29 = 3744;
      if ( (unsigned int)WinReGetConfigInternal(0, 0, (__int64)&v29) )
      {
        if ( !v30 )
        {
          LODWORD(v7) = 50;
          goto LABEL_48;
        }
        if ( WinReSetRecoveryAction(4u, 0, 0, 0) )
        {
          if ( (unsigned int)WinReQueueRecoveryBoot() )
          {
            v9 = 0;
            v10 = std::char_traits<unsigned short>::length(a1 + 2);
            std::wstring::append(lpData, v11, v10);
            if ( a2 && *a2 )
            {
              v12 = std::char_traits<unsigned short>::length(L" <");
              std::wstring::append(lpData, v13, v12);
              v14 = std::char_traits<unsigned short>::length(a2);
              std::wstring::append(lpData, (__int64)a2, v14);
              v15 = std::char_traits<unsigned short>::length(L">");
              std::wstring::append(lpData, v16, v15);
            }
            v17 = (BYTE *)lpData;
            if ( v28 >= 8 )
              v17 = lpData[0];
            LODWORD(v7) = winreRegisterOfflineScanningCommand(v17);
            if ( (_DWORD)v7 )
            {
              UnattendLogW(
                1,
                L"failed to register offline scanning command to registry key. Error: 0x%08X",
                (unsigned int)v7);
            }
            else
            {
              v19 = (unsigned __int16 *)lpData;
              if ( v28 >= 8 )
                v19 = (unsigned __int16 *)lpData[0];
              if ( (unsigned int)winreConfigureBootApp(v31, 1, v18, v19, 1) )
              {
                v9 = 1;
                if ( (unsigned int)Utils::EnablePrivilege(0x13u, &v26) )
                {
                  if ( InitiateSystemShutdownExW(0, 0, 5u, 1, 1, 0x20001u) )
                  {
                    v4 = 1;
                    goto LABEL_48;
                  }
                  LastError = GetLastError();
                  v21 = L"failed to initiate system shutdown. Error: 0x%08X";
                }
                else
                {
                  LastError = GetLastError();
                  v21 = L"Cannot enable privilege SE_SHUTDOWN_PRIVILEGE. Error: 0x%08X";
                }
              }
              else
              {
                LastError = GetLastError();
                v21 = L"failed to configure boot app. Error: 0x%08X";
              }
              LODWORD(v7) = LastError;
              UnattendLogW(1, v21, LastError);
            }
            if ( winreDeleteBCDBootEntry() )
            {
              v22 = GetLastError();
              UnattendLogW(1, L"failed to delete BCD boot entry. Error: 0x%08X", v22);
            }
            if ( v9 == 1 && !(unsigned int)WinReClearBootApp(v31) )
            {
              v23 = GetLastError();
              UnattendLogW(1, L"failed to clear boot app. Error: 0x%08X", v23);
            }
          }
          else
          {
            v7 = GetLastError();
            UnattendLogW(1, L"failed to queue recovery boot. Error: 0x%08X", v7);
          }
        }
        else
        {
          v7 = GetLastError();
          UnattendLogW(1, L"failed to set recovery action. Error: 0x%08X", v7);
        }
      }
      else
      {
        v7 = GetLastError();
        UnattendLogW(1, L"failed to get winre config. Error: 0x%08X", v7);
      }
    }
    else
    {
      v7 = GetLastError();
      UnattendLogW(1, L"failed to get Windows directory. Error: 0x%08X", v7);
    }
    if ( !(_DWORD)v7 )
      LODWORD(v7) = 31;
  }
  else
  {
    LODWORD(v7) = 87;
  }
LABEL_48:
  UnattendLogW(0, L"Exit WinReInitiateOfflineScanning return value: %d, last error: 0x%x", v4, (unsigned int)v7);
  UnattendFinalizeLog();
  SetLastError(v7);
  LOBYTE(v24) = 1;
  std::wstring::_Tidy(lpData, v24, 0);
  return v4;
}

```

## disassembly

```asm
0x180023b50  mov     [rsp-8+arg_10], rbx
0x180023b55  mov     [rsp-8+arg_18], rsi
0x180023b5a  push    rbp
0x180023b5b  push    rdi
0x180023b5c  push    r12
0x180023b5e  push    r14
0x180023b60  push    r15
0x180023b62  lea     rbp, [rsp-1020h]
0x180023b6a  mov     eax, 1120h
0x180023b6f  call    _alloca_probe
0x180023b74  sub     rsp, rax
0x180023b77  mov     rax, cs:__security_cookie
0x180023b7e  xor     rax, rsp
0x180023b81  mov     [rbp+1040h+var_30], rax
0x180023b88  mov     rsi, rdx
0x180023b8b  mov     rdi, rcx
0x180023b8e  mov     r14d, 0EA0h
0x180023b94  lea     rcx, [rsp+1140h+var_10E0]; void *
0x180023b99  mov     r8d, r14d; Size
0x180023b9c  xor     edx, edx; Val
0x180023b9e  xor     r15d, r15d
0x180023ba1  call    memset_0
0x180023ba6  xor     eax, eax
0x180023ba8  mov     [rsp+1140h+var_10F0], 7
0x180023bb1  lea     r12d, [r15+1]
0x180023bb5  mov     word ptr [rsp+1140h+lpData], ax
0x180023bba  xor     ecx, ecx
0x180023bbc  mov     [rsp+1140h+var_1110], r12d
0x180023bc1  mov     [rsp+1140h+var_10F8], r15
0x180023bc6  call    UnattendInitializeLogEx2
0x180023bcb  lea     rdx, aEnterWinreinit; "Enter WinReInitiateOfflineScanning"
0x180023bd2  xor     ecx, ecx
0x180023bd4  call    UnattendLogW
0x180023bd9  lea     rax, aNull_0; "NULL"
0x180023be0  test    rsi, rsi
0x180023be3  mov     r9, rsi
0x180023be6  lea     rdx, aParametersAppl; "Parameters: applicationName: %s, comman"...
0x180023bed  cmovz   r9, rax
0x180023bf1  mov     r8, rdi
0x180023bf4  test    rdi, rdi
0x180023bf7  cmovz   r8, rax
0x180023bfb  xor     ecx, ecx
0x180023bfd  call    UnattendLogW
0x180023c02  test    rdi, rdi
0x180023c05  jnz     short loc_180023C0F
0x180023c07  lea     ebx, [rdi+57h]
0x180023c0a  jmp     loc_180023EB2
0x180023c0f  mov     edx, 104h; uSize
0x180023c14  lea     rcx, [rbp+1040h+Buffer]; lpBuffer
0x180023c1b  call    cs:__imp_GetWindowsDirectoryW
0x180023c21  test    eax, eax
0x180023c23  jnz     short loc_180023C39
0x180023c25  call    cs:__imp_GetLastError
0x180023c2b  mov     ebx, eax
0x180023c2d  lea     rdx, aFailedToGetWin_4; "failed to get Windows directory. Error:"...
0x180023c34  jmp     loc_180023E91
0x180023c39  xor     eax, eax
0x180023c3b  cmp     ax, [rbp+1040h+Buffer]
0x180023c42  jz      loc_180023EAD
0x180023c48  cmp     ax, [rdi]
0x180023c4b  jz      loc_180023EAD
0x180023c51  mov     r8, r12; MaxCount
0x180023c54  lea     rcx, [rbp+1040h+Buffer]; String1
0x180023c5b  mov     rdx, rdi; String2
0x180023c5e  call    cs:__imp__wcsnicmp
0x180023c64  test    eax, eax
0x180023c66  jnz     loc_180023EAD
0x180023c6c  mov     rcx, rdi; unsigned __int16 *
0x180023c6f  call    ?DoesPathExist@Utils@@SAKPEBG@Z; Utils::DoesPathExist(ushort const *)
0x180023c74  mov     ebx, eax
0x180023c76  test    eax, eax
0x180023c78  jz      short loc_180023C94
0x180023c7a  mov     r9d, eax
0x180023c7d  lea     rdx, aFileSDoesNotEx; "File %s does not exist. Error: 0x%08X"
0x180023c84  mov     r8, rdi
0x180023c87  mov     ecx, r12d
0x180023c8a  call    UnattendLogW
0x180023c8f  jmp     loc_180023EB2
0x180023c94  lea     r8, [rsp+1140h+var_10E0]
0x180023c99  mov     [rsp+1140h+var_10E0], r14
0x180023c9e  xor     edx, edx
0x180023ca0  xor     ecx, ecx
0x180023ca2  call    WinReGetConfigInternal
0x180023ca7  test    eax, eax
0x180023ca9  jnz     short loc_180023CBF
0x180023cab  call    cs:__imp_GetLastError
0x180023cb1  mov     ebx, eax
0x180023cb3  lea     rdx, aFailedToGetWin_0; "failed to get winre config. Error: 0x%0"...
0x180023cba  jmp     loc_180023E91
0x180023cbf  cmp     [rsp+1140h+var_10D8], r15d
0x180023cc4  jnz     short loc_180023CD0
0x180023cc6  mov     ebx, 32h ; '2'
0x180023ccb  jmp     loc_180023EB2
0x180023cd0  xor     edx, edx
0x180023cd2  xor     r9d, r9d
0x180023cd5  xor     r8d, r8d
0x180023cd8  lea     ecx, [rdx+4]
0x180023cdb  call    WinReSetRecoveryAction
0x180023ce0  test    eax, eax
0x180023ce2  jnz     short loc_180023CF8
0x180023ce4  call    cs:__imp_GetLastError
0x180023cea  mov     ebx, eax
0x180023cec  lea     rdx, aFailedToSetRec_1; "failed to set recovery action. Error: 0"...
0x180023cf3  jmp     loc_180023E91
0x180023cf8  call    WinReQueueRecoveryBoot
0x180023cfd  test    eax, eax
0x180023cff  jnz     short loc_180023D15
0x180023d01  call    cs:__imp_GetLastError
0x180023d07  mov     ebx, eax
0x180023d09  lea     rdx, aFailedToQueueR; "failed to queue recovery boot. Error: 0"...
0x180023d10  jmp     loc_180023E91
0x180023d15  lea     rcx, [rdi+4]
0x180023d19  xor     r14d, r14d
0x180023d1c  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180023d21  mov     rdx, rcx
0x180023d24  mov     r8, rax
0x180023d27  lea     rcx, [rsp+1140h+lpData]
0x180023d2c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180023d31  test    rsi, rsi
0x180023d34  jz      short loc_180023D8D
0x180023d36  xor     eax, eax
0x180023d38  cmp     ax, [rsi]
0x180023d3b  jz      short loc_180023D8D
0x180023d3d  lea     rcx, asc_18007827C; " <"
0x180023d44  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180023d49  mov     rdx, rcx
0x180023d4c  mov     r8, rax
0x180023d4f  lea     rcx, [rsp+1140h+lpData]
0x180023d54  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180023d59  mov     rcx, rsi
0x180023d5c  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180023d61  mov     r8, rax
0x180023d64  lea     rcx, [rsp+1140h+lpData]
0x180023d69  mov     rdx, rsi
0x180023d6c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180023d71  lea     rcx, asc_180078284; ">"
0x180023d78  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180023d7d  mov     rdx, rcx
0x180023d80  mov     r8, rax
0x180023d83  lea     rcx, [rsp+1140h+lpData]
0x180023d88  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180023d8d  cmp     [rsp+1140h+var_10F0], 8
0x180023d93  lea     rcx, [rsp+1140h+lpData]
0x180023d98  cmovnb  rcx, [rsp+1140h+lpData]; lpData
0x180023d9e  call    ?winreRegisterOfflineScanningCommand@@YAKPEBG@Z; winreRegisterOfflineScanningCommand(ushort const *)
0x180023da3  mov     ebx, eax
0x180023da5  test    eax, eax
0x180023da7  jz      short loc_180023DB5
0x180023da9  lea     rdx, aFailedToRegist_1; "failed to register offline scanning com"...
0x180023db0  jmp     loc_180023E43
0x180023db5  cmp     [rsp+1140h+var_10F0], 8
0x180023dbb  lea     r9, [rsp+1140h+lpData]
0x180023dc0  mov     edx, r12d
0x180023dc3  mov     [rsp+1140h+bRebootAfterShutdown], r12d; int
0x180023dc8  cmovnb  r9, [rsp+1140h+lpData]
0x180023dce  lea     rcx, [rbp+1040h+var_E68]; unsigned __int16 *
0x180023dd5  call    winreConfigureBootApp
0x180023dda  test    eax, eax
0x180023ddc  jnz     short loc_180023DED
0x180023dde  call    cs:__imp_GetLastError
0x180023de4  lea     rdx, aFailedToConfig; "failed to configure boot app. Error: 0x"...
0x180023deb  jmp     short loc_180023E41
0x180023ded  lea     rdx, [rsp+1140h+var_1110]; int *
0x180023df2  mov     ecx, 13h; unsigned int
0x180023df7  mov     r14d, r12d
0x180023dfa  call    ?EnablePrivilege@Utils@@SAHKPEAH@Z; Utils::EnablePrivilege(ulong,int *)
0x180023dff  test    eax, eax
0x180023e01  jnz     short loc_180023E12
0x180023e03  call    cs:__imp_GetLastError
0x180023e09  lea     rdx, aCannotEnablePr; "Cannot enable privilege SE_SHUTDOWN_PRI"...
0x180023e10  jmp     short loc_180023E41
0x180023e12  xor     edx, edx; lpMessage
0x180023e14  mov     [rsp+1140h+dwReason], 20001h; dwReason
0x180023e1c  mov     r9d, r12d; bForceAppsClosed
0x180023e1f  mov     [rsp+1140h+bRebootAfterShutdown], r12d; bRebootAfterShutdown
0x180023e24  xor     ecx, ecx; lpMachineName
0x180023e26  lea     r8d, [rdx+5]; dwTimeout
0x180023e2a  call    cs:__imp_InitiateSystemShutdownExW
0x180023e30  test    eax, eax
0x180023e32  jnz     short loc_180023EA8
0x180023e34  call    cs:__imp_GetLastError
0x180023e3a  lea     rdx, aFailedToInitia_6; "failed to initiate system shutdown. Err"...
0x180023e41  mov     ebx, eax
0x180023e43  mov     ecx, r12d
0x180023e46  mov     r8d, ebx
0x180023e49  call    UnattendLogW
0x180023e4e  call    winreDeleteBCDBootEntry
0x180023e53  test    eax, eax
0x180023e55  jz      short loc_180023E6F
0x180023e57  call    cs:__imp_GetLastError
0x180023e5d  lea     rdx, aFailedToDelete_7; "failed to delete BCD boot entry. Error:"...
0x180023e64  mov     ecx, r12d
0x180023e67  mov     r8d, eax
0x180023e6a  call    UnattendLogW
0x180023e6f  cmp     r14d, r12d
0x180023e72  jnz     short loc_180023E9C
0x180023e74  lea     rcx, [rbp+1040h+var_E68]
0x180023e7b  call    WinReClearBootApp
0x180023e80  test    eax, eax
0x180023e82  jnz     short loc_180023E9C
0x180023e84  call    cs:__imp_GetLastError
0x180023e8a  lea     rdx, aFailedToClearB; "failed to clear boot app. Error: 0x%08X"
0x180023e91  mov     r8d, eax
0x180023e94  mov     ecx, r12d
0x180023e97  call    UnattendLogW
0x180023e9c  test    ebx, ebx
0x180023e9e  mov     eax, 1Fh
0x180023ea3  cmovz   ebx, eax
0x180023ea6  jmp     short loc_180023EB2
0x180023ea8  mov     r15d, r12d
0x180023eab  jmp     short loc_180023EB2
0x180023ead  mov     ebx, 0Dh
0x180023eb2  mov     r9d, ebx
0x180023eb5  lea     rdx, aExitWinreiniti; "Exit WinReInitiateOfflineScanning retur"...
0x180023ebc  mov     r8d, r15d
0x180023ebf  xor     ecx, ecx
0x180023ec1  call    UnattendLogW
0x180023ec6  call    UnattendFinalizeLog
0x180023ecb  mov     ecx, ebx; dwErrCode
0x180023ecd  call    cs:__imp_SetLastError
0x180023ed3  xor     r8d, r8d
0x180023ed6  lea     rcx, [rsp+1140h+lpData]
0x180023edb  mov     dl, r12b
0x180023ede  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180023ee3  mov     eax, r15d
0x180023ee6  mov     rcx, [rbp+1040h+var_30]
0x180023eed  xor     rcx, rsp; StackCookie
0x180023ef0  call    __security_check_cookie
0x180023ef5  lea     r11, [rsp+1140h+var_20]
0x180023efd  mov     rbx, [r11+40h]
0x180023f01  mov     rsi, [r11+48h]
0x180023f05  mov     rsp, r11
0x180023f08  pop     r15
0x180023f0a  pop     r14
0x180023f0c  pop     r12
0x180023f0e  pop     rdi
0x180023f0f  pop     rbp
0x180023f10  retn
```
