# CBrowserBrokerInstance::RunExtExportToGenerateFirefoxFavoritesTempFile(ushort const *,_GUID)

- ea: `0x18000c3a0`
- end: `0x18000c637`
- name: `?RunExtExportToGenerateFirefoxFavoritesTempFile@CBrowserBrokerInstance@@UEAAJPEBGU_GUID@@@Z`
- size: `663`
- prototype: `__int64 __fastcall(CBrowserBrokerInstance *__hidden this, const unsigned __int16 *, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x18000c3a0`
- `0x18000d1c0`
- `0x18000e428`
- `0x18001ead0`
- `0x18001eb88`
- `0x18001ed08`
- `0x1800245ec`
- `0x18002b4e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c5eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c5f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c5eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c5f6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c4a4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c4a4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c5ad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c5ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5fe`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000c599`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000c599`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000c44e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000c44e`

## string_xrefs

- `0x18000c4aa`: `"%s" "%s" "%s" "%s" JSON FIREFOX "%s"`

## pseudocode

```c
__int64 __fastcall CBrowserBrokerInstance::RunExtExportToGenerateFirefoxFavoritesTempFile(
        CBrowserBrokerInstance *this,
        const unsigned __int16 *a2,
        struct _GUID *a3)
{
  unsigned int v5; // edx
  int PIC; // ebx
  __int64 v7; // rdx
  int v8; // r8d
  unsigned int v9; // r8d
  DWORD v10; // eax
  signed int v11; // eax
  signed int LastError; // eax
  bool v14; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v15; // [rsp+54h] [rbp-ACh] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v18[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v19; // [rsp+F0h] [rbp-10h]
  __int128 v20; // [rsp+100h] [rbp+0h]
  _OWORD v21[2]; // [rsp+110h] [rbp+10h]
  OLECHAR sz[128]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR pszPath[264]; // [rsp+230h] [rbp+130h] BYREF
  wchar_t Str[264]; // [rsp+440h] [rbp+340h] BYREF
  unsigned __int16 v25[264]; // [rsp+650h] [rbp+550h] BYREF
  unsigned __int16 v26[264]; // [rsp+860h] [rbp+760h] BYREF
  WCHAR CommandLine[1344]; // [rsp+A70h] [rbp+970h] BYREF

  v15 = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, &v15);
  if ( PIC < 0 )
    return (unsigned int)PIC;
  v14 = 0;
  PIC = GetDefaultFirefoxInstallPath(Str, v5, &v14);
  if ( PIC < 0 )
  {
LABEL_19:
    LastError = GetLastError();
    PIC = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)PIC;
  }
  v8 = 42;
  if ( !v14 )
    v8 = 38;
  if ( GetIEPathFromCsidlW(pszPath, v7, v8, 0) )
  {
    PIC = PathCchAppend(pszPath, 0x104u, L"ExtExport.exe");
    if ( PIC >= 0 )
    {
      PIC = GetFirefoxSqliteDllPath(Str, v26, v9);
      if ( PIC >= 0 )
      {
        PIC = GetFirefoxBookmarksFilePath(v25);
        if ( PIC >= 0 )
        {
          sz[0] = 0;
          StringFromGUID2(a3, sz, 128);
          *(_OWORD *)v18 = *(_OWORD *)L"\"%s\" \"%s\" \"%s\" \"%s\" JSON FIREFOX \"%s\"";
          v20 = *(_OWORD *)L"%s\" JSON FIREFOX \"%s\"";
          v19 = *(_OWORD *)L"\" \"%s\" \"%s\" JSON FIREFOX \"%s\"";
          v21[0] = *(_OWORD *)L" FIREFOX \"%s\"";
          *(_OWORD *)((char *)v21 + 12) = *(_OWORD *)L"OX \"%s\"";
          PIC = StringCchPrintfW(CommandLine, 0x53Au, v18, pszPath, v26, v25, a2, sz);
          if ( PIC >= 0 )
          {
            memset_0(&StartupInfo.cb + 1, 0, 0x64u);
            StartupInfo.cb = 104;
            memset(&ProcessInformation, 0, sizeof(ProcessInformation));
            if ( CreateProcessW(0, CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
            {
              v10 = WaitForSingleObject(ProcessInformation.hProcess, 0x3A98u);
              if ( v10 )
              {
                if ( v10 == 258 )
                {
                  PIC = -2147418113;
                }
                else if ( v10 == -1 )
                {
                  v11 = GetLastError();
                  PIC = v11;
                  if ( v11 > 0 )
                    PIC = (unsigned __int16)v11 | 0x80070000;
                }
                else
                {
                  PIC = -2147467259;
                }
              }
              CloseHandle(ProcessInformation.hProcess);
              CloseHandle(ProcessInformation.hThread);
              return (unsigned int)PIC;
            }
            goto LABEL_19;
          }
        }
      }
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x18000c3a0  mov     [rsp-8+arg_0], rbx
0x18000c3a5  push    rbp
0x18000c3a6  push    rsi
0x18000c3a7  push    rdi
0x18000c3a8  lea     rbp, [rsp-1400h]
0x18000c3b0  mov     eax, 1500h
0x18000c3b5  call    _alloca_probe
0x18000c3ba  sub     rsp, rax
0x18000c3bd  mov     rax, cs:__security_cookie
0x18000c3c4  xor     rax, rsp
0x18000c3c7  mov     [rbp+1410h+var_20], rax
0x18000c3ce  mov     rdi, rdx
0x18000c3d1  mov     [rsp+1510h+var_14BC], 0
0x18000c3d9  lea     rdx, [rsp+1510h+var_14BC]; unsigned int *
0x18000c3de  mov     ecx, 1; unsigned int
0x18000c3e3  mov     rsi, r8
0x18000c3e6  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x18000c3eb  mov     ebx, eax
0x18000c3ed  test    eax, eax
0x18000c3ef  js      loc_18000C613
0x18000c3f5  lea     r8, [rsp+1510h+var_14C0]; bool *
0x18000c3fa  mov     [rsp+1510h+var_14C0], 0
0x18000c3ff  lea     rcx, [rbp+1410h+Str]; Str
0x18000c406  call    ?GetDefaultFirefoxInstallPath@@YAJPEAGKPEA_N@Z; GetDefaultFirefoxInstallPath(ushort *,ulong,bool *)
0x18000c40b  mov     ebx, eax
0x18000c40d  test    eax, eax
0x18000c40f  js      loc_18000C5FE
0x18000c415  xor     r9d, r9d; bool
0x18000c418  lea     rcx, [rbp+1410h+pszPath]; unsigned __int16 *
0x18000c41f  lea     r8d, [r9+2Ah]
0x18000c423  cmp     [rsp+1510h+var_14C0], r9b
0x18000c428  jnz     short loc_18000C42E
0x18000c42a  lea     r8d, [r9+26h]; unsigned int
0x18000c42e  call    ?GetIEPathFromCsidlW@@YA_NPEAGKK_N@Z; GetIEPathFromCsidlW(ushort *,ulong,ulong,bool)
0x18000c433  test    al, al
0x18000c435  jz      loc_18000C613
0x18000c43b  lea     r8, pszMore; "ExtExport.exe"
0x18000c442  mov     edx, 104h; cchPath
0x18000c447  lea     rcx, [rbp+1410h+pszPath]; pszPath
0x18000c44e  call    cs:__imp_PathCchAppend
0x18000c454  mov     ebx, eax
0x18000c456  test    eax, eax
0x18000c458  js      loc_18000C613
0x18000c45e  lea     rdx, [rbp+1410h+var_CB0]; unsigned __int16 *
0x18000c465  lea     rcx, [rbp+1410h+Str]; unsigned __int16 *
0x18000c46c  call    ?GetFirefoxSqliteDllPath@@YAJPEAG0K@Z; GetFirefoxSqliteDllPath(ushort *,ushort *,ulong)
0x18000c471  mov     ebx, eax
0x18000c473  test    eax, eax
0x18000c475  js      loc_18000C613
0x18000c47b  lea     rcx, [rbp+1410h+var_EC0]; unsigned __int16 *
0x18000c482  call    ?GetFirefoxBookmarksFilePath@@YAJPEAGK@Z; GetFirefoxBookmarksFilePath(ushort *,ulong)
0x18000c487  mov     ebx, eax
0x18000c489  test    eax, eax
0x18000c48b  js      loc_18000C613
0x18000c491  xor     eax, eax
0x18000c493  lea     rdx, [rbp+1410h+sz]; lpsz
0x18000c497  mov     r8d, 80h; cchMax
0x18000c49d  mov     [rbp+1410h+sz], ax
0x18000c4a1  mov     rcx, rsi; rguid
0x18000c4a4  call    cs:__imp_StringFromGUID2
0x18000c4aa  movaps  xmm0, xmmword ptr cs:aSSSSJsonFirefo; "\"%s\" \"%s\" \"%s\" \"%s\" JSON FIREFO"...
0x18000c4b1  lea     rax, [rbp+1410h+sz]
0x18000c4b5  movaps  xmm1, xmmword ptr cs:aSSSSJsonFirefo+10h; "\" \"%s\" \"%s\" JSON FIREFOX \"%s\""
0x18000c4bc  lea     r9, [rbp+1410h+pszPath]
0x18000c4c3  mov     [rsp+1510h+lpCurrentDirectory], rax
0x18000c4c8  lea     r8, [rbp+1410h+var_1430]; unsigned __int16 *
0x18000c4cc  movaps  xmmword ptr [rbp+1410h+var_1430], xmm0
0x18000c4d0  lea     rax, [rbp+1410h+var_EC0]
0x18000c4d7  movaps  xmm0, xmmword ptr cs:aSSSSJsonFirefo+20h; "%s\" JSON FIREFOX \"%s\""
0x18000c4de  lea     rcx, [rbp+1410h+CommandLine]; unsigned __int16 *
0x18000c4e5  movaps  [rbp+1410h+var_1410], xmm0
0x18000c4e9  mov     edx, 53Ah; unsigned __int64
0x18000c4ee  movups  xmm0, xmmword ptr cs:aSSSSJsonFirefo+3Ch; "OX \"%s\""
0x18000c4f5  mov     [rsp+1510h+lpEnvironment], rdi
0x18000c4fa  mov     qword ptr [rsp+1510h+dwCreationFlags], rax
0x18000c4ff  lea     rax, [rbp+1410h+var_CB0]
0x18000c506  movaps  [rbp+1410h+var_1420], xmm1
0x18000c50a  movaps  xmm1, xmmword ptr cs:aSSSSJsonFirefo+30h; " FIREFOX \"%s\""
0x18000c511  movaps  xmmword ptr [rbp+1410h+var_1400], xmm1
0x18000c515  movups  xmmword ptr [rbp+1410h+var_1400+0Ch], xmm0
0x18000c519  mov     qword ptr [rsp+1510h+bInheritHandles], rax
0x18000c51e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c523  mov     ebx, eax
0x18000c525  test    eax, eax
0x18000c527  js      loc_18000C613
0x18000c52d  xor     edx, edx; Val
0x18000c52f  lea     rcx, [rsp+1510h+StartupInfo+4]; void *
0x18000c534  lea     r8d, [rdx+64h]; Size
0x18000c538  call    memset_0
0x18000c53d  xor     eax, eax
0x18000c53f  mov     [rsp+1510h+StartupInfo.cb], 68h ; 'h'
0x18000c547  mov     qword ptr [rsp+1510h+ProcessInformation.dwProcessId], rax
0x18000c54c  lea     rdx, [rbp+1410h+CommandLine]; lpCommandLine
0x18000c553  lea     rax, [rsp+1510h+ProcessInformation]
0x18000c558  xorps   xmm0, xmm0
0x18000c55b  mov     [rsp+1510h+lpProcessInformation], rax; lpProcessInformation
0x18000c560  xor     r9d, r9d; lpThreadAttributes
0x18000c563  lea     rax, [rsp+1510h+StartupInfo]
0x18000c568  xor     r8d, r8d; lpProcessAttributes
0x18000c56b  mov     [rsp+1510h+lpStartupInfo], rax; lpStartupInfo
0x18000c570  xor     ecx, ecx; lpApplicationName
0x18000c572  mov     [rsp+1510h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18000c57b  mov     [rsp+1510h+lpEnvironment], 0; lpEnvironment
0x18000c584  mov     [rsp+1510h+dwCreationFlags], 0; dwCreationFlags
0x18000c58c  mov     [rsp+1510h+bInheritHandles], 0; bInheritHandles
0x18000c594  movups  xmmword ptr [rsp+1510h+ProcessInformation.hProcess], xmm0
0x18000c599  call    cs:__imp_CreateProcessW
0x18000c59f  test    eax, eax
0x18000c5a1  jz      short loc_18000C5FE
0x18000c5a3  mov     rcx, [rsp+1510h+ProcessInformation.hProcess]; hHandle
0x18000c5a8  mov     edx, 3A98h; dwMilliseconds
0x18000c5ad  call    cs:__imp_WaitForSingleObject
0x18000c5b3  test    eax, eax
0x18000c5b5  jz      short loc_18000C5E6
0x18000c5b7  cmp     eax, 102h
0x18000c5bc  jnz     short loc_18000C5C5
0x18000c5be  mov     ebx, 8000FFFFh
0x18000c5c3  jmp     short loc_18000C5E6
0x18000c5c5  cmp     eax, 0FFFFFFFFh
0x18000c5c8  jnz     short loc_18000C5E1
0x18000c5ca  call    cs:__imp_GetLastError
0x18000c5d0  mov     ebx, eax
0x18000c5d2  test    eax, eax
0x18000c5d4  jle     short loc_18000C5E6
0x18000c5d6  movzx   ebx, ax
0x18000c5d9  or      ebx, 80070000h
0x18000c5df  jmp     short loc_18000C5E6
0x18000c5e1  mov     ebx, 80004005h
0x18000c5e6  mov     rcx, [rsp+1510h+ProcessInformation.hProcess]; hObject
0x18000c5eb  call    cs:__imp_CloseHandle
0x18000c5f1  mov     rcx, [rsp+1510h+ProcessInformation.hThread]; hObject
0x18000c5f6  call    cs:__imp_CloseHandle
0x18000c5fc  jmp     short loc_18000C613
0x18000c5fe  call    cs:__imp_GetLastError
0x18000c604  mov     ebx, eax
0x18000c606  test    eax, eax
0x18000c608  jle     short loc_18000C613
0x18000c60a  movzx   ebx, ax
0x18000c60d  or      ebx, 80070000h
0x18000c613  mov     eax, ebx
0x18000c615  mov     rcx, [rbp+1410h+var_20]
0x18000c61c  xor     rcx, rsp; StackCookie
0x18000c61f  call    __security_check_cookie
0x18000c624  mov     rbx, [rsp+1510h+arg_0]
0x18000c62c  add     rsp, 1500h
0x18000c633  pop     rdi
0x18000c634  pop     rsi
0x18000c635  pop     rbp
0x18000c636  retn
```
